---
title: Ordens de compra para um projeto
description: Este artigo descreve os diversos métodos que podem ser usados para criar ordens de compra para um projeto. O método usado dependerá da finalidade da ordem de compra e de quando os itens comprados serão consumidos cobrados para um projeto.
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a4975b9f9e20906fb1259e36a07d8ef3db4f4fee
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174549"
---
# <a name="purchase-orders-for-a-project"></a><span data-ttu-id="0ad4c-104">Ordens de compra para um projeto</span><span class="sxs-lookup"><span data-stu-id="0ad4c-104">Purchase orders for a project</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0ad4c-105">Este artigo descreve os diversos métodos que podem ser usados para criar ordens de compra para um projeto.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-105">This article describes the various methods that you can use to create purchase orders for a project.</span></span> <span data-ttu-id="0ad4c-106">O método usado dependerá da finalidade da ordem de compra e de quando os itens comprados serão consumidos cobrados para um projeto.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-106">The method that you use depends on the purpose of the purchase order, and when the purchased items are consumed and charged to a project.</span></span>

### <a name="methods-for-creating-a-purchase-order"></a><span data-ttu-id="0ad4c-107">Métodos para criar uma ordem de compra</span><span class="sxs-lookup"><span data-stu-id="0ad4c-107">Methods for creating a purchase order</span></span>

<span data-ttu-id="0ad4c-108">Você pode usar um dos seguintes métodos para criar uma ordem de compra em Gerenciamento e contabilidade de projetos.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-108">You can use one of the following methods to create a purchase order in Project management and accounting.</span></span> <span data-ttu-id="0ad4c-109">A finalidade da ordem de compra determina quando ela é consumida e, portanto, quando os itens são cobrados para um projeto.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-109">The purpose of the purchase order determines when the purchase order is consumed and, therefore, when items are charged to a project.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ad4c-110">Método</span><span class="sxs-lookup"><span data-stu-id="0ad4c-110">Method</span></span></th>
<th><span data-ttu-id="0ad4c-111">Finalidade</span><span class="sxs-lookup"><span data-stu-id="0ad4c-111">Purpose</span></span></th>
<th><span data-ttu-id="0ad4c-112">Consumo de itens</span><span class="sxs-lookup"><span data-stu-id="0ad4c-112">Consumption of items</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0ad4c-113">Crie uma ordem de compra diretamente de um projeto.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-113">Create a purchase order directly from a project.</span></span></td>
<td><span data-ttu-id="0ad4c-114">Use este método para comprar itens de um fornecedor externo para consumo em um projeto.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-114">Use this method to purchase items from an external vendor for consumption on a project.</span></span> <span data-ttu-id="0ad4c-115">Você pode criar a ordem de compra de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="0ad4c-115">You can create the purchase order in two ways:</span></span>
<ul>
<li><span data-ttu-id="0ad4c-116">No próprio projeto.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-116">From the project itself.</span></span> <span data-ttu-id="0ad4c-117">Neste caso o projeto já está definido para a ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-117">In this case, the project is already defined for the purchase order.</span></span></li>
<li><span data-ttu-id="0ad4c-118">Navegando na ordem de compra de projeto.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-118">By navigating to the project purchase order.</span></span> <span data-ttu-id="0ad4c-119">Você deve selecionar o fornecedor e o projeto para os quais a ordem de compra será criada.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-119">You must select both the vendor and the project to create the purchase order for.</span></span></li>
</ul></td>
<td><span data-ttu-id="0ad4c-120">Os itens serão consumidos quando a nota fiscal do fornecedor for atualizada.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-120">Items are consumed when the vendor invoice is updated.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0ad4c-121">Criar uma ordem de compra a partir de uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-121">Create a purchase order from a sales order.</span></span></td>
<td><span data-ttu-id="0ad4c-122">Use este método para comprar itens ao criar uma ordem de venda de um projeto.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-122">Use this method to purchase items when you create a sales order from a project.</span></span></td>
<td><span data-ttu-id="0ad4c-123">Os itens serão consumidos quando a ordem de venda for faturada para o cliente.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-123">Items are consumed when the sales order is invoiced to the customer.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0ad4c-124">Criar uma ordem de compra a partir de uma requisição de itens.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-124">Create a purchase order from an item requirement.</span></span></td>
<td><span data-ttu-id="0ad4c-125">Use este método para comprar itens ao criar uma requisição de itens a partir de um projeto.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-125">Use this method to purchase items when you create an item requirement from a project.</span></span></td>
<td><span data-ttu-id="0ad4c-126">Os itens serão consumidos quando a guia de remessa da requisição de itens for atualizada.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-126">Items are consumed when the item requirement packing slip is updated.</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE] 
> <span data-ttu-id="0ad4c-127">Quando você atualiza a fatura do fornecedor ou a guia de remessa, o programa solicita a atualização da guia de remessa na requisição de itens.</span><span class="sxs-lookup"><span data-stu-id="0ad4c-127">When you update the vendor invoice or packing slip, you're prompted to update the packing slip on the item requirement.</span></span>

<span data-ttu-id="0ad4c-128">Para saber mais, consulte [Receber itens na ordem de compra da requisição de itens](tasks/receive-items-purchase-order-item-requirement.md).</span><span class="sxs-lookup"><span data-stu-id="0ad4c-128">For more information, see [Receive items on purchase order from item requirement](tasks/receive-items-purchase-order-item-requirement.md).</span></span>

