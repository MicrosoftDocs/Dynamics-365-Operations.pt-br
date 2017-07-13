---
title: "Atualização de dados em um ambiente sandbox"
description: "Este tópico explica como realizar uma atualização de dados do AX 2012 para o Dynamics 365 for Finance and Operations em um ambiente sandbox."
author: tariqbell
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Operations, UnifiedOperations, Platform
ms.search.region: Global
ms.author: tabell
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: Platform update 8
ms.translationtype: Human Translation
ms.sourcegitcommit: 6816e3820ab77c71bbf9bde4a068375448331671
ms.openlocfilehash: 7140bf740f37a5eb970a5103750a7095d12a33cc
ms.contentlocale: pt-br
ms.lasthandoff: 06/15/2017

---

# <a name="data-upgrade-in-a-sandbox-environment"></a>Atualização de dados em um ambiente sandbox

[!include[banner](../includes/banner.md)]

[!include[upgrade banner](../includes/upgrade-banner.md)]

O resultado desta tarefa é um banco de dados atualizado que você pode usar em um ambiente sandbox. Um ambiente sandbox é um ambiente onde os usuários empresariais e os membros da equipe funcional podem validar a funcionalidade do aplicativo. Esta funcionalidade inclui personalizações e os dados que foram trazidos a partir do Microsoft Dynamics AX 2012.

Recomendamos encarecidamente que você execute o processo de atualização de dados em um ambiente de desenvolvimento antes de executá-lo em um ambiente sandbox compartilhado, porque essa abordagem ajudará a reduzir o tempo total necessário para uma atualização de dados bem-sucedida. Para obter mais informações, consulte [Atualização de dados em um ambiente de desenvolvimento](prepare-data-upgrade.md).

## <a name="overview-of-the-sandbox-data-upgrade-process"></a>Visão geral do processo de atualização de dados do sandbox

Antes de começar a atualizar dados em um ambiente sandbox, você já terá atualizado os dados em um ambiente de desenvolvimento, conforme explicado em [Atualização de dados em um ambiente de desenvolvimento](prepare-data-upgrade.md). Os dois processos são muito semelhantes. A principal diferença é que um ambiente sandbox usa o Microsoft Azure SQL Database para armazenamento de dados, enquanto um ambiente de desenvolvimento usa o Microsoft SQL Server. Essa diferença técnica na camada do banco de dados requer que você modifique o procedimento de atualização de dados ligeiramente em um ambiente sandbox, porque um backup da instância do banco de dados AX 2012 não pode ser restaurado apenas no banco de dados SQL.

![Processo de atualização de dados do sandbox](./media/data-upgrade-sandbox.png)

Veja aqui as etapas de alto nível no processo de atualização.

1. Crie uma cópia do banco de dados do AX 2012. Recomendamos que você use uma cópia, porque você deve excluir alguns objetos na cópia que serão exportados.
2. Exporte o banco de dados copiado para um arquivo bacpac usando uma ferramenta SQL Server gratuita chamada SQLPackage.exe. Esta ferramenta fornece um tipo especial de backup do banco de dados que pode ser importado para o banco de dados SQL.
3. Carregue o arquivo bacpac no armazenamento Azure.
4. Faça o download do arquivo bacpac na máquina do Servidor de Objetos de Aplicação (AOS) no ambiente sandbox e, em seguida, importe-o usando o SQLPackage.exe. Você deve então executar um script contra o banco de dados importado para redefinir os usuários do banco de dados SQL.
5. Execute o pacote MajorVersionDataUpgrade.zip para executar a atualização de dados contra o banco de dados importado.

## <a name="create-a-copy-of-the-ax-2012-database"></a>Crie uma cópia do banco de dados do AX 2012

Você deve criar uma cópia do banco de dados do AX 2012 que você está atualizando, porque você deve excluir alguns objetos do banco de dados. Esses objetos incluem qualquer usuário de autenticação do Microsoft Windows. Essas mudanças tornam o banco de dados modificado inutilizável para o AX 2012. Durante esta etapa, você criará uma cópia do banco de dados e excluirá esses objetos.

Essa etapa deve ser executada pelo administrador do banco de dados (DBA) ou por uma pessoa que tenha conhecimento e experiência semelhantes.

Para criar uma cópia de banco de dados, faça um backup do banco de dados original e restaure-o com um novo nome. Certifique-se de que esteja disponível espaço suficiente para ambos os bancos de dados. Você pode criar a cópia em um servidor diferente. A versão da instância do SQL Server que executa o banco de dados não é importante.

Veja aqui um exemplo do código que cria uma cópia de banco de dados. Você deve modificar este exemplo para refletir seus nomes de banco de dados específicos.

    BACKUP DATABASE [AxDB] TO  DISK = N'D:\Backups\axdb_copyForUpgrade.bak' WITH NOFORMAT, NOINIT,  
    NAME = N'AxDB_copyForUpgrade-Full Database Backup', SKIP, NOREWIND, NOUNLOAD, COMPRESSION,  STATS = 10
    GO

    RESTORE DATABASE [AxDB_copyForUpgrade] FROM  DISK = N'D:\Backups\axdb_copyForUpgrade.bak'   WITH  FILE = 1,  
    MOVE N'AXDBBuild_Data' TO N'F:\MSSQL_DATA\AxDB_copyForUpgrade.mdf',  
    MOVE N'AXDBBuild_Log' TO N'G:\MSSQL_LOGS\AxDB_CopyForUpgrade.ldf',  
    NOUNLOAD,  STATS = 5

Após a criação da cópia, execute o seguinte script Transact-SQL (T-SQL) contra ela.
TAREFA 

### <a name="export-the-copied-database-to-a-bacpac-file"></a>Exporte o banco de dados copiado para um arquivo bacpac

Exporte o banco de dados copiado para um arquivo bacpac usando a ferramenta SQLPackage.exe. Este passo deve ser feito pelo DBA ou por um membro da equipe que tenha conhecimento equivalente.

É muito importante que você instale a versão mais recente do SQL Server Management Studio antes de iniciar esta etapa. Embora o SQLPackage esteja presente em versões anteriores do Management Studio, ele não funcionará corretamente para esta etapa, a menos que você primeiro instale a versão mais recente.

Essa etapa é importante, porque a exportação terá que ser feita novamente durante o tempo de inatividade antes do início da vida. Veja aqui alguns dicas:

- O processo de bacpac utiliza muito E/S e CPU. Portanto, execute a exportação em uma máquina de alto desempenho.
- O SQLPackage deve ser executado localmente na máquina que hospeda o banco de dados. Não execute o SQLPackage em um laptop local que você conecta à máquina do banco de dados, porque este processo também consome muita rede.

Em seguida, abra uma janela **Prompt de Comando** como um administrador e execute os seguintes comandos.

    cd C:\Program Files (x86)\Microsoft SQL Server\130\DAC\bin\

    SqlPackage.exe /a:export /ssn:localhost /sdn:<database to export> /tf:D:\Exportedbacpac\my.bacpac /p:CommandTimeout=1200 /p:VerifyFullTextDocumentTypesSupported=false

Veja aqui uma explicação dos parâmetros:

- **ssn** (nome do servidor de origem) – o nome do SQL Server de exportação. Para o nosso processo, este parâmetro sempre deve ser definido como **localhost**.
- **sdn** (nome do banco de dados de origem) – O nome do banco de dados a ser exportado.
- **tf** (arquivo de destino) – O caminho e o nome do arquivo a ser exportado. A pasta já deve existir, mas o arquivo será criado pelo processo.
- **/p: CommandTimeout** – O valor de limite por consulta. Este parâmetro permite que as tabelas maiores sejam exportadas sem atingir um tempo limite.

### <a name="upload-the-bacpac-file-to-azure-storage"></a>Carregue o arquivo bacpac no armazenamento Azure

Carregue o arquivo bacpac no armazenamento Azure. Consulte UsingStorageExplorer.docx

### <a name="import-the-bacpac-file-into-sql-database"></a>Importe o arquivo bacpac no banco de dados SQL

Durante esta etapa, você importará o arquivo bacpac exportado para a instância do banco de dados SQL que o ambiente de sandbox usa. Você deve primeiro instalar a versão mais recente do Management Studio na sua máquina AOS sandbox. Em seguida, você importará o arquivo usando a ferramenta SQLPackage.exe.

Você executará essas tarefas diretamente na máquina AOS no seu ambiente sandbox, porque existem regras de firewall que restringem o acesso à instância do banco de dados SQL. No entanto, ao usar a máquina AOS, você pode obter acesso.

Quanto ao passo de exportação, você deve ter a versão mais recente do Management Studio antes de iniciar a importação. Esta etapa não funcionará se você tiver uma versão mais antiga.

Por razões de desempenho, recomendamos que você coloque o arquivo bacpac na unidade D na máquina AOS. Nas máquinas virtuais Azure (VMs), a unidade D é um disco físico que normalmente possui um desempenho maior do que outros discos disponíveis.

Abra uma janela **Prompt de Comando** como um administrador e execute os seguintes comandos.

    cd C:\Program Files (x86)\Microsoft SQL Server\130\DAC\bin\

    SqlPackage.exe /a:import /sf:D:\Exportedbacpac\my.bacpac /tsn:<azure sql database server name>.database.windows.net /tu:sqladmin /tp:<password from LCS> /tdn:<New database name> /p:CommandTimeout=1200 /p:DatabaseEdition=Premium /p:DatabaseServiceObjective=P1

Veja aqui uma explicação dos parâmetros:

- **tsn** (nome do servidor de destino) – O nome do servidor de SQL Azure no qual a importação será realizada. O nome pode ser encontrado no LCS. Adicione o sufixo **.database.windows.net** a ele.
- **tdn** (nome do banco de dados de destino) – O nome do banco de dados no qual a importação ocorrerá. O banco de dados não pode ser um já existente. O processo de importação irá criá-lo.
- **sf** (arquivo de origem) – O caminho e o nome do arquivo a partir do qual a importação ocorrerá.
- **tp** (senha de destino) – A senha de SQL para a instância de banco de dados SQL de destino.
- **tu** (usuário de destino) – O nome de usuário de SQL para a instância de banco de dados SQL de destino. É recomendável usar **sqladmin**. Você pode recuperar a senha desse usuário do seu projeto LCS.
- **/p: CommandTimeout** – O valor de limite por consulta. Este parâmetro permite que as tabelas maiores sejam exportadas sem atingir um tempo limite.
- **/p:DatabaseServiceObjective** – O nível de camada de serviço do banco de dados que é criado. Você pode verificar o valor do banco de dados existente usando o Management Studio. Clique com o botão direito no banco de dados e, em seguida, selecione **Propriedades**.

Depois de executar os comandos, você receberá o seguinte aviso. Você pode ignorá-lo com segurança.

![Erro do sandbox](./media/sandbox-2.png)
 
### <a name="run-the-majorversiondataupgradezip-package"></a>Execute o pacote MajorVersionDataUpgrade.zip

Execute o pacote implementável de atualização de dados conforme descrito em [Atualizar dados em ambientes de desenvolvimento, demo ou sandbox](upgrade-data-to-latest-update.md).

### <a name="upgrade-a-copy-of-the-database-in-a-development-environment"></a>Atualize uma cópia do banco de dados em um ambiente de desenvolvimento

É útil atualizar o mesmo banco de dados em um ambiente de desenvolvimento. Se você tiver uma cópia do banco de dados disponível para ambientes de desenvolvimento, será muito mais fácil investigar os erros encontrados no ambiente sandbox atualizado.

