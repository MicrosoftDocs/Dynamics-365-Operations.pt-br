---
title: "Exemplo de dias de redução"
description: "Exemplo de dias de redução."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 69e4b1b0fe100b17e5b2c59be81604019347956f
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---


# <a name="reduction-days-example"></a><span data-ttu-id="1aa35-103">Exemplo de dias de redução</span><span class="sxs-lookup"><span data-stu-id="1aa35-103">Reduction days example</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="1aa35-104">Você criou uma transação de subscrição para a subscrição de manutenção de um cliente, conforme descrito na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="1aa35-104">You have created a subscription transaction for a customer's maintenance subscription, as described in the following table.</span></span>

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1aa35-105">De</span><span class="sxs-lookup"><span data-stu-id="1aa35-105">From date</span></span></p></th>
<th><p><span data-ttu-id="1aa35-106">Até</span><span class="sxs-lookup"><span data-stu-id="1aa35-106">To date</span></span></p></th>
<th><p><span data-ttu-id="1aa35-107">Subscrição</span><span class="sxs-lookup"><span data-stu-id="1aa35-107">Subscription</span></span></p></th>
<th><p><span data-ttu-id="1aa35-108">Tipo de subscrição</span><span class="sxs-lookup"><span data-stu-id="1aa35-108">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="1aa35-109">Project</span><span class="sxs-lookup"><span data-stu-id="1aa35-109">Project</span></span></p></th>
<th><p><span data-ttu-id="1aa35-110">Categoria</span><span class="sxs-lookup"><span data-stu-id="1aa35-110">Category</span></span></p></th>
<th><p><span data-ttu-id="1aa35-111">Moeda de venda</span><span class="sxs-lookup"><span data-stu-id="1aa35-111">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="1aa35-112">Preço de venda</span><span class="sxs-lookup"><span data-stu-id="1aa35-112">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1aa35-113">01 de março, 2011</span><span class="sxs-lookup"><span data-stu-id="1aa35-113">March 01, 2011</span></span></p></td>
<td><p><span data-ttu-id="1aa35-114">31 de março, 2011</span><span class="sxs-lookup"><span data-stu-id="1aa35-114">March 31, 2011</span></span></p></td>
<td><p><span data-ttu-id="1aa35-115">NR-2</span><span class="sxs-lookup"><span data-stu-id="1aa35-115">NR-2</span></span></p></td>
<td><p><span data-ttu-id="1aa35-116"><strong>Normal</strong></span><span class="sxs-lookup"><span data-stu-id="1aa35-116"><strong>Regular</strong></span></span></p></td>
<td><p><span data-ttu-id="1aa35-117">9013</span><span class="sxs-lookup"><span data-stu-id="1aa35-117">9013</span></span></p></td>
<td><p><span data-ttu-id="1aa35-118">SubCat2</span><span class="sxs-lookup"><span data-stu-id="1aa35-118">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="1aa35-119">EUR</span><span class="sxs-lookup"><span data-stu-id="1aa35-119">EUR</span></span></p></td>
<td><p><span data-ttu-id="1aa35-120">200,00</span><span class="sxs-lookup"><span data-stu-id="1aa35-120">200.00</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1aa35-121">O cliente informa que não precisa da cobertura do serviço por dois dias (10 e 11 de março).</span><span class="sxs-lookup"><span data-stu-id="1aa35-121">The customer reports that it does not need service coverage for two days (March 10 and March 11).</span></span> <span data-ttu-id="1aa35-122">Você concorda em reduzir esses dois dias da subscrição.</span><span class="sxs-lookup"><span data-stu-id="1aa35-122">You agree to reduce the subscription by these two days.</span></span>

<span data-ttu-id="1aa35-123">Você cria uma nova transação do tipo **Dias de redução**, conforme descrito na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="1aa35-123">You create a new transaction of the **Reduction days** type, as described in the following table.</span></span>

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1aa35-124">De</span><span class="sxs-lookup"><span data-stu-id="1aa35-124">From date</span></span></p></th>
<th><p><span data-ttu-id="1aa35-125">Até</span><span class="sxs-lookup"><span data-stu-id="1aa35-125">To date</span></span></p></th>
<th><p><span data-ttu-id="1aa35-126">Subscrição</span><span class="sxs-lookup"><span data-stu-id="1aa35-126">Subscription</span></span></p></th>
<th><p><span data-ttu-id="1aa35-127">Tipo de subscrição</span><span class="sxs-lookup"><span data-stu-id="1aa35-127">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="1aa35-128">Project</span><span class="sxs-lookup"><span data-stu-id="1aa35-128">Project</span></span></p></th>
<th><p><span data-ttu-id="1aa35-129">Categoria</span><span class="sxs-lookup"><span data-stu-id="1aa35-129">Category</span></span></p></th>
<th><p><span data-ttu-id="1aa35-130">Moeda de venda</span><span class="sxs-lookup"><span data-stu-id="1aa35-130">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="1aa35-131">Preço de venda</span><span class="sxs-lookup"><span data-stu-id="1aa35-131">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1aa35-132">10 de março, 2011</span><span class="sxs-lookup"><span data-stu-id="1aa35-132">March 10, 2011</span></span></p></td>
<td><p><span data-ttu-id="1aa35-133">11 de março, 2011</span><span class="sxs-lookup"><span data-stu-id="1aa35-133">March 11, 2011</span></span></p></td>
<td><p><span data-ttu-id="1aa35-134">NR-2</span><span class="sxs-lookup"><span data-stu-id="1aa35-134">NR-2</span></span></p></td>
<td><p><span data-ttu-id="1aa35-135"><strong>Dias de redução</strong></span><span class="sxs-lookup"><span data-stu-id="1aa35-135"><strong>Reduction days</strong></span></span></p></td>
<td><p><span data-ttu-id="1aa35-136">9013</span><span class="sxs-lookup"><span data-stu-id="1aa35-136">9013</span></span></p></td>
<td><p><span data-ttu-id="1aa35-137">SubCat2</span><span class="sxs-lookup"><span data-stu-id="1aa35-137">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="1aa35-138">EUR</span><span class="sxs-lookup"><span data-stu-id="1aa35-138">EUR</span></span></p></td>
<td><p><span data-ttu-id="1aa35-139">-12,90</span><span class="sxs-lookup"><span data-stu-id="1aa35-139">-12.90</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1aa35-140">Quando as transações de março de 2011 são faturadas, o preço de venda de 200 euros é reduzido em 12,90 euros.</span><span class="sxs-lookup"><span data-stu-id="1aa35-140">When the transactions for March 2011 are invoiced, the sales price of EUR 200 is reduced by EUR 12.90.</span></span> <span data-ttu-id="1aa35-141">Portanto, o valor passível de cobrança da transação de subscrição é de 187,10 euros, e duas transações são faturadas no total de 187,10 euros.</span><span class="sxs-lookup"><span data-stu-id="1aa35-141">The chargeable amount for the subscription transaction is therefore EUR 187.10, and two transactions are invoiced at a total of EUR 187.10.</span></span>

## <a name="see-also"></a><span data-ttu-id="1aa35-142">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1aa35-142">See also</span></span>

[<span data-ttu-id="1aa35-143">Reduzir os dias em taxas de subscrição</span><span class="sxs-lookup"><span data-stu-id="1aa35-143">Reduce the days on subscription fees</span></span>](reduce-the-days-on-subscription-fees.md)

  



