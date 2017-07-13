---
title: Atualizar teste de fechamento
description: "Este tópico explica como testar as tarefas que ocorrem depois de desativar o AX 2012, mas antes de ativar o Dynamics 365 for Finance and Operations, Enterprise Edition."
author: tariqbell
manager: AnnBe
ms.date: 05/29/2017
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
ms.openlocfilehash: 711ad5cc3aafacf209704349effb4e08019205ac
ms.contentlocale: pt-br
ms.lasthandoff: 06/15/2017

---

# <a name="upgrade-cutover-testing"></a>Atualizar teste de fechamento

[!include[banner](../includes/banner.md)]

[!include[upgrade banner](../includes/upgrade-banner.md)]

*Fechamento* é o termo que usamos para o processo final de conseguir um novo sistema ao vivo. Este processo de fechamento consiste nas tarefas que ocorrem depois que o Microsoft Dynamics AX 2012 estiver desativado, mas antes que o Microsoft Dynamics 365 for Finanças e Operações, Enterprise Edition, esteja ativado. O objetivo do teste de fechamento de atualização é praticar o processo de fechamento, para ajudar a garantir uma experiência suave para todos os envolvidos durante o corte real para a ativação.

Há dois fluxos de trabalho principais durante um fechamento:

- **Fluxo de trabalho técnico** – Este fluxo de trabalho inclui execução do processo de atualização de dados. Sua empresa aplicará um limite na quantidade de tempo de inatividade permitido. Durante este período de inatividade, nem o AX 2012 nem Finanças e Operações estarão disponíveis. Este fluxo de trabalho pode ter que ajustar o procedimento de atualização de dados para atender ao limite de tempo de inatividade da empresa.
- **Fluxo de trabalho funcional** – Este fluxo de trabalho inclui as tarefas de configuração que são executadas após a atualização de dados ser concluída. Todas essas tarefas devem ser documentadas e quantificadas, e um recurso deve ser atribuído, porque o fluxo de trabalho funcional e o fluxo de trabalho técnico devem caber dentro do limite de tempo de inatividade da empresa.

A ilustração a seguir mostra o processo geral do corte para a ativação, pois ele ocorrerá no ambiente de produção.

![Processo de fechamento](./media/cutover_1.png)

Esse processo de fechamento difere de uma atualização de dados básicos em um ambiente do sandbox das seguintes maneiras:

- O banco de dados do AX 2012 não é copiado, mas é salvo e, em seguida, o banco de dados original é modificado Essa abordagem é mais rápida, e o backup fornece rollback, se for necessária uma reversão.
- Como o ambiente de produção para Finanças e Operações tem acesso restrito, as tarefas que foram executadas anteriormente na instância sandbox do Application Object Server (AOS) são agora executadas pela equipe Microsoft DSE. Essas tarefas incluem baixar e importar o arquivo bacpac e executar o pacote MajorversionDataUpgrade.zip.
- Nós adicionamos as seguintes tarefas:

    - Executar um teste de fumaça.
    - Concluir as tarefas de configuração do aplicativo. Este passo pode ser grande, dependendo da funcionalidade que é usada. Durante esta etapa, a equipe funcional configura a nova funcionalidade do aplicativo de modo que esteja pronta para ser usada no sistema atualizado.
    - Permitir que os usuários voltem a entrar. Notifique a sua base de usuários que a atualização está concluída e que eles podem usar o sistema novamente.

## <a name="technical-workstream"></a>Fluxo de trabalho técnico

O fluxo de trabalho técnico envolve vários membros da equipe técnica: o administrador do banco de dados (DBA), o administrador do sistema AX 2012, administradores de servidores e desenvolvedores que estão familiarizados com o AX 2012 e Finanças e Operações. Este tópico irá explicar quais tarefas envolvem quais funções.

Durante o teste de fechamento, a equipe técnica fica focada em testes de desempenho e confiabilidade do processo de atualização de dados, para garantir que ele atenda o limite de tempo de inatividade da empresa Muitos elementos de hardware e software estão envolvidos neste processo. Alguns desses elementos estão no local, enquanto outros estão na nuvem da Microsoft. Além disso, muitos elementos do código de aplicativo personalizado e código padrão estão envolvidos. O resultado desse teste deve ser a confiança no processo de fechamento para o seu ambiente.

### <a name="turn-off-the-ax-2012-aos-instances"></a>Desative as instâncias do AX 2012 AOS

Esta tarefa envolve o administrador do sistema AX 2012 e os administradores do servidor.

As seguintes áreas devem ser validadas:

- **Trabalhos em lote que estão sendo executados no momento do fechamento** – Um trabalho em lote de longa duração que já começou a ser executado impedirá o sistema de parar. Planeje com antecedência, para que você possa interromper suas instâncias AOS no momento desejado. Você pode ter que agendar lotes para que eles sejam concluídos algum tempo antes de desativar o AX 2012.
- **Sistemas integrados** – Você pode ter outros sistemas integrados ao ambiente AX 2012 Você deve fatorar esses sistemas em seu plano para desativar o AX 2012. Por exemplo, você pode ter que desligar os sistemas integrados algum tempo antes de desligar o próprio AX 2012, para que quaisquer transações restantes em andamento possam ser concluídas Os requisitos para sistemas integrados variam amplamente de negócio para negócio. Portanto, sua equipe de especialistas deve planejar esse cenário de forma independente.

### <a name="create-a-backup-of-the-ax-2012-database"></a>Crie um backup do banco de dados AX 2012

Esta tarefa envolve o DBA. O backup será usado se uma reversão for necessária. Ele também será usado como um ponto de referência que será mantido por um período e mostrará o estado do sistema no momento do fechamento.

As seguintes áreas devem ser validadas:

- As seguintes áreas devem ser validadas:
- Ajuste as opções de backup usadas (por exemplo, compressão versus não compressão), para ajudar a garantir o backup mais rápido possível.

### <a name="export-the-database-to-bacpac"></a>Exportar o banco de dados para bacpac

Esta tarefa envolve o DBA. O resultado desta tarefa é o arquivo de exportação que será carregado no Microsoft Azure para o novo sistema.

As seguintes áreas devem ser validadas:

- As seguintes áreas devem ser validadas:
- Otimize o processo de exportação para ajudar a garantir a experiência o mais rápido possível. A otimização pode exigir as seguintes tarefas:

    - Medir recursos do sistema durante a exportação, como CPU, E/S de disco e memória.
    - Se forem encontrados gargalos de recursos, crie um plano para mitigar os mesmos. Normalmente, você irá mitigar esses estrangulamentos atribuindo mais recursos necessários.

### <a name="upload-the-bacpac-file-to-azure-storage"></a>Carregue o arquivo bacpac no armazenamento Azure

Esta tarefa envolve o DBA ou os administradores do servidor. Durante esta tarefa, o arquivo bacpac é movido para o Azure.

As seguintes áreas devem ser validadas:

- Selecione a máquina que será usada para carregar e certifique-se de que a ferramenta do explorador de armazenamento do Azure esteja configurada e pronta para usar.
- Obtenha horários concretos para o processo de upload, medindo-o várias vezes. Os tempos de upload variam, com base na velocidade da sua conexão com a Internet e na localização geográfica do datacenter Azure em relação à sua localização.

### <a name="download-and-import-the-bacpac-file-to-the-azure-sql-database"></a>Baixe e importe o arquivo bacpac no banco de dados Azure SQL

Quando esta tarefa ocorrer na ativação, ela será realizada pela equipe Microsoft DSE. Entretanto, durante os testes de fechamento, ela envolve o DBA. O resultado desta tarefa é o arquivo de exportação que será carregado no Azure para o novo sistema.

As seguintes áreas devem ser validadas:

- Obtenha horários concretos para o processo de importação.
- Otimize o processo de exportação para ajudar a garantir a experiência o mais rápido possível. A otimização pode exigir as seguintes tarefas:

    - Medir os recursos do sistema durante a exportação. Eis alguns exemplos:

        - **Na máquina AOS:** CPU, E/S de disco, e memória
        - **Na instância do banco de dados do Azure SQL:** taxa de transferência de banco de dados SQL (DTU). Você pode monitorar a DTU do Azure SQL do Microsoft SQL Server Management Studio na máquina AOS, observando a exibição do sistema sys.dm_resource_stats.

    - Se forem encontrados gargalos de recursos, crie um plano para mitigar os mesmos. Normalmente, você irá mitigar esses estrangulamentos atribuindo mais recursos necessários. Como esta máquina está hospedada na Microsoft, você deve enviar uma solicitação à Microsoft para aumentar os recursos se você identificar que eles são um gargalo.

### <a name="run-the-majorversiondataupgradezip-package"></a>Execute o pacote MajorVersiondataUpgrade.zip

Quando esta tarefa ocorrer na ativação, ela será realizada pela equipe Microsoft DSE. Entretanto, durante os testes de fechamento, ela envolve os desenvolvedores. Durante esta tarefa, a estrutura do banco de dados antigo é transformada na estrutura do novo sistema.

O processo de sincronização do banco de dados é executado como parte desta tarefa. A sincronização do banco de dados pode levar uma quantidade significativa de tempo em algumas situações, como quando um índice agrupado foi alterado em uma tabela, porque esta operação é uma operação dispendiosa em SQL.

Recomendamos que você primeiro execute seu processo de análise e depuração em um ambiente de desenvolvimento. Em um ambiente sandbox, as opções de depuração e análise são mais restritas. O objetivo é ter poucos ou nenhum problema que devem ser resolvidos quando você realiza testes de fechamento.

As seguintes áreas devem ser validadas:

- Obtenha horários concretos para o processo de importação.
- Otimize o processo para ajudar a garantir a experiência mais rápida. A otimização pode exigir as seguintes tarefas:

    - Monitore o desempenho dos scripts de atualização individuais através da tabela ReleaseUpdateScriptsExecution.
    - Ajuste os scripts para otimizar o desempenho. Esta tarefa pode exigir que você personalize o código X++ de um script para otimizar o seu conjunto de dados.
    - Monitore o Azure SQL DTU usando o monitoramento do Microsoft Dynamics Lifecycle Services (LCS) ou a exibição do sistema sys.dm_resources_stats no Management Studio. Se os recursos forem preenchidos, talvez seja necessário solicitar um nível de banco de dados mais alto à equipe Microsoft DSE.

### <a name="roll-back-to-ax-2012"></a>Reverter para o AX 2012

O objetivo desta tarefa é restaurar o banco de dados usando o backup que foi feito quando o AX 2012 foi desativado e, em seguida, ative novamente o AX 2012. O estado dos sistemas integrados também pode ser restaurado. No entanto, como os sistemas integrados variam de empresa para empresa, você deve planejar esse cenário de forma independente, com base em suas circunstâncias específicas. Embora seja improvável que você tenha que reverter, é muito importante que você tenha um processo testado caso você precise.

## <a name="functional-workstream"></a>Fluxo de trabalho funcional

Após a atualização dos dados, várias tarefas de configuração serão necessárias no novo ambiente. O objetivo deste fluxo de trabalho é documentar e quantificar todas as tarefas de configuração e atribuir um recurso a cada tarefa, para garantir que essas tarefas possam ser realizadas junto com o fluxo de trabalho técnico durante a janela de tempo de inatividade.

Normalmente, as tarefas funcionais envolvem a alteração dos valores de parâmetros específicos do sistema ou outros dados de configuração. Essas tarefas são identificadas através da aprovação do teste funcional completo, que é uma atividade separada dos testes de fechamento. Quando uma tarefa desse tipo é identificada, ela deve ser revisada juntamente com o recurso funcional e seu desenvolvedor.

Alterações maiores podem exigir que um novo script personalizado de atualização de dados seja escrito para atualizar os dados durante o processo de atualização de dados. No entanto, o recurso funcional pode executar manualmente alterações menores através do novo sistema após a atualização de dados.

Alterações maiores que tenham novos scripts de atualização de dados devem ser testadas. Portanto, uma ou mais iterações adicionais do pacote MajorVersionDataUpgrade.zip terá que ser executada. É importante que você pese o custo de executar o pacote novamente contra o custo da entrada manual de dados.

Para cada mudança manual, uma tarefa deve ser adicionada ao documento do plano de deslocamento. Esta tarefa deve mostrar os seguintes detalhes:

-   Qual é a tarefa e o que deve ser feito?
-   Quem deve executá-la?
-   Quanto tempo leva?

