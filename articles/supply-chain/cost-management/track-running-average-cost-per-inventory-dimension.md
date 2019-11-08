---
title: Rastrear o custo médio por dimensão de estoque
description: Um grupo de dimensões de estoque é anexado a cada item de estoque. Portanto, o preço de custo médio de um item é calculado com base nas dimensões de estoque selecionadas que estão sendo rastreadas financeiramente.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventOnhandItem
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 75053
ms.assetid: 68cc00f4-0f7a-4a7d-be90-8f2e0d0563d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bdf8115bef3b56b9148539b4add95c5b1e8cd9c7
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2019
ms.locfileid: "2569170"
---
# <a name="track-running-average-cost-per-inventory-dimension"></a><span data-ttu-id="e4e64-104">Rastrear o custo médio por dimensão de estoque</span><span class="sxs-lookup"><span data-stu-id="e4e64-104">Track running average cost per inventory dimension</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e4e64-105">Um grupo de dimensões de estoque é anexado a cada item de estoque.</span><span class="sxs-lookup"><span data-stu-id="e4e64-105">An inventory dimension group is attached to every inventory item.</span></span> <span data-ttu-id="e4e64-106">Portanto, o preço de custo médio de um item é calculado com base nas dimensões de estoque selecionadas que estão sendo rastreadas financeiramente.</span><span class="sxs-lookup"><span data-stu-id="e4e64-106">Therefore, the running average cost price of an item is calculated based on the selected inventory dimensions that are being tracked financially.</span></span>

<span data-ttu-id="e4e64-107">Há três tipos de dimensões de estoque: produto, armazenamento e rastreamento.</span><span class="sxs-lookup"><span data-stu-id="e4e64-107">There are three types of inventory dimensions: product, storage, and tracking.</span></span> <span data-ttu-id="e4e64-108">As dimensões de produto incluem a configuração, o tamanho e a cor.</span><span class="sxs-lookup"><span data-stu-id="e4e64-108">Product dimensions include configuration, size, and color.</span></span> <span data-ttu-id="e4e64-109">As dimensões de produto sempre são rastreadas financeiramente.</span><span class="sxs-lookup"><span data-stu-id="e4e64-109">Product dimensions are always tracked financially.</span></span> <span data-ttu-id="e4e64-110">As dimensões de armazenamento e de rastreamento incluem o site, o depósito, a localização, o status de estoque, a placa de licença, o número do lote e o número de série.</span><span class="sxs-lookup"><span data-stu-id="e4e64-110">Storage and tracking dimensions include site, warehouse, location, inventory status, license plate, batch number, and serial number.</span></span> <span data-ttu-id="e4e64-111">Você pode decidir quais dimensões de armazenamento e de rastreamento são rastreadas financeiramente.</span><span class="sxs-lookup"><span data-stu-id="e4e64-111">You can decide which storage and tracking dimensions are tracked financially.</span></span> 

<span data-ttu-id="e4e64-112">**Exemplo 1**</span><span class="sxs-lookup"><span data-stu-id="e4e64-112">**Example 1**</span></span> 

<span data-ttu-id="e4e64-113">Se o grupo de dimensões de armazenamento que for anexado ao item, for rastreado financeiramente por depósito, o preço de custo médio será calculado por depósito.</span><span class="sxs-lookup"><span data-stu-id="e4e64-113">If the storage dimension group that is attached to the item is financially tracked by warehouse, the running average cost price is calculated per warehouse.</span></span> <span data-ttu-id="e4e64-114">Estas ordens de compra foram faturadas:</span><span class="sxs-lookup"><span data-stu-id="e4e64-114">The following purchase orders have been invoiced:</span></span>

-   <span data-ttu-id="e4e64-115">Uma ordem de compra para uma quantidade de 2 ao preço de custo de BRL 10,00 foi faturada para o depósito GW.</span><span class="sxs-lookup"><span data-stu-id="e4e64-115">A purchase order for a quantity of 2 at a cost price of USD 10.00 has been invoiced for warehouse GW.</span></span>
-   <span data-ttu-id="e4e64-116">Um ordem de compra para uma quantidade de 3 ao preço de custo de BRL 12,00 foi faturada para o depósito GW.</span><span class="sxs-lookup"><span data-stu-id="e4e64-116">A purchase order for a quantity of 3 at a cost price of USD 12.00 has been invoiced for warehouse GW.</span></span>
-   <span data-ttu-id="e4e64-117">Uma ordem de compra para uma quantidade de 5 ao preço de custo de BRL 15,00 foi faturada para o depósito MW.</span><span class="sxs-lookup"><span data-stu-id="e4e64-117">A purchase order for a quantity of 5 at a cost price of USD 15.00 has been invoiced for warehouse MW.</span></span>

<span data-ttu-id="e4e64-118">O preço de custo médio para o depósito GW é BRL 11.20, e o preço de custo médio para o depósito MW é BRL 15.00.</span><span class="sxs-lookup"><span data-stu-id="e4e64-118">The running average cost price for warehouse GW is USD 11.20, and the running average cost price for warehouse MW is USD 15.00.</span></span> <span data-ttu-id="e4e64-119">Uma fatura de ordem de venda é lançada para o depósito GW.</span><span class="sxs-lookup"><span data-stu-id="e4e64-119">A sales order invoice is posted for warehouse GW.</span></span> <span data-ttu-id="e4e64-120">O valor do estoque e o custo dos produtos vendidos (antes do fechamento do estoque é executado sem marcação) será BRL 11,20.</span><span class="sxs-lookup"><span data-stu-id="e4e64-120">The value of the inventory and the cost of goods sold (before inventory close is run and without marking) is USD 11.20.</span></span> <span data-ttu-id="e4e64-121">Outra ordem de venda é lançada para o depósito MW.</span><span class="sxs-lookup"><span data-stu-id="e4e64-121">Another sales order is posted for warehouse MW.</span></span> <span data-ttu-id="e4e64-122">O valor do estoque e o custo dos produtos vendidos (antes do fechamento do estoque é executado sem marcação) será BRL 15,00.</span><span class="sxs-lookup"><span data-stu-id="e4e64-122">The value of the inventory and the cost of goods sold (before inventory close is run and without marking) is USD 15.00.</span></span> 

<span data-ttu-id="e4e64-123">**Exemplo 2** Se o grupo de dimensões de armazenamento que está associado ao item for rastreado financeiramente pelo depósito, e o grupo de dimensões de rastreamento for rastreado financeiramente por número de lote, o preço de custo médio será calculado para cada lote.</span><span class="sxs-lookup"><span data-stu-id="e4e64-123">**Example 2** If the storage dimension group that is attached to the item is financially tracked by warehouse, and the tracking dimension group is financially tracked by batch number, the running average cost price is calculated for each batch.</span></span> 

<span data-ttu-id="e4e64-124">**Observação:** Recomenda-se que você sempre exiba o preço de custo de todas as dimensões financeiras que estão sendo rastreadas.</span><span class="sxs-lookup"><span data-stu-id="e4e64-124">**Note:** We recommend that you always view the cost price for all financial dimensions that are being tracked.</span></span> <span data-ttu-id="e4e64-125">Estas ordens de compra foram faturadas:</span><span class="sxs-lookup"><span data-stu-id="e4e64-125">The following purchase orders have been invoiced:</span></span>

-   <span data-ttu-id="e4e64-126">Uma ordem de compra para uma quantidade de 2 ao preço de custo de BRL 10,00 foi faturada para o depósito GW e o lote AAA.</span><span class="sxs-lookup"><span data-stu-id="e4e64-126">A purchase order for a quantity of 2 at a cost price of USD 10.00 has been invoiced for warehouse GW and batch AAA.</span></span>
-   <span data-ttu-id="e4e64-127">Uma ordem de compra para uma quantidade de 3 ao preço de custo de BRL 12,00 foi faturada para o depósito GW e o lote AAA.</span><span class="sxs-lookup"><span data-stu-id="e4e64-127">A purchase order for a quantity of 3 at a cost price of USD 12.00 has been invoiced for warehouse GW and batch AAA.</span></span>
-   <span data-ttu-id="e4e64-128">Uma ordem de compra para uma quantidade de 2 ao preço de custo de BRL 15,00 foi faturada para o depósito GW e o lote BBB.</span><span class="sxs-lookup"><span data-stu-id="e4e64-128">A purchase order for a quantity of 2 at a cost price of USD 15.00 has been invoiced for warehouse GW and batch BBB.</span></span>

<span data-ttu-id="e4e64-129">O preço de custo médio para o depósito GW e lote AAA é BRL 11,20, e o preço de custo médio para o depósito GW e lote BBB é BRL 15,00.</span><span class="sxs-lookup"><span data-stu-id="e4e64-129">The running average cost price for warehouse GW and batch AAA is USD 11.20, and the running average cost price for warehouse GW and batch BBB is USD 15.00.</span></span>



