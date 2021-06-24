---
title: Disponibilidade de estoque em gravação dupla
description: Este tópico fornece informações sobre como verificar a disponibilidade de estoque em gravação dupla.
author: RamaKrishnamoorthy
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: 0fded78134b1427e6faea9656e1d3b02b467ae91
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193398"
---
# <a name="inventory-availability-in-dual-write"></a>Disponibilidade de estoque em gravação dupla

[!include [banner](../../includes/banner.md)]

Usando a disponibilidade de estoque, você pode verificar seu estoque antes de adicionar um produto à página **Cotações**, **Ordens** ou **Faturas** no Microsoft Dynamics 365 Sales. Por exemplo, você verifica o estoque e determina uma data de atendimento como uma tarefa fundamental no processo de [pagamento à vista](dual-write-prospect-to-cash.md).

Se não tiver estoque suficiente, você poderá estimar uma data de entrega com base em recebimentos e saídas de estoque projetado. Você também pode verificar as informações de disponível para promessa (ATP), em que é possível encontrar a quantidade ATP no limite de tempo predefinido.

## <a name="on-hand-inventory"></a>Estoque Disponível

No Dynamics 365 Sales, um novo botão **Estoque disponível** foi adicionado ao cabeçalho das páginas **Cotações**, **Ordens** e **Faturas**. Quando você seleciona esse botão, uma caixa de diálogo é exibida e você pode especificar a empresa e o produto para o qual deseja verificar o estoque disponível. Essa caixa de diálogo mostra as mesmas informações do que o [Estoque disponível](../../../../supply-chain/inventory/tasks/check-availability-stock.md).

A caixa de diálogo retorna as informações de estoque do Dynamics 365 Supply Chain Management. Essas informações incluem as seguintes quantidades:

- Quantidade disponível
- Quantidade disponível reservada
- Quantidade disponível
- Quantidade encomendada
- Quantidade na ordem
- Quantidade encomendada reservada
- Quantidade disponível total

## <a name="atp-information"></a>Informações sobre ATP

No Sales, um novo botão **Informações sobre ATP** foi adicionado aos itens de linha nas páginas **Cotações**, **Ordens** e **Faturas**. Quando você selecione essa botão, uma caixa de diálogo é exibida e você pode especificar empresa, produto, site do estoque, depósito de estoque e quantidade da ordem. Essa caixa de diálogo tem as mesmas configurações descritas em [Promessa de ordem](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).

A caixa de diálogo retorna as informações sobre ATP do Supply Chain Management. Essas informações incluem as seguintes quantidades:

- Quantidade ATP
- Quantidade recebida
- Quantidade emitida
- Quantidade disponível

## <a name="how-it-works"></a>Como funciona

Ao selecionar o botão **Estoque disponível** na página **Cotações**, **Pedidos** ou **Faturas**, uma chamada de gravação dupla será feita para a API **Estoque disponível**. A API calcula o estoque disponível do produto fornecido. O resultado é armazenado nas tabelas **InventCDSInventoryOnHandRequestEntity** e **InventCDSInventoryOnHandEntryEntity** e, em seguida, é registrado no Dataverse por gravação dupla. Para usar essa funcionalidade, é necessário executar os seguintes mapas de gravação dupla. Ignore a sincronização inicial ao executar os mapas.

- Entradas de estoque disponível do CDS (msdyn_inventoryonhandentries)
- Solicitações de estoque disponível do CDS (msdyn_inventoryonhandrequests)

## <a name="templates"></a>Modelos
Os seguintes modelos estão disponíveis para a exposição de dados de estoque disponível.

Aplicativos Finance and Operations | Aplicativo Customer Engagement | descrição 
---|---|---
[Entradas de estoque disponível do CDS](#145) | msdyn_inventoryonhandentries |
[Solicitações de estoque disponível do CDS](#147) | msdyn_inventoryonhandrequests |

[!include [banner](../../includes/dual-write-symbols.md)]

###  <a name="cds-inventory-on-hand-entries-msdyn_inventoryonhandentries"></a><a name="145"></a>Entradas de estoque disponível do CDS (msdyn_inventoryonhandentries)

Este modelo sincroniza dados entre aplicativos do Finance and Operations e do Dataverse.

Campo do Finance and Operations | Tipo de mapa | Campo do Customer Engagement | Valor padrão
---|---|---|---
`REQUESTID` | = | `msdyn_request.msdyn_requestid` |
`INVENTORYSITEID` | = | `msdyn_inventorysite.msdyn_siteid` |
`INVENTORYWAREHOUSEID` | = | `msdyn_inventorywarehouse.msdyn_warehouseidentifier` |
`AVAILABLEONHANDQUANTITY` | > | `msdyn_availableonhandquantity` |
`AVAILABLEORDEREDQUANTITY` | > | `msdyn_availableorderedquantity` |
`ONHANDQUANTITY` | > | `msdyn_onhandquantity` |
`ONORDERQUANTITY` | > | `msdyn_onorderquantity` |
`ORDEREDQUANTITY` | > | `msdyn_orderedquantity` |
`RESERVEDONHANDQUANTITY` | > | `msdyn_reservedonhandquantity` |
`RESERVEDORDEREDQUANTITY` | > | `msdyn_reservedorderedquantity` |
`TOTALAVAILABLEQUANTITY` | > | `msdyn_totalavailablequantity` |
`ATPDATE` | = | `msdyn_atpdate` |
`ATPQUANTITY` | > | `msdyn_atpquantity` |
`PROJECTEDISSUEQUANTITY` | > | `msdyn_projectedissuequantity` |
`PROJECTEDONHANDQUANTITY` | > | `msdyn_projectedonhandquantity` |
`PROJECTEDRECEIPTQUANTITY` | > | `msdyn_projectedreceiptquantity` |
`ORDERQUANTITY` | > | `msdyn_orderquantity` |
`UNAVAILABLEONHANDQUANTITY` | > | `msdyn_unavailableonhandquantity` |

###  <a name="cds-inventory-on-hand-requests-msdyn_inventoryonhandrequests"></a><a name="147"></a>Solicitações de estoque disponível do CDS (msdyn_inventoryonhandrequests)

Este modelo sincroniza dados entre aplicativos do Finance and Operations e do Dataverse.

Campo do Finance and Operations | Tipo de mapa | Campo do Customer Engagement | Valor padrão
---|---|---|---
`REQUESTID` | = | `msdyn_requestid` |
`PRODUCTNUMBER` | < | `msdyn_product.msdyn_productnumber` |
`ISATPCALCULATION` | << | `msdyn_isatpcalculation` |
`ORDERQUANTITY` | < | `msdyn_orderquantity` |
`INVENTORYSITEID` | < | `msdyn_inventorysite.msdyn_siteid` |
`INVENTORYWAREHOUSEID` | < | `msdyn_inventorywarehouse.msdyn_warehouseidentifier` |
`REFERENCENUMBER` | < | `msdyn_referencenumber` |
`LINECREATIONSEQUENCENUMBER` | < | `msdyn_linecreationsequencenumber` |






[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]