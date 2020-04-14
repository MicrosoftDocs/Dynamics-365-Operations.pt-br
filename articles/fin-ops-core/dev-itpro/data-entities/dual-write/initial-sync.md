---
title: Cadeia de dependência de entidade (ordem de sincronização)
description: Este tópico especifica a ordem de sincronização que você deve seguir para criar os dados iniciais.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 4adb2c8d57ad8f67346b8d34212b7a4b0bd052ab
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173122"
---
# <a name="entity-dependency-chain-synchronization-order"></a>Cadeia de dependência de entidade (ordem de sincronização)

[!include [banner](../../includes/banner.md)]



Nas tabelas a seguir, as entidades são listadas na ordem em que você deve habilitá-las. Quando você habilita um mapa para sincronização inicial, a gravação dupla detecta automaticamente outros mapas que devem ser habilitados. É possível usar a página **Gravação dupla** nos aplicativos do Finance and Operations para selecionar ou cancelar a seleção de entidades durante a sincronização inicial.

Na versão mais recente da gravação dupla, é possível habilitar apenas algumas entidades, e as dependências são processadas para você.

## <a name="dynamics-365-supply-chain-management-entities"></a>Entidades do Dynamics 365 Supply Chain Management

As entidades do Supply Chain Management a seguir estão listadas na ordem em que você deve habilitá-las.

| Nome do mapeamento na página de gravação dupla | Nome dos metadados da entidade no Supply Chain Management | Nome dos metadados da entidade no Common Data Service | Anotações |
|---|---|---|---|
| Unidades ... uoms                                                                      | UnitOfMeasureEntity                                    | uom                                          | |
| Conversões de unidades ... msdyn_unitofmeasureconversions                                 | UnitOfMeasureConversionEntity                          | msdyn_unitofmeasureconversion                | |
| Todos os produtos ... msdyn_globalproducts                                               | EcoResEveryProductEntity                               | msdyn_globalproduct                          | |
| Grupos de dimensão do produto ... msdyn_productdimensiongroups                           | EcoResProductDimensionGroupEntity                      | msdyn_productdimensiongroup                  | |
| Grupos de dimensão de armazenamento ... msdyn_productstoragedimensiongroups                    | EcoResStorageDimensionGroupEntity                      | msdyn_productstoragedimensiongroup           | |
| Grupos de dimensão de rastreamento ... msdyn_producttrackingdimensiongroups                  | EcoResTrackingDimensionGroupEntity                     | msdyn_producttrackingdimensiongroup          | |
| Cores ... msdyn_productcolors                                                      | EcoResProductColorEntity                               | msdyn_productcolor                           | |
| Tamanhos ... msdyn_productsizes                                                        | EcoResProductSizeEntity                                | msdyn_productsize                            | |
| Estilos ... msdyn_productstyles                                                      | EcoResProductStyleEntity                               | msdyn_productstyle                           | |
| Configurações ... msdyn_productconfigurations                                      | EcoResProductConfigurationEntity                       | msdyn_productconfiguration                   | |
| Produtos liberados V2 ... msdyn_sharedproductdetails                                 | EcoResReleasedProductV2Entity                          | msdyn_sharedproductdetail                    | |
| Produtos distintos liberados pelo Common Data Service ... produtos                         | EcoResReleasedDistinctProductCommon Data ServiceEntity | produto                                      | |
| Número do produto identificado no código de barras ... msdyn_productbarcodes                         | EcoResProductNumberIdentifiedBarcodeEntity             | msdyn_productbarcode                         | |
| Configurações de ordem padrão ... msdyn_productdefaultordersettings                        | InventProductDefaultOrderSettingsEntity                | msdyn_productdefaultordersetting             | |
| Configurações de ordem padrão de produto V2 ... msdyn_productspecificdefaultordersettings     | InventProductSpecificOrderSettingsV2Entity             | msdyn_productspecificdefaultordersetting     | |
| Conversões de unidade específicas do produto ... msdyn_productspecificunitofmeasureconversions | EcoResProductSpecificUnitConversionEntity              | msdyn_productspecificunitofmeasureconversion | |
| Sites ... msdyn_operationalsites                                                    | InventOperationalSiteEntity                            | msdyn_operationalsite                        | |
| Depósitos ... msdyn_warehouses                                                     | InventWarehouseEntity                                  | msdyn_warehouse                              | Consulte a [nota 1](#scm-notes). |
| Cores do produto mestre ... msdyn_sharedproductcolors                                 | EcoResProductMasterColorEntity                         | msdyn_sharedproductcolor                     | |
| Tamanhos de produto mestre ... msdyn_sharedproductsizes                                   | EcoResProductMasterSizeEntity                          | msdyn_sharedproductsize                      | |
| Estilos de produto mestre ... msdyn_sharedproductstyles                                 | EcoResProductMasterStyleEntity                         | msdyn_sharedproductstyle                     | |
| Configurações de produto mestre ... msdyn_sharedproductconfigurations                 | EcoResProductMasterConfigurationEntity                 | msdyn_sharedproductconfiguration             | |
| Categorias de produtos ... msdyn_productcategories                                      | EcoResProductCategoryEntity                            | msdyn_productcategory                        | Consulte a [nota 2](#scm-notes). |
| Atribuições de categoria de produto ... msdyn_productcategoryassignments                   | EcoResProductCategoryAssignmentEntity                  | msdyn_productcategoryassignment              | |
| Hierarquias de categoria de produto ... msdyn_productcategoryhierarchies                   | EcoResProductCategoryHierarchyEntity                   | msdyn_productcategoryhierarchy               | |
| Funções da hierarquia de categoria de produto ... msdyn_productcategoryhierarchyroles            | EcoResProductCategoryHierarchyRoleEntity               | msdyn_productcategoryhierarchyrole           | |
| Corredor do estoque ... msdyn_warehouseaisles                                           | WMSWarehouseAisleEntity                                | msdyn_warehouseaisle                         | |
| Zonas de depósito ... msdyn_warehousezones                                            | WHSWarehouseZoneEntity                                 | msdyn_warehousezone                          | |
| Grupos de zonas do depósito ... msdyn_warehousezonegroups                                 | WHSWarehouseZoneGroupEntity                            | msdyn_warehousezonegroup                     | |
| Locais de depósito ... msdyn_inventorylocations                                    | WMSWarehouseLocationEntity                             | msdyn_inventorylocation                      | Consulte a [nota 3](#scm-notes). |
| Cabeçalhos de trabalho de depósito ... msdyn_warehouseworkheaders                               | WHSWarehouseWorkHeaderEntity                           | msdyn_warehouseworkheader                    | |
| Linhas de trabalho de depósito ... msdyn_warehouseworklines                                    | WHSWarehouseWorkLineEntity                             | msdyn_warehouseworklines                     | Consulte a [nota 4](#scm-notes). |
| Modos de entrega ... msdyn_shipvias                                                | DlvDeliveryModeEntity                                  | msdyn_shipvias                               | |
| Condições de entrega ... msdyn_termsofdeliveries                                       | DeliveryTermsEntity                                    | msdyn_termsofdelivery                        | |
| Códigos de origem de ordem de venda ... msdyn_salesorderorigins                                | SalesOrderOriginEntity                                 | msdyn_salesorderorigin                       | |
| Cabeçalhos de ordens de venda do Common Data Service ... salesorders                             | SalesOrderHeaderCommon Data ServiceEntity              | salesorder                                   | |
| Linhas de ordem de venda do Common Data Service ... salesorderdetails                         | SalesOrderLineCommon Data ServiceEntity                | salesorderdetails                            | |
| Cabeçalho de cotação de venda do Common Data Service ... quotes                               | SalesQuotationHeaderCommon Data ServiceEntity          | cota                                        | |
| Linhas de cotação de venda do Common Data Service ... quotedetails                          | SalesQuotationLineCommon Data ServiceEntity            | QuoteDetails                                 | |
| Cabeçalhos de fatura de venda V2 ... invoices                                               | SalesInvoiceHeaderV2Entity                             | nota fiscal                                      | |
| Linhas da fatura de venda V2 ... invoicedetails                                           | SalesInvoiceLineV2Entity                               | invoicedetail                                | |

### <a name="mapping-specific-notes"></a><a id='scm-notes'></a>Notas específicas do mapeamento

1. Por causa da autodependência, pode ser necessário executar a sincronização inicial duas vezes.
2. Por padrão, a sincronização inicial é desativada em razão do relacionamento pai-filho (a ordem "inteligente" não é tratada pela plataforma). Portanto, as categorias de produtos existentes devem ser sincronizadas manualmente (por exemplo, atualizando a descrição da categoria) na ordem correta (primeiro a categoria raiz e depois os filhos e os filhos dos filhos). Vá para **Gerenciamento de informações sobre produtos \> Configuração \> Categorias e atributos \> Hierarquias de categoria**. Na página **Hierarquias de categoria**, você pode selecionar cada hierarquia e ver as categorias de produtos nela.
3. O mapeamento dos campos de pesquisa **ItemNumberInLocation** vazios e as primeira, segunda e terceira zonas adicionais do depósito causarão falha na sincronização inicial. Portanto, esses mapeamentos são removidos por enquanto.
4. O mapeamento do campo **CaptureWeight** vazio fará com que a sincronização inicial falhe. Portanto, esse mapeamento é removido por enquanto.

### <a name="setup-related-information"></a>Informações relacionadas à instalação

+ Quando os registros são criados pela primeira vez na entidade **Produtos** em aplicativos baseados em modelo no Dynamics 365, eles têm um status de **Rascunho**. Para alterar o status para **Ativo**, acesse **Configurações \> Administração \> Configurações do sistema \> Vendas** no aplicativo baseado em modelo e defina a opção **Criar produtos em estado ativo** como **Sim**.
+ Se você criar registros na entidade **Produtos** em aplicativos baseados em modelo no Dynamics 365 ou no Common Data Service antes de habilitar a gravação dupla, esses registros serão atualizados apenas se a chave inteira, incluindo **Empresa**, corresponder aos dados no aplicativo do Finance and Operations.
+ A sincronização da entidade **Produtos** é unidirecional, dos aplicativos do Finance and Operations ao Common Data Service. Se um campo mapeado na entidade **Produtos** em aplicativos baseados em modelo no Dynamics 365 for atualizado, a atualização será substituída durante a próxima sincronização no aplicativo do Finance and Operations.

### <a name="known-issues"></a>Problemas conhecidos

- Ocorre um erro quando uma unidade é excluída em um aplicativo do Finance and Operations. Quando as unidades de medida são sincronizadas do aplicativo do Finance and Operations com o Common Data Service, a primeira unidade de uma classe específica será criada como a unidade principal e evitará a exclusão.

    **Mitigação:** primeiro exclua a unidade no Common Data Service. Em seguida, ela pode ser excluída no aplicativo do Finance and Operations.

- Ocorre um erro quando um site operacional é excluído no Common Data Service. A mensagem de erro informa: "Infolog: aviso: o endereço principal não pode ser excluído.; aviso: o registro da entidade não pôde ser excluído porque a validação falhou para a seguinte fonte de dados: InventSiteLogisticsLocation (InventSiteLogisticsLocation)." Esse erro é causado por um problema na entidade de dados no aplicativo do Finance and Operations.

    **Mitigação:** você pode excluir o site no aplicativo do Finance and Operations. O site será excluído no Common Data Service se o mapa de gravação dupla correspondente estiver em execução.

## <a name="dynamics-365-finance-entities"></a>Entidades do Dynamics 365 Finance

As entidades do Dynamics 365 Finance a seguir estão listadas na ordem em que você deve habilitá-las.

| Nome do mapeamento na página de gravação dupla | Nome dos metadados da entidade no Finance | Nome dos metadados da entidade no Common Data Service | Anotações |
|---|---|---|---|
| Moedas ... transactioncurrencies                                            | CurrencyEntity                              | Moeda                                   | |
| Tipo de taxa de câmbio ... msdyn_exchangeratetypes                                  | ExchangeRateTypeEntity                      | msdyn_exchangeratetype                     | |
| Par de moedas de taxa de câmbio ... msdyn_currencyexchangeratepairs                 | ExchangeRateCurrencyPairEntity              | msdyn_currencyexchangeratepair             | |
| Taxas de câmbio do Common Data Service ... msdyn_currencyexchangerates              | ExchangeRateCommon Data ServiceEntity       | msdyn_currencyexchangerate                 | Consulte a [nota 1](#fin-notes). |
| Entidade de integração de calendário fiscal ... msdyn_fiscalcalendars                    | FiscalCalendarEntity                        | msdyn_fiscalcalendar                       | |
| Entidade de integração de ano fiscal ... msdyn_fiscalcalendaryears           | FiscalCalendarYearEntity                    | msdyn_fiscalcalendaryear                   | |
| Período do calendário fiscal ... msdyn_fiscalcalendarperiods                          | FiscalPeriodEntity                          | msdyn_fiscalcalendarperiod                 | |
| Tipo de hierarquia da organização ... msdyn_internalorganizationhierarchytypes        | OMOrganizationHierarchyTypeEntity           | msdyn_internalorganizationhierarchytype    | Consulte a [nota 1](#fin-notes). |
| Finalidades da hierarquia da organização ... msdyn_internalorganizationhierarchypurposes | OMOrganizationHierarchyPurposeEntity        | msdyn_internalorganizationhierarchypurpose | Consulte a [nota 1](#fin-notes). |
| Entidades legais ... msdyn_internalorganizations                                  | OMLegalEntity                               | msdyn_internalorganization                 | Consulte a [nota 1](#fin-notes). |
| Entidades legais ... cdm_companies                                                | OMLegalEntity                               | cdm_company                                | |
| Unidade operacional ... msdyn_internalorganizations                                  | OMOperatingUnitEntity                       | msdyn_internalorganization                 | Consulte a [nota 1](#fin-notes). |
| Hierarquia da organização - publicada ... msdyn_internalorganizationhierarchies    | OMOrganizationHierarchyPublishedEntity      | msdyn_internalorganizationhierarchy        | Consulte a [nota 1](#fin-notes). |
| Afixos de nome ... msdyn_nameaffixes                                              | DirNameAffixEntity                          | msdyn_nameaffix                            | |
| Dias de pagamento do Common Data Service ... msdyn_paymentdays                          | PaymentDayCommon Data ServiceEntity         | msdyn_paymentday                           | |
| Linhas de dia de pagamento do Common Data Service V2 ... msdyn_paymentdaylines              | PaymentDayLineCommon Data ServiceV2Entity   | msdyn_paymentdayline                       | |
| Linhas da agenda de pagamento ... msdyn_paymentschedules                                     | PaymentScheduleEntity                       | msdyn_paymentschedule                      | |
| Linhas da agenda de pagamento ... msdyn_paymentschedulelines                           | PaymentScheduleLineEntity                   | msdyn_paymentscheduleline                  | |
| Condições de pagamento ... msdyn_paymentterms                                         | PaymentTermEntity                           | msdyn_paymentterm                          | |
| Método de pagamento de clientes ... msdyn_customerpaymentmethods                        | CustomerPaymentMethodEntity                 | msdyn_customerpaymentmethod                | |
| Método de pagamento de fornecedor ... msdyn_vendorpaymentmethods                            | VendorPaymentMethodEntity                   | msdyn_vendorpaymentmethod                  | |
| Grupos de clientes ... msdyn_customergroups                                        | CustCustomerGroupEntity                     | msdyn_customergroup                        | |
| Grupos de fornecedores ... msdyn_vendorgroups                                            | VendVendorGroupEntity                       | msdyn_vendorgroup                          | |
| Grupos de imposto ... msdyn_taxgroups                                            | TaxGroupEntity                              | msdyn_taxgroup                             | |
| Grupos de imposto de itens ... msdyn_taxitemgroups                                   | TaxItemGroupEntity                          | msdyn_taxitemgroup                         | |
| Grupos de lançamento de imposto no razão V2 ... msdyn_taxpostinggroups                   | TaxPostingGroupEntityV2                     | msdyn_taxpostinggroup                      | |
| Common Data Service da entidade de código de isenção de imposto ... msdyn_taxexemptcodes       | TaxExemptCodeCommon Data ServiceEntity      | msdyn_taxexemptcode                        | |
| Autoridades de imposto ... msdyn_taxauthorities                                  | TaxAuthorityEntity                          | msdyn_taxauthority                         | |
| Código de imposto ... msdyn_taxcodes                                               | TaxCodeEntity                               | msdyn_taxcode                              | Consulte a [nota 1](#fin-notes). |
| Formato de dimensão financeira ... msdyn_financialdimensionformats                  | DimensionIntegrationFormatEntity            | msdyn_financialdimensionformat             | |
| Dimensões financeiras ... msdyn_dimensionattributes                              | DimensionAttributeEntity                    | msdyn_dimensionattribute                   | |
| Grupos de imposto retido na fonte ... msdyn_withholdingtaxgroups                           | TaxWithholdingGroupEntity                   | msdyn_withholdingtaxgroup                  | |
| Códigos de imposto retido na fonte ... msdyn_withholdingtaxcodes                             | TaxWithholdingTaxCodes                      | msdyn_withholdingtaxcode                   | |
| Plano de contas ... msdyn_chartofaccountses                                   | LedgerChartOfAccountsEntity                 | msdyn_chartofaccounts                      | |
| Razão ... msdyn_ledgers                                                        | LedgerEntity                                | msdyn_ledger                               | Consulte a [nota 1](#fin-notes). |
| Categorias de conta principal ... msdyn_mainaccountcategories                         | MainAccountCategoryEntity                   | msdyn_mainaccountcategory                  | |
| Conta principal ... msdyn_mainaccounts                                             | MainAccountEntity                           | msdyn_mainaccount                          | |
| Clientes V3 ... contas                                                       | CustCustomerV3Entity                        | conta                                    | Consulte a [nota 2](#fin-notes). |
| Clientes V3 ... contatos                                                       | CustCustomerV3Entity                        | contato                                    | Consulte a [nota 3](#fin-notes). |
| Fornecedores v2 ... msdyn_vendors                                                    | VendVendorV2Entity                          | msdyn_vendor                               | Consulte a [nota 2](#fin-notes). |
| Contatos V2 do Common Data Service ... contacts                                    | smmContactPersonCommon Data ServiceV2Entity | contato                                    | Consulte a [nota 4](#fin-notes). |
| Contatos V2 do Common Data Service ... contacts                                    | smmContactPersonCommon Data ServiceV2Entity | contato                                    | Consulte a [nota 5](#fin-notes). |

### <a name="mapping-specific-notes"></a><a id='fin-notes'></a>Notas específicas do mapeamento

1. A sincronização unidirecional ocorre dos aplicativos do Finance and Operations ao Common Data Service.
2. Por causa da autodependência, pode ser necessário executar a sincronização inicial mais de uma vez. Certifique-se de selecionar **Cliente** como o tipo de relação ao criar uma conta usando a página **Contas** no Common Data Service. Se você encontrar problemas com o campo **Contato Principal** durante a sincronização inicial, remova esse campo do mapeamento e execute a sincronização inicial novamente. Depois que a sincronização inicial for concluída com êxito, interrompa o mapeamento e adicione o campo **Contato Principal** novamente. Em seguida, inicie o mapeamento, mas ignore a sincronização inicial. O valor do campo **Contato Principal** não será incluído na sincronização inicial e você precisará migrar manualmente os valores.
3. Defina a opção **Comercializável** como **Sim** na página **Contatos** no Common Data Service ao tentar criar um cliente do tipo **Pessoa**.
4. Esse mapeamento possui um filtro nos dois lados para vincular os contatos do cliente. Abra os detalhes do mapeamento, selecione o botão de filtro (símbolo em forma de funil) ao lado do nome da entidade **Sales.Contact** e verifique se os critérios do arquivo contêm **msdyn_contactforvendor eq true and msdyn_sellable eq false**.
5. Esse mapeamento possui um filtro nos dois lados para vincular os contatos do fornecedor. Abra os detalhes do mapeamento, selecione o botão de filtro (símbolo em forma de funil) ao lado do nome da entidade **Sales.Contact** e verifique se os critérios do filtro contêm **msdyn_contactforvendor eq true and msdyn_sellable eq false**. 

## <a name="dynamics-365-human-resources-entities"></a>Entidades do Dynamics 365 Human Resources

As entidades do Dynamics 365 Human Resources a seguir estão listadas na ordem em que você deve habilitá-las.

| Nome do mapeamento na página de gravação dupla | Nome dos metadados da entidade no Human Resources | Nome dos metadados da entidade no Common Data Service | Anotações |
|---|---|---|---|
| cdm_jobfunction - Função de trabalho                                |                                   | cdm_jobfunction                  | |
| cdm_jobtypes - Tipos de trabalho                                      |                                   | cdm_jobtypes                     | |
| cdm_jobs - Trabalhos                                               |                                   | cdm_jobs                         | |
| cdm_jobs - Detalhes do trabalho                                        |                                   | cdm_jobs                         | |
| cdm_positiontype - PositionType                               | HcmPositionTypeEntity             | cdm_positiontype                 | |
| cdm_jobpositions - Cargos de trabalho                              | HcmPositionBaseEntity             | cdm_jobposition                  | Consulte a [nota 1](#hr-notes). |
| cdm_jobposition - Detalhes de cargo                            | HcmPositionDetailEntity           | cdm_jobposition                  | Consulte a [nota 1](#hr-notes). |
| cdm_jobposition - Duração de cargo                           | HcmPositionDurationEntity         | cdm_jobposition                  | Consulte a [nota 1](#hr-notes). |
| cdm_jobposition - Hierarquias de cargo                        | HcmPositionHierarchyEntity        | cdm_jobposition                  | Consulte a [nota 1](#hr-notes). |
| cdm_veteranstatus - Situação militar                            |                                   | cdm_veteranstatus                | |
| cdm_ethnicorigin - Origem étnica                              |                                   | cdm_ethnicorigin                 | |
| cdm_languagecode - Código do idioma                              |                                   | cdm_languagecode                 | |
| cdm_worker - Trabalhador                                           | HcmWorkerEntity                   | cdm_worker                       | |
| cdm_employments - Empregos                                 |                                   | cdm_employments                  | |
| cdm_employments - Detalhe de emprego                           |                                   | cdm_employments                  | |
| cdm_positionworkerassignmentmaps - Atribuição do trabalhador da posição | HcmPositionWorkerAssignmentEntity | cdm_positionworkerassignmentmaps | Consulte a [nota 2](#hr-notes).|

### <a name="mapping-specific-notes"></a><a id='hr-notes'></a>Notas específicas do mapeamento

1. Uma entidade do Common Data Service é mapeada para várias entidades do aplicativo do Finance and Operations.
2. Esse mapeamento tem uma autorreferência.

## <a name="asset-management-entities"></a>Entidades de gerenciamento de ativos

As entidades do Gerenciamento de Ativos para Dynamics 365 Supply Chain Management estão listadas na ordem em que você deve habilitá-las.

| Nome do mapeamento na página de gravação dupla | Nome dos metadados da entidade no Gerenciamento de Ativos | Nome dos metadados da entidade no Common Data Service | Anotações |
|---|---|---|---|
| FO.AssetManagementAssetLifecycleStates--Common Data Service.msdyn_assetlifecyclestates                           | Estados de ciclo de vida do ativo de gerenciamento de ativos               | msdyn_assetlifecyclestates               | |
| FO.AssetManagementAssetLifecycleModels--Common Data Service.msdyn_assetlifecyclemodels                           | Modelos de ciclo de vida do ativo de gerenciamento de ativos               | msdyn_assetlifecyclemodels               | |
| FO.AssetManagementFunctionalLocationLifecycleModels--Common Data Service.msdyn_functionallocationlifecyclemodels | Modelos de ciclo de vida do local funcional de gerenciamento de ativos | msdyn_functionallocationlifecyclemodels  | |
| FO.AssetManagementFunctionalLocationLifecycleStates--Common Data Service.msdyn_functionallocationlifecyclestates | Estados de ciclo de vida do local funcional de gerenciamento de ativos | msdyn_functionallocationlifecyclestates  | |
| FO.AssetManagementAssetTypes--Common Data Service.msdyn_customerassetcategories                                  | Tipos de ativo de gerenciamento de ativo                          | msdyn_customerassetcategories            | |
| FO.AssetManagementFunctionalLocationTypes--Common Data Service.msdyn_functionallocationtypes                     | Tipos de locais funcionais de gerenciamento de ativos            | msdyn_functionallocationtypes            | |
| FO.AssetManagementFunctionalLocations--Common Data Service.msdyn_functionallocations                             | Locais funcionais de gerenciamento de ativos                 | msdyn_functionallocations                | Consulte a [nota](#am-notes). |
| FO.AssetManagementAssets--Common Data Service.msdyn_customerassets                                               | Ativos de gerenciamento de ativo                               | msdyn_customerassets                     | Consulte a [nota](#am-notes). |
| FO.AssetManagementManufacturers--Common Data Service.msdyn_manufacturers                                         | Fabricantes de gerenciamento de ativos                        | msdyn_manufacturers                      | |
| FO.AssetManagementModels--Common Data Service.msdyn_models                                                       | Modelos de gerenciamento de ativo                               | msdyn_models                             | |
| FO.AssetManagementWarranty--Common Data Service.msdyn_warranties                                                 | Garantia de gerenciamento de ativos                             | msdyn_warranties                         | |

### <a name="mapping-specific-notes"></a><a id='am-notes'></a>Notas específicas do mapeamento

- Por causa da autodependência, pode ser necessário executar a sincronização inicial mais de uma vez.
