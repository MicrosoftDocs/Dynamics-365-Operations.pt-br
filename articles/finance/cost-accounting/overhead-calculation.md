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
ms.openlocfilehash: 2dddc22128621dc148a253cd568430587f294544
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822894"
---
# <a name="overhead-calculation"></a><span data-ttu-id="a3cf2-103">Cálculo de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="a3cf2-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a3cf2-104">Este tópico descreve processos comuns para calcular e alocar os custos gerais indiretos.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="a3cf2-105">Definição de termo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-105">Term definition</span></span>
---------------

<span data-ttu-id="a3cf2-106">Os custos gerais indiretos são aqueles que foram incorridos para realizar um negócio, mas não podem ser diretamente atribuídos a qualquer atividade comercial, produto ou serviço específico.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="a3cf2-107">Os custos gerais indiretos fornecem suporte crítico para geração de atividades produtivas.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="a3cf2-108">Eis alguns exemplos de custos gerais:</span><span class="sxs-lookup"><span data-stu-id="a3cf2-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="a3cf2-109">Aluguel</span><span class="sxs-lookup"><span data-stu-id="a3cf2-109">Rent</span></span>
-   <span data-ttu-id="a3cf2-110">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-110">Electricity</span></span>
-   <span data-ttu-id="a3cf2-111">Salários administrativos</span><span class="sxs-lookup"><span data-stu-id="a3cf2-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="a3cf2-112">Visão geral do cálculo de custos gerais indiretos</span><span class="sxs-lookup"><span data-stu-id="a3cf2-112">Overhead calculation overview</span></span>
<span data-ttu-id="a3cf2-113">O cálculo de custos gerais indiretos executa as políticas de contabilização de custos na ordem correta.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="a3cf2-114">Você pode executar o cálculo de custos gerais indiretos várias vezes para o mesmo período fiscal, se as políticas de contabilidade de custo foram modificadas ou foram detectados erros específicos.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="a3cf2-115">Cada execução do cálculo de custos gerais indiretos é armazenada e recebe um ID exclusivo de versão que permite comparar os cálculos em várias versões.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="a3cf2-116">As entradas de custo que o cálculo de custos indiretos gera recebe uma data contábil.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="a3cf2-117">Essa data contábil corresponde à data final do período fiscal que é usada no cálculo.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="a3cf2-118">A ID exclusiva de versão consiste nos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="a3cf2-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="a3cf2-119">Tipo de versão</span><span class="sxs-lookup"><span data-stu-id="a3cf2-119">Version type</span></span>
-   <span data-ttu-id="a3cf2-120">Data e hora</span><span class="sxs-lookup"><span data-stu-id="a3cf2-120">Date and time</span></span>
-   <span data-ttu-id="a3cf2-121">Razão de contabilização de custos</span><span class="sxs-lookup"><span data-stu-id="a3cf2-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="a3cf2-122">Ano fiscal</span><span class="sxs-lookup"><span data-stu-id="a3cf2-122">Fiscal year</span></span>
-   <span data-ttu-id="a3cf2-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="a3cf2-123">Fiscal period</span></span>

<span data-ttu-id="a3cf2-124">O cálculo de custos gerais indiretos é executado independentemente da versão.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="a3cf2-125">Portanto, você pode calcular a versão de orçamento antes da versão atual.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="a3cf2-126">O cálculo de custos gerais indiretos consiste em quatro etapas, conforme mostrado na ilustração.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="a3cf2-127">Em cada etapa, um cabeçalho de diário é criado com entradas de diário.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="a3cf2-128">Esse cabeçalho de diário mantém dados de entrada para cada etapa de cálculo.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="a3cf2-129">As políticas e regras são aplicadas a cada linha do diário e as entradas de custo são geradas como saídas.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="a3cf2-130">Portanto, você sempre terá rastreabilidade total.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="a3cf2-131">[![Cálculo de custos gerais indiretos](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="a3cf2-132">Calcular e alocar os custos gerais indiretos de Eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="a3cf2-133">Na contabilidade financeira, alguns custos, como eletricidade, são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="a3cf2-134">Portanto, a visão administrativa detalhada não é fornecida para a contabilização de custo.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="a3cf2-135">Na contabilização de custo, para fornecer a visão administrativa correta em todas as unidades organizacionais e níveis, os custos devem passar pelas unidades organizacionais.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="a3cf2-136">Este fluxo deve ser baseado em qualquer um registro exato do consumo ou de uma previsão justa.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="a3cf2-137">Na contabilidade, um custo de eletricidade pode ser lançado, conforme mostrado na tabela.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a3cf2-138">Data contábil</span><span class="sxs-lookup"><span data-stu-id="a3cf2-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="a3cf2-139">Centro de custos</span><span class="sxs-lookup"><span data-stu-id="a3cf2-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="a3cf2-140">Conta principal</span><span class="sxs-lookup"><span data-stu-id="a3cf2-140">Main account</span></span></th>
<th><span data-ttu-id="a3cf2-141">Valor na moeda contábil</span><span class="sxs-lookup"><span data-stu-id="a3cf2-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-142">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="a3cf2-143">CC099</span><span class="sxs-lookup"><span data-stu-id="a3cf2-143">CC099</span></span></td>
<td><span data-ttu-id="a3cf2-144">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="a3cf2-144">Default cost center</span></span></td>
<td><span data-ttu-id="a3cf2-145">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-145">10001</span></span></td>
<td><span data-ttu-id="a3cf2-146">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-146">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="a3cf2-148">Etapa 1: Processar o cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="a3cf2-149">Por padrão, quando as entradas de custo previsto são importadas de dados de origem, elas recebem a classificação de comportamento de custo **Não classificado** na Contabilidade de custos.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="a3cf2-150">Aplicando regras da política de comportamento de custo, é possível reclassificar entradas de custo como **Custo fixo** ou **Custo variável**.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="a3cf2-151">Definir a regra de custo de comportamento</span><span class="sxs-lookup"><span data-stu-id="a3cf2-151">Define the cost behavior rule</span></span>

<span data-ttu-id="a3cf2-152">Em alguns casos, parte do custo é uma taxa fixa e o custos pendente é baseado no consumo.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="a3cf2-153">Geralmente, as contas de eletricidade correspondem a esta definição.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="a3cf2-154">Após você pagar uma taxa fixa específica, você paga por consumo, por hora de quilowatt (Kwh).</span><span class="sxs-lookup"><span data-stu-id="a3cf2-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="a3cf2-155">Por exemplo, se a taxa de custo fixa for 1.000.00, veja aqui como a regra de comportamento de custo é definida:</span><span class="sxs-lookup"><span data-stu-id="a3cf2-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="a3cf2-156">Valor fixo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="a3cf2-157">0 &lt;= 1.000,00 = Fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="a3cf2-158">1000.01 &lt; N = Variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="a3cf2-159">Diário</span><span class="sxs-lookup"><span data-stu-id="a3cf2-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a3cf2-160">Diário</span><span class="sxs-lookup"><span data-stu-id="a3cf2-160">Journal</span></span></th>
<th><span data-ttu-id="a3cf2-161">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="a3cf2-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="a3cf2-162">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="a3cf2-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="a3cf2-163">Versão</span><span class="sxs-lookup"><span data-stu-id="a3cf2-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-164">00001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-164">00001</span></span></td>
<td><span data-ttu-id="a3cf2-165">Diário de cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="a3cf2-166">fiscal</span><span class="sxs-lookup"><span data-stu-id="a3cf2-166">Fiscal</span></span></td>
<td><span data-ttu-id="a3cf2-167">2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-167">2017</span></span></td>
<td><span data-ttu-id="a3cf2-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-168">Period 1</span></span></td>
<td><span data-ttu-id="a3cf2-169">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="a3cf2-170">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a3cf2-171">Data contábil</span><span class="sxs-lookup"><span data-stu-id="a3cf2-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="a3cf2-172">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a3cf2-173">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-173">Cost element</span></span></th>
<th><span data-ttu-id="a3cf2-174">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-174">Cost behavior</span></span></th>
<th><span data-ttu-id="a3cf2-175">Valor</span><span class="sxs-lookup"><span data-stu-id="a3cf2-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-176">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="a3cf2-177">CC099</span><span class="sxs-lookup"><span data-stu-id="a3cf2-177">CC099</span></span></td>
<td><span data-ttu-id="a3cf2-178">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="a3cf2-178">Default cost center</span></span></td>
<td><span data-ttu-id="a3cf2-179">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-179">10001</span></span></td>
<td><span data-ttu-id="a3cf2-180">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-180">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-181">Não classificado</span><span class="sxs-lookup"><span data-stu-id="a3cf2-181">Unclassified</span></span></td>
<td><span data-ttu-id="a3cf2-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="a3cf2-183">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3cf2-184">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a3cf2-185">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-185">Cost element</span></span></th>
<th><span data-ttu-id="a3cf2-186">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-186">Cost behavior</span></span></th>
<th><span data-ttu-id="a3cf2-187">Valor</span><span class="sxs-lookup"><span data-stu-id="a3cf2-187">Amount</span></span></th>
<th><span data-ttu-id="a3cf2-188">Data contábil</span><span class="sxs-lookup"><span data-stu-id="a3cf2-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-189">CC099</span><span class="sxs-lookup"><span data-stu-id="a3cf2-189">CC099</span></span></td>
<td><span data-ttu-id="a3cf2-190">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="a3cf2-190">Default cost center</span></span></td>
<td><span data-ttu-id="a3cf2-191">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-191">10001</span></span></td>
<td><span data-ttu-id="a3cf2-192">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-192">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-193">Não classificado</span><span class="sxs-lookup"><span data-stu-id="a3cf2-193">Unclassified</span></span></td>
<td><span data-ttu-id="a3cf2-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-194">10,000.00</span></span></td>
<td><span data-ttu-id="a3cf2-195">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-196">CC099</span><span class="sxs-lookup"><span data-stu-id="a3cf2-196">CC099</span></span></td>
<td><span data-ttu-id="a3cf2-197">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="a3cf2-197">Default cost center</span></span></td>
<td><span data-ttu-id="a3cf2-198">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-198">10001</span></span></td>
<td><span data-ttu-id="a3cf2-199">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-199">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-200">Não classificado</span><span class="sxs-lookup"><span data-stu-id="a3cf2-200">Unclassified</span></span></td>
<td><span data-ttu-id="a3cf2-201">-10.000,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-201">-10,000.00</span></span></td>
<td><span data-ttu-id="a3cf2-202">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-203">CC099</span><span class="sxs-lookup"><span data-stu-id="a3cf2-203">CC099</span></span></td>
<td><span data-ttu-id="a3cf2-204">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="a3cf2-204">Default cost center</span></span></td>
<td><span data-ttu-id="a3cf2-205">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-205">10001</span></span></td>
<td><span data-ttu-id="a3cf2-206">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-206">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-207">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-207">Fixed cost</span></span></td>
<td><span data-ttu-id="a3cf2-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-208">1,000.00</span></span></td>
<td><span data-ttu-id="a3cf2-209">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-210">CC099</span><span class="sxs-lookup"><span data-stu-id="a3cf2-210">CC099</span></span></td>
<td><span data-ttu-id="a3cf2-211">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="a3cf2-211">Default cost center</span></span></td>
<td><span data-ttu-id="a3cf2-212">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-212">10001</span></span></td>
<td><span data-ttu-id="a3cf2-213">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-213">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-214">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-214">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-215">9,000.00</span></span></td>
<td><span data-ttu-id="a3cf2-216">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3cf2-217">Para obter mais informações, consulte [Criar e atribuir uma política de comportamento de custos a uma unidade de controle de custos](tasks/create-assign-cost-behavior-policy-cost-control-unit.md)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="a3cf2-218">Etapa 2: Processar o cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="a3cf2-219">A distribuição de custos é usada para redistribuir custo de um objeto de custo a um ou mais outros objetos de custo, aplicando uma base de alocação relevante.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="a3cf2-220">A distribuição de custos e a alocação de custo são diferentes na distribuição de custos, sempre que ocorrer em nível de elemento de custo principal do custo original.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="a3cf2-221">Definir a regra de distribuição de custos</span><span class="sxs-lookup"><span data-stu-id="a3cf2-221">Define the cost distribution rule</span></span>

<span data-ttu-id="a3cf2-222">Na contabilidade financeira, os custos de eletricidade geralmente são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="a3cf2-223">Na contabilização de custo, esta abordagem não é suficientemente detalhada.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="a3cf2-224">O custo variável deve ser distribuído a objetos de custos individuais com base justa.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="a3cf2-225">A base de alocação mais lógica é o consumo de eletricidade (Kwh).</span><span class="sxs-lookup"><span data-stu-id="a3cf2-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="a3cf2-226">O membro da dimensão estatística que é chamado Eletricidade é criado e o consumo de eletricidade é registrado.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="a3cf2-227">Por padrão, todos os membros estatísticos da dimensão se tornam disponíveis como bases de alocação.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3cf2-228">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-228">Cost object</span></span></th>
<th><span data-ttu-id="a3cf2-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="a3cf2-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-230">CC001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-230">CC001</span></span></td>
<td><span data-ttu-id="a3cf2-231">RH</span><span class="sxs-lookup"><span data-stu-id="a3cf2-231">HR</span></span></td>
<td><span data-ttu-id="a3cf2-232">1.000</span><span class="sxs-lookup"><span data-stu-id="a3cf2-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-233">CC002</span><span class="sxs-lookup"><span data-stu-id="a3cf2-233">CC002</span></span></td>
<td><span data-ttu-id="a3cf2-234">Finanças</span><span class="sxs-lookup"><span data-stu-id="a3cf2-234">Finance</span></span></td>
<td><span data-ttu-id="a3cf2-235">6,000</span><span class="sxs-lookup"><span data-stu-id="a3cf2-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-236">CC003</span><span class="sxs-lookup"><span data-stu-id="a3cf2-236">CC003</span></span></td>
<td><span data-ttu-id="a3cf2-237">Montagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-237">Assembly</span></span></td>
<td><span data-ttu-id="a3cf2-238">0</span><span class="sxs-lookup"><span data-stu-id="a3cf2-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3cf2-239">A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação para custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3cf2-240">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-240">Cost object</span></span></th>
<th><span data-ttu-id="a3cf2-241">Magnitude</span><span class="sxs-lookup"><span data-stu-id="a3cf2-241">Magnitude</span></span></th>
<th><span data-ttu-id="a3cf2-242">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="a3cf2-242">Allocation factor</span></span></th>
<th><span data-ttu-id="a3cf2-243">Valor</span><span class="sxs-lookup"><span data-stu-id="a3cf2-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-244">CC001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-244">CC001</span></span></td>
<td><span data-ttu-id="a3cf2-245">RH</span><span class="sxs-lookup"><span data-stu-id="a3cf2-245">HR</span></span></td>
<td><span data-ttu-id="a3cf2-246">1.000</span><span class="sxs-lookup"><span data-stu-id="a3cf2-246">1,000</span></span></td>
<td><span data-ttu-id="a3cf2-247">(1.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="a3cf2-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="a3cf2-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-249">CC002</span><span class="sxs-lookup"><span data-stu-id="a3cf2-249">CC002</span></span></td>
<td><span data-ttu-id="a3cf2-250">Finanças</span><span class="sxs-lookup"><span data-stu-id="a3cf2-250">Finance</span></span></td>
<td><span data-ttu-id="a3cf2-251">6,000</span><span class="sxs-lookup"><span data-stu-id="a3cf2-251">6,000</span></span></td>
<td><span data-ttu-id="a3cf2-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="a3cf2-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="a3cf2-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-254">CC003</span><span class="sxs-lookup"><span data-stu-id="a3cf2-254">CC003</span></span></td>
<td><span data-ttu-id="a3cf2-255">Montagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-255">Assembly</span></span></td>
<td><span data-ttu-id="a3cf2-256">0</span><span class="sxs-lookup"><span data-stu-id="a3cf2-256">0</span></span></td>
<td><span data-ttu-id="a3cf2-257">(0 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="a3cf2-258">0,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3cf2-259">Os custos fixos devem ser distribuídos igualmente a objetos de custo individuais que têm a eletricidade consumida.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="a3cf2-260">Você pode obter esse resultado usando o membro estatístico de dimensão de eletricidade em uma base e alocação da fórmula: (Eletricidade &gt; 0,00) A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação de custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3cf2-261">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-261">Cost object</span></span></th>
<th><span data-ttu-id="a3cf2-262">Fórmula</span><span class="sxs-lookup"><span data-stu-id="a3cf2-262">Formula</span></span></th>
<th><span data-ttu-id="a3cf2-263">Magnitude</span><span class="sxs-lookup"><span data-stu-id="a3cf2-263">Magnitude</span></span></th>
<th><span data-ttu-id="a3cf2-264">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="a3cf2-264">Allocation factor</span></span></th>
<th><span data-ttu-id="a3cf2-265">Valor</span><span class="sxs-lookup"><span data-stu-id="a3cf2-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-266">CC001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-266">CC001</span></span></td>
<td><span data-ttu-id="a3cf2-267">RH</span><span class="sxs-lookup"><span data-stu-id="a3cf2-267">HR</span></span></td>
<td><span data-ttu-id="a3cf2-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="a3cf2-269">1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-269">1</span></span></td>
<td><span data-ttu-id="a3cf2-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="a3cf2-271">500,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-272">CC002</span><span class="sxs-lookup"><span data-stu-id="a3cf2-272">CC002</span></span></td>
<td><span data-ttu-id="a3cf2-273">Finanças</span><span class="sxs-lookup"><span data-stu-id="a3cf2-273">Finance</span></span></td>
<td><span data-ttu-id="a3cf2-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="a3cf2-275">1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-275">1</span></span></td>
<td><span data-ttu-id="a3cf2-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="a3cf2-277">500,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-278">CC003</span><span class="sxs-lookup"><span data-stu-id="a3cf2-278">CC003</span></span></td>
<td><span data-ttu-id="a3cf2-279">Montagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-279">Assembly</span></span></td>
<td><span data-ttu-id="a3cf2-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="a3cf2-281">0</span><span class="sxs-lookup"><span data-stu-id="a3cf2-281">0</span></span></td>
<td><span data-ttu-id="a3cf2-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="a3cf2-283">0,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="a3cf2-284">Diário</span><span class="sxs-lookup"><span data-stu-id="a3cf2-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a3cf2-285">Diário</span><span class="sxs-lookup"><span data-stu-id="a3cf2-285">Journal</span></span></th>
<th><span data-ttu-id="a3cf2-286">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="a3cf2-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="a3cf2-287">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="a3cf2-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="a3cf2-288">Versão</span><span class="sxs-lookup"><span data-stu-id="a3cf2-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-289">00002</span><span class="sxs-lookup"><span data-stu-id="a3cf2-289">00002</span></span></td>
<td><span data-ttu-id="a3cf2-290">Diário de cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="a3cf2-291">fiscal</span><span class="sxs-lookup"><span data-stu-id="a3cf2-291">Fiscal</span></span></td>
<td><span data-ttu-id="a3cf2-292">2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-292">2017</span></span></td>
<td><span data-ttu-id="a3cf2-293">Período 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-293">Period 1</span></span></td>
<td><span data-ttu-id="a3cf2-294">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="a3cf2-295">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a3cf2-296">Data contábil</span><span class="sxs-lookup"><span data-stu-id="a3cf2-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="a3cf2-297">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a3cf2-298">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-298">Cost element</span></span></th>
<th><span data-ttu-id="a3cf2-299">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-299">Cost behavior</span></span></th>
<th><span data-ttu-id="a3cf2-300">Valor</span><span class="sxs-lookup"><span data-stu-id="a3cf2-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-301">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3cf2-302">CC099</span><span class="sxs-lookup"><span data-stu-id="a3cf2-302">CC099</span></span></td>
<td><span data-ttu-id="a3cf2-303">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="a3cf2-303">Default cost center</span></span></td>
<td><span data-ttu-id="a3cf2-304">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-304">10001</span></span></td>
<td><span data-ttu-id="a3cf2-305">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-305">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-306">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-306">Fixed cost</span></span></td>
<td><span data-ttu-id="a3cf2-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-308">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3cf2-309">CC099</span><span class="sxs-lookup"><span data-stu-id="a3cf2-309">CC099</span></span></td>
<td><span data-ttu-id="a3cf2-310">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="a3cf2-310">Default cost center</span></span></td>
<td><span data-ttu-id="a3cf2-311">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-311">10001</span></span></td>
<td><span data-ttu-id="a3cf2-312">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-312">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-313">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-313">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="a3cf2-315">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3cf2-316">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a3cf2-317">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-317">Cost element</span></span></th>
<th><span data-ttu-id="a3cf2-318">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-318">Cost behavior</span></span></th>
<th><span data-ttu-id="a3cf2-319">Valor</span><span class="sxs-lookup"><span data-stu-id="a3cf2-319">Amount</span></span></th>
<th><span data-ttu-id="a3cf2-320">Data contábil</span><span class="sxs-lookup"><span data-stu-id="a3cf2-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-321">CC099</span><span class="sxs-lookup"><span data-stu-id="a3cf2-321">CC099</span></span></td>
<td><span data-ttu-id="a3cf2-322">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="a3cf2-322">Default cost center</span></span></td>
<td><span data-ttu-id="a3cf2-323">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-323">10001</span></span></td>
<td><span data-ttu-id="a3cf2-324">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-324">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-325">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-325">Fixed cost</span></span></td>
<td><span data-ttu-id="a3cf2-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-326">-1,000.00</span></span></td>
<td><span data-ttu-id="a3cf2-327">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-328">CC001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-328">CC001</span></span></td>
<td><span data-ttu-id="a3cf2-329">RH</span><span class="sxs-lookup"><span data-stu-id="a3cf2-329">HR</span></span></td>
<td><span data-ttu-id="a3cf2-330">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-330">10001</span></span></td>
<td><span data-ttu-id="a3cf2-331">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-331">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-332">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-332">Fixed cost</span></span></td>
<td><span data-ttu-id="a3cf2-333">500,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-333">500.00</span></span></td>
<td><span data-ttu-id="a3cf2-334">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-335">CC002</span><span class="sxs-lookup"><span data-stu-id="a3cf2-335">CC002</span></span></td>
<td><span data-ttu-id="a3cf2-336">Finanças</span><span class="sxs-lookup"><span data-stu-id="a3cf2-336">Finance</span></span></td>
<td><span data-ttu-id="a3cf2-337">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-337">10001</span></span></td>
<td><span data-ttu-id="a3cf2-338">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-338">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-339">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-339">Fixed cost</span></span></td>
<td><span data-ttu-id="a3cf2-340">500,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-340">500.00</span></span></td>
<td><span data-ttu-id="a3cf2-341">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-342">CC099</span><span class="sxs-lookup"><span data-stu-id="a3cf2-342">CC099</span></span></td>
<td><span data-ttu-id="a3cf2-343">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="a3cf2-343">Default cost center</span></span></td>
<td><span data-ttu-id="a3cf2-344">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-344">10001</span></span></td>
<td><span data-ttu-id="a3cf2-345">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-345">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-346">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-346">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-347">-9,000.00</span></span></td>
<td><span data-ttu-id="a3cf2-348">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-349">CC001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-349">CC001</span></span></td>
<td><span data-ttu-id="a3cf2-350">RH</span><span class="sxs-lookup"><span data-stu-id="a3cf2-350">HR</span></span></td>
<td><span data-ttu-id="a3cf2-351">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-351">10001</span></span></td>
<td><span data-ttu-id="a3cf2-352">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-352">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-353">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-353">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="a3cf2-354">1,285.71</span></span></td>
<td><span data-ttu-id="a3cf2-355">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-356">CC002</span><span class="sxs-lookup"><span data-stu-id="a3cf2-356">CC002</span></span></td>
<td><span data-ttu-id="a3cf2-357">Finanças</span><span class="sxs-lookup"><span data-stu-id="a3cf2-357">Finance</span></span></td>
<td><span data-ttu-id="a3cf2-358">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-358">10001</span></span></td>
<td><span data-ttu-id="a3cf2-359">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-359">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-360">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-360">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="a3cf2-361">7,714.29</span></span></td>
<td><span data-ttu-id="a3cf2-362">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3cf2-363">Para obter mais informações, consulte [Criar e atribuir uma política de distribuição de custos a uma unidade de controle de custos](tasks/create-assign-cost-distribution-policy-cost-control-unit.md)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="a3cf2-364">Etapa 3: Processar o cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="a3cf2-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="a3cf2-365">A taxa de custos indiretos é usada para cobrar um ou mais objetos de custos específicos.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="a3cf2-366">O encargo se baseia em uma taxa de custo predeterminada e a magnitude da básica de alocação atribuída.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="a3cf2-367">Defina a taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="a3cf2-367">Define the overhead rate</span></span>

<span data-ttu-id="a3cf2-368">O objeto de custo CC001 HR contribui para um conjunto de projetos internos.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="a3cf2-369">Um membro de dimensão estatística que é chamado de projetos de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3cf2-370">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-370">Cost object</span></span></th>
<th><span data-ttu-id="a3cf2-371">Horas</span><span class="sxs-lookup"><span data-stu-id="a3cf2-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-372">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-372">Proj 1</span></span></td>
<td><span data-ttu-id="a3cf2-373">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-373">Project 1</span></span></td>
<td><span data-ttu-id="a3cf2-374">3</span><span class="sxs-lookup"><span data-stu-id="a3cf2-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-375">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-375">Proj 2</span></span></td>
<td><span data-ttu-id="a3cf2-376">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-376">Project 2</span></span></td>
<td><span data-ttu-id="a3cf2-377">1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3cf2-378">Uma taxa de custo predeterminada da contribuição de projetos de custo foi definida.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3cf2-379">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-379">Cost object</span></span></th>
<th><span data-ttu-id="a3cf2-380">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-380">Cost element</span></span></th>
<th><span data-ttu-id="a3cf2-381">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-381">Cost behavior</span></span></th>
<th><span data-ttu-id="a3cf2-382">Unidades</span><span class="sxs-lookup"><span data-stu-id="a3cf2-382">Units</span></span></th>
<th><span data-ttu-id="a3cf2-383">Taxa</span><span class="sxs-lookup"><span data-stu-id="a3cf2-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-384">CC001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-384">CC001</span></span></td>
<td><span data-ttu-id="a3cf2-385">RH</span><span class="sxs-lookup"><span data-stu-id="a3cf2-385">HR</span></span></td>
<td><span data-ttu-id="a3cf2-386">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-386">10001</span></span></td>
<td><span data-ttu-id="a3cf2-387">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-387">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-388">1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-388">1</span></span></td>
<td><span data-ttu-id="a3cf2-389">10</span><span class="sxs-lookup"><span data-stu-id="a3cf2-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3cf2-390">A tabela a seguir mostra o resultado quando projetos de RH são aplicados como base de alocação.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3cf2-391">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-391">Cost object</span></span></th>
<th><span data-ttu-id="a3cf2-392">Magnitude</span><span class="sxs-lookup"><span data-stu-id="a3cf2-392">Magnitude</span></span></th>
<th><span data-ttu-id="a3cf2-393">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-393">Cost element</span></span></th>
<th><span data-ttu-id="a3cf2-394">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="a3cf2-394">Allocation factor</span></span></th>
<th><span data-ttu-id="a3cf2-395">Valor</span><span class="sxs-lookup"><span data-stu-id="a3cf2-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-396">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-396">Proj 1</span></span></td>
<td><span data-ttu-id="a3cf2-397">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-397">Project 1</span></span></td>
<td><span data-ttu-id="a3cf2-398">3</span><span class="sxs-lookup"><span data-stu-id="a3cf2-398">3</span></span></td>
<td><span data-ttu-id="a3cf2-399">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-399">10001</span></span></td>
<td><span data-ttu-id="a3cf2-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="a3cf2-401">30,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-402">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-402">Proj 2</span></span></td>
<td><span data-ttu-id="a3cf2-403">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-403">Project 2</span></span></td>
<td><span data-ttu-id="a3cf2-404">1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-404">1</span></span></td>
<td><span data-ttu-id="a3cf2-405">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-405">10001</span></span></td>
<td><span data-ttu-id="a3cf2-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="a3cf2-407">10,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="a3cf2-408">Diário</span><span class="sxs-lookup"><span data-stu-id="a3cf2-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a3cf2-409">Diário</span><span class="sxs-lookup"><span data-stu-id="a3cf2-409">Journal</span></span></th>
<th><span data-ttu-id="a3cf2-410">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="a3cf2-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="a3cf2-411">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="a3cf2-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="a3cf2-412">Versão</span><span class="sxs-lookup"><span data-stu-id="a3cf2-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-413">00003</span><span class="sxs-lookup"><span data-stu-id="a3cf2-413">00003</span></span></td>
<td><span data-ttu-id="a3cf2-414">Diário de cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="a3cf2-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="a3cf2-415">fiscal</span><span class="sxs-lookup"><span data-stu-id="a3cf2-415">Fiscal</span></span></td>
<td><span data-ttu-id="a3cf2-416">2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-416">2017</span></span></td>
<td><span data-ttu-id="a3cf2-417">Período 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-417">Period 1</span></span></td>
<td><span data-ttu-id="a3cf2-418">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="a3cf2-419">Entradas de diário (As entradas de diário para cálculo da taxa de custos indiretos)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a3cf2-420">Data contábil</span><span class="sxs-lookup"><span data-stu-id="a3cf2-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="a3cf2-421">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-421">Cost object</span></span></th>
<th><span data-ttu-id="a3cf2-422">Magnitude</span><span class="sxs-lookup"><span data-stu-id="a3cf2-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-423">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3cf2-424">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-424">Proj 1</span></span></td>
<td><span data-ttu-id="a3cf2-425">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="a3cf2-426">3,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-427">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3cf2-428">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-428">Proj 2</span></span></td>
<td><span data-ttu-id="a3cf2-429">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="a3cf2-430">1.00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="a3cf2-431">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3cf2-432">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a3cf2-433">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-433">Cost element</span></span></th>
<th><span data-ttu-id="a3cf2-434">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-434">Cost behavior</span></span></th>
<th><span data-ttu-id="a3cf2-435">Valor</span><span class="sxs-lookup"><span data-stu-id="a3cf2-435">Amount</span></span></th>
<th><span data-ttu-id="a3cf2-436">Data contábil</span><span class="sxs-lookup"><span data-stu-id="a3cf2-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-437">CC0001</span></span></td>
<td><span data-ttu-id="a3cf2-438">RH</span><span class="sxs-lookup"><span data-stu-id="a3cf2-438">HR</span></span></td>
<td><span data-ttu-id="a3cf2-439">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-439">10001</span></span></td>
<td><span data-ttu-id="a3cf2-440">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-440">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-441">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-441">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-442">-30.00</span></span></td>
<td><span data-ttu-id="a3cf2-443">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-444">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-444">Proj 1</span></span></td>
<td><span data-ttu-id="a3cf2-445">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="a3cf2-446">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-446">10001</span></span></td>
<td><span data-ttu-id="a3cf2-447">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-447">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-448">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-448">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-449">30,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-449">30.00</span></span></td>
<td><span data-ttu-id="a3cf2-450">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-451">CC001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-451">CC001</span></span></td>
<td><span data-ttu-id="a3cf2-452">RH</span><span class="sxs-lookup"><span data-stu-id="a3cf2-452">HR</span></span></td>
<td><span data-ttu-id="a3cf2-453">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-453">10001</span></span></td>
<td><span data-ttu-id="a3cf2-454">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-454">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-455">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-455">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-456">-10.00</span></span></td>
<td><span data-ttu-id="a3cf2-457">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-458">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-458">Proj 2</span></span></td>
<td><span data-ttu-id="a3cf2-459">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="a3cf2-460">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-460">10001</span></span></td>
<td><span data-ttu-id="a3cf2-461">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-461">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-462">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-462">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-463">10,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-463">10.00</span></span></td>
<td><span data-ttu-id="a3cf2-464">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3cf2-465">Para obter mais informações, consulte [Realizar cálculo de custos indiretos](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="a3cf2-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="a3cf2-466">Etapa 4: Processar o cálculo de alocação de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="a3cf2-467">A alocação é usada para alocar o saldo de um objeto de custo a outros objetos de custo pela aplicação de uma base de alocação.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="a3cf2-468">O Finance oferece suporte ao método de alocação recíproco.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="a3cf2-469">No método de alocação recíproco, os serviços mútuos que os objetos de custo auxiliar trocam são totalmente reconhecidos.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="a3cf2-470">O sistema determina automaticamente a ordem correta realizar as alocações.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="a3cf2-471">O saldo de um objeto de custo é alocado por uma base de alocação única.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="a3cf2-472">As alocações entre as dimensões de objetos de custo e os respectivos membros são suportadas.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="a3cf2-473">A ordem de alocação é controlada pela unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="a3cf2-474">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="a3cf2-475">Defina a alocação de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-475">Define the cost allocation</span></span>

<span data-ttu-id="a3cf2-476">Aqui está um exemplo simples que explica como você pode rastrear o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="a3cf2-477">O objeto de custo previsto CC001 HR contribui a vários objetos de custo previsto.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="a3cf2-478">Um membro de dimensão estatística que é chamado de serviços de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3cf2-479">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-479">Cost object</span></span></th>
<th><span data-ttu-id="a3cf2-480">Serviços de RH</span><span class="sxs-lookup"><span data-stu-id="a3cf2-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-481">CC002</span><span class="sxs-lookup"><span data-stu-id="a3cf2-481">CC002</span></span></td>
<td><span data-ttu-id="a3cf2-482">Finanças</span><span class="sxs-lookup"><span data-stu-id="a3cf2-482">Finance</span></span></td>
<td><span data-ttu-id="a3cf2-483">35</span><span class="sxs-lookup"><span data-stu-id="a3cf2-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-484">CC003</span><span class="sxs-lookup"><span data-stu-id="a3cf2-484">CC003</span></span></td>
<td><span data-ttu-id="a3cf2-485">Montagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-485">Assembly</span></span></td>
<td><span data-ttu-id="a3cf2-486">55</span><span class="sxs-lookup"><span data-stu-id="a3cf2-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-487">CC004</span><span class="sxs-lookup"><span data-stu-id="a3cf2-487">CC004</span></span></td>
<td><span data-ttu-id="a3cf2-488">Embalagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-488">Packaging</span></span></td>
<td><span data-ttu-id="a3cf2-489">10</span><span class="sxs-lookup"><span data-stu-id="a3cf2-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3cf2-490">O objeto de custo CC002 Finanças contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="a3cf2-491">Um membro de dimensão estatística que é chamado de serviços de Finanças foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3cf2-492">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-492">Cost object</span></span></th>
<th><span data-ttu-id="a3cf2-493">Serviços financeiros</span><span class="sxs-lookup"><span data-stu-id="a3cf2-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-494">CC003</span><span class="sxs-lookup"><span data-stu-id="a3cf2-494">CC003</span></span></td>
<td><span data-ttu-id="a3cf2-495">Montagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-495">Assembly</span></span></td>
<td><span data-ttu-id="a3cf2-496">65</span><span class="sxs-lookup"><span data-stu-id="a3cf2-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-497">CC004</span><span class="sxs-lookup"><span data-stu-id="a3cf2-497">CC004</span></span></td>
<td><span data-ttu-id="a3cf2-498">Embalagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-498">Packaging</span></span></td>
<td><span data-ttu-id="a3cf2-499">35</span><span class="sxs-lookup"><span data-stu-id="a3cf2-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3cf2-500">O objeto de custo CC003 Montagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="a3cf2-501">Um membro de dimensão estatística que é chamado de serviços de Montagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3cf2-502">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-502">Cost object</span></span></th>
<th><span data-ttu-id="a3cf2-503">Serviços de montagem (horas)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-504">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-504">Prod 1</span></span></td>
<td><span data-ttu-id="a3cf2-505">Produto 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-505">Product 1</span></span></td>
<td><span data-ttu-id="a3cf2-506">60</span><span class="sxs-lookup"><span data-stu-id="a3cf2-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-507">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-507">Prod 2</span></span></td>
<td><span data-ttu-id="a3cf2-508">Produto 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-508">Product 2</span></span></td>
<td><span data-ttu-id="a3cf2-509">20</span><span class="sxs-lookup"><span data-stu-id="a3cf2-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3cf2-510">O objeto de custo CC004 Embalagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="a3cf2-511">Um membro de dimensão estatística que é chamado de serviços de Embalagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3cf2-512">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-512">Cost object</span></span></th>
<th><span data-ttu-id="a3cf2-513">Serviços de embalagem (horas)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-514">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-514">Prod 1</span></span></td>
<td><span data-ttu-id="a3cf2-515">Produto 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-515">Product 1</span></span></td>
<td><span data-ttu-id="a3cf2-516">80</span><span class="sxs-lookup"><span data-stu-id="a3cf2-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-517">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-517">Prod 2</span></span></td>
<td><span data-ttu-id="a3cf2-518">Produto 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-518">Product 2</span></span></td>
<td><span data-ttu-id="a3cf2-519">15</span><span class="sxs-lookup"><span data-stu-id="a3cf2-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="a3cf2-520">Medidas estatísticas, como as horas de produção que um produto consome, podem ser derivadas dos dados de origem.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="a3cf2-521">Para obter mais informações, consulte [Modelo de provedor de medidas estatísticas](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="a3cf2-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="a3cf2-522">A tabela a seguir mostra o resultado quando os serviços de RH são aplicados como base de alocação para custos totais (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3cf2-523">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-523">Cost object</span></span></th>
<th><span data-ttu-id="a3cf2-524">Magnitude</span><span class="sxs-lookup"><span data-stu-id="a3cf2-524">Magnitude</span></span></th>
<th><span data-ttu-id="a3cf2-525">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="a3cf2-525">Allocation factor</span></span></th>
<th><span data-ttu-id="a3cf2-526">Valor</span><span class="sxs-lookup"><span data-stu-id="a3cf2-526">Amount</span></span></th>
<th><span data-ttu-id="a3cf2-527">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-528">CC002</span><span class="sxs-lookup"><span data-stu-id="a3cf2-528">CC002</span></span></td>
<td><span data-ttu-id="a3cf2-529">Finanças</span><span class="sxs-lookup"><span data-stu-id="a3cf2-529">Finance</span></span></td>
<td><span data-ttu-id="a3cf2-530">35</span><span class="sxs-lookup"><span data-stu-id="a3cf2-530">35</span></span></td>
<td><span data-ttu-id="a3cf2-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="a3cf2-532">175.00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-532">175.00</span></span></td>
<td><span data-ttu-id="a3cf2-533">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-534">CC003</span><span class="sxs-lookup"><span data-stu-id="a3cf2-534">CC003</span></span></td>
<td><span data-ttu-id="a3cf2-535">Montagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-535">Assembly</span></span></td>
<td><span data-ttu-id="a3cf2-536">55</span><span class="sxs-lookup"><span data-stu-id="a3cf2-536">55</span></span></td>
<td><span data-ttu-id="a3cf2-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="a3cf2-538">275.00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-538">275.00</span></span></td>
<td><span data-ttu-id="a3cf2-539">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-540">CC004</span><span class="sxs-lookup"><span data-stu-id="a3cf2-540">CC004</span></span></td>
<td><span data-ttu-id="a3cf2-541">Embalagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-541">Packaging</span></span></td>
<td><span data-ttu-id="a3cf2-542">10</span><span class="sxs-lookup"><span data-stu-id="a3cf2-542">10</span></span></td>
<td><span data-ttu-id="a3cf2-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="a3cf2-544">50,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-544">50.00</span></span></td>
<td><span data-ttu-id="a3cf2-545">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-546">CC002</span><span class="sxs-lookup"><span data-stu-id="a3cf2-546">CC002</span></span></td>
<td><span data-ttu-id="a3cf2-547">Finanças</span><span class="sxs-lookup"><span data-stu-id="a3cf2-547">Finance</span></span></td>
<td><span data-ttu-id="a3cf2-548">35</span><span class="sxs-lookup"><span data-stu-id="a3cf2-548">35</span></span></td>
<td><span data-ttu-id="a3cf2-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="a3cf2-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="a3cf2-550">436.00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-550">436.00</span></span></td>
<td><span data-ttu-id="a3cf2-551">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-552">CC003</span><span class="sxs-lookup"><span data-stu-id="a3cf2-552">CC003</span></span></td>
<td><span data-ttu-id="a3cf2-553">Montagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-553">Assembly</span></span></td>
<td><span data-ttu-id="a3cf2-554">55</span><span class="sxs-lookup"><span data-stu-id="a3cf2-554">55</span></span></td>
<td><span data-ttu-id="a3cf2-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="a3cf2-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="a3cf2-556">685.14</span><span class="sxs-lookup"><span data-stu-id="a3cf2-556">685.14</span></span></td>
<td><span data-ttu-id="a3cf2-557">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-558">CC004</span><span class="sxs-lookup"><span data-stu-id="a3cf2-558">CC004</span></span></td>
<td><span data-ttu-id="a3cf2-559">Embalagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-559">Packaging</span></span></td>
<td><span data-ttu-id="a3cf2-560">10</span><span class="sxs-lookup"><span data-stu-id="a3cf2-560">10</span></span></td>
<td><span data-ttu-id="a3cf2-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="a3cf2-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="a3cf2-562">124.57</span><span class="sxs-lookup"><span data-stu-id="a3cf2-562">124.57</span></span></td>
<td><span data-ttu-id="a3cf2-563">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3cf2-564">A tabela a seguir mostra o resultado quando os serviços financeiros são aplicados como base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3cf2-565">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-565">Cost object</span></span></th>
<th><span data-ttu-id="a3cf2-566">Magnitude</span><span class="sxs-lookup"><span data-stu-id="a3cf2-566">Magnitude</span></span></th>
<th><span data-ttu-id="a3cf2-567">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="a3cf2-567">Allocation factor</span></span></th>
<th><span data-ttu-id="a3cf2-568">Valor</span><span class="sxs-lookup"><span data-stu-id="a3cf2-568">Amount</span></span></th>
<th><span data-ttu-id="a3cf2-569">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-570">CC003</span><span class="sxs-lookup"><span data-stu-id="a3cf2-570">CC003</span></span></td>
<td><span data-ttu-id="a3cf2-571">Montagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-571">Assembly</span></span></td>
<td><span data-ttu-id="a3cf2-572">65</span><span class="sxs-lookup"><span data-stu-id="a3cf2-572">65</span></span></td>
<td><span data-ttu-id="a3cf2-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="a3cf2-574">438.75</span><span class="sxs-lookup"><span data-stu-id="a3cf2-574">438.75</span></span></td>
<td><span data-ttu-id="a3cf2-575">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-576">CC004</span><span class="sxs-lookup"><span data-stu-id="a3cf2-576">CC004</span></span></td>
<td><span data-ttu-id="a3cf2-577">Embalagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-577">Packaging</span></span></td>
<td><span data-ttu-id="a3cf2-578">35</span><span class="sxs-lookup"><span data-stu-id="a3cf2-578">35</span></span></td>
<td><span data-ttu-id="a3cf2-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="a3cf2-580">236.25</span><span class="sxs-lookup"><span data-stu-id="a3cf2-580">236.25</span></span></td>
<td><span data-ttu-id="a3cf2-581">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-582">CC003</span><span class="sxs-lookup"><span data-stu-id="a3cf2-582">CC003</span></span></td>
<td><span data-ttu-id="a3cf2-583">Montagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-583">Assembly</span></span></td>
<td><span data-ttu-id="a3cf2-584">65</span><span class="sxs-lookup"><span data-stu-id="a3cf2-584">65</span></span></td>
<td><span data-ttu-id="a3cf2-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="a3cf2-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="a3cf2-586">5,297.69</span></span></td>
<td><span data-ttu-id="a3cf2-587">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-588">CC004</span><span class="sxs-lookup"><span data-stu-id="a3cf2-588">CC004</span></span></td>
<td><span data-ttu-id="a3cf2-589">Embalagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-589">Packaging</span></span></td>
<td><span data-ttu-id="a3cf2-590">35</span><span class="sxs-lookup"><span data-stu-id="a3cf2-590">35</span></span></td>
<td><span data-ttu-id="a3cf2-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="a3cf2-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="a3cf2-592">2,852.60</span></span></td>
<td><span data-ttu-id="a3cf2-593">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3cf2-594">A tabela a seguir mostra o resultado quando os serviços de Montagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3cf2-595">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-595">Cost object</span></span></th>
<th><span data-ttu-id="a3cf2-596">Magnitude</span><span class="sxs-lookup"><span data-stu-id="a3cf2-596">Magnitude</span></span></th>
<th><span data-ttu-id="a3cf2-597">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="a3cf2-597">Allocation factor</span></span></th>
<th><span data-ttu-id="a3cf2-598">Valor</span><span class="sxs-lookup"><span data-stu-id="a3cf2-598">Amount</span></span></th>
<th><span data-ttu-id="a3cf2-599">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-600">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-600">Prod 1</span></span></td>
<td><span data-ttu-id="a3cf2-601">Produto 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-601">Product 1</span></span></td>
<td><span data-ttu-id="a3cf2-602">60</span><span class="sxs-lookup"><span data-stu-id="a3cf2-602">60</span></span></td>
<td><span data-ttu-id="a3cf2-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="a3cf2-604">535.31</span><span class="sxs-lookup"><span data-stu-id="a3cf2-604">535.31</span></span></td>
<td><span data-ttu-id="a3cf2-605">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-606">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-606">Prod 2</span></span></td>
<td><span data-ttu-id="a3cf2-607">Produto 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-607">Product 2</span></span></td>
<td><span data-ttu-id="a3cf2-608">20</span><span class="sxs-lookup"><span data-stu-id="a3cf2-608">20</span></span></td>
<td><span data-ttu-id="a3cf2-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="a3cf2-610">178.44</span><span class="sxs-lookup"><span data-stu-id="a3cf2-610">178.44</span></span></td>
<td><span data-ttu-id="a3cf2-611">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-612">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-612">Prod 1</span></span></td>
<td><span data-ttu-id="a3cf2-613">Produto 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-613">Product 1</span></span></td>
<td><span data-ttu-id="a3cf2-614">60</span><span class="sxs-lookup"><span data-stu-id="a3cf2-614">60</span></span></td>
<td><span data-ttu-id="a3cf2-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="a3cf2-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="a3cf2-616">4,487.12</span></span></td>
<td><span data-ttu-id="a3cf2-617">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-618">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-618">Prod 2</span></span></td>
<td><span data-ttu-id="a3cf2-619">Produto 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-619">Product 2</span></span></td>
<td><span data-ttu-id="a3cf2-620">20</span><span class="sxs-lookup"><span data-stu-id="a3cf2-620">20</span></span></td>
<td><span data-ttu-id="a3cf2-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="a3cf2-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="a3cf2-622">1,495.71</span></span></td>
<td><span data-ttu-id="a3cf2-623">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3cf2-624">A tabela a seguir mostra o resultado quando os serviços de Embalagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3cf2-625">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-625">Cost object</span></span></th>
<th><span data-ttu-id="a3cf2-626">Magnitude</span><span class="sxs-lookup"><span data-stu-id="a3cf2-626">Magnitude</span></span></th>
<th><span data-ttu-id="a3cf2-627">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="a3cf2-627">Allocation factor</span></span></th>
<th><span data-ttu-id="a3cf2-628">Valor</span><span class="sxs-lookup"><span data-stu-id="a3cf2-628">Amount</span></span></th>
<th><span data-ttu-id="a3cf2-629">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-630">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-630">Prod 1</span></span></td>
<td><span data-ttu-id="a3cf2-631">Produto 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-631">Product 1</span></span></td>
<td><span data-ttu-id="a3cf2-632">80</span><span class="sxs-lookup"><span data-stu-id="a3cf2-632">80</span></span></td>
<td><span data-ttu-id="a3cf2-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="a3cf2-634">241.05</span><span class="sxs-lookup"><span data-stu-id="a3cf2-634">241.05</span></span></td>
<td><span data-ttu-id="a3cf2-635">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-636">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-636">Prod 2</span></span></td>
<td><span data-ttu-id="a3cf2-637">Produto 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-637">Product 2</span></span></td>
<td><span data-ttu-id="a3cf2-638">15</span><span class="sxs-lookup"><span data-stu-id="a3cf2-638">15</span></span></td>
<td><span data-ttu-id="a3cf2-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="a3cf2-640">45.20</span><span class="sxs-lookup"><span data-stu-id="a3cf2-640">45.20</span></span></td>
<td><span data-ttu-id="a3cf2-641">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-642">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-642">Prod 1</span></span></td>
<td><span data-ttu-id="a3cf2-643">Produto 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-643">Product 1</span></span></td>
<td><span data-ttu-id="a3cf2-644">80</span><span class="sxs-lookup"><span data-stu-id="a3cf2-644">80</span></span></td>
<td><span data-ttu-id="a3cf2-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="a3cf2-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="a3cf2-646">2,507.09</span></span></td>
<td><span data-ttu-id="a3cf2-647">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-648">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-648">Prod 2</span></span></td>
<td><span data-ttu-id="a3cf2-649">Produto 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-649">Product 2</span></span></td>
<td><span data-ttu-id="a3cf2-650">15</span><span class="sxs-lookup"><span data-stu-id="a3cf2-650">15</span></span></td>
<td><span data-ttu-id="a3cf2-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="a3cf2-652">470.08</span><span class="sxs-lookup"><span data-stu-id="a3cf2-652">470.08</span></span></td>
<td><span data-ttu-id="a3cf2-653">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="a3cf2-654">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="a3cf2-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a3cf2-655">Diário</span><span class="sxs-lookup"><span data-stu-id="a3cf2-655">Journal</span></span></th>
<th><span data-ttu-id="a3cf2-656">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="a3cf2-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="a3cf2-657">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="a3cf2-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="a3cf2-658">Versão</span><span class="sxs-lookup"><span data-stu-id="a3cf2-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-659">00004</span><span class="sxs-lookup"><span data-stu-id="a3cf2-659">00004</span></span></td>
<td><span data-ttu-id="a3cf2-660">Diário de alocação de custos</span><span class="sxs-lookup"><span data-stu-id="a3cf2-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="a3cf2-661">fiscal</span><span class="sxs-lookup"><span data-stu-id="a3cf2-661">Fiscal</span></span></td>
<td><span data-ttu-id="a3cf2-662">2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-662">2017</span></span></td>
<td><span data-ttu-id="a3cf2-663">Período 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-663">Period 1</span></span></td>
<td><span data-ttu-id="a3cf2-664">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="a3cf2-665">Linhas do diário</span><span class="sxs-lookup"><span data-stu-id="a3cf2-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a3cf2-666">Data contábil</span><span class="sxs-lookup"><span data-stu-id="a3cf2-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="a3cf2-667">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a3cf2-668">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-668">Cost element</span></span></th>
<th><span data-ttu-id="a3cf2-669">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-669">Cost behavior</span></span></th>
<th><span data-ttu-id="a3cf2-670">Valor</span><span class="sxs-lookup"><span data-stu-id="a3cf2-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-671">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3cf2-672">CC001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-672">CC001</span></span></td>
<td><span data-ttu-id="a3cf2-673">RH</span><span class="sxs-lookup"><span data-stu-id="a3cf2-673">HR</span></span></td>
<td><span data-ttu-id="a3cf2-674">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-674">10001</span></span></td>
<td><span data-ttu-id="a3cf2-675">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-675">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-676">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-676">Fixed cost</span></span></td>
<td><span data-ttu-id="a3cf2-677">500,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-678">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3cf2-679">CC001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-679">CC001</span></span></td>
<td><span data-ttu-id="a3cf2-680">RH</span><span class="sxs-lookup"><span data-stu-id="a3cf2-680">HR</span></span></td>
<td><span data-ttu-id="a3cf2-681">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-681">10001</span></span></td>
<td><span data-ttu-id="a3cf2-682">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-682">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-683">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-683">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="a3cf2-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-685">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3cf2-686">CC002</span><span class="sxs-lookup"><span data-stu-id="a3cf2-686">CC002</span></span></td>
<td><span data-ttu-id="a3cf2-687">Finanças</span><span class="sxs-lookup"><span data-stu-id="a3cf2-687">Finance</span></span></td>
<td><span data-ttu-id="a3cf2-688">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-688">10001</span></span></td>
<td><span data-ttu-id="a3cf2-689">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-689">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-690">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-690">Fixed cost</span></span></td>
<td><span data-ttu-id="a3cf2-691">675.00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-692">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3cf2-693">CC002</span><span class="sxs-lookup"><span data-stu-id="a3cf2-693">CC002</span></span></td>
<td><span data-ttu-id="a3cf2-694">Finanças</span><span class="sxs-lookup"><span data-stu-id="a3cf2-694">Finance</span></span></td>
<td><span data-ttu-id="a3cf2-695">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-695">10001</span></span></td>
<td><span data-ttu-id="a3cf2-696">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-696">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-697">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-697">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="a3cf2-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-699">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3cf2-700">CC003</span><span class="sxs-lookup"><span data-stu-id="a3cf2-700">CC003</span></span></td>
<td><span data-ttu-id="a3cf2-701">Montagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-701">Assembly</span></span></td>
<td><span data-ttu-id="a3cf2-702">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-702">10001</span></span></td>
<td><span data-ttu-id="a3cf2-703">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-703">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-704">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-704">Fixed cost</span></span></td>
<td><span data-ttu-id="a3cf2-705">713.75</span><span class="sxs-lookup"><span data-stu-id="a3cf2-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-706">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3cf2-707">CC003</span><span class="sxs-lookup"><span data-stu-id="a3cf2-707">CC003</span></span></td>
<td><span data-ttu-id="a3cf2-708">Montagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-708">Assembly</span></span></td>
<td><span data-ttu-id="a3cf2-709">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-709">10001</span></span></td>
<td><span data-ttu-id="a3cf2-710">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-710">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-711">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-711">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="a3cf2-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-713">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3cf2-714">CC003</span><span class="sxs-lookup"><span data-stu-id="a3cf2-714">CC003</span></span></td>
<td><span data-ttu-id="a3cf2-715">Embalagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-715">Packaging</span></span></td>
<td><span data-ttu-id="a3cf2-716">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-716">10001</span></span></td>
<td><span data-ttu-id="a3cf2-717">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-717">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-718">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-718">Fixed cost</span></span></td>
<td><span data-ttu-id="a3cf2-719">286.25</span><span class="sxs-lookup"><span data-stu-id="a3cf2-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-720">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3cf2-721">CC003</span><span class="sxs-lookup"><span data-stu-id="a3cf2-721">CC003</span></span></td>
<td><span data-ttu-id="a3cf2-722">Embalagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-722">Packaging</span></span></td>
<td><span data-ttu-id="a3cf2-723">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-723">10001</span></span></td>
<td><span data-ttu-id="a3cf2-724">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-724">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-725">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-725">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="a3cf2-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-727">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3cf2-728">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-728">Prod 1</span></span></td>
<td><span data-ttu-id="a3cf2-729">Produto 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-729">Product 1</span></span></td>
<td><span data-ttu-id="a3cf2-730">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-730">10001</span></span></td>
<td><span data-ttu-id="a3cf2-731">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-731">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-732">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-732">Fixed cost</span></span></td>
<td><span data-ttu-id="a3cf2-733">776.36</span><span class="sxs-lookup"><span data-stu-id="a3cf2-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-734">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3cf2-735">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-735">Prod 1</span></span></td>
<td><span data-ttu-id="a3cf2-736">Produto 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-736">Product 1</span></span></td>
<td><span data-ttu-id="a3cf2-737">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-737">10001</span></span></td>
<td><span data-ttu-id="a3cf2-738">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-738">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-739">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-739">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="a3cf2-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-741">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3cf2-742">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-742">Prod 2</span></span></td>
<td><span data-ttu-id="a3cf2-743">Produto 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-743">Product 1</span></span></td>
<td><span data-ttu-id="a3cf2-744">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-744">10001</span></span></td>
<td><span data-ttu-id="a3cf2-745">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-745">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-746">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-746">Fixed cost</span></span></td>
<td><span data-ttu-id="a3cf2-747">223.64</span><span class="sxs-lookup"><span data-stu-id="a3cf2-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-748">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3cf2-749">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-749">Prod 2</span></span></td>
<td><span data-ttu-id="a3cf2-750">Produto 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-750">Product 1</span></span></td>
<td><span data-ttu-id="a3cf2-751">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-751">10001</span></span></td>
<td><span data-ttu-id="a3cf2-752">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-752">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-753">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-753">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="a3cf2-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="a3cf2-755">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3cf2-756">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a3cf2-757">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-757">Cost element</span></span></th>
<th><span data-ttu-id="a3cf2-758">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-758">Cost behavior</span></span></th>
<th><span data-ttu-id="a3cf2-759">Valor</span><span class="sxs-lookup"><span data-stu-id="a3cf2-759">Amount</span></span></th>
<th><span data-ttu-id="a3cf2-760">Data contábil</span><span class="sxs-lookup"><span data-stu-id="a3cf2-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3cf2-761">CC001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-761">CC001</span></span></td>
<td><span data-ttu-id="a3cf2-762">RH</span><span class="sxs-lookup"><span data-stu-id="a3cf2-762">HR</span></span></td>
<td><span data-ttu-id="a3cf2-763">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-763">10001</span></span></td>
<td><span data-ttu-id="a3cf2-764">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-764">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-765">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-765">Fixed cost</span></span></td>
<td><span data-ttu-id="a3cf2-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-766">-500.00</span></span></td>
<td><span data-ttu-id="a3cf2-767">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-768">CC002</span><span class="sxs-lookup"><span data-stu-id="a3cf2-768">CC002</span></span></td>
<td><span data-ttu-id="a3cf2-769">Finanças</span><span class="sxs-lookup"><span data-stu-id="a3cf2-769">Finance</span></span></td>
<td><span data-ttu-id="a3cf2-770">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-770">10001</span></span></td>
<td><span data-ttu-id="a3cf2-771">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-771">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-772">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-772">Fixed cost</span></span></td>
<td><span data-ttu-id="a3cf2-773">175.00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-773">175.00</span></span></td>
<td><span data-ttu-id="a3cf2-774">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-775">CC003</span><span class="sxs-lookup"><span data-stu-id="a3cf2-775">CC003</span></span></td>
<td><span data-ttu-id="a3cf2-776">Montagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-776">Assembly</span></span></td>
<td><span data-ttu-id="a3cf2-777">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-777">10001</span></span></td>
<td><span data-ttu-id="a3cf2-778">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-778">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-779">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-779">Fixed cost</span></span></td>
<td><span data-ttu-id="a3cf2-780">275.00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-780">275.00</span></span></td>
<td><span data-ttu-id="a3cf2-781">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-782">CC004</span><span class="sxs-lookup"><span data-stu-id="a3cf2-782">CC004</span></span></td>
<td><span data-ttu-id="a3cf2-783">Embalagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-783">Packaging</span></span></td>
<td><span data-ttu-id="a3cf2-784">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-784">10001</span></span></td>
<td><span data-ttu-id="a3cf2-785">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-785">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-786">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-786">Fixed cost</span></span></td>
<td><span data-ttu-id="a3cf2-787">50,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-787">50,00</span></span></td>
<td><span data-ttu-id="a3cf2-788">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-789">CC001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-789">CC001</span></span></td>
<td><span data-ttu-id="a3cf2-790">RH</span><span class="sxs-lookup"><span data-stu-id="a3cf2-790">HR</span></span></td>
<td><span data-ttu-id="a3cf2-791">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-791">10001</span></span></td>
<td><span data-ttu-id="a3cf2-792">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-792">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-793">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-793">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="a3cf2-794">-1,245.71</span></span></td>
<td><span data-ttu-id="a3cf2-795">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-796">CC002</span><span class="sxs-lookup"><span data-stu-id="a3cf2-796">CC002</span></span></td>
<td><span data-ttu-id="a3cf2-797">Finanças</span><span class="sxs-lookup"><span data-stu-id="a3cf2-797">Finance</span></span></td>
<td><span data-ttu-id="a3cf2-798">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-798">10001</span></span></td>
<td><span data-ttu-id="a3cf2-799">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-799">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-800">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-800">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-801">436.00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-801">436.00</span></span></td>
<td><span data-ttu-id="a3cf2-802">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-803">CC003</span><span class="sxs-lookup"><span data-stu-id="a3cf2-803">CC003</span></span></td>
<td><span data-ttu-id="a3cf2-804">Montagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-804">Assembly</span></span></td>
<td><span data-ttu-id="a3cf2-805">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-805">10001</span></span></td>
<td><span data-ttu-id="a3cf2-806">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-806">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-807">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-807">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-808">685.14</span><span class="sxs-lookup"><span data-stu-id="a3cf2-808">685.14</span></span></td>
<td><span data-ttu-id="a3cf2-809">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-810">CC004</span><span class="sxs-lookup"><span data-stu-id="a3cf2-810">CC004</span></span></td>
<td><span data-ttu-id="a3cf2-811">Embalagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-811">Packaging</span></span></td>
<td><span data-ttu-id="a3cf2-812">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-812">10001</span></span></td>
<td><span data-ttu-id="a3cf2-813">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-813">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-814">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-814">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-815">124.57</span><span class="sxs-lookup"><span data-stu-id="a3cf2-815">124.57</span></span></td>
<td><span data-ttu-id="a3cf2-816">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-817">CC002</span><span class="sxs-lookup"><span data-stu-id="a3cf2-817">CC002</span></span></td>
<td><span data-ttu-id="a3cf2-818">Finanças</span><span class="sxs-lookup"><span data-stu-id="a3cf2-818">Finance</span></span></td>
<td><span data-ttu-id="a3cf2-819">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-819">10001</span></span></td>
<td><span data-ttu-id="a3cf2-820">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-820">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-821">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-821">Fixed cost</span></span></td>
<td><span data-ttu-id="a3cf2-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-822">-675.00</span></span></td>
<td><span data-ttu-id="a3cf2-823">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-824">CC003</span><span class="sxs-lookup"><span data-stu-id="a3cf2-824">CC003</span></span></td>
<td><span data-ttu-id="a3cf2-825">Montagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-825">Assembly</span></span></td>
<td><span data-ttu-id="a3cf2-826">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-826">10001</span></span></td>
<td><span data-ttu-id="a3cf2-827">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-827">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-828">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-828">Fixed cost</span></span></td>
<td><span data-ttu-id="a3cf2-829">438.75</span><span class="sxs-lookup"><span data-stu-id="a3cf2-829">438.75</span></span></td>
<td><span data-ttu-id="a3cf2-830">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-831">CC004</span><span class="sxs-lookup"><span data-stu-id="a3cf2-831">CC004</span></span></td>
<td><span data-ttu-id="a3cf2-832">Embalagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-832">Packaging</span></span></td>
<td><span data-ttu-id="a3cf2-833">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-833">10001</span></span></td>
<td><span data-ttu-id="a3cf2-834">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-834">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-835">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-835">Fixed cost</span></span></td>
<td><span data-ttu-id="a3cf2-836">236.25</span><span class="sxs-lookup"><span data-stu-id="a3cf2-836">236.25</span></span></td>
<td><span data-ttu-id="a3cf2-837">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-838">CC002</span><span class="sxs-lookup"><span data-stu-id="a3cf2-838">CC002</span></span></td>
<td><span data-ttu-id="a3cf2-839">Finanças</span><span class="sxs-lookup"><span data-stu-id="a3cf2-839">Finance</span></span></td>
<td><span data-ttu-id="a3cf2-840">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-840">10001</span></span></td>
<td><span data-ttu-id="a3cf2-841">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-841">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-842">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-842">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="a3cf2-843">-8,150.29</span></span></td>
<td><span data-ttu-id="a3cf2-844">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-845">CC003</span><span class="sxs-lookup"><span data-stu-id="a3cf2-845">CC003</span></span></td>
<td><span data-ttu-id="a3cf2-846">Montagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-846">Assembly</span></span></td>
<td><span data-ttu-id="a3cf2-847">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-847">10001</span></span></td>
<td><span data-ttu-id="a3cf2-848">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-848">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-849">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-849">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="a3cf2-850">5,297.69</span></span></td>
<td><span data-ttu-id="a3cf2-851">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-852">CC004</span><span class="sxs-lookup"><span data-stu-id="a3cf2-852">CC004</span></span></td>
<td><span data-ttu-id="a3cf2-853">Embalagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-853">Packaging</span></span></td>
<td><span data-ttu-id="a3cf2-854">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-854">10001</span></span></td>
<td><span data-ttu-id="a3cf2-855">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-855">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-856">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-856">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="a3cf2-857">2,852.60</span></span></td>
<td><span data-ttu-id="a3cf2-858">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-859">CC003</span><span class="sxs-lookup"><span data-stu-id="a3cf2-859">CC003</span></span></td>
<td><span data-ttu-id="a3cf2-860">Montagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-860">Assembly</span></span></td>
<td><span data-ttu-id="a3cf2-861">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-861">10001</span></span></td>
<td><span data-ttu-id="a3cf2-862">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-862">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-863">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-863">Fixed cost</span></span></td>
<td><span data-ttu-id="a3cf2-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="a3cf2-864">-713.75</span></span></td>
<td><span data-ttu-id="a3cf2-865">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-866">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-866">Prod 1</span></span></td>
<td><span data-ttu-id="a3cf2-867">Produto 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-867">Product 1</span></span></td>
<td><span data-ttu-id="a3cf2-868">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-868">10001</span></span></td>
<td><span data-ttu-id="a3cf2-869">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-869">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-870">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-870">Fixed cost</span></span></td>
<td><span data-ttu-id="a3cf2-871">535.31</span><span class="sxs-lookup"><span data-stu-id="a3cf2-871">535.31</span></span></td>
<td><span data-ttu-id="a3cf2-872">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-873">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-873">Prod 2</span></span></td>
<td><span data-ttu-id="a3cf2-874">Produto 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-874">Product 2</span></span></td>
<td><span data-ttu-id="a3cf2-875">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-875">10001</span></span></td>
<td><span data-ttu-id="a3cf2-876">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-876">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-877">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-877">Fixed cost</span></span></td>
<td><span data-ttu-id="a3cf2-878">178.44</span><span class="sxs-lookup"><span data-stu-id="a3cf2-878">178.44</span></span></td>
<td><span data-ttu-id="a3cf2-879">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-880">CC003</span><span class="sxs-lookup"><span data-stu-id="a3cf2-880">CC003</span></span></td>
<td><span data-ttu-id="a3cf2-881">Montagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-881">Assembly</span></span></td>
<td><span data-ttu-id="a3cf2-882">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-882">10001</span></span></td>
<td><span data-ttu-id="a3cf2-883">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-883">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-884">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-884">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="a3cf2-885">-5,982.83</span></span></td>
<td><span data-ttu-id="a3cf2-886">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-887">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-887">Prod 1</span></span></td>
<td><span data-ttu-id="a3cf2-888">Produto 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-888">Product 1</span></span></td>
<td><span data-ttu-id="a3cf2-889">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-889">10001</span></span></td>
<td><span data-ttu-id="a3cf2-890">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-890">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-891">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-891">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="a3cf2-892">4,487.12</span></span></td>
<td><span data-ttu-id="a3cf2-893">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-894">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-894">Prod 2</span></span></td>
<td><span data-ttu-id="a3cf2-895">Produto 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-895">Product 2</span></span></td>
<td><span data-ttu-id="a3cf2-896">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-896">10001</span></span></td>
<td><span data-ttu-id="a3cf2-897">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-897">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-898">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-898">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="a3cf2-899">1,495.71</span></span></td>
<td><span data-ttu-id="a3cf2-900">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-901">CC003</span><span class="sxs-lookup"><span data-stu-id="a3cf2-901">CC003</span></span></td>
<td><span data-ttu-id="a3cf2-902">Montagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-902">Assembly</span></span></td>
<td><span data-ttu-id="a3cf2-903">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-903">10001</span></span></td>
<td><span data-ttu-id="a3cf2-904">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-904">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-905">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-905">Fixed cost</span></span></td>
<td><span data-ttu-id="a3cf2-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="a3cf2-906">-286.25</span></span></td>
<td><span data-ttu-id="a3cf2-907">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-908">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-908">Prod 1</span></span></td>
<td><span data-ttu-id="a3cf2-909">Produto 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-909">Product 1</span></span></td>
<td><span data-ttu-id="a3cf2-910">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-910">10001</span></span></td>
<td><span data-ttu-id="a3cf2-911">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-911">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-912">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-912">Fixed cost</span></span></td>
<td><span data-ttu-id="a3cf2-913">241.05</span><span class="sxs-lookup"><span data-stu-id="a3cf2-913">241.05</span></span></td>
<td><span data-ttu-id="a3cf2-914">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-915">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-915">Prod 2</span></span></td>
<td><span data-ttu-id="a3cf2-916">Produto 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-916">Product 2</span></span></td>
<td><span data-ttu-id="a3cf2-917">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-917">10001</span></span></td>
<td><span data-ttu-id="a3cf2-918">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-918">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-919">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-919">Fixed cost</span></span></td>
<td><span data-ttu-id="a3cf2-920">45.20</span><span class="sxs-lookup"><span data-stu-id="a3cf2-920">45.20</span></span></td>
<td><span data-ttu-id="a3cf2-921">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-922">CC003</span><span class="sxs-lookup"><span data-stu-id="a3cf2-922">CC003</span></span></td>
<td><span data-ttu-id="a3cf2-923">Montagem</span><span class="sxs-lookup"><span data-stu-id="a3cf2-923">Assembly</span></span></td>
<td><span data-ttu-id="a3cf2-924">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-924">10001</span></span></td>
<td><span data-ttu-id="a3cf2-925">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-925">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-926">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-926">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="a3cf2-927">-2,977.17</span></span></td>
<td><span data-ttu-id="a3cf2-928">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-929">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-929">Prod 1</span></span></td>
<td><span data-ttu-id="a3cf2-930">Produto 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-930">Product 1</span></span></td>
<td><span data-ttu-id="a3cf2-931">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-931">10001</span></span></td>
<td><span data-ttu-id="a3cf2-932">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-932">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-933">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-933">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="a3cf2-934">2,507.09</span></span></td>
<td><span data-ttu-id="a3cf2-935">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3cf2-936">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-936">Prod 2</span></span></td>
<td><span data-ttu-id="a3cf2-937">Produto 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-937">Product 2</span></span></td>
<td><span data-ttu-id="a3cf2-938">10001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-938">10001</span></span></td>
<td><span data-ttu-id="a3cf2-939">eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-939">Electricity</span></span></td>
<td><span data-ttu-id="a3cf2-940">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-940">Variable cost</span></span></td>
<td><span data-ttu-id="a3cf2-941">470.08</span><span class="sxs-lookup"><span data-stu-id="a3cf2-941">470.08</span></span></td>
<td><span data-ttu-id="a3cf2-942">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="a3cf2-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="a3cf2-943">Conclusão</span><span class="sxs-lookup"><span data-stu-id="a3cf2-943">Conclusion</span></span>
<span data-ttu-id="a3cf2-944">Na contabilidade financeira, um custo de 10,000.00 para a eletricidade é lançado para um ID fictício de centro de custos.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="a3cf2-945">Portanto, os contadores de custo saberão que esses custos devem ser alocados.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="a3cf2-946">Na contabilização de custo, os custos fluem nas unidades organizacionais e nos níveis, com base nas políticas e regras que são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="a3cf2-947">Cada custo foi associado a uma base de alocação que fornece a melhor apuração para a alocação de custos.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="a3cf2-948">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="a3cf2-949">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="a3cf2-950">Total</span><span class="sxs-lookup"><span data-stu-id="a3cf2-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="a3cf2-951">CC099</span><span class="sxs-lookup"><span data-stu-id="a3cf2-951">CC099</span></span></th>
<th><span data-ttu-id="a3cf2-952">CC001</span><span class="sxs-lookup"><span data-stu-id="a3cf2-952">CC001</span></span></th>
<th><span data-ttu-id="a3cf2-953">CC002</span><span class="sxs-lookup"><span data-stu-id="a3cf2-953">CC002</span></span></th>
<th><span data-ttu-id="a3cf2-954">CC003</span><span class="sxs-lookup"><span data-stu-id="a3cf2-954">CC003</span></span></th>
<th><span data-ttu-id="a3cf2-955">CC004</span><span class="sxs-lookup"><span data-stu-id="a3cf2-955">CC004</span></span></th>
<th><span data-ttu-id="a3cf2-956">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-956">Proj 1</span></span></th>
<th><span data-ttu-id="a3cf2-957">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-957">Proj 2</span></span></th>
<th><span data-ttu-id="a3cf2-958">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="a3cf2-958">Prod 1</span></span></th>
<th><span data-ttu-id="a3cf2-959">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="a3cf2-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="a3cf2-960">10001 Eletricidade</span><span class="sxs-lookup"><span data-stu-id="a3cf2-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="a3cf2-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="a3cf2-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="a3cf2-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="a3cf2-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="a3cf2-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="a3cf2-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="a3cf2-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="a3cf2-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="a3cf2-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="a3cf2-970">Não classificado</span><span class="sxs-lookup"><span data-stu-id="a3cf2-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-971">0,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="a3cf2-972">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="a3cf2-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-973">0,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-974">0,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-975">0,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-976">0,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-977">0,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-978">776.36</span><span class="sxs-lookup"><span data-stu-id="a3cf2-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-979">223.64</span><span class="sxs-lookup"><span data-stu-id="a3cf2-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="a3cf2-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="a3cf2-981">Custo variável</span><span class="sxs-lookup"><span data-stu-id="a3cf2-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-982">000</span><span class="sxs-lookup"><span data-stu-id="a3cf2-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-983">0,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-984">0,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-985">0,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-986">0,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-987">30,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-988">10,00</span><span class="sxs-lookup"><span data-stu-id="a3cf2-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="a3cf2-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="a3cf2-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3cf2-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="a3cf2-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="a3cf2-992">Esse tópico mostra como um elemento de custo principal, 10001 Eletricidade flui pelos objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="a3cf2-993">Portanto, esse custo geral indireto é alocado no nível mais baixo na organização.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="a3cf2-994">Em outras palavras, os objetos de custo no nível mais baixo assumem o custo.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="a3cf2-995">Se você exigir um fluxo visual de custo entre objetos de custo, é possível usar as regras de política de acúmulo de custos para visualizar o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="a3cf2-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="a3cf2-996">Para obter mais informações, consulte [Política de acúmulo de custo e cálculo de custos indiretos](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="a3cf2-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]