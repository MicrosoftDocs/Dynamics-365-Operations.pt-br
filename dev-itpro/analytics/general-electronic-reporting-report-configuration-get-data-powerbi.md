---
title: "Relatório eletrônico de instalação para fornecer o power BI com dados do 365 para operações"
description: "Este tópico explica como você pode usar suas configurações de ER (Relatório eletrônico) para organizar a transferência de dados da sua instância do Dynamics 365 for Operations para os serviços do Power BI. Como exemplo, este tópico usa transações intrastat como os dados comerciais que devem ser transferidos. A visualização de mapa do Power BI usa esses dados de transação intrastat para apresentar uma exibição para a análise das atividades de importação/exportação da empresa no relatório do Power BI."
author: kfend
manager: AnnBe
ms.date: 2016-10-31 13 - 22 - 29
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Operations, Core
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: ed0192c44b6d7e88120c64e539ebb0ac3b379831
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-electronic-reporting-to-provide-power-bi-with-data-from-dynamics-365-for-operations"></a>Relatório eletrônico de instalação para fornecer o power BI com dados do 365 para operações

Este tópico explica como você pode usar suas configurações de ER (Relatório eletrônico) para organizar a transferência de dados da sua instância do Dynamics 365 for Operations para os serviços do Power BI. Como exemplo, este tópico usa transações intrastat como os dados comerciais que devem ser transferidos. A visualização de mapa do Power BI usa esses dados de transação intrastat para apresentar uma exibição para a análise das atividades de importação/exportação da empresa no relatório do Power BI.

<a name="overview"></a>Visão Geral
--------

O Microsoft Power BI é uma coleção de serviços de software, aplicativos e conectores que funcionam juntos para transformar fontes externas de dados em informações coerentes, visualmente imersivas e interativas. O ER (Relatório eletrônico) permite que os usuários do Microsoft Dynamics 365 for Operations configurem fontes de dados e organizem a transferência de dados do Dynamics 365 for Operations para o Power BI com facilidade. Os dados são transferidos como arquivos no formato de planilha OpenXML (arquivo de pasta de trabalho do Microsoft Excel). Os arquivos transferidos são armazenados em um Microsoft SharePoint Server configurado para essa finalidade. Os arquivos armazenados são usados no Power BI para criar relatórios que incluem visualizações (tabelas, gráficos, mapas, etc.). Os relatórios do Power BI são compartilhados com os usuários do Power BI e são acessados nos painéis do Power BI e nas páginas do Dynamics 365 for Operations. Este tópico explica as seguintes tarefas:

-   Configurar o Dynamics 365 for Operations.
-   Preparar sua configuração de formato ER para obter dados do Dynamics 365 for Operations.
-   Configurar o ambiente do ER para transferir dados para o Power BI.
-   Usar os dados transferidos para criar um relatório do Power BI.
-   Tornar o relatório do Power BI acessível no Dynamics 365 for Operations.

## <a name="prerequisites"></a>Pré-requisitos
Para concluir os exemplos neste tópico, você deve ter:

-   Acesso ao Dynamics 365 for Operations para uma das seguintes funções:
    -   Desenvolvedor de relatório eletrônico
    -   Consultor funcional de relatório eletrônico
    -   Administrador do sistema
-   Acesso ao SharePoint Server configurado para uso com o Dynamics 365 for Operations
-   Acesso à estrutura do Power BI

## <a name="configure-document-management-parameters"></a>Configurar parâmetros de gerenciamento de documentos
1.  Na página **Parâmetros de gerenciamento de documentos**, configure o acesso ao SharePoint Server que será usado na empresa à qual você está conectado (a empresa de DEMF neste exemplo.)
2.  Teste a conexão com o SharePoint Server para certificar-se de que você tem acesso. [página parâmetros de gerenciamento![documentos do![(]. /media/ger-power-bi-sharepoint-server-setting-1024x369.png)](. /media/ger-power-bi-sharepoint-server-setting.png)
3.  Abra o site do SharePoint configurado. Crie uma nova pasta onde o ER armazenará os arquivos do Excel com os dados comerciais que os relatórios do Power BI exigem como uma fonte de conjunto de dados do Power BI.
4.  No Dynamics 365 for Operations, na página **Tipos de documento**, crie um novo tipo de documento que será usado para acessar a pasta do SharePoint que você acabou de criar. Insira **Arquivo** no campo **Grupo** e **SharePoint** no campo **Localização** e, em seguida, insira o endereço da pasta do SharePoint. [página tipos de documento do![(]. /media/ger-power-bi-sharepoint-document-type-1024x485.png)](. /media/ger-power-bi-sharepoint-document-type.png)

## <a name="configure-er-parameters"></a>Configurar parâmetros de ER
1.  No espaço de trabalho do **Relatório eletrônico**, clique no link **Parâmetros de relatório eletrônico**.
2.  Na guia **Anexos**, selecione o tipo de documento **Arquivo** para todos os campos.
3.  No espaço de trabalho do **Relatório eletrônico**, ative o provedor exigido clicando em **Definir como ativo**. Para saber mais, execute o guia de tarefas **ER Selecionar provedor de serviços**.

## <a name="use-an-er-data-model-as-the-source-of-data"></a>Usar um modelo de dados ER como a fonte de dados
Você deve ter um modelo de dados ER como a fonte dos dados comerciais que serão usados nos relatórios do Power BI. Esse modelo de dados é carregado do repositório de configurações de ER. Para saber mais, consulte [Baixar configurações do Relatório eletrônico do Lifecycle Services](download-electronic-reporting-configuration-lcs.md) ou execute o guia de tarefas **ER Importar uma configuração do Lifecycle Services**. Selecione **Intrastat **como o modelo de dados que será carregado do repositório de configurações de ER selecionado. (Neste exemplo, a versão 1 de modelo usada.) Você poderá acessar ** intrastat ** a configuração de modelo ER ** configurações ** na página. [página configurações![(]. /media/ger-power-bi-data-model-1024x371.png)](. /media/ger-power-bi-data-model.png)

## <a name="design-an-er-format-configuration"></a>Criar uma configuração de formato ER
Você deve criar uma nova configuração de formato ER que usa o modelo de dados **Intrastat** como a fonte de dados comerciais. Essa configuração de formato deve gerar resultados de saída como documentos eletrônicos no formato OpenXML (arquivo do Excel). Para saber mais, execute o guia de tarefas **ER Criar uma configuração para relatórios no formato OPENXML**. Nomeie a nova configuração **Atividades de importação/exportação** conforme mostrado na ilustração. Use o arquivo Excel [Dados de ER – detalhes de importação e exportação](https://go.microsoft.com/fwlink/?linkid=845208) como modelo ao criar o formato ER. (Para obter informações sobre como importar um modelo de formato, execute o guia de tarefa.) [] configuração (mídia atividades de exportação/importação do![)/ger-power-bi-format-configuration.png]mídia (/) ger-power-bi-format-configuration.png modificar ** atividades de exportação/importação ** formatam a configuração, acompanham essas etapas.

1.  Clique em **Designer**.
2.  Na guia **Formato**, nomeie o elemento de arquivo para o formato como **Arquivo de saída do Excel**. [elemento de arquivo de saída do![Excel (]. /media/ger-power-bi-format-configuration-file-element-name-1024x395.png)](. /media/ger-power-bi-format-configuration-file-element-name.png)
3.  Na guia **Mapeamento**, especifique o nome do arquivo do Excel que será gerado sempre que esse formato for executado. Configure a expressão relacionada para retornar o valor **Detalhes de importação/exportação** (a extensão do nome de arquivo .xlsx será adicionada automaticamente). [![Format designer](./media/ger-power-bi-format-configuration-output-file-name-1024x396.png)](./media/ger-power-bi-format-configuration-output-file-name.png)
4.  Adicione um novo item de fonte de dados para esse formato. (Esta enumeração será necessária para outras associações de dados.)
    1.  Nomeiam a fonte de dados\_** enums ** de direção.
    2.  Selecione **Enumeração do modelo de dados** como o tipo de fonte de dados.
    3.  Use a enumeração do modelo de dados **Direção** como referência.

    [enums\_a direção (![]. /media/ger-power-bi-format-configuration-mapping-added-enum-1024x454.png)](. /media/ger-power-bi-format-configuration-mapping-added-enum.png)
5.  Conclua a associação de elementos do modelo de dados **Intrastat** e os elementos do formato criado conforme mostrado na ilustração a seguir. [![que completa a associação. (]/media/ger-power-bi-format-configuration-mapping-details-1024x454.png)](. /media/ger-power-bi-format-configuration-mapping-details.png)

Após a execução, o formato ER gera o resultado da saída no formato Excel. Ele envia os detalhes das transações Intrastat para o resultado de saída e separa-os como transações que descrevem atividades de importação ou de exportação. Clique ** execução ** para testar formato do novo ER para a lista das transações intrastat ** intrastat ** na página (** impostos ** &gt; ** declarações ** &gt; ** comércio exterior ** &gt; ** intrastat **). [página intrastat![(]. /media/ger-power-bi-format-test-run-transactions-1024x322.png)](. /media/ger-power-bi-format-test-run-transactions.png) O seguinte resultado de saída é gerado. O nome do arquivo será **Detalhes de importação e exportação.xlsx**, conforme você especificou nas configurações do formato. [importação e exportação do![(details.xlsx]. /media/ger-power-bi-format-test-run-output-1024x472.png)](. /media/ger-power-bi-format-test-run-output.png)

## <a name="configure-the-er-destination"></a>Configurar o destino do ER
Você deve configurar a estrutura do ER para enviar o resultado de saída da nova configuração de formato ER de uma maneira especial.

-   O resultado de saída deve ser enviado para a pasta do SharePoint Server selecionado.
-   Cada execução da configuração de formato deve criar uma nova versão do mesmo arquivo do Excel.

** Relatório eletrônico ** na página administração (** organizacional ** &gt; ** relatório eletrônico **), clique ** destino do relatório eletrônico ** o item, e adicione um novo destino. No campo **Referência**, selecione a configuração de formato **Atividades de importação/exportação** que você criou anteriormente. Siga estas etapas para adicionar um novo registro de destino do arquivo para a referência.

1.  No campo **Nome**, insira o título do destino do arquivo.
2.  No campo **Nome do arquivo**, selecione o nome **Arquivo de saída do Excel** para o componente do formato de arquivo do Excel.

Clique no botão **Configurações** para o novo registro de destino. Em seguida, na caixa de diálogo **Configurações de destino**, siga estas etapas:

1.  Na guia **Power BI**, defina a opção **Habilitado** como **Sim**.
2.  No campo **SharePoint**, selecione o tipo de documento **Compartilhado** que você criou anteriormente.

## <a name="schedule-execution-of-the-configured-er-format"></a>Programar a execução do formato ER configurado
Em configurações ** ** página administração (** organizacional ** &gt; ** relatório eletrônico ** &gt; ** configurações **), a árvore configurações, selecione ** atividades de exportação/importação ** configuração criadas anteriormente. Altere o status da versão 1.1 de **Rascunho** para **Concluído** para tornar o formato disponível para uso. [página configurações![(]. /media/ger-power-bi-format-configuration-complete-1024x401.png)](. /media/ger-power-bi-format-configuration-complete.png) Selecione a versão concluído ** atividades de exportação/importação ** configuração, e em execução. ** ** Observe que o destino configurado será aplicado ao resultado de saída que é gerado no formato Excel. Defina a opção **Processamento em lotes** como **Sim** para executar o relatório no modo autônomo. Clique em **Recorrência** para agendar a recorrência exigida desta execução de lote. A recorrência define a frequência com que os dados atualizados serão transferidos do Dynamics 365 for Operations para o Power BI. [caixa de diálogo eletrônica parâmetros de relatório do![(]. /media/ger-power-bi-format-configuration-run-to-schedule-1024x413.png)](. /media/ger-power-bi-format-configuration-run-to-schedule.png) Após configurado, você poderá encontrar os trabalhos de execução do relatório de ER ** ** trabalhos em lotes na página (** trabalho em lotes consultas &gt; de administração &gt; de sistema **). [página de trabalhos em lotes do![(]. /media/ger-power-bi-format-configuration-running-job-1024x410.png)](. /media/ger-power-bi-format-configuration-running-job.png) Quando esses trabalhos são executados pela primeira vez, o destino cria um novo arquivo de Excel que possui o nome da pasta configurada selecionada de O SharePoint. Cada vez subsequente que o trabalho for executado, o destino criará uma nova versão desse arquivo do Excel. [nova versão do![de arquivo excel (]. /media/ger-power-bi-output-file-in-sharepoint-server-folder-2-1024x412.png)](. /media/ger-power-bi-output-file-in-sharepoint-server-folder-2.png)

## <a name="create-a-power-bi-dataset-by-using-the-output-result-of-the-er-format"></a>Criar um conjunto de dados do Power BI usando o resultado de saída do formato ER
Entre no Power BI e abra um grupo existente do Power BI (espaço de trabalho) ou crie um novo grupo. Clique em adicionar ** ** abaixo ** arquivos ** ** importar ou conectar-se a dados ** na seção, ou clicar no sinal de adição (** **+) ao lado de ** ** conjunto de dados no painel esquerdo. [![que criar um conjunto de dados (]. /media/ger-power-bi-add-dataset-1024x524.png)](. /media/ger-power-bi-add-dataset.png) Selecione ** SharePoint – os sites de equipe ** opção, e digite o caminho do SharePoint Server usada (** https://ax7partner.spoppe.com** em nosso exemplo). Navegue até a pasta **/Documentos compartilhados/Dados GER/PowerBI** e selecione o arquivo do Excel que você criou como a fonte de dados para o novo conjunto de dados do Power BI. [![que selecionar o arquivo excel (]. /media/ger-power-bi-add-dataset-select-excel-file-1024x522.png)](. O clique de /media/ger-power-bi-add-dataset-select-excel-file.png) ** conectar **, clique em importar. ** ** Um novo conjunto de dados será criado com base no arquivo do Excel selecionado. O conjunto de dados também pode ser adicionado automaticamente ao painel recém-criado. [conjunto de dados do![no painel. (]/media/ger-power-bi-added-dataset-1024x489.png)](. /media/ger-power-bi-added-dataset.png) Configurar a agenda de atualização para que este conjunto de dados force uma atualização periódica. As atualizações periódicas habilitam o consumo de novos dados comerciais que vêm do Dynamics 365 for Operations pela execução periódica do relatório de ER por meio das novas versões do arquivo do Excel que são criadas no SharePoint Server.

## <a name="create-a-power-bi-report-by-using-the-new-dataset"></a>Criar um relatório do Power BI usando o novo conjunto de dados
Para criar um novo relatório do Power BI, clique no conjunto de dados do Power BI **Detalhes de importação e exportação** que você criou. Em seguida, configure a visualização. Por exemplo, selecione a visualização **Mapa Coroplético** e configure-o da seguinte maneira:

-   Atribua o campo do conjunto de dados **CountryOrigin** ao campo **Localização** da visualização de mapa.
-   Atribua o campo do conjunto de dados **Valor** ao campo **Saturação da cor** da visualização de mapa.
-   Adicione os campos dos conjuntos de dados **Atividade** e **Ano** à coleção de campos **Filtros** da visualização de mapa.

Salve o relatório do Power BI como **Relatório de detalhes de importação e exportação**. [importação do![e relatório de detalhes de exportação (]. /media/ger-power-bi-added-report-1024x498.png)](. Nota de /media/ger-power-bi-added-report.png) o mapa mostra os países/regiões mencionados em arquivo excel (áustria e a Suíça neste exemplo.) Esses países/regiões estão coloridos para mostrar a proporção de valores faturados para cada um. Atualize a lista das transações intrastat. A transação de exportação originada da Itália será adicionada. [lista das transações intrastat![(]. /media/ger-power-bi-new-run-new-transaction-1024x321.png)](. /media/ger-power-bi-new-run-new-transaction.png) De espera para a próxima execução agendado de relatório de ER e atualização programada do conjunto de dados de O power BI. Em seguida, revise o relatório do Power BI (selecione a opção para mostrar as transações de importação somente). O mapa atualizado agora mostrará a Itália. mapa atualizado [] (![. /media/ger-power-bi-new-run-new-map-1024x511.png)](. /media/ger-power-bi-new-run-new-map.png)

## <a name="access-power-bi-report-in-dynamics-365-for-operations"></a>Acessar o relatório do Power BI no Dynamics 365 for Operations
Configurar a integração entre o Dynamics 365 for Operations e o Power BI. Para saber mais, consulte [Configurando a integração do Power BI para espaços de trabalho](configure-power-bi-integration.md). ** Relatório eletrônico ** na página de área de trabalho que oferece suporte à integração do POWER BI (** administração organizacional ** &gt; ** espaços de trabalho ** &gt; ** o espaço de trabalho eletrônico ** de relatórios), clique ** opções ** &gt; ** catálogo saber ** relatório. Selecione o relatório do Power BI **Detalhes de importação e exportação** que você criou para mostrar esse relatório como um item de ação na página selecionada. Clique no item de ação para abrir a página do Dynamics 365 for Operations que mostra o relatório que você criou no Power BI. [importação do![e relatório de detalhes de exportação (]. /media/ger-power-bi-review-bi-report-in-ax-form-1024x586.png)](. /media/ger-power-bi-review-bi-report-in-ax-form.png)

<a name="see-also"></a>Consulte também
--------

[Destinos de relatório eletrônico](electronic-reporting-destinations.md)

[Visão geral do relatório eletrônico](general-electronic-reporting.md)


