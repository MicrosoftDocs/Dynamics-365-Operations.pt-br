---
title: Cálculo de custos indiretos
description: Este tópico descreve processos comuns para calcular e alocar os custos gerais indiretos.
author: AndersGirke
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation, CAMOverheadRateCalculationJournalEntry, CAMFormulaAllocationBase
audience: Application User
ms.reviewer: roschlom
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 8dc312e66dc666ac6c23bac6b705ffc7893fd06b
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187988"
---
# <a name="overhead-calculation"></a><span data-ttu-id="743ba-103">Cálculo de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="743ba-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="743ba-104">Este tópico descreve processos comuns para calcular e alocar os custos gerais indiretos.</span><span class="sxs-lookup"><span data-stu-id="743ba-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

## <a name="term-definition"></a><span data-ttu-id="743ba-105">Definição de termo</span><span class="sxs-lookup"><span data-stu-id="743ba-105">Term definition</span></span>

<span data-ttu-id="743ba-106">Os custos gerais indiretos são aqueles que foram incorridos para realizar um negócio, mas não podem ser diretamente atribuídos a qualquer atividade comercial, produto ou serviço específico.</span><span class="sxs-lookup"><span data-stu-id="743ba-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="743ba-107">Os custos gerais indiretos fornecem suporte crítico para geração de atividades produtivas.</span><span class="sxs-lookup"><span data-stu-id="743ba-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="743ba-108">Eis alguns exemplos de custos gerais:</span><span class="sxs-lookup"><span data-stu-id="743ba-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="743ba-109">Aluguel</span><span class="sxs-lookup"><span data-stu-id="743ba-109">Rent</span></span>
-   <span data-ttu-id="743ba-110">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-110">Electricity</span></span>
-   <span data-ttu-id="743ba-111">Salários administrativos</span><span class="sxs-lookup"><span data-stu-id="743ba-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="743ba-112">Visão geral do cálculo de custos gerais indiretos</span><span class="sxs-lookup"><span data-stu-id="743ba-112">Overhead calculation overview</span></span>
<span data-ttu-id="743ba-113">O cálculo de custos gerais indiretos executa as políticas de contabilização de custos na ordem correta.</span><span class="sxs-lookup"><span data-stu-id="743ba-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="743ba-114">Você pode executar o cálculo de custos gerais indiretos várias vezes para o mesmo período fiscal, se as políticas de contabilidade de custo foram modificadas ou foram detectados erros específicos.</span><span class="sxs-lookup"><span data-stu-id="743ba-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="743ba-115">Cada execução do cálculo de custos gerais indiretos é armazenada e recebe um ID exclusivo de versão que permite comparar os cálculos em várias versões.</span><span class="sxs-lookup"><span data-stu-id="743ba-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="743ba-116">As entradas de custo que o cálculo de custos indiretos gera recebe uma data contábil.</span><span class="sxs-lookup"><span data-stu-id="743ba-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="743ba-117">Essa data contábil corresponde à data final do período fiscal que é usada no cálculo.</span><span class="sxs-lookup"><span data-stu-id="743ba-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="743ba-118">A ID exclusiva de versão consiste nos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="743ba-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="743ba-119">Tipo de versão</span><span class="sxs-lookup"><span data-stu-id="743ba-119">Version type</span></span>
-   <span data-ttu-id="743ba-120">Data e hora</span><span class="sxs-lookup"><span data-stu-id="743ba-120">Date and time</span></span>
-   <span data-ttu-id="743ba-121">Razão de contabilização de custos</span><span class="sxs-lookup"><span data-stu-id="743ba-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="743ba-122">Ano fiscal</span><span class="sxs-lookup"><span data-stu-id="743ba-122">Fiscal year</span></span>
-   <span data-ttu-id="743ba-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="743ba-123">Fiscal period</span></span>

<span data-ttu-id="743ba-124">O cálculo de custos gerais indiretos é executado independentemente da versão.</span><span class="sxs-lookup"><span data-stu-id="743ba-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="743ba-125">Portanto, você pode calcular a versão de orçamento antes da versão atual.</span><span class="sxs-lookup"><span data-stu-id="743ba-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="743ba-126">O cálculo de custos gerais indiretos consiste em quatro etapas, conforme mostrado na ilustração.</span><span class="sxs-lookup"><span data-stu-id="743ba-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="743ba-127">Em cada etapa, um cabeçalho de diário é criado com entradas de diário.</span><span class="sxs-lookup"><span data-stu-id="743ba-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="743ba-128">Esse cabeçalho de diário mantém dados de entrada para cada etapa de cálculo.</span><span class="sxs-lookup"><span data-stu-id="743ba-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="743ba-129">As políticas e regras são aplicadas a cada linha do diário e as entradas de custo são geradas como saídas.</span><span class="sxs-lookup"><span data-stu-id="743ba-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="743ba-130">Portanto, você sempre terá rastreabilidade total.</span><span class="sxs-lookup"><span data-stu-id="743ba-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="743ba-131">[![Cálculo de custos gerais indiretos](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="743ba-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="743ba-132">Calcular e alocar os custos gerais indiretos de Eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="743ba-133">Na contabilidade financeira, alguns custos, como eletricidade, são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="743ba-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="743ba-134">Portanto, a visão administrativa detalhada não é fornecida para a contabilização de custo.</span><span class="sxs-lookup"><span data-stu-id="743ba-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="743ba-135">Na contabilização de custo, para fornecer a visão administrativa correta em todas as unidades organizacionais e níveis, os custos devem passar pelas unidades organizacionais.</span><span class="sxs-lookup"><span data-stu-id="743ba-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="743ba-136">Este fluxo deve ser baseado em qualquer um registro exato do consumo ou de uma previsão justa.</span><span class="sxs-lookup"><span data-stu-id="743ba-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="743ba-137">Na contabilidade, um custo de eletricidade pode ser lançado, conforme mostrado na tabela.</span><span class="sxs-lookup"><span data-stu-id="743ba-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="743ba-138">Data contábil</span><span class="sxs-lookup"><span data-stu-id="743ba-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="743ba-139">Centro de custos</span><span class="sxs-lookup"><span data-stu-id="743ba-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="743ba-140">Conta principal</span><span class="sxs-lookup"><span data-stu-id="743ba-140">Main account</span></span></th>
<th><span data-ttu-id="743ba-141">Valor na moeda contábil</span><span class="sxs-lookup"><span data-stu-id="743ba-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-142">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="743ba-143">CC099</span><span class="sxs-lookup"><span data-stu-id="743ba-143">CC099</span></span></td>
<td><span data-ttu-id="743ba-144">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="743ba-144">Default cost center</span></span></td>
<td><span data-ttu-id="743ba-145">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-145">10001</span></span></td>
<td><span data-ttu-id="743ba-146">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-146">Electricity</span></span></td>
<td><span data-ttu-id="743ba-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="743ba-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="743ba-148">Etapa 1: Processar o cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="743ba-149">Por padrão, quando as entradas de custo previsto são importadas de dados de origem, elas recebem a classificação de comportamento de custo **Não classificado** na Contabilidade de custos.</span><span class="sxs-lookup"><span data-stu-id="743ba-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="743ba-150">Aplicando regras da política de comportamento de custo, é possível reclassificar entradas de custo como **Custo fixo** ou **Custo variável**.</span><span class="sxs-lookup"><span data-stu-id="743ba-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="743ba-151">Definir a regra de custo de comportamento</span><span class="sxs-lookup"><span data-stu-id="743ba-151">Define the cost behavior rule</span></span>

<span data-ttu-id="743ba-152">Em alguns casos, parte do custo é uma taxa fixa e o custos pendente é baseado no consumo.</span><span class="sxs-lookup"><span data-stu-id="743ba-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="743ba-153">Geralmente, as contas de eletricidade correspondem a esta definição.</span><span class="sxs-lookup"><span data-stu-id="743ba-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="743ba-154">Após você pagar uma taxa fixa específica, você paga por consumo, por hora de quilowatt (Kwh).</span><span class="sxs-lookup"><span data-stu-id="743ba-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="743ba-155">Por exemplo, se a taxa de custo fixa for 1.000.00, veja aqui como a regra de comportamento de custo é definida:</span><span class="sxs-lookup"><span data-stu-id="743ba-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="743ba-156">Valor fixo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="743ba-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="743ba-157">0 &lt;= 1.000,00 = Fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="743ba-158">1000.01 &lt; N = Variável</span><span class="sxs-lookup"><span data-stu-id="743ba-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="743ba-159">Diário</span><span class="sxs-lookup"><span data-stu-id="743ba-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="743ba-160">Diário</span><span class="sxs-lookup"><span data-stu-id="743ba-160">Journal</span></span></th>
<th><span data-ttu-id="743ba-161">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="743ba-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="743ba-162">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="743ba-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="743ba-163">Versão</span><span class="sxs-lookup"><span data-stu-id="743ba-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-164">00001</span><span class="sxs-lookup"><span data-stu-id="743ba-164">00001</span></span></td>
<td><span data-ttu-id="743ba-165">Diário de cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="743ba-166">fiscal</span><span class="sxs-lookup"><span data-stu-id="743ba-166">Fiscal</span></span></td>
<td><span data-ttu-id="743ba-167">2017</span><span class="sxs-lookup"><span data-stu-id="743ba-167">2017</span></span></td>
<td><span data-ttu-id="743ba-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="743ba-168">Period 1</span></span></td>
<td><span data-ttu-id="743ba-169">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="743ba-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="743ba-170">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="743ba-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="743ba-171">Data contábil</span><span class="sxs-lookup"><span data-stu-id="743ba-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="743ba-172">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="743ba-173">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-173">Cost element</span></span></th>
<th><span data-ttu-id="743ba-174">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-174">Cost behavior</span></span></th>
<th><span data-ttu-id="743ba-175">Valor</span><span class="sxs-lookup"><span data-stu-id="743ba-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-176">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="743ba-177">CC099</span><span class="sxs-lookup"><span data-stu-id="743ba-177">CC099</span></span></td>
<td><span data-ttu-id="743ba-178">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="743ba-178">Default cost center</span></span></td>
<td><span data-ttu-id="743ba-179">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-179">10001</span></span></td>
<td><span data-ttu-id="743ba-180">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-180">Electricity</span></span></td>
<td><span data-ttu-id="743ba-181">Não classificado</span><span class="sxs-lookup"><span data-stu-id="743ba-181">Unclassified</span></span></td>
<td><span data-ttu-id="743ba-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="743ba-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="743ba-183">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="743ba-184">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="743ba-185">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-185">Cost element</span></span></th>
<th><span data-ttu-id="743ba-186">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-186">Cost behavior</span></span></th>
<th><span data-ttu-id="743ba-187">Valor</span><span class="sxs-lookup"><span data-stu-id="743ba-187">Amount</span></span></th>
<th><span data-ttu-id="743ba-188">Data contábil</span><span class="sxs-lookup"><span data-stu-id="743ba-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-189">CC099</span><span class="sxs-lookup"><span data-stu-id="743ba-189">CC099</span></span></td>
<td><span data-ttu-id="743ba-190">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="743ba-190">Default cost center</span></span></td>
<td><span data-ttu-id="743ba-191">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-191">10001</span></span></td>
<td><span data-ttu-id="743ba-192">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-192">Electricity</span></span></td>
<td><span data-ttu-id="743ba-193">Não classificado</span><span class="sxs-lookup"><span data-stu-id="743ba-193">Unclassified</span></span></td>
<td><span data-ttu-id="743ba-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="743ba-194">10,000.00</span></span></td>
<td><span data-ttu-id="743ba-195">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-196">CC099</span><span class="sxs-lookup"><span data-stu-id="743ba-196">CC099</span></span></td>
<td><span data-ttu-id="743ba-197">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="743ba-197">Default cost center</span></span></td>
<td><span data-ttu-id="743ba-198">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-198">10001</span></span></td>
<td><span data-ttu-id="743ba-199">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-199">Electricity</span></span></td>
<td><span data-ttu-id="743ba-200">Não classificado</span><span class="sxs-lookup"><span data-stu-id="743ba-200">Unclassified</span></span></td>
<td><span data-ttu-id="743ba-201">-10.000,00</span><span class="sxs-lookup"><span data-stu-id="743ba-201">-10,000.00</span></span></td>
<td><span data-ttu-id="743ba-202">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-203">CC099</span><span class="sxs-lookup"><span data-stu-id="743ba-203">CC099</span></span></td>
<td><span data-ttu-id="743ba-204">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="743ba-204">Default cost center</span></span></td>
<td><span data-ttu-id="743ba-205">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-205">10001</span></span></td>
<td><span data-ttu-id="743ba-206">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-206">Electricity</span></span></td>
<td><span data-ttu-id="743ba-207">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-207">Fixed cost</span></span></td>
<td><span data-ttu-id="743ba-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="743ba-208">1,000.00</span></span></td>
<td><span data-ttu-id="743ba-209">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-210">CC099</span><span class="sxs-lookup"><span data-stu-id="743ba-210">CC099</span></span></td>
<td><span data-ttu-id="743ba-211">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="743ba-211">Default cost center</span></span></td>
<td><span data-ttu-id="743ba-212">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-212">10001</span></span></td>
<td><span data-ttu-id="743ba-213">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-213">Electricity</span></span></td>
<td><span data-ttu-id="743ba-214">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-214">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="743ba-215">9,000.00</span></span></td>
<td><span data-ttu-id="743ba-216">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="743ba-217">Para obter mais informações, consulte [Criar e atribuir uma política de comportamento de custos a uma unidade de controle de custos](tasks/create-assign-cost-behavior-policy-cost-control-unit.md)</span><span class="sxs-lookup"><span data-stu-id="743ba-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="743ba-218">Etapa 2: Processar o cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="743ba-219">A distribuição de custos é usada para redistribuir custo de um objeto de custo a um ou mais outros objetos de custo, aplicando uma base de alocação relevante.</span><span class="sxs-lookup"><span data-stu-id="743ba-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="743ba-220">A distribuição de custos e a alocação de custo são diferentes na distribuição de custos, sempre que ocorrer em nível de elemento de custo principal do custo original.</span><span class="sxs-lookup"><span data-stu-id="743ba-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="743ba-221">Definir a regra de distribuição de custos</span><span class="sxs-lookup"><span data-stu-id="743ba-221">Define the cost distribution rule</span></span>

<span data-ttu-id="743ba-222">Na contabilidade financeira, os custos de eletricidade geralmente são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="743ba-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="743ba-223">Na contabilização de custo, esta abordagem não é suficientemente detalhada.</span><span class="sxs-lookup"><span data-stu-id="743ba-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="743ba-224">O custo variável deve ser distribuído a objetos de custos individuais com base justa.</span><span class="sxs-lookup"><span data-stu-id="743ba-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="743ba-225">A base de alocação mais lógica é o consumo de eletricidade (Kwh).</span><span class="sxs-lookup"><span data-stu-id="743ba-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="743ba-226">O membro da dimensão estatística que é chamado Eletricidade é criado e o consumo de eletricidade é registrado.</span><span class="sxs-lookup"><span data-stu-id="743ba-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="743ba-227">Por padrão, todos os membros estatísticos da dimensão se tornam disponíveis como bases de alocação.</span><span class="sxs-lookup"><span data-stu-id="743ba-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="743ba-228">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-228">Cost object</span></span></th>
<th><span data-ttu-id="743ba-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="743ba-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-230">CC001</span><span class="sxs-lookup"><span data-stu-id="743ba-230">CC001</span></span></td>
<td><span data-ttu-id="743ba-231">RH</span><span class="sxs-lookup"><span data-stu-id="743ba-231">HR</span></span></td>
<td><span data-ttu-id="743ba-232">1.000</span><span class="sxs-lookup"><span data-stu-id="743ba-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-233">CC002</span><span class="sxs-lookup"><span data-stu-id="743ba-233">CC002</span></span></td>
<td><span data-ttu-id="743ba-234">Finanças</span><span class="sxs-lookup"><span data-stu-id="743ba-234">Finance</span></span></td>
<td><span data-ttu-id="743ba-235">6,000</span><span class="sxs-lookup"><span data-stu-id="743ba-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-236">CC003</span><span class="sxs-lookup"><span data-stu-id="743ba-236">CC003</span></span></td>
<td><span data-ttu-id="743ba-237">Montagem</span><span class="sxs-lookup"><span data-stu-id="743ba-237">Assembly</span></span></td>
<td><span data-ttu-id="743ba-238">0</span><span class="sxs-lookup"><span data-stu-id="743ba-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="743ba-239">A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação para custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="743ba-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="743ba-240">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-240">Cost object</span></span></th>
<th><span data-ttu-id="743ba-241">Magnitude</span><span class="sxs-lookup"><span data-stu-id="743ba-241">Magnitude</span></span></th>
<th><span data-ttu-id="743ba-242">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="743ba-242">Allocation factor</span></span></th>
<th><span data-ttu-id="743ba-243">Valor</span><span class="sxs-lookup"><span data-stu-id="743ba-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-244">CC001</span><span class="sxs-lookup"><span data-stu-id="743ba-244">CC001</span></span></td>
<td><span data-ttu-id="743ba-245">RH</span><span class="sxs-lookup"><span data-stu-id="743ba-245">HR</span></span></td>
<td><span data-ttu-id="743ba-246">1.000</span><span class="sxs-lookup"><span data-stu-id="743ba-246">1,000</span></span></td>
<td><span data-ttu-id="743ba-247">(1.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="743ba-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="743ba-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="743ba-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-249">CC002</span><span class="sxs-lookup"><span data-stu-id="743ba-249">CC002</span></span></td>
<td><span data-ttu-id="743ba-250">Finanças</span><span class="sxs-lookup"><span data-stu-id="743ba-250">Finance</span></span></td>
<td><span data-ttu-id="743ba-251">6,000</span><span class="sxs-lookup"><span data-stu-id="743ba-251">6,000</span></span></td>
<td><span data-ttu-id="743ba-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="743ba-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="743ba-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="743ba-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-254">CC003</span><span class="sxs-lookup"><span data-stu-id="743ba-254">CC003</span></span></td>
<td><span data-ttu-id="743ba-255">Montagem</span><span class="sxs-lookup"><span data-stu-id="743ba-255">Assembly</span></span></td>
<td><span data-ttu-id="743ba-256">0</span><span class="sxs-lookup"><span data-stu-id="743ba-256">0</span></span></td>
<td><span data-ttu-id="743ba-257">(0 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="743ba-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="743ba-258">0,00</span><span class="sxs-lookup"><span data-stu-id="743ba-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="743ba-259">Os custos fixos devem ser distribuídos igualmente a objetos de custo individuais que têm a eletricidade consumida.</span><span class="sxs-lookup"><span data-stu-id="743ba-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="743ba-260">Você pode obter esse resultado usando o membro estatístico de dimensão de eletricidade em uma base e alocação da fórmula: (Eletricidade &gt; 0,00) A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação de custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="743ba-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="743ba-261">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-261">Cost object</span></span></th>
<th><span data-ttu-id="743ba-262">Fórmula</span><span class="sxs-lookup"><span data-stu-id="743ba-262">Formula</span></span></th>
<th><span data-ttu-id="743ba-263">Magnitude</span><span class="sxs-lookup"><span data-stu-id="743ba-263">Magnitude</span></span></th>
<th><span data-ttu-id="743ba-264">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="743ba-264">Allocation factor</span></span></th>
<th><span data-ttu-id="743ba-265">Valor</span><span class="sxs-lookup"><span data-stu-id="743ba-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-266">CC001</span><span class="sxs-lookup"><span data-stu-id="743ba-266">CC001</span></span></td>
<td><span data-ttu-id="743ba-267">RH</span><span class="sxs-lookup"><span data-stu-id="743ba-267">HR</span></span></td>
<td><span data-ttu-id="743ba-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="743ba-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="743ba-269">1</span><span class="sxs-lookup"><span data-stu-id="743ba-269">1</span></span></td>
<td><span data-ttu-id="743ba-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="743ba-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="743ba-271">500,00</span><span class="sxs-lookup"><span data-stu-id="743ba-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-272">CC002</span><span class="sxs-lookup"><span data-stu-id="743ba-272">CC002</span></span></td>
<td><span data-ttu-id="743ba-273">Finanças</span><span class="sxs-lookup"><span data-stu-id="743ba-273">Finance</span></span></td>
<td><span data-ttu-id="743ba-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="743ba-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="743ba-275">1</span><span class="sxs-lookup"><span data-stu-id="743ba-275">1</span></span></td>
<td><span data-ttu-id="743ba-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="743ba-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="743ba-277">500,00</span><span class="sxs-lookup"><span data-stu-id="743ba-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-278">CC003</span><span class="sxs-lookup"><span data-stu-id="743ba-278">CC003</span></span></td>
<td><span data-ttu-id="743ba-279">Montagem</span><span class="sxs-lookup"><span data-stu-id="743ba-279">Assembly</span></span></td>
<td><span data-ttu-id="743ba-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="743ba-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="743ba-281">0</span><span class="sxs-lookup"><span data-stu-id="743ba-281">0</span></span></td>
<td><span data-ttu-id="743ba-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="743ba-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="743ba-283">0,00</span><span class="sxs-lookup"><span data-stu-id="743ba-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="743ba-284">Diário</span><span class="sxs-lookup"><span data-stu-id="743ba-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="743ba-285">Diário</span><span class="sxs-lookup"><span data-stu-id="743ba-285">Journal</span></span></th>
<th><span data-ttu-id="743ba-286">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="743ba-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="743ba-287">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="743ba-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="743ba-288">Versão</span><span class="sxs-lookup"><span data-stu-id="743ba-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-289">00002</span><span class="sxs-lookup"><span data-stu-id="743ba-289">00002</span></span></td>
<td><span data-ttu-id="743ba-290">Diário de cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="743ba-291">fiscal</span><span class="sxs-lookup"><span data-stu-id="743ba-291">Fiscal</span></span></td>
<td><span data-ttu-id="743ba-292">2017</span><span class="sxs-lookup"><span data-stu-id="743ba-292">2017</span></span></td>
<td><span data-ttu-id="743ba-293">Período 1</span><span class="sxs-lookup"><span data-stu-id="743ba-293">Period 1</span></span></td>
<td><span data-ttu-id="743ba-294">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="743ba-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="743ba-295">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="743ba-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="743ba-296">Data contábil</span><span class="sxs-lookup"><span data-stu-id="743ba-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="743ba-297">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="743ba-298">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-298">Cost element</span></span></th>
<th><span data-ttu-id="743ba-299">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-299">Cost behavior</span></span></th>
<th><span data-ttu-id="743ba-300">Valor</span><span class="sxs-lookup"><span data-stu-id="743ba-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-301">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="743ba-302">CC099</span><span class="sxs-lookup"><span data-stu-id="743ba-302">CC099</span></span></td>
<td><span data-ttu-id="743ba-303">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="743ba-303">Default cost center</span></span></td>
<td><span data-ttu-id="743ba-304">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-304">10001</span></span></td>
<td><span data-ttu-id="743ba-305">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-305">Electricity</span></span></td>
<td><span data-ttu-id="743ba-306">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-306">Fixed cost</span></span></td>
<td><span data-ttu-id="743ba-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="743ba-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-308">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="743ba-309">CC099</span><span class="sxs-lookup"><span data-stu-id="743ba-309">CC099</span></span></td>
<td><span data-ttu-id="743ba-310">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="743ba-310">Default cost center</span></span></td>
<td><span data-ttu-id="743ba-311">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-311">10001</span></span></td>
<td><span data-ttu-id="743ba-312">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-312">Electricity</span></span></td>
<td><span data-ttu-id="743ba-313">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-313">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="743ba-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="743ba-315">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="743ba-316">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="743ba-317">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-317">Cost element</span></span></th>
<th><span data-ttu-id="743ba-318">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-318">Cost behavior</span></span></th>
<th><span data-ttu-id="743ba-319">Valor</span><span class="sxs-lookup"><span data-stu-id="743ba-319">Amount</span></span></th>
<th><span data-ttu-id="743ba-320">Data contábil</span><span class="sxs-lookup"><span data-stu-id="743ba-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-321">CC099</span><span class="sxs-lookup"><span data-stu-id="743ba-321">CC099</span></span></td>
<td><span data-ttu-id="743ba-322">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="743ba-322">Default cost center</span></span></td>
<td><span data-ttu-id="743ba-323">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-323">10001</span></span></td>
<td><span data-ttu-id="743ba-324">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-324">Electricity</span></span></td>
<td><span data-ttu-id="743ba-325">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-325">Fixed cost</span></span></td>
<td><span data-ttu-id="743ba-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="743ba-326">-1,000.00</span></span></td>
<td><span data-ttu-id="743ba-327">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-328">CC001</span><span class="sxs-lookup"><span data-stu-id="743ba-328">CC001</span></span></td>
<td><span data-ttu-id="743ba-329">RH</span><span class="sxs-lookup"><span data-stu-id="743ba-329">HR</span></span></td>
<td><span data-ttu-id="743ba-330">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-330">10001</span></span></td>
<td><span data-ttu-id="743ba-331">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-331">Electricity</span></span></td>
<td><span data-ttu-id="743ba-332">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-332">Fixed cost</span></span></td>
<td><span data-ttu-id="743ba-333">500,00</span><span class="sxs-lookup"><span data-stu-id="743ba-333">500.00</span></span></td>
<td><span data-ttu-id="743ba-334">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-335">CC002</span><span class="sxs-lookup"><span data-stu-id="743ba-335">CC002</span></span></td>
<td><span data-ttu-id="743ba-336">Finanças</span><span class="sxs-lookup"><span data-stu-id="743ba-336">Finance</span></span></td>
<td><span data-ttu-id="743ba-337">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-337">10001</span></span></td>
<td><span data-ttu-id="743ba-338">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-338">Electricity</span></span></td>
<td><span data-ttu-id="743ba-339">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-339">Fixed cost</span></span></td>
<td><span data-ttu-id="743ba-340">500,00</span><span class="sxs-lookup"><span data-stu-id="743ba-340">500.00</span></span></td>
<td><span data-ttu-id="743ba-341">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-342">CC099</span><span class="sxs-lookup"><span data-stu-id="743ba-342">CC099</span></span></td>
<td><span data-ttu-id="743ba-343">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="743ba-343">Default cost center</span></span></td>
<td><span data-ttu-id="743ba-344">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-344">10001</span></span></td>
<td><span data-ttu-id="743ba-345">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-345">Electricity</span></span></td>
<td><span data-ttu-id="743ba-346">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-346">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="743ba-347">-9,000.00</span></span></td>
<td><span data-ttu-id="743ba-348">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-349">CC001</span><span class="sxs-lookup"><span data-stu-id="743ba-349">CC001</span></span></td>
<td><span data-ttu-id="743ba-350">RH</span><span class="sxs-lookup"><span data-stu-id="743ba-350">HR</span></span></td>
<td><span data-ttu-id="743ba-351">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-351">10001</span></span></td>
<td><span data-ttu-id="743ba-352">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-352">Electricity</span></span></td>
<td><span data-ttu-id="743ba-353">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-353">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="743ba-354">1,285.71</span></span></td>
<td><span data-ttu-id="743ba-355">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-356">CC002</span><span class="sxs-lookup"><span data-stu-id="743ba-356">CC002</span></span></td>
<td><span data-ttu-id="743ba-357">Finanças</span><span class="sxs-lookup"><span data-stu-id="743ba-357">Finance</span></span></td>
<td><span data-ttu-id="743ba-358">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-358">10001</span></span></td>
<td><span data-ttu-id="743ba-359">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-359">Electricity</span></span></td>
<td><span data-ttu-id="743ba-360">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-360">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="743ba-361">7,714.29</span></span></td>
<td><span data-ttu-id="743ba-362">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="743ba-363">Para obter mais informações, consulte [Criar e atribuir uma política de distribuição de custos a uma unidade de controle de custos](tasks/create-assign-cost-distribution-policy-cost-control-unit.md)</span><span class="sxs-lookup"><span data-stu-id="743ba-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="743ba-364">Etapa 3: Processar o cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="743ba-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="743ba-365">A taxa de custos indiretos é usada para cobrar um ou mais objetos de custos específicos.</span><span class="sxs-lookup"><span data-stu-id="743ba-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="743ba-366">O encargo se baseia em uma taxa de custo predeterminada e a magnitude da básica de alocação atribuída.</span><span class="sxs-lookup"><span data-stu-id="743ba-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="743ba-367">Defina a taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="743ba-367">Define the overhead rate</span></span>

<span data-ttu-id="743ba-368">O objeto de custo CC001 HR contribui para um conjunto de projetos internos.</span><span class="sxs-lookup"><span data-stu-id="743ba-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="743ba-369">Um membro de dimensão estatística que é chamado de projetos de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="743ba-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="743ba-370">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-370">Cost object</span></span></th>
<th><span data-ttu-id="743ba-371">Horas</span><span class="sxs-lookup"><span data-stu-id="743ba-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-372">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="743ba-372">Proj 1</span></span></td>
<td><span data-ttu-id="743ba-373">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="743ba-373">Project 1</span></span></td>
<td><span data-ttu-id="743ba-374">3</span><span class="sxs-lookup"><span data-stu-id="743ba-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-375">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="743ba-375">Proj 2</span></span></td>
<td><span data-ttu-id="743ba-376">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="743ba-376">Project 2</span></span></td>
<td><span data-ttu-id="743ba-377">1</span><span class="sxs-lookup"><span data-stu-id="743ba-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="743ba-378">Uma taxa de custo predeterminada da contribuição de projetos de custo foi definida.</span><span class="sxs-lookup"><span data-stu-id="743ba-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="743ba-379">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-379">Cost object</span></span></th>
<th><span data-ttu-id="743ba-380">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-380">Cost element</span></span></th>
<th><span data-ttu-id="743ba-381">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-381">Cost behavior</span></span></th>
<th><span data-ttu-id="743ba-382">Unidades</span><span class="sxs-lookup"><span data-stu-id="743ba-382">Units</span></span></th>
<th><span data-ttu-id="743ba-383">Taxa</span><span class="sxs-lookup"><span data-stu-id="743ba-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-384">CC001</span><span class="sxs-lookup"><span data-stu-id="743ba-384">CC001</span></span></td>
<td><span data-ttu-id="743ba-385">RH</span><span class="sxs-lookup"><span data-stu-id="743ba-385">HR</span></span></td>
<td><span data-ttu-id="743ba-386">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-386">10001</span></span></td>
<td><span data-ttu-id="743ba-387">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-387">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-388">1</span><span class="sxs-lookup"><span data-stu-id="743ba-388">1</span></span></td>
<td><span data-ttu-id="743ba-389">10</span><span class="sxs-lookup"><span data-stu-id="743ba-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="743ba-390">A tabela a seguir mostra o resultado quando projetos de RH são aplicados como base de alocação.</span><span class="sxs-lookup"><span data-stu-id="743ba-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="743ba-391">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-391">Cost object</span></span></th>
<th><span data-ttu-id="743ba-392">Magnitude</span><span class="sxs-lookup"><span data-stu-id="743ba-392">Magnitude</span></span></th>
<th><span data-ttu-id="743ba-393">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-393">Cost element</span></span></th>
<th><span data-ttu-id="743ba-394">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="743ba-394">Allocation factor</span></span></th>
<th><span data-ttu-id="743ba-395">Valor</span><span class="sxs-lookup"><span data-stu-id="743ba-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-396">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="743ba-396">Proj 1</span></span></td>
<td><span data-ttu-id="743ba-397">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="743ba-397">Project 1</span></span></td>
<td><span data-ttu-id="743ba-398">3</span><span class="sxs-lookup"><span data-stu-id="743ba-398">3</span></span></td>
<td><span data-ttu-id="743ba-399">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-399">10001</span></span></td>
<td><span data-ttu-id="743ba-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="743ba-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="743ba-401">30,00</span><span class="sxs-lookup"><span data-stu-id="743ba-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-402">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="743ba-402">Proj 2</span></span></td>
<td><span data-ttu-id="743ba-403">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="743ba-403">Project 2</span></span></td>
<td><span data-ttu-id="743ba-404">1</span><span class="sxs-lookup"><span data-stu-id="743ba-404">1</span></span></td>
<td><span data-ttu-id="743ba-405">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-405">10001</span></span></td>
<td><span data-ttu-id="743ba-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="743ba-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="743ba-407">10,00</span><span class="sxs-lookup"><span data-stu-id="743ba-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="743ba-408">Diário</span><span class="sxs-lookup"><span data-stu-id="743ba-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="743ba-409">Diário</span><span class="sxs-lookup"><span data-stu-id="743ba-409">Journal</span></span></th>
<th><span data-ttu-id="743ba-410">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="743ba-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="743ba-411">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="743ba-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="743ba-412">Versão</span><span class="sxs-lookup"><span data-stu-id="743ba-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-413">00003</span><span class="sxs-lookup"><span data-stu-id="743ba-413">00003</span></span></td>
<td><span data-ttu-id="743ba-414">Diário de cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="743ba-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="743ba-415">fiscal</span><span class="sxs-lookup"><span data-stu-id="743ba-415">Fiscal</span></span></td>
<td><span data-ttu-id="743ba-416">2017</span><span class="sxs-lookup"><span data-stu-id="743ba-416">2017</span></span></td>
<td><span data-ttu-id="743ba-417">Período 1</span><span class="sxs-lookup"><span data-stu-id="743ba-417">Period 1</span></span></td>
<td><span data-ttu-id="743ba-418">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="743ba-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="743ba-419">Entradas de diário (As entradas de diário para cálculo da taxa de custos indiretos)</span><span class="sxs-lookup"><span data-stu-id="743ba-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="743ba-420">Data contábil</span><span class="sxs-lookup"><span data-stu-id="743ba-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="743ba-421">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-421">Cost object</span></span></th>
<th><span data-ttu-id="743ba-422">Magnitude</span><span class="sxs-lookup"><span data-stu-id="743ba-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-423">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="743ba-424">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="743ba-424">Proj 1</span></span></td>
<td><span data-ttu-id="743ba-425">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="743ba-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="743ba-426">3,00</span><span class="sxs-lookup"><span data-stu-id="743ba-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-427">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="743ba-428">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="743ba-428">Proj 2</span></span></td>
<td><span data-ttu-id="743ba-429">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="743ba-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="743ba-430">1.00</span><span class="sxs-lookup"><span data-stu-id="743ba-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="743ba-431">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="743ba-432">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="743ba-433">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-433">Cost element</span></span></th>
<th><span data-ttu-id="743ba-434">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-434">Cost behavior</span></span></th>
<th><span data-ttu-id="743ba-435">Valor</span><span class="sxs-lookup"><span data-stu-id="743ba-435">Amount</span></span></th>
<th><span data-ttu-id="743ba-436">Data contábil</span><span class="sxs-lookup"><span data-stu-id="743ba-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="743ba-437">CC0001</span></span></td>
<td><span data-ttu-id="743ba-438">RH</span><span class="sxs-lookup"><span data-stu-id="743ba-438">HR</span></span></td>
<td><span data-ttu-id="743ba-439">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-439">10001</span></span></td>
<td><span data-ttu-id="743ba-440">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-440">Electricity</span></span></td>
<td><span data-ttu-id="743ba-441">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-441">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="743ba-442">-30.00</span></span></td>
<td><span data-ttu-id="743ba-443">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-444">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="743ba-444">Proj 1</span></span></td>
<td><span data-ttu-id="743ba-445">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="743ba-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="743ba-446">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-446">10001</span></span></td>
<td><span data-ttu-id="743ba-447">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-447">Electricity</span></span></td>
<td><span data-ttu-id="743ba-448">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-448">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-449">30,00</span><span class="sxs-lookup"><span data-stu-id="743ba-449">30.00</span></span></td>
<td><span data-ttu-id="743ba-450">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-451">CC001</span><span class="sxs-lookup"><span data-stu-id="743ba-451">CC001</span></span></td>
<td><span data-ttu-id="743ba-452">RH</span><span class="sxs-lookup"><span data-stu-id="743ba-452">HR</span></span></td>
<td><span data-ttu-id="743ba-453">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-453">10001</span></span></td>
<td><span data-ttu-id="743ba-454">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-454">Electricity</span></span></td>
<td><span data-ttu-id="743ba-455">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-455">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="743ba-456">-10.00</span></span></td>
<td><span data-ttu-id="743ba-457">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-458">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="743ba-458">Proj 2</span></span></td>
<td><span data-ttu-id="743ba-459">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="743ba-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="743ba-460">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-460">10001</span></span></td>
<td><span data-ttu-id="743ba-461">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-461">Electricity</span></span></td>
<td><span data-ttu-id="743ba-462">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-462">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-463">10,00</span><span class="sxs-lookup"><span data-stu-id="743ba-463">10.00</span></span></td>
<td><span data-ttu-id="743ba-464">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="743ba-465">Para obter mais informações, consulte [Realizar cálculo de custos indiretos](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="743ba-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="743ba-466">Etapa 4: Processar o cálculo de alocação de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="743ba-467">A alocação é usada para alocar o saldo de um objeto de custo a outros objetos de custo pela aplicação de uma base de alocação.</span><span class="sxs-lookup"><span data-stu-id="743ba-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="743ba-468">O Finance oferece suporte ao método de alocação recíproco.</span><span class="sxs-lookup"><span data-stu-id="743ba-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="743ba-469">No método de alocação recíproco, os serviços mútuos que os objetos de custo auxiliar trocam são totalmente reconhecidos.</span><span class="sxs-lookup"><span data-stu-id="743ba-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="743ba-470">O sistema determina automaticamente a ordem correta realizar as alocações.</span><span class="sxs-lookup"><span data-stu-id="743ba-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="743ba-471">O saldo de um objeto de custo é alocado por uma base de alocação única.</span><span class="sxs-lookup"><span data-stu-id="743ba-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="743ba-472">As alocações entre as dimensões de objetos de custo e os respectivos membros são suportadas.</span><span class="sxs-lookup"><span data-stu-id="743ba-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="743ba-473">A ordem de alocação é controlada pela unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="743ba-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="743ba-474">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="743ba-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="743ba-475">Defina a alocação de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-475">Define the cost allocation</span></span>

<span data-ttu-id="743ba-476">Aqui está um exemplo simples que explica como você pode rastrear o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="743ba-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="743ba-477">O objeto de custo previsto CC001 HR contribui a vários objetos de custo previsto.</span><span class="sxs-lookup"><span data-stu-id="743ba-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="743ba-478">Um membro de dimensão estatística que é chamado de serviços de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="743ba-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="743ba-479">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-479">Cost object</span></span></th>
<th><span data-ttu-id="743ba-480">Serviços de RH</span><span class="sxs-lookup"><span data-stu-id="743ba-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-481">CC002</span><span class="sxs-lookup"><span data-stu-id="743ba-481">CC002</span></span></td>
<td><span data-ttu-id="743ba-482">Finanças</span><span class="sxs-lookup"><span data-stu-id="743ba-482">Finance</span></span></td>
<td><span data-ttu-id="743ba-483">35</span><span class="sxs-lookup"><span data-stu-id="743ba-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-484">CC003</span><span class="sxs-lookup"><span data-stu-id="743ba-484">CC003</span></span></td>
<td><span data-ttu-id="743ba-485">Montagem</span><span class="sxs-lookup"><span data-stu-id="743ba-485">Assembly</span></span></td>
<td><span data-ttu-id="743ba-486">55</span><span class="sxs-lookup"><span data-stu-id="743ba-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-487">CC004</span><span class="sxs-lookup"><span data-stu-id="743ba-487">CC004</span></span></td>
<td><span data-ttu-id="743ba-488">Embalagem</span><span class="sxs-lookup"><span data-stu-id="743ba-488">Packaging</span></span></td>
<td><span data-ttu-id="743ba-489">10</span><span class="sxs-lookup"><span data-stu-id="743ba-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="743ba-490">O objeto de custo CC002 Finanças contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="743ba-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="743ba-491">Um membro de dimensão estatística que é chamado de serviços de Finanças foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="743ba-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="743ba-492">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-492">Cost object</span></span></th>
<th><span data-ttu-id="743ba-493">Serviços financeiros</span><span class="sxs-lookup"><span data-stu-id="743ba-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-494">CC003</span><span class="sxs-lookup"><span data-stu-id="743ba-494">CC003</span></span></td>
<td><span data-ttu-id="743ba-495">Montagem</span><span class="sxs-lookup"><span data-stu-id="743ba-495">Assembly</span></span></td>
<td><span data-ttu-id="743ba-496">65</span><span class="sxs-lookup"><span data-stu-id="743ba-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-497">CC004</span><span class="sxs-lookup"><span data-stu-id="743ba-497">CC004</span></span></td>
<td><span data-ttu-id="743ba-498">Embalagem</span><span class="sxs-lookup"><span data-stu-id="743ba-498">Packaging</span></span></td>
<td><span data-ttu-id="743ba-499">35</span><span class="sxs-lookup"><span data-stu-id="743ba-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="743ba-500">O objeto de custo CC003 Montagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="743ba-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="743ba-501">Um membro de dimensão estatística que é chamado de serviços de Montagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="743ba-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="743ba-502">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-502">Cost object</span></span></th>
<th><span data-ttu-id="743ba-503">Serviços de montagem (horas)</span><span class="sxs-lookup"><span data-stu-id="743ba-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-504">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="743ba-504">Prod 1</span></span></td>
<td><span data-ttu-id="743ba-505">Produto 1</span><span class="sxs-lookup"><span data-stu-id="743ba-505">Product 1</span></span></td>
<td><span data-ttu-id="743ba-506">60</span><span class="sxs-lookup"><span data-stu-id="743ba-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-507">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="743ba-507">Prod 2</span></span></td>
<td><span data-ttu-id="743ba-508">Produto 2</span><span class="sxs-lookup"><span data-stu-id="743ba-508">Product 2</span></span></td>
<td><span data-ttu-id="743ba-509">20</span><span class="sxs-lookup"><span data-stu-id="743ba-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="743ba-510">O objeto de custo CC004 Embalagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="743ba-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="743ba-511">Um membro de dimensão estatística que é chamado de serviços de Embalagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="743ba-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="743ba-512">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-512">Cost object</span></span></th>
<th><span data-ttu-id="743ba-513">Serviços de embalagem (horas)</span><span class="sxs-lookup"><span data-stu-id="743ba-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-514">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="743ba-514">Prod 1</span></span></td>
<td><span data-ttu-id="743ba-515">Produto 1</span><span class="sxs-lookup"><span data-stu-id="743ba-515">Product 1</span></span></td>
<td><span data-ttu-id="743ba-516">80</span><span class="sxs-lookup"><span data-stu-id="743ba-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-517">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="743ba-517">Prod 2</span></span></td>
<td><span data-ttu-id="743ba-518">Produto 2</span><span class="sxs-lookup"><span data-stu-id="743ba-518">Product 2</span></span></td>
<td><span data-ttu-id="743ba-519">15</span><span class="sxs-lookup"><span data-stu-id="743ba-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="743ba-520">Medidas estatísticas, como as horas de produção que um produto consome, podem ser derivadas dos dados de origem.</span><span class="sxs-lookup"><span data-stu-id="743ba-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="743ba-521">Para obter mais informações, consulte [Modelo de provedor de medidas estatísticas](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="743ba-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="743ba-522">A tabela a seguir mostra o resultado quando os serviços de RH são aplicados como base de alocação para custos totais (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="743ba-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="743ba-523">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-523">Cost object</span></span></th>
<th><span data-ttu-id="743ba-524">Magnitude</span><span class="sxs-lookup"><span data-stu-id="743ba-524">Magnitude</span></span></th>
<th><span data-ttu-id="743ba-525">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="743ba-525">Allocation factor</span></span></th>
<th><span data-ttu-id="743ba-526">Valor</span><span class="sxs-lookup"><span data-stu-id="743ba-526">Amount</span></span></th>
<th><span data-ttu-id="743ba-527">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-528">CC002</span><span class="sxs-lookup"><span data-stu-id="743ba-528">CC002</span></span></td>
<td><span data-ttu-id="743ba-529">Finanças</span><span class="sxs-lookup"><span data-stu-id="743ba-529">Finance</span></span></td>
<td><span data-ttu-id="743ba-530">35</span><span class="sxs-lookup"><span data-stu-id="743ba-530">35</span></span></td>
<td><span data-ttu-id="743ba-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="743ba-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="743ba-532">175.00</span><span class="sxs-lookup"><span data-stu-id="743ba-532">175.00</span></span></td>
<td><span data-ttu-id="743ba-533">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-534">CC003</span><span class="sxs-lookup"><span data-stu-id="743ba-534">CC003</span></span></td>
<td><span data-ttu-id="743ba-535">Montagem</span><span class="sxs-lookup"><span data-stu-id="743ba-535">Assembly</span></span></td>
<td><span data-ttu-id="743ba-536">55</span><span class="sxs-lookup"><span data-stu-id="743ba-536">55</span></span></td>
<td><span data-ttu-id="743ba-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="743ba-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="743ba-538">275.00</span><span class="sxs-lookup"><span data-stu-id="743ba-538">275.00</span></span></td>
<td><span data-ttu-id="743ba-539">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-540">CC004</span><span class="sxs-lookup"><span data-stu-id="743ba-540">CC004</span></span></td>
<td><span data-ttu-id="743ba-541">Embalagem</span><span class="sxs-lookup"><span data-stu-id="743ba-541">Packaging</span></span></td>
<td><span data-ttu-id="743ba-542">10</span><span class="sxs-lookup"><span data-stu-id="743ba-542">10</span></span></td>
<td><span data-ttu-id="743ba-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="743ba-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="743ba-544">50,00</span><span class="sxs-lookup"><span data-stu-id="743ba-544">50.00</span></span></td>
<td><span data-ttu-id="743ba-545">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-546">CC002</span><span class="sxs-lookup"><span data-stu-id="743ba-546">CC002</span></span></td>
<td><span data-ttu-id="743ba-547">Finanças</span><span class="sxs-lookup"><span data-stu-id="743ba-547">Finance</span></span></td>
<td><span data-ttu-id="743ba-548">35</span><span class="sxs-lookup"><span data-stu-id="743ba-548">35</span></span></td>
<td><span data-ttu-id="743ba-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="743ba-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="743ba-550">436.00</span><span class="sxs-lookup"><span data-stu-id="743ba-550">436.00</span></span></td>
<td><span data-ttu-id="743ba-551">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-552">CC003</span><span class="sxs-lookup"><span data-stu-id="743ba-552">CC003</span></span></td>
<td><span data-ttu-id="743ba-553">Montagem</span><span class="sxs-lookup"><span data-stu-id="743ba-553">Assembly</span></span></td>
<td><span data-ttu-id="743ba-554">55</span><span class="sxs-lookup"><span data-stu-id="743ba-554">55</span></span></td>
<td><span data-ttu-id="743ba-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="743ba-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="743ba-556">685.14</span><span class="sxs-lookup"><span data-stu-id="743ba-556">685.14</span></span></td>
<td><span data-ttu-id="743ba-557">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-558">CC004</span><span class="sxs-lookup"><span data-stu-id="743ba-558">CC004</span></span></td>
<td><span data-ttu-id="743ba-559">Embalagem</span><span class="sxs-lookup"><span data-stu-id="743ba-559">Packaging</span></span></td>
<td><span data-ttu-id="743ba-560">10</span><span class="sxs-lookup"><span data-stu-id="743ba-560">10</span></span></td>
<td><span data-ttu-id="743ba-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="743ba-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="743ba-562">124.57</span><span class="sxs-lookup"><span data-stu-id="743ba-562">124.57</span></span></td>
<td><span data-ttu-id="743ba-563">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="743ba-564">A tabela a seguir mostra o resultado quando os serviços financeiros são aplicados como base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="743ba-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="743ba-565">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-565">Cost object</span></span></th>
<th><span data-ttu-id="743ba-566">Magnitude</span><span class="sxs-lookup"><span data-stu-id="743ba-566">Magnitude</span></span></th>
<th><span data-ttu-id="743ba-567">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="743ba-567">Allocation factor</span></span></th>
<th><span data-ttu-id="743ba-568">Valor</span><span class="sxs-lookup"><span data-stu-id="743ba-568">Amount</span></span></th>
<th><span data-ttu-id="743ba-569">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-570">CC003</span><span class="sxs-lookup"><span data-stu-id="743ba-570">CC003</span></span></td>
<td><span data-ttu-id="743ba-571">Montagem</span><span class="sxs-lookup"><span data-stu-id="743ba-571">Assembly</span></span></td>
<td><span data-ttu-id="743ba-572">65</span><span class="sxs-lookup"><span data-stu-id="743ba-572">65</span></span></td>
<td><span data-ttu-id="743ba-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="743ba-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="743ba-574">438.75</span><span class="sxs-lookup"><span data-stu-id="743ba-574">438.75</span></span></td>
<td><span data-ttu-id="743ba-575">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-576">CC004</span><span class="sxs-lookup"><span data-stu-id="743ba-576">CC004</span></span></td>
<td><span data-ttu-id="743ba-577">Embalagem</span><span class="sxs-lookup"><span data-stu-id="743ba-577">Packaging</span></span></td>
<td><span data-ttu-id="743ba-578">35</span><span class="sxs-lookup"><span data-stu-id="743ba-578">35</span></span></td>
<td><span data-ttu-id="743ba-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="743ba-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="743ba-580">236.25</span><span class="sxs-lookup"><span data-stu-id="743ba-580">236.25</span></span></td>
<td><span data-ttu-id="743ba-581">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-582">CC003</span><span class="sxs-lookup"><span data-stu-id="743ba-582">CC003</span></span></td>
<td><span data-ttu-id="743ba-583">Montagem</span><span class="sxs-lookup"><span data-stu-id="743ba-583">Assembly</span></span></td>
<td><span data-ttu-id="743ba-584">65</span><span class="sxs-lookup"><span data-stu-id="743ba-584">65</span></span></td>
<td><span data-ttu-id="743ba-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="743ba-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="743ba-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="743ba-586">5,297.69</span></span></td>
<td><span data-ttu-id="743ba-587">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-588">CC004</span><span class="sxs-lookup"><span data-stu-id="743ba-588">CC004</span></span></td>
<td><span data-ttu-id="743ba-589">Embalagem</span><span class="sxs-lookup"><span data-stu-id="743ba-589">Packaging</span></span></td>
<td><span data-ttu-id="743ba-590">35</span><span class="sxs-lookup"><span data-stu-id="743ba-590">35</span></span></td>
<td><span data-ttu-id="743ba-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="743ba-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="743ba-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="743ba-592">2,852.60</span></span></td>
<td><span data-ttu-id="743ba-593">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="743ba-594">A tabela a seguir mostra o resultado quando os serviços de Montagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="743ba-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="743ba-595">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-595">Cost object</span></span></th>
<th><span data-ttu-id="743ba-596">Magnitude</span><span class="sxs-lookup"><span data-stu-id="743ba-596">Magnitude</span></span></th>
<th><span data-ttu-id="743ba-597">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="743ba-597">Allocation factor</span></span></th>
<th><span data-ttu-id="743ba-598">Valor</span><span class="sxs-lookup"><span data-stu-id="743ba-598">Amount</span></span></th>
<th><span data-ttu-id="743ba-599">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-600">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="743ba-600">Prod 1</span></span></td>
<td><span data-ttu-id="743ba-601">Produto 1</span><span class="sxs-lookup"><span data-stu-id="743ba-601">Product 1</span></span></td>
<td><span data-ttu-id="743ba-602">60</span><span class="sxs-lookup"><span data-stu-id="743ba-602">60</span></span></td>
<td><span data-ttu-id="743ba-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="743ba-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="743ba-604">535.31</span><span class="sxs-lookup"><span data-stu-id="743ba-604">535.31</span></span></td>
<td><span data-ttu-id="743ba-605">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-606">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="743ba-606">Prod 2</span></span></td>
<td><span data-ttu-id="743ba-607">Produto 2</span><span class="sxs-lookup"><span data-stu-id="743ba-607">Product 2</span></span></td>
<td><span data-ttu-id="743ba-608">20</span><span class="sxs-lookup"><span data-stu-id="743ba-608">20</span></span></td>
<td><span data-ttu-id="743ba-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="743ba-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="743ba-610">178.44</span><span class="sxs-lookup"><span data-stu-id="743ba-610">178.44</span></span></td>
<td><span data-ttu-id="743ba-611">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-612">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="743ba-612">Prod 1</span></span></td>
<td><span data-ttu-id="743ba-613">Produto 1</span><span class="sxs-lookup"><span data-stu-id="743ba-613">Product 1</span></span></td>
<td><span data-ttu-id="743ba-614">60</span><span class="sxs-lookup"><span data-stu-id="743ba-614">60</span></span></td>
<td><span data-ttu-id="743ba-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="743ba-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="743ba-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="743ba-616">4,487.12</span></span></td>
<td><span data-ttu-id="743ba-617">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-618">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="743ba-618">Prod 2</span></span></td>
<td><span data-ttu-id="743ba-619">Produto 2</span><span class="sxs-lookup"><span data-stu-id="743ba-619">Product 2</span></span></td>
<td><span data-ttu-id="743ba-620">20</span><span class="sxs-lookup"><span data-stu-id="743ba-620">20</span></span></td>
<td><span data-ttu-id="743ba-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="743ba-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="743ba-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="743ba-622">1,495.71</span></span></td>
<td><span data-ttu-id="743ba-623">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="743ba-624">A tabela a seguir mostra o resultado quando os serviços de Embalagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="743ba-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="743ba-625">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-625">Cost object</span></span></th>
<th><span data-ttu-id="743ba-626">Magnitude</span><span class="sxs-lookup"><span data-stu-id="743ba-626">Magnitude</span></span></th>
<th><span data-ttu-id="743ba-627">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="743ba-627">Allocation factor</span></span></th>
<th><span data-ttu-id="743ba-628">Valor</span><span class="sxs-lookup"><span data-stu-id="743ba-628">Amount</span></span></th>
<th><span data-ttu-id="743ba-629">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-630">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="743ba-630">Prod 1</span></span></td>
<td><span data-ttu-id="743ba-631">Produto 1</span><span class="sxs-lookup"><span data-stu-id="743ba-631">Product 1</span></span></td>
<td><span data-ttu-id="743ba-632">80</span><span class="sxs-lookup"><span data-stu-id="743ba-632">80</span></span></td>
<td><span data-ttu-id="743ba-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="743ba-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="743ba-634">241.05</span><span class="sxs-lookup"><span data-stu-id="743ba-634">241.05</span></span></td>
<td><span data-ttu-id="743ba-635">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-636">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="743ba-636">Prod 2</span></span></td>
<td><span data-ttu-id="743ba-637">Produto 2</span><span class="sxs-lookup"><span data-stu-id="743ba-637">Product 2</span></span></td>
<td><span data-ttu-id="743ba-638">15</span><span class="sxs-lookup"><span data-stu-id="743ba-638">15</span></span></td>
<td><span data-ttu-id="743ba-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="743ba-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="743ba-640">45.20</span><span class="sxs-lookup"><span data-stu-id="743ba-640">45.20</span></span></td>
<td><span data-ttu-id="743ba-641">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-642">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="743ba-642">Prod 1</span></span></td>
<td><span data-ttu-id="743ba-643">Produto 1</span><span class="sxs-lookup"><span data-stu-id="743ba-643">Product 1</span></span></td>
<td><span data-ttu-id="743ba-644">80</span><span class="sxs-lookup"><span data-stu-id="743ba-644">80</span></span></td>
<td><span data-ttu-id="743ba-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="743ba-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="743ba-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="743ba-646">2,507.09</span></span></td>
<td><span data-ttu-id="743ba-647">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-648">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="743ba-648">Prod 2</span></span></td>
<td><span data-ttu-id="743ba-649">Produto 2</span><span class="sxs-lookup"><span data-stu-id="743ba-649">Product 2</span></span></td>
<td><span data-ttu-id="743ba-650">15</span><span class="sxs-lookup"><span data-stu-id="743ba-650">15</span></span></td>
<td><span data-ttu-id="743ba-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="743ba-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="743ba-652">470.08</span><span class="sxs-lookup"><span data-stu-id="743ba-652">470.08</span></span></td>
<td><span data-ttu-id="743ba-653">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="743ba-654">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="743ba-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="743ba-655">Diário</span><span class="sxs-lookup"><span data-stu-id="743ba-655">Journal</span></span></th>
<th><span data-ttu-id="743ba-656">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="743ba-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="743ba-657">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="743ba-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="743ba-658">Versão</span><span class="sxs-lookup"><span data-stu-id="743ba-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-659">00004</span><span class="sxs-lookup"><span data-stu-id="743ba-659">00004</span></span></td>
<td><span data-ttu-id="743ba-660">Diário de alocação de custos</span><span class="sxs-lookup"><span data-stu-id="743ba-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="743ba-661">fiscal</span><span class="sxs-lookup"><span data-stu-id="743ba-661">Fiscal</span></span></td>
<td><span data-ttu-id="743ba-662">2017</span><span class="sxs-lookup"><span data-stu-id="743ba-662">2017</span></span></td>
<td><span data-ttu-id="743ba-663">Período 1</span><span class="sxs-lookup"><span data-stu-id="743ba-663">Period 1</span></span></td>
<td><span data-ttu-id="743ba-664">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="743ba-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="743ba-665">Linhas do diário</span><span class="sxs-lookup"><span data-stu-id="743ba-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="743ba-666">Data contábil</span><span class="sxs-lookup"><span data-stu-id="743ba-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="743ba-667">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="743ba-668">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-668">Cost element</span></span></th>
<th><span data-ttu-id="743ba-669">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-669">Cost behavior</span></span></th>
<th><span data-ttu-id="743ba-670">Valor</span><span class="sxs-lookup"><span data-stu-id="743ba-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-671">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="743ba-672">CC001</span><span class="sxs-lookup"><span data-stu-id="743ba-672">CC001</span></span></td>
<td><span data-ttu-id="743ba-673">RH</span><span class="sxs-lookup"><span data-stu-id="743ba-673">HR</span></span></td>
<td><span data-ttu-id="743ba-674">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-674">10001</span></span></td>
<td><span data-ttu-id="743ba-675">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-675">Electricity</span></span></td>
<td><span data-ttu-id="743ba-676">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-676">Fixed cost</span></span></td>
<td><span data-ttu-id="743ba-677">500,00</span><span class="sxs-lookup"><span data-stu-id="743ba-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-678">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="743ba-679">CC001</span><span class="sxs-lookup"><span data-stu-id="743ba-679">CC001</span></span></td>
<td><span data-ttu-id="743ba-680">RH</span><span class="sxs-lookup"><span data-stu-id="743ba-680">HR</span></span></td>
<td><span data-ttu-id="743ba-681">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-681">10001</span></span></td>
<td><span data-ttu-id="743ba-682">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-682">Electricity</span></span></td>
<td><span data-ttu-id="743ba-683">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-683">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="743ba-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-685">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="743ba-686">CC002</span><span class="sxs-lookup"><span data-stu-id="743ba-686">CC002</span></span></td>
<td><span data-ttu-id="743ba-687">Finanças</span><span class="sxs-lookup"><span data-stu-id="743ba-687">Finance</span></span></td>
<td><span data-ttu-id="743ba-688">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-688">10001</span></span></td>
<td><span data-ttu-id="743ba-689">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-689">Electricity</span></span></td>
<td><span data-ttu-id="743ba-690">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-690">Fixed cost</span></span></td>
<td><span data-ttu-id="743ba-691">675.00</span><span class="sxs-lookup"><span data-stu-id="743ba-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-692">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="743ba-693">CC002</span><span class="sxs-lookup"><span data-stu-id="743ba-693">CC002</span></span></td>
<td><span data-ttu-id="743ba-694">Finanças</span><span class="sxs-lookup"><span data-stu-id="743ba-694">Finance</span></span></td>
<td><span data-ttu-id="743ba-695">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-695">10001</span></span></td>
<td><span data-ttu-id="743ba-696">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-696">Electricity</span></span></td>
<td><span data-ttu-id="743ba-697">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-697">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="743ba-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-699">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="743ba-700">CC003</span><span class="sxs-lookup"><span data-stu-id="743ba-700">CC003</span></span></td>
<td><span data-ttu-id="743ba-701">Montagem</span><span class="sxs-lookup"><span data-stu-id="743ba-701">Assembly</span></span></td>
<td><span data-ttu-id="743ba-702">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-702">10001</span></span></td>
<td><span data-ttu-id="743ba-703">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-703">Electricity</span></span></td>
<td><span data-ttu-id="743ba-704">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-704">Fixed cost</span></span></td>
<td><span data-ttu-id="743ba-705">713.75</span><span class="sxs-lookup"><span data-stu-id="743ba-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-706">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="743ba-707">CC003</span><span class="sxs-lookup"><span data-stu-id="743ba-707">CC003</span></span></td>
<td><span data-ttu-id="743ba-708">Montagem</span><span class="sxs-lookup"><span data-stu-id="743ba-708">Assembly</span></span></td>
<td><span data-ttu-id="743ba-709">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-709">10001</span></span></td>
<td><span data-ttu-id="743ba-710">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-710">Electricity</span></span></td>
<td><span data-ttu-id="743ba-711">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-711">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="743ba-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-713">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="743ba-714">CC003</span><span class="sxs-lookup"><span data-stu-id="743ba-714">CC003</span></span></td>
<td><span data-ttu-id="743ba-715">Embalagem</span><span class="sxs-lookup"><span data-stu-id="743ba-715">Packaging</span></span></td>
<td><span data-ttu-id="743ba-716">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-716">10001</span></span></td>
<td><span data-ttu-id="743ba-717">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-717">Electricity</span></span></td>
<td><span data-ttu-id="743ba-718">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-718">Fixed cost</span></span></td>
<td><span data-ttu-id="743ba-719">286.25</span><span class="sxs-lookup"><span data-stu-id="743ba-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-720">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="743ba-721">CC003</span><span class="sxs-lookup"><span data-stu-id="743ba-721">CC003</span></span></td>
<td><span data-ttu-id="743ba-722">Embalagem</span><span class="sxs-lookup"><span data-stu-id="743ba-722">Packaging</span></span></td>
<td><span data-ttu-id="743ba-723">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-723">10001</span></span></td>
<td><span data-ttu-id="743ba-724">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-724">Electricity</span></span></td>
<td><span data-ttu-id="743ba-725">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-725">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="743ba-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-727">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="743ba-728">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="743ba-728">Prod 1</span></span></td>
<td><span data-ttu-id="743ba-729">Produto 1</span><span class="sxs-lookup"><span data-stu-id="743ba-729">Product 1</span></span></td>
<td><span data-ttu-id="743ba-730">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-730">10001</span></span></td>
<td><span data-ttu-id="743ba-731">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-731">Electricity</span></span></td>
<td><span data-ttu-id="743ba-732">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-732">Fixed cost</span></span></td>
<td><span data-ttu-id="743ba-733">776.36</span><span class="sxs-lookup"><span data-stu-id="743ba-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-734">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="743ba-735">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="743ba-735">Prod 1</span></span></td>
<td><span data-ttu-id="743ba-736">Produto 1</span><span class="sxs-lookup"><span data-stu-id="743ba-736">Product 1</span></span></td>
<td><span data-ttu-id="743ba-737">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-737">10001</span></span></td>
<td><span data-ttu-id="743ba-738">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-738">Electricity</span></span></td>
<td><span data-ttu-id="743ba-739">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-739">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="743ba-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-741">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="743ba-742">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="743ba-742">Prod 2</span></span></td>
<td><span data-ttu-id="743ba-743">Produto 1</span><span class="sxs-lookup"><span data-stu-id="743ba-743">Product 1</span></span></td>
<td><span data-ttu-id="743ba-744">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-744">10001</span></span></td>
<td><span data-ttu-id="743ba-745">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-745">Electricity</span></span></td>
<td><span data-ttu-id="743ba-746">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-746">Fixed cost</span></span></td>
<td><span data-ttu-id="743ba-747">223.64</span><span class="sxs-lookup"><span data-stu-id="743ba-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-748">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="743ba-749">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="743ba-749">Prod 2</span></span></td>
<td><span data-ttu-id="743ba-750">Produto 1</span><span class="sxs-lookup"><span data-stu-id="743ba-750">Product 1</span></span></td>
<td><span data-ttu-id="743ba-751">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-751">10001</span></span></td>
<td><span data-ttu-id="743ba-752">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-752">Electricity</span></span></td>
<td><span data-ttu-id="743ba-753">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-753">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="743ba-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="743ba-755">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="743ba-756">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="743ba-757">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-757">Cost element</span></span></th>
<th><span data-ttu-id="743ba-758">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-758">Cost behavior</span></span></th>
<th><span data-ttu-id="743ba-759">Valor</span><span class="sxs-lookup"><span data-stu-id="743ba-759">Amount</span></span></th>
<th><span data-ttu-id="743ba-760">Data contábil</span><span class="sxs-lookup"><span data-stu-id="743ba-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="743ba-761">CC001</span><span class="sxs-lookup"><span data-stu-id="743ba-761">CC001</span></span></td>
<td><span data-ttu-id="743ba-762">RH</span><span class="sxs-lookup"><span data-stu-id="743ba-762">HR</span></span></td>
<td><span data-ttu-id="743ba-763">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-763">10001</span></span></td>
<td><span data-ttu-id="743ba-764">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-764">Electricity</span></span></td>
<td><span data-ttu-id="743ba-765">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-765">Fixed cost</span></span></td>
<td><span data-ttu-id="743ba-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="743ba-766">-500.00</span></span></td>
<td><span data-ttu-id="743ba-767">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-768">CC002</span><span class="sxs-lookup"><span data-stu-id="743ba-768">CC002</span></span></td>
<td><span data-ttu-id="743ba-769">Finanças</span><span class="sxs-lookup"><span data-stu-id="743ba-769">Finance</span></span></td>
<td><span data-ttu-id="743ba-770">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-770">10001</span></span></td>
<td><span data-ttu-id="743ba-771">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-771">Electricity</span></span></td>
<td><span data-ttu-id="743ba-772">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-772">Fixed cost</span></span></td>
<td><span data-ttu-id="743ba-773">175.00</span><span class="sxs-lookup"><span data-stu-id="743ba-773">175.00</span></span></td>
<td><span data-ttu-id="743ba-774">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-775">CC003</span><span class="sxs-lookup"><span data-stu-id="743ba-775">CC003</span></span></td>
<td><span data-ttu-id="743ba-776">Montagem</span><span class="sxs-lookup"><span data-stu-id="743ba-776">Assembly</span></span></td>
<td><span data-ttu-id="743ba-777">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-777">10001</span></span></td>
<td><span data-ttu-id="743ba-778">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-778">Electricity</span></span></td>
<td><span data-ttu-id="743ba-779">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-779">Fixed cost</span></span></td>
<td><span data-ttu-id="743ba-780">275.00</span><span class="sxs-lookup"><span data-stu-id="743ba-780">275.00</span></span></td>
<td><span data-ttu-id="743ba-781">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-782">CC004</span><span class="sxs-lookup"><span data-stu-id="743ba-782">CC004</span></span></td>
<td><span data-ttu-id="743ba-783">Embalagem</span><span class="sxs-lookup"><span data-stu-id="743ba-783">Packaging</span></span></td>
<td><span data-ttu-id="743ba-784">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-784">10001</span></span></td>
<td><span data-ttu-id="743ba-785">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-785">Electricity</span></span></td>
<td><span data-ttu-id="743ba-786">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-786">Fixed cost</span></span></td>
<td><span data-ttu-id="743ba-787">50,00</span><span class="sxs-lookup"><span data-stu-id="743ba-787">50,00</span></span></td>
<td><span data-ttu-id="743ba-788">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-789">CC001</span><span class="sxs-lookup"><span data-stu-id="743ba-789">CC001</span></span></td>
<td><span data-ttu-id="743ba-790">RH</span><span class="sxs-lookup"><span data-stu-id="743ba-790">HR</span></span></td>
<td><span data-ttu-id="743ba-791">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-791">10001</span></span></td>
<td><span data-ttu-id="743ba-792">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-792">Electricity</span></span></td>
<td><span data-ttu-id="743ba-793">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-793">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="743ba-794">-1,245.71</span></span></td>
<td><span data-ttu-id="743ba-795">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-796">CC002</span><span class="sxs-lookup"><span data-stu-id="743ba-796">CC002</span></span></td>
<td><span data-ttu-id="743ba-797">Finanças</span><span class="sxs-lookup"><span data-stu-id="743ba-797">Finance</span></span></td>
<td><span data-ttu-id="743ba-798">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-798">10001</span></span></td>
<td><span data-ttu-id="743ba-799">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-799">Electricity</span></span></td>
<td><span data-ttu-id="743ba-800">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-800">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-801">436.00</span><span class="sxs-lookup"><span data-stu-id="743ba-801">436.00</span></span></td>
<td><span data-ttu-id="743ba-802">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-803">CC003</span><span class="sxs-lookup"><span data-stu-id="743ba-803">CC003</span></span></td>
<td><span data-ttu-id="743ba-804">Montagem</span><span class="sxs-lookup"><span data-stu-id="743ba-804">Assembly</span></span></td>
<td><span data-ttu-id="743ba-805">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-805">10001</span></span></td>
<td><span data-ttu-id="743ba-806">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-806">Electricity</span></span></td>
<td><span data-ttu-id="743ba-807">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-807">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-808">685.14</span><span class="sxs-lookup"><span data-stu-id="743ba-808">685.14</span></span></td>
<td><span data-ttu-id="743ba-809">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-810">CC004</span><span class="sxs-lookup"><span data-stu-id="743ba-810">CC004</span></span></td>
<td><span data-ttu-id="743ba-811">Embalagem</span><span class="sxs-lookup"><span data-stu-id="743ba-811">Packaging</span></span></td>
<td><span data-ttu-id="743ba-812">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-812">10001</span></span></td>
<td><span data-ttu-id="743ba-813">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-813">Electricity</span></span></td>
<td><span data-ttu-id="743ba-814">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-814">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-815">124.57</span><span class="sxs-lookup"><span data-stu-id="743ba-815">124.57</span></span></td>
<td><span data-ttu-id="743ba-816">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-817">CC002</span><span class="sxs-lookup"><span data-stu-id="743ba-817">CC002</span></span></td>
<td><span data-ttu-id="743ba-818">Finanças</span><span class="sxs-lookup"><span data-stu-id="743ba-818">Finance</span></span></td>
<td><span data-ttu-id="743ba-819">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-819">10001</span></span></td>
<td><span data-ttu-id="743ba-820">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-820">Electricity</span></span></td>
<td><span data-ttu-id="743ba-821">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-821">Fixed cost</span></span></td>
<td><span data-ttu-id="743ba-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="743ba-822">-675.00</span></span></td>
<td><span data-ttu-id="743ba-823">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-824">CC003</span><span class="sxs-lookup"><span data-stu-id="743ba-824">CC003</span></span></td>
<td><span data-ttu-id="743ba-825">Montagem</span><span class="sxs-lookup"><span data-stu-id="743ba-825">Assembly</span></span></td>
<td><span data-ttu-id="743ba-826">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-826">10001</span></span></td>
<td><span data-ttu-id="743ba-827">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-827">Electricity</span></span></td>
<td><span data-ttu-id="743ba-828">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-828">Fixed cost</span></span></td>
<td><span data-ttu-id="743ba-829">438.75</span><span class="sxs-lookup"><span data-stu-id="743ba-829">438.75</span></span></td>
<td><span data-ttu-id="743ba-830">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-831">CC004</span><span class="sxs-lookup"><span data-stu-id="743ba-831">CC004</span></span></td>
<td><span data-ttu-id="743ba-832">Embalagem</span><span class="sxs-lookup"><span data-stu-id="743ba-832">Packaging</span></span></td>
<td><span data-ttu-id="743ba-833">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-833">10001</span></span></td>
<td><span data-ttu-id="743ba-834">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-834">Electricity</span></span></td>
<td><span data-ttu-id="743ba-835">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-835">Fixed cost</span></span></td>
<td><span data-ttu-id="743ba-836">236.25</span><span class="sxs-lookup"><span data-stu-id="743ba-836">236.25</span></span></td>
<td><span data-ttu-id="743ba-837">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-838">CC002</span><span class="sxs-lookup"><span data-stu-id="743ba-838">CC002</span></span></td>
<td><span data-ttu-id="743ba-839">Finanças</span><span class="sxs-lookup"><span data-stu-id="743ba-839">Finance</span></span></td>
<td><span data-ttu-id="743ba-840">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-840">10001</span></span></td>
<td><span data-ttu-id="743ba-841">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-841">Electricity</span></span></td>
<td><span data-ttu-id="743ba-842">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-842">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="743ba-843">-8,150.29</span></span></td>
<td><span data-ttu-id="743ba-844">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-845">CC003</span><span class="sxs-lookup"><span data-stu-id="743ba-845">CC003</span></span></td>
<td><span data-ttu-id="743ba-846">Montagem</span><span class="sxs-lookup"><span data-stu-id="743ba-846">Assembly</span></span></td>
<td><span data-ttu-id="743ba-847">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-847">10001</span></span></td>
<td><span data-ttu-id="743ba-848">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-848">Electricity</span></span></td>
<td><span data-ttu-id="743ba-849">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-849">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="743ba-850">5,297.69</span></span></td>
<td><span data-ttu-id="743ba-851">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-852">CC004</span><span class="sxs-lookup"><span data-stu-id="743ba-852">CC004</span></span></td>
<td><span data-ttu-id="743ba-853">Embalagem</span><span class="sxs-lookup"><span data-stu-id="743ba-853">Packaging</span></span></td>
<td><span data-ttu-id="743ba-854">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-854">10001</span></span></td>
<td><span data-ttu-id="743ba-855">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-855">Electricity</span></span></td>
<td><span data-ttu-id="743ba-856">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-856">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="743ba-857">2,852.60</span></span></td>
<td><span data-ttu-id="743ba-858">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-859">CC003</span><span class="sxs-lookup"><span data-stu-id="743ba-859">CC003</span></span></td>
<td><span data-ttu-id="743ba-860">Montagem</span><span class="sxs-lookup"><span data-stu-id="743ba-860">Assembly</span></span></td>
<td><span data-ttu-id="743ba-861">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-861">10001</span></span></td>
<td><span data-ttu-id="743ba-862">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-862">Electricity</span></span></td>
<td><span data-ttu-id="743ba-863">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-863">Fixed cost</span></span></td>
<td><span data-ttu-id="743ba-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="743ba-864">-713.75</span></span></td>
<td><span data-ttu-id="743ba-865">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-866">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="743ba-866">Prod 1</span></span></td>
<td><span data-ttu-id="743ba-867">Produto 1</span><span class="sxs-lookup"><span data-stu-id="743ba-867">Product 1</span></span></td>
<td><span data-ttu-id="743ba-868">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-868">10001</span></span></td>
<td><span data-ttu-id="743ba-869">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-869">Electricity</span></span></td>
<td><span data-ttu-id="743ba-870">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-870">Fixed cost</span></span></td>
<td><span data-ttu-id="743ba-871">535.31</span><span class="sxs-lookup"><span data-stu-id="743ba-871">535.31</span></span></td>
<td><span data-ttu-id="743ba-872">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-873">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="743ba-873">Prod 2</span></span></td>
<td><span data-ttu-id="743ba-874">Produto 2</span><span class="sxs-lookup"><span data-stu-id="743ba-874">Product 2</span></span></td>
<td><span data-ttu-id="743ba-875">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-875">10001</span></span></td>
<td><span data-ttu-id="743ba-876">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-876">Electricity</span></span></td>
<td><span data-ttu-id="743ba-877">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-877">Fixed cost</span></span></td>
<td><span data-ttu-id="743ba-878">178.44</span><span class="sxs-lookup"><span data-stu-id="743ba-878">178.44</span></span></td>
<td><span data-ttu-id="743ba-879">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-880">CC003</span><span class="sxs-lookup"><span data-stu-id="743ba-880">CC003</span></span></td>
<td><span data-ttu-id="743ba-881">Montagem</span><span class="sxs-lookup"><span data-stu-id="743ba-881">Assembly</span></span></td>
<td><span data-ttu-id="743ba-882">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-882">10001</span></span></td>
<td><span data-ttu-id="743ba-883">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-883">Electricity</span></span></td>
<td><span data-ttu-id="743ba-884">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-884">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="743ba-885">-5,982.83</span></span></td>
<td><span data-ttu-id="743ba-886">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-887">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="743ba-887">Prod 1</span></span></td>
<td><span data-ttu-id="743ba-888">Produto 1</span><span class="sxs-lookup"><span data-stu-id="743ba-888">Product 1</span></span></td>
<td><span data-ttu-id="743ba-889">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-889">10001</span></span></td>
<td><span data-ttu-id="743ba-890">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-890">Electricity</span></span></td>
<td><span data-ttu-id="743ba-891">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-891">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="743ba-892">4,487.12</span></span></td>
<td><span data-ttu-id="743ba-893">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-894">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="743ba-894">Prod 2</span></span></td>
<td><span data-ttu-id="743ba-895">Produto 2</span><span class="sxs-lookup"><span data-stu-id="743ba-895">Product 2</span></span></td>
<td><span data-ttu-id="743ba-896">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-896">10001</span></span></td>
<td><span data-ttu-id="743ba-897">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-897">Electricity</span></span></td>
<td><span data-ttu-id="743ba-898">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-898">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="743ba-899">1,495.71</span></span></td>
<td><span data-ttu-id="743ba-900">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-901">CC003</span><span class="sxs-lookup"><span data-stu-id="743ba-901">CC003</span></span></td>
<td><span data-ttu-id="743ba-902">Montagem</span><span class="sxs-lookup"><span data-stu-id="743ba-902">Assembly</span></span></td>
<td><span data-ttu-id="743ba-903">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-903">10001</span></span></td>
<td><span data-ttu-id="743ba-904">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-904">Electricity</span></span></td>
<td><span data-ttu-id="743ba-905">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-905">Fixed cost</span></span></td>
<td><span data-ttu-id="743ba-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="743ba-906">-286.25</span></span></td>
<td><span data-ttu-id="743ba-907">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-908">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="743ba-908">Prod 1</span></span></td>
<td><span data-ttu-id="743ba-909">Produto 1</span><span class="sxs-lookup"><span data-stu-id="743ba-909">Product 1</span></span></td>
<td><span data-ttu-id="743ba-910">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-910">10001</span></span></td>
<td><span data-ttu-id="743ba-911">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-911">Electricity</span></span></td>
<td><span data-ttu-id="743ba-912">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-912">Fixed cost</span></span></td>
<td><span data-ttu-id="743ba-913">241.05</span><span class="sxs-lookup"><span data-stu-id="743ba-913">241.05</span></span></td>
<td><span data-ttu-id="743ba-914">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-915">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="743ba-915">Prod 2</span></span></td>
<td><span data-ttu-id="743ba-916">Produto 2</span><span class="sxs-lookup"><span data-stu-id="743ba-916">Product 2</span></span></td>
<td><span data-ttu-id="743ba-917">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-917">10001</span></span></td>
<td><span data-ttu-id="743ba-918">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-918">Electricity</span></span></td>
<td><span data-ttu-id="743ba-919">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-919">Fixed cost</span></span></td>
<td><span data-ttu-id="743ba-920">45.20</span><span class="sxs-lookup"><span data-stu-id="743ba-920">45.20</span></span></td>
<td><span data-ttu-id="743ba-921">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-922">CC003</span><span class="sxs-lookup"><span data-stu-id="743ba-922">CC003</span></span></td>
<td><span data-ttu-id="743ba-923">Montagem</span><span class="sxs-lookup"><span data-stu-id="743ba-923">Assembly</span></span></td>
<td><span data-ttu-id="743ba-924">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-924">10001</span></span></td>
<td><span data-ttu-id="743ba-925">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-925">Electricity</span></span></td>
<td><span data-ttu-id="743ba-926">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-926">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="743ba-927">-2,977.17</span></span></td>
<td><span data-ttu-id="743ba-928">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-929">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="743ba-929">Prod 1</span></span></td>
<td><span data-ttu-id="743ba-930">Produto 1</span><span class="sxs-lookup"><span data-stu-id="743ba-930">Product 1</span></span></td>
<td><span data-ttu-id="743ba-931">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-931">10001</span></span></td>
<td><span data-ttu-id="743ba-932">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-932">Electricity</span></span></td>
<td><span data-ttu-id="743ba-933">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-933">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="743ba-934">2,507.09</span></span></td>
<td><span data-ttu-id="743ba-935">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="743ba-936">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="743ba-936">Prod 2</span></span></td>
<td><span data-ttu-id="743ba-937">Produto 2</span><span class="sxs-lookup"><span data-stu-id="743ba-937">Product 2</span></span></td>
<td><span data-ttu-id="743ba-938">10001</span><span class="sxs-lookup"><span data-stu-id="743ba-938">10001</span></span></td>
<td><span data-ttu-id="743ba-939">eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-939">Electricity</span></span></td>
<td><span data-ttu-id="743ba-940">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-940">Variable cost</span></span></td>
<td><span data-ttu-id="743ba-941">470.08</span><span class="sxs-lookup"><span data-stu-id="743ba-941">470.08</span></span></td>
<td><span data-ttu-id="743ba-942">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="743ba-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="743ba-943">Conclusão</span><span class="sxs-lookup"><span data-stu-id="743ba-943">Conclusion</span></span>
<span data-ttu-id="743ba-944">Na contabilidade financeira, um custo de 10,000.00 para a eletricidade é lançado para um ID fictício de centro de custos.</span><span class="sxs-lookup"><span data-stu-id="743ba-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="743ba-945">Portanto, os contadores de custo saberão que esses custos devem ser alocados.</span><span class="sxs-lookup"><span data-stu-id="743ba-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="743ba-946">Na contabilização de custo, os custos fluem nas unidades organizacionais e nos níveis, com base nas políticas e regras que são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="743ba-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="743ba-947">Cada custo foi associado a uma base de alocação que fornece a melhor apuração para a alocação de custos.</span><span class="sxs-lookup"><span data-stu-id="743ba-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="743ba-948">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="743ba-949">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="743ba-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="743ba-950">Total</span><span class="sxs-lookup"><span data-stu-id="743ba-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="743ba-951">CC099</span><span class="sxs-lookup"><span data-stu-id="743ba-951">CC099</span></span></th>
<th><span data-ttu-id="743ba-952">CC001</span><span class="sxs-lookup"><span data-stu-id="743ba-952">CC001</span></span></th>
<th><span data-ttu-id="743ba-953">CC002</span><span class="sxs-lookup"><span data-stu-id="743ba-953">CC002</span></span></th>
<th><span data-ttu-id="743ba-954">CC003</span><span class="sxs-lookup"><span data-stu-id="743ba-954">CC003</span></span></th>
<th><span data-ttu-id="743ba-955">CC004</span><span class="sxs-lookup"><span data-stu-id="743ba-955">CC004</span></span></th>
<th><span data-ttu-id="743ba-956">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="743ba-956">Proj 1</span></span></th>
<th><span data-ttu-id="743ba-957">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="743ba-957">Proj 2</span></span></th>
<th><span data-ttu-id="743ba-958">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="743ba-958">Prod 1</span></span></th>
<th><span data-ttu-id="743ba-959">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="743ba-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="743ba-960">10001 Eletricidade</span><span class="sxs-lookup"><span data-stu-id="743ba-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="743ba-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="743ba-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="743ba-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="743ba-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="743ba-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="743ba-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="743ba-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="743ba-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="743ba-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="743ba-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="743ba-970">Não classificado</span><span class="sxs-lookup"><span data-stu-id="743ba-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-971">0,00</span><span class="sxs-lookup"><span data-stu-id="743ba-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="743ba-972">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="743ba-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-973">0,00</span><span class="sxs-lookup"><span data-stu-id="743ba-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-974">0,00</span><span class="sxs-lookup"><span data-stu-id="743ba-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-975">0,00</span><span class="sxs-lookup"><span data-stu-id="743ba-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-976">0,00</span><span class="sxs-lookup"><span data-stu-id="743ba-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-977">0,00</span><span class="sxs-lookup"><span data-stu-id="743ba-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="743ba-978">776.36</span><span class="sxs-lookup"><span data-stu-id="743ba-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-979">223.64</span><span class="sxs-lookup"><span data-stu-id="743ba-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="743ba-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="743ba-981">Custo variável</span><span class="sxs-lookup"><span data-stu-id="743ba-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-982">000</span><span class="sxs-lookup"><span data-stu-id="743ba-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-983">0,00</span><span class="sxs-lookup"><span data-stu-id="743ba-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-984">0,00</span><span class="sxs-lookup"><span data-stu-id="743ba-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-985">0,00</span><span class="sxs-lookup"><span data-stu-id="743ba-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-986">0,00</span><span class="sxs-lookup"><span data-stu-id="743ba-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-987">30,00</span><span class="sxs-lookup"><span data-stu-id="743ba-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-988">10,00</span><span class="sxs-lookup"><span data-stu-id="743ba-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="743ba-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="743ba-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="743ba-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="743ba-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="743ba-992">Esse tópico mostra como um elemento de custo principal, 10001 Eletricidade flui pelos objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="743ba-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="743ba-993">Portanto, esse custo geral indireto é alocado no nível mais baixo na organização.</span><span class="sxs-lookup"><span data-stu-id="743ba-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="743ba-994">Em outras palavras, os objetos de custo no nível mais baixo assumem o custo.</span><span class="sxs-lookup"><span data-stu-id="743ba-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="743ba-995">Se você exigir um fluxo visual de custo entre objetos de custo, é possível usar as regras de política de acúmulo de custos para visualizar o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="743ba-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="743ba-996">Para obter mais informações, consulte [Política de acúmulo de custo e cálculo de custos indiretos](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="743ba-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]