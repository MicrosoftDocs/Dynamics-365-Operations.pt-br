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
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: e57db8f4b692aa9c27916625897e268f63031782
ms.openlocfilehash: 285799d70a945c2dae1e3c65296282d5c432a243
ms.contentlocale: pt-br
ms.lasthandoff: 10/30/2017

---

# <a name="overhead-calculation"></a><span data-ttu-id="ce845-103">Cálculo de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="ce845-103">Overhead calculation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="ce845-104">Este tópico descreve processos comuns para calcular e alocar os custos gerais indiretos.</span><span class="sxs-lookup"><span data-stu-id="ce845-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="ce845-105">Definição de termo</span><span class="sxs-lookup"><span data-stu-id="ce845-105">Term definition</span></span>
---------------

<span data-ttu-id="ce845-106">Os custos gerais indiretos são aqueles que foram incorridos para realizar um negócio, mas não podem ser diretamente atribuídos a qualquer atividade comercial, produto ou serviço específico.</span><span class="sxs-lookup"><span data-stu-id="ce845-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="ce845-107">Os custos gerais indiretos fornecem suporte crítico para geração de atividades produtivas.</span><span class="sxs-lookup"><span data-stu-id="ce845-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="ce845-108">Eis alguns exemplos de custos gerais:</span><span class="sxs-lookup"><span data-stu-id="ce845-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="ce845-109">Aluguel</span><span class="sxs-lookup"><span data-stu-id="ce845-109">Rent</span></span>
-   <span data-ttu-id="ce845-110">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-110">Electricity</span></span>
-   <span data-ttu-id="ce845-111">Salários administrativos</span><span class="sxs-lookup"><span data-stu-id="ce845-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="ce845-112">Visão geral do cálculo de custos gerais indiretos</span><span class="sxs-lookup"><span data-stu-id="ce845-112">Overhead calculation overview</span></span>
<span data-ttu-id="ce845-113">O cálculo de custos gerais indiretos executa as políticas de contabilização de custos na ordem correta.</span><span class="sxs-lookup"><span data-stu-id="ce845-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="ce845-114">Você pode executar o cálculo de custos gerais indiretos várias vezes para o mesmo período fiscal, se as políticas de contabilidade de custo foram modificadas ou foram detectados erros específicos.</span><span class="sxs-lookup"><span data-stu-id="ce845-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="ce845-115">Cada execução do cálculo de custos gerais indiretos é armazenada e recebe um ID exclusivo de versão que permite comparar os cálculos em várias versões.</span><span class="sxs-lookup"><span data-stu-id="ce845-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="ce845-116">As entradas de custo que o cálculo de custos indiretos gera recebe uma data contábil.</span><span class="sxs-lookup"><span data-stu-id="ce845-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="ce845-117">Essa data contábil corresponde à data final do período fiscal que é usada no cálculo.</span><span class="sxs-lookup"><span data-stu-id="ce845-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="ce845-118">A ID exclusiva de versão consiste nos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="ce845-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="ce845-119">Tipo de versão</span><span class="sxs-lookup"><span data-stu-id="ce845-119">Version type</span></span>
-   <span data-ttu-id="ce845-120">Data e hora</span><span class="sxs-lookup"><span data-stu-id="ce845-120">Date and time</span></span>
-   <span data-ttu-id="ce845-121">Razão de contabilização de custos</span><span class="sxs-lookup"><span data-stu-id="ce845-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="ce845-122">Ano fiscal</span><span class="sxs-lookup"><span data-stu-id="ce845-122">Fiscal year</span></span>
-   <span data-ttu-id="ce845-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="ce845-123">Fiscal period</span></span>

<span data-ttu-id="ce845-124">O cálculo de custos gerais indiretos é executado independentemente da versão.</span><span class="sxs-lookup"><span data-stu-id="ce845-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="ce845-125">Portanto, você pode calcular a versão de orçamento antes da versão atual.</span><span class="sxs-lookup"><span data-stu-id="ce845-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="ce845-126">O cálculo de custos gerais indiretos consiste em quatro etapas, conforme mostrado na ilustração.</span><span class="sxs-lookup"><span data-stu-id="ce845-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="ce845-127">Em cada etapa, um cabeçalho de diário é criado com entradas de diário.</span><span class="sxs-lookup"><span data-stu-id="ce845-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="ce845-128">Esse cabeçalho de diário mantém dados de entrada para cada etapa de cálculo.</span><span class="sxs-lookup"><span data-stu-id="ce845-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="ce845-129">As políticas e regras são aplicadas a cada linha do diário e as entradas de custo são geradas como saídas.</span><span class="sxs-lookup"><span data-stu-id="ce845-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="ce845-130">Portanto, você sempre terá rastreabilidade total.</span><span class="sxs-lookup"><span data-stu-id="ce845-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="ce845-131">[![Cálculo de custos gerais indiretos](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="ce845-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="ce845-132">Calcular e alocar os custos gerais indiretos de Eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="ce845-133">Na contabilidade financeira, alguns custos, como eletricidade, são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="ce845-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="ce845-134">Portanto, a visão administrativa detalhada não é fornecida para a contabilização de custo.</span><span class="sxs-lookup"><span data-stu-id="ce845-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="ce845-135">Na contabilização de custo, para fornecer a visão administrativa correta em todas as unidades organizacionais e níveis, os custos devem passar pelas unidades organizacionais.</span><span class="sxs-lookup"><span data-stu-id="ce845-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="ce845-136">Este fluxo deve ser baseado em qualquer um registro exato do consumo ou de uma previsão justa.</span><span class="sxs-lookup"><span data-stu-id="ce845-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="ce845-137">Na contabilidade, um custo de eletricidade pode ser lançado, conforme mostrado na tabela.</span><span class="sxs-lookup"><span data-stu-id="ce845-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ce845-138">Data contábil</span><span class="sxs-lookup"><span data-stu-id="ce845-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ce845-139">Centro de custos</span><span class="sxs-lookup"><span data-stu-id="ce845-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="ce845-140">Conta principal</span><span class="sxs-lookup"><span data-stu-id="ce845-140">Main account</span></span></th>
<th><span data-ttu-id="ce845-141">Valor na moeda contábil</span><span class="sxs-lookup"><span data-stu-id="ce845-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-142">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="ce845-143">CC099</span><span class="sxs-lookup"><span data-stu-id="ce845-143">CC099</span></span></td>
<td><span data-ttu-id="ce845-144">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="ce845-144">Default cost center</span></span></td>
<td><span data-ttu-id="ce845-145">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-145">10001</span></span></td>
<td><span data-ttu-id="ce845-146">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-146">Electricity</span></span></td>
<td><span data-ttu-id="ce845-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="ce845-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="ce845-148">Etapa 1: Processar o cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="ce845-149">Por padrão, quando as entradas de custo previsto são importadas de dados de origem, elas recebem a classificação de comportamento de custo **Não classificado** na Contabilidade de custos.</span><span class="sxs-lookup"><span data-stu-id="ce845-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="ce845-150">Aplicando regras da política de comportamento de custo, é possível reclassificar entradas de custo como **Custo fixo** ou **Custo variável**.</span><span class="sxs-lookup"><span data-stu-id="ce845-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="ce845-151">Definir a regra de custo de comportamento</span><span class="sxs-lookup"><span data-stu-id="ce845-151">Define the cost behavior rule</span></span>

<span data-ttu-id="ce845-152">Em alguns casos, parte do custo é uma taxa fixa e o custos pendente é baseado no consumo.</span><span class="sxs-lookup"><span data-stu-id="ce845-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="ce845-153">Geralmente, as contas de eletricidade correspondem a esta definição.</span><span class="sxs-lookup"><span data-stu-id="ce845-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="ce845-154">Após você pagar uma taxa fixa específica, você paga por consumo, por hora de quilowatt (Kwh).</span><span class="sxs-lookup"><span data-stu-id="ce845-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="ce845-155">Por exemplo, se a taxa de custo fixa for 1.000.00, veja aqui como a regra de comportamento de custo é definida:</span><span class="sxs-lookup"><span data-stu-id="ce845-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="ce845-156">Valor fixo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="ce845-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="ce845-157">0 &lt;= 1.000,00 = Fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="ce845-158">1000.01 &lt; N = Variável</span><span class="sxs-lookup"><span data-stu-id="ce845-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="ce845-159">Diário</span><span class="sxs-lookup"><span data-stu-id="ce845-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ce845-160">Diário</span><span class="sxs-lookup"><span data-stu-id="ce845-160">Journal</span></span></th>
<th><span data-ttu-id="ce845-161">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="ce845-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ce845-162">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="ce845-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ce845-163">Versão</span><span class="sxs-lookup"><span data-stu-id="ce845-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-164">00001</span><span class="sxs-lookup"><span data-stu-id="ce845-164">00001</span></span></td>
<td><span data-ttu-id="ce845-165">Diário de cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="ce845-166">fiscal</span><span class="sxs-lookup"><span data-stu-id="ce845-166">Fiscal</span></span></td>
<td><span data-ttu-id="ce845-167">2017</span><span class="sxs-lookup"><span data-stu-id="ce845-167">2017</span></span></td>
<td><span data-ttu-id="ce845-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="ce845-168">Period 1</span></span></td>
<td><span data-ttu-id="ce845-169">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="ce845-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="ce845-170">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="ce845-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ce845-171">Data contábil</span><span class="sxs-lookup"><span data-stu-id="ce845-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ce845-172">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ce845-173">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-173">Cost element</span></span></th>
<th><span data-ttu-id="ce845-174">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-174">Cost behavior</span></span></th>
<th><span data-ttu-id="ce845-175">Valor</span><span class="sxs-lookup"><span data-stu-id="ce845-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-176">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="ce845-177">CC099</span><span class="sxs-lookup"><span data-stu-id="ce845-177">CC099</span></span></td>
<td><span data-ttu-id="ce845-178">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="ce845-178">Default cost center</span></span></td>
<td><span data-ttu-id="ce845-179">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-179">10001</span></span></td>
<td><span data-ttu-id="ce845-180">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-180">Electricity</span></span></td>
<td><span data-ttu-id="ce845-181">Não classificado</span><span class="sxs-lookup"><span data-stu-id="ce845-181">Unclassified</span></span></td>
<td><span data-ttu-id="ce845-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="ce845-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ce845-183">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ce845-184">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ce845-185">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-185">Cost element</span></span></th>
<th><span data-ttu-id="ce845-186">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-186">Cost behavior</span></span></th>
<th><span data-ttu-id="ce845-187">Valor</span><span class="sxs-lookup"><span data-stu-id="ce845-187">Amount</span></span></th>
<th><span data-ttu-id="ce845-188">Data contábil</span><span class="sxs-lookup"><span data-stu-id="ce845-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-189">CC099</span><span class="sxs-lookup"><span data-stu-id="ce845-189">CC099</span></span></td>
<td><span data-ttu-id="ce845-190">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="ce845-190">Default cost center</span></span></td>
<td><span data-ttu-id="ce845-191">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-191">10001</span></span></td>
<td><span data-ttu-id="ce845-192">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-192">Electricity</span></span></td>
<td><span data-ttu-id="ce845-193">Não classificado</span><span class="sxs-lookup"><span data-stu-id="ce845-193">Unclassified</span></span></td>
<td><span data-ttu-id="ce845-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="ce845-194">10,000.00</span></span></td>
<td><span data-ttu-id="ce845-195">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-196">CC099</span><span class="sxs-lookup"><span data-stu-id="ce845-196">CC099</span></span></td>
<td><span data-ttu-id="ce845-197">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="ce845-197">Default cost center</span></span></td>
<td><span data-ttu-id="ce845-198">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-198">10001</span></span></td>
<td><span data-ttu-id="ce845-199">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-199">Electricity</span></span></td>
<td><span data-ttu-id="ce845-200">Não classificado</span><span class="sxs-lookup"><span data-stu-id="ce845-200">Unclassified</span></span></td>
<td><span data-ttu-id="ce845-201">-10.000,00</span><span class="sxs-lookup"><span data-stu-id="ce845-201">-10,000.00</span></span></td>
<td><span data-ttu-id="ce845-202">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-203">CC099</span><span class="sxs-lookup"><span data-stu-id="ce845-203">CC099</span></span></td>
<td><span data-ttu-id="ce845-204">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="ce845-204">Default cost center</span></span></td>
<td><span data-ttu-id="ce845-205">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-205">10001</span></span></td>
<td><span data-ttu-id="ce845-206">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-206">Electricity</span></span></td>
<td><span data-ttu-id="ce845-207">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-207">Fixed cost</span></span></td>
<td><span data-ttu-id="ce845-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="ce845-208">1,000.00</span></span></td>
<td><span data-ttu-id="ce845-209">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-210">CC099</span><span class="sxs-lookup"><span data-stu-id="ce845-210">CC099</span></span></td>
<td><span data-ttu-id="ce845-211">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="ce845-211">Default cost center</span></span></td>
<td><span data-ttu-id="ce845-212">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-212">10001</span></span></td>
<td><span data-ttu-id="ce845-213">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-213">Electricity</span></span></td>
<td><span data-ttu-id="ce845-214">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-214">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="ce845-215">9,000.00</span></span></td>
<td><span data-ttu-id="ce845-216">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ce845-217">Para obter informações detalhadas sobre o comportamento de custo, consulte a política de comportamento de custo.</span><span class="sxs-lookup"><span data-stu-id="ce845-217">For detailed information about cost behavior, see Cost behavior policy.</span></span> <span data-ttu-id="ce845-218">(Observe que este tópico não está incluído, mas estará em breve).</span><span class="sxs-lookup"><span data-stu-id="ce845-218">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="ce845-219">Etapa 2: Processar o cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-219">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="ce845-220">A distribuição de custos é usada para redistribuir custo de um objeto de custo a um ou mais outros objetos de custo, aplicando uma base de alocação relevante.</span><span class="sxs-lookup"><span data-stu-id="ce845-220">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="ce845-221">A distribuição de custos e a alocação de custo são diferentes na distribuição de custos, sempre que ocorrer em nível de elemento de custo principal do custo original.</span><span class="sxs-lookup"><span data-stu-id="ce845-221">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="ce845-222">Definir a regra de distribuição de custos</span><span class="sxs-lookup"><span data-stu-id="ce845-222">Define the cost distribution rule</span></span>

<span data-ttu-id="ce845-223">Na contabilidade financeira, os custos de eletricidade geralmente são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="ce845-223">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="ce845-224">Na contabilização de custo, esta abordagem não é suficientemente detalhada.</span><span class="sxs-lookup"><span data-stu-id="ce845-224">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="ce845-225">O custo variável deve ser distribuído a objetos de custos individuais com base justa.</span><span class="sxs-lookup"><span data-stu-id="ce845-225">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="ce845-226">A base de alocação mais lógica é o consumo de eletricidade (Kwh).</span><span class="sxs-lookup"><span data-stu-id="ce845-226">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="ce845-227">O membro da dimensão estatística que é chamado Eletricidade é criado e o consumo de eletricidade é registrado.</span><span class="sxs-lookup"><span data-stu-id="ce845-227">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="ce845-228">Por padrão, todos os membros estatísticos da dimensão se tornam disponíveis como bases de alocação.</span><span class="sxs-lookup"><span data-stu-id="ce845-228">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ce845-229">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-229">Cost object</span></span></th>
<th><span data-ttu-id="ce845-230">Kwh</span><span class="sxs-lookup"><span data-stu-id="ce845-230">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-231">CC001</span><span class="sxs-lookup"><span data-stu-id="ce845-231">CC001</span></span></td>
<td><span data-ttu-id="ce845-232">RH</span><span class="sxs-lookup"><span data-stu-id="ce845-232">HR</span></span></td>
<td><span data-ttu-id="ce845-233">1.000</span><span class="sxs-lookup"><span data-stu-id="ce845-233">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-234">CC002</span><span class="sxs-lookup"><span data-stu-id="ce845-234">CC002</span></span></td>
<td><span data-ttu-id="ce845-235">Finanças</span><span class="sxs-lookup"><span data-stu-id="ce845-235">Finance</span></span></td>
<td><span data-ttu-id="ce845-236">6,000</span><span class="sxs-lookup"><span data-stu-id="ce845-236">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-237">CC003</span><span class="sxs-lookup"><span data-stu-id="ce845-237">CC003</span></span></td>
<td><span data-ttu-id="ce845-238">Montagem</span><span class="sxs-lookup"><span data-stu-id="ce845-238">Assembly</span></span></td>
<td><span data-ttu-id="ce845-239">0</span><span class="sxs-lookup"><span data-stu-id="ce845-239">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ce845-240">A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação para custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="ce845-240">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ce845-241">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-241">Cost object</span></span></th>
<th><span data-ttu-id="ce845-242">Magnitude</span><span class="sxs-lookup"><span data-stu-id="ce845-242">Magnitude</span></span></th>
<th><span data-ttu-id="ce845-243">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="ce845-243">Allocation factor</span></span></th>
<th><span data-ttu-id="ce845-244">Valor</span><span class="sxs-lookup"><span data-stu-id="ce845-244">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-245">CC001</span><span class="sxs-lookup"><span data-stu-id="ce845-245">CC001</span></span></td>
<td><span data-ttu-id="ce845-246">RH</span><span class="sxs-lookup"><span data-stu-id="ce845-246">HR</span></span></td>
<td><span data-ttu-id="ce845-247">1.000</span><span class="sxs-lookup"><span data-stu-id="ce845-247">1,000</span></span></td>
<td><span data-ttu-id="ce845-248">(1.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="ce845-248">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="ce845-249">1,285.71</span><span class="sxs-lookup"><span data-stu-id="ce845-249">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-250">CC002</span><span class="sxs-lookup"><span data-stu-id="ce845-250">CC002</span></span></td>
<td><span data-ttu-id="ce845-251">Finanças</span><span class="sxs-lookup"><span data-stu-id="ce845-251">Finance</span></span></td>
<td><span data-ttu-id="ce845-252">6,000</span><span class="sxs-lookup"><span data-stu-id="ce845-252">6,000</span></span></td>
<td><span data-ttu-id="ce845-253">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="ce845-253">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="ce845-254">7,714.29</span><span class="sxs-lookup"><span data-stu-id="ce845-254">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-255">CC003</span><span class="sxs-lookup"><span data-stu-id="ce845-255">CC003</span></span></td>
<td><span data-ttu-id="ce845-256">Montagem</span><span class="sxs-lookup"><span data-stu-id="ce845-256">Assembly</span></span></td>
<td><span data-ttu-id="ce845-257">0</span><span class="sxs-lookup"><span data-stu-id="ce845-257">0</span></span></td>
<td><span data-ttu-id="ce845-258">(0 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="ce845-258">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="ce845-259">0,00</span><span class="sxs-lookup"><span data-stu-id="ce845-259">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ce845-260">Os custos fixos devem ser distribuídos igualmente a objetos de custo individuais que têm a eletricidade consumida.</span><span class="sxs-lookup"><span data-stu-id="ce845-260">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="ce845-261">Você pode obter esse resultado usando o membro estatístico de dimensão de eletricidade em uma base e alocação da fórmula: (Eletricidade &gt; 0,00) A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação de custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="ce845-261">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ce845-262">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-262">Cost object</span></span></th>
<th><span data-ttu-id="ce845-263">Fórmula</span><span class="sxs-lookup"><span data-stu-id="ce845-263">Formula</span></span></th>
<th><span data-ttu-id="ce845-264">Magnitude</span><span class="sxs-lookup"><span data-stu-id="ce845-264">Magnitude</span></span></th>
<th><span data-ttu-id="ce845-265">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="ce845-265">Allocation factor</span></span></th>
<th><span data-ttu-id="ce845-266">Valor</span><span class="sxs-lookup"><span data-stu-id="ce845-266">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-267">CC001</span><span class="sxs-lookup"><span data-stu-id="ce845-267">CC001</span></span></td>
<td><span data-ttu-id="ce845-268">RH</span><span class="sxs-lookup"><span data-stu-id="ce845-268">HR</span></span></td>
<td><span data-ttu-id="ce845-269">(1.000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="ce845-269">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="ce845-270">1</span><span class="sxs-lookup"><span data-stu-id="ce845-270">1</span></span></td>
<td><span data-ttu-id="ce845-271">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="ce845-271">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="ce845-272">500,00</span><span class="sxs-lookup"><span data-stu-id="ce845-272">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-273">CC002</span><span class="sxs-lookup"><span data-stu-id="ce845-273">CC002</span></span></td>
<td><span data-ttu-id="ce845-274">Finanças</span><span class="sxs-lookup"><span data-stu-id="ce845-274">Finance</span></span></td>
<td><span data-ttu-id="ce845-275">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="ce845-275">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="ce845-276">1</span><span class="sxs-lookup"><span data-stu-id="ce845-276">1</span></span></td>
<td><span data-ttu-id="ce845-277">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="ce845-277">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="ce845-278">500,00</span><span class="sxs-lookup"><span data-stu-id="ce845-278">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-279">CC003</span><span class="sxs-lookup"><span data-stu-id="ce845-279">CC003</span></span></td>
<td><span data-ttu-id="ce845-280">Montagem</span><span class="sxs-lookup"><span data-stu-id="ce845-280">Assembly</span></span></td>
<td><span data-ttu-id="ce845-281">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="ce845-281">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="ce845-282">0</span><span class="sxs-lookup"><span data-stu-id="ce845-282">0</span></span></td>
<td><span data-ttu-id="ce845-283">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="ce845-283">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="ce845-284">0,00</span><span class="sxs-lookup"><span data-stu-id="ce845-284">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="ce845-285">Diário</span><span class="sxs-lookup"><span data-stu-id="ce845-285">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ce845-286">Diário</span><span class="sxs-lookup"><span data-stu-id="ce845-286">Journal</span></span></th>
<th><span data-ttu-id="ce845-287">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="ce845-287">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ce845-288">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="ce845-288">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ce845-289">Versão</span><span class="sxs-lookup"><span data-stu-id="ce845-289">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-290">00002</span><span class="sxs-lookup"><span data-stu-id="ce845-290">00002</span></span></td>
<td><span data-ttu-id="ce845-291">Diário de cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-291">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="ce845-292">fiscal</span><span class="sxs-lookup"><span data-stu-id="ce845-292">Fiscal</span></span></td>
<td><span data-ttu-id="ce845-293">2017</span><span class="sxs-lookup"><span data-stu-id="ce845-293">2017</span></span></td>
<td><span data-ttu-id="ce845-294">Período 1</span><span class="sxs-lookup"><span data-stu-id="ce845-294">Period 1</span></span></td>
<td><span data-ttu-id="ce845-295">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="ce845-295">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="ce845-296">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="ce845-296">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ce845-297">Data contábil</span><span class="sxs-lookup"><span data-stu-id="ce845-297">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ce845-298">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-298">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ce845-299">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-299">Cost element</span></span></th>
<th><span data-ttu-id="ce845-300">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-300">Cost behavior</span></span></th>
<th><span data-ttu-id="ce845-301">Valor</span><span class="sxs-lookup"><span data-stu-id="ce845-301">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-302">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-302">January 31, 2017</span></span></td>
<td><span data-ttu-id="ce845-303">CC099</span><span class="sxs-lookup"><span data-stu-id="ce845-303">CC099</span></span></td>
<td><span data-ttu-id="ce845-304">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="ce845-304">Default cost center</span></span></td>
<td><span data-ttu-id="ce845-305">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-305">10001</span></span></td>
<td><span data-ttu-id="ce845-306">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-306">Electricity</span></span></td>
<td><span data-ttu-id="ce845-307">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-307">Fixed cost</span></span></td>
<td><span data-ttu-id="ce845-308">1.000,00</span><span class="sxs-lookup"><span data-stu-id="ce845-308">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-309">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-309">January 31, 2017</span></span></td>
<td><span data-ttu-id="ce845-310">CC099</span><span class="sxs-lookup"><span data-stu-id="ce845-310">CC099</span></span></td>
<td><span data-ttu-id="ce845-311">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="ce845-311">Default cost center</span></span></td>
<td><span data-ttu-id="ce845-312">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-312">10001</span></span></td>
<td><span data-ttu-id="ce845-313">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-313">Electricity</span></span></td>
<td><span data-ttu-id="ce845-314">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-314">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-315">9,000.00</span><span class="sxs-lookup"><span data-stu-id="ce845-315">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ce845-316">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-316">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ce845-317">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-317">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ce845-318">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-318">Cost element</span></span></th>
<th><span data-ttu-id="ce845-319">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-319">Cost behavior</span></span></th>
<th><span data-ttu-id="ce845-320">Valor</span><span class="sxs-lookup"><span data-stu-id="ce845-320">Amount</span></span></th>
<th><span data-ttu-id="ce845-321">Data contábil</span><span class="sxs-lookup"><span data-stu-id="ce845-321">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-322">CC099</span><span class="sxs-lookup"><span data-stu-id="ce845-322">CC099</span></span></td>
<td><span data-ttu-id="ce845-323">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="ce845-323">Default cost center</span></span></td>
<td><span data-ttu-id="ce845-324">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-324">10001</span></span></td>
<td><span data-ttu-id="ce845-325">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-325">Electricity</span></span></td>
<td><span data-ttu-id="ce845-326">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-326">Fixed cost</span></span></td>
<td><span data-ttu-id="ce845-327">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="ce845-327">-1,000.00</span></span></td>
<td><span data-ttu-id="ce845-328">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-328">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-329">CC001</span><span class="sxs-lookup"><span data-stu-id="ce845-329">CC001</span></span></td>
<td><span data-ttu-id="ce845-330">RH</span><span class="sxs-lookup"><span data-stu-id="ce845-330">HR</span></span></td>
<td><span data-ttu-id="ce845-331">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-331">10001</span></span></td>
<td><span data-ttu-id="ce845-332">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-332">Electricity</span></span></td>
<td><span data-ttu-id="ce845-333">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-333">Fixed cost</span></span></td>
<td><span data-ttu-id="ce845-334">500,00</span><span class="sxs-lookup"><span data-stu-id="ce845-334">500.00</span></span></td>
<td><span data-ttu-id="ce845-335">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-335">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-336">CC002</span><span class="sxs-lookup"><span data-stu-id="ce845-336">CC002</span></span></td>
<td><span data-ttu-id="ce845-337">Finanças</span><span class="sxs-lookup"><span data-stu-id="ce845-337">Finance</span></span></td>
<td><span data-ttu-id="ce845-338">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-338">10001</span></span></td>
<td><span data-ttu-id="ce845-339">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-339">Electricity</span></span></td>
<td><span data-ttu-id="ce845-340">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-340">Fixed cost</span></span></td>
<td><span data-ttu-id="ce845-341">500,00</span><span class="sxs-lookup"><span data-stu-id="ce845-341">500.00</span></span></td>
<td><span data-ttu-id="ce845-342">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-342">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-343">CC099</span><span class="sxs-lookup"><span data-stu-id="ce845-343">CC099</span></span></td>
<td><span data-ttu-id="ce845-344">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="ce845-344">Default cost center</span></span></td>
<td><span data-ttu-id="ce845-345">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-345">10001</span></span></td>
<td><span data-ttu-id="ce845-346">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-346">Electricity</span></span></td>
<td><span data-ttu-id="ce845-347">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-347">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-348">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="ce845-348">-9,000.00</span></span></td>
<td><span data-ttu-id="ce845-349">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-349">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-350">CC001</span><span class="sxs-lookup"><span data-stu-id="ce845-350">CC001</span></span></td>
<td><span data-ttu-id="ce845-351">RH</span><span class="sxs-lookup"><span data-stu-id="ce845-351">HR</span></span></td>
<td><span data-ttu-id="ce845-352">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-352">10001</span></span></td>
<td><span data-ttu-id="ce845-353">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-353">Electricity</span></span></td>
<td><span data-ttu-id="ce845-354">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-354">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-355">1,285.71</span><span class="sxs-lookup"><span data-stu-id="ce845-355">1,285.71</span></span></td>
<td><span data-ttu-id="ce845-356">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-356">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-357">CC002</span><span class="sxs-lookup"><span data-stu-id="ce845-357">CC002</span></span></td>
<td><span data-ttu-id="ce845-358">Finanças</span><span class="sxs-lookup"><span data-stu-id="ce845-358">Finance</span></span></td>
<td><span data-ttu-id="ce845-359">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-359">10001</span></span></td>
<td><span data-ttu-id="ce845-360">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-360">Electricity</span></span></td>
<td><span data-ttu-id="ce845-361">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-361">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-362">7,714.29</span><span class="sxs-lookup"><span data-stu-id="ce845-362">7,714.29</span></span></td>
<td><span data-ttu-id="ce845-363">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-363">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ce845-364">Para obter informações detalhadas sobre bases de alocação e distribuição de custos, consulte a política de custo e as bases de alocação.</span><span class="sxs-lookup"><span data-stu-id="ce845-364">For detailed information about cost distribution and allocation bases, see Cost distribution policy and Allocation bases.</span></span> <span data-ttu-id="ce845-365">(Observe que este tópico não está incluído, mas estará em breve).</span><span class="sxs-lookup"><span data-stu-id="ce845-365">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="ce845-366">Etapa 3: Processar o cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="ce845-366">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="ce845-367">A taxa de custos indiretos é usada para cobrar um ou mais objetos de custos específicos.</span><span class="sxs-lookup"><span data-stu-id="ce845-367">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="ce845-368">O encargo se baseia em uma taxa de custo predeterminada e a magnitude da básica de alocação atribuída.</span><span class="sxs-lookup"><span data-stu-id="ce845-368">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="ce845-369">Defina a taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="ce845-369">Define the overhead rate</span></span>

<span data-ttu-id="ce845-370">O objeto de custo CC001 HR contribui para um conjunto de projetos internos.</span><span class="sxs-lookup"><span data-stu-id="ce845-370">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="ce845-371">Um membro de dimensão estatística que é chamado de projetos de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="ce845-371">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ce845-372">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-372">Cost object</span></span></th>
<th><span data-ttu-id="ce845-373">Horas</span><span class="sxs-lookup"><span data-stu-id="ce845-373">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-374">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="ce845-374">Proj 1</span></span></td>
<td><span data-ttu-id="ce845-375">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="ce845-375">Project 1</span></span></td>
<td><span data-ttu-id="ce845-376">3</span><span class="sxs-lookup"><span data-stu-id="ce845-376">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-377">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="ce845-377">Proj 2</span></span></td>
<td><span data-ttu-id="ce845-378">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="ce845-378">Project 2</span></span></td>
<td><span data-ttu-id="ce845-379">1</span><span class="sxs-lookup"><span data-stu-id="ce845-379">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ce845-380">Uma taxa de custo predeterminada da contribuição de projetos de custo foi definida.</span><span class="sxs-lookup"><span data-stu-id="ce845-380">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ce845-381">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-381">Cost object</span></span></th>
<th><span data-ttu-id="ce845-382">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-382">Cost element</span></span></th>
<th><span data-ttu-id="ce845-383">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-383">Cost behavior</span></span></th>
<th><span data-ttu-id="ce845-384">Unidades</span><span class="sxs-lookup"><span data-stu-id="ce845-384">Units</span></span></th>
<th><span data-ttu-id="ce845-385">Taxa</span><span class="sxs-lookup"><span data-stu-id="ce845-385">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-386">CC001</span><span class="sxs-lookup"><span data-stu-id="ce845-386">CC001</span></span></td>
<td><span data-ttu-id="ce845-387">RH</span><span class="sxs-lookup"><span data-stu-id="ce845-387">HR</span></span></td>
<td><span data-ttu-id="ce845-388">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-388">10001</span></span></td>
<td><span data-ttu-id="ce845-389">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-389">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-390">1</span><span class="sxs-lookup"><span data-stu-id="ce845-390">1</span></span></td>
<td><span data-ttu-id="ce845-391">10</span><span class="sxs-lookup"><span data-stu-id="ce845-391">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ce845-392">A tabela a seguir mostra o resultado quando projetos de RH são aplicados como base de alocação.</span><span class="sxs-lookup"><span data-stu-id="ce845-392">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ce845-393">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-393">Cost object</span></span></th>
<th><span data-ttu-id="ce845-394">Magnitude</span><span class="sxs-lookup"><span data-stu-id="ce845-394">Magnitude</span></span></th>
<th><span data-ttu-id="ce845-395">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-395">Cost element</span></span></th>
<th><span data-ttu-id="ce845-396">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="ce845-396">Allocation factor</span></span></th>
<th><span data-ttu-id="ce845-397">Valor</span><span class="sxs-lookup"><span data-stu-id="ce845-397">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-398">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="ce845-398">Proj 1</span></span></td>
<td><span data-ttu-id="ce845-399">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="ce845-399">Project 1</span></span></td>
<td><span data-ttu-id="ce845-400">3</span><span class="sxs-lookup"><span data-stu-id="ce845-400">3</span></span></td>
<td><span data-ttu-id="ce845-401">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-401">10001</span></span></td>
<td><span data-ttu-id="ce845-402">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="ce845-402">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="ce845-403">30,00</span><span class="sxs-lookup"><span data-stu-id="ce845-403">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-404">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="ce845-404">Proj 2</span></span></td>
<td><span data-ttu-id="ce845-405">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="ce845-405">Project 2</span></span></td>
<td><span data-ttu-id="ce845-406">1</span><span class="sxs-lookup"><span data-stu-id="ce845-406">1</span></span></td>
<td><span data-ttu-id="ce845-407">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-407">10001</span></span></td>
<td><span data-ttu-id="ce845-408">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="ce845-408">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="ce845-409">10,00</span><span class="sxs-lookup"><span data-stu-id="ce845-409">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="ce845-410">Diário</span><span class="sxs-lookup"><span data-stu-id="ce845-410">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ce845-411">Diário</span><span class="sxs-lookup"><span data-stu-id="ce845-411">Journal</span></span></th>
<th><span data-ttu-id="ce845-412">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="ce845-412">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ce845-413">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="ce845-413">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ce845-414">Versão</span><span class="sxs-lookup"><span data-stu-id="ce845-414">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-415">00003</span><span class="sxs-lookup"><span data-stu-id="ce845-415">00003</span></span></td>
<td><span data-ttu-id="ce845-416">Diário de cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="ce845-416">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="ce845-417">fiscal</span><span class="sxs-lookup"><span data-stu-id="ce845-417">Fiscal</span></span></td>
<td><span data-ttu-id="ce845-418">2017</span><span class="sxs-lookup"><span data-stu-id="ce845-418">2017</span></span></td>
<td><span data-ttu-id="ce845-419">Período 1</span><span class="sxs-lookup"><span data-stu-id="ce845-419">Period 1</span></span></td>
<td><span data-ttu-id="ce845-420">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="ce845-420">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="ce845-421">Entradas de diário (As entradas de diário para cálculo da taxa de custos indiretos)</span><span class="sxs-lookup"><span data-stu-id="ce845-421">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ce845-422">Data contábil</span><span class="sxs-lookup"><span data-stu-id="ce845-422">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ce845-423">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-423">Cost object</span></span></th>
<th><span data-ttu-id="ce845-424">Magnitude</span><span class="sxs-lookup"><span data-stu-id="ce845-424">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-425">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-425">January 31, 2017</span></span></td>
<td><span data-ttu-id="ce845-426">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="ce845-426">Proj 1</span></span></td>
<td><span data-ttu-id="ce845-427">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="ce845-427">Internal Proj 1</span></span></td>
<td><span data-ttu-id="ce845-428">3,00</span><span class="sxs-lookup"><span data-stu-id="ce845-428">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-429">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-429">January 31, 2017</span></span></td>
<td><span data-ttu-id="ce845-430">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="ce845-430">Proj 2</span></span></td>
<td><span data-ttu-id="ce845-431">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="ce845-431">Internal Proj 2</span></span></td>
<td><span data-ttu-id="ce845-432">1.00</span><span class="sxs-lookup"><span data-stu-id="ce845-432">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ce845-433">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-433">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ce845-434">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-434">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ce845-435">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-435">Cost element</span></span></th>
<th><span data-ttu-id="ce845-436">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-436">Cost behavior</span></span></th>
<th><span data-ttu-id="ce845-437">Valor</span><span class="sxs-lookup"><span data-stu-id="ce845-437">Amount</span></span></th>
<th><span data-ttu-id="ce845-438">Data contábil</span><span class="sxs-lookup"><span data-stu-id="ce845-438">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-439">CC0001</span><span class="sxs-lookup"><span data-stu-id="ce845-439">CC0001</span></span></td>
<td><span data-ttu-id="ce845-440">RH</span><span class="sxs-lookup"><span data-stu-id="ce845-440">HR</span></span></td>
<td><span data-ttu-id="ce845-441">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-441">10001</span></span></td>
<td><span data-ttu-id="ce845-442">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-442">Electricity</span></span></td>
<td><span data-ttu-id="ce845-443">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-443">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-444">-30,00</span><span class="sxs-lookup"><span data-stu-id="ce845-444">-30.00</span></span></td>
<td><span data-ttu-id="ce845-445">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-445">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-446">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="ce845-446">Proj 1</span></span></td>
<td><span data-ttu-id="ce845-447">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="ce845-447">Internal Proj 1</span></span></td>
<td><span data-ttu-id="ce845-448">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-448">10001</span></span></td>
<td><span data-ttu-id="ce845-449">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-449">Electricity</span></span></td>
<td><span data-ttu-id="ce845-450">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-450">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-451">30,00</span><span class="sxs-lookup"><span data-stu-id="ce845-451">30.00</span></span></td>
<td><span data-ttu-id="ce845-452">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-452">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-453">CC001</span><span class="sxs-lookup"><span data-stu-id="ce845-453">CC001</span></span></td>
<td><span data-ttu-id="ce845-454">RH</span><span class="sxs-lookup"><span data-stu-id="ce845-454">HR</span></span></td>
<td><span data-ttu-id="ce845-455">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-455">10001</span></span></td>
<td><span data-ttu-id="ce845-456">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-456">Electricity</span></span></td>
<td><span data-ttu-id="ce845-457">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-457">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-458">-10,00</span><span class="sxs-lookup"><span data-stu-id="ce845-458">-10.00</span></span></td>
<td><span data-ttu-id="ce845-459">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-459">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-460">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="ce845-460">Proj 2</span></span></td>
<td><span data-ttu-id="ce845-461">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="ce845-461">Internal Proj 2</span></span></td>
<td><span data-ttu-id="ce845-462">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-462">10001</span></span></td>
<td><span data-ttu-id="ce845-463">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-463">Electricity</span></span></td>
<td><span data-ttu-id="ce845-464">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-464">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-465">10,00</span><span class="sxs-lookup"><span data-stu-id="ce845-465">10.00</span></span></td>
<td><span data-ttu-id="ce845-466">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-466">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ce845-467">Para obter informações detalhadas sobre a política de taxa de custos indiretos, consulte a política de taxa de custos indiretos e as bases de alocação.</span><span class="sxs-lookup"><span data-stu-id="ce845-467">For detailed information about overhead rate policy, see Overhead rate policy and Allocation bases.</span></span> <span data-ttu-id="ce845-468">(Observe que este tópico não está incluído, mas estará em breve).</span><span class="sxs-lookup"><span data-stu-id="ce845-468">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="ce845-469">Etapa 4: Processar o cálculo de alocação de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-469">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="ce845-470">A alocação é usada para alocar o saldo de um objeto de custo a outros objetos de custo pela aplicação de uma base de alocação.</span><span class="sxs-lookup"><span data-stu-id="ce845-470">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="ce845-471">O Finance and Operations oferece suporte ao método de alocação recíproco.</span><span class="sxs-lookup"><span data-stu-id="ce845-471">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="ce845-472">No método de alocação recíproco, os serviços mútuos que os objetos de custo auxiliar trocam são totalmente reconhecidos.</span><span class="sxs-lookup"><span data-stu-id="ce845-472">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="ce845-473">O sistema determina automaticamente a ordem correta realizar as alocações.</span><span class="sxs-lookup"><span data-stu-id="ce845-473">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="ce845-474">O saldo de um objeto de custo é alocado por uma base de alocação única.</span><span class="sxs-lookup"><span data-stu-id="ce845-474">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="ce845-475">As alocações entre as dimensões de objetos de custo e os respectivos membros são suportadas.</span><span class="sxs-lookup"><span data-stu-id="ce845-475">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="ce845-476">A ordem de alocação é controlada pela unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="ce845-476">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="ce845-477">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="ce845-477">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="ce845-478">Defina a alocação de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-478">Define the cost allocation</span></span>

<span data-ttu-id="ce845-479">Aqui está um exemplo simples que explica como você pode rastrear o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="ce845-479">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="ce845-480">O objeto de custo previsto CC001 HR contribui a vários objetos de custo previsto.</span><span class="sxs-lookup"><span data-stu-id="ce845-480">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="ce845-481">Um membro de dimensão estatística que é chamado de serviços de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="ce845-481">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ce845-482">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-482">Cost object</span></span></th>
<th><span data-ttu-id="ce845-483">Serviços de RH</span><span class="sxs-lookup"><span data-stu-id="ce845-483">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-484">CC002</span><span class="sxs-lookup"><span data-stu-id="ce845-484">CC002</span></span></td>
<td><span data-ttu-id="ce845-485">Finanças</span><span class="sxs-lookup"><span data-stu-id="ce845-485">Finance</span></span></td>
<td><span data-ttu-id="ce845-486">35</span><span class="sxs-lookup"><span data-stu-id="ce845-486">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-487">CC003</span><span class="sxs-lookup"><span data-stu-id="ce845-487">CC003</span></span></td>
<td><span data-ttu-id="ce845-488">Montagem</span><span class="sxs-lookup"><span data-stu-id="ce845-488">Assembly</span></span></td>
<td><span data-ttu-id="ce845-489">55</span><span class="sxs-lookup"><span data-stu-id="ce845-489">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-490">CC004</span><span class="sxs-lookup"><span data-stu-id="ce845-490">CC004</span></span></td>
<td><span data-ttu-id="ce845-491">Embalagem</span><span class="sxs-lookup"><span data-stu-id="ce845-491">Packaging</span></span></td>
<td><span data-ttu-id="ce845-492">10</span><span class="sxs-lookup"><span data-stu-id="ce845-492">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ce845-493">O objeto de custo CC002 Finanças contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="ce845-493">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="ce845-494">Um membro de dimensão estatística que é chamado de serviços de Finanças foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="ce845-494">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ce845-495">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-495">Cost object</span></span></th>
<th><span data-ttu-id="ce845-496">Serviços financeiros</span><span class="sxs-lookup"><span data-stu-id="ce845-496">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-497">CC003</span><span class="sxs-lookup"><span data-stu-id="ce845-497">CC003</span></span></td>
<td><span data-ttu-id="ce845-498">Montagem</span><span class="sxs-lookup"><span data-stu-id="ce845-498">Assembly</span></span></td>
<td><span data-ttu-id="ce845-499">65</span><span class="sxs-lookup"><span data-stu-id="ce845-499">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-500">CC004</span><span class="sxs-lookup"><span data-stu-id="ce845-500">CC004</span></span></td>
<td><span data-ttu-id="ce845-501">Embalagem</span><span class="sxs-lookup"><span data-stu-id="ce845-501">Packaging</span></span></td>
<td><span data-ttu-id="ce845-502">35</span><span class="sxs-lookup"><span data-stu-id="ce845-502">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ce845-503">O objeto de custo CC003 Montagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="ce845-503">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="ce845-504">Um membro de dimensão estatística que é chamado de serviços de Montagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="ce845-504">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ce845-505">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-505">Cost object</span></span></th>
<th><span data-ttu-id="ce845-506">Serviços de montagem (horas)</span><span class="sxs-lookup"><span data-stu-id="ce845-506">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-507">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="ce845-507">Prod 1</span></span></td>
<td><span data-ttu-id="ce845-508">Produto 1</span><span class="sxs-lookup"><span data-stu-id="ce845-508">Product 1</span></span></td>
<td><span data-ttu-id="ce845-509">60</span><span class="sxs-lookup"><span data-stu-id="ce845-509">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-510">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="ce845-510">Prod 2</span></span></td>
<td><span data-ttu-id="ce845-511">Produto 2</span><span class="sxs-lookup"><span data-stu-id="ce845-511">Product 2</span></span></td>
<td><span data-ttu-id="ce845-512">20</span><span class="sxs-lookup"><span data-stu-id="ce845-512">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ce845-513">O objeto de custo CC004 Embalagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="ce845-513">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="ce845-514">Um membro de dimensão estatística que é chamado de serviços de Embalagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="ce845-514">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ce845-515">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-515">Cost object</span></span></th>
<th><span data-ttu-id="ce845-516">Serviços de embalagem (horas)</span><span class="sxs-lookup"><span data-stu-id="ce845-516">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-517">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="ce845-517">Prod 1</span></span></td>
<td><span data-ttu-id="ce845-518">Produto 1</span><span class="sxs-lookup"><span data-stu-id="ce845-518">Product 1</span></span></td>
<td><span data-ttu-id="ce845-519">80</span><span class="sxs-lookup"><span data-stu-id="ce845-519">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-520">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="ce845-520">Prod 2</span></span></td>
<td><span data-ttu-id="ce845-521">Produto 2</span><span class="sxs-lookup"><span data-stu-id="ce845-521">Product 2</span></span></td>
<td><span data-ttu-id="ce845-522">15</span><span class="sxs-lookup"><span data-stu-id="ce845-522">15</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ce845-523">**Observação:** No Finance and Operations, as medições estatísticas, como as horas de produção que um produto consome podem ser derivadas dos dados de origem.</span><span class="sxs-lookup"><span data-stu-id="ce845-523">**Note:** In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="ce845-524">Para obter informações mais detalhadas sobre provedores de medidas estatísticas, consulte o modelo do provedor de medida estatística.</span><span class="sxs-lookup"><span data-stu-id="ce845-524">For more detailed information about statistical measure providers, see Statistical measure provider template.</span></span> <span data-ttu-id="ce845-525">(Observe que este tópico não está concluído ainda, mas estará em breve.) A tabela a seguir mostra o resultado quando os serviços de RH são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="ce845-525">(Note that this topic isn't completed yet but is coming soon.) The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ce845-526">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-526">Cost object</span></span></th>
<th><span data-ttu-id="ce845-527">Magnitude</span><span class="sxs-lookup"><span data-stu-id="ce845-527">Magnitude</span></span></th>
<th><span data-ttu-id="ce845-528">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="ce845-528">Allocation factor</span></span></th>
<th><span data-ttu-id="ce845-529">Valor</span><span class="sxs-lookup"><span data-stu-id="ce845-529">Amount</span></span></th>
<th><span data-ttu-id="ce845-530">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-530">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-531">CC002</span><span class="sxs-lookup"><span data-stu-id="ce845-531">CC002</span></span></td>
<td><span data-ttu-id="ce845-532">Finanças</span><span class="sxs-lookup"><span data-stu-id="ce845-532">Finance</span></span></td>
<td><span data-ttu-id="ce845-533">35</span><span class="sxs-lookup"><span data-stu-id="ce845-533">35</span></span></td>
<td><span data-ttu-id="ce845-534">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="ce845-534">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="ce845-535">175.00</span><span class="sxs-lookup"><span data-stu-id="ce845-535">175.00</span></span></td>
<td><span data-ttu-id="ce845-536">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-536">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-537">CC003</span><span class="sxs-lookup"><span data-stu-id="ce845-537">CC003</span></span></td>
<td><span data-ttu-id="ce845-538">Montagem</span><span class="sxs-lookup"><span data-stu-id="ce845-538">Assembly</span></span></td>
<td><span data-ttu-id="ce845-539">55</span><span class="sxs-lookup"><span data-stu-id="ce845-539">55</span></span></td>
<td><span data-ttu-id="ce845-540">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="ce845-540">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="ce845-541">275.00</span><span class="sxs-lookup"><span data-stu-id="ce845-541">275.00</span></span></td>
<td><span data-ttu-id="ce845-542">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-542">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-543">CC004</span><span class="sxs-lookup"><span data-stu-id="ce845-543">CC004</span></span></td>
<td><span data-ttu-id="ce845-544">Embalagem</span><span class="sxs-lookup"><span data-stu-id="ce845-544">Packaging</span></span></td>
<td><span data-ttu-id="ce845-545">10</span><span class="sxs-lookup"><span data-stu-id="ce845-545">10</span></span></td>
<td><span data-ttu-id="ce845-546">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="ce845-546">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="ce845-547">50,00</span><span class="sxs-lookup"><span data-stu-id="ce845-547">50.00</span></span></td>
<td><span data-ttu-id="ce845-548">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-548">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-549">CC002</span><span class="sxs-lookup"><span data-stu-id="ce845-549">CC002</span></span></td>
<td><span data-ttu-id="ce845-550">Finanças</span><span class="sxs-lookup"><span data-stu-id="ce845-550">Finance</span></span></td>
<td><span data-ttu-id="ce845-551">35</span><span class="sxs-lookup"><span data-stu-id="ce845-551">35</span></span></td>
<td><span data-ttu-id="ce845-552">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="ce845-552">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="ce845-553">436.00</span><span class="sxs-lookup"><span data-stu-id="ce845-553">436.00</span></span></td>
<td><span data-ttu-id="ce845-554">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-554">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-555">CC003</span><span class="sxs-lookup"><span data-stu-id="ce845-555">CC003</span></span></td>
<td><span data-ttu-id="ce845-556">Montagem</span><span class="sxs-lookup"><span data-stu-id="ce845-556">Assembly</span></span></td>
<td><span data-ttu-id="ce845-557">55</span><span class="sxs-lookup"><span data-stu-id="ce845-557">55</span></span></td>
<td><span data-ttu-id="ce845-558">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="ce845-558">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="ce845-559">685.14</span><span class="sxs-lookup"><span data-stu-id="ce845-559">685.14</span></span></td>
<td><span data-ttu-id="ce845-560">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-560">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-561">CC004</span><span class="sxs-lookup"><span data-stu-id="ce845-561">CC004</span></span></td>
<td><span data-ttu-id="ce845-562">Embalagem</span><span class="sxs-lookup"><span data-stu-id="ce845-562">Packaging</span></span></td>
<td><span data-ttu-id="ce845-563">10</span><span class="sxs-lookup"><span data-stu-id="ce845-563">10</span></span></td>
<td><span data-ttu-id="ce845-564">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="ce845-564">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="ce845-565">124.57</span><span class="sxs-lookup"><span data-stu-id="ce845-565">124.57</span></span></td>
<td><span data-ttu-id="ce845-566">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-566">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ce845-567">A tabela a seguir mostra o resultado quando os serviços financeiros são aplicados como base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="ce845-567">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ce845-568">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-568">Cost object</span></span></th>
<th><span data-ttu-id="ce845-569">Magnitude</span><span class="sxs-lookup"><span data-stu-id="ce845-569">Magnitude</span></span></th>
<th><span data-ttu-id="ce845-570">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="ce845-570">Allocation factor</span></span></th>
<th><span data-ttu-id="ce845-571">Valor</span><span class="sxs-lookup"><span data-stu-id="ce845-571">Amount</span></span></th>
<th><span data-ttu-id="ce845-572">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-572">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-573">CC003</span><span class="sxs-lookup"><span data-stu-id="ce845-573">CC003</span></span></td>
<td><span data-ttu-id="ce845-574">Montagem</span><span class="sxs-lookup"><span data-stu-id="ce845-574">Assembly</span></span></td>
<td><span data-ttu-id="ce845-575">65</span><span class="sxs-lookup"><span data-stu-id="ce845-575">65</span></span></td>
<td><span data-ttu-id="ce845-576">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="ce845-576">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="ce845-577">438.75</span><span class="sxs-lookup"><span data-stu-id="ce845-577">438.75</span></span></td>
<td><span data-ttu-id="ce845-578">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-578">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-579">CC004</span><span class="sxs-lookup"><span data-stu-id="ce845-579">CC004</span></span></td>
<td><span data-ttu-id="ce845-580">Embalagem</span><span class="sxs-lookup"><span data-stu-id="ce845-580">Packaging</span></span></td>
<td><span data-ttu-id="ce845-581">35</span><span class="sxs-lookup"><span data-stu-id="ce845-581">35</span></span></td>
<td><span data-ttu-id="ce845-582">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="ce845-582">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="ce845-583">236.25</span><span class="sxs-lookup"><span data-stu-id="ce845-583">236.25</span></span></td>
<td><span data-ttu-id="ce845-584">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-584">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-585">CC003</span><span class="sxs-lookup"><span data-stu-id="ce845-585">CC003</span></span></td>
<td><span data-ttu-id="ce845-586">Montagem</span><span class="sxs-lookup"><span data-stu-id="ce845-586">Assembly</span></span></td>
<td><span data-ttu-id="ce845-587">65</span><span class="sxs-lookup"><span data-stu-id="ce845-587">65</span></span></td>
<td><span data-ttu-id="ce845-588">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="ce845-588">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="ce845-589">5,297.69</span><span class="sxs-lookup"><span data-stu-id="ce845-589">5,297.69</span></span></td>
<td><span data-ttu-id="ce845-590">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-590">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-591">CC004</span><span class="sxs-lookup"><span data-stu-id="ce845-591">CC004</span></span></td>
<td><span data-ttu-id="ce845-592">Embalagem</span><span class="sxs-lookup"><span data-stu-id="ce845-592">Packaging</span></span></td>
<td><span data-ttu-id="ce845-593">35</span><span class="sxs-lookup"><span data-stu-id="ce845-593">35</span></span></td>
<td><span data-ttu-id="ce845-594">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="ce845-594">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="ce845-595">2,852.60</span><span class="sxs-lookup"><span data-stu-id="ce845-595">2,852.60</span></span></td>
<td><span data-ttu-id="ce845-596">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-596">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ce845-597">A tabela a seguir mostra o resultado quando os serviços de Montagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="ce845-597">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ce845-598">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-598">Cost object</span></span></th>
<th><span data-ttu-id="ce845-599">Magnitude</span><span class="sxs-lookup"><span data-stu-id="ce845-599">Magnitude</span></span></th>
<th><span data-ttu-id="ce845-600">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="ce845-600">Allocation factor</span></span></th>
<th><span data-ttu-id="ce845-601">Valor</span><span class="sxs-lookup"><span data-stu-id="ce845-601">Amount</span></span></th>
<th><span data-ttu-id="ce845-602">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-602">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-603">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="ce845-603">Prod 1</span></span></td>
<td><span data-ttu-id="ce845-604">Produto 1</span><span class="sxs-lookup"><span data-stu-id="ce845-604">Product 1</span></span></td>
<td><span data-ttu-id="ce845-605">60</span><span class="sxs-lookup"><span data-stu-id="ce845-605">60</span></span></td>
<td><span data-ttu-id="ce845-606">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="ce845-606">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="ce845-607">535.31</span><span class="sxs-lookup"><span data-stu-id="ce845-607">535.31</span></span></td>
<td><span data-ttu-id="ce845-608">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-608">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-609">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="ce845-609">Prod 2</span></span></td>
<td><span data-ttu-id="ce845-610">Produto 2</span><span class="sxs-lookup"><span data-stu-id="ce845-610">Product 2</span></span></td>
<td><span data-ttu-id="ce845-611">20</span><span class="sxs-lookup"><span data-stu-id="ce845-611">20</span></span></td>
<td><span data-ttu-id="ce845-612">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="ce845-612">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="ce845-613">178.44</span><span class="sxs-lookup"><span data-stu-id="ce845-613">178.44</span></span></td>
<td><span data-ttu-id="ce845-614">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-614">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-615">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="ce845-615">Prod 1</span></span></td>
<td><span data-ttu-id="ce845-616">Produto 1</span><span class="sxs-lookup"><span data-stu-id="ce845-616">Product 1</span></span></td>
<td><span data-ttu-id="ce845-617">60</span><span class="sxs-lookup"><span data-stu-id="ce845-617">60</span></span></td>
<td><span data-ttu-id="ce845-618">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="ce845-618">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="ce845-619">4,487.12</span><span class="sxs-lookup"><span data-stu-id="ce845-619">4,487.12</span></span></td>
<td><span data-ttu-id="ce845-620">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-620">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-621">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="ce845-621">Prod 2</span></span></td>
<td><span data-ttu-id="ce845-622">Produto 2</span><span class="sxs-lookup"><span data-stu-id="ce845-622">Product 2</span></span></td>
<td><span data-ttu-id="ce845-623">20</span><span class="sxs-lookup"><span data-stu-id="ce845-623">20</span></span></td>
<td><span data-ttu-id="ce845-624">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="ce845-624">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="ce845-625">1,495.71</span><span class="sxs-lookup"><span data-stu-id="ce845-625">1,495.71</span></span></td>
<td><span data-ttu-id="ce845-626">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-626">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ce845-627">A tabela a seguir mostra o resultado quando os serviços de Embalagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="ce845-627">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ce845-628">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-628">Cost object</span></span></th>
<th><span data-ttu-id="ce845-629">Magnitude</span><span class="sxs-lookup"><span data-stu-id="ce845-629">Magnitude</span></span></th>
<th><span data-ttu-id="ce845-630">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="ce845-630">Allocation factor</span></span></th>
<th><span data-ttu-id="ce845-631">Valor</span><span class="sxs-lookup"><span data-stu-id="ce845-631">Amount</span></span></th>
<th><span data-ttu-id="ce845-632">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-632">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-633">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="ce845-633">Prod 1</span></span></td>
<td><span data-ttu-id="ce845-634">Produto 1</span><span class="sxs-lookup"><span data-stu-id="ce845-634">Product 1</span></span></td>
<td><span data-ttu-id="ce845-635">80</span><span class="sxs-lookup"><span data-stu-id="ce845-635">80</span></span></td>
<td><span data-ttu-id="ce845-636">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="ce845-636">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="ce845-637">241.05</span><span class="sxs-lookup"><span data-stu-id="ce845-637">241.05</span></span></td>
<td><span data-ttu-id="ce845-638">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-638">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-639">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="ce845-639">Prod 2</span></span></td>
<td><span data-ttu-id="ce845-640">Produto 2</span><span class="sxs-lookup"><span data-stu-id="ce845-640">Product 2</span></span></td>
<td><span data-ttu-id="ce845-641">15</span><span class="sxs-lookup"><span data-stu-id="ce845-641">15</span></span></td>
<td><span data-ttu-id="ce845-642">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="ce845-642">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="ce845-643">45.20</span><span class="sxs-lookup"><span data-stu-id="ce845-643">45.20</span></span></td>
<td><span data-ttu-id="ce845-644">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-644">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-645">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="ce845-645">Prod 1</span></span></td>
<td><span data-ttu-id="ce845-646">Produto 1</span><span class="sxs-lookup"><span data-stu-id="ce845-646">Product 1</span></span></td>
<td><span data-ttu-id="ce845-647">80</span><span class="sxs-lookup"><span data-stu-id="ce845-647">80</span></span></td>
<td><span data-ttu-id="ce845-648">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="ce845-648">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="ce845-649">2,507.09</span><span class="sxs-lookup"><span data-stu-id="ce845-649">2,507.09</span></span></td>
<td><span data-ttu-id="ce845-650">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-650">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-651">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="ce845-651">Prod 2</span></span></td>
<td><span data-ttu-id="ce845-652">Produto 2</span><span class="sxs-lookup"><span data-stu-id="ce845-652">Product 2</span></span></td>
<td><span data-ttu-id="ce845-653">15</span><span class="sxs-lookup"><span data-stu-id="ce845-653">15</span></span></td>
<td><span data-ttu-id="ce845-654">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="ce845-654">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="ce845-655">470.08</span><span class="sxs-lookup"><span data-stu-id="ce845-655">470.08</span></span></td>
<td><span data-ttu-id="ce845-656">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-656">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="ce845-657">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="ce845-657">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ce845-658">Diário</span><span class="sxs-lookup"><span data-stu-id="ce845-658">Journal</span></span></th>
<th><span data-ttu-id="ce845-659">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="ce845-659">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ce845-660">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="ce845-660">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ce845-661">Versão</span><span class="sxs-lookup"><span data-stu-id="ce845-661">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-662">00004</span><span class="sxs-lookup"><span data-stu-id="ce845-662">00004</span></span></td>
<td><span data-ttu-id="ce845-663">Diário de alocação de custos</span><span class="sxs-lookup"><span data-stu-id="ce845-663">Cost allocation journal</span></span></td>
<td><span data-ttu-id="ce845-664">fiscal</span><span class="sxs-lookup"><span data-stu-id="ce845-664">Fiscal</span></span></td>
<td><span data-ttu-id="ce845-665">2017</span><span class="sxs-lookup"><span data-stu-id="ce845-665">2017</span></span></td>
<td><span data-ttu-id="ce845-666">Período 1</span><span class="sxs-lookup"><span data-stu-id="ce845-666">Period 1</span></span></td>
<td><span data-ttu-id="ce845-667">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="ce845-667">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="ce845-668">Linhas do diário</span><span class="sxs-lookup"><span data-stu-id="ce845-668">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ce845-669">Data contábil</span><span class="sxs-lookup"><span data-stu-id="ce845-669">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ce845-670">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-670">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ce845-671">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-671">Cost element</span></span></th>
<th><span data-ttu-id="ce845-672">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-672">Cost behavior</span></span></th>
<th><span data-ttu-id="ce845-673">Valor</span><span class="sxs-lookup"><span data-stu-id="ce845-673">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-674">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-674">January 31, 2017</span></span></td>
<td><span data-ttu-id="ce845-675">CC001</span><span class="sxs-lookup"><span data-stu-id="ce845-675">CC001</span></span></td>
<td><span data-ttu-id="ce845-676">RH</span><span class="sxs-lookup"><span data-stu-id="ce845-676">HR</span></span></td>
<td><span data-ttu-id="ce845-677">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-677">10001</span></span></td>
<td><span data-ttu-id="ce845-678">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-678">Electricity</span></span></td>
<td><span data-ttu-id="ce845-679">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-679">Fixed cost</span></span></td>
<td><span data-ttu-id="ce845-680">500,00</span><span class="sxs-lookup"><span data-stu-id="ce845-680">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-681">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-681">January 31, 2017</span></span></td>
<td><span data-ttu-id="ce845-682">CC001</span><span class="sxs-lookup"><span data-stu-id="ce845-682">CC001</span></span></td>
<td><span data-ttu-id="ce845-683">RH</span><span class="sxs-lookup"><span data-stu-id="ce845-683">HR</span></span></td>
<td><span data-ttu-id="ce845-684">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-684">10001</span></span></td>
<td><span data-ttu-id="ce845-685">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-685">Electricity</span></span></td>
<td><span data-ttu-id="ce845-686">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-686">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-687">1,245.71</span><span class="sxs-lookup"><span data-stu-id="ce845-687">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-688">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-688">January 31, 2017</span></span></td>
<td><span data-ttu-id="ce845-689">CC002</span><span class="sxs-lookup"><span data-stu-id="ce845-689">CC002</span></span></td>
<td><span data-ttu-id="ce845-690">Finanças</span><span class="sxs-lookup"><span data-stu-id="ce845-690">Finance</span></span></td>
<td><span data-ttu-id="ce845-691">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-691">10001</span></span></td>
<td><span data-ttu-id="ce845-692">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-692">Electricity</span></span></td>
<td><span data-ttu-id="ce845-693">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-693">Fixed cost</span></span></td>
<td><span data-ttu-id="ce845-694">675.00</span><span class="sxs-lookup"><span data-stu-id="ce845-694">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-695">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-695">January 31, 2017</span></span></td>
<td><span data-ttu-id="ce845-696">CC002</span><span class="sxs-lookup"><span data-stu-id="ce845-696">CC002</span></span></td>
<td><span data-ttu-id="ce845-697">Finanças</span><span class="sxs-lookup"><span data-stu-id="ce845-697">Finance</span></span></td>
<td><span data-ttu-id="ce845-698">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-698">10001</span></span></td>
<td><span data-ttu-id="ce845-699">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-699">Electricity</span></span></td>
<td><span data-ttu-id="ce845-700">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-700">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-701">8,150.29</span><span class="sxs-lookup"><span data-stu-id="ce845-701">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-702">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-702">January 31, 2017</span></span></td>
<td><span data-ttu-id="ce845-703">CC003</span><span class="sxs-lookup"><span data-stu-id="ce845-703">CC003</span></span></td>
<td><span data-ttu-id="ce845-704">Montagem</span><span class="sxs-lookup"><span data-stu-id="ce845-704">Assembly</span></span></td>
<td><span data-ttu-id="ce845-705">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-705">10001</span></span></td>
<td><span data-ttu-id="ce845-706">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-706">Electricity</span></span></td>
<td><span data-ttu-id="ce845-707">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-707">Fixed cost</span></span></td>
<td><span data-ttu-id="ce845-708">713.75</span><span class="sxs-lookup"><span data-stu-id="ce845-708">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-709">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-709">January 31, 2017</span></span></td>
<td><span data-ttu-id="ce845-710">CC003</span><span class="sxs-lookup"><span data-stu-id="ce845-710">CC003</span></span></td>
<td><span data-ttu-id="ce845-711">Montagem</span><span class="sxs-lookup"><span data-stu-id="ce845-711">Assembly</span></span></td>
<td><span data-ttu-id="ce845-712">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-712">10001</span></span></td>
<td><span data-ttu-id="ce845-713">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-713">Electricity</span></span></td>
<td><span data-ttu-id="ce845-714">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-714">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-715">5,982.83</span><span class="sxs-lookup"><span data-stu-id="ce845-715">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-716">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-716">January 31, 2017</span></span></td>
<td><span data-ttu-id="ce845-717">CC003</span><span class="sxs-lookup"><span data-stu-id="ce845-717">CC003</span></span></td>
<td><span data-ttu-id="ce845-718">Embalagem</span><span class="sxs-lookup"><span data-stu-id="ce845-718">Packaging</span></span></td>
<td><span data-ttu-id="ce845-719">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-719">10001</span></span></td>
<td><span data-ttu-id="ce845-720">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-720">Electricity</span></span></td>
<td><span data-ttu-id="ce845-721">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-721">Fixed cost</span></span></td>
<td><span data-ttu-id="ce845-722">286.25</span><span class="sxs-lookup"><span data-stu-id="ce845-722">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-723">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-723">January 31, 2017</span></span></td>
<td><span data-ttu-id="ce845-724">CC003</span><span class="sxs-lookup"><span data-stu-id="ce845-724">CC003</span></span></td>
<td><span data-ttu-id="ce845-725">Embalagem</span><span class="sxs-lookup"><span data-stu-id="ce845-725">Packaging</span></span></td>
<td><span data-ttu-id="ce845-726">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-726">10001</span></span></td>
<td><span data-ttu-id="ce845-727">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-727">Electricity</span></span></td>
<td><span data-ttu-id="ce845-728">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-728">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-729">2,977.17</span><span class="sxs-lookup"><span data-stu-id="ce845-729">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-730">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-730">January 31, 2017</span></span></td>
<td><span data-ttu-id="ce845-731">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="ce845-731">Prod 1</span></span></td>
<td><span data-ttu-id="ce845-732">Produto 1</span><span class="sxs-lookup"><span data-stu-id="ce845-732">Product 1</span></span></td>
<td><span data-ttu-id="ce845-733">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-733">10001</span></span></td>
<td><span data-ttu-id="ce845-734">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-734">Electricity</span></span></td>
<td><span data-ttu-id="ce845-735">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-735">Fixed cost</span></span></td>
<td><span data-ttu-id="ce845-736">776.36</span><span class="sxs-lookup"><span data-stu-id="ce845-736">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-737">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-737">January 31, 2017</span></span></td>
<td><span data-ttu-id="ce845-738">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="ce845-738">Prod 1</span></span></td>
<td><span data-ttu-id="ce845-739">Produto 1</span><span class="sxs-lookup"><span data-stu-id="ce845-739">Product 1</span></span></td>
<td><span data-ttu-id="ce845-740">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-740">10001</span></span></td>
<td><span data-ttu-id="ce845-741">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-741">Electricity</span></span></td>
<td><span data-ttu-id="ce845-742">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-742">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-743">6,994.21</span><span class="sxs-lookup"><span data-stu-id="ce845-743">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-744">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-744">January 31, 2017</span></span></td>
<td><span data-ttu-id="ce845-745">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="ce845-745">Prod 2</span></span></td>
<td><span data-ttu-id="ce845-746">Produto 1</span><span class="sxs-lookup"><span data-stu-id="ce845-746">Product 1</span></span></td>
<td><span data-ttu-id="ce845-747">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-747">10001</span></span></td>
<td><span data-ttu-id="ce845-748">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-748">Electricity</span></span></td>
<td><span data-ttu-id="ce845-749">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-749">Fixed cost</span></span></td>
<td><span data-ttu-id="ce845-750">223.64</span><span class="sxs-lookup"><span data-stu-id="ce845-750">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-751">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-751">January 31, 2017</span></span></td>
<td><span data-ttu-id="ce845-752">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="ce845-752">Prod 2</span></span></td>
<td><span data-ttu-id="ce845-753">Produto 1</span><span class="sxs-lookup"><span data-stu-id="ce845-753">Product 1</span></span></td>
<td><span data-ttu-id="ce845-754">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-754">10001</span></span></td>
<td><span data-ttu-id="ce845-755">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-755">Electricity</span></span></td>
<td><span data-ttu-id="ce845-756">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-756">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-757">1,965.79</span><span class="sxs-lookup"><span data-stu-id="ce845-757">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ce845-758">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-758">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ce845-759">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-759">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ce845-760">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-760">Cost element</span></span></th>
<th><span data-ttu-id="ce845-761">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-761">Cost behavior</span></span></th>
<th><span data-ttu-id="ce845-762">Valor</span><span class="sxs-lookup"><span data-stu-id="ce845-762">Amount</span></span></th>
<th><span data-ttu-id="ce845-763">Data contábil</span><span class="sxs-lookup"><span data-stu-id="ce845-763">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ce845-764">CC001</span><span class="sxs-lookup"><span data-stu-id="ce845-764">CC001</span></span></td>
<td><span data-ttu-id="ce845-765">RH</span><span class="sxs-lookup"><span data-stu-id="ce845-765">HR</span></span></td>
<td><span data-ttu-id="ce845-766">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-766">10001</span></span></td>
<td><span data-ttu-id="ce845-767">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-767">Electricity</span></span></td>
<td><span data-ttu-id="ce845-768">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-768">Fixed cost</span></span></td>
<td><span data-ttu-id="ce845-769">-500,00</span><span class="sxs-lookup"><span data-stu-id="ce845-769">-500.00</span></span></td>
<td><span data-ttu-id="ce845-770">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-770">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-771">CC002</span><span class="sxs-lookup"><span data-stu-id="ce845-771">CC002</span></span></td>
<td><span data-ttu-id="ce845-772">Finanças</span><span class="sxs-lookup"><span data-stu-id="ce845-772">Finance</span></span></td>
<td><span data-ttu-id="ce845-773">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-773">10001</span></span></td>
<td><span data-ttu-id="ce845-774">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-774">Electricity</span></span></td>
<td><span data-ttu-id="ce845-775">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-775">Fixed cost</span></span></td>
<td><span data-ttu-id="ce845-776">175.00</span><span class="sxs-lookup"><span data-stu-id="ce845-776">175.00</span></span></td>
<td><span data-ttu-id="ce845-777">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-777">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-778">CC003</span><span class="sxs-lookup"><span data-stu-id="ce845-778">CC003</span></span></td>
<td><span data-ttu-id="ce845-779">Montagem</span><span class="sxs-lookup"><span data-stu-id="ce845-779">Assembly</span></span></td>
<td><span data-ttu-id="ce845-780">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-780">10001</span></span></td>
<td><span data-ttu-id="ce845-781">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-781">Electricity</span></span></td>
<td><span data-ttu-id="ce845-782">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-782">Fixed cost</span></span></td>
<td><span data-ttu-id="ce845-783">275.00</span><span class="sxs-lookup"><span data-stu-id="ce845-783">275.00</span></span></td>
<td><span data-ttu-id="ce845-784">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-784">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-785">CC004</span><span class="sxs-lookup"><span data-stu-id="ce845-785">CC004</span></span></td>
<td><span data-ttu-id="ce845-786">Embalagem</span><span class="sxs-lookup"><span data-stu-id="ce845-786">Packaging</span></span></td>
<td><span data-ttu-id="ce845-787">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-787">10001</span></span></td>
<td><span data-ttu-id="ce845-788">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-788">Electricity</span></span></td>
<td><span data-ttu-id="ce845-789">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-789">Fixed cost</span></span></td>
<td><span data-ttu-id="ce845-790">50,00</span><span class="sxs-lookup"><span data-stu-id="ce845-790">50,00</span></span></td>
<td><span data-ttu-id="ce845-791">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-791">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-792">CC001</span><span class="sxs-lookup"><span data-stu-id="ce845-792">CC001</span></span></td>
<td><span data-ttu-id="ce845-793">RH</span><span class="sxs-lookup"><span data-stu-id="ce845-793">HR</span></span></td>
<td><span data-ttu-id="ce845-794">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-794">10001</span></span></td>
<td><span data-ttu-id="ce845-795">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-795">Electricity</span></span></td>
<td><span data-ttu-id="ce845-796">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-796">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-797">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="ce845-797">-1,245.71</span></span></td>
<td><span data-ttu-id="ce845-798">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-798">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-799">CC002</span><span class="sxs-lookup"><span data-stu-id="ce845-799">CC002</span></span></td>
<td><span data-ttu-id="ce845-800">Finanças</span><span class="sxs-lookup"><span data-stu-id="ce845-800">Finance</span></span></td>
<td><span data-ttu-id="ce845-801">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-801">10001</span></span></td>
<td><span data-ttu-id="ce845-802">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-802">Electricity</span></span></td>
<td><span data-ttu-id="ce845-803">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-803">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-804">436.00</span><span class="sxs-lookup"><span data-stu-id="ce845-804">436.00</span></span></td>
<td><span data-ttu-id="ce845-805">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-805">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-806">CC003</span><span class="sxs-lookup"><span data-stu-id="ce845-806">CC003</span></span></td>
<td><span data-ttu-id="ce845-807">Montagem</span><span class="sxs-lookup"><span data-stu-id="ce845-807">Assembly</span></span></td>
<td><span data-ttu-id="ce845-808">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-808">10001</span></span></td>
<td><span data-ttu-id="ce845-809">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-809">Electricity</span></span></td>
<td><span data-ttu-id="ce845-810">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-810">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-811">685.14</span><span class="sxs-lookup"><span data-stu-id="ce845-811">685.14</span></span></td>
<td><span data-ttu-id="ce845-812">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-812">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-813">CC004</span><span class="sxs-lookup"><span data-stu-id="ce845-813">CC004</span></span></td>
<td><span data-ttu-id="ce845-814">Embalagem</span><span class="sxs-lookup"><span data-stu-id="ce845-814">Packaging</span></span></td>
<td><span data-ttu-id="ce845-815">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-815">10001</span></span></td>
<td><span data-ttu-id="ce845-816">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-816">Electricity</span></span></td>
<td><span data-ttu-id="ce845-817">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-817">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-818">124.57</span><span class="sxs-lookup"><span data-stu-id="ce845-818">124.57</span></span></td>
<td><span data-ttu-id="ce845-819">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-819">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-820">CC002</span><span class="sxs-lookup"><span data-stu-id="ce845-820">CC002</span></span></td>
<td><span data-ttu-id="ce845-821">Finanças</span><span class="sxs-lookup"><span data-stu-id="ce845-821">Finance</span></span></td>
<td><span data-ttu-id="ce845-822">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-822">10001</span></span></td>
<td><span data-ttu-id="ce845-823">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-823">Electricity</span></span></td>
<td><span data-ttu-id="ce845-824">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-824">Fixed cost</span></span></td>
<td><span data-ttu-id="ce845-825">-675,00</span><span class="sxs-lookup"><span data-stu-id="ce845-825">-675.00</span></span></td>
<td><span data-ttu-id="ce845-826">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-826">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-827">CC003</span><span class="sxs-lookup"><span data-stu-id="ce845-827">CC003</span></span></td>
<td><span data-ttu-id="ce845-828">Montagem</span><span class="sxs-lookup"><span data-stu-id="ce845-828">Assembly</span></span></td>
<td><span data-ttu-id="ce845-829">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-829">10001</span></span></td>
<td><span data-ttu-id="ce845-830">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-830">Electricity</span></span></td>
<td><span data-ttu-id="ce845-831">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-831">Fixed cost</span></span></td>
<td><span data-ttu-id="ce845-832">438.75</span><span class="sxs-lookup"><span data-stu-id="ce845-832">438.75</span></span></td>
<td><span data-ttu-id="ce845-833">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-833">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-834">CC004</span><span class="sxs-lookup"><span data-stu-id="ce845-834">CC004</span></span></td>
<td><span data-ttu-id="ce845-835">Embalagem</span><span class="sxs-lookup"><span data-stu-id="ce845-835">Packaging</span></span></td>
<td><span data-ttu-id="ce845-836">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-836">10001</span></span></td>
<td><span data-ttu-id="ce845-837">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-837">Electricity</span></span></td>
<td><span data-ttu-id="ce845-838">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-838">Fixed cost</span></span></td>
<td><span data-ttu-id="ce845-839">236.25</span><span class="sxs-lookup"><span data-stu-id="ce845-839">236.25</span></span></td>
<td><span data-ttu-id="ce845-840">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-840">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-841">CC002</span><span class="sxs-lookup"><span data-stu-id="ce845-841">CC002</span></span></td>
<td><span data-ttu-id="ce845-842">Finanças</span><span class="sxs-lookup"><span data-stu-id="ce845-842">Finance</span></span></td>
<td><span data-ttu-id="ce845-843">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-843">10001</span></span></td>
<td><span data-ttu-id="ce845-844">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-844">Electricity</span></span></td>
<td><span data-ttu-id="ce845-845">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-845">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-846">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="ce845-846">-8,150.29</span></span></td>
<td><span data-ttu-id="ce845-847">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-847">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-848">CC003</span><span class="sxs-lookup"><span data-stu-id="ce845-848">CC003</span></span></td>
<td><span data-ttu-id="ce845-849">Montagem</span><span class="sxs-lookup"><span data-stu-id="ce845-849">Assembly</span></span></td>
<td><span data-ttu-id="ce845-850">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-850">10001</span></span></td>
<td><span data-ttu-id="ce845-851">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-851">Electricity</span></span></td>
<td><span data-ttu-id="ce845-852">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-852">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-853">5,297.69</span><span class="sxs-lookup"><span data-stu-id="ce845-853">5,297.69</span></span></td>
<td><span data-ttu-id="ce845-854">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-854">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-855">CC004</span><span class="sxs-lookup"><span data-stu-id="ce845-855">CC004</span></span></td>
<td><span data-ttu-id="ce845-856">Embalagem</span><span class="sxs-lookup"><span data-stu-id="ce845-856">Packaging</span></span></td>
<td><span data-ttu-id="ce845-857">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-857">10001</span></span></td>
<td><span data-ttu-id="ce845-858">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-858">Electricity</span></span></td>
<td><span data-ttu-id="ce845-859">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-859">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-860">2,852.60</span><span class="sxs-lookup"><span data-stu-id="ce845-860">2,852.60</span></span></td>
<td><span data-ttu-id="ce845-861">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-861">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-862">CC003</span><span class="sxs-lookup"><span data-stu-id="ce845-862">CC003</span></span></td>
<td><span data-ttu-id="ce845-863">Montagem</span><span class="sxs-lookup"><span data-stu-id="ce845-863">Assembly</span></span></td>
<td><span data-ttu-id="ce845-864">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-864">10001</span></span></td>
<td><span data-ttu-id="ce845-865">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-865">Electricity</span></span></td>
<td><span data-ttu-id="ce845-866">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-866">Fixed cost</span></span></td>
<td><span data-ttu-id="ce845-867">-713,75</span><span class="sxs-lookup"><span data-stu-id="ce845-867">-713.75</span></span></td>
<td><span data-ttu-id="ce845-868">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-868">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-869">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="ce845-869">Prod 1</span></span></td>
<td><span data-ttu-id="ce845-870">Produto 1</span><span class="sxs-lookup"><span data-stu-id="ce845-870">Product 1</span></span></td>
<td><span data-ttu-id="ce845-871">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-871">10001</span></span></td>
<td><span data-ttu-id="ce845-872">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-872">Electricity</span></span></td>
<td><span data-ttu-id="ce845-873">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-873">Fixed cost</span></span></td>
<td><span data-ttu-id="ce845-874">535.31</span><span class="sxs-lookup"><span data-stu-id="ce845-874">535.31</span></span></td>
<td><span data-ttu-id="ce845-875">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-875">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-876">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="ce845-876">Prod 2</span></span></td>
<td><span data-ttu-id="ce845-877">Produto 2</span><span class="sxs-lookup"><span data-stu-id="ce845-877">Product 2</span></span></td>
<td><span data-ttu-id="ce845-878">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-878">10001</span></span></td>
<td><span data-ttu-id="ce845-879">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-879">Electricity</span></span></td>
<td><span data-ttu-id="ce845-880">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-880">Fixed cost</span></span></td>
<td><span data-ttu-id="ce845-881">178.44</span><span class="sxs-lookup"><span data-stu-id="ce845-881">178.44</span></span></td>
<td><span data-ttu-id="ce845-882">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-882">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-883">CC003</span><span class="sxs-lookup"><span data-stu-id="ce845-883">CC003</span></span></td>
<td><span data-ttu-id="ce845-884">Montagem</span><span class="sxs-lookup"><span data-stu-id="ce845-884">Assembly</span></span></td>
<td><span data-ttu-id="ce845-885">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-885">10001</span></span></td>
<td><span data-ttu-id="ce845-886">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-886">Electricity</span></span></td>
<td><span data-ttu-id="ce845-887">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-887">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-888">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="ce845-888">-5,982.83</span></span></td>
<td><span data-ttu-id="ce845-889">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-889">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-890">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="ce845-890">Prod 1</span></span></td>
<td><span data-ttu-id="ce845-891">Produto 1</span><span class="sxs-lookup"><span data-stu-id="ce845-891">Product 1</span></span></td>
<td><span data-ttu-id="ce845-892">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-892">10001</span></span></td>
<td><span data-ttu-id="ce845-893">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-893">Electricity</span></span></td>
<td><span data-ttu-id="ce845-894">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-894">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-895">4,487.12</span><span class="sxs-lookup"><span data-stu-id="ce845-895">4,487.12</span></span></td>
<td><span data-ttu-id="ce845-896">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-896">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-897">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="ce845-897">Prod 2</span></span></td>
<td><span data-ttu-id="ce845-898">Produto 2</span><span class="sxs-lookup"><span data-stu-id="ce845-898">Product 2</span></span></td>
<td><span data-ttu-id="ce845-899">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-899">10001</span></span></td>
<td><span data-ttu-id="ce845-900">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-900">Electricity</span></span></td>
<td><span data-ttu-id="ce845-901">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-901">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-902">1,495.71</span><span class="sxs-lookup"><span data-stu-id="ce845-902">1,495.71</span></span></td>
<td><span data-ttu-id="ce845-903">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-903">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-904">CC003</span><span class="sxs-lookup"><span data-stu-id="ce845-904">CC003</span></span></td>
<td><span data-ttu-id="ce845-905">Montagem</span><span class="sxs-lookup"><span data-stu-id="ce845-905">Assembly</span></span></td>
<td><span data-ttu-id="ce845-906">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-906">10001</span></span></td>
<td><span data-ttu-id="ce845-907">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-907">Electricity</span></span></td>
<td><span data-ttu-id="ce845-908">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-908">Fixed cost</span></span></td>
<td><span data-ttu-id="ce845-909">-286,25</span><span class="sxs-lookup"><span data-stu-id="ce845-909">-286.25</span></span></td>
<td><span data-ttu-id="ce845-910">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-910">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-911">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="ce845-911">Prod 1</span></span></td>
<td><span data-ttu-id="ce845-912">Produto 1</span><span class="sxs-lookup"><span data-stu-id="ce845-912">Product 1</span></span></td>
<td><span data-ttu-id="ce845-913">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-913">10001</span></span></td>
<td><span data-ttu-id="ce845-914">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-914">Electricity</span></span></td>
<td><span data-ttu-id="ce845-915">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-915">Fixed cost</span></span></td>
<td><span data-ttu-id="ce845-916">241.05</span><span class="sxs-lookup"><span data-stu-id="ce845-916">241.05</span></span></td>
<td><span data-ttu-id="ce845-917">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-917">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-918">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="ce845-918">Prod 2</span></span></td>
<td><span data-ttu-id="ce845-919">Produto 2</span><span class="sxs-lookup"><span data-stu-id="ce845-919">Product 2</span></span></td>
<td><span data-ttu-id="ce845-920">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-920">10001</span></span></td>
<td><span data-ttu-id="ce845-921">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-921">Electricity</span></span></td>
<td><span data-ttu-id="ce845-922">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-922">Fixed cost</span></span></td>
<td><span data-ttu-id="ce845-923">45.20</span><span class="sxs-lookup"><span data-stu-id="ce845-923">45.20</span></span></td>
<td><span data-ttu-id="ce845-924">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-924">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-925">CC003</span><span class="sxs-lookup"><span data-stu-id="ce845-925">CC003</span></span></td>
<td><span data-ttu-id="ce845-926">Montagem</span><span class="sxs-lookup"><span data-stu-id="ce845-926">Assembly</span></span></td>
<td><span data-ttu-id="ce845-927">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-927">10001</span></span></td>
<td><span data-ttu-id="ce845-928">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-928">Electricity</span></span></td>
<td><span data-ttu-id="ce845-929">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-929">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-930">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="ce845-930">-2,977.17</span></span></td>
<td><span data-ttu-id="ce845-931">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-931">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-932">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="ce845-932">Prod 1</span></span></td>
<td><span data-ttu-id="ce845-933">Produto 1</span><span class="sxs-lookup"><span data-stu-id="ce845-933">Product 1</span></span></td>
<td><span data-ttu-id="ce845-934">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-934">10001</span></span></td>
<td><span data-ttu-id="ce845-935">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-935">Electricity</span></span></td>
<td><span data-ttu-id="ce845-936">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-936">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-937">2,507.09</span><span class="sxs-lookup"><span data-stu-id="ce845-937">2,507.09</span></span></td>
<td><span data-ttu-id="ce845-938">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-938">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ce845-939">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="ce845-939">Prod 2</span></span></td>
<td><span data-ttu-id="ce845-940">Produto 2</span><span class="sxs-lookup"><span data-stu-id="ce845-940">Product 2</span></span></td>
<td><span data-ttu-id="ce845-941">10001</span><span class="sxs-lookup"><span data-stu-id="ce845-941">10001</span></span></td>
<td><span data-ttu-id="ce845-942">eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-942">Electricity</span></span></td>
<td><span data-ttu-id="ce845-943">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-943">Variable cost</span></span></td>
<td><span data-ttu-id="ce845-944">470.08</span><span class="sxs-lookup"><span data-stu-id="ce845-944">470.08</span></span></td>
<td><span data-ttu-id="ce845-945">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="ce845-945">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="ce845-946">Conclusão</span><span class="sxs-lookup"><span data-stu-id="ce845-946">Conclusion</span></span>
<span data-ttu-id="ce845-947">Na contabilidade financeira, um custo de 10,000.00 para a eletricidade é lançado para um ID fictício de centro de custos.</span><span class="sxs-lookup"><span data-stu-id="ce845-947">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="ce845-948">Portanto, os contadores de custo saberão que esses custos devem ser alocados.</span><span class="sxs-lookup"><span data-stu-id="ce845-948">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="ce845-949">Na contabilização de custo, os custos fluem nas unidades organizacionais e nos níveis, com base nas políticas e regras que são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="ce845-949">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="ce845-950">Cada custo foi associado a uma base de alocação que fornece a melhor apuração para a alocação de custos.</span><span class="sxs-lookup"><span data-stu-id="ce845-950">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="ce845-951">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-951">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="ce845-952">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="ce845-952">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="ce845-953">Total</span><span class="sxs-lookup"><span data-stu-id="ce845-953">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="ce845-954">CC099</span><span class="sxs-lookup"><span data-stu-id="ce845-954">CC099</span></span></th>
<th><span data-ttu-id="ce845-955">CC001</span><span class="sxs-lookup"><span data-stu-id="ce845-955">CC001</span></span></th>
<th><span data-ttu-id="ce845-956">CC002</span><span class="sxs-lookup"><span data-stu-id="ce845-956">CC002</span></span></th>
<th><span data-ttu-id="ce845-957">CC003</span><span class="sxs-lookup"><span data-stu-id="ce845-957">CC003</span></span></th>
<th><span data-ttu-id="ce845-958">CC004</span><span class="sxs-lookup"><span data-stu-id="ce845-958">CC004</span></span></th>
<th><span data-ttu-id="ce845-959">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="ce845-959">Proj 1</span></span></th>
<th><span data-ttu-id="ce845-960">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="ce845-960">Proj 2</span></span></th>
<th><span data-ttu-id="ce845-961">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="ce845-961">Prod 1</span></span></th>
<th><span data-ttu-id="ce845-962">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="ce845-962">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="ce845-963">10001 Eletricidade</span><span class="sxs-lookup"><span data-stu-id="ce845-963">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="ce845-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-965"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="ce845-965"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-966"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="ce845-966"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-967"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="ce845-967"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="ce845-968"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="ce845-968"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-969"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="ce845-969"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-970"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="ce845-970"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-971"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="ce845-971"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-972"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="ce845-972"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="ce845-973">Não classificado</span><span class="sxs-lookup"><span data-stu-id="ce845-973">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-974">0,00</span><span class="sxs-lookup"><span data-stu-id="ce845-974">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="ce845-975">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="ce845-975">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-976">0,00</span><span class="sxs-lookup"><span data-stu-id="ce845-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-977">0,00</span><span class="sxs-lookup"><span data-stu-id="ce845-977">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-978">0,00</span><span class="sxs-lookup"><span data-stu-id="ce845-978">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-979">0,00</span><span class="sxs-lookup"><span data-stu-id="ce845-979">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-980">0,00</span><span class="sxs-lookup"><span data-stu-id="ce845-980">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="ce845-981">776.36</span><span class="sxs-lookup"><span data-stu-id="ce845-981">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-982">223.64</span><span class="sxs-lookup"><span data-stu-id="ce845-982">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-983"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="ce845-983"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="ce845-984">Custo variável</span><span class="sxs-lookup"><span data-stu-id="ce845-984">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-985">000</span><span class="sxs-lookup"><span data-stu-id="ce845-985">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-986">0,00</span><span class="sxs-lookup"><span data-stu-id="ce845-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-987">0,00</span><span class="sxs-lookup"><span data-stu-id="ce845-987">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-988">0,00</span><span class="sxs-lookup"><span data-stu-id="ce845-988">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-989">0,00</span><span class="sxs-lookup"><span data-stu-id="ce845-989">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-990">30,00</span><span class="sxs-lookup"><span data-stu-id="ce845-990">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-991">10,00</span><span class="sxs-lookup"><span data-stu-id="ce845-991">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-992">6,994.21</span><span class="sxs-lookup"><span data-stu-id="ce845-992">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-993">1,965.79</span><span class="sxs-lookup"><span data-stu-id="ce845-993">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ce845-994"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="ce845-994"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="ce845-995">Esse tópico mostra como um elemento de custo principal, 10001 Eletricidade flui pelos objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="ce845-995">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="ce845-996">Portanto, esse custo geral indireto é alocado no nível mais baixo na organização.</span><span class="sxs-lookup"><span data-stu-id="ce845-996">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="ce845-997">Em outras palavras, os objetos de custo no nível mais baixo assumem o custo.</span><span class="sxs-lookup"><span data-stu-id="ce845-997">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="ce845-998">Se você exigir um fluxo visual de custo entre objetos de custo, é possível usar as regras de política de acúmulo de custos para visualizar o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="ce845-998">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="ce845-999">Para obter informações mais detalhadas, consulte a política de acúmulo de custos.</span><span class="sxs-lookup"><span data-stu-id="ce845-999">For more detailed information, see Cost roll-up policy.</span></span> <span data-ttu-id="ce845-1000">(Observe que este tópico não está incluído, mas estará em breve).</span><span class="sxs-lookup"><span data-stu-id="ce845-1000">(Note that this topic isn't competed yet but is coming soon.)</span></span>




