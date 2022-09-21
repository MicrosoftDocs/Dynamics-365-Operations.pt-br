---
title: Configurar um fluxo de dados alternativo para recomendações
description: Este artigo descreve como configurar um ambiente usando um fluxo de dados alternativo para fornecer dados ao serviço de recomendações.
author: bebeale
ms.date: 09/08/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.openlocfilehash: b507b9bb57c68aca9424b53f8ccc009efea733bc
ms.sourcegitcommit: f88273627ba105ede27f28fe67ccec2d7f78261c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460155"
---
# <a name="set-up-an-alternate-dataflow-for-recommendations"></a>Configurar um fluxo de dados alternativo para recomendações

[!include [banner](includes/banner.md)]

Este artigo descreve como configurar um ambiente usando um fluxo de dados alternativo para fornecer dados ao serviço de recomendações.

## <a name="comparison-of-out-of-the-box-dataflow-with-alternate-dataflow"></a>Comparação do fluxo de dados pronto para uso com fluxo de dados alternativo

A ilustração a seguir mostra o fluxo de dados pronto para uso em um ambiente.

![Fluxo de dados pronto para uso em um ambiente](media/reco-out-of-the-box-dataflow-2.png)

A ilustração a seguir mostra um fluxo de dados alternativo, no qual o trabalho em lotes de sincronização do armazenamento da entidade é substituído pelas etapas de fluxo de dados alternativo.

![Fluxo de dados alternativo em um ambiente](media/reco-alternate-dataflow-2.png)

## <a name="assumptions"></a>Hipóteses

- Este artigo presume que você já ativou o serviço de recomendações para seu ambiente. Para obter mais informações, consulte [Habilitar recomendações de produto](enable-product-recommendations.md).
- Quando estiver trabalhando com arquivos e pastas na conta do Microsoft Azure Data Lake Storage:

    - Você pode usar a interface do portal da Web do Azure ou o aplicativo Gerenciador de Armazenamento do Azure.
    - Os pontos de partida para trabalhar com arquivos e pastas estão no contêiner **dynamics365 financeandoperations** localizado na pasta que é nomeada para corresponder ao URL do ambiente.
    - Se o nome do seu ambiente de área restrita for **MyUAT**, o URL base do ambiente será `myuat.sandbox.operations.dynamics.com`.
    - Se mais de um ambiente estiver conectado à mesma conta de armazenamento, cada ambiente terá sua própria pasta raiz.

## <a name="prerequisites"></a>Pré-requisitos

Os pré-requisitos a seguir devem ser satisfeitos para ser possível implementar a abordagem do fluxo de dados alternativo.

### <a name="set-up-microsoft-power-platform"></a>Configurar Microsoft Power Platform

Para configurar o Microsoft Power Platform, siga as instruções em [Habilitar a integração do Microsoft Power Platform](../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md).

### <a name="install-the-export-to-data-lake-add-in"></a>Instalar o suplemento Exportar para o Data Lake

Para instalar o suplemento Exportar para o Data Lake, siga as instruções em [Instalar o suplemento Exportar para o Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

> [!NOTE]
> Anote os valores de configuração, pois você vai precisar deles para algumas das etapas a seguir.

### <a name="configure-tables-to-export-in-dynamics-365"></a>Configurar tabelas para exportação no Dynamics 365

A sincronização de tabelas do Dynamics 365 com o Azure Data Lake Storage é gerenciada na página **Exportar para Data Lake**. Como a página não tem um item de menu no momento, somente os usuários da função de segurança **Administrador do sistema** podem abri-la.

Para configurar as tabelas a serem exportadas no Dynamics 365, siga estas etapas.

1. Para abrir a página **Exportar para Data Lake**, adicione a string `?mi=DataFeedsDefinitionWorkspace` ao URL base do ambiente, conforme mostrado no exemplo a seguir:

    `https://<environment-URL>/?mi=DataFeedsDefinitionWorkspace`

1. Na página **Exportar para Data Lake** e copie as tabelas listadas na seção [Lista de tabelas de cubos de RetailSales](#list-of-retailsales-cube-tables) deste artigo.
1. Na coluna **Nome do sistema**, expanda a lista de opções de filtro.
1. Para o tipo de filtro, selecione **é um de**. Em seguida, coloque o cursor na caixa de texto e cole a lista de tabelas copiada na página **Exportar para Data Lake**.
1. Na parte inferior da lista de opções de filtro, selecione **Aplicar**.
1. Selecione todas as linhas na grade e, em seguida, selecione **Ativar**.

> [!NOTE]
> Antes de passar para a próxima etapa, todas as linhas devem ser atualizadas com o status **Em execução**. Solucione os problemas e resolva os erros conforme necessário.

### <a name="create-a-synapse-workspace"></a>Criar um espaço de trabalho Synapse

Para criar um espaço de trabalho Synapse se você ainda não tiver um, siga as instruções descritas em [Início Rápido: criar um espaço de trabalho Synapse](/azure/synapse-analytics/quickstart-create-workspace).

Para manter seus recursos do Azure organizados, recomendamos que você coloque a conta do Data Lake Storage e o espaço de trabalho Synapse em um grupo de recursos no Azure. Você pode reutilizar a conta de armazenamento criada ao instalar o suplemento Exportar para Data Lake.

## <a name="create-a-database-in-synapse-for-recommendation-data-processing"></a>Criar um banco de dados no Synapse para processamento de dados de recomendações

Use o aplicativo de console de utilitário Common Data Model (CDMUtil_ConsoleApp) para criar um banco de dados no seu espaço de trabalho Synapse e preenchê-lo com as tabelas do Common Data Model no Data Lake Storage. Recomendamos que você use o utilitário Common Data Model com o seu banco de dados em um ambiente de desenvolvimento, caso haja alguma extensão.

> [!NOTE]
> As etapas a seguir supõem que nenhum dado de extensão está sendo adicionado ao cubo RetailSales.

Para criar um banco de dados no Synapse, siga estas etapas.

1. Vá até [Dynamics-365-FastTrack-Implementation-Assets GitHub](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Analytics/CDMUtilSolution#2-cdmutil-console-app) e siga as etapas para baixar o arquivo **CDMUtilConsoleApp.zip**.
1. Extraia o arquivo zip para uma pasta local.
1. Abra o arquivo **CDMUtil_ConsoleApp.dll.config** em um editor de texto e atualize os seguintes valores:

    1. Defina o valor de **ID de locatário** (ID do locatário do Azure).
    1. Defina o valor de **Chave de acesso** (a chave de acesso da conta do Data Lake Storage).

        1. No portal do Azure, abra sua conta de armazenamento.
        1. No menu, no lado esquerdo da página, selecione **Chaves de acesso**.
        1. Na parte superior da página, selecione **Mostrar chaves**.
        1. Selecione o botão Copiar para um dos dois campos de chave e cole o valor entre as aspas duplas no arquivo de configuração.

    1. Defina o valor de **ManifestURL** como o URL do arquivo **Tables.manifest.cdm.json** no Azure Data Lake Storage. Para obter o URL, navegue até o arquivo no portal do Azure, selecione as reticências (**...**) no lado direito do modo de exibição e, em seguida, selecione **Propriedades**. O URL é a primeira propriedade mostrada na guia **Visão geral**.
    1. Defina o valor de **TargetDbConnectionString** como a cadeia de conexão do pool de SQL interno sem servidor do espaço de trabalho Synapse.

        1. No espaço de trabalho Synapse, selecione a guia **Gerenciar**.
        1. No submenu, selecione **Pools de SQL**.
        1. Selecione o nome **Interno** para exibir as propriedades do pool.
        1. Na caixa de diálogo Propriedades, selecione o tipo de conexão de ADO.NET que deseja usar. Em seguida, copie o valor da cadeia de conexão e cole-o entre as aspas duplas no arquivo de configuração.

        > [!NOTE]
        > Você deve ter permissão para criar bancos de dados. Para facilitar o uso, talvez você queira usar a conta de administrador **sqladminuser** interna.

    1. Cancele o comentário do nó **ProcessEntities** e defina seu valor como **true** (por exemplo, `<add key="ProcessEntities" value ="true"/>`).

1. Salve e feche o arquivo e **CDMUtil_ConsoleApp.dll.config**.
1. Copie o arquivo **EntityList.json** para o diretório **/Manifest**.
1. Em uma janela de prompt de comando, execute **cdmutil_consoleapp.exe**.

> [!NOTE]
> Ao revisar a saída, deve haver 35 entidades/exibições, pelo menos 75 tabelas e nenhum erro.

## <a name="prepare-the-data-lake-retailsales-aggregate-measurements-directory"></a>Preparar o diretório de medidas agregadas RetailSales do Data Lake

### <a name="back-up-your-current-retailsales-cube-data-from-data-lake-storage"></a>Fazer backup dos dados atuais do cubo RetailSales do Data Lake Storage

A maneira mais fácil de fazer backup dos dados atuais do cubo RetailSales é renomear o diretório **RetailSales** como **RetailSales-backup** ou algo semelhante Data Lake Storage. Esse método preserva os dados existentes caso a solução de problemas seja necessária posteriormente.

A pasta do cubo **/RetailSales** pode ser encontrada no seguinte local:

`<storage-account>/dynamics365-financeandoperations/<environment-url (for example, myuat.sandbox.operations.dynamics.com)>/AggregateMeasurements/RetailSales`

### <a name="create-a-new-retailsales-folder-and-upload-the-model-file"></a>Criar uma nova pasta RetailSales e carregar o arquivo de modelo

Para criar um novo diretório **RetailSales** e carregar o arquivo **model.json** para o Data Lake Storage, siga estas etapas.

1. Crie um novo diretório vazio no mesmo nível do diretório anterior e chame-o de **RetailSales**.
1. Carregue o arquivo **model.json** para o novo diretório.

## <a name="create-a-pipeline-to-copy-the-retailsales-cube-data"></a>Criar um pipeline para copiar os dados do cubo RetailSales

O pipeline lerá as exibições do cubo RetailSales e exportará os dados para os arquivos .csv no Data Lake Storage.

Para criar um pipeline para copiar os dados do cubo RetailSales, siga estas etapas.

1. No espaço de trabalho Synapse, selecione a guia **Integrar**.
1. Selecione o sinal de adição (**+**) e, em seguida, selecione **Importar do modelo de pipeline**.
1. Baixe e selecione o arquivo [ExportRetailSalesCubeViews.zip](https://aka.ms/reco-alternate-dataflow-files).
1. Selecione o serviço vinculado do banco de dados SQL.
1. Selecione seu serviço vinculado da conta de armazenamento.
1. Abra a ferramenta **Copiar Dados** e altere a propriedade **Caminho da pasta** para **\<environment_name\>/...**.

### <a name="test-execution-of-the-pipeline"></a>Testar execução do pipeline

É recomendável testar o pipeline usando apenas um modo de exibição. A exibição de **RetailSales_RetailMediaTemplateView** funciona bem porque geralmente contém menos de 10 linhas.

## <a name="schedule-the-pipeline-to-run-on-a-recurring-schedule"></a>Programar o pipeline para ser executado em uma programação recorrente

Toda vez que o pipeline é executado, ocorre o consumo do Azure. Recomendamos que você programe as execuções em intervalos de 48 horas ou mais. Você sempre poderá executar o pipeline manualmente se precisar sincronizar os dados imediatamente. 
 
## <a name="table-list-for-synchronization-from-dynamics-365-to-data-lake-storage"></a>Lista de tabelas para sincronização do Dynamics 365 para o Data Lake Storage

A lista de tabelas a seguir é um subconjunto de todas as tabelas necessárias para todo o cubo RetailSales. Somente 15 das exibições no cubo RetailSales são usadas pelo serviço de recomendações e a lista de tabelas necessárias foi filtrada adequadamente.

### <a name="list-of-retailsales-cube-tables"></a>Lista de tabelas do cubo RetailSales

- BICalendarOffsets
- BIDateDimension
- BIDateDimensionValue
- Catálogo
- CatalogProduct
- CatalogProductCategory
- CustInvoiceJour
- CustInvoiceTrans
- CustTable
- DataArea
- DimensionAttributeValueCombination
- DimensionAttributeValueSet
- DirPartyTable
- EcoResCategory
- EcoResCategoryHierarchy
- EcoResCategoryHierarchyRole
- EcoResColor
- EcoResConfiguration
- EcoResProduct
- EcoResProductCategory
- EcoResProductTranslation
- EcoResSize
- EcoResStyle
- HcmWorker
- InventDim
- InventDimCombination
- InventItemGroup
- InventItemGroupItem
- InventItemSetupSupplyType
- InventTable
- InventTrans
- LogisticsAddressCountryRegion
- LogisticsAddressCountryRegionTranslation
- LogisticsLocation
- LogisticsPostalAddress
- OMHIERARCHYPURPOSE
- RetailAssortmentLookup
- RetailAssortmentLookupChannelGroup
- RetailChannelProfile
- RetailChannelProfileProperty
- RetailChannelTable
- RetailChannelTableExt
- RetailConnDatabaseProfile
- RetailCustInvoiceJourTable
- RetailCustTable
- RetailMediaTemplate
- RetailOfflineProfile
- RetailPeriodicDiscount
- RetailRecoListConfigurationParameters
- RetailSalesTaxOverrideGroup
- RetailSharedParameters
- RetailSpecialCategoryMember
- RetailTenderTypeCardTable
- RetailTenderTypeTable
- RetailTerminalTable
- RetailTmpProductMedia
- RetailTransactionDiscountTrans
- RetailTransactionPaymentTrans
- RetailTransactionPaymentTransExt
- RetailTransactionSalesTrans
- RetailTransactionSalesTransExt
- RetailTransactionTable
- SalesLine
- SalesTable
- SystemParameters
- RETAILCATALOGINTERNALORG
- RETAILGROUPMEMBERLINE
- RETAILINTERNALORGANIZATION
- RETAILSPECIALCATEGORYPRODUCT
- RETAILPRODUCTCATEGORY
- ECORESCONFIGURATION
- DIMENSIONATTRIBUTE
- DIMENSIONATTRIBUTEVALUESET
- DIMENSIONHIERARCHY
- DIMENSIONHIERARCHYINTEGRATION
- DIMENSIONHIERARCHYLEVEL
- DIMENSIONPARAMETER
- OMExplodedOrganizationSecurityGraph

### <a name="view-list-for-the-parameter-to-pass-to-the-synapse-pipeline"></a>Exiba a lista para o parâmetro a ser transmitido para o pipeline Synapse

A seguinte lista separada por vírgulas contém as exibições do cubo RetailSales em que o pipeline executará uma operação "Select". Em seguida, ele copiará os resultados para o Data Lake Storage.

RetailSales_RetailAssortmentRulesView,RetailSales_RetailChannelNavigationHierarchiesView,RetailSales_RetailChannelNavigationHierarchyCatalogProductsView,RetailSales_RetailChannelNavigationHierarchyCategoryNodesView,RetailSales_RetailChannelNavigationHierarchyCategoryProductsView,RetailSales_RetailMediaBaseUrlChannelView,RetailSales_RetailMediaRelativeUrlProductView,RetailSales_RetailMediaTemplateView,RetailSales_RetailOptOutCustomersView,RetailSales_RetailProductCategory,RetailSales_RetailProductTransaction,RetailSales_RetailProductVariantDimensionsView,RetailSales_RetailRecoListConfigurationParametersView,RetailSales_RetailRecoListsSharedParametersView,RetailSales_RetailEcoResProductTranslation

> [!IMPORTANT]
> O parâmetro do pipeline deve ser uma lista de nomes de exibição separados por vírgulas simples. Não deve haver espaços ou feeds de linha.

## <a name="environment-specific-fixes"></a>Correções específicas do ambiente

### <a name="retailchannelview-fix"></a>Correção RETAILCHANNELVIEW

A exibição **RETAILCHANNELVIEW** contém um inteiro codificado que representa uma organização do tipo "canal de varejo". O valor real do tipo pode ser alterado de ambiente para ambiente ou de locatário para locatário.

```SQL
CREATE OR ALTER   VIEW [dbo].[RETAILCHANNELVIEW]
AS
SELECT T1.RECID AS RECID1,
       T1.STOREAREA AS STOREAREA,
       T1.OMOPERATINGUNITID AS OMOPERATINGUNITID,
       T1.DEFAULTCUSTACCOUNT AS DEFAULTCUSTOMER,
       T1.RETAILCHANNELID AS RETAILCHANNELID,
       T1.CHANNELTYPE AS CHANNELTYPE,
       T1.PARTITION AS PARTITION,
       T1.RECID AS RECID,
       T2.OMOPERATINGUNITNUMBER AS OMOPERATINGUNITNUMBER,
       T3.NAME AS NAME
FROM   dbo.RETAILCHANNELTABLE AS T1 CROSS JOIN dbo.DIRPARTYTABLE AS T2 CROSS JOIN dbo.DIRPARTYTABLE AS T3
WHERE  ((((T1.OMOPERATINGUNITID = T2.RECID)
          )
         AND ((T2.RECID = T3.RECID)
              ))
        AND T2.INSTANCERELATIONTYPE IN (8363));
```

Para atualizar o inteiro codificado, siga as etapas a seguir.

1. No Dynamics 365, procure o valor de **ChannelID** para seu canal online.
1. Em uma instância do SQL Server Management Studio (SSMS) anexada ao banco de dados Synapse, execute a seguinte consulta.

    ```SQL
    select INSTANCERELATIONTYPE, NAME, NAMEALIAS, * from dbo.DIRPARTYTABLE where RECID IN (select OMOPERATINGUNITID from dbo.RETAILCHANNELTABLE where RETAILCHANNELID =     <channelID>)
    ```

1. Copie o valor da primeira coluna (**INSTANCERELATIONTYPE**) e cole-o na definição do modo de exibição.

## <a name="troubleshooting"></a>Solução de problemas

### <a name="pipeline-task-fails"></a>Falha da tarefa de pipeline

Deve haver 15 execuções de tarefas de pipeline para a tarefa **CopyData**. Se alguma execução falhar, verifique se todos os objetos SQL dependentes existem e se as consultas são executadas. A maneira mais fácil de obter todas as dependências é usar o SSMS para conectar-se ao banco de dados. Em seguida, você pode selecionar e manter pressionado (ou clicar com o botão direito do mouse em) um modo de exibição e selecionar **Gerar CREATE como em uma nova janela**.

A mensagem de erro pode incluir o seguinte texto:

- Erro: ocorreu uma falha no lado 'Fonte'
- Erro ao manipular arquivo externo: 'Contagem máxima de erros'.
- /RetailSales/RetailSales_xxxxxx

#### <a name="example-scenario"></a>Cenário de exemplo

Neste exemplo, a tarefa **RetailSales_RetailProductCategory** falha e você recebe um erro "Contagem máxima de erros".

Para depurar o erro, siga estas etapas.

1. Abra o arquivo **EntityList.json** em um editor de texto (por exemplo, Visual Studio Code).
1. Localize a definição de exibição para **RetailSales_RetailProductCategory**.

    ```SQL
    CREATE  VIEW [dbo].[RetailSales_RetailProductCategory] AS SELECT 0 AS ROW_UNIQUEKEY ,CATEGORY AS CATEGORYID ,PRODUCT AS PRODUCTID ,PRODUCTNAME ,CATEGORYNAME     ,PARENTCATEGORY AS PARENTCATEGORYID ,PARTITION ,RECID FROM RetailProductCategoryView
    ```

1. Essa exibição depende de apenas uma outra exibição: **RetailProductCategoryView** _. Localize a definição de exibição para _*RetailProductCategoryView**.

    ```SQL
    CREATE VIEW [DBO].[RETAILPRODUCTCATEGORYVIEW] AS SELECT T1.CATEGORY AS CATEGORY, T1.PRODUCT AS PRODUCT, T1.PARTITION AS PARTITION, T1.RECID AS RECID, T2.PRODUCTNAME AS PRODUCTNAME, T2.PARTITION AS PARTITION#2, T3.NAME AS CATEGORYNAME, T3.PARENTCATEGORY AS PARENTCATEGORY, T3.PARTITION AS PARTITION#3 FROM RETAILPRODUCTCATEGORY T1 CROSS JOIN ECORESPRODUCTTRANSLATIONS T2 CROSS JOIN RETAILCATEGORYEXPANDED T3 WHERE((( T1.PRODUCT = T2.PRODUCT) AND ( T1.PARTITION = T2.PARTITION)) AND (( T1.CATEGORY = T3.RECID) AND ( T1.PARTITION = T3.PARTITION)))
    ```

1. Essa exibição depende de três outras exibições: **RETAILPRODUCTCATEGORY**, **ECORESPRODUCTTRANSLATIONS** e **RETAILCATEGORYEXPANDED**. Localize a definição de cada uma dessas exibições e liste suas dependências. Continue até localizar todas as exibições dependentes.

    Esta é a lista inteira na ordem da árvore de dependência. Treze exibições devem ser validadas.

    - RetailSales_RetailProductCategory

        - RetailProductCategoryView

            - RETAILPRODUCTCATEGORY

                - ECORESPRODUCTCATEGORY
                - ECORESCATEGORYHIERARCHYROLE
                - RETAILSPECIALCATEGORYPRODUCT

                    - ECORESPRODUCT
                    - RETAILGROUPMEMBERLINE
                    - RETAILSPECIALCATEGORYMEMBER

            - ECORESPRODUCTTRANSLATIONS

                - ECORESPRODUCT
                - ECORESPRODUCTTRANSLATION
                - SYSTEMPARAMETERS

            - RETAILCATEGORYEXPANDED

                - ECORESCATEGORY
                - ECORESCATEGORYHIERARCHYROLE

1. No Excel, crie as 13 instruções **select count(\*) from \<view_name\>** a seguir. Execute essas instruções no SSMS e envie os resultados para texto. Em seguida, percorra os resultados para ver se alguma das exibições falhou. O erro inicial sugere que pelo menos uma exibição irá falhar.

    ```SQL
    select count(*) from RetailProductCategoryView
    select count(*) from RETAILPRODUCTCATEGORY
    select count(*) from ECORESPRODUCTCATEGORY
    select count(*) from ECORESCATEGORYHIERARCHYROLE
    select count(*) from RETAILSPECIALCATEGORYPRODUCT
    select count(*) from ECORESPRODUCT
    select count(*) from RETAILGROUPMEMBERLINE
    select count(*) from RETAILSPECIALCATEGORYMEMBER
    select count(*) from ECORESPRODUCTTRANSLATIONS
    select count(*) from ECORESPRODUCTTRANSLATION
    select count(*) from SYSTEMPARAMETERS
    select count(*) from RETAILCATEGORYEXPANDED
    select count(*) from ECORESCATEGORY
    ```

1. Uma forma de validar o que você está vendo é criar uma exibição dependente da raiz para gerar a definição da exibição no SSMS. Em seguida, verifique se há uma coluna de arquivo do Azure Data Lake chamada **r.filepath**. A presença dessa coluna indicará que a exibição que você está inspecionando está lendo dados do Data Lake Storage.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral das recomendações de produtos](product-recommendations.md)

[Habilitar Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce](enable-adls-environment.md)

[Habilitar recomendações personalizadas](personalized-recommendations.md)

[Habilitar recomendações de "comprar looks semelhantes"](shop-similar-looks.md)

[Cancelar recomendações personalizadas](personalization-gdpr.md)

[Adicionar recomendações de produtos no PDV](product.md)

[Adicionar recomendações à tela de transação](add-recommendations-control-pos-screen.md)

[Ajustar os resultados das recomendações de AI-ML](modify-product-recommendation-results.md)

[Criar manualmente recomendações selecionadas](create-editorial-recommendation-lists.md)

[Criar recomendações com dados de demonstração](product-recommendations-demo-data.md)

[Perguntas frequentes sobre recomendações de produtos](faq-recommendations.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
