---
title: Pacote de orquestração de aplicativos com gravação dupla separado
description: O pacote de orquestração de aplicativos com gravação dupla não é mais um pacote único, mas foi separado em pacotes menores. Este tópico explica as soluções e os mapas que cada pacote contém e sua dependência em outros pacotes.
author: RamaKrishnamoorthy
ms.date: 11/29/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.custom: separate-solution
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-11-29
ms.openlocfilehash: 3fe1b7707df72927fba78ee9659502cc62471799
ms.sourcegitcommit: 70ac76be31bab7ed5e93f92f4683e65031fbdf85
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2021
ms.locfileid: "7924862"
---
# <a name="separated-dual-write-application-orchestration-package"></a>Pacote de orquestração de aplicativos com gravação dupla separado

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Anteriormente, o pacote de orquestração de aplicativos com gravação dupla era um pacote único que continha as seguintes soluções:

- Notas do Dynamics 365
- Âncora Comum do Dynamics 365 Finance and Operations
- Mapas de Entidade de Gravação Dupla do Dynamics 365 Finance and Operations
- Aplicativo Dynamics 365 Gerenciamento de ativos
- Dynamics 365 Gerenciamento de ativos
- HCM comum
- Dynamics 365 Supply Chain Extended
- Dynamics 365 Finance Extended
- Dynamics 365 Finance and Operations Common
- Dynamics 365 Company
- Taxas de Câmbio
- Field Service Common

Como era um pacote único, ele criou uma situação de "tudo ou nada" para os clientes. No entanto, a Microsoft agora o separou em pacotes menores. Portanto, o cliente pode selecionar apenas os pacotes para as soluções necessárias. Por exemplo, se você é cliente do Microsoft Dynamics 365 Supply Chain Management e não precisa de integração com o Dynamics 365 Human Resources, notas e gerenciamento de ativos, você pode excluir essas soluções daquelas que estão instaladas. Como as versões de nome de solução subjacente, editor e mapa permanecem as mesmas, essa alteração não interrompe nada. Instalações existentes são atualizadas.

![Pacote separado.](media/separated-package-1.png)

Este tópico explica as soluções e os mapas que cada pacote contém e sua dependência em outros pacotes.

## <a name="dual-write-application-core"></a>Núcleo de aplicativos com gravação dupla

O pacote de núcleos de aplicativos com gravação dupla permite que os usuários instalem e configurem a gravação dupla sem qualquer aplicativo de participação do cliente. Ele contém as cinco soluções a seguir.

| Nome exclusivo                           | Nome para exibição                               |
|---------------------------------------|--------------------------------------------|
| Dynamics365Company                    | Dynamics 365 Company                       |
| Dynamics365FinanceAndOperationsCommon | Dynamics 365 Finance and Operations Common |
| CurrencyExchangeRates                 | Taxas de Câmbio                    |
| msdyn_DualWriteAppCoreMaps            | Mapas de entidade de núcleo de aplicativos com gravação dupla   |
| msdyn_DualWriteAppCoreAnchor          | Âncora de núcleo de aplicativos com gravação dupla        |

Os seguintes mapas estão disponíveis neste pacote.

| Aplicativos Finance and Operations     | Aplicativos do Customer Engagement                    |
|---------------------------------|---------------------------------------------|
| Unidade operacional                  | msdyn_internalorganizations                 |
| Hierarquia da organização          | msdyn_internalorganizationhierarchies       |
| Entidades legais                  | msdyn_internalorganizations                 |
| Entidades legais                  | cdm_companies                               |
| Finalidades da hierarquia da organização | msdyn_internalorganizationhierarchypurposes |
| Par de moedas de taxa de câmbio     | msdyn_currencyexchangeratepairs             |
| Afixos de nome                    | msdyn_nameaffixes                           |
| Tipo de taxa de câmbio              | msdyn_exchangeratetypes                     |
| Taxas de Câmbio do CDS              | msdyn_currencyexchangerates                 |
| Tipo de hierarquia da organização     | msdyn_internalorganizationhierarchytypes    |
| Moedas                      | transactioncurrencies                       |
| Entidade de guias de realidade misturada     | msmrw_guides                                |

**Informações sobre dependência**

O pacote de núcleos de aplicativos com gravação dupla não tem dependência em outros pacotes.

## <a name="dual-write-human-resources"></a>Human Resources com gravação dupla

O pacote do Human Resources com gravação dupla contém as soluções e os mapas necessários para sincronizar dados do Human Resources. Ele contém as três soluções a seguir.

| Nome exclusivo                | Nome para exibição                             |
|----------------------------|------------------------------------------|
| HCMCommon                  | HCM comum                               |
| msdyn_Dynamics365HCMMaps   | Mapas de entidades do Dynamics 365 Human Resources |
| msdyn_Dynamics365HCMAnchor | Âncora do Dynamics 365 Human Resources      |

Os seguintes mapas estão disponíveis neste pacote.

| Aplicativos Finance and Operations | Aplicativos do Customer Engagement         |
|-----------------------------|----------------------------------|
| Origens étnicas              | cdm_ethnicorigins                |
| Função de trabalho de remuneração   | cdm_jobfunctions                 |
| Posições V2                | cdm_jobpositions                 |
| Trabalhos                        | cdm_jobs                         |
| Tipo de trabalho de remuneração       | cdm_jobtypes                     |
| Códigos de idiomas              | cdm_languages                    |
| Tipo de posição               | cdm_positiontypes                |
| Atribuições do trabalhador do cargo | cdm_positionworkerassignmentmaps |
| Situação militar              | cdm_veteranstatuses              |
| Trabalhador                      | cdm_workers                      |
| Emprego por empresa      | cdm_employments                  |

**Informações sobre dependência**

O pacote do Human Resources com gravação dupla depende do pacote de núcleos de aplicativos com gravação dupla. Portanto, você deve instalar o pacote de núcleos de aplicativos com gravação dupla antes de instalar o pacote do Human Resources com gravação dupla.

## <a name="dual-write-supply-chain"></a>Supply Chain com gravação dupla

O pacote do Supply Chain com gravação dupla contém as soluções e os mapas necessários para sincronizar dados do Supply Chain Management. Ele contém as três soluções a seguir.

| Nome exclusivo                                | Nome para exibição                                              |
|--------------------------------------------|-----------------------------------------------------------|
| Dynamics365SupplyChainExtended             | Dynamics 365 Supply Chain Extended                        |
| msdyn_Dynamics365SupplyChainExtendedMaps   | Mapas de entidade do Dynamics 365 Supply Chain Management Extended |
| msdyn_Dynamics365SupplyChainExtendedAnchor | Âncora do Dynamics 365 Supply Chain Management Extended      |

Os seguintes mapas estão disponíveis neste pacote.

| Aplicativos Finance and Operations                 | Aplicativos do Customer Engagement                      |
|---------------------------------------------|-----------------------------------------------|
| Unidades                                       | uoms                                          |
| Cabeçalhos de ordens de venda CDS                     | salesorders                                   |
| Linhas de ordem de venda do CDS                       | salesorderdetails                             |
| Cabeçalho de cotação de venda CDS                  | cotações                                        |
| Linhas de cotação de venda do CDS                   | quotedetails                                  |
| Produtos distintos liberados pelo CDS              | produtos                                      |
| Zonas de depósito                             | msdyn_warehousezones                          |
| Grupo de zonas de depósito                       | msdyn_warehousezonegroups                     |
| Linhas de trabalho de depósito                        | msdyn_warehouseworklines                      |
| Cabeçalhos de trabalho de depósito                      | msdyn_warehouseworkheaders                    |
| Depósitos                                  | msdyn_warehouses                              |
| Corredor do Estoque                             | msdyn_warehouseaisles                         |
| Conversões de unidades                            | msdyn_unitofmeasureconversions                |
| Condições de entrega                           | msdyn_termsofdeliveries                       |
| Modos de entrega                           | msdyn_shipvias                                |
| Estilos do produto mestre                       | msdyn_sharedproductstyles                     |
| Linhas da fatura de venda V2                      | invoicedetails                                |
| Cabeçalhos de fatura de venda V2                    | faturas                                      |
| Tamanhos do produto mestre                        | msdyn_sharedproductsizes                      |
| Produtos liberados V2                        | msdyn_sharedproductdetails                    |
| Configuração do produto mestre               | msdyn_sharedproductconfigurations             |
| Cores do produto mestre                       | msdyn_sharedproductcolors                     |
| Códigos de origem de ordem de venda                    | msdyn_salesorderorigins                       |
| Cabeçalho de recebimento de produtos                      | msdyn_purchaseorderreceipts                   |
| Linha de recebimento de produtos                        | msdyn_purchaseorderreceiptproducts            |
| Cabeçalhos da ordem de compra V2                   | msdyn_purchaseorders                          |
| Entidade de linha de ordem de compra do CDS excluída de modo reversível | msdyn_purchaseorderproducts                   |
| Entidade da linha de ordem de compra do CDS              | msdyn_purchaseorderproducts                   |
| Grupos de dimensões de rastreamento                   | msdyn_producttrackingdimensiongroups          |
| Estilos                                      | msdyn_productstyles                           |
| Grupos de dimensões de armazenamento                    | msdyn_productstoragedimensiongroups           |
| Conversões de unidade específicas do produto           | msdyn_productspecificunitofmeasureconversions |
| Configurações de ordem padrão de produto V2           | msdyn_productspecificdefaultordersettings     |
| Tamanhos                                       | msdyn_productsizes                            |
| Grupos de dimensões de produto                    | msdyn_productdimensiongroups                  |
| Configurações Padrão da Ordem                      | msdyn_productdefaultordersettings             |
| Configurações                              | msdyn_productconfigurations                   |
| Todos os produtos                                | msdyn_globalproducts                          |
| Cores                                      | msdyn_productcolors                           |
| Funções de hierarquia de categorias de produtos            | msdyn_productcategoryhierarchyroles           |
| Hierarquias de categorias de produtos                | msdyn_productcategoryhierarchies              |
| Atribuições de categoria de produtos                | msdyn_productcategoryassignments              |
| Categorias de produto                          | msdyn_productcategories                       |
| Localizações do depósito                         | msdyn_inventorylocations                      |
| Estoque do CDS em                            | msdyn_inventoryonhandentries                  |
| Categorias de produto                          | msdyn_productcategories                       |
| Estoque do CDS em                            | msdyn_inventoryonhandrequests                 |
| Código de barras identificado por número de produto           | msdyn_productbarcodes                         |
| Cartão-fidelidade                                | msdyn_loyaltycards                            |
| Pontos de premiação de fidelidade                       | msdyn_loyaltyrewardpoints                     |
| Grupos de clientes do preço                       | msdyn_pricecustomergroups                     |
| Sites                                       | msdyn_operationalsites                        |
| Linhas de cotação de venda do CDS                   | quotedetails                                  |
| Linhas de ordem de venda do CDS                       | salesorderdetails                             |

**Informações sobre dependência**

O pacote do Supply Chain com gravação dupla depende dos três pacotes a seguir. Portanto, você deve instalar esses pacotes antes de instalar o pacote do Supply Chain com gravação dupla.

- Pacote de núcleos de aplicativos com gravação dupla
- Pacote do Finance com gravação dupla
- Pacote do Human Resources com gravação dupla

## <a name="dual-write-finance"></a>Finance com gravação dupla

O pacote do Finance com gravação dupla contém as soluções e os mapas necessários para sincronizar dados do Dynamics 365 Finance. Ele contém as quatro soluções a seguir.

| Nome exclusivo                            | Nome para exibição                               |
|----------------------------------------|-------------------------------------------|
| Dynamics365FinanceExtended             | Dynamics 365 Finance Extended             |
| msdyn_Dynamics365FinanceExtendedMaps   | Mapas de entidade do Dynamics 365 Finance Extended |
| FieldServiceCommon                     | Field Service Common                      |
| msdyn_Dynamics365FinanceExtendedAnchor | Âncora do Dynamics 365 Finance Extended      |

Os seguintes mapas estão disponíveis neste pacote.

| Aplicativos Finance and Operations             | Aplicativos do Customer Engagement        |
|-----------------------------------------|---------------------------------|
| Grupos de impostos retidos na fonte                  | msdyn_withholdingtaxgroups      |
| Contatos do CDS V2 (Cliente)              | contatos                        |
| Contatos do CDS V2 (Fornecedor)                | contatos                        |
| Clientes V3                            | contatos                        |
| Códigos de impostos retidos na fonte                   | msdyn_withholdingtaxcodes       |
| Fornecedores V2                              | msdyn_vendors                   |
| Método de pagamento do fornecedor                   | msdyn_vendorpaymentmethods      |
| Grupos de fornecedores                           | msdyn_vendorgroups              |
| Plano de Contas                       | msdyn_chartofaccountses         |
| Grupos de lançamentos contábeis de imposto V2      | msdyn_taxpostinggroups          |
| Grupo de impostos do item                    | msdyn_taxitemgroups             |
| Grupos de impostos                        | msdyn_taxgroups                 |
| CDS de entidade de código de isenção de imposto        | msdyn_taxexemptcodes            |
| Grupos de clientes                         | msdyn_customergroups            |
| Método de pagamento do cliente                 | msdyn_customerpaymentmethods    |
| Dimensões financeiras                    | msdyn_dimensionattributes       |
| Autoridades do imposto                   | msdyn_taxauthorities            |
| Formato da dimensão financeira              | msdyn_financialdimensionformats |
| Período do calendário fiscal                  | msdyn_fiscalcalendarperiods     |
| Entidade de integração do calendário fiscal      | msdyn_fiscalcalendars           |
| Entidade de integração do ano do calendário fiscal | msdyn_fiscalcalendaryears       |
| Condições de pagamento                        | msdyn_paymentterms              |
| Plano de Pagamento                        | msdyn_paymentschedules          |
| Linhas de plano de pagamento                  | msdyn_paymentschedulelines      |
| Dias de pagamento CDS                        | msdyn_paymentdays               |
| Linhas de dia de pagamento CDS V2                | msdyn_paymentdaylines           |
| Conta principal                            | msdyn_mainaccounts              |
| Categorias de conta principal                 | msdyn_mainaccountcategories     |
| Ledger                                  | msdyn_ledgers                   |
| Clientes V3                            | contas                        |

**Informações sobre dependência**

O pacote do Finance com gravação dupla depende do pacote de núcleos de aplicativos com gravação dupla. Portanto, você deve instalar o pacote de núcleos de aplicativos com gravação dupla antes de instalar o pacote do Finance com gravação dupla.

## <a name="dual-write-notes"></a>Notas com gravação dupla

O pacote do Notes com gravação dupla contém as soluções e os mapas necessários para sincronizar dados de notas ou anotações. Ele contém as quatro soluções a seguir.

| Nome exclusivo                  | Nome para exibição                   |
|------------------------------|--------------------------------|
| Dynamics365Notes             | Notas do Dynamics 365             |
| Dynamics365NotesExtended     | Notas do Dynamics 365 Estendidas    |
| msdyn_Dynamics365NotesMaps   | Mapas de entidade das Notas do Dynamics 365 |
| msdyn_Dynamics365NotesAnchor | Âncora das Notas do Dynamics 365      |

Os seguintes mapas estão disponíveis neste pacote.

| Finance and Operations                     | Customer Engagement |
|--------------------------------------------|---------------------|
| Anexos de documento de cabeçalho de ordem de venda    | anotações         |
| Anexos do Cliente                       | anotações         |
| Anexos de documentos do fornecedor                | anotações         |
| Anexos de documento de cabeçalho de ordem de compra | anotações         |

**Informações sobre dependência**

O pacote do Notes com gravação dupla depende dos dois pacotes a seguir. Portanto, você deve instalar esses pacotes antes de instalar o pacote do Notes com gravação dupla.

- Pacote de núcleos de aplicativos com gravação dupla
- Pacote do Finance com gravação dupla

## <a name="dual-write-asset-management"></a>Gerenciamento de ativos com gravação dupla

O pacote do Gerenciamento de ativos com gravação dupla contém as soluções e os mapas necessários para sincronizar dados de ativos do Supply Chain Management ou do Dynamics 365 Field Service. Ele contém as quatro soluções a seguir.

| Nome exclusivo                          | Nome para exibição                              |
|--------------------------------------|-------------------------------------------|
| Dynamics365AssetManagement           | Dynamics 365 Gerenciamento de ativos             |
| Dynamics365AssetManagementApp        | Aplicativo Dynamics365 Gerenciamento de ativos          |
| msdyn_DualWriteAssetManagementMaps   | Mapas de entidade do Dynamics 365 Gerenciamento de ativos |
| msdyn_DualWriteAssetManagementAnchor | Âncora do Dynamics 365 Gerenciamento de ativos      |

Os seguintes mapas estão disponíveis neste pacote.

| Aplicativos Finance and Operations                           | Aplicativos do Customer Engagement                |
|-------------------------------------------------------|-----------------------------------------|
| Garantia de gerenciamento de ativos                             | msdyn_warranties                        |
| Modelos de gerenciamento de ativo                               | msdyn_models                            |
| Fabricantes de gerenciamento de ativos                        | msdyn_manufacturers                     |
| Tipos de locais funcionais de gerenciamento de ativos            | msdyn_functionallocationtypes           |
| Locais funcionais de gerenciamento de ativos                 | msdyn_functionallocations               |
| Estados de ciclo de vida do local funcional de gerenciamento de ativos | msdyn_functionallocationlifecyclestates |
| Modelos de ciclo de vida do local funcional de gerenciamento de ativos | msdyn_functionallocationlifecyclemodels |
| Ativos de gerenciamento de ativo                               | msdyn_customerassets                    |
| Tipos de ativo de gerenciamento de ativo                          | msdyn_customerassetcategories           |
| Estados de ciclo de vida do ativo de gerenciamento de ativos               | msdyn_assetlifecyclestates              |
| Modelos de ciclo de vida do ativo de gerenciamento de ativos               | msdyn_assetlifecyclemodels              |

**Informações sobre dependência**

O pacote do Gerenciamento de ativos com gravação dupla depende do pacote de núcleos de aplicativos com gravação dupla. Portanto, você deve instalar o pacote de núcleos de aplicativos com gravação dupla antes de instalar o pacote do Gerenciamento de ativos com gravação dupla.

## <a name="packages-required-for-project-operations"></a>Pacotes necessários para o Project Operations
O Project Operations dependem dos pacotes a seguir. Portanto, você deve instalar esses pacotes antes de instalar o Project Operations.

- Pacote de núcleos de aplicativos com gravação dupla
- Pacote do Finance com gravação dupla
- Pacote do Supply Chain com gravação dupla
- Pacote do Gerenciamento de ativos com gravação dupla
- Pacote do Human Resources com gravação dupla
