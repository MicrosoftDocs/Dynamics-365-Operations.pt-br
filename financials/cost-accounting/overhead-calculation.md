---
title: "Cálculo de custos indiretos"
description: "Este tópico descreve processos comuns para calcular e alocar os custos gerais indiretos."
author: AndersGirke
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: 9e13fc9fa7e51a1299ca8698f581de979b680a7b
ms.openlocfilehash: a8c867ba49b95af2816fe8294059307e974c0a81
ms.contentlocale: pt-br
ms.lasthandoff: 09/18/2017

---

# <a name="overhead-calculation"></a><span data-ttu-id="3102b-103">Cálculo de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="3102b-103">Overhead calculation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="3102b-104">Este tópico descreve processos comuns para calcular e alocar os custos gerais indiretos.</span><span class="sxs-lookup"><span data-stu-id="3102b-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="3102b-105">Definição de termo</span><span class="sxs-lookup"><span data-stu-id="3102b-105">Term definition</span></span>
---------------

<span data-ttu-id="3102b-106">Os custos gerais indiretos são aqueles que foram incorridos para realizar um negócio, mas não podem ser diretamente atribuídos a qualquer atividade comercial, produto ou serviço específico.</span><span class="sxs-lookup"><span data-stu-id="3102b-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="3102b-107">Os custos gerais indiretos fornecem suporte crítico para geração de atividades produtivas.</span><span class="sxs-lookup"><span data-stu-id="3102b-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="3102b-108">Eis alguns exemplos de custos gerais:</span><span class="sxs-lookup"><span data-stu-id="3102b-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="3102b-109">Aluguel</span><span class="sxs-lookup"><span data-stu-id="3102b-109">Rent</span></span>
-   <span data-ttu-id="3102b-110">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-110">Electricity</span></span>
-   <span data-ttu-id="3102b-111">Salários administrativos</span><span class="sxs-lookup"><span data-stu-id="3102b-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="3102b-112">Visão geral do cálculo de custos gerais indiretos</span><span class="sxs-lookup"><span data-stu-id="3102b-112">Overhead calculation overview</span></span>
<span data-ttu-id="3102b-113">O cálculo de custos gerais indiretos executa as políticas de contabilização de custos na ordem correta.</span><span class="sxs-lookup"><span data-stu-id="3102b-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="3102b-114">Você pode executar o cálculo de custos gerais indiretos várias vezes para o mesmo período fiscal, se as políticas de contabilidade de custo foram modificadas ou foram detectados erros específicos.</span><span class="sxs-lookup"><span data-stu-id="3102b-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="3102b-115">Cada execução do cálculo de custos gerais indiretos é armazenada e recebe um ID exclusivo de versão que permite comparar os cálculos em várias versões.</span><span class="sxs-lookup"><span data-stu-id="3102b-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="3102b-116">As entradas de custo que o cálculo de custos indiretos gera recebe uma data contábil.</span><span class="sxs-lookup"><span data-stu-id="3102b-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="3102b-117">Essa data contábil corresponde à data final do período fiscal que é usada no cálculo.</span><span class="sxs-lookup"><span data-stu-id="3102b-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="3102b-118">A ID exclusiva de versão consiste nos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="3102b-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="3102b-119">Tipo de versão</span><span class="sxs-lookup"><span data-stu-id="3102b-119">Version type</span></span>
-   <span data-ttu-id="3102b-120">Data e hora</span><span class="sxs-lookup"><span data-stu-id="3102b-120">Date and time</span></span>
-   <span data-ttu-id="3102b-121">Razão de contabilização de custos</span><span class="sxs-lookup"><span data-stu-id="3102b-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="3102b-122">Ano fiscal</span><span class="sxs-lookup"><span data-stu-id="3102b-122">Fiscal year</span></span>
-   <span data-ttu-id="3102b-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="3102b-123">Fiscal period</span></span>

<span data-ttu-id="3102b-124">O cálculo de custos gerais indiretos é executado independentemente da versão.</span><span class="sxs-lookup"><span data-stu-id="3102b-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="3102b-125">Portanto, você pode calcular a versão de orçamento antes da versão atual.</span><span class="sxs-lookup"><span data-stu-id="3102b-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="3102b-126">O cálculo de custos gerais indiretos consiste em quatro etapas, conforme mostrado na ilustração.</span><span class="sxs-lookup"><span data-stu-id="3102b-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="3102b-127">Em cada etapa, um cabeçalho de diário é criado com entradas de diário.</span><span class="sxs-lookup"><span data-stu-id="3102b-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="3102b-128">Esse cabeçalho de diário mantém dados de entrada para cada etapa de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3102b-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="3102b-129">As políticas e regras são aplicadas a cada linha do diário e as entradas de custo são geradas como saídas.</span><span class="sxs-lookup"><span data-stu-id="3102b-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="3102b-130">Portanto, você sempre terá rastreabilidade total.</span><span class="sxs-lookup"><span data-stu-id="3102b-130">Therefore, you always have full traceability.</span></span> 
<span data-ttu-id="3102b-131">[![Cálculo de custos gerais indiretos](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="3102b-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="3102b-132">Calcular e alocar os custos gerais indiretos de Eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="3102b-133">Na contabilidade financeira, alguns custos, como eletricidade, são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="3102b-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="3102b-134">Portanto, a visão administrativa detalhada não é fornecida para a contabilização de custo.</span><span class="sxs-lookup"><span data-stu-id="3102b-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="3102b-135">Na contabilização de custo, para fornecer a visão administrativa correta em todas as unidades organizacionais e níveis, os custos devem passar pelas unidades organizacionais.</span><span class="sxs-lookup"><span data-stu-id="3102b-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="3102b-136">Este fluxo deve ser baseado em qualquer um registro exato do consumo ou de uma previsão justa.</span><span class="sxs-lookup"><span data-stu-id="3102b-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="3102b-137">Na contabilidade, um custo de eletricidade pode ser lançado, conforme mostrado na tabela.</span><span class="sxs-lookup"><span data-stu-id="3102b-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3102b-138">Data contábil</span><span class="sxs-lookup"><span data-stu-id="3102b-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="3102b-139">Centro de custos</span><span class="sxs-lookup"><span data-stu-id="3102b-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="3102b-140">Conta principal</span><span class="sxs-lookup"><span data-stu-id="3102b-140">Main account</span></span></th>
<th><span data-ttu-id="3102b-141">Valor na moeda contábil</span><span class="sxs-lookup"><span data-stu-id="3102b-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-142">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="3102b-143">CC099</span><span class="sxs-lookup"><span data-stu-id="3102b-143">CC099</span></span></td>
<td><span data-ttu-id="3102b-144">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="3102b-144">Default cost center</span></span></td>
<td><span data-ttu-id="3102b-145">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-145">10001</span></span></td>
<td><span data-ttu-id="3102b-146">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-146">Electricity</span></span></td>
<td><span data-ttu-id="3102b-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="3102b-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="3102b-148">Etapa 1: Processar o cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="3102b-149">Por padrão, quando as entradas de custo previsto são importadas de dados de origem, elas recebem a classificação de comportamento de custo **Não classificado** na Contabilidade de custos.</span><span class="sxs-lookup"><span data-stu-id="3102b-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="3102b-150">Aplicando regras da política de comportamento de custo, é possível reclassificar entradas de custo como **Custo fixo** ou **Custo variável**.</span><span class="sxs-lookup"><span data-stu-id="3102b-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="3102b-151">Definir a regra de custo de comportamento</span><span class="sxs-lookup"><span data-stu-id="3102b-151">Define the cost behavior rule</span></span>

<span data-ttu-id="3102b-152">Em alguns casos, parte do custo é uma taxa fixa e o custos pendente é baseado no consumo.</span><span class="sxs-lookup"><span data-stu-id="3102b-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="3102b-153">Geralmente, as contas de eletricidade correspondem a esta definição.</span><span class="sxs-lookup"><span data-stu-id="3102b-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="3102b-154">Após você pagar uma taxa fixa específica, você paga por consumo, por hora de quilowatt (Kwh).</span><span class="sxs-lookup"><span data-stu-id="3102b-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="3102b-155">Por exemplo, se a taxa de custo fixa for 1.000.00, veja aqui como a regra de comportamento de custo é definida:</span><span class="sxs-lookup"><span data-stu-id="3102b-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="3102b-156">Valor fixo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="3102b-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="3102b-157">0 &lt;= 1.000,00 = Fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="3102b-158">1000.01 &lt; N = Variável</span><span class="sxs-lookup"><span data-stu-id="3102b-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="3102b-159">Diário</span><span class="sxs-lookup"><span data-stu-id="3102b-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3102b-160">Diário</span><span class="sxs-lookup"><span data-stu-id="3102b-160">Journal</span></span></th>
<th><span data-ttu-id="3102b-161">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="3102b-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="3102b-162">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="3102b-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="3102b-163">Versão</span><span class="sxs-lookup"><span data-stu-id="3102b-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-164">00001</span><span class="sxs-lookup"><span data-stu-id="3102b-164">00001</span></span></td>
<td><span data-ttu-id="3102b-165">Diário de cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="3102b-166">fiscal</span><span class="sxs-lookup"><span data-stu-id="3102b-166">Fiscal</span></span></td>
<td><span data-ttu-id="3102b-167">2017</span><span class="sxs-lookup"><span data-stu-id="3102b-167">2017</span></span></td>
<td><span data-ttu-id="3102b-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="3102b-168">Period 1</span></span></td>
<td><span data-ttu-id="3102b-169">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="3102b-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="3102b-170">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="3102b-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3102b-171">Data contábil</span><span class="sxs-lookup"><span data-stu-id="3102b-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="3102b-172">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="3102b-173">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-173">Cost element</span></span></th>
<th><span data-ttu-id="3102b-174">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-174">Cost behavior</span></span></th>
<th><span data-ttu-id="3102b-175">Valor</span><span class="sxs-lookup"><span data-stu-id="3102b-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-176">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="3102b-177">CC099</span><span class="sxs-lookup"><span data-stu-id="3102b-177">CC099</span></span></td>
<td><span data-ttu-id="3102b-178">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="3102b-178">Default cost center</span></span></td>
<td><span data-ttu-id="3102b-179">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-179">10001</span></span></td>
<td><span data-ttu-id="3102b-180">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-180">Electricity</span></span></td>
<td><span data-ttu-id="3102b-181">Não classificado</span><span class="sxs-lookup"><span data-stu-id="3102b-181">Unclassified</span></span></td>
<td><span data-ttu-id="3102b-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="3102b-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="3102b-183">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3102b-184">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="3102b-185">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-185">Cost element</span></span></th>
<th><span data-ttu-id="3102b-186">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-186">Cost behavior</span></span></th>
<th><span data-ttu-id="3102b-187">Valor</span><span class="sxs-lookup"><span data-stu-id="3102b-187">Amount</span></span></th>
<th><span data-ttu-id="3102b-188">Data contábil</span><span class="sxs-lookup"><span data-stu-id="3102b-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-189">CC099</span><span class="sxs-lookup"><span data-stu-id="3102b-189">CC099</span></span></td>
<td><span data-ttu-id="3102b-190">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="3102b-190">Default cost center</span></span></td>
<td><span data-ttu-id="3102b-191">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-191">10001</span></span></td>
<td><span data-ttu-id="3102b-192">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-192">Electricity</span></span></td>
<td><span data-ttu-id="3102b-193">Não classificado</span><span class="sxs-lookup"><span data-stu-id="3102b-193">Unclassified</span></span></td>
<td><span data-ttu-id="3102b-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="3102b-194">10,000.00</span></span></td>
<td><span data-ttu-id="3102b-195">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-196">CC099</span><span class="sxs-lookup"><span data-stu-id="3102b-196">CC099</span></span></td>
<td><span data-ttu-id="3102b-197">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="3102b-197">Default cost center</span></span></td>
<td><span data-ttu-id="3102b-198">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-198">10001</span></span></td>
<td><span data-ttu-id="3102b-199">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-199">Electricity</span></span></td>
<td><span data-ttu-id="3102b-200">Não classificado</span><span class="sxs-lookup"><span data-stu-id="3102b-200">Unclassified</span></span></td>
<td><span data-ttu-id="3102b-201">-10.000,00</span><span class="sxs-lookup"><span data-stu-id="3102b-201">-10,000.00</span></span></td>
<td><span data-ttu-id="3102b-202">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-203">CC099</span><span class="sxs-lookup"><span data-stu-id="3102b-203">CC099</span></span></td>
<td><span data-ttu-id="3102b-204">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="3102b-204">Default cost center</span></span></td>
<td><span data-ttu-id="3102b-205">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-205">10001</span></span></td>
<td><span data-ttu-id="3102b-206">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-206">Electricity</span></span></td>
<td><span data-ttu-id="3102b-207">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-207">Fixed cost</span></span></td>
<td><span data-ttu-id="3102b-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="3102b-208">1,000.00</span></span></td>
<td><span data-ttu-id="3102b-209">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-210">CC099</span><span class="sxs-lookup"><span data-stu-id="3102b-210">CC099</span></span></td>
<td><span data-ttu-id="3102b-211">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="3102b-211">Default cost center</span></span></td>
<td><span data-ttu-id="3102b-212">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-212">10001</span></span></td>
<td><span data-ttu-id="3102b-213">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-213">Electricity</span></span></td>
<td><span data-ttu-id="3102b-214">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-214">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="3102b-215">9,000.00</span></span></td>
<td><span data-ttu-id="3102b-216">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3102b-217">Para obter informações detalhadas sobre o comportamento de custo, consulte a política de comportamento de custo.</span><span class="sxs-lookup"><span data-stu-id="3102b-217">For detailed information about cost behavior, see Cost behavior policy.</span></span> <span data-ttu-id="3102b-218">(Observe que este tópico não está incluído, mas estará em breve).</span><span class="sxs-lookup"><span data-stu-id="3102b-218">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="3102b-219">Etapa 2: Processar o cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-219">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="3102b-220">A distribuição de custos é usada para redistribuir custo de um objeto de custo a um ou mais outros objetos de custo, aplicando uma base de alocação relevante.</span><span class="sxs-lookup"><span data-stu-id="3102b-220">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="3102b-221">A distribuição de custos e a alocação de custo são diferentes na distribuição de custos, sempre que ocorrer em nível de elemento de custo principal do custo original.</span><span class="sxs-lookup"><span data-stu-id="3102b-221">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="3102b-222">Definir a regra de distribuição de custos</span><span class="sxs-lookup"><span data-stu-id="3102b-222">Define the cost distribution rule</span></span>

<span data-ttu-id="3102b-223">Na contabilidade financeira, os custos de eletricidade geralmente são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="3102b-223">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="3102b-224">Na contabilização de custo, esta abordagem não é suficientemente detalhada.</span><span class="sxs-lookup"><span data-stu-id="3102b-224">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="3102b-225">O custo variável deve ser distribuído a objetos de custos individuais com base justa.</span><span class="sxs-lookup"><span data-stu-id="3102b-225">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="3102b-226">A base de alocação mais lógica é o consumo de eletricidade (Kwh).</span><span class="sxs-lookup"><span data-stu-id="3102b-226">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="3102b-227">O membro da dimensão estatística que é chamado Eletricidade é criado e o consumo de eletricidade é registrado.</span><span class="sxs-lookup"><span data-stu-id="3102b-227">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="3102b-228">Por padrão, todos os membros estatísticos da dimensão se tornam disponíveis como bases de alocação.</span><span class="sxs-lookup"><span data-stu-id="3102b-228">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3102b-229">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-229">Cost object</span></span></th>
<th><span data-ttu-id="3102b-230">Kwh</span><span class="sxs-lookup"><span data-stu-id="3102b-230">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-231">CC001</span><span class="sxs-lookup"><span data-stu-id="3102b-231">CC001</span></span></td>
<td><span data-ttu-id="3102b-232">RH</span><span class="sxs-lookup"><span data-stu-id="3102b-232">HR</span></span></td>
<td><span data-ttu-id="3102b-233">1.000</span><span class="sxs-lookup"><span data-stu-id="3102b-233">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-234">CC002</span><span class="sxs-lookup"><span data-stu-id="3102b-234">CC002</span></span></td>
<td><span data-ttu-id="3102b-235">Finanças</span><span class="sxs-lookup"><span data-stu-id="3102b-235">Finance</span></span></td>
<td><span data-ttu-id="3102b-236">6,000</span><span class="sxs-lookup"><span data-stu-id="3102b-236">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-237">CC003</span><span class="sxs-lookup"><span data-stu-id="3102b-237">CC003</span></span></td>
<td><span data-ttu-id="3102b-238">Montagem</span><span class="sxs-lookup"><span data-stu-id="3102b-238">Assembly</span></span></td>
<td><span data-ttu-id="3102b-239">0</span><span class="sxs-lookup"><span data-stu-id="3102b-239">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3102b-240">A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação para custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="3102b-240">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3102b-241">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-241">Cost object</span></span></th>
<th><span data-ttu-id="3102b-242">Magnitude</span><span class="sxs-lookup"><span data-stu-id="3102b-242">Magnitude</span></span></th>
<th><span data-ttu-id="3102b-243">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="3102b-243">Allocation factor</span></span></th>
<th><span data-ttu-id="3102b-244">Valor</span><span class="sxs-lookup"><span data-stu-id="3102b-244">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-245">CC001</span><span class="sxs-lookup"><span data-stu-id="3102b-245">CC001</span></span></td>
<td><span data-ttu-id="3102b-246">RH</span><span class="sxs-lookup"><span data-stu-id="3102b-246">HR</span></span></td>
<td><span data-ttu-id="3102b-247">1.000</span><span class="sxs-lookup"><span data-stu-id="3102b-247">1,000</span></span></td>
<td><span data-ttu-id="3102b-248">(1.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="3102b-248">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="3102b-249">1,285.71</span><span class="sxs-lookup"><span data-stu-id="3102b-249">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-250">CC002</span><span class="sxs-lookup"><span data-stu-id="3102b-250">CC002</span></span></td>
<td><span data-ttu-id="3102b-251">Finanças</span><span class="sxs-lookup"><span data-stu-id="3102b-251">Finance</span></span></td>
<td><span data-ttu-id="3102b-252">6,000</span><span class="sxs-lookup"><span data-stu-id="3102b-252">6,000</span></span></td>
<td><span data-ttu-id="3102b-253">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="3102b-253">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="3102b-254">7,714.29</span><span class="sxs-lookup"><span data-stu-id="3102b-254">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-255">CC003</span><span class="sxs-lookup"><span data-stu-id="3102b-255">CC003</span></span></td>
<td><span data-ttu-id="3102b-256">Montagem</span><span class="sxs-lookup"><span data-stu-id="3102b-256">Assembly</span></span></td>
<td><span data-ttu-id="3102b-257">0</span><span class="sxs-lookup"><span data-stu-id="3102b-257">0</span></span></td>
<td><span data-ttu-id="3102b-258">(0 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="3102b-258">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="3102b-259">0,00</span><span class="sxs-lookup"><span data-stu-id="3102b-259">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3102b-260">Os custos fixos devem ser distribuídos igualmente a objetos de custo individuais que têm a eletricidade consumida.</span><span class="sxs-lookup"><span data-stu-id="3102b-260">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="3102b-261">Você pode obter esse resultado usando o membro estatístico de dimensão de eletricidade em uma base e alocação da fórmula: (Eletricidade &gt; 0,00) A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação de custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="3102b-261">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3102b-262">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-262">Cost object</span></span></th>
<th><span data-ttu-id="3102b-263">Fórmula</span><span class="sxs-lookup"><span data-stu-id="3102b-263">Formula</span></span></th>
<th><span data-ttu-id="3102b-264">Magnitude</span><span class="sxs-lookup"><span data-stu-id="3102b-264">Magnitude</span></span></th>
<th><span data-ttu-id="3102b-265">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="3102b-265">Allocation factor</span></span></th>
<th><span data-ttu-id="3102b-266">Valor</span><span class="sxs-lookup"><span data-stu-id="3102b-266">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-267">CC001</span><span class="sxs-lookup"><span data-stu-id="3102b-267">CC001</span></span></td>
<td><span data-ttu-id="3102b-268">RH</span><span class="sxs-lookup"><span data-stu-id="3102b-268">HR</span></span></td>
<td><span data-ttu-id="3102b-269">(1.000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="3102b-269">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="3102b-270">1</span><span class="sxs-lookup"><span data-stu-id="3102b-270">1</span></span></td>
<td><span data-ttu-id="3102b-271">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="3102b-271">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="3102b-272">500,00</span><span class="sxs-lookup"><span data-stu-id="3102b-272">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-273">CC002</span><span class="sxs-lookup"><span data-stu-id="3102b-273">CC002</span></span></td>
<td><span data-ttu-id="3102b-274">Finanças</span><span class="sxs-lookup"><span data-stu-id="3102b-274">Finance</span></span></td>
<td><span data-ttu-id="3102b-275">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="3102b-275">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="3102b-276">1</span><span class="sxs-lookup"><span data-stu-id="3102b-276">1</span></span></td>
<td><span data-ttu-id="3102b-277">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="3102b-277">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="3102b-278">500,00</span><span class="sxs-lookup"><span data-stu-id="3102b-278">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-279">CC003</span><span class="sxs-lookup"><span data-stu-id="3102b-279">CC003</span></span></td>
<td><span data-ttu-id="3102b-280">Montagem</span><span class="sxs-lookup"><span data-stu-id="3102b-280">Assembly</span></span></td>
<td><span data-ttu-id="3102b-281">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="3102b-281">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="3102b-282">0</span><span class="sxs-lookup"><span data-stu-id="3102b-282">0</span></span></td>
<td><span data-ttu-id="3102b-283">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="3102b-283">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="3102b-284">0,00</span><span class="sxs-lookup"><span data-stu-id="3102b-284">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="3102b-285">Diário</span><span class="sxs-lookup"><span data-stu-id="3102b-285">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3102b-286">Diário</span><span class="sxs-lookup"><span data-stu-id="3102b-286">Journal</span></span></th>
<th><span data-ttu-id="3102b-287">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="3102b-287">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="3102b-288">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="3102b-288">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="3102b-289">Versão</span><span class="sxs-lookup"><span data-stu-id="3102b-289">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-290">00002</span><span class="sxs-lookup"><span data-stu-id="3102b-290">00002</span></span></td>
<td><span data-ttu-id="3102b-291">Diário de cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-291">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="3102b-292">fiscal</span><span class="sxs-lookup"><span data-stu-id="3102b-292">Fiscal</span></span></td>
<td><span data-ttu-id="3102b-293">2017</span><span class="sxs-lookup"><span data-stu-id="3102b-293">2017</span></span></td>
<td><span data-ttu-id="3102b-294">Período 1</span><span class="sxs-lookup"><span data-stu-id="3102b-294">Period 1</span></span></td>
<td><span data-ttu-id="3102b-295">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="3102b-295">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="3102b-296">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="3102b-296">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3102b-297">Data contábil</span><span class="sxs-lookup"><span data-stu-id="3102b-297">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="3102b-298">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-298">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="3102b-299">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-299">Cost element</span></span></th>
<th><span data-ttu-id="3102b-300">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-300">Cost behavior</span></span></th>
<th><span data-ttu-id="3102b-301">Valor</span><span class="sxs-lookup"><span data-stu-id="3102b-301">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-302">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-302">January 31, 2017</span></span></td>
<td><span data-ttu-id="3102b-303">CC099</span><span class="sxs-lookup"><span data-stu-id="3102b-303">CC099</span></span></td>
<td><span data-ttu-id="3102b-304">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="3102b-304">Default cost center</span></span></td>
<td><span data-ttu-id="3102b-305">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-305">10001</span></span></td>
<td><span data-ttu-id="3102b-306">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-306">Electricity</span></span></td>
<td><span data-ttu-id="3102b-307">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-307">Fixed cost</span></span></td>
<td><span data-ttu-id="3102b-308">1.000,00</span><span class="sxs-lookup"><span data-stu-id="3102b-308">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-309">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-309">January 31, 2017</span></span></td>
<td><span data-ttu-id="3102b-310">CC099</span><span class="sxs-lookup"><span data-stu-id="3102b-310">CC099</span></span></td>
<td><span data-ttu-id="3102b-311">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="3102b-311">Default cost center</span></span></td>
<td><span data-ttu-id="3102b-312">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-312">10001</span></span></td>
<td><span data-ttu-id="3102b-313">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-313">Electricity</span></span></td>
<td><span data-ttu-id="3102b-314">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-314">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-315">9,000.00</span><span class="sxs-lookup"><span data-stu-id="3102b-315">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="3102b-316">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-316">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3102b-317">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-317">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="3102b-318">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-318">Cost element</span></span></th>
<th><span data-ttu-id="3102b-319">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-319">Cost behavior</span></span></th>
<th><span data-ttu-id="3102b-320">Valor</span><span class="sxs-lookup"><span data-stu-id="3102b-320">Amount</span></span></th>
<th><span data-ttu-id="3102b-321">Data contábil</span><span class="sxs-lookup"><span data-stu-id="3102b-321">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-322">CC099</span><span class="sxs-lookup"><span data-stu-id="3102b-322">CC099</span></span></td>
<td><span data-ttu-id="3102b-323">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="3102b-323">Default cost center</span></span></td>
<td><span data-ttu-id="3102b-324">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-324">10001</span></span></td>
<td><span data-ttu-id="3102b-325">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-325">Electricity</span></span></td>
<td><span data-ttu-id="3102b-326">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-326">Fixed cost</span></span></td>
<td><span data-ttu-id="3102b-327">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="3102b-327">-1,000.00</span></span></td>
<td><span data-ttu-id="3102b-328">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-328">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-329">CC001</span><span class="sxs-lookup"><span data-stu-id="3102b-329">CC001</span></span></td>
<td><span data-ttu-id="3102b-330">RH</span><span class="sxs-lookup"><span data-stu-id="3102b-330">HR</span></span></td>
<td><span data-ttu-id="3102b-331">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-331">10001</span></span></td>
<td><span data-ttu-id="3102b-332">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-332">Electricity</span></span></td>
<td><span data-ttu-id="3102b-333">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-333">Fixed cost</span></span></td>
<td><span data-ttu-id="3102b-334">500,00</span><span class="sxs-lookup"><span data-stu-id="3102b-334">500.00</span></span></td>
<td><span data-ttu-id="3102b-335">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-335">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-336">CC002</span><span class="sxs-lookup"><span data-stu-id="3102b-336">CC002</span></span></td>
<td><span data-ttu-id="3102b-337">Finanças</span><span class="sxs-lookup"><span data-stu-id="3102b-337">Finance</span></span></td>
<td><span data-ttu-id="3102b-338">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-338">10001</span></span></td>
<td><span data-ttu-id="3102b-339">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-339">Electricity</span></span></td>
<td><span data-ttu-id="3102b-340">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-340">Fixed cost</span></span></td>
<td><span data-ttu-id="3102b-341">500,00</span><span class="sxs-lookup"><span data-stu-id="3102b-341">500.00</span></span></td>
<td><span data-ttu-id="3102b-342">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-342">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-343">CC099</span><span class="sxs-lookup"><span data-stu-id="3102b-343">CC099</span></span></td>
<td><span data-ttu-id="3102b-344">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="3102b-344">Default cost center</span></span></td>
<td><span data-ttu-id="3102b-345">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-345">10001</span></span></td>
<td><span data-ttu-id="3102b-346">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-346">Electricity</span></span></td>
<td><span data-ttu-id="3102b-347">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-347">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-348">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="3102b-348">-9,000.00</span></span></td>
<td><span data-ttu-id="3102b-349">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-349">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-350">CC001</span><span class="sxs-lookup"><span data-stu-id="3102b-350">CC001</span></span></td>
<td><span data-ttu-id="3102b-351">RH</span><span class="sxs-lookup"><span data-stu-id="3102b-351">HR</span></span></td>
<td><span data-ttu-id="3102b-352">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-352">10001</span></span></td>
<td><span data-ttu-id="3102b-353">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-353">Electricity</span></span></td>
<td><span data-ttu-id="3102b-354">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-354">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-355">1,285.71</span><span class="sxs-lookup"><span data-stu-id="3102b-355">1,285.71</span></span></td>
<td><span data-ttu-id="3102b-356">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-356">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-357">CC002</span><span class="sxs-lookup"><span data-stu-id="3102b-357">CC002</span></span></td>
<td><span data-ttu-id="3102b-358">Finanças</span><span class="sxs-lookup"><span data-stu-id="3102b-358">Finance</span></span></td>
<td><span data-ttu-id="3102b-359">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-359">10001</span></span></td>
<td><span data-ttu-id="3102b-360">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-360">Electricity</span></span></td>
<td><span data-ttu-id="3102b-361">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-361">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-362">7,714.29</span><span class="sxs-lookup"><span data-stu-id="3102b-362">7,714.29</span></span></td>
<td><span data-ttu-id="3102b-363">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-363">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3102b-364">Para obter informações detalhadas sobre bases de alocação e distribuição de custos, consulte a política de custo e as bases de alocação.</span><span class="sxs-lookup"><span data-stu-id="3102b-364">For detailed information about cost distribution and allocation bases, see Cost distribution policy and Allocation bases.</span></span> <span data-ttu-id="3102b-365">(Observe que este tópico não está incluído, mas estará em breve).</span><span class="sxs-lookup"><span data-stu-id="3102b-365">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="3102b-366">Etapa 3: Processar o cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="3102b-366">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="3102b-367">A taxa de custos indiretos é usada para cobrar um ou mais objetos de custos específicos.</span><span class="sxs-lookup"><span data-stu-id="3102b-367">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="3102b-368">O encargo se baseia em uma taxa de custo predeterminada e a magnitude da básica de alocação atribuída.</span><span class="sxs-lookup"><span data-stu-id="3102b-368">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="3102b-369">Defina a taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="3102b-369">Define the overhead rate</span></span>

<span data-ttu-id="3102b-370">O objeto de custo CC001 HR contribui para um conjunto de projetos internos.</span><span class="sxs-lookup"><span data-stu-id="3102b-370">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="3102b-371">Um membro de dimensão estatística que é chamado de projetos de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="3102b-371">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3102b-372">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-372">Cost object</span></span></th>
<th><span data-ttu-id="3102b-373">Horas</span><span class="sxs-lookup"><span data-stu-id="3102b-373">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-374">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="3102b-374">Proj 1</span></span></td>
<td><span data-ttu-id="3102b-375">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="3102b-375">Project 1</span></span></td>
<td><span data-ttu-id="3102b-376">3</span><span class="sxs-lookup"><span data-stu-id="3102b-376">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-377">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="3102b-377">Proj 2</span></span></td>
<td><span data-ttu-id="3102b-378">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="3102b-378">Project 2</span></span></td>
<td><span data-ttu-id="3102b-379">1</span><span class="sxs-lookup"><span data-stu-id="3102b-379">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3102b-380">Uma taxa de custo predeterminada da contribuição de projetos de custo foi definida.</span><span class="sxs-lookup"><span data-stu-id="3102b-380">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3102b-381">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-381">Cost object</span></span></th>
<th><span data-ttu-id="3102b-382">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-382">Cost element</span></span></th>
<th><span data-ttu-id="3102b-383">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-383">Cost behavior</span></span></th>
<th><span data-ttu-id="3102b-384">Unidades</span><span class="sxs-lookup"><span data-stu-id="3102b-384">Units</span></span></th>
<th><span data-ttu-id="3102b-385">Taxa</span><span class="sxs-lookup"><span data-stu-id="3102b-385">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-386">CC001</span><span class="sxs-lookup"><span data-stu-id="3102b-386">CC001</span></span></td>
<td><span data-ttu-id="3102b-387">RH</span><span class="sxs-lookup"><span data-stu-id="3102b-387">HR</span></span></td>
<td><span data-ttu-id="3102b-388">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-388">10001</span></span></td>
<td><span data-ttu-id="3102b-389">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-389">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-390">1</span><span class="sxs-lookup"><span data-stu-id="3102b-390">1</span></span></td>
<td><span data-ttu-id="3102b-391">10</span><span class="sxs-lookup"><span data-stu-id="3102b-391">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3102b-392">A tabela a seguir mostra o resultado quando projetos de RH são aplicados como base de alocação.</span><span class="sxs-lookup"><span data-stu-id="3102b-392">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3102b-393">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-393">Cost object</span></span></th>
<th><span data-ttu-id="3102b-394">Magnitude</span><span class="sxs-lookup"><span data-stu-id="3102b-394">Magnitude</span></span></th>
<th><span data-ttu-id="3102b-395">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-395">Cost element</span></span></th>
<th><span data-ttu-id="3102b-396">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="3102b-396">Allocation factor</span></span></th>
<th><span data-ttu-id="3102b-397">Valor</span><span class="sxs-lookup"><span data-stu-id="3102b-397">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-398">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="3102b-398">Proj 1</span></span></td>
<td><span data-ttu-id="3102b-399">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="3102b-399">Project 1</span></span></td>
<td><span data-ttu-id="3102b-400">3</span><span class="sxs-lookup"><span data-stu-id="3102b-400">3</span></span></td>
<td><span data-ttu-id="3102b-401">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-401">10001</span></span></td>
<td><span data-ttu-id="3102b-402">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="3102b-402">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="3102b-403">30,00</span><span class="sxs-lookup"><span data-stu-id="3102b-403">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-404">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="3102b-404">Proj 2</span></span></td>
<td><span data-ttu-id="3102b-405">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="3102b-405">Project 2</span></span></td>
<td><span data-ttu-id="3102b-406">1</span><span class="sxs-lookup"><span data-stu-id="3102b-406">1</span></span></td>
<td><span data-ttu-id="3102b-407">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-407">10001</span></span></td>
<td><span data-ttu-id="3102b-408">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="3102b-408">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="3102b-409">10,00</span><span class="sxs-lookup"><span data-stu-id="3102b-409">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="3102b-410">Diário</span><span class="sxs-lookup"><span data-stu-id="3102b-410">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3102b-411">Diário</span><span class="sxs-lookup"><span data-stu-id="3102b-411">Journal</span></span></th>
<th><span data-ttu-id="3102b-412">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="3102b-412">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="3102b-413">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="3102b-413">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="3102b-414">Versão</span><span class="sxs-lookup"><span data-stu-id="3102b-414">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-415">00003</span><span class="sxs-lookup"><span data-stu-id="3102b-415">00003</span></span></td>
<td><span data-ttu-id="3102b-416">Diário de cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="3102b-416">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="3102b-417">fiscal</span><span class="sxs-lookup"><span data-stu-id="3102b-417">Fiscal</span></span></td>
<td><span data-ttu-id="3102b-418">2017</span><span class="sxs-lookup"><span data-stu-id="3102b-418">2017</span></span></td>
<td><span data-ttu-id="3102b-419">Período 1</span><span class="sxs-lookup"><span data-stu-id="3102b-419">Period 1</span></span></td>
<td><span data-ttu-id="3102b-420">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="3102b-420">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="3102b-421">Entradas de diário (As entradas de diário para cálculo da taxa de custos indiretos)</span><span class="sxs-lookup"><span data-stu-id="3102b-421">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3102b-422">Data contábil</span><span class="sxs-lookup"><span data-stu-id="3102b-422">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="3102b-423">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-423">Cost object</span></span></th>
<th><span data-ttu-id="3102b-424">Magnitude</span><span class="sxs-lookup"><span data-stu-id="3102b-424">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-425">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-425">January 31, 2017</span></span></td>
<td><span data-ttu-id="3102b-426">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="3102b-426">Proj 1</span></span></td>
<td><span data-ttu-id="3102b-427">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="3102b-427">Internal Proj 1</span></span></td>
<td><span data-ttu-id="3102b-428">3,00</span><span class="sxs-lookup"><span data-stu-id="3102b-428">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-429">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-429">January 31, 2017</span></span></td>
<td><span data-ttu-id="3102b-430">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="3102b-430">Proj 2</span></span></td>
<td><span data-ttu-id="3102b-431">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="3102b-431">Internal Proj 2</span></span></td>
<td><span data-ttu-id="3102b-432">1.00</span><span class="sxs-lookup"><span data-stu-id="3102b-432">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="3102b-433">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-433">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3102b-434">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-434">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="3102b-435">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-435">Cost element</span></span></th>
<th><span data-ttu-id="3102b-436">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-436">Cost behavior</span></span></th>
<th><span data-ttu-id="3102b-437">Valor</span><span class="sxs-lookup"><span data-stu-id="3102b-437">Amount</span></span></th>
<th><span data-ttu-id="3102b-438">Data contábil</span><span class="sxs-lookup"><span data-stu-id="3102b-438">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-439">CC0001</span><span class="sxs-lookup"><span data-stu-id="3102b-439">CC0001</span></span></td>
<td><span data-ttu-id="3102b-440">RH</span><span class="sxs-lookup"><span data-stu-id="3102b-440">HR</span></span></td>
<td><span data-ttu-id="3102b-441">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-441">10001</span></span></td>
<td><span data-ttu-id="3102b-442">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-442">Electricity</span></span></td>
<td><span data-ttu-id="3102b-443">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-443">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-444">-30,00</span><span class="sxs-lookup"><span data-stu-id="3102b-444">-30.00</span></span></td>
<td><span data-ttu-id="3102b-445">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-445">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-446">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="3102b-446">Proj 1</span></span></td>
<td><span data-ttu-id="3102b-447">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="3102b-447">Internal Proj 1</span></span></td>
<td><span data-ttu-id="3102b-448">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-448">10001</span></span></td>
<td><span data-ttu-id="3102b-449">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-449">Electricity</span></span></td>
<td><span data-ttu-id="3102b-450">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-450">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-451">30,00</span><span class="sxs-lookup"><span data-stu-id="3102b-451">30.00</span></span></td>
<td><span data-ttu-id="3102b-452">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-452">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-453">CC001</span><span class="sxs-lookup"><span data-stu-id="3102b-453">CC001</span></span></td>
<td><span data-ttu-id="3102b-454">RH</span><span class="sxs-lookup"><span data-stu-id="3102b-454">HR</span></span></td>
<td><span data-ttu-id="3102b-455">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-455">10001</span></span></td>
<td><span data-ttu-id="3102b-456">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-456">Electricity</span></span></td>
<td><span data-ttu-id="3102b-457">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-457">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-458">-10,00</span><span class="sxs-lookup"><span data-stu-id="3102b-458">-10.00</span></span></td>
<td><span data-ttu-id="3102b-459">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-459">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-460">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="3102b-460">Proj 2</span></span></td>
<td><span data-ttu-id="3102b-461">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="3102b-461">Internal Proj 2</span></span></td>
<td><span data-ttu-id="3102b-462">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-462">10001</span></span></td>
<td><span data-ttu-id="3102b-463">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-463">Electricity</span></span></td>
<td><span data-ttu-id="3102b-464">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-464">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-465">10,00</span><span class="sxs-lookup"><span data-stu-id="3102b-465">10.00</span></span></td>
<td><span data-ttu-id="3102b-466">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-466">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3102b-467">Para obter informações detalhadas sobre a política de taxa de custos indiretos, consulte a política de taxa de custos indiretos e as bases de alocação.</span><span class="sxs-lookup"><span data-stu-id="3102b-467">For detailed information about overhead rate policy, see Overhead rate policy and Allocation bases.</span></span> <span data-ttu-id="3102b-468">(Observe que este tópico não está incluído, mas estará em breve).</span><span class="sxs-lookup"><span data-stu-id="3102b-468">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="3102b-469">Etapa 4: Processar o cálculo de alocação de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-469">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="3102b-470">A alocação é usada para alocar o saldo de um objeto de custo a outros objetos de custo pela aplicação de uma base de alocação.</span><span class="sxs-lookup"><span data-stu-id="3102b-470">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="3102b-471">O Finance and Operations oferece suporte ao método de alocação recíproco.</span><span class="sxs-lookup"><span data-stu-id="3102b-471">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="3102b-472">No método de alocação recíproco, os serviços mútuos que os objetos de custo auxiliar trocam são totalmente reconhecidos.</span><span class="sxs-lookup"><span data-stu-id="3102b-472">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="3102b-473">O sistema determina automaticamente a ordem correta realizar as alocações.</span><span class="sxs-lookup"><span data-stu-id="3102b-473">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="3102b-474">O saldo de um objeto de custo é alocado por uma base de alocação única.</span><span class="sxs-lookup"><span data-stu-id="3102b-474">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="3102b-475">As alocações entre as dimensões de objetos de custo e os respectivos membros são suportadas.</span><span class="sxs-lookup"><span data-stu-id="3102b-475">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="3102b-476">A ordem de alocação é controlada pela unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="3102b-476">The allocation order is controlled by the cost control unit.</span></span> <span data-ttu-id="3102b-477">[![Método recíproco](./media/reciprocal-method.png)]</span><span class="sxs-lookup"><span data-stu-id="3102b-477">[![Reciprocal method](./media/reciprocal-method.png)]</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="3102b-478">Defina a alocação de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-478">Define the cost allocation</span></span>

<span data-ttu-id="3102b-479">Aqui está um exemplo simples que explica como você pode rastrear o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="3102b-479">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="3102b-480">O objeto de custo previsto CC001 HR contribui a vários objetos de custo previsto.</span><span class="sxs-lookup"><span data-stu-id="3102b-480">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="3102b-481">Um membro de dimensão estatística que é chamado de serviços de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="3102b-481">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3102b-482">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-482">Cost object</span></span></th>
<th><span data-ttu-id="3102b-483">Serviços de RH</span><span class="sxs-lookup"><span data-stu-id="3102b-483">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-484">CC002</span><span class="sxs-lookup"><span data-stu-id="3102b-484">CC002</span></span></td>
<td><span data-ttu-id="3102b-485">Finanças</span><span class="sxs-lookup"><span data-stu-id="3102b-485">Finance</span></span></td>
<td><span data-ttu-id="3102b-486">35</span><span class="sxs-lookup"><span data-stu-id="3102b-486">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-487">CC003</span><span class="sxs-lookup"><span data-stu-id="3102b-487">CC003</span></span></td>
<td><span data-ttu-id="3102b-488">Montagem</span><span class="sxs-lookup"><span data-stu-id="3102b-488">Assembly</span></span></td>
<td><span data-ttu-id="3102b-489">55</span><span class="sxs-lookup"><span data-stu-id="3102b-489">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-490">CC004</span><span class="sxs-lookup"><span data-stu-id="3102b-490">CC004</span></span></td>
<td><span data-ttu-id="3102b-491">Embalagem</span><span class="sxs-lookup"><span data-stu-id="3102b-491">Packaging</span></span></td>
<td><span data-ttu-id="3102b-492">10</span><span class="sxs-lookup"><span data-stu-id="3102b-492">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3102b-493">O objeto de custo CC002 Finanças contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="3102b-493">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="3102b-494">Um membro de dimensão estatística que é chamado de serviços de Finanças foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="3102b-494">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3102b-495">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-495">Cost object</span></span></th>
<th><span data-ttu-id="3102b-496">Serviços financeiros</span><span class="sxs-lookup"><span data-stu-id="3102b-496">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-497">CC003</span><span class="sxs-lookup"><span data-stu-id="3102b-497">CC003</span></span></td>
<td><span data-ttu-id="3102b-498">Montagem</span><span class="sxs-lookup"><span data-stu-id="3102b-498">Assembly</span></span></td>
<td><span data-ttu-id="3102b-499">65</span><span class="sxs-lookup"><span data-stu-id="3102b-499">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-500">CC004</span><span class="sxs-lookup"><span data-stu-id="3102b-500">CC004</span></span></td>
<td><span data-ttu-id="3102b-501">Embalagem</span><span class="sxs-lookup"><span data-stu-id="3102b-501">Packaging</span></span></td>
<td><span data-ttu-id="3102b-502">35</span><span class="sxs-lookup"><span data-stu-id="3102b-502">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3102b-503">O objeto de custo CC003 Montagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="3102b-503">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="3102b-504">Um membro de dimensão estatística que é chamado de serviços de Montagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="3102b-504">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3102b-505">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-505">Cost object</span></span></th>
<th><span data-ttu-id="3102b-506">Serviços de montagem (horas)</span><span class="sxs-lookup"><span data-stu-id="3102b-506">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-507">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3102b-507">Prod 1</span></span></td>
<td><span data-ttu-id="3102b-508">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3102b-508">Product 1</span></span></td>
<td><span data-ttu-id="3102b-509">60</span><span class="sxs-lookup"><span data-stu-id="3102b-509">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-510">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3102b-510">Prod 2</span></span></td>
<td><span data-ttu-id="3102b-511">Produto 2</span><span class="sxs-lookup"><span data-stu-id="3102b-511">Product 2</span></span></td>
<td><span data-ttu-id="3102b-512">20</span><span class="sxs-lookup"><span data-stu-id="3102b-512">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3102b-513">O objeto de custo CC004 Embalagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="3102b-513">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="3102b-514">Um membro de dimensão estatística que é chamado de serviços de Embalagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="3102b-514">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3102b-515">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-515">Cost object</span></span></th>
<th><span data-ttu-id="3102b-516">Serviços de embalagem (horas)</span><span class="sxs-lookup"><span data-stu-id="3102b-516">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-517">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3102b-517">Prod 1</span></span></td>
<td><span data-ttu-id="3102b-518">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3102b-518">Product 1</span></span></td>
<td><span data-ttu-id="3102b-519">80</span><span class="sxs-lookup"><span data-stu-id="3102b-519">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-520">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3102b-520">Prod 2</span></span></td>
<td><span data-ttu-id="3102b-521">Produto 2</span><span class="sxs-lookup"><span data-stu-id="3102b-521">Product 2</span></span></td>
<td><span data-ttu-id="3102b-522">15</span><span class="sxs-lookup"><span data-stu-id="3102b-522">15</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3102b-523">**Observação:** No Finance and Operations, as medições estatísticas, como as horas de produção que um produto consome podem ser derivadas dos dados de origem.</span><span class="sxs-lookup"><span data-stu-id="3102b-523">**Note:** In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="3102b-524">Para obter informações mais detalhadas sobre provedores de medidas estatísticas, consulte o modelo do provedor de medida estatística.</span><span class="sxs-lookup"><span data-stu-id="3102b-524">For more detailed information about statistical measure providers, see Statistical measure provider template.</span></span> <span data-ttu-id="3102b-525">(Observe que este tópico não está concluído ainda, mas estará em breve.) A tabela a seguir mostra o resultado quando os serviços de RH são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="3102b-525">(Note that this topic isn't completed yet but is coming soon.) The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3102b-526">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-526">Cost object</span></span></th>
<th><span data-ttu-id="3102b-527">Magnitude</span><span class="sxs-lookup"><span data-stu-id="3102b-527">Magnitude</span></span></th>
<th><span data-ttu-id="3102b-528">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="3102b-528">Allocation factor</span></span></th>
<th><span data-ttu-id="3102b-529">Valor</span><span class="sxs-lookup"><span data-stu-id="3102b-529">Amount</span></span></th>
<th><span data-ttu-id="3102b-530">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-530">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-531">CC002</span><span class="sxs-lookup"><span data-stu-id="3102b-531">CC002</span></span></td>
<td><span data-ttu-id="3102b-532">Finanças</span><span class="sxs-lookup"><span data-stu-id="3102b-532">Finance</span></span></td>
<td><span data-ttu-id="3102b-533">35</span><span class="sxs-lookup"><span data-stu-id="3102b-533">35</span></span></td>
<td><span data-ttu-id="3102b-534">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="3102b-534">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="3102b-535">175.00</span><span class="sxs-lookup"><span data-stu-id="3102b-535">175.00</span></span></td>
<td><span data-ttu-id="3102b-536">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-536">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-537">CC003</span><span class="sxs-lookup"><span data-stu-id="3102b-537">CC003</span></span></td>
<td><span data-ttu-id="3102b-538">Montagem</span><span class="sxs-lookup"><span data-stu-id="3102b-538">Assembly</span></span></td>
<td><span data-ttu-id="3102b-539">55</span><span class="sxs-lookup"><span data-stu-id="3102b-539">55</span></span></td>
<td><span data-ttu-id="3102b-540">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="3102b-540">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="3102b-541">275.00</span><span class="sxs-lookup"><span data-stu-id="3102b-541">275.00</span></span></td>
<td><span data-ttu-id="3102b-542">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-542">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-543">CC004</span><span class="sxs-lookup"><span data-stu-id="3102b-543">CC004</span></span></td>
<td><span data-ttu-id="3102b-544">Embalagem</span><span class="sxs-lookup"><span data-stu-id="3102b-544">Packaging</span></span></td>
<td><span data-ttu-id="3102b-545">10</span><span class="sxs-lookup"><span data-stu-id="3102b-545">10</span></span></td>
<td><span data-ttu-id="3102b-546">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="3102b-546">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="3102b-547">50,00</span><span class="sxs-lookup"><span data-stu-id="3102b-547">50.00</span></span></td>
<td><span data-ttu-id="3102b-548">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-548">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-549">CC002</span><span class="sxs-lookup"><span data-stu-id="3102b-549">CC002</span></span></td>
<td><span data-ttu-id="3102b-550">Finanças</span><span class="sxs-lookup"><span data-stu-id="3102b-550">Finance</span></span></td>
<td><span data-ttu-id="3102b-551">35</span><span class="sxs-lookup"><span data-stu-id="3102b-551">35</span></span></td>
<td><span data-ttu-id="3102b-552">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="3102b-552">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="3102b-553">436.00</span><span class="sxs-lookup"><span data-stu-id="3102b-553">436.00</span></span></td>
<td><span data-ttu-id="3102b-554">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-554">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-555">CC003</span><span class="sxs-lookup"><span data-stu-id="3102b-555">CC003</span></span></td>
<td><span data-ttu-id="3102b-556">Montagem</span><span class="sxs-lookup"><span data-stu-id="3102b-556">Assembly</span></span></td>
<td><span data-ttu-id="3102b-557">55</span><span class="sxs-lookup"><span data-stu-id="3102b-557">55</span></span></td>
<td><span data-ttu-id="3102b-558">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="3102b-558">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="3102b-559">685.14</span><span class="sxs-lookup"><span data-stu-id="3102b-559">685.14</span></span></td>
<td><span data-ttu-id="3102b-560">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-560">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-561">CC004</span><span class="sxs-lookup"><span data-stu-id="3102b-561">CC004</span></span></td>
<td><span data-ttu-id="3102b-562">Embalagem</span><span class="sxs-lookup"><span data-stu-id="3102b-562">Packaging</span></span></td>
<td><span data-ttu-id="3102b-563">10</span><span class="sxs-lookup"><span data-stu-id="3102b-563">10</span></span></td>
<td><span data-ttu-id="3102b-564">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="3102b-564">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="3102b-565">124.57</span><span class="sxs-lookup"><span data-stu-id="3102b-565">124.57</span></span></td>
<td><span data-ttu-id="3102b-566">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-566">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3102b-567">A tabela a seguir mostra o resultado quando os serviços financeiros são aplicados como base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="3102b-567">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3102b-568">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-568">Cost object</span></span></th>
<th><span data-ttu-id="3102b-569">Magnitude</span><span class="sxs-lookup"><span data-stu-id="3102b-569">Magnitude</span></span></th>
<th><span data-ttu-id="3102b-570">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="3102b-570">Allocation factor</span></span></th>
<th><span data-ttu-id="3102b-571">Valor</span><span class="sxs-lookup"><span data-stu-id="3102b-571">Amount</span></span></th>
<th><span data-ttu-id="3102b-572">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-572">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-573">CC003</span><span class="sxs-lookup"><span data-stu-id="3102b-573">CC003</span></span></td>
<td><span data-ttu-id="3102b-574">Montagem</span><span class="sxs-lookup"><span data-stu-id="3102b-574">Assembly</span></span></td>
<td><span data-ttu-id="3102b-575">65</span><span class="sxs-lookup"><span data-stu-id="3102b-575">65</span></span></td>
<td><span data-ttu-id="3102b-576">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="3102b-576">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="3102b-577">438.75</span><span class="sxs-lookup"><span data-stu-id="3102b-577">438.75</span></span></td>
<td><span data-ttu-id="3102b-578">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-578">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-579">CC004</span><span class="sxs-lookup"><span data-stu-id="3102b-579">CC004</span></span></td>
<td><span data-ttu-id="3102b-580">Embalagem</span><span class="sxs-lookup"><span data-stu-id="3102b-580">Packaging</span></span></td>
<td><span data-ttu-id="3102b-581">35</span><span class="sxs-lookup"><span data-stu-id="3102b-581">35</span></span></td>
<td><span data-ttu-id="3102b-582">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="3102b-582">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="3102b-583">236.25</span><span class="sxs-lookup"><span data-stu-id="3102b-583">236.25</span></span></td>
<td><span data-ttu-id="3102b-584">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-584">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-585">CC003</span><span class="sxs-lookup"><span data-stu-id="3102b-585">CC003</span></span></td>
<td><span data-ttu-id="3102b-586">Montagem</span><span class="sxs-lookup"><span data-stu-id="3102b-586">Assembly</span></span></td>
<td><span data-ttu-id="3102b-587">65</span><span class="sxs-lookup"><span data-stu-id="3102b-587">65</span></span></td>
<td><span data-ttu-id="3102b-588">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="3102b-588">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="3102b-589">5,297.69</span><span class="sxs-lookup"><span data-stu-id="3102b-589">5,297.69</span></span></td>
<td><span data-ttu-id="3102b-590">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-590">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-591">CC004</span><span class="sxs-lookup"><span data-stu-id="3102b-591">CC004</span></span></td>
<td><span data-ttu-id="3102b-592">Embalagem</span><span class="sxs-lookup"><span data-stu-id="3102b-592">Packaging</span></span></td>
<td><span data-ttu-id="3102b-593">35</span><span class="sxs-lookup"><span data-stu-id="3102b-593">35</span></span></td>
<td><span data-ttu-id="3102b-594">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="3102b-594">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="3102b-595">2,852.60</span><span class="sxs-lookup"><span data-stu-id="3102b-595">2,852.60</span></span></td>
<td><span data-ttu-id="3102b-596">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-596">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3102b-597">A tabela a seguir mostra o resultado quando os serviços de Montagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="3102b-597">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3102b-598">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-598">Cost object</span></span></th>
<th><span data-ttu-id="3102b-599">Magnitude</span><span class="sxs-lookup"><span data-stu-id="3102b-599">Magnitude</span></span></th>
<th><span data-ttu-id="3102b-600">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="3102b-600">Allocation factor</span></span></th>
<th><span data-ttu-id="3102b-601">Valor</span><span class="sxs-lookup"><span data-stu-id="3102b-601">Amount</span></span></th>
<th><span data-ttu-id="3102b-602">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-602">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-603">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3102b-603">Prod 1</span></span></td>
<td><span data-ttu-id="3102b-604">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3102b-604">Product 1</span></span></td>
<td><span data-ttu-id="3102b-605">60</span><span class="sxs-lookup"><span data-stu-id="3102b-605">60</span></span></td>
<td><span data-ttu-id="3102b-606">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="3102b-606">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="3102b-607">535.31</span><span class="sxs-lookup"><span data-stu-id="3102b-607">535.31</span></span></td>
<td><span data-ttu-id="3102b-608">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-608">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-609">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3102b-609">Prod 2</span></span></td>
<td><span data-ttu-id="3102b-610">Produto 2</span><span class="sxs-lookup"><span data-stu-id="3102b-610">Product 2</span></span></td>
<td><span data-ttu-id="3102b-611">20</span><span class="sxs-lookup"><span data-stu-id="3102b-611">20</span></span></td>
<td><span data-ttu-id="3102b-612">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="3102b-612">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="3102b-613">178.44</span><span class="sxs-lookup"><span data-stu-id="3102b-613">178.44</span></span></td>
<td><span data-ttu-id="3102b-614">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-614">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-615">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3102b-615">Prod 1</span></span></td>
<td><span data-ttu-id="3102b-616">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3102b-616">Product 1</span></span></td>
<td><span data-ttu-id="3102b-617">60</span><span class="sxs-lookup"><span data-stu-id="3102b-617">60</span></span></td>
<td><span data-ttu-id="3102b-618">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="3102b-618">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="3102b-619">4,487.12</span><span class="sxs-lookup"><span data-stu-id="3102b-619">4,487.12</span></span></td>
<td><span data-ttu-id="3102b-620">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-620">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-621">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3102b-621">Prod 2</span></span></td>
<td><span data-ttu-id="3102b-622">Produto 2</span><span class="sxs-lookup"><span data-stu-id="3102b-622">Product 2</span></span></td>
<td><span data-ttu-id="3102b-623">20</span><span class="sxs-lookup"><span data-stu-id="3102b-623">20</span></span></td>
<td><span data-ttu-id="3102b-624">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="3102b-624">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="3102b-625">1,495.71</span><span class="sxs-lookup"><span data-stu-id="3102b-625">1,495.71</span></span></td>
<td><span data-ttu-id="3102b-626">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-626">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3102b-627">A tabela a seguir mostra o resultado quando os serviços de Embalagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="3102b-627">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3102b-628">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-628">Cost object</span></span></th>
<th><span data-ttu-id="3102b-629">Magnitude</span><span class="sxs-lookup"><span data-stu-id="3102b-629">Magnitude</span></span></th>
<th><span data-ttu-id="3102b-630">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="3102b-630">Allocation factor</span></span></th>
<th><span data-ttu-id="3102b-631">Valor</span><span class="sxs-lookup"><span data-stu-id="3102b-631">Amount</span></span></th>
<th><span data-ttu-id="3102b-632">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-632">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-633">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3102b-633">Prod 1</span></span></td>
<td><span data-ttu-id="3102b-634">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3102b-634">Product 1</span></span></td>
<td><span data-ttu-id="3102b-635">80</span><span class="sxs-lookup"><span data-stu-id="3102b-635">80</span></span></td>
<td><span data-ttu-id="3102b-636">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="3102b-636">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="3102b-637">241.05</span><span class="sxs-lookup"><span data-stu-id="3102b-637">241.05</span></span></td>
<td><span data-ttu-id="3102b-638">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-638">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-639">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3102b-639">Prod 2</span></span></td>
<td><span data-ttu-id="3102b-640">Produto 2</span><span class="sxs-lookup"><span data-stu-id="3102b-640">Product 2</span></span></td>
<td><span data-ttu-id="3102b-641">15</span><span class="sxs-lookup"><span data-stu-id="3102b-641">15</span></span></td>
<td><span data-ttu-id="3102b-642">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="3102b-642">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="3102b-643">45.20</span><span class="sxs-lookup"><span data-stu-id="3102b-643">45.20</span></span></td>
<td><span data-ttu-id="3102b-644">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-644">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-645">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3102b-645">Prod 1</span></span></td>
<td><span data-ttu-id="3102b-646">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3102b-646">Product 1</span></span></td>
<td><span data-ttu-id="3102b-647">80</span><span class="sxs-lookup"><span data-stu-id="3102b-647">80</span></span></td>
<td><span data-ttu-id="3102b-648">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="3102b-648">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="3102b-649">2,507.09</span><span class="sxs-lookup"><span data-stu-id="3102b-649">2,507.09</span></span></td>
<td><span data-ttu-id="3102b-650">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-650">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-651">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3102b-651">Prod 2</span></span></td>
<td><span data-ttu-id="3102b-652">Produto 2</span><span class="sxs-lookup"><span data-stu-id="3102b-652">Product 2</span></span></td>
<td><span data-ttu-id="3102b-653">15</span><span class="sxs-lookup"><span data-stu-id="3102b-653">15</span></span></td>
<td><span data-ttu-id="3102b-654">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="3102b-654">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="3102b-655">470.08</span><span class="sxs-lookup"><span data-stu-id="3102b-655">470.08</span></span></td>
<td><span data-ttu-id="3102b-656">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-656">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="3102b-657">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="3102b-657">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3102b-658">Diário</span><span class="sxs-lookup"><span data-stu-id="3102b-658">Journal</span></span></th>
<th><span data-ttu-id="3102b-659">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="3102b-659">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="3102b-660">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="3102b-660">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="3102b-661">Versão</span><span class="sxs-lookup"><span data-stu-id="3102b-661">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-662">00004</span><span class="sxs-lookup"><span data-stu-id="3102b-662">00004</span></span></td>
<td><span data-ttu-id="3102b-663">Diário de alocação de custos</span><span class="sxs-lookup"><span data-stu-id="3102b-663">Cost allocation journal</span></span></td>
<td><span data-ttu-id="3102b-664">fiscal</span><span class="sxs-lookup"><span data-stu-id="3102b-664">Fiscal</span></span></td>
<td><span data-ttu-id="3102b-665">2017</span><span class="sxs-lookup"><span data-stu-id="3102b-665">2017</span></span></td>
<td><span data-ttu-id="3102b-666">Período 1</span><span class="sxs-lookup"><span data-stu-id="3102b-666">Period 1</span></span></td>
<td><span data-ttu-id="3102b-667">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="3102b-667">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="3102b-668">Linhas do diário</span><span class="sxs-lookup"><span data-stu-id="3102b-668">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3102b-669">Data contábil</span><span class="sxs-lookup"><span data-stu-id="3102b-669">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="3102b-670">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-670">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="3102b-671">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-671">Cost element</span></span></th>
<th><span data-ttu-id="3102b-672">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-672">Cost behavior</span></span></th>
<th><span data-ttu-id="3102b-673">Valor</span><span class="sxs-lookup"><span data-stu-id="3102b-673">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-674">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-674">January 31, 2017</span></span></td>
<td><span data-ttu-id="3102b-675">CC001</span><span class="sxs-lookup"><span data-stu-id="3102b-675">CC001</span></span></td>
<td><span data-ttu-id="3102b-676">RH</span><span class="sxs-lookup"><span data-stu-id="3102b-676">HR</span></span></td>
<td><span data-ttu-id="3102b-677">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-677">10001</span></span></td>
<td><span data-ttu-id="3102b-678">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-678">Electricity</span></span></td>
<td><span data-ttu-id="3102b-679">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-679">Fixed cost</span></span></td>
<td><span data-ttu-id="3102b-680">500,00</span><span class="sxs-lookup"><span data-stu-id="3102b-680">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-681">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-681">January 31, 2017</span></span></td>
<td><span data-ttu-id="3102b-682">CC001</span><span class="sxs-lookup"><span data-stu-id="3102b-682">CC001</span></span></td>
<td><span data-ttu-id="3102b-683">RH</span><span class="sxs-lookup"><span data-stu-id="3102b-683">HR</span></span></td>
<td><span data-ttu-id="3102b-684">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-684">10001</span></span></td>
<td><span data-ttu-id="3102b-685">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-685">Electricity</span></span></td>
<td><span data-ttu-id="3102b-686">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-686">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-687">1,245.71</span><span class="sxs-lookup"><span data-stu-id="3102b-687">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-688">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-688">January 31, 2017</span></span></td>
<td><span data-ttu-id="3102b-689">CC002</span><span class="sxs-lookup"><span data-stu-id="3102b-689">CC002</span></span></td>
<td><span data-ttu-id="3102b-690">Finanças</span><span class="sxs-lookup"><span data-stu-id="3102b-690">Finance</span></span></td>
<td><span data-ttu-id="3102b-691">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-691">10001</span></span></td>
<td><span data-ttu-id="3102b-692">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-692">Electricity</span></span></td>
<td><span data-ttu-id="3102b-693">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-693">Fixed cost</span></span></td>
<td><span data-ttu-id="3102b-694">675.00</span><span class="sxs-lookup"><span data-stu-id="3102b-694">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-695">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-695">January 31, 2017</span></span></td>
<td><span data-ttu-id="3102b-696">CC002</span><span class="sxs-lookup"><span data-stu-id="3102b-696">CC002</span></span></td>
<td><span data-ttu-id="3102b-697">Finanças</span><span class="sxs-lookup"><span data-stu-id="3102b-697">Finance</span></span></td>
<td><span data-ttu-id="3102b-698">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-698">10001</span></span></td>
<td><span data-ttu-id="3102b-699">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-699">Electricity</span></span></td>
<td><span data-ttu-id="3102b-700">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-700">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-701">8,150.29</span><span class="sxs-lookup"><span data-stu-id="3102b-701">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-702">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-702">January 31, 2017</span></span></td>
<td><span data-ttu-id="3102b-703">CC003</span><span class="sxs-lookup"><span data-stu-id="3102b-703">CC003</span></span></td>
<td><span data-ttu-id="3102b-704">Montagem</span><span class="sxs-lookup"><span data-stu-id="3102b-704">Assembly</span></span></td>
<td><span data-ttu-id="3102b-705">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-705">10001</span></span></td>
<td><span data-ttu-id="3102b-706">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-706">Electricity</span></span></td>
<td><span data-ttu-id="3102b-707">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-707">Fixed cost</span></span></td>
<td><span data-ttu-id="3102b-708">713.75</span><span class="sxs-lookup"><span data-stu-id="3102b-708">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-709">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-709">January 31, 2017</span></span></td>
<td><span data-ttu-id="3102b-710">CC003</span><span class="sxs-lookup"><span data-stu-id="3102b-710">CC003</span></span></td>
<td><span data-ttu-id="3102b-711">Montagem</span><span class="sxs-lookup"><span data-stu-id="3102b-711">Assembly</span></span></td>
<td><span data-ttu-id="3102b-712">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-712">10001</span></span></td>
<td><span data-ttu-id="3102b-713">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-713">Electricity</span></span></td>
<td><span data-ttu-id="3102b-714">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-714">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-715">5,982.83</span><span class="sxs-lookup"><span data-stu-id="3102b-715">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-716">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-716">January 31, 2017</span></span></td>
<td><span data-ttu-id="3102b-717">CC003</span><span class="sxs-lookup"><span data-stu-id="3102b-717">CC003</span></span></td>
<td><span data-ttu-id="3102b-718">Embalagem</span><span class="sxs-lookup"><span data-stu-id="3102b-718">Packaging</span></span></td>
<td><span data-ttu-id="3102b-719">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-719">10001</span></span></td>
<td><span data-ttu-id="3102b-720">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-720">Electricity</span></span></td>
<td><span data-ttu-id="3102b-721">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-721">Fixed cost</span></span></td>
<td><span data-ttu-id="3102b-722">286.25</span><span class="sxs-lookup"><span data-stu-id="3102b-722">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-723">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-723">January 31, 2017</span></span></td>
<td><span data-ttu-id="3102b-724">CC003</span><span class="sxs-lookup"><span data-stu-id="3102b-724">CC003</span></span></td>
<td><span data-ttu-id="3102b-725">Embalagem</span><span class="sxs-lookup"><span data-stu-id="3102b-725">Packaging</span></span></td>
<td><span data-ttu-id="3102b-726">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-726">10001</span></span></td>
<td><span data-ttu-id="3102b-727">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-727">Electricity</span></span></td>
<td><span data-ttu-id="3102b-728">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-728">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-729">2,977.17</span><span class="sxs-lookup"><span data-stu-id="3102b-729">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-730">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-730">January 31, 2017</span></span></td>
<td><span data-ttu-id="3102b-731">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3102b-731">Prod 1</span></span></td>
<td><span data-ttu-id="3102b-732">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3102b-732">Product 1</span></span></td>
<td><span data-ttu-id="3102b-733">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-733">10001</span></span></td>
<td><span data-ttu-id="3102b-734">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-734">Electricity</span></span></td>
<td><span data-ttu-id="3102b-735">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-735">Fixed cost</span></span></td>
<td><span data-ttu-id="3102b-736">776.36</span><span class="sxs-lookup"><span data-stu-id="3102b-736">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-737">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-737">January 31, 2017</span></span></td>
<td><span data-ttu-id="3102b-738">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3102b-738">Prod 1</span></span></td>
<td><span data-ttu-id="3102b-739">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3102b-739">Product 1</span></span></td>
<td><span data-ttu-id="3102b-740">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-740">10001</span></span></td>
<td><span data-ttu-id="3102b-741">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-741">Electricity</span></span></td>
<td><span data-ttu-id="3102b-742">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-742">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-743">6,994.21</span><span class="sxs-lookup"><span data-stu-id="3102b-743">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-744">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-744">January 31, 2017</span></span></td>
<td><span data-ttu-id="3102b-745">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3102b-745">Prod 2</span></span></td>
<td><span data-ttu-id="3102b-746">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3102b-746">Product 1</span></span></td>
<td><span data-ttu-id="3102b-747">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-747">10001</span></span></td>
<td><span data-ttu-id="3102b-748">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-748">Electricity</span></span></td>
<td><span data-ttu-id="3102b-749">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-749">Fixed cost</span></span></td>
<td><span data-ttu-id="3102b-750">223.64</span><span class="sxs-lookup"><span data-stu-id="3102b-750">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-751">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-751">January 31, 2017</span></span></td>
<td><span data-ttu-id="3102b-752">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3102b-752">Prod 2</span></span></td>
<td><span data-ttu-id="3102b-753">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3102b-753">Product 1</span></span></td>
<td><span data-ttu-id="3102b-754">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-754">10001</span></span></td>
<td><span data-ttu-id="3102b-755">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-755">Electricity</span></span></td>
<td><span data-ttu-id="3102b-756">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-756">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-757">1,965.79</span><span class="sxs-lookup"><span data-stu-id="3102b-757">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="3102b-758">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-758">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3102b-759">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-759">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="3102b-760">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-760">Cost element</span></span></th>
<th><span data-ttu-id="3102b-761">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-761">Cost behavior</span></span></th>
<th><span data-ttu-id="3102b-762">Valor</span><span class="sxs-lookup"><span data-stu-id="3102b-762">Amount</span></span></th>
<th><span data-ttu-id="3102b-763">Data contábil</span><span class="sxs-lookup"><span data-stu-id="3102b-763">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3102b-764">CC001</span><span class="sxs-lookup"><span data-stu-id="3102b-764">CC001</span></span></td>
<td><span data-ttu-id="3102b-765">RH</span><span class="sxs-lookup"><span data-stu-id="3102b-765">HR</span></span></td>
<td><span data-ttu-id="3102b-766">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-766">10001</span></span></td>
<td><span data-ttu-id="3102b-767">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-767">Electricity</span></span></td>
<td><span data-ttu-id="3102b-768">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-768">Fixed cost</span></span></td>
<td><span data-ttu-id="3102b-769">-500,00</span><span class="sxs-lookup"><span data-stu-id="3102b-769">-500.00</span></span></td>
<td><span data-ttu-id="3102b-770">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-770">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-771">CC002</span><span class="sxs-lookup"><span data-stu-id="3102b-771">CC002</span></span></td>
<td><span data-ttu-id="3102b-772">Finanças</span><span class="sxs-lookup"><span data-stu-id="3102b-772">Finance</span></span></td>
<td><span data-ttu-id="3102b-773">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-773">10001</span></span></td>
<td><span data-ttu-id="3102b-774">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-774">Electricity</span></span></td>
<td><span data-ttu-id="3102b-775">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-775">Fixed cost</span></span></td>
<td><span data-ttu-id="3102b-776">175.00</span><span class="sxs-lookup"><span data-stu-id="3102b-776">175.00</span></span></td>
<td><span data-ttu-id="3102b-777">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-777">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-778">CC003</span><span class="sxs-lookup"><span data-stu-id="3102b-778">CC003</span></span></td>
<td><span data-ttu-id="3102b-779">Montagem</span><span class="sxs-lookup"><span data-stu-id="3102b-779">Assembly</span></span></td>
<td><span data-ttu-id="3102b-780">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-780">10001</span></span></td>
<td><span data-ttu-id="3102b-781">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-781">Electricity</span></span></td>
<td><span data-ttu-id="3102b-782">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-782">Fixed cost</span></span></td>
<td><span data-ttu-id="3102b-783">275.00</span><span class="sxs-lookup"><span data-stu-id="3102b-783">275.00</span></span></td>
<td><span data-ttu-id="3102b-784">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-784">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-785">CC004</span><span class="sxs-lookup"><span data-stu-id="3102b-785">CC004</span></span></td>
<td><span data-ttu-id="3102b-786">Embalagem</span><span class="sxs-lookup"><span data-stu-id="3102b-786">Packaging</span></span></td>
<td><span data-ttu-id="3102b-787">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-787">10001</span></span></td>
<td><span data-ttu-id="3102b-788">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-788">Electricity</span></span></td>
<td><span data-ttu-id="3102b-789">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-789">Fixed cost</span></span></td>
<td><span data-ttu-id="3102b-790">50,00</span><span class="sxs-lookup"><span data-stu-id="3102b-790">50,00</span></span></td>
<td><span data-ttu-id="3102b-791">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-791">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-792">CC001</span><span class="sxs-lookup"><span data-stu-id="3102b-792">CC001</span></span></td>
<td><span data-ttu-id="3102b-793">RH</span><span class="sxs-lookup"><span data-stu-id="3102b-793">HR</span></span></td>
<td><span data-ttu-id="3102b-794">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-794">10001</span></span></td>
<td><span data-ttu-id="3102b-795">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-795">Electricity</span></span></td>
<td><span data-ttu-id="3102b-796">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-796">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-797">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="3102b-797">-1,245.71</span></span></td>
<td><span data-ttu-id="3102b-798">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-798">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-799">CC002</span><span class="sxs-lookup"><span data-stu-id="3102b-799">CC002</span></span></td>
<td><span data-ttu-id="3102b-800">Finanças</span><span class="sxs-lookup"><span data-stu-id="3102b-800">Finance</span></span></td>
<td><span data-ttu-id="3102b-801">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-801">10001</span></span></td>
<td><span data-ttu-id="3102b-802">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-802">Electricity</span></span></td>
<td><span data-ttu-id="3102b-803">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-803">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-804">436.00</span><span class="sxs-lookup"><span data-stu-id="3102b-804">436.00</span></span></td>
<td><span data-ttu-id="3102b-805">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-805">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-806">CC003</span><span class="sxs-lookup"><span data-stu-id="3102b-806">CC003</span></span></td>
<td><span data-ttu-id="3102b-807">Montagem</span><span class="sxs-lookup"><span data-stu-id="3102b-807">Assembly</span></span></td>
<td><span data-ttu-id="3102b-808">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-808">10001</span></span></td>
<td><span data-ttu-id="3102b-809">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-809">Electricity</span></span></td>
<td><span data-ttu-id="3102b-810">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-810">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-811">685.14</span><span class="sxs-lookup"><span data-stu-id="3102b-811">685.14</span></span></td>
<td><span data-ttu-id="3102b-812">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-812">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-813">CC004</span><span class="sxs-lookup"><span data-stu-id="3102b-813">CC004</span></span></td>
<td><span data-ttu-id="3102b-814">Embalagem</span><span class="sxs-lookup"><span data-stu-id="3102b-814">Packaging</span></span></td>
<td><span data-ttu-id="3102b-815">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-815">10001</span></span></td>
<td><span data-ttu-id="3102b-816">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-816">Electricity</span></span></td>
<td><span data-ttu-id="3102b-817">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-817">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-818">124.57</span><span class="sxs-lookup"><span data-stu-id="3102b-818">124.57</span></span></td>
<td><span data-ttu-id="3102b-819">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-819">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-820">CC002</span><span class="sxs-lookup"><span data-stu-id="3102b-820">CC002</span></span></td>
<td><span data-ttu-id="3102b-821">Finanças</span><span class="sxs-lookup"><span data-stu-id="3102b-821">Finance</span></span></td>
<td><span data-ttu-id="3102b-822">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-822">10001</span></span></td>
<td><span data-ttu-id="3102b-823">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-823">Electricity</span></span></td>
<td><span data-ttu-id="3102b-824">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-824">Fixed cost</span></span></td>
<td><span data-ttu-id="3102b-825">-675,00</span><span class="sxs-lookup"><span data-stu-id="3102b-825">-675.00</span></span></td>
<td><span data-ttu-id="3102b-826">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-826">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-827">CC003</span><span class="sxs-lookup"><span data-stu-id="3102b-827">CC003</span></span></td>
<td><span data-ttu-id="3102b-828">Montagem</span><span class="sxs-lookup"><span data-stu-id="3102b-828">Assembly</span></span></td>
<td><span data-ttu-id="3102b-829">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-829">10001</span></span></td>
<td><span data-ttu-id="3102b-830">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-830">Electricity</span></span></td>
<td><span data-ttu-id="3102b-831">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-831">Fixed cost</span></span></td>
<td><span data-ttu-id="3102b-832">438.75</span><span class="sxs-lookup"><span data-stu-id="3102b-832">438.75</span></span></td>
<td><span data-ttu-id="3102b-833">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-833">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-834">CC004</span><span class="sxs-lookup"><span data-stu-id="3102b-834">CC004</span></span></td>
<td><span data-ttu-id="3102b-835">Embalagem</span><span class="sxs-lookup"><span data-stu-id="3102b-835">Packaging</span></span></td>
<td><span data-ttu-id="3102b-836">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-836">10001</span></span></td>
<td><span data-ttu-id="3102b-837">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-837">Electricity</span></span></td>
<td><span data-ttu-id="3102b-838">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-838">Fixed cost</span></span></td>
<td><span data-ttu-id="3102b-839">236.25</span><span class="sxs-lookup"><span data-stu-id="3102b-839">236.25</span></span></td>
<td><span data-ttu-id="3102b-840">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-840">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-841">CC002</span><span class="sxs-lookup"><span data-stu-id="3102b-841">CC002</span></span></td>
<td><span data-ttu-id="3102b-842">Finanças</span><span class="sxs-lookup"><span data-stu-id="3102b-842">Finance</span></span></td>
<td><span data-ttu-id="3102b-843">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-843">10001</span></span></td>
<td><span data-ttu-id="3102b-844">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-844">Electricity</span></span></td>
<td><span data-ttu-id="3102b-845">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-845">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-846">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="3102b-846">-8,150.29</span></span></td>
<td><span data-ttu-id="3102b-847">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-847">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-848">CC003</span><span class="sxs-lookup"><span data-stu-id="3102b-848">CC003</span></span></td>
<td><span data-ttu-id="3102b-849">Montagem</span><span class="sxs-lookup"><span data-stu-id="3102b-849">Assembly</span></span></td>
<td><span data-ttu-id="3102b-850">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-850">10001</span></span></td>
<td><span data-ttu-id="3102b-851">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-851">Electricity</span></span></td>
<td><span data-ttu-id="3102b-852">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-852">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-853">5,297.69</span><span class="sxs-lookup"><span data-stu-id="3102b-853">5,297.69</span></span></td>
<td><span data-ttu-id="3102b-854">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-854">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-855">CC004</span><span class="sxs-lookup"><span data-stu-id="3102b-855">CC004</span></span></td>
<td><span data-ttu-id="3102b-856">Embalagem</span><span class="sxs-lookup"><span data-stu-id="3102b-856">Packaging</span></span></td>
<td><span data-ttu-id="3102b-857">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-857">10001</span></span></td>
<td><span data-ttu-id="3102b-858">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-858">Electricity</span></span></td>
<td><span data-ttu-id="3102b-859">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-859">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-860">2,852.60</span><span class="sxs-lookup"><span data-stu-id="3102b-860">2,852.60</span></span></td>
<td><span data-ttu-id="3102b-861">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-861">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-862">CC003</span><span class="sxs-lookup"><span data-stu-id="3102b-862">CC003</span></span></td>
<td><span data-ttu-id="3102b-863">Montagem</span><span class="sxs-lookup"><span data-stu-id="3102b-863">Assembly</span></span></td>
<td><span data-ttu-id="3102b-864">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-864">10001</span></span></td>
<td><span data-ttu-id="3102b-865">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-865">Electricity</span></span></td>
<td><span data-ttu-id="3102b-866">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-866">Fixed cost</span></span></td>
<td><span data-ttu-id="3102b-867">-713,75</span><span class="sxs-lookup"><span data-stu-id="3102b-867">-713.75</span></span></td>
<td><span data-ttu-id="3102b-868">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-868">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-869">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3102b-869">Prod 1</span></span></td>
<td><span data-ttu-id="3102b-870">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3102b-870">Product 1</span></span></td>
<td><span data-ttu-id="3102b-871">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-871">10001</span></span></td>
<td><span data-ttu-id="3102b-872">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-872">Electricity</span></span></td>
<td><span data-ttu-id="3102b-873">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-873">Fixed cost</span></span></td>
<td><span data-ttu-id="3102b-874">535.31</span><span class="sxs-lookup"><span data-stu-id="3102b-874">535.31</span></span></td>
<td><span data-ttu-id="3102b-875">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-875">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-876">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3102b-876">Prod 2</span></span></td>
<td><span data-ttu-id="3102b-877">Produto 2</span><span class="sxs-lookup"><span data-stu-id="3102b-877">Product 2</span></span></td>
<td><span data-ttu-id="3102b-878">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-878">10001</span></span></td>
<td><span data-ttu-id="3102b-879">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-879">Electricity</span></span></td>
<td><span data-ttu-id="3102b-880">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-880">Fixed cost</span></span></td>
<td><span data-ttu-id="3102b-881">178.44</span><span class="sxs-lookup"><span data-stu-id="3102b-881">178.44</span></span></td>
<td><span data-ttu-id="3102b-882">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-882">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-883">CC003</span><span class="sxs-lookup"><span data-stu-id="3102b-883">CC003</span></span></td>
<td><span data-ttu-id="3102b-884">Montagem</span><span class="sxs-lookup"><span data-stu-id="3102b-884">Assembly</span></span></td>
<td><span data-ttu-id="3102b-885">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-885">10001</span></span></td>
<td><span data-ttu-id="3102b-886">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-886">Electricity</span></span></td>
<td><span data-ttu-id="3102b-887">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-887">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-888">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="3102b-888">-5,982.83</span></span></td>
<td><span data-ttu-id="3102b-889">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-889">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-890">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3102b-890">Prod 1</span></span></td>
<td><span data-ttu-id="3102b-891">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3102b-891">Product 1</span></span></td>
<td><span data-ttu-id="3102b-892">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-892">10001</span></span></td>
<td><span data-ttu-id="3102b-893">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-893">Electricity</span></span></td>
<td><span data-ttu-id="3102b-894">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-894">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-895">4,487.12</span><span class="sxs-lookup"><span data-stu-id="3102b-895">4,487.12</span></span></td>
<td><span data-ttu-id="3102b-896">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-896">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-897">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3102b-897">Prod 2</span></span></td>
<td><span data-ttu-id="3102b-898">Produto 2</span><span class="sxs-lookup"><span data-stu-id="3102b-898">Product 2</span></span></td>
<td><span data-ttu-id="3102b-899">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-899">10001</span></span></td>
<td><span data-ttu-id="3102b-900">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-900">Electricity</span></span></td>
<td><span data-ttu-id="3102b-901">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-901">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-902">1,495.71</span><span class="sxs-lookup"><span data-stu-id="3102b-902">1,495.71</span></span></td>
<td><span data-ttu-id="3102b-903">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-903">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-904">CC003</span><span class="sxs-lookup"><span data-stu-id="3102b-904">CC003</span></span></td>
<td><span data-ttu-id="3102b-905">Montagem</span><span class="sxs-lookup"><span data-stu-id="3102b-905">Assembly</span></span></td>
<td><span data-ttu-id="3102b-906">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-906">10001</span></span></td>
<td><span data-ttu-id="3102b-907">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-907">Electricity</span></span></td>
<td><span data-ttu-id="3102b-908">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-908">Fixed cost</span></span></td>
<td><span data-ttu-id="3102b-909">-286,25</span><span class="sxs-lookup"><span data-stu-id="3102b-909">-286.25</span></span></td>
<td><span data-ttu-id="3102b-910">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-910">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-911">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3102b-911">Prod 1</span></span></td>
<td><span data-ttu-id="3102b-912">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3102b-912">Product 1</span></span></td>
<td><span data-ttu-id="3102b-913">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-913">10001</span></span></td>
<td><span data-ttu-id="3102b-914">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-914">Electricity</span></span></td>
<td><span data-ttu-id="3102b-915">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-915">Fixed cost</span></span></td>
<td><span data-ttu-id="3102b-916">241.05</span><span class="sxs-lookup"><span data-stu-id="3102b-916">241.05</span></span></td>
<td><span data-ttu-id="3102b-917">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-917">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-918">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3102b-918">Prod 2</span></span></td>
<td><span data-ttu-id="3102b-919">Produto 2</span><span class="sxs-lookup"><span data-stu-id="3102b-919">Product 2</span></span></td>
<td><span data-ttu-id="3102b-920">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-920">10001</span></span></td>
<td><span data-ttu-id="3102b-921">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-921">Electricity</span></span></td>
<td><span data-ttu-id="3102b-922">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-922">Fixed cost</span></span></td>
<td><span data-ttu-id="3102b-923">45.20</span><span class="sxs-lookup"><span data-stu-id="3102b-923">45.20</span></span></td>
<td><span data-ttu-id="3102b-924">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-924">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-925">CC003</span><span class="sxs-lookup"><span data-stu-id="3102b-925">CC003</span></span></td>
<td><span data-ttu-id="3102b-926">Montagem</span><span class="sxs-lookup"><span data-stu-id="3102b-926">Assembly</span></span></td>
<td><span data-ttu-id="3102b-927">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-927">10001</span></span></td>
<td><span data-ttu-id="3102b-928">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-928">Electricity</span></span></td>
<td><span data-ttu-id="3102b-929">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-929">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-930">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="3102b-930">-2,977.17</span></span></td>
<td><span data-ttu-id="3102b-931">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-931">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-932">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3102b-932">Prod 1</span></span></td>
<td><span data-ttu-id="3102b-933">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3102b-933">Product 1</span></span></td>
<td><span data-ttu-id="3102b-934">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-934">10001</span></span></td>
<td><span data-ttu-id="3102b-935">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-935">Electricity</span></span></td>
<td><span data-ttu-id="3102b-936">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-936">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-937">2,507.09</span><span class="sxs-lookup"><span data-stu-id="3102b-937">2,507.09</span></span></td>
<td><span data-ttu-id="3102b-938">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-938">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3102b-939">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3102b-939">Prod 2</span></span></td>
<td><span data-ttu-id="3102b-940">Produto 2</span><span class="sxs-lookup"><span data-stu-id="3102b-940">Product 2</span></span></td>
<td><span data-ttu-id="3102b-941">10001</span><span class="sxs-lookup"><span data-stu-id="3102b-941">10001</span></span></td>
<td><span data-ttu-id="3102b-942">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-942">Electricity</span></span></td>
<td><span data-ttu-id="3102b-943">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-943">Variable cost</span></span></td>
<td><span data-ttu-id="3102b-944">470.08</span><span class="sxs-lookup"><span data-stu-id="3102b-944">470.08</span></span></td>
<td><span data-ttu-id="3102b-945">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3102b-945">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="3102b-946">Conclusão</span><span class="sxs-lookup"><span data-stu-id="3102b-946">Conclusion</span></span>
<span data-ttu-id="3102b-947">Na contabilidade financeira, um custo de 10,000.00 para a eletricidade é lançado para um ID fictício de centro de custos.</span><span class="sxs-lookup"><span data-stu-id="3102b-947">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="3102b-948">Portanto, os contadores de custo saberão que esses custos devem ser alocados.</span><span class="sxs-lookup"><span data-stu-id="3102b-948">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="3102b-949">Na contabilização de custo, os custos fluem nas unidades organizacionais e nos níveis, com base nas políticas e regras que são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="3102b-949">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="3102b-950">Cada custo foi associado a uma base de alocação que fornece a melhor apuração para a alocação de custos.</span><span class="sxs-lookup"><span data-stu-id="3102b-950">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="3102b-951">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-951">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="3102b-952">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3102b-952">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="3102b-953">Total</span><span class="sxs-lookup"><span data-stu-id="3102b-953">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="3102b-954">CC099</span><span class="sxs-lookup"><span data-stu-id="3102b-954">CC099</span></span></th>
<th><span data-ttu-id="3102b-955">CC001</span><span class="sxs-lookup"><span data-stu-id="3102b-955">CC001</span></span></th>
<th><span data-ttu-id="3102b-956">CC002</span><span class="sxs-lookup"><span data-stu-id="3102b-956">CC002</span></span></th>
<th><span data-ttu-id="3102b-957">CC003</span><span class="sxs-lookup"><span data-stu-id="3102b-957">CC003</span></span></th>
<th><span data-ttu-id="3102b-958">CC004</span><span class="sxs-lookup"><span data-stu-id="3102b-958">CC004</span></span></th>
<th><span data-ttu-id="3102b-959">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="3102b-959">Proj 1</span></span></th>
<th><span data-ttu-id="3102b-960">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="3102b-960">Proj 2</span></span></th>
<th><span data-ttu-id="3102b-961">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3102b-961">Prod 1</span></span></th>
<th><span data-ttu-id="3102b-962">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3102b-962">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="3102b-963">10001 Eletricidade</span><span class="sxs-lookup"><span data-stu-id="3102b-963">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="3102b-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-965"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="3102b-965"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-966"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="3102b-966"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-967"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="3102b-967"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="3102b-968"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="3102b-968"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-969"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="3102b-969"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-970"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="3102b-970"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-971"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="3102b-971"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-972"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="3102b-972"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="3102b-973">Não classificado</span><span class="sxs-lookup"><span data-stu-id="3102b-973">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-974">0,00</span><span class="sxs-lookup"><span data-stu-id="3102b-974">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="3102b-975">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3102b-975">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-976">0,00</span><span class="sxs-lookup"><span data-stu-id="3102b-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-977">0,00</span><span class="sxs-lookup"><span data-stu-id="3102b-977">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-978">0,00</span><span class="sxs-lookup"><span data-stu-id="3102b-978">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-979">0,00</span><span class="sxs-lookup"><span data-stu-id="3102b-979">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-980">0,00</span><span class="sxs-lookup"><span data-stu-id="3102b-980">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="3102b-981">776.36</span><span class="sxs-lookup"><span data-stu-id="3102b-981">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-982">223.64</span><span class="sxs-lookup"><span data-stu-id="3102b-982">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-983"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="3102b-983"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="3102b-984">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3102b-984">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-985">000</span><span class="sxs-lookup"><span data-stu-id="3102b-985">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-986">0,00</span><span class="sxs-lookup"><span data-stu-id="3102b-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-987">0,00</span><span class="sxs-lookup"><span data-stu-id="3102b-987">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-988">0,00</span><span class="sxs-lookup"><span data-stu-id="3102b-988">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-989">0,00</span><span class="sxs-lookup"><span data-stu-id="3102b-989">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-990">30,00</span><span class="sxs-lookup"><span data-stu-id="3102b-990">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-991">10,00</span><span class="sxs-lookup"><span data-stu-id="3102b-991">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-992">6,994.21</span><span class="sxs-lookup"><span data-stu-id="3102b-992">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-993">1,965.79</span><span class="sxs-lookup"><span data-stu-id="3102b-993">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3102b-994"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="3102b-994"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="3102b-995">Esse tópico mostra como um elemento de custo principal, 10001 Eletricidade flui pelos objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="3102b-995">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="3102b-996">Portanto, esse custo geral indireto é alocado no nível mais baixo na organização.</span><span class="sxs-lookup"><span data-stu-id="3102b-996">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="3102b-997">Em outras palavras, os objetos de custo no nível mais baixo assumem o custo.</span><span class="sxs-lookup"><span data-stu-id="3102b-997">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="3102b-998">Se você exigir um fluxo visual de custo entre objetos de custo, é possível usar as regras de política de acúmulo de custos para visualizar o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="3102b-998">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="3102b-999">Para obter informações mais detalhadas, consulte a política de acúmulo de custos.</span><span class="sxs-lookup"><span data-stu-id="3102b-999">For more detailed information, see Cost roll-up policy.</span></span> <span data-ttu-id="3102b-1000">(Observe que este tópico não está incluído, mas estará em breve).</span><span class="sxs-lookup"><span data-stu-id="3102b-1000">(Note that this topic isn't competed yet but is coming soon.)</span></span>




