---
title: "Redefinir data mart de relatório financeiro após restaurar um banco de dados"
description: "Este tópico descreve como redefinir o data mart de relatório financeiro após restaurar um banco de dados do Microsoft Dynamics 365 for Finance and Operations."
author: ShylaThompson
manager: AnnBe
ms.date: 08/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 261824
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6e3f78fb2f6528449d2a411225cd0e14ca33443e
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a>Redefinir data mart de relatório financeiro após restaurar um banco de dados

[!include[banner](../includes/banner.md)]


Este tópico descreve como redefinir o data mart de relatório financeiro após restaurar um banco de dados do Microsoft Dynamics 365 for Finance and Operations.

Se restaurar a banco de dados do Finance and Operations a partir de um backup ou copiar o banco de dados de outro ambiente, você deve seguir as etapas deste tópico para garantir que o data mart de relatório financeiro está usando corretamente o banco de dados restaurado do Finance and Operations. 
> [!Note] 
> As etapas deste processo têm suporte na versão de maio de 2016 do Dynamics 365 for Operations (compilação de aplicativo 7.0.1265.23014 e compilação de geração de relatórios financeiros 7.0.10000.4) e versões mais recentes. Se você tiver uma versão anterior do Finance and Operations, contate nossa Equipe de suporte para obter assistência.

## <a name="export-report-definitions"></a>Exportar definições de relatório
Primeiro, exporte os projetos de relatório localizados no Report Designer, usando as seguintes etapas:

1.  No Report Designer, vá para **Empresa** &gt; **Grupos do bloco de construção**.
2.  Selecione o grupo do bloco de construção para exportar, clique em **Exportar**. 

    > [!Note] 
    > Para o Finanças e Operações, apenas um grupo de blocos de construção é suportado, **Padrão**.
    
3.  Selecione as definições de relatório a serem exportadas:
    -   Para exportar todas as definições de relatório e os blocos de construção associados, clique em **Selecionar Tudo**.
    -   Para exportar relatórios, linhas, colunas, árvores ou conjuntos de dimensões específicos, clique na guia apropriada e selecione os itens a serem exportados. Pressione e mantenha pressionada a tecla Ctrl para selecionar vários itens em uma guia. Quando você seleciona relatórios para exportar, as linhas, as colunas, as hierarquias e os conjuntos de dimensões associados são selecionados.

4.  Clique em **Exportar**.
5.  Insira um nome de arquivo e selecione um local seguro onde deseja salvar as definições de relatório exportadas.
6.  Clique em **Salvar**.

O arquivo pode ser copiado ou carregado em um local seguro, permitindo que seja importado em um ambiente em outro momento. Informações sobre como usar uma conta de armazenamento do Microsoft Azure podem ser encontradas em [Transferir dados com o utilitário de linha de comando AzCopy](/azure/storage/storage-use-azcopy). 
> [!NOTE]
> A Microsoft não fornece uma conta de armazenamento como parte do seu contrato do Finanças e Operações. Você deve comprar uma conta de armazenamento ou usar uma conta de armazenamento de uma subscrição separada do Azure. 
> [!WARNING]
> Esteja ciente do comportamento da unidade D no Azure Virtual Machines. Não mantenha seus grupos de blocos de construção exportados aqui permanentemente. Para obter mais informações sobre unidades temporárias, consulte [Entendendo a unidade temporária nas máquinas virtuais do Windows Azure](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).

## <a name="stop-services"></a>Interromper serviços
Use a Área de Trabalho Remota para se conectar a todos os computadores no ambiente e parar os seguintes serviços do Windows usando services.msc:

-   Serviço de publicação na Web (em todos os computadores AOS)
-   Gerenciamento de Lotes do Microsoft Dynamics 365 for Finance and Operations (somente em computadores AOS não particulares)
-   Serviço de Processamento do Management Reporter 2012 (somente computadores BI)

Esses serviços terão conexões abertas com o banco de dados do Finanças e Operações.

## <a name="reset"></a>Redefinir
### <a name="locate-and-download-the-latest-minorversiondataupgradezip-package"></a>Localizar e baixar o pacote MinorVersionDataUpgrade.zip mais recente

Localize o pacote MinorVersionDataUpgrade.zip mais recente usando as instruções encontradas em [Baixar o pacote implantável de atualização de dados mais recente](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages). As instruções explicam como localizar e baixar a versão correta do pacote de atualização de dados. Não é necessária uma atualização para baixar o pacote MinorVersionDataUpgrade.zip. Basta concluir as etapas na seção "Baixar o pacote implantável de atualização de dados mais recente" sem executar nenhuma das outras etapas no artigo para recuperar uma cópia do pacote MinorVersionDataUpgrade.zip.

### <a name="execute-scripts-against-finance-and-operations-database"></a>Executar scripts no banco de dados do Finanças e Operações

Execute os seguintes scripts no banco de dados do Finanças e Operações (não no banco de dados de relatórios financeiros).

-   DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql
-   DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql

Esses scripts garantem que os usuários, as funções e as configurações de controle de alterações estejam corretas.

### <a name="execute-powershell-command-to-reset-database"></a>Execute o comando PowerShell para redefinir o banco de dados.

No computador AOS, execute os seguintes comandos no PowerShell como Administrador para redefinir a integração entre o Finance and Operations e os relatórios financeiros:

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail “<my reason for resetting>”

```
> [!NOTE]
> Depois de executar os comandos, será solicitado que você pressione “Y” para confirmar.

Explicação dos parâmetros:

-   Os valores válidos para -Reason são: SERVICING, BADDATA, OTHER.
-   O parâmetro -ReasonDetail é texto livre.
-   A razão e o reasonDetail serão registrados em telemetria/monitoramento de ambiente.

## <a name="start-services"></a>Iniciar serviços
Use o services.msc para reiniciar os serviços que você interrompeu anteriormente:

-   Serviço de publicação na Web (em todos os computadores AOS)
-   Gerenciamento de Lotes do Microsoft Dynamics 365 for Finance and Operations (somente em computadores AOS não particulares)
-   Serviço de Processamento do Management Reporter 2012 (somente computadores BI)

## <a name="import-report-definitions"></a>Importar definições de relatório
Importe seus designs de relatório do Report Designer, usando o arquivo criado durante a exportação:

1.  No Report Designer, vá para **Empresa** &gt; **Grupos do bloco de construção**.
2.  Selecione o grupo do bloco de construção para exportar, clique em **Exportar**. 

    > [!NOTE]
    > Para o Finanças e Operações, apenas um grupo de blocos de construção é suportado, **Padrão**.
    
3.  Selecione o bloco de construção **Padrão** e clique em **Importar**.
4.  Selecione o arquivo que contém as definições de relatório exportadas e clique em **Abrir**.
5.  Na caixa de diálogo Importar, selecione as definições de relatório para importação:
    -   Para importar todas as definições de relatório e os blocos de construção de suporte, clique em **Selecionar Tudo**.
    -   Para importar relatórios, linhas, colunas, árvores ou conjuntos de dimensões específicos, selecione os relatórios, as linhas, as colunas, as árvores ou os conjuntos de dimensões a serem importados.

6.  Clique em **Importar**.





