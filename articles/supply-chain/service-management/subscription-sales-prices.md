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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d6c59c90d49a4dcf3df4672c5f40d52ed639760c
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206602"
---
# <a name="subscription-sales-prices"></a><span data-ttu-id="953ea-103">Preços de venda de subscrição</span><span class="sxs-lookup"><span data-stu-id="953ea-103">Subscription sales prices</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="953ea-104">Quando você cria uma subscrição, o preço de venda é derivado da configuração do preço de venda criada no formulário **Subscrição do preço de venda**.</span><span class="sxs-lookup"><span data-stu-id="953ea-104">When you create a subscription, the sales price is derived from the sales price setup that was created in the **Sales price (subscription)** form.</span></span>

<span data-ttu-id="953ea-105">No formulário **Subscrição do preço de venda**, você pode criar preços de venda para uma subscrição específica ou pode criar preços de venda com uma aplicação mais ampla.</span><span class="sxs-lookup"><span data-stu-id="953ea-105">In the **Sales price (subscription)** form, you can create sales prices for a specific subscription or you can create sales prices that apply more broadly.</span></span> <span data-ttu-id="953ea-106">Para que um preço de venda seja aplicado a uma subscrição, o código de período e a moeda da subscrição e do preço de venda devem ser idênticos.</span><span class="sxs-lookup"><span data-stu-id="953ea-106">For a sales price to be applied to a subscription, the period code and the currency of the subscription must be identical to the period code and the currency of the sales price.</span></span>

<span data-ttu-id="953ea-107">Se o código de período e a moeda forem idênticos para ambas a subscrição e o preço de venda, os preços de venda da subscrição serão selecionados com base nas prioridades listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="953ea-107">If the period code and currency are identical for the subscription and the sales price, subscription sales prices are selected on the basis of the priorities listed in the following table.</span></span> <span data-ttu-id="953ea-108">Uma célula em branco na tabela indica um campo vazio e um X indica um valor igual ao valor na subscrição da qual a transação é gerada.</span><span class="sxs-lookup"><span data-stu-id="953ea-108">A blank cell in the table indicates an empty field and an X indicates a value that is equal to the value in the subscription from which the transaction is generated.</span></span>

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
<th><p><span data-ttu-id="953ea-109">Prioridade</span><span class="sxs-lookup"><span data-stu-id="953ea-109">Priority</span></span></p></th>
<th><p><span data-ttu-id="953ea-110"><strong>Categoria</strong></span><span class="sxs-lookup"><span data-stu-id="953ea-110"><strong>Category</strong></span></span></p></th>
<th><p><span data-ttu-id="953ea-111"><strong>ID do projeto</strong></span><span class="sxs-lookup"><span data-stu-id="953ea-111"><strong>Project ID</strong></span></span></p></th>
<th><p><span data-ttu-id="953ea-112"><strong>Subscrição</strong></span><span class="sxs-lookup"><span data-stu-id="953ea-112"><strong>Subscription</strong></span></span></p></th>
<th><p><span data-ttu-id="953ea-113"><strong>Moeda de venda</strong></span><span class="sxs-lookup"><span data-stu-id="953ea-113"><strong>Sales currency</strong></span></span></p></th>
<th><p><span data-ttu-id="953ea-114"><strong>Código de período</strong></span><span class="sxs-lookup"><span data-stu-id="953ea-114"><strong>Period code</strong></span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="953ea-115">1</span><span class="sxs-lookup"><span data-stu-id="953ea-115">1</span></span></p></td>
<td><p><span data-ttu-id="953ea-116">X</span><span class="sxs-lookup"><span data-stu-id="953ea-116">X</span></span></p></td>
<td><p><span data-ttu-id="953ea-117">X</span><span class="sxs-lookup"><span data-stu-id="953ea-117">X</span></span></p></td>
<td><p><span data-ttu-id="953ea-118">X</span><span class="sxs-lookup"><span data-stu-id="953ea-118">X</span></span></p></td>
<td><p><span data-ttu-id="953ea-119">X</span><span class="sxs-lookup"><span data-stu-id="953ea-119">X</span></span></p></td>
<td><p><span data-ttu-id="953ea-120">X</span><span class="sxs-lookup"><span data-stu-id="953ea-120">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="953ea-121">2</span><span class="sxs-lookup"><span data-stu-id="953ea-121">2</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="953ea-122">X</span><span class="sxs-lookup"><span data-stu-id="953ea-122">X</span></span></p></td>
<td><p><span data-ttu-id="953ea-123">X</span><span class="sxs-lookup"><span data-stu-id="953ea-123">X</span></span></p></td>
<td><p><span data-ttu-id="953ea-124">X</span><span class="sxs-lookup"><span data-stu-id="953ea-124">X</span></span></p></td>
<td><p><span data-ttu-id="953ea-125">X</span><span class="sxs-lookup"><span data-stu-id="953ea-125">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="953ea-126">3</span><span class="sxs-lookup"><span data-stu-id="953ea-126">3</span></span></p></td>
<td><p><span data-ttu-id="953ea-127">X</span><span class="sxs-lookup"><span data-stu-id="953ea-127">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="953ea-128">X</span><span class="sxs-lookup"><span data-stu-id="953ea-128">X</span></span></p></td>
<td><p><span data-ttu-id="953ea-129">X</span><span class="sxs-lookup"><span data-stu-id="953ea-129">X</span></span></p></td>
<td><p><span data-ttu-id="953ea-130">X</span><span class="sxs-lookup"><span data-stu-id="953ea-130">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="953ea-131">4</span><span class="sxs-lookup"><span data-stu-id="953ea-131">4</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="953ea-132">X</span><span class="sxs-lookup"><span data-stu-id="953ea-132">X</span></span></p></td>
<td><p><span data-ttu-id="953ea-133">X</span><span class="sxs-lookup"><span data-stu-id="953ea-133">X</span></span></p></td>
<td><p><span data-ttu-id="953ea-134">X</span><span class="sxs-lookup"><span data-stu-id="953ea-134">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="953ea-135">5</span><span class="sxs-lookup"><span data-stu-id="953ea-135">5</span></span></p></td>
<td><p><span data-ttu-id="953ea-136">X</span><span class="sxs-lookup"><span data-stu-id="953ea-136">X</span></span></p></td>
<td><p><span data-ttu-id="953ea-137">X</span><span class="sxs-lookup"><span data-stu-id="953ea-137">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="953ea-138">X</span><span class="sxs-lookup"><span data-stu-id="953ea-138">X</span></span></p></td>
<td><p><span data-ttu-id="953ea-139">X</span><span class="sxs-lookup"><span data-stu-id="953ea-139">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="953ea-140">6</span><span class="sxs-lookup"><span data-stu-id="953ea-140">6</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="953ea-141">X</span><span class="sxs-lookup"><span data-stu-id="953ea-141">X</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="953ea-142">X</span><span class="sxs-lookup"><span data-stu-id="953ea-142">X</span></span></p></td>
<td><p><span data-ttu-id="953ea-143">X</span><span class="sxs-lookup"><span data-stu-id="953ea-143">X</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="953ea-144">7</span><span class="sxs-lookup"><span data-stu-id="953ea-144">7</span></span></p></td>
<td><p><span data-ttu-id="953ea-145">X</span><span class="sxs-lookup"><span data-stu-id="953ea-145">X</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="953ea-146">X</span><span class="sxs-lookup"><span data-stu-id="953ea-146">X</span></span></p></td>
<td><p><span data-ttu-id="953ea-147">X</span><span class="sxs-lookup"><span data-stu-id="953ea-147">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="953ea-148">8</span><span class="sxs-lookup"><span data-stu-id="953ea-148">8</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="953ea-149">X</span><span class="sxs-lookup"><span data-stu-id="953ea-149">X</span></span></p></td>
<td><p><span data-ttu-id="953ea-150">X</span><span class="sxs-lookup"><span data-stu-id="953ea-150">X</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="953ea-151">Quando uma taxa de subscrição é criada, o preço de venda com o maior nível de detalhe, como observado na tabela acima, é selecionado como o preço de venda da subscrição.</span><span class="sxs-lookup"><span data-stu-id="953ea-151">When a subscription fee is created, the sales price with the greatest level of detail, as noted in the table above, is selected as the subscription sales price.</span></span>

## <a name="update-and-index-subscription-sales-prices"></a><span data-ttu-id="953ea-152">Atualizar e indexar preços de venda da subscrição</span><span class="sxs-lookup"><span data-stu-id="953ea-152">Update and index subscription sales prices</span></span>

<span data-ttu-id="953ea-153">Você pode atualizar o preço de venda da subscrição atualizando o preço base ou o índice.</span><span class="sxs-lookup"><span data-stu-id="953ea-153">You can update the subscription sales price by updating the base price or the index.</span></span> <span data-ttu-id="953ea-154">É possível atualizar por uma porcentagem ou para um novo valor.</span><span class="sxs-lookup"><span data-stu-id="953ea-154">You can update by a percentage or to a new value.</span></span>

## <a name="subscription-fee-sales-prices"></a><span data-ttu-id="953ea-155">Preços de venda da taxa de subscrição</span><span class="sxs-lookup"><span data-stu-id="953ea-155">Subscription fee sales prices</span></span>

<span data-ttu-id="953ea-156">Quando você cria uma taxa de subscrição, o preço de venda se baseia na configuração do preço de venda da subscrição.</span><span class="sxs-lookup"><span data-stu-id="953ea-156">When you create a subscription fee, the sales price is based on the sales price setup of the subscription.</span></span> <span data-ttu-id="953ea-157">Você pode usar o preço base da configuração do preço da subscrição ou criar preços de venda indexados.</span><span class="sxs-lookup"><span data-stu-id="953ea-157">You can either use the base price from the subscription price setup or create indexed sales prices.</span></span>

## <a name="example"></a><span data-ttu-id="953ea-158">exemplo</span><span class="sxs-lookup"><span data-stu-id="953ea-158">Example</span></span>

<span data-ttu-id="953ea-159">Você deseja configurar preços de venda da subscrição de EUR 500 para um novo projeto 9030.</span><span class="sxs-lookup"><span data-stu-id="953ea-159">You want to set up subscription sales prices of EUR 500 for a new project 9030.</span></span> <span data-ttu-id="953ea-160">No formulário **Preço de venda (subscrição)**, crie uma linha de preço de venda de subscrição como indicado na tabela.</span><span class="sxs-lookup"><span data-stu-id="953ea-160">In the **Sales price (subscription)** form, you create a subscription sales price line as indicated in the following table.</span></span>

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
<th><p><span data-ttu-id="953ea-161">Válido de</span><span class="sxs-lookup"><span data-stu-id="953ea-161">Valid from</span></span></p></th>
<th><p><span data-ttu-id="953ea-162">Categoria</span><span class="sxs-lookup"><span data-stu-id="953ea-162">Category</span></span></p></th>
<th><p><span data-ttu-id="953ea-163">Projeto</span><span class="sxs-lookup"><span data-stu-id="953ea-163">Project</span></span></p></th>
<th><p><span data-ttu-id="953ea-164">Subscrição</span><span class="sxs-lookup"><span data-stu-id="953ea-164">Subscription</span></span></p></th>
<th><p><span data-ttu-id="953ea-165">Código de período</span><span class="sxs-lookup"><span data-stu-id="953ea-165">Period code</span></span></p></th>
<th><p><span data-ttu-id="953ea-166">Moeda de venda</span><span class="sxs-lookup"><span data-stu-id="953ea-166">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="953ea-167">Preço de venda</span><span class="sxs-lookup"><span data-stu-id="953ea-167">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="953ea-168">28/08/2006</span><span class="sxs-lookup"><span data-stu-id="953ea-168">28-08-2006</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="953ea-169">9030</span><span class="sxs-lookup"><span data-stu-id="953ea-169">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="953ea-170">Mês</span><span class="sxs-lookup"><span data-stu-id="953ea-170">Month</span></span></p></td>
<td><p><span data-ttu-id="953ea-171">EUR</span><span class="sxs-lookup"><span data-stu-id="953ea-171">EUR</span></span></p></td>
<td><p><span data-ttu-id="953ea-172">500</span><span class="sxs-lookup"><span data-stu-id="953ea-172">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="953ea-173">Observe que os campos **Categoria** e **Subscrição** estão vazios.</span><span class="sxs-lookup"><span data-stu-id="953ea-173">Note that the **Category** and **Subscription** fields are empty.</span></span>

<span data-ttu-id="953ea-174">Então, você cria as seguintes subscrições.</span><span class="sxs-lookup"><span data-stu-id="953ea-174">You then create the following subscriptions.</span></span>

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
<th><p><span data-ttu-id="953ea-175">Subscrição no serviço</span><span class="sxs-lookup"><span data-stu-id="953ea-175">Service subscription</span></span></p></th>
<th><p><span data-ttu-id="953ea-176">Projeto</span><span class="sxs-lookup"><span data-stu-id="953ea-176">Project</span></span></p></th>
<th><p><span data-ttu-id="953ea-177">Grupo de subscrições</span><span class="sxs-lookup"><span data-stu-id="953ea-177">Subscription group</span></span></p></th>
<th><p><span data-ttu-id="953ea-178">Categoria</span><span class="sxs-lookup"><span data-stu-id="953ea-178">Category</span></span></p></th>
<th><p><span data-ttu-id="953ea-179">Moeda</span><span class="sxs-lookup"><span data-stu-id="953ea-179">Currency</span></span></p></th>
<th><p><span data-ttu-id="953ea-180">Código de período</span><span class="sxs-lookup"><span data-stu-id="953ea-180">Period code</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="953ea-181">00020_135</span><span class="sxs-lookup"><span data-stu-id="953ea-181">00020_135</span></span></p></td>
<td><p><span data-ttu-id="953ea-182">9030</span><span class="sxs-lookup"><span data-stu-id="953ea-182">9030</span></span></p></td>
<td><p><span data-ttu-id="953ea-183">Sub1</span><span class="sxs-lookup"><span data-stu-id="953ea-183">Sub1</span></span></p></td>
<td><p><span data-ttu-id="953ea-184">SubCat1</span><span class="sxs-lookup"><span data-stu-id="953ea-184">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="953ea-185">EUR</span><span class="sxs-lookup"><span data-stu-id="953ea-185">EUR</span></span></p></td>
<td><p><span data-ttu-id="953ea-186">Mensalmente</span><span class="sxs-lookup"><span data-stu-id="953ea-186">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="953ea-187">00021_135</span><span class="sxs-lookup"><span data-stu-id="953ea-187">00021_135</span></span></p></td>
<td><p><span data-ttu-id="953ea-188">9030</span><span class="sxs-lookup"><span data-stu-id="953ea-188">9030</span></span></p></td>
<td><p><span data-ttu-id="953ea-189">Sub1</span><span class="sxs-lookup"><span data-stu-id="953ea-189">Sub1</span></span></p></td>
<td><p><span data-ttu-id="953ea-190">SubCat2</span><span class="sxs-lookup"><span data-stu-id="953ea-190">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="953ea-191">EUR</span><span class="sxs-lookup"><span data-stu-id="953ea-191">EUR</span></span></p></td>
<td><p><span data-ttu-id="953ea-192">Mensalmente</span><span class="sxs-lookup"><span data-stu-id="953ea-192">Monthly</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="953ea-193">Agora, crie taxas de subscrição para as duas subscrições no grupo de subscrições Sub1:</span><span class="sxs-lookup"><span data-stu-id="953ea-193">Now you create subscription fees for both subscriptions in the subscription group Sub1:</span></span>

1.  <span data-ttu-id="953ea-194">Clique em **Gerenciamento de serviço** \> **Configuração** \> **Subscrições de serviço** \> **Grupos de subscrições**.</span><span class="sxs-lookup"><span data-stu-id="953ea-194">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups**.</span></span>

2.  <span data-ttu-id="953ea-195">No formulário **Grupos de subscrição**, clique em **Funções** \> **Criar taxa de subscrição**.</span><span class="sxs-lookup"><span data-stu-id="953ea-195">In the **Subscription groups** form, click **Function** \> **Create subscription fee**.</span></span>

3.  <span data-ttu-id="953ea-196">No formulário **Criar taxa de subscrição**, insira as informações apropriadas.</span><span class="sxs-lookup"><span data-stu-id="953ea-196">In the **Create subscription fee** form, enter the appropriate information.</span></span> <span data-ttu-id="953ea-197">Para obter mais informações, consulte [Criar transações de taxa de subscrição](create-subscription-fee-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="953ea-197">For more information, see [Create subscription fee transactions](create-subscription-fee-transactions.md).</span></span>

<span data-ttu-id="953ea-198">Taxas de subscrição com um preço de venda de EUR 500 são criadas para as duas subscrições, como mostra a tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="953ea-198">Subscription fees that have a sales price of EUR 500 are created for both subscriptions, as shown in the following table.</span></span>

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
<th><p><span data-ttu-id="953ea-199">Data do projeto</span><span class="sxs-lookup"><span data-stu-id="953ea-199">Project date</span></span></p></th>
<th><p><span data-ttu-id="953ea-200">Subscrição no serviço</span><span class="sxs-lookup"><span data-stu-id="953ea-200">Service subscription</span></span></p></th>
<th><p><span data-ttu-id="953ea-201">Projeto</span><span class="sxs-lookup"><span data-stu-id="953ea-201">Project</span></span></p></th>
<th><p><span data-ttu-id="953ea-202">Categoria</span><span class="sxs-lookup"><span data-stu-id="953ea-202">Category</span></span></p></th>
<th><p><span data-ttu-id="953ea-203">Data inicial</span><span class="sxs-lookup"><span data-stu-id="953ea-203">Start date</span></span></p></th>
<th><p><span data-ttu-id="953ea-204">Data final</span><span class="sxs-lookup"><span data-stu-id="953ea-204">End date</span></span></p></th>
<th><p><span data-ttu-id="953ea-205">Moeda de venda</span><span class="sxs-lookup"><span data-stu-id="953ea-205">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="953ea-206">Preço de venda</span><span class="sxs-lookup"><span data-stu-id="953ea-206">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="953ea-207">28/08/2006</span><span class="sxs-lookup"><span data-stu-id="953ea-207">28-08-2006</span></span></p></td>
<td><p><span data-ttu-id="953ea-208">00020_135</span><span class="sxs-lookup"><span data-stu-id="953ea-208">00020_135</span></span></p></td>
<td><p><span data-ttu-id="953ea-209">9030</span><span class="sxs-lookup"><span data-stu-id="953ea-209">9030</span></span></p></td>
<td><p><span data-ttu-id="953ea-210">SubCat1</span><span class="sxs-lookup"><span data-stu-id="953ea-210">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="953ea-211">01/01/2007</span><span class="sxs-lookup"><span data-stu-id="953ea-211">01-01-2007</span></span></p></td>
<td><p><span data-ttu-id="953ea-212">31/03/2007</span><span class="sxs-lookup"><span data-stu-id="953ea-212">31-03-2007</span></span></p></td>
<td><p><span data-ttu-id="953ea-213">EUR</span><span class="sxs-lookup"><span data-stu-id="953ea-213">EUR</span></span></p></td>
<td><p><span data-ttu-id="953ea-214">500</span><span class="sxs-lookup"><span data-stu-id="953ea-214">500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="953ea-215">28/08/2006</span><span class="sxs-lookup"><span data-stu-id="953ea-215">28-08-2006</span></span></p></td>
<td><p><span data-ttu-id="953ea-216">00021_135</span><span class="sxs-lookup"><span data-stu-id="953ea-216">00021_135</span></span></p></td>
<td><p><span data-ttu-id="953ea-217">9030</span><span class="sxs-lookup"><span data-stu-id="953ea-217">9030</span></span></p></td>
<td><p><span data-ttu-id="953ea-218">SubCat2</span><span class="sxs-lookup"><span data-stu-id="953ea-218">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="953ea-219">01/01/2007</span><span class="sxs-lookup"><span data-stu-id="953ea-219">01-01-2007</span></span></p></td>
<td><p><span data-ttu-id="953ea-220">31/03/2007</span><span class="sxs-lookup"><span data-stu-id="953ea-220">31-03-2007</span></span></p></td>
<td><p><span data-ttu-id="953ea-221">EUR</span><span class="sxs-lookup"><span data-stu-id="953ea-221">EUR</span></span></p></td>
<td><p><span data-ttu-id="953ea-222">500</span><span class="sxs-lookup"><span data-stu-id="953ea-222">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="953ea-223">Posteriormente, você decide que deseja especificar preços de venda para a categoria SubCat1 para o projeto 9030.</span><span class="sxs-lookup"><span data-stu-id="953ea-223">Later, you decide that you want to specify sales prices for the category SubCat1 for project 9030.</span></span> <span data-ttu-id="953ea-224">Assim, cria uma nova linha de preço de venda com um preço de venda de EUR 550 para a combinação do projeto 9030 e a categoria de taxa SubCat1.</span><span class="sxs-lookup"><span data-stu-id="953ea-224">Therefore, you create a new sales price line that has a sales price of EUR 550 for the combination of project 9030 and fee category SubCat1.</span></span> <span data-ttu-id="953ea-225">Há agora duas linhas de preço de venda de subscrição para o projeto 9030, conforme mostrado na tabela.</span><span class="sxs-lookup"><span data-stu-id="953ea-225">There are now two subscription sales price lines for project 9030, as shown in the following table.</span></span>

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
<th><p><span data-ttu-id="953ea-226">Válido de</span><span class="sxs-lookup"><span data-stu-id="953ea-226">Valid from</span></span></p></th>
<th><p><span data-ttu-id="953ea-227">Categoria</span><span class="sxs-lookup"><span data-stu-id="953ea-227">Category</span></span></p></th>
<th><p><span data-ttu-id="953ea-228">Projeto</span><span class="sxs-lookup"><span data-stu-id="953ea-228">Project</span></span></p></th>
<th><p><span data-ttu-id="953ea-229">Subscrição</span><span class="sxs-lookup"><span data-stu-id="953ea-229">Subscription</span></span></p></th>
<th><p><span data-ttu-id="953ea-230">Código de período</span><span class="sxs-lookup"><span data-stu-id="953ea-230">Period code</span></span></p></th>
<th><p><span data-ttu-id="953ea-231">Moeda</span><span class="sxs-lookup"><span data-stu-id="953ea-231">Currency</span></span></p></th>
<th><p><span data-ttu-id="953ea-232">Preço de venda</span><span class="sxs-lookup"><span data-stu-id="953ea-232">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="953ea-233">28/08/2007</span><span class="sxs-lookup"><span data-stu-id="953ea-233">28-08-2007</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="953ea-234">9030</span><span class="sxs-lookup"><span data-stu-id="953ea-234">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="953ea-235">Mês</span><span class="sxs-lookup"><span data-stu-id="953ea-235">Month</span></span></p></td>
<td><p><span data-ttu-id="953ea-236">EUR</span><span class="sxs-lookup"><span data-stu-id="953ea-236">EUR</span></span></p></td>
<td><p><span data-ttu-id="953ea-237">500</span><span class="sxs-lookup"><span data-stu-id="953ea-237">500</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="953ea-238">28/08/2007</span><span class="sxs-lookup"><span data-stu-id="953ea-238">28-08-2007</span></span></p></td>
<td><p><span data-ttu-id="953ea-239">SubCat1</span><span class="sxs-lookup"><span data-stu-id="953ea-239">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="953ea-240">9030</span><span class="sxs-lookup"><span data-stu-id="953ea-240">9030</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="953ea-241">Mês</span><span class="sxs-lookup"><span data-stu-id="953ea-241">Month</span></span></p></td>
<td><p><span data-ttu-id="953ea-242">EUR</span><span class="sxs-lookup"><span data-stu-id="953ea-242">EUR</span></span></p></td>
<td><p><span data-ttu-id="953ea-243">550</span><span class="sxs-lookup"><span data-stu-id="953ea-243">550</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="953ea-244">Repita o procedimento descrito acima para criar taxas de subscrição para as duas subscrições no grupo de subscrições Sub1.</span><span class="sxs-lookup"><span data-stu-id="953ea-244">You repeat the procedure described above to create subscription fees for both subscriptions in the subscription group Sub1.</span></span> <span data-ttu-id="953ea-245">A tabela a seguir mostra as transações criadas para cada subscrição associada ao grupo de subscrições.</span><span class="sxs-lookup"><span data-stu-id="953ea-245">The following table shows the transactions that are created for each subscription that is attached to the subscription group.</span></span>

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
<th><p><span data-ttu-id="953ea-246">Data do projeto</span><span class="sxs-lookup"><span data-stu-id="953ea-246">Project date</span></span></p></th>
<th><p><span data-ttu-id="953ea-247">Subscrição</span><span class="sxs-lookup"><span data-stu-id="953ea-247">Subscription</span></span></p></th>
<th><p><span data-ttu-id="953ea-248">Projeto</span><span class="sxs-lookup"><span data-stu-id="953ea-248">Project</span></span></p></th>
<th><p><span data-ttu-id="953ea-249">Categoria</span><span class="sxs-lookup"><span data-stu-id="953ea-249">Category</span></span></p></th>
<th><p><span data-ttu-id="953ea-250">Data inicial</span><span class="sxs-lookup"><span data-stu-id="953ea-250">Start date</span></span></p></th>
<th><p><span data-ttu-id="953ea-251">Data final</span><span class="sxs-lookup"><span data-stu-id="953ea-251">End date</span></span></p></th>
<th><p><span data-ttu-id="953ea-252">Moeda de venda</span><span class="sxs-lookup"><span data-stu-id="953ea-252">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="953ea-253">Preço de venda</span><span class="sxs-lookup"><span data-stu-id="953ea-253">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="953ea-254">28/07/2007</span><span class="sxs-lookup"><span data-stu-id="953ea-254">28-07-2007</span></span></p></td>
<td><p><span data-ttu-id="953ea-255">00020_135</span><span class="sxs-lookup"><span data-stu-id="953ea-255">00020_135</span></span></p></td>
<td><p><span data-ttu-id="953ea-256">9030</span><span class="sxs-lookup"><span data-stu-id="953ea-256">9030</span></span></p></td>
<td><p><span data-ttu-id="953ea-257">SubCat1</span><span class="sxs-lookup"><span data-stu-id="953ea-257">SubCat1</span></span></p></td>
<td><p><span data-ttu-id="953ea-258">01/01/2008</span><span class="sxs-lookup"><span data-stu-id="953ea-258">01-01-2008</span></span></p></td>
<td><p><span data-ttu-id="953ea-259">31/03/2008</span><span class="sxs-lookup"><span data-stu-id="953ea-259">31-03-2008</span></span></p></td>
<td><p><span data-ttu-id="953ea-260">EUR</span><span class="sxs-lookup"><span data-stu-id="953ea-260">EUR</span></span></p></td>
<td><p><span data-ttu-id="953ea-261">550</span><span class="sxs-lookup"><span data-stu-id="953ea-261">550</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="953ea-262">28/07/2008</span><span class="sxs-lookup"><span data-stu-id="953ea-262">28-07-2008</span></span></p></td>
<td><p><span data-ttu-id="953ea-263">00021_135</span><span class="sxs-lookup"><span data-stu-id="953ea-263">00021_135</span></span></p></td>
<td><p><span data-ttu-id="953ea-264">9030</span><span class="sxs-lookup"><span data-stu-id="953ea-264">9030</span></span></p></td>
<td><p><span data-ttu-id="953ea-265">SubCat2</span><span class="sxs-lookup"><span data-stu-id="953ea-265">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="953ea-266">01/01/2008</span><span class="sxs-lookup"><span data-stu-id="953ea-266">01-01-2008</span></span></p></td>
<td><p><span data-ttu-id="953ea-267">31/03/2008</span><span class="sxs-lookup"><span data-stu-id="953ea-267">31-03-2008</span></span></p></td>
<td><p><span data-ttu-id="953ea-268">EUR</span><span class="sxs-lookup"><span data-stu-id="953ea-268">EUR</span></span></p></td>
<td><p><span data-ttu-id="953ea-269">500</span><span class="sxs-lookup"><span data-stu-id="953ea-269">500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="953ea-270">Na primeira transação da subscrição 00020\_135, o preço de venda de EUR 550 é derivado do preço de venda da subscrição configurado para a combinação do projeto e da categoria específicos.</span><span class="sxs-lookup"><span data-stu-id="953ea-270">In the first transaction for subscription 00020\_135, the sales price of EUR 550 derives from the subscription sales price that is set up for the combination of the specific project and category.</span></span> <span data-ttu-id="953ea-271">Na segunda transação da subscrição 00021\_135, o preço de venda de EUR 500 é usado como preço de venda da subscrição do projeto porque não há um preço configurado para a combinação do projeto 9030 e da categoria SubCat2.</span><span class="sxs-lookup"><span data-stu-id="953ea-271">In the second transaction for subscription 00021\_135, the sales price of EUR 500 is used as the project subscription sales price because there is no price set up for the combination of project 9030 and category SubCat2.</span></span>

## <a name="see-also"></a><span data-ttu-id="953ea-272">Consulte também</span><span class="sxs-lookup"><span data-stu-id="953ea-272">See also</span></span>

[<span data-ttu-id="953ea-273">Atualizar e indexar preços de venda da subscrição</span><span class="sxs-lookup"><span data-stu-id="953ea-273">Update and index subscription sales prices</span></span>](update-and-index-subscription-sales-prices.md)

  


