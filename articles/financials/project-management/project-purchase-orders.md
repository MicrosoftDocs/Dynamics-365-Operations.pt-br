---
title: Ordens de compra para um projeto
description: "Este artigo descreve os diversos métodos que podem ser usados para criar ordens de compra para um projeto. O método usado dependerá da finalidade da ordem de compra e de quando os itens comprados serão consumidos cobrados para um projeto."
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 985a57ae9fb116b1c4514b836b35c5da0f8838fd
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="purchase-orders-for-a-project"></a><span data-ttu-id="5c88b-104">Ordens de compra para um projeto</span><span class="sxs-lookup"><span data-stu-id="5c88b-104">Purchase orders for a project</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="5c88b-105">Este artigo descreve os diversos métodos que podem ser usados para criar ordens de compra para um projeto.</span><span class="sxs-lookup"><span data-stu-id="5c88b-105">This article describes the various methods that you can use to create purchase orders for a project.</span></span> <span data-ttu-id="5c88b-106">O método usado dependerá da finalidade da ordem de compra e de quando os itens comprados serão consumidos cobrados para um projeto.</span><span class="sxs-lookup"><span data-stu-id="5c88b-106">The method that you use depends on the purpose of the purchase order, and when the purchased items are consumed and charged to a project.</span></span>

<span data-ttu-id="5c88b-107">No Microsoft Dynamics 365 for Finance and Operations, edição Enterprise, você pode usar vários métodos para criar ordens de compra para um projeto.</span><span class="sxs-lookup"><span data-stu-id="5c88b-107">In Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, you can use multiple methods to create purchase orders for a project.</span></span> <span data-ttu-id="5c88b-108">O método usado dependerá da finalidade da ordem de compra, de quando os itens comprados serão consumidos e de quando eles serão cobrados para um projeto.</span><span class="sxs-lookup"><span data-stu-id="5c88b-108">The method that you use depends on the purpose of the purchase order, when the purchased items are consumed, and when the purchased items are charged to a project.</span></span>

### <a name="methods-for-creating-a-purchase-order"></a><span data-ttu-id="5c88b-109">Métodos para criar uma ordem de compra</span><span class="sxs-lookup"><span data-stu-id="5c88b-109">Methods for creating a purchase order</span></span>

<span data-ttu-id="5c88b-110">Você pode usar um dos seguintes métodos para criar uma ordem de compra em Gerenciamento e contabilidade de projetos.</span><span class="sxs-lookup"><span data-stu-id="5c88b-110">You can use one of the following methods to create a purchase order in Project management and accounting.</span></span> <span data-ttu-id="5c88b-111">A finalidade da ordem de compra determina quando ela é consumida e, portanto, quando os itens são cobrados para um projeto.</span><span class="sxs-lookup"><span data-stu-id="5c88b-111">The purpose of the purchase order determines when the purchase order is consumed and, therefore, when items are charged to a project.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5c88b-112">Método</span><span class="sxs-lookup"><span data-stu-id="5c88b-112">Method</span></span></th>
<th><span data-ttu-id="5c88b-113">Finalidade</span><span class="sxs-lookup"><span data-stu-id="5c88b-113">Purpose</span></span></th>
<th><span data-ttu-id="5c88b-114">Consumo de itens</span><span class="sxs-lookup"><span data-stu-id="5c88b-114">Consumption of items</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="5c88b-115">Crie uma ordem de compra diretamente de um projeto.</span><span class="sxs-lookup"><span data-stu-id="5c88b-115">Create a purchase order directly from a project.</span></span></td>
<td><span data-ttu-id="5c88b-116">Use este método para comprar itens de um fornecedor externo para consumo em um projeto.</span><span class="sxs-lookup"><span data-stu-id="5c88b-116">Use this method to purchase items from an external vendor for consumption on a project.</span></span> <span data-ttu-id="5c88b-117">Você pode criar a ordem de compra de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="5c88b-117">You can create the purchase order in two ways:</span></span>
<ul>
<li><span data-ttu-id="5c88b-118">No próprio projeto.</span><span class="sxs-lookup"><span data-stu-id="5c88b-118">From the project itself.</span></span> <span data-ttu-id="5c88b-119">Neste caso o projeto já está definido para a ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="5c88b-119">In this case, the project is already defined for the purchase order.</span></span></li>
<li><span data-ttu-id="5c88b-120">Navegando na ordem de compra de projeto.</span><span class="sxs-lookup"><span data-stu-id="5c88b-120">By navigating to the project purchase order.</span></span> <span data-ttu-id="5c88b-121">Você deve selecionar o fornecedor e o projeto para os quais a ordem de compra será criada.</span><span class="sxs-lookup"><span data-stu-id="5c88b-121">You must select both the vendor and the project to create the purchase order for.</span></span></li>
</ul></td>
<td><span data-ttu-id="5c88b-122">Os itens serão consumidos quando a nota fiscal do fornecedor for atualizada.</span><span class="sxs-lookup"><span data-stu-id="5c88b-122">Items are consumed when the vendor invoice is updated.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5c88b-123">Criar uma ordem de compra a partir de uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="5c88b-123">Create a purchase order from a sales order.</span></span></td>
<td><span data-ttu-id="5c88b-124">Use este método para comprar itens ao criar uma ordem de venda de um projeto.</span><span class="sxs-lookup"><span data-stu-id="5c88b-124">Use this method to purchase items when you create a sales order from a project.</span></span></td>
<td><span data-ttu-id="5c88b-125">Os itens serão consumidos quando a ordem de venda for faturada para o cliente.</span><span class="sxs-lookup"><span data-stu-id="5c88b-125">Items are consumed when the sales order is invoiced to the customer.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5c88b-126">Criar uma ordem de compra a partir de uma requisição de itens.</span><span class="sxs-lookup"><span data-stu-id="5c88b-126">Create a purchase order from an item requirement.</span></span></td>
<td><span data-ttu-id="5c88b-127">Use este método para comprar itens ao criar uma requisição de itens a partir de um projeto.</span><span class="sxs-lookup"><span data-stu-id="5c88b-127">Use this method to purchase items when you create an item requirement from a project.</span></span></td>
<td><span data-ttu-id="5c88b-128">Os itens serão consumidos quando a guia de remessa da requisição de itens for atualizada.</span><span class="sxs-lookup"><span data-stu-id="5c88b-128">Items are consumed when the item requirement packing slip is updated.</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE] 
> <span data-ttu-id="5c88b-129">Quando você atualiza a fatura do fornecedor ou a guia de remessa, o programa solicita a atualização da guia de remessa na requisição de itens.</span><span class="sxs-lookup"><span data-stu-id="5c88b-129">When you update the vendor invoice or packing slip, you're prompted to update the packing slip on the item requirement.</span></span>

<span data-ttu-id="5c88b-130">Para saber mais, consulte [Receber itens na ordem de compra da requisição de itens](tasks/receive-items-purchase-order-item-requirement.md).</span><span class="sxs-lookup"><span data-stu-id="5c88b-130">For more information, see [Receive items on purchase order from item requirement](tasks/receive-items-purchase-order-item-requirement.md).</span></span>


