---
title: Preços de venda de subscrição
description: Quando você cria uma subscrição, o preço de venda é derivado da configuração do preço de venda criada no formulário Subscrição do preço de venda.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASalespriceSubscription
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 35f4e3f3bdbdad7a48b89bad7da96d221f09bdb4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974201"
---
# <a name="subscription-sales-prices"></a><span data-ttu-id="fc971-103">Preços de venda de subscrição</span><span class="sxs-lookup"><span data-stu-id="fc971-103">Subscription sales prices</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="fc971-104">Quando você cria uma subscrição, o preço de venda é derivado da configuração do preço de venda criada no formulário **Subscrição do preço de venda**.</span><span class="sxs-lookup"><span data-stu-id="fc971-104">When you create a subscription, the sales price is derived from the sales price setup that was created in the **Sales price (subscription)** form.</span></span>

<span data-ttu-id="fc971-105">No formulário **Subscrição do preço de venda**, você pode criar preços de venda para uma subscrição específica ou pode criar preços de venda com uma aplicação mais ampla.</span><span class="sxs-lookup"><span data-stu-id="fc971-105">In the **Sales price (subscription)** form, you can create sales prices for a specific subscription or you can create sales prices that apply more broadly.</span></span> <span data-ttu-id="fc971-106">Para que um preço de venda seja aplicado a uma subscrição, o código de período e a moeda da subscrição e do preço de venda devem ser idênticos.</span><span class="sxs-lookup"><span data-stu-id="fc971-106">For a sales price to be applied to a subscription, the period code and the currency of the subscription must be identical to the period code and the currency of the sales price.</span></span>

<span data-ttu-id="fc971-107">Se o código de período e a moeda forem idênticos para ambas a subscrição e o preço de venda, os preços de venda da subscrição serão selecionados com base nas prioridades listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="fc971-107">If the period code and currency are identical for the subscription and the sales price, subscription sales prices are selected on the basis of the priorities listed in the following table.</span></span> <span data-ttu-id="fc971-108">Uma célula em branco na tabela indica um campo vazio e um X indica um valor igual ao valor na subscrição da qual a transação é gerada.</span><span class="sxs-lookup"><span data-stu-id="fc971-108">A blank cell in the table indicates an empty field and an X indicates a value that is equal to the value in the subscription from which the transaction is generated.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fc971-109">Prioridade</span><span class="sxs-lookup"><span data-stu-id="fc971-109">Priority</span></span></p></th>
<th><p><span data-ttu-id="fc971-110"><strong>Categoria</strong></span><span class="sxs-lookup"><span data-stu-id="fc971-110"><strong>Category</strong></span></span></p></th>
<th><p><span data-ttu-id="fc971-111"><strong>ID do projeto</strong></span><span class="sxs-lookup"><span data-stu-id="fc971-111"><strong>Project ID</strong></span></span></p></th>
<th><p><span data-ttu-id="fc971-112"><strong>Subscrição</strong></span><span class="sxs-lookup"><span data-stu-id="fc971-112"><strong>Subscription</strong></span></span></p></th>
<th><p><span data-ttu-id="fc971-113"><strong>Moeda de venda</strong></span><span class="sxs-lookup"><span data-stu-id="fc971-113"><strong>Sales currency</strong></span></span></p></th>
<th><p><span data-ttu-id="fc971-114"><strong>Código de período</strong></span><span class="sxs-lookup"><span data-stu-id="fc971-114"><strong>Period code</strong></span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc971-115">1</span><span class="sxs-lookup"><span data-stu-id="fc971-115">1</span></span></p></td>
<td><p><span data-ttu-id="fc971-116">X</span><span class="sxs-lookup"><span data-stu-id="fc971-116">X</span></span></p></td>
<td><p><span data-ttu-id="fc971-117">X</span><span class="sxs-lookup"><span data-stu-id="fc971-117">X</span></span></p></td>
<td><p><span data-ttu-id="fc971-118">X</span><span class="sxs-lookup"><span data-stu-id="fc971-118">X</span></span></p></td>
<td><p><span data-ttu-id="fc971-119">X</span><span class="sxs-lookup"><span data-stu-id="fc971-119">X</span></span></p></td>
<td><p><span data-ttu-id="fc971-120">X</span><span class="sxs-lookup"><span data-stu-id="fc971-120">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc971-121">2</span><span class="sxs-lookup"><span data-stu-id="fc971-121">2</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="fc971-122">X</span><span class="sxs-lookup"><span data-stu-id="fc971-122">X</span></span></p></td>
<td><p><span data-ttu-id="fc971-123">X</span><span class="sxs-lookup"><span data-stu-id="fc971-123">X</span></span></p></td>
<td><p><span data-ttu-id="fc971-124">X</span><span class="sxs-lookup"><span data-stu-id="fc971-124">X</span></span></p></td>
<td><p><span data-ttu-id="fc971-125">X</span><span class="sxs-lookup"><span data-stu-id="fc971-125">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc971-126">3</span><span class="sxs-lookup"><span data-stu-id="fc971-126">3</span></span></p></td>
<td><p><span data-ttu-id="fc971-127">X</span><span class="sxs-lookup"><span data-stu-id="fc971-127">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="fc971-128">X</span><span class="sxs-lookup"><span data-stu-id="fc971-128">X</span></span></p></td>
<td><p><span data-ttu-id="fc971-129">X</span><span class="sxs-lookup"><span data-stu-id="fc971-129">X</span></span></p></td>
<td><p><span data-ttu-id="fc971-130">X</span><span class="sxs-lookup"><span data-stu-id="fc971-130">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc971-131">4</span><span class="sxs-lookup"><span data-stu-id="fc971-131">4</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="fc971-132">X</span><span class="sxs-lookup"><span data-stu-id="fc971-132">X</span></span></p></td>
<td><p><span data-ttu-id="fc971-133">X</span><span class="sxs-lookup"><span data-stu-id="fc971-133">X</span></span></p></td>
<td><p><span data-ttu-id="fc971-134">X</span><span class="sxs-lookup"><span data-stu-id="fc971-134">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc971-135">5</span><span class="sxs-lookup"><span data-stu-id="fc971-135">5</span></span></p></td>
<td><p><span data-ttu-id="fc971-136">X</span><span class="sxs-lookup"><span data-stu-id="fc971-136">X</span></span></p></td>
<td><p><span data-ttu-id="fc971-137">X</span><span class="sxs-lookup"><span data-stu-id="fc971-137">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="fc971-138">X</span><span class="sxs-lookup"><span data-stu-id="fc971-138">X</span></span></p></td>
<td><p><span data-ttu-id="fc971-139">X</span><span class="sxs-lookup"><span data-stu-id="fc971-139">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc971-140">6</span><span class="sxs-lookup"><span data-stu-id="fc971-140">6</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="fc971-141">X</span><span class="sxs-lookup"><span data-stu-id="fc971-141">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="fc971-142">X</span><span class="sxs-lookup"><span data-stu-id="fc971-142">X</span></span></p></td>
<td><p><span data-ttu-id="fc971-143">X</span><span class="sxs-lookup"><span data-stu-id="fc971-143">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc971-144">7</span><span class="sxs-lookup"><span data-stu-id="fc971-144">7</span></span></p></td>
<td><p><span data-ttu-id="fc971-145">X</span><span class="sxs-lookup"><span data-stu-id="fc971-145">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="fc971-146">X</span><span class="sxs-lookup"><span data-stu-id="fc971-146">X</span></span></p></td>
<td><p><span data-ttu-id="fc971-147">X</span><span class="sxs-lookup"><span data-stu-id="fc971-147">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc971-148">8</span><span class="sxs-lookup"><span data-stu-id="fc971-148">8</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="fc971-149">X</span><span class="sxs-lookup"><span data-stu-id="fc971-149">X</span></span></p></td>
<td><p><span data-ttu-id="fc971-150">X</span><span class="sxs-lookup"><span data-stu-id="fc971-150">X</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fc971-151">Quando uma taxa de subscrição é criada, o preço de venda com o maior nível de detalhe, como observado na tabela acima, é selecionado como o preço de venda da subscrição.</span><span class="sxs-lookup"><span data-stu-id="fc971-151">When a subscription fee is created, the sales price with the greatest level of detail, as noted in the table above, is selected as the subscription sales price.</span></span>

## <a name="update-and-index-subscription-sales-prices"></a><span data-ttu-id="fc971-152">Atualizar e indexar preços de venda da subscrição</span><span class="sxs-lookup"><span data-stu-id="fc971-152">Update and index subscription sales prices</span></span>

<span data-ttu-id="fc971-153">Você pode atualizar o preço de venda da subscrição atualizando o preço base ou o índice.</span><span class="sxs-lookup"><span data-stu-id="fc971-153">You can update the subscription sales price by updating the base price or the index.</span></span> <span data-ttu-id="fc971-154">É possível atualizar por uma porcentagem ou para um novo valor.</span><span class="sxs-lookup"><span data-stu-id="fc971-154">You can update by a percentage or to a new value.</span></span>

## <a name="subscription-fee-sales-prices"></a><span data-ttu-id="fc971-155">Preços de venda da taxa de subscrição</span><span class="sxs-lookup"><span data-stu-id="fc971-155">Subscription fee sales prices</span></span>

<span data-ttu-id="fc971-156">Quando você cria uma taxa de subscrição, o preço de venda se baseia na configuração do preço de venda da subscrição.</span><span class="sxs-lookup"><span data-stu-id="fc971-156">When you create a subscription fee, the sales price is based on the sales price setup of the subscription.</span></span> <span data-ttu-id="fc971-157">Você pode usar o preço base da configuração do preço da subscrição ou criar preços de venda indexados.</span><span class="sxs-lookup"><span data-stu-id="fc971-157">You can either use the base price from the subscription price setup or create indexed sales prices.</span></span>

## <a name="example"></a><span data-ttu-id="fc971-158">exemplo</span><span class="sxs-lookup"><span data-stu-id="fc971-158">Example</span></span>

<span data-ttu-id="fc971-159">Você deseja configurar preços de venda da subscrição de EUR 500 para um novo projeto 9030.</span><span class="sxs-lookup"><span data-stu-id="fc971-159">You want to set up subscription sales prices of EUR 500 for a new project 9030.</span></span> <span data-ttu-id="fc971-160">No formulário **Preço de venda (subscrição)**, crie uma linha de preço de venda de subscrição como indicado na tabela.</span><span class="sxs-lookup"><span data-stu-id="fc971-160">In the **Sales price (subscription)** form, you create a subscription sales price line as indicated in the following table.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fc971-161">Válido de</span><span class="sxs-lookup"><span data-stu-id="fc971-161">Valid from</span></span></p></th>
<th><p><span data-ttu-id="fc971-162">Categoria</span><span class="sxs-lookup"><span data-stu-id="fc971-162">Category</span></span></p></th>
<th><p><span data-ttu-id="fc971-163">Projeto</span><span class="sxs-lookup"><span data-stu-id="fc971-163">Project</span></span></p></th>
<th><p><span data-ttu-id="fc971-164">Subscrição</span><span class="sxs-lookup"><span data-stu-id="fc971-164">Subscription</span></span></p></th>
<th><p><span data-ttu-id="fc971-165">Código de período</span><span class="sxs-lookup"><span data-stu-id="fc971-165">Period code</span></span></p></th>
<th><p><span data-ttu-id="fc971-166">Moeda de venda</span><span class="sxs-lookup"><span data-stu-id="fc971-166">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="fc971-167">Preço de venda</span><span class="sxs-lookup"><span data-stu-id="fc971-167">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc971-168">28/08/2006</span><span class="sxs-lookup"><span data-stu-id="fc971-168">28-08-2006</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fc971-169">9030</span><span class="sxs-lookup"><span data-stu-id="fc971-169">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fc971-170">Mês</span><span class="sxs-lookup"><span data-stu-id="fc971-170">Month</span></span></p></td>
<td><p><span data-ttu-id="fc971-171">EUR</span><span class="sxs-lookup"><span data-stu-id="fc971-171">EUR</span></span></p></td>
<td><p><span data-ttu-id="fc971-172">500</span><span class="sxs-lookup"><span data-stu-id="fc971-172">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fc971-173">Observe que os campos **Categoria** e **Subscrição** estão vazios.</span><span class="sxs-lookup"><span data-stu-id="fc971-173">Note that the **Category** and **Subscription** fields are empty.</span></span>

<span data-ttu-id="fc971-174">Então, você cria as seguintes subscrições.</span><span class="sxs-lookup"><span data-stu-id="fc971-174">You then create the following subscriptions.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fc971-175">Subscrição no serviço</span><span class="sxs-lookup"><span data-stu-id="fc971-175">Service subscription</span></span></p></th>
<th><p><span data-ttu-id="fc971-176">Projeto</span><span class="sxs-lookup"><span data-stu-id="fc971-176">Project</span></span></p></th>
<th><p><span data-ttu-id="fc971-177">Grupo de subscrições</span><span class="sxs-lookup"><span data-stu-id="fc971-177">Subscription group</span></span></p></th>
<th><p><span data-ttu-id="fc971-178">Categoria</span><span class="sxs-lookup"><span data-stu-id="fc971-178">Category</span></span></p></th>
<th><p><span data-ttu-id="fc971-179">Moeda</span><span class="sxs-lookup"><span data-stu-id="fc971-179">Currency</span></span></p></th>
<th><p><span data-ttu-id="fc971-180">Código de período</span><span class="sxs-lookup"><span data-stu-id="fc971-180">Period code</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc971-181">00020_135</span><span class="sxs-lookup"><span data-stu-id="fc971-181">00020_135</span></span></p></td>
<td><p><span data-ttu-id="fc971-182">9030</span><span class="sxs-lookup"><span data-stu-id="fc971-182">9030</span></span></p></td>
<td><p><span data-ttu-id="fc971-183">Sub1</span><span class="sxs-lookup"><span data-stu-id="fc971-183">Sub1</span></span></p></td>
<td><p><span data-ttu-id="fc971-184">SubCat1</span><span class="sxs-lookup"><span data-stu-id="fc971-184">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="fc971-185">EUR</span><span class="sxs-lookup"><span data-stu-id="fc971-185">EUR</span></span></p></td>
<td><p><span data-ttu-id="fc971-186">Mensalmente</span><span class="sxs-lookup"><span data-stu-id="fc971-186">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc971-187">00021_135</span><span class="sxs-lookup"><span data-stu-id="fc971-187">00021_135</span></span></p></td>
<td><p><span data-ttu-id="fc971-188">9030</span><span class="sxs-lookup"><span data-stu-id="fc971-188">9030</span></span></p></td>
<td><p><span data-ttu-id="fc971-189">Sub1</span><span class="sxs-lookup"><span data-stu-id="fc971-189">Sub1</span></span></p></td>
<td><p><span data-ttu-id="fc971-190">SubCat2</span><span class="sxs-lookup"><span data-stu-id="fc971-190">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="fc971-191">EUR</span><span class="sxs-lookup"><span data-stu-id="fc971-191">EUR</span></span></p></td>
<td><p><span data-ttu-id="fc971-192">Mensalmente</span><span class="sxs-lookup"><span data-stu-id="fc971-192">Monthly</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fc971-193">Agora, crie taxas de subscrição para as duas subscrições no grupo de subscrições Sub1:</span><span class="sxs-lookup"><span data-stu-id="fc971-193">Now you create subscription fees for both subscriptions in the subscription group Sub1:</span></span>

1.  <span data-ttu-id="fc971-194">Clique em **Gerenciamento de serviço** \> **Configuração** \> **Subscrições de serviço** \> **Grupos de subscrições**.</span><span class="sxs-lookup"><span data-stu-id="fc971-194">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups**.</span></span>

2.  <span data-ttu-id="fc971-195">No formulário **Grupos de subscrição**, clique em **Funções** \> **Criar taxa de subscrição**.</span><span class="sxs-lookup"><span data-stu-id="fc971-195">In the **Subscription groups** form, click **Function** \> **Create subscription fee**.</span></span>

3.  <span data-ttu-id="fc971-196">No formulário **Criar taxa de subscrição**, insira as informações apropriadas.</span><span class="sxs-lookup"><span data-stu-id="fc971-196">In the **Create subscription fee** form, enter the appropriate information.</span></span> <span data-ttu-id="fc971-197">Para obter mais informações, consulte [Criar transações de taxa de subscrição](create-subscription-fee-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="fc971-197">For more information, see [Create subscription fee transactions](create-subscription-fee-transactions.md).</span></span>

<span data-ttu-id="fc971-198">Taxas de subscrição com um preço de venda de EUR 500 são criadas para as duas subscrições, como mostra a tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="fc971-198">Subscription fees that have a sales price of EUR 500 are created for both subscriptions, as shown in the following table.</span></span>

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
<th><p><span data-ttu-id="fc971-199">Data do projeto</span><span class="sxs-lookup"><span data-stu-id="fc971-199">Project date</span></span></p></th>
<th><p><span data-ttu-id="fc971-200">Subscrição no serviço</span><span class="sxs-lookup"><span data-stu-id="fc971-200">Service subscription</span></span></p></th>
<th><p><span data-ttu-id="fc971-201">Projeto</span><span class="sxs-lookup"><span data-stu-id="fc971-201">Project</span></span></p></th>
<th><p><span data-ttu-id="fc971-202">Categoria</span><span class="sxs-lookup"><span data-stu-id="fc971-202">Category</span></span></p></th>
<th><p><span data-ttu-id="fc971-203">Data inicial</span><span class="sxs-lookup"><span data-stu-id="fc971-203">Start date</span></span></p></th>
<th><p><span data-ttu-id="fc971-204">Data final</span><span class="sxs-lookup"><span data-stu-id="fc971-204">End date</span></span></p></th>
<th><p><span data-ttu-id="fc971-205">Moeda de venda</span><span class="sxs-lookup"><span data-stu-id="fc971-205">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="fc971-206">Preço de venda</span><span class="sxs-lookup"><span data-stu-id="fc971-206">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc971-207">28/08/2006</span><span class="sxs-lookup"><span data-stu-id="fc971-207">28-08-2006</span></span></p></td>
<td><p><span data-ttu-id="fc971-208">00020_135</span><span class="sxs-lookup"><span data-stu-id="fc971-208">00020_135</span></span></p></td>
<td><p><span data-ttu-id="fc971-209">9030</span><span class="sxs-lookup"><span data-stu-id="fc971-209">9030</span></span></p></td>
<td><p><span data-ttu-id="fc971-210">SubCat1</span><span class="sxs-lookup"><span data-stu-id="fc971-210">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="fc971-211">01/01/2007</span><span class="sxs-lookup"><span data-stu-id="fc971-211">01-01-2007</span></span></p></td>
<td><p><span data-ttu-id="fc971-212">31/03/2007</span><span class="sxs-lookup"><span data-stu-id="fc971-212">31-03-2007</span></span></p></td>
<td><p><span data-ttu-id="fc971-213">EUR</span><span class="sxs-lookup"><span data-stu-id="fc971-213">EUR</span></span></p></td>
<td><p><span data-ttu-id="fc971-214">500</span><span class="sxs-lookup"><span data-stu-id="fc971-214">500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc971-215">28/08/2006</span><span class="sxs-lookup"><span data-stu-id="fc971-215">28-08-2006</span></span></p></td>
<td><p><span data-ttu-id="fc971-216">00021_135</span><span class="sxs-lookup"><span data-stu-id="fc971-216">00021_135</span></span></p></td>
<td><p><span data-ttu-id="fc971-217">9030</span><span class="sxs-lookup"><span data-stu-id="fc971-217">9030</span></span></p></td>
<td><p><span data-ttu-id="fc971-218">SubCat2</span><span class="sxs-lookup"><span data-stu-id="fc971-218">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="fc971-219">01/01/2007</span><span class="sxs-lookup"><span data-stu-id="fc971-219">01-01-2007</span></span></p></td>
<td><p><span data-ttu-id="fc971-220">31/03/2007</span><span class="sxs-lookup"><span data-stu-id="fc971-220">31-03-2007</span></span></p></td>
<td><p><span data-ttu-id="fc971-221">EUR</span><span class="sxs-lookup"><span data-stu-id="fc971-221">EUR</span></span></p></td>
<td><p><span data-ttu-id="fc971-222">500</span><span class="sxs-lookup"><span data-stu-id="fc971-222">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fc971-223">Posteriormente, você decide que deseja especificar preços de venda para a categoria SubCat1 para o projeto 9030.</span><span class="sxs-lookup"><span data-stu-id="fc971-223">Later, you decide that you want to specify sales prices for the category SubCat1 for project 9030.</span></span> <span data-ttu-id="fc971-224">Assim, cria uma nova linha de preço de venda com um preço de venda de EUR 550 para a combinação do projeto 9030 e a categoria de taxa SubCat1.</span><span class="sxs-lookup"><span data-stu-id="fc971-224">Therefore, you create a new sales price line that has a sales price of EUR 550 for the combination of project 9030 and fee category SubCat1.</span></span> <span data-ttu-id="fc971-225">Há agora duas linhas de preço de venda de subscrição para o projeto 9030, conforme mostrado na tabela.</span><span class="sxs-lookup"><span data-stu-id="fc971-225">There are now two subscription sales price lines for project 9030, as shown in the following table.</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fc971-226">Válido de</span><span class="sxs-lookup"><span data-stu-id="fc971-226">Valid from</span></span></p></th>
<th><p><span data-ttu-id="fc971-227">Categoria</span><span class="sxs-lookup"><span data-stu-id="fc971-227">Category</span></span></p></th>
<th><p><span data-ttu-id="fc971-228">Projeto</span><span class="sxs-lookup"><span data-stu-id="fc971-228">Project</span></span></p></th>
<th><p><span data-ttu-id="fc971-229">Subscrição</span><span class="sxs-lookup"><span data-stu-id="fc971-229">Subscription</span></span></p></th>
<th><p><span data-ttu-id="fc971-230">Código de período</span><span class="sxs-lookup"><span data-stu-id="fc971-230">Period code</span></span></p></th>
<th><p><span data-ttu-id="fc971-231">Moeda</span><span class="sxs-lookup"><span data-stu-id="fc971-231">Currency</span></span></p></th>
<th><p><span data-ttu-id="fc971-232">Preço de venda</span><span class="sxs-lookup"><span data-stu-id="fc971-232">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc971-233">28/08/2007</span><span class="sxs-lookup"><span data-stu-id="fc971-233">28-08-2007</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fc971-234">9030</span><span class="sxs-lookup"><span data-stu-id="fc971-234">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fc971-235">Mês</span><span class="sxs-lookup"><span data-stu-id="fc971-235">Month</span></span></p></td>
<td><p><span data-ttu-id="fc971-236">EUR</span><span class="sxs-lookup"><span data-stu-id="fc971-236">EUR</span></span></p></td>
<td><p><span data-ttu-id="fc971-237">500</span><span class="sxs-lookup"><span data-stu-id="fc971-237">500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc971-238">28/08/2007</span><span class="sxs-lookup"><span data-stu-id="fc971-238">28-08-2007</span></span></p></td>
<td><p><span data-ttu-id="fc971-239">SubCat1</span><span class="sxs-lookup"><span data-stu-id="fc971-239">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="fc971-240">9030</span><span class="sxs-lookup"><span data-stu-id="fc971-240">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fc971-241">Mês</span><span class="sxs-lookup"><span data-stu-id="fc971-241">Month</span></span></p></td>
<td><p><span data-ttu-id="fc971-242">EUR</span><span class="sxs-lookup"><span data-stu-id="fc971-242">EUR</span></span></p></td>
<td><p><span data-ttu-id="fc971-243">550</span><span class="sxs-lookup"><span data-stu-id="fc971-243">550</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fc971-244">Repita o procedimento descrito acima para criar taxas de subscrição para as duas subscrições no grupo de subscrições Sub1.</span><span class="sxs-lookup"><span data-stu-id="fc971-244">You repeat the procedure described above to create subscription fees for both subscriptions in the subscription group Sub1.</span></span> <span data-ttu-id="fc971-245">A tabela a seguir mostra as transações criadas para cada subscrição associada ao grupo de subscrições.</span><span class="sxs-lookup"><span data-stu-id="fc971-245">The following table shows the transactions that are created for each subscription that is attached to the subscription group.</span></span>

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
<th><p><span data-ttu-id="fc971-246">Data do projeto</span><span class="sxs-lookup"><span data-stu-id="fc971-246">Project date</span></span></p></th>
<th><p><span data-ttu-id="fc971-247">Subscrição</span><span class="sxs-lookup"><span data-stu-id="fc971-247">Subscription</span></span></p></th>
<th><p><span data-ttu-id="fc971-248">Projeto</span><span class="sxs-lookup"><span data-stu-id="fc971-248">Project</span></span></p></th>
<th><p><span data-ttu-id="fc971-249">Categoria</span><span class="sxs-lookup"><span data-stu-id="fc971-249">Category</span></span></p></th>
<th><p><span data-ttu-id="fc971-250">Data inicial</span><span class="sxs-lookup"><span data-stu-id="fc971-250">Start date</span></span></p></th>
<th><p><span data-ttu-id="fc971-251">Data final</span><span class="sxs-lookup"><span data-stu-id="fc971-251">End date</span></span></p></th>
<th><p><span data-ttu-id="fc971-252">Moeda de venda</span><span class="sxs-lookup"><span data-stu-id="fc971-252">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="fc971-253">Preço de venda</span><span class="sxs-lookup"><span data-stu-id="fc971-253">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc971-254">28/07/2007</span><span class="sxs-lookup"><span data-stu-id="fc971-254">28-07-2007</span></span></p></td>
<td><p><span data-ttu-id="fc971-255">00020_135</span><span class="sxs-lookup"><span data-stu-id="fc971-255">00020_135</span></span></p></td>
<td><p><span data-ttu-id="fc971-256">9030</span><span class="sxs-lookup"><span data-stu-id="fc971-256">9030</span></span></p></td>
<td><p><span data-ttu-id="fc971-257">SubCat1</span><span class="sxs-lookup"><span data-stu-id="fc971-257">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="fc971-258">01/01/2008</span><span class="sxs-lookup"><span data-stu-id="fc971-258">01-01-2008</span></span></p></td>
<td><p><span data-ttu-id="fc971-259">31/03/2008</span><span class="sxs-lookup"><span data-stu-id="fc971-259">31-03-2008</span></span></p></td>
<td><p><span data-ttu-id="fc971-260">EUR</span><span class="sxs-lookup"><span data-stu-id="fc971-260">EUR</span></span></p></td>
<td><p><span data-ttu-id="fc971-261">550</span><span class="sxs-lookup"><span data-stu-id="fc971-261">550</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc971-262">28/07/2008</span><span class="sxs-lookup"><span data-stu-id="fc971-262">28-07-2008</span></span></p></td>
<td><p><span data-ttu-id="fc971-263">00021_135</span><span class="sxs-lookup"><span data-stu-id="fc971-263">00021_135</span></span></p></td>
<td><p><span data-ttu-id="fc971-264">9030</span><span class="sxs-lookup"><span data-stu-id="fc971-264">9030</span></span></p></td>
<td><p><span data-ttu-id="fc971-265">SubCat2</span><span class="sxs-lookup"><span data-stu-id="fc971-265">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="fc971-266">01/01/2008</span><span class="sxs-lookup"><span data-stu-id="fc971-266">01-01-2008</span></span></p></td>
<td><p><span data-ttu-id="fc971-267">31/03/2008</span><span class="sxs-lookup"><span data-stu-id="fc971-267">31-03-2008</span></span></p></td>
<td><p><span data-ttu-id="fc971-268">EUR</span><span class="sxs-lookup"><span data-stu-id="fc971-268">EUR</span></span></p></td>
<td><p><span data-ttu-id="fc971-269">500</span><span class="sxs-lookup"><span data-stu-id="fc971-269">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fc971-270">Na primeira transação da subscrição 00020\_135, o preço de venda de EUR 550 é derivado do preço de venda da subscrição configurado para a combinação do projeto e da categoria específicos.</span><span class="sxs-lookup"><span data-stu-id="fc971-270">In the first transaction for subscription 00020\_135, the sales price of EUR 550 derives from the subscription sales price that is set up for the combination of the specific project and category.</span></span> <span data-ttu-id="fc971-271">Na segunda transação da subscrição 00021\_135, o preço de venda de EUR 500 é usado como preço de venda da subscrição do projeto porque não há um preço configurado para a combinação do projeto 9030 e da categoria SubCat2.</span><span class="sxs-lookup"><span data-stu-id="fc971-271">In the second transaction for subscription 00021\_135, the sales price of EUR 500 is used as the project subscription sales price because there is no price set up for the combination of project 9030 and category SubCat2.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc971-272">Consulte também</span><span class="sxs-lookup"><span data-stu-id="fc971-272">See also</span></span>

[<span data-ttu-id="fc971-273">Atualizar e indexar preços de venda da subscrição</span><span class="sxs-lookup"><span data-stu-id="fc971-273">Update and index subscription sales prices</span></span>](update-and-index-subscription-sales-prices.md)

  


