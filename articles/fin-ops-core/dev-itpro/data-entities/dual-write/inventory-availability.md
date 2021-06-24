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
# <a name="inventory-availability-in-dual-write"></a><span data-ttu-id="52706-103">Disponibilidade de estoque em gravação dupla</span><span class="sxs-lookup"><span data-stu-id="52706-103">Inventory availability in dual-write</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="52706-104">Usando a disponibilidade de estoque, você pode verificar seu estoque antes de adicionar um produto à página **Cotações**, **Ordens** ou **Faturas** no Microsoft Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="52706-104">By using inventory availability, you can check your inventory before you add a product to the **Quotations**, **Orders**, or **Invoices** page in Microsoft Dynamics 365 Sales.</span></span> <span data-ttu-id="52706-105">Por exemplo, você verifica o estoque e determina uma data de atendimento como uma tarefa fundamental no processo de [pagamento à vista](dual-write-prospect-to-cash.md).</span><span class="sxs-lookup"><span data-stu-id="52706-105">For example, you check inventory and determine a fulfillment date as one key task in the [prospect-to-cash](dual-write-prospect-to-cash.md) process.</span></span>

<span data-ttu-id="52706-106">Se não tiver estoque suficiente, você poderá estimar uma data de entrega com base em recebimentos e saídas de estoque projetado.</span><span class="sxs-lookup"><span data-stu-id="52706-106">If you don't have enough inventory, you can estimate a delivery date, based on projected inventory receipts and issues.</span></span> <span data-ttu-id="52706-107">Você também pode verificar as informações de disponível para promessa (ATP), em que é possível encontrar a quantidade ATP no limite de tempo predefinido.</span><span class="sxs-lookup"><span data-stu-id="52706-107">You can also check the product's available-to-promise (ATP) information, where you can find the ATP quantity in the predefined time fence.</span></span>

## <a name="on-hand-inventory"></a><span data-ttu-id="52706-108">Estoque Disponível</span><span class="sxs-lookup"><span data-stu-id="52706-108">On-hand inventory</span></span>

<span data-ttu-id="52706-109">No Dynamics 365 Sales, um novo botão **Estoque disponível** foi adicionado ao cabeçalho das páginas **Cotações**, **Ordens** e **Faturas**.</span><span class="sxs-lookup"><span data-stu-id="52706-109">In Dynamics 365 Sales, a new **On-hand Inventory** button has been added to the header of the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="52706-110">Quando você seleciona esse botão, uma caixa de diálogo é exibida e você pode especificar a empresa e o produto para o qual deseja verificar o estoque disponível.</span><span class="sxs-lookup"><span data-stu-id="52706-110">When you select this button, a dialog box appears, where you can specify the company and the product that you want to check the on-hand inventory for.</span></span> <span data-ttu-id="52706-111">Essa caixa de diálogo mostra as mesmas informações do que o [Estoque disponível](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span><span class="sxs-lookup"><span data-stu-id="52706-111">This dialog box shows the same information as [On-hand inventory](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span></span>

<span data-ttu-id="52706-112">A caixa de diálogo retorna as informações de estoque do Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="52706-112">The dialog box returns the inventory information from Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="52706-113">Essas informações incluem as seguintes quantidades:</span><span class="sxs-lookup"><span data-stu-id="52706-113">This information includes the following quantities:</span></span>

- <span data-ttu-id="52706-114">Quantidade disponível</span><span class="sxs-lookup"><span data-stu-id="52706-114">On-hand quantity</span></span>
- <span data-ttu-id="52706-115">Quantidade disponível reservada</span><span class="sxs-lookup"><span data-stu-id="52706-115">Reserved on-hand quantity</span></span>
- <span data-ttu-id="52706-116">Quantidade disponível</span><span class="sxs-lookup"><span data-stu-id="52706-116">Available on-hand quantity</span></span>
- <span data-ttu-id="52706-117">Quantidade encomendada</span><span class="sxs-lookup"><span data-stu-id="52706-117">Ordered quantity</span></span>
- <span data-ttu-id="52706-118">Quantidade na ordem</span><span class="sxs-lookup"><span data-stu-id="52706-118">On-order quantity</span></span>
- <span data-ttu-id="52706-119">Quantidade encomendada reservada</span><span class="sxs-lookup"><span data-stu-id="52706-119">Reserved ordered quantity</span></span>
- <span data-ttu-id="52706-120">Quantidade disponível total</span><span class="sxs-lookup"><span data-stu-id="52706-120">Total available quantity</span></span>

## <a name="atp-information"></a><span data-ttu-id="52706-121">Informações sobre ATP</span><span class="sxs-lookup"><span data-stu-id="52706-121">ATP information</span></span>

<span data-ttu-id="52706-122">No Sales, um novo botão **Informações sobre ATP** foi adicionado aos itens de linha nas páginas **Cotações**, **Ordens** e **Faturas**.</span><span class="sxs-lookup"><span data-stu-id="52706-122">In Sales, a new **ATP Information** button has been added to line items on the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="52706-123">Quando você selecione essa botão, uma caixa de diálogo é exibida e você pode especificar empresa, produto, site do estoque, depósito de estoque e quantidade da ordem.</span><span class="sxs-lookup"><span data-stu-id="52706-123">When you select this button, a dialog box appears, where you can specify the company, product, inventory site, inventory warehouse, and order quantity.</span></span> <span data-ttu-id="52706-124">Essa caixa de diálogo tem as mesmas configurações descritas em [Promessa de ordem](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span><span class="sxs-lookup"><span data-stu-id="52706-124">This dialog box has the same settings that are described in [Order promising](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span></span>

<span data-ttu-id="52706-125">A caixa de diálogo retorna as informações sobre ATP do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="52706-125">The dialog box returns the ATP information from Supply Chain Management.</span></span> <span data-ttu-id="52706-126">Essas informações incluem as seguintes quantidades:</span><span class="sxs-lookup"><span data-stu-id="52706-126">This information includes the following quantities:</span></span>

- <span data-ttu-id="52706-127">Quantidade ATP</span><span class="sxs-lookup"><span data-stu-id="52706-127">ATP quantity</span></span>
- <span data-ttu-id="52706-128">Quantidade recebida</span><span class="sxs-lookup"><span data-stu-id="52706-128">Receipt quantity</span></span>
- <span data-ttu-id="52706-129">Quantidade emitida</span><span class="sxs-lookup"><span data-stu-id="52706-129">Issue quantity</span></span>
- <span data-ttu-id="52706-130">Quantidade disponível</span><span class="sxs-lookup"><span data-stu-id="52706-130">On-hand quantity</span></span>

## <a name="how-it-works"></a><span data-ttu-id="52706-131">Como funciona</span><span class="sxs-lookup"><span data-stu-id="52706-131">How it works</span></span>

<span data-ttu-id="52706-132">Ao selecionar o botão **Estoque disponível** na página **Cotações**, **Pedidos** ou **Faturas**, uma chamada de gravação dupla será feita para a API **Estoque disponível**.</span><span class="sxs-lookup"><span data-stu-id="52706-132">When you select the **On-hand Inventory** button on the **Quotes**, **Orders**, or **Invoices** page, a live dual-write call is made to the **Onhand inventory** API.</span></span> <span data-ttu-id="52706-133">A API calcula o estoque disponível do produto fornecido.</span><span class="sxs-lookup"><span data-stu-id="52706-133">The API calculates the on-hand inventory for the given product.</span></span> <span data-ttu-id="52706-134">O resultado é armazenado nas tabelas **InventCDSInventoryOnHandRequestEntity** e **InventCDSInventoryOnHandEntryEntity** e, em seguida, é registrado no Dataverse por gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="52706-134">The result is stored in the **InventCDSInventoryOnHandRequestEntity** and **InventCDSInventoryOnHandEntryEntity** tables, and then is written to Dataverse by dual-write.</span></span> <span data-ttu-id="52706-135">Para usar essa funcionalidade, é necessário executar os seguintes mapas de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="52706-135">To use this functionality, you need to run the following dual-write maps.</span></span> <span data-ttu-id="52706-136">Ignore a sincronização inicial ao executar os mapas.</span><span class="sxs-lookup"><span data-stu-id="52706-136">Skip initial synchronization when you run the maps.</span></span>

- <span data-ttu-id="52706-137">Entradas de estoque disponível do CDS (msdyn_inventoryonhandentries)</span><span class="sxs-lookup"><span data-stu-id="52706-137">CDS inventory on-hand entries (msdyn_inventoryonhandentries)</span></span>
- <span data-ttu-id="52706-138">Solicitações de estoque disponível do CDS (msdyn_inventoryonhandrequests)</span><span class="sxs-lookup"><span data-stu-id="52706-138">CDS inventory on-hand requests (msdyn_inventoryonhandrequests)</span></span>

## <a name="templates"></a><span data-ttu-id="52706-139">Modelos</span><span class="sxs-lookup"><span data-stu-id="52706-139">Templates</span></span>
<span data-ttu-id="52706-140">Os seguintes modelos estão disponíveis para a exposição de dados de estoque disponível.</span><span class="sxs-lookup"><span data-stu-id="52706-140">The following templates are available for the exposing the onhand inventory data.</span></span>

<span data-ttu-id="52706-141">Aplicativos Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="52706-141">Finance and Operations apps</span></span> | <span data-ttu-id="52706-142">Aplicativo Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="52706-142">Customer engagement app</span></span> | <span data-ttu-id="52706-143">descrição</span><span class="sxs-lookup"><span data-stu-id="52706-143">Description</span></span> 
---|---|---
[<span data-ttu-id="52706-144">Entradas de estoque disponível do CDS</span><span class="sxs-lookup"><span data-stu-id="52706-144">CDS inventory on-hand entries</span></span>](#145) | <span data-ttu-id="52706-145">msdyn_inventoryonhandentries</span><span class="sxs-lookup"><span data-stu-id="52706-145">msdyn_inventoryonhandentries</span></span> |
[<span data-ttu-id="52706-146">Solicitações de estoque disponível do CDS</span><span class="sxs-lookup"><span data-stu-id="52706-146">CDS inventory on-hand requests</span></span>](#147) | <span data-ttu-id="52706-147">msdyn_inventoryonhandrequests</span><span class="sxs-lookup"><span data-stu-id="52706-147">msdyn_inventoryonhandrequests</span></span> |

[!include [banner](../../includes/dual-write-symbols.md)]

###  <a name="cds-inventory-on-hand-entries-msdyn_inventoryonhandentries"></a><a name="145"></a><span data-ttu-id="52706-148">Entradas de estoque disponível do CDS (msdyn_inventoryonhandentries)</span><span class="sxs-lookup"><span data-stu-id="52706-148">CDS inventory on-hand entries (msdyn_inventoryonhandentries)</span></span>

<span data-ttu-id="52706-149">Este modelo sincroniza dados entre aplicativos do Finance and Operations e do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="52706-149">This template synchronizes data between Finance and Operations apps and Dataverse.</span></span>

<span data-ttu-id="52706-150">Campo do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="52706-150">Finance and Operations field</span></span> | <span data-ttu-id="52706-151">Tipo de mapa</span><span class="sxs-lookup"><span data-stu-id="52706-151">Map type</span></span> | <span data-ttu-id="52706-152">Campo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="52706-152">Customer engagement field</span></span> | <span data-ttu-id="52706-153">Valor padrão</span><span class="sxs-lookup"><span data-stu-id="52706-153">Default value</span></span>
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

###  <a name="cds-inventory-on-hand-requests-msdyn_inventoryonhandrequests"></a><a name="147"></a><span data-ttu-id="52706-154">Solicitações de estoque disponível do CDS (msdyn_inventoryonhandrequests)</span><span class="sxs-lookup"><span data-stu-id="52706-154">CDS inventory on-hand requests (msdyn_inventoryonhandrequests)</span></span>

<span data-ttu-id="52706-155">Este modelo sincroniza dados entre aplicativos do Finance and Operations e do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="52706-155">This template synchronizes data between Finance and Operations apps and Dataverse.</span></span>

<span data-ttu-id="52706-156">Campo do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="52706-156">Finance and Operations field</span></span> | <span data-ttu-id="52706-157">Tipo de mapa</span><span class="sxs-lookup"><span data-stu-id="52706-157">Map type</span></span> | <span data-ttu-id="52706-158">Campo do Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="52706-158">Customer engagement field</span></span> | <span data-ttu-id="52706-159">Valor padrão</span><span class="sxs-lookup"><span data-stu-id="52706-159">Default value</span></span>
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