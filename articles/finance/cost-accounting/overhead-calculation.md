---
title: Cálculo de custos indiretos
description: Este tópico descreve processos comuns para calcular e alocar os custos gerais indiretos.
author: AndersGirke
manager: AnnBe
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation, CAMOverheadRateCalculationJournalEntry, CAMFormulaAllocationBase
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 923e6e38a664e17ec3349d839c4b77ec903c5dc2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440461"
---
# <a name="overhead-calculation"></a><span data-ttu-id="c8c96-103">Cálculo de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="c8c96-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c8c96-104">Este tópico descreve processos comuns para calcular e alocar os custos gerais indiretos.</span><span class="sxs-lookup"><span data-stu-id="c8c96-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="c8c96-105">Definição de termo</span><span class="sxs-lookup"><span data-stu-id="c8c96-105">Term definition</span></span>
---------------

<span data-ttu-id="c8c96-106">Os custos gerais indiretos são aqueles que foram incorridos para realizar um negócio, mas não podem ser diretamente atribuídos a qualquer atividade comercial, produto ou serviço específico.</span><span class="sxs-lookup"><span data-stu-id="c8c96-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="c8c96-107">Os custos gerais indiretos fornecem suporte crítico para geração de atividades produtivas.</span><span class="sxs-lookup"><span data-stu-id="c8c96-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="c8c96-108">Eis alguns exemplos de custos gerais:</span><span class="sxs-lookup"><span data-stu-id="c8c96-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="c8c96-109">Aluguel</span><span class="sxs-lookup"><span data-stu-id="c8c96-109">Rent</span></span>
-   <span data-ttu-id="c8c96-110">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-110">Electricity</span></span>
-   <span data-ttu-id="c8c96-111">Salários administrativos</span><span class="sxs-lookup"><span data-stu-id="c8c96-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="c8c96-112">Visão geral do cálculo de custos gerais indiretos</span><span class="sxs-lookup"><span data-stu-id="c8c96-112">Overhead calculation overview</span></span>
<span data-ttu-id="c8c96-113">O cálculo de custos gerais indiretos executa as políticas de contabilização de custos na ordem correta.</span><span class="sxs-lookup"><span data-stu-id="c8c96-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="c8c96-114">Você pode executar o cálculo de custos gerais indiretos várias vezes para o mesmo período fiscal, se as políticas de contabilidade de custo foram modificadas ou foram detectados erros específicos.</span><span class="sxs-lookup"><span data-stu-id="c8c96-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="c8c96-115">Cada execução do cálculo de custos gerais indiretos é armazenada e recebe um ID exclusivo de versão que permite comparar os cálculos em várias versões.</span><span class="sxs-lookup"><span data-stu-id="c8c96-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="c8c96-116">As entradas de custo que o cálculo de custos indiretos gera recebe uma data contábil.</span><span class="sxs-lookup"><span data-stu-id="c8c96-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="c8c96-117">Essa data contábil corresponde à data final do período fiscal que é usada no cálculo.</span><span class="sxs-lookup"><span data-stu-id="c8c96-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="c8c96-118">A ID exclusiva de versão consiste nos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="c8c96-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="c8c96-119">Tipo de versão</span><span class="sxs-lookup"><span data-stu-id="c8c96-119">Version type</span></span>
-   <span data-ttu-id="c8c96-120">Data e hora</span><span class="sxs-lookup"><span data-stu-id="c8c96-120">Date and time</span></span>
-   <span data-ttu-id="c8c96-121">Razão de contabilização de custos</span><span class="sxs-lookup"><span data-stu-id="c8c96-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="c8c96-122">Ano fiscal</span><span class="sxs-lookup"><span data-stu-id="c8c96-122">Fiscal year</span></span>
-   <span data-ttu-id="c8c96-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="c8c96-123">Fiscal period</span></span>

<span data-ttu-id="c8c96-124">O cálculo de custos gerais indiretos é executado independentemente da versão.</span><span class="sxs-lookup"><span data-stu-id="c8c96-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="c8c96-125">Portanto, você pode calcular a versão de orçamento antes da versão atual.</span><span class="sxs-lookup"><span data-stu-id="c8c96-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="c8c96-126">O cálculo de custos gerais indiretos consiste em quatro etapas, conforme mostrado na ilustração.</span><span class="sxs-lookup"><span data-stu-id="c8c96-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="c8c96-127">Em cada etapa, um cabeçalho de diário é criado com entradas de diário.</span><span class="sxs-lookup"><span data-stu-id="c8c96-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="c8c96-128">Esse cabeçalho de diário mantém dados de entrada para cada etapa de cálculo.</span><span class="sxs-lookup"><span data-stu-id="c8c96-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="c8c96-129">As políticas e regras são aplicadas a cada linha do diário e as entradas de custo são geradas como saídas.</span><span class="sxs-lookup"><span data-stu-id="c8c96-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="c8c96-130">Portanto, você sempre terá rastreabilidade total.</span><span class="sxs-lookup"><span data-stu-id="c8c96-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="c8c96-131">[![Cálculo de custos gerais indiretos](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="c8c96-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="c8c96-132">Calcular e alocar os custos gerais indiretos de Eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="c8c96-133">Na contabilidade financeira, alguns custos, como eletricidade, são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="c8c96-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="c8c96-134">Portanto, a visão administrativa detalhada não é fornecida para a contabilização de custo.</span><span class="sxs-lookup"><span data-stu-id="c8c96-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="c8c96-135">Na contabilização de custo, para fornecer a visão administrativa correta em todas as unidades organizacionais e níveis, os custos devem passar pelas unidades organizacionais.</span><span class="sxs-lookup"><span data-stu-id="c8c96-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="c8c96-136">Este fluxo deve ser baseado em qualquer um registro exato do consumo ou de uma previsão justa.</span><span class="sxs-lookup"><span data-stu-id="c8c96-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="c8c96-137">Na contabilidade, um custo de eletricidade pode ser lançado, conforme mostrado na tabela.</span><span class="sxs-lookup"><span data-stu-id="c8c96-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c8c96-138">Data contábil</span><span class="sxs-lookup"><span data-stu-id="c8c96-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c8c96-139">Centro de custos</span><span class="sxs-lookup"><span data-stu-id="c8c96-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="c8c96-140">Conta principal</span><span class="sxs-lookup"><span data-stu-id="c8c96-140">Main account</span></span></th>
<th><span data-ttu-id="c8c96-141">Valor na moeda contábil</span><span class="sxs-lookup"><span data-stu-id="c8c96-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-142">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="c8c96-143">CC099</span><span class="sxs-lookup"><span data-stu-id="c8c96-143">CC099</span></span></td>
<td><span data-ttu-id="c8c96-144">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="c8c96-144">Default cost center</span></span></td>
<td><span data-ttu-id="c8c96-145">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-145">10001</span></span></td>
<td><span data-ttu-id="c8c96-146">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-146">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="c8c96-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="c8c96-148">Etapa 1: Processar o cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="c8c96-149">Por padrão, quando as entradas de custo previsto são importadas de dados de origem, elas recebem a classificação de comportamento de custo **Não classificado** na Contabilidade de custos.</span><span class="sxs-lookup"><span data-stu-id="c8c96-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="c8c96-150">Aplicando regras da política de comportamento de custo, é possível reclassificar entradas de custo como **Custo fixo** ou **Custo variável**.</span><span class="sxs-lookup"><span data-stu-id="c8c96-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="c8c96-151">Definir a regra de custo de comportamento</span><span class="sxs-lookup"><span data-stu-id="c8c96-151">Define the cost behavior rule</span></span>

<span data-ttu-id="c8c96-152">Em alguns casos, parte do custo é uma taxa fixa e o custos pendente é baseado no consumo.</span><span class="sxs-lookup"><span data-stu-id="c8c96-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="c8c96-153">Geralmente, as contas de eletricidade correspondem a esta definição.</span><span class="sxs-lookup"><span data-stu-id="c8c96-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="c8c96-154">Após você pagar uma taxa fixa específica, você paga por consumo, por hora de quilowatt (Kwh).</span><span class="sxs-lookup"><span data-stu-id="c8c96-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="c8c96-155">Por exemplo, se a taxa de custo fixa for 1.000.00, veja aqui como a regra de comportamento de custo é definida:</span><span class="sxs-lookup"><span data-stu-id="c8c96-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="c8c96-156">Valor fixo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="c8c96-157">0 &lt;= 1.000,00 = Fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="c8c96-158">1000.01 &lt; N = Variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="c8c96-159">Diário</span><span class="sxs-lookup"><span data-stu-id="c8c96-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c8c96-160">Diário</span><span class="sxs-lookup"><span data-stu-id="c8c96-160">Journal</span></span></th>
<th><span data-ttu-id="c8c96-161">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="c8c96-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="c8c96-162">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="c8c96-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="c8c96-163">Versão</span><span class="sxs-lookup"><span data-stu-id="c8c96-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-164">00001</span><span class="sxs-lookup"><span data-stu-id="c8c96-164">00001</span></span></td>
<td><span data-ttu-id="c8c96-165">Diário de cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="c8c96-166">fiscal</span><span class="sxs-lookup"><span data-stu-id="c8c96-166">Fiscal</span></span></td>
<td><span data-ttu-id="c8c96-167">2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-167">2017</span></span></td>
<td><span data-ttu-id="c8c96-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-168">Period 1</span></span></td>
<td><span data-ttu-id="c8c96-169">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="c8c96-170">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="c8c96-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c8c96-171">Data contábil</span><span class="sxs-lookup"><span data-stu-id="c8c96-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c8c96-172">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c8c96-173">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-173">Cost element</span></span></th>
<th><span data-ttu-id="c8c96-174">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-174">Cost behavior</span></span></th>
<th><span data-ttu-id="c8c96-175">Valor</span><span class="sxs-lookup"><span data-stu-id="c8c96-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-176">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="c8c96-177">CC099</span><span class="sxs-lookup"><span data-stu-id="c8c96-177">CC099</span></span></td>
<td><span data-ttu-id="c8c96-178">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="c8c96-178">Default cost center</span></span></td>
<td><span data-ttu-id="c8c96-179">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-179">10001</span></span></td>
<td><span data-ttu-id="c8c96-180">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-180">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-181">Não classificado</span><span class="sxs-lookup"><span data-stu-id="c8c96-181">Unclassified</span></span></td>
<td><span data-ttu-id="c8c96-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="c8c96-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="c8c96-183">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c8c96-184">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c8c96-185">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-185">Cost element</span></span></th>
<th><span data-ttu-id="c8c96-186">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-186">Cost behavior</span></span></th>
<th><span data-ttu-id="c8c96-187">Valor</span><span class="sxs-lookup"><span data-stu-id="c8c96-187">Amount</span></span></th>
<th><span data-ttu-id="c8c96-188">Data contábil</span><span class="sxs-lookup"><span data-stu-id="c8c96-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-189">CC099</span><span class="sxs-lookup"><span data-stu-id="c8c96-189">CC099</span></span></td>
<td><span data-ttu-id="c8c96-190">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="c8c96-190">Default cost center</span></span></td>
<td><span data-ttu-id="c8c96-191">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-191">10001</span></span></td>
<td><span data-ttu-id="c8c96-192">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-192">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-193">Não classificado</span><span class="sxs-lookup"><span data-stu-id="c8c96-193">Unclassified</span></span></td>
<td><span data-ttu-id="c8c96-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="c8c96-194">10,000.00</span></span></td>
<td><span data-ttu-id="c8c96-195">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-196">CC099</span><span class="sxs-lookup"><span data-stu-id="c8c96-196">CC099</span></span></td>
<td><span data-ttu-id="c8c96-197">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="c8c96-197">Default cost center</span></span></td>
<td><span data-ttu-id="c8c96-198">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-198">10001</span></span></td>
<td><span data-ttu-id="c8c96-199">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-199">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-200">Não classificado</span><span class="sxs-lookup"><span data-stu-id="c8c96-200">Unclassified</span></span></td>
<td><span data-ttu-id="c8c96-201">-10.000,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-201">-10,000.00</span></span></td>
<td><span data-ttu-id="c8c96-202">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-203">CC099</span><span class="sxs-lookup"><span data-stu-id="c8c96-203">CC099</span></span></td>
<td><span data-ttu-id="c8c96-204">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="c8c96-204">Default cost center</span></span></td>
<td><span data-ttu-id="c8c96-205">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-205">10001</span></span></td>
<td><span data-ttu-id="c8c96-206">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-206">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-207">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-207">Fixed cost</span></span></td>
<td><span data-ttu-id="c8c96-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-208">1,000.00</span></span></td>
<td><span data-ttu-id="c8c96-209">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-210">CC099</span><span class="sxs-lookup"><span data-stu-id="c8c96-210">CC099</span></span></td>
<td><span data-ttu-id="c8c96-211">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="c8c96-211">Default cost center</span></span></td>
<td><span data-ttu-id="c8c96-212">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-212">10001</span></span></td>
<td><span data-ttu-id="c8c96-213">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-213">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-214">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-214">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="c8c96-215">9,000.00</span></span></td>
<td><span data-ttu-id="c8c96-216">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c8c96-217">Para obter mais informações, consulte [Criar e atribuir uma política de comportamento de custos a uma unidade de controle de custos](tasks/create-assign-cost-behavior-policy-cost-control-unit.md)</span><span class="sxs-lookup"><span data-stu-id="c8c96-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="c8c96-218">Etapa 2: Processar o cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="c8c96-219">A distribuição de custos é usada para redistribuir custo de um objeto de custo a um ou mais outros objetos de custo, aplicando uma base de alocação relevante.</span><span class="sxs-lookup"><span data-stu-id="c8c96-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="c8c96-220">A distribuição de custos e a alocação de custo são diferentes na distribuição de custos, sempre que ocorrer em nível de elemento de custo principal do custo original.</span><span class="sxs-lookup"><span data-stu-id="c8c96-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="c8c96-221">Definir a regra de distribuição de custos</span><span class="sxs-lookup"><span data-stu-id="c8c96-221">Define the cost distribution rule</span></span>

<span data-ttu-id="c8c96-222">Na contabilidade financeira, os custos de eletricidade geralmente são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="c8c96-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="c8c96-223">Na contabilização de custo, esta abordagem não é suficientemente detalhada.</span><span class="sxs-lookup"><span data-stu-id="c8c96-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="c8c96-224">O custo variável deve ser distribuído a objetos de custos individuais com base justa.</span><span class="sxs-lookup"><span data-stu-id="c8c96-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="c8c96-225">A base de alocação mais lógica é o consumo de eletricidade (Kwh).</span><span class="sxs-lookup"><span data-stu-id="c8c96-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="c8c96-226">O membro da dimensão estatística que é chamado Eletricidade é criado e o consumo de eletricidade é registrado.</span><span class="sxs-lookup"><span data-stu-id="c8c96-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="c8c96-227">Por padrão, todos os membros estatísticos da dimensão se tornam disponíveis como bases de alocação.</span><span class="sxs-lookup"><span data-stu-id="c8c96-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c8c96-228">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-228">Cost object</span></span></th>
<th><span data-ttu-id="c8c96-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="c8c96-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-230">CC001</span><span class="sxs-lookup"><span data-stu-id="c8c96-230">CC001</span></span></td>
<td><span data-ttu-id="c8c96-231">RH</span><span class="sxs-lookup"><span data-stu-id="c8c96-231">HR</span></span></td>
<td><span data-ttu-id="c8c96-232">1.000</span><span class="sxs-lookup"><span data-stu-id="c8c96-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-233">CC002</span><span class="sxs-lookup"><span data-stu-id="c8c96-233">CC002</span></span></td>
<td><span data-ttu-id="c8c96-234">Finanças</span><span class="sxs-lookup"><span data-stu-id="c8c96-234">Finance</span></span></td>
<td><span data-ttu-id="c8c96-235">6,000</span><span class="sxs-lookup"><span data-stu-id="c8c96-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-236">CC003</span><span class="sxs-lookup"><span data-stu-id="c8c96-236">CC003</span></span></td>
<td><span data-ttu-id="c8c96-237">Montagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-237">Assembly</span></span></td>
<td><span data-ttu-id="c8c96-238">0</span><span class="sxs-lookup"><span data-stu-id="c8c96-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c8c96-239">A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação para custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="c8c96-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c8c96-240">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-240">Cost object</span></span></th>
<th><span data-ttu-id="c8c96-241">Magnitude</span><span class="sxs-lookup"><span data-stu-id="c8c96-241">Magnitude</span></span></th>
<th><span data-ttu-id="c8c96-242">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="c8c96-242">Allocation factor</span></span></th>
<th><span data-ttu-id="c8c96-243">Valor</span><span class="sxs-lookup"><span data-stu-id="c8c96-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-244">CC001</span><span class="sxs-lookup"><span data-stu-id="c8c96-244">CC001</span></span></td>
<td><span data-ttu-id="c8c96-245">RH</span><span class="sxs-lookup"><span data-stu-id="c8c96-245">HR</span></span></td>
<td><span data-ttu-id="c8c96-246">1.000</span><span class="sxs-lookup"><span data-stu-id="c8c96-246">1,000</span></span></td>
<td><span data-ttu-id="c8c96-247">(1.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="c8c96-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="c8c96-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-249">CC002</span><span class="sxs-lookup"><span data-stu-id="c8c96-249">CC002</span></span></td>
<td><span data-ttu-id="c8c96-250">Finanças</span><span class="sxs-lookup"><span data-stu-id="c8c96-250">Finance</span></span></td>
<td><span data-ttu-id="c8c96-251">6,000</span><span class="sxs-lookup"><span data-stu-id="c8c96-251">6,000</span></span></td>
<td><span data-ttu-id="c8c96-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="c8c96-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="c8c96-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-254">CC003</span><span class="sxs-lookup"><span data-stu-id="c8c96-254">CC003</span></span></td>
<td><span data-ttu-id="c8c96-255">Montagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-255">Assembly</span></span></td>
<td><span data-ttu-id="c8c96-256">0</span><span class="sxs-lookup"><span data-stu-id="c8c96-256">0</span></span></td>
<td><span data-ttu-id="c8c96-257">(0 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="c8c96-258">0,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c8c96-259">Os custos fixos devem ser distribuídos igualmente a objetos de custo individuais que têm a eletricidade consumida.</span><span class="sxs-lookup"><span data-stu-id="c8c96-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="c8c96-260">Você pode obter esse resultado usando o membro estatístico de dimensão de eletricidade em uma base e alocação da fórmula: (Eletricidade &gt; 0,00) A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação de custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="c8c96-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c8c96-261">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-261">Cost object</span></span></th>
<th><span data-ttu-id="c8c96-262">Fórmula</span><span class="sxs-lookup"><span data-stu-id="c8c96-262">Formula</span></span></th>
<th><span data-ttu-id="c8c96-263">Magnitude</span><span class="sxs-lookup"><span data-stu-id="c8c96-263">Magnitude</span></span></th>
<th><span data-ttu-id="c8c96-264">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="c8c96-264">Allocation factor</span></span></th>
<th><span data-ttu-id="c8c96-265">Valor</span><span class="sxs-lookup"><span data-stu-id="c8c96-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-266">CC001</span><span class="sxs-lookup"><span data-stu-id="c8c96-266">CC001</span></span></td>
<td><span data-ttu-id="c8c96-267">RH</span><span class="sxs-lookup"><span data-stu-id="c8c96-267">HR</span></span></td>
<td><span data-ttu-id="c8c96-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="c8c96-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="c8c96-269">1</span><span class="sxs-lookup"><span data-stu-id="c8c96-269">1</span></span></td>
<td><span data-ttu-id="c8c96-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="c8c96-271">500,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-272">CC002</span><span class="sxs-lookup"><span data-stu-id="c8c96-272">CC002</span></span></td>
<td><span data-ttu-id="c8c96-273">Finanças</span><span class="sxs-lookup"><span data-stu-id="c8c96-273">Finance</span></span></td>
<td><span data-ttu-id="c8c96-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="c8c96-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="c8c96-275">1</span><span class="sxs-lookup"><span data-stu-id="c8c96-275">1</span></span></td>
<td><span data-ttu-id="c8c96-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="c8c96-277">500,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-278">CC003</span><span class="sxs-lookup"><span data-stu-id="c8c96-278">CC003</span></span></td>
<td><span data-ttu-id="c8c96-279">Montagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-279">Assembly</span></span></td>
<td><span data-ttu-id="c8c96-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="c8c96-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="c8c96-281">0</span><span class="sxs-lookup"><span data-stu-id="c8c96-281">0</span></span></td>
<td><span data-ttu-id="c8c96-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="c8c96-283">0,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="c8c96-284">Diário</span><span class="sxs-lookup"><span data-stu-id="c8c96-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c8c96-285">Diário</span><span class="sxs-lookup"><span data-stu-id="c8c96-285">Journal</span></span></th>
<th><span data-ttu-id="c8c96-286">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="c8c96-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="c8c96-287">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="c8c96-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="c8c96-288">Versão</span><span class="sxs-lookup"><span data-stu-id="c8c96-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-289">00002</span><span class="sxs-lookup"><span data-stu-id="c8c96-289">00002</span></span></td>
<td><span data-ttu-id="c8c96-290">Diário de cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="c8c96-291">fiscal</span><span class="sxs-lookup"><span data-stu-id="c8c96-291">Fiscal</span></span></td>
<td><span data-ttu-id="c8c96-292">2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-292">2017</span></span></td>
<td><span data-ttu-id="c8c96-293">Período 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-293">Period 1</span></span></td>
<td><span data-ttu-id="c8c96-294">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="c8c96-295">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="c8c96-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c8c96-296">Data contábil</span><span class="sxs-lookup"><span data-stu-id="c8c96-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c8c96-297">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c8c96-298">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-298">Cost element</span></span></th>
<th><span data-ttu-id="c8c96-299">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-299">Cost behavior</span></span></th>
<th><span data-ttu-id="c8c96-300">Valor</span><span class="sxs-lookup"><span data-stu-id="c8c96-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-301">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="c8c96-302">CC099</span><span class="sxs-lookup"><span data-stu-id="c8c96-302">CC099</span></span></td>
<td><span data-ttu-id="c8c96-303">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="c8c96-303">Default cost center</span></span></td>
<td><span data-ttu-id="c8c96-304">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-304">10001</span></span></td>
<td><span data-ttu-id="c8c96-305">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-305">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-306">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-306">Fixed cost</span></span></td>
<td><span data-ttu-id="c8c96-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-308">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="c8c96-309">CC099</span><span class="sxs-lookup"><span data-stu-id="c8c96-309">CC099</span></span></td>
<td><span data-ttu-id="c8c96-310">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="c8c96-310">Default cost center</span></span></td>
<td><span data-ttu-id="c8c96-311">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-311">10001</span></span></td>
<td><span data-ttu-id="c8c96-312">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-312">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-313">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-313">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="c8c96-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="c8c96-315">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c8c96-316">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c8c96-317">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-317">Cost element</span></span></th>
<th><span data-ttu-id="c8c96-318">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-318">Cost behavior</span></span></th>
<th><span data-ttu-id="c8c96-319">Valor</span><span class="sxs-lookup"><span data-stu-id="c8c96-319">Amount</span></span></th>
<th><span data-ttu-id="c8c96-320">Data contábil</span><span class="sxs-lookup"><span data-stu-id="c8c96-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-321">CC099</span><span class="sxs-lookup"><span data-stu-id="c8c96-321">CC099</span></span></td>
<td><span data-ttu-id="c8c96-322">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="c8c96-322">Default cost center</span></span></td>
<td><span data-ttu-id="c8c96-323">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-323">10001</span></span></td>
<td><span data-ttu-id="c8c96-324">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-324">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-325">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-325">Fixed cost</span></span></td>
<td><span data-ttu-id="c8c96-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-326">-1,000.00</span></span></td>
<td><span data-ttu-id="c8c96-327">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-328">CC001</span><span class="sxs-lookup"><span data-stu-id="c8c96-328">CC001</span></span></td>
<td><span data-ttu-id="c8c96-329">RH</span><span class="sxs-lookup"><span data-stu-id="c8c96-329">HR</span></span></td>
<td><span data-ttu-id="c8c96-330">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-330">10001</span></span></td>
<td><span data-ttu-id="c8c96-331">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-331">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-332">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-332">Fixed cost</span></span></td>
<td><span data-ttu-id="c8c96-333">500,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-333">500.00</span></span></td>
<td><span data-ttu-id="c8c96-334">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-335">CC002</span><span class="sxs-lookup"><span data-stu-id="c8c96-335">CC002</span></span></td>
<td><span data-ttu-id="c8c96-336">Finanças</span><span class="sxs-lookup"><span data-stu-id="c8c96-336">Finance</span></span></td>
<td><span data-ttu-id="c8c96-337">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-337">10001</span></span></td>
<td><span data-ttu-id="c8c96-338">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-338">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-339">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-339">Fixed cost</span></span></td>
<td><span data-ttu-id="c8c96-340">500,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-340">500.00</span></span></td>
<td><span data-ttu-id="c8c96-341">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-342">CC099</span><span class="sxs-lookup"><span data-stu-id="c8c96-342">CC099</span></span></td>
<td><span data-ttu-id="c8c96-343">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="c8c96-343">Default cost center</span></span></td>
<td><span data-ttu-id="c8c96-344">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-344">10001</span></span></td>
<td><span data-ttu-id="c8c96-345">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-345">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-346">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-346">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-347">-9,000.00</span></span></td>
<td><span data-ttu-id="c8c96-348">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-349">CC001</span><span class="sxs-lookup"><span data-stu-id="c8c96-349">CC001</span></span></td>
<td><span data-ttu-id="c8c96-350">RH</span><span class="sxs-lookup"><span data-stu-id="c8c96-350">HR</span></span></td>
<td><span data-ttu-id="c8c96-351">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-351">10001</span></span></td>
<td><span data-ttu-id="c8c96-352">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-352">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-353">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-353">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="c8c96-354">1,285.71</span></span></td>
<td><span data-ttu-id="c8c96-355">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-356">CC002</span><span class="sxs-lookup"><span data-stu-id="c8c96-356">CC002</span></span></td>
<td><span data-ttu-id="c8c96-357">Finanças</span><span class="sxs-lookup"><span data-stu-id="c8c96-357">Finance</span></span></td>
<td><span data-ttu-id="c8c96-358">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-358">10001</span></span></td>
<td><span data-ttu-id="c8c96-359">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-359">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-360">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-360">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="c8c96-361">7,714.29</span></span></td>
<td><span data-ttu-id="c8c96-362">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c8c96-363">Para obter mais informações, consulte [Criar e atribuir uma política de distribuição de custos a uma unidade de controle de custos](tasks/create-assign-cost-distribution-policy-cost-control-unit.md)</span><span class="sxs-lookup"><span data-stu-id="c8c96-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="c8c96-364">Etapa 3: Processar o cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="c8c96-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="c8c96-365">A taxa de custos indiretos é usada para cobrar um ou mais objetos de custos específicos.</span><span class="sxs-lookup"><span data-stu-id="c8c96-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="c8c96-366">O encargo se baseia em uma taxa de custo predeterminada e a magnitude da básica de alocação atribuída.</span><span class="sxs-lookup"><span data-stu-id="c8c96-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="c8c96-367">Defina a taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="c8c96-367">Define the overhead rate</span></span>

<span data-ttu-id="c8c96-368">O objeto de custo CC001 HR contribui para um conjunto de projetos internos.</span><span class="sxs-lookup"><span data-stu-id="c8c96-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="c8c96-369">Um membro de dimensão estatística que é chamado de projetos de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="c8c96-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c8c96-370">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-370">Cost object</span></span></th>
<th><span data-ttu-id="c8c96-371">Horas</span><span class="sxs-lookup"><span data-stu-id="c8c96-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-372">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-372">Proj 1</span></span></td>
<td><span data-ttu-id="c8c96-373">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-373">Project 1</span></span></td>
<td><span data-ttu-id="c8c96-374">3</span><span class="sxs-lookup"><span data-stu-id="c8c96-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-375">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-375">Proj 2</span></span></td>
<td><span data-ttu-id="c8c96-376">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-376">Project 2</span></span></td>
<td><span data-ttu-id="c8c96-377">1</span><span class="sxs-lookup"><span data-stu-id="c8c96-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c8c96-378">Uma taxa de custo predeterminada da contribuição de projetos de custo foi definida.</span><span class="sxs-lookup"><span data-stu-id="c8c96-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c8c96-379">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-379">Cost object</span></span></th>
<th><span data-ttu-id="c8c96-380">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-380">Cost element</span></span></th>
<th><span data-ttu-id="c8c96-381">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-381">Cost behavior</span></span></th>
<th><span data-ttu-id="c8c96-382">Unidades</span><span class="sxs-lookup"><span data-stu-id="c8c96-382">Units</span></span></th>
<th><span data-ttu-id="c8c96-383">Taxa</span><span class="sxs-lookup"><span data-stu-id="c8c96-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-384">CC001</span><span class="sxs-lookup"><span data-stu-id="c8c96-384">CC001</span></span></td>
<td><span data-ttu-id="c8c96-385">RH</span><span class="sxs-lookup"><span data-stu-id="c8c96-385">HR</span></span></td>
<td><span data-ttu-id="c8c96-386">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-386">10001</span></span></td>
<td><span data-ttu-id="c8c96-387">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-387">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-388">1</span><span class="sxs-lookup"><span data-stu-id="c8c96-388">1</span></span></td>
<td><span data-ttu-id="c8c96-389">10</span><span class="sxs-lookup"><span data-stu-id="c8c96-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c8c96-390">A tabela a seguir mostra o resultado quando projetos de RH são aplicados como base de alocação.</span><span class="sxs-lookup"><span data-stu-id="c8c96-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c8c96-391">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-391">Cost object</span></span></th>
<th><span data-ttu-id="c8c96-392">Magnitude</span><span class="sxs-lookup"><span data-stu-id="c8c96-392">Magnitude</span></span></th>
<th><span data-ttu-id="c8c96-393">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-393">Cost element</span></span></th>
<th><span data-ttu-id="c8c96-394">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="c8c96-394">Allocation factor</span></span></th>
<th><span data-ttu-id="c8c96-395">Valor</span><span class="sxs-lookup"><span data-stu-id="c8c96-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-396">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-396">Proj 1</span></span></td>
<td><span data-ttu-id="c8c96-397">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-397">Project 1</span></span></td>
<td><span data-ttu-id="c8c96-398">3</span><span class="sxs-lookup"><span data-stu-id="c8c96-398">3</span></span></td>
<td><span data-ttu-id="c8c96-399">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-399">10001</span></span></td>
<td><span data-ttu-id="c8c96-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="c8c96-401">30,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-402">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-402">Proj 2</span></span></td>
<td><span data-ttu-id="c8c96-403">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-403">Project 2</span></span></td>
<td><span data-ttu-id="c8c96-404">1</span><span class="sxs-lookup"><span data-stu-id="c8c96-404">1</span></span></td>
<td><span data-ttu-id="c8c96-405">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-405">10001</span></span></td>
<td><span data-ttu-id="c8c96-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="c8c96-407">10,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="c8c96-408">Diário</span><span class="sxs-lookup"><span data-stu-id="c8c96-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c8c96-409">Diário</span><span class="sxs-lookup"><span data-stu-id="c8c96-409">Journal</span></span></th>
<th><span data-ttu-id="c8c96-410">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="c8c96-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="c8c96-411">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="c8c96-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="c8c96-412">Versão</span><span class="sxs-lookup"><span data-stu-id="c8c96-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-413">00003</span><span class="sxs-lookup"><span data-stu-id="c8c96-413">00003</span></span></td>
<td><span data-ttu-id="c8c96-414">Diário de cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="c8c96-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="c8c96-415">fiscal</span><span class="sxs-lookup"><span data-stu-id="c8c96-415">Fiscal</span></span></td>
<td><span data-ttu-id="c8c96-416">2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-416">2017</span></span></td>
<td><span data-ttu-id="c8c96-417">Período 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-417">Period 1</span></span></td>
<td><span data-ttu-id="c8c96-418">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="c8c96-419">Entradas de diário (As entradas de diário para cálculo da taxa de custos indiretos)</span><span class="sxs-lookup"><span data-stu-id="c8c96-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c8c96-420">Data contábil</span><span class="sxs-lookup"><span data-stu-id="c8c96-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c8c96-421">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-421">Cost object</span></span></th>
<th><span data-ttu-id="c8c96-422">Magnitude</span><span class="sxs-lookup"><span data-stu-id="c8c96-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-423">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="c8c96-424">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-424">Proj 1</span></span></td>
<td><span data-ttu-id="c8c96-425">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="c8c96-426">3,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-427">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="c8c96-428">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-428">Proj 2</span></span></td>
<td><span data-ttu-id="c8c96-429">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="c8c96-430">1.00</span><span class="sxs-lookup"><span data-stu-id="c8c96-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="c8c96-431">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c8c96-432">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c8c96-433">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-433">Cost element</span></span></th>
<th><span data-ttu-id="c8c96-434">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-434">Cost behavior</span></span></th>
<th><span data-ttu-id="c8c96-435">Valor</span><span class="sxs-lookup"><span data-stu-id="c8c96-435">Amount</span></span></th>
<th><span data-ttu-id="c8c96-436">Data contábil</span><span class="sxs-lookup"><span data-stu-id="c8c96-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="c8c96-437">CC0001</span></span></td>
<td><span data-ttu-id="c8c96-438">RH</span><span class="sxs-lookup"><span data-stu-id="c8c96-438">HR</span></span></td>
<td><span data-ttu-id="c8c96-439">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-439">10001</span></span></td>
<td><span data-ttu-id="c8c96-440">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-440">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-441">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-441">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-442">-30.00</span></span></td>
<td><span data-ttu-id="c8c96-443">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-444">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-444">Proj 1</span></span></td>
<td><span data-ttu-id="c8c96-445">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="c8c96-446">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-446">10001</span></span></td>
<td><span data-ttu-id="c8c96-447">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-447">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-448">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-448">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-449">30,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-449">30.00</span></span></td>
<td><span data-ttu-id="c8c96-450">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-451">CC001</span><span class="sxs-lookup"><span data-stu-id="c8c96-451">CC001</span></span></td>
<td><span data-ttu-id="c8c96-452">RH</span><span class="sxs-lookup"><span data-stu-id="c8c96-452">HR</span></span></td>
<td><span data-ttu-id="c8c96-453">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-453">10001</span></span></td>
<td><span data-ttu-id="c8c96-454">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-454">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-455">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-455">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-456">-10.00</span></span></td>
<td><span data-ttu-id="c8c96-457">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-458">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-458">Proj 2</span></span></td>
<td><span data-ttu-id="c8c96-459">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="c8c96-460">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-460">10001</span></span></td>
<td><span data-ttu-id="c8c96-461">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-461">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-462">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-462">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-463">10,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-463">10.00</span></span></td>
<td><span data-ttu-id="c8c96-464">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c8c96-465">Para obter mais informações, consulte [Realizar cálculo de custos indiretos](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="c8c96-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="c8c96-466">Etapa 4: Processar o cálculo de alocação de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="c8c96-467">A alocação é usada para alocar o saldo de um objeto de custo a outros objetos de custo pela aplicação de uma base de alocação.</span><span class="sxs-lookup"><span data-stu-id="c8c96-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="c8c96-468">O Finance oferece suporte ao método de alocação recíproco.</span><span class="sxs-lookup"><span data-stu-id="c8c96-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="c8c96-469">No método de alocação recíproco, os serviços mútuos que os objetos de custo auxiliar trocam são totalmente reconhecidos.</span><span class="sxs-lookup"><span data-stu-id="c8c96-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="c8c96-470">O sistema determina automaticamente a ordem correta realizar as alocações.</span><span class="sxs-lookup"><span data-stu-id="c8c96-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="c8c96-471">O saldo de um objeto de custo é alocado por uma base de alocação única.</span><span class="sxs-lookup"><span data-stu-id="c8c96-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="c8c96-472">As alocações entre as dimensões de objetos de custo e os respectivos membros são suportadas.</span><span class="sxs-lookup"><span data-stu-id="c8c96-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="c8c96-473">A ordem de alocação é controlada pela unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="c8c96-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="c8c96-474">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="c8c96-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="c8c96-475">Defina a alocação de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-475">Define the cost allocation</span></span>

<span data-ttu-id="c8c96-476">Aqui está um exemplo simples que explica como você pode rastrear o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="c8c96-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="c8c96-477">O objeto de custo previsto CC001 HR contribui a vários objetos de custo previsto.</span><span class="sxs-lookup"><span data-stu-id="c8c96-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="c8c96-478">Um membro de dimensão estatística que é chamado de serviços de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="c8c96-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c8c96-479">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-479">Cost object</span></span></th>
<th><span data-ttu-id="c8c96-480">Serviços de RH</span><span class="sxs-lookup"><span data-stu-id="c8c96-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-481">CC002</span><span class="sxs-lookup"><span data-stu-id="c8c96-481">CC002</span></span></td>
<td><span data-ttu-id="c8c96-482">Finanças</span><span class="sxs-lookup"><span data-stu-id="c8c96-482">Finance</span></span></td>
<td><span data-ttu-id="c8c96-483">35</span><span class="sxs-lookup"><span data-stu-id="c8c96-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-484">CC003</span><span class="sxs-lookup"><span data-stu-id="c8c96-484">CC003</span></span></td>
<td><span data-ttu-id="c8c96-485">Montagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-485">Assembly</span></span></td>
<td><span data-ttu-id="c8c96-486">55</span><span class="sxs-lookup"><span data-stu-id="c8c96-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-487">CC004</span><span class="sxs-lookup"><span data-stu-id="c8c96-487">CC004</span></span></td>
<td><span data-ttu-id="c8c96-488">Embalagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-488">Packaging</span></span></td>
<td><span data-ttu-id="c8c96-489">10</span><span class="sxs-lookup"><span data-stu-id="c8c96-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c8c96-490">O objeto de custo CC002 Finanças contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="c8c96-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="c8c96-491">Um membro de dimensão estatística que é chamado de serviços de Finanças foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="c8c96-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c8c96-492">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-492">Cost object</span></span></th>
<th><span data-ttu-id="c8c96-493">Serviços financeiros</span><span class="sxs-lookup"><span data-stu-id="c8c96-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-494">CC003</span><span class="sxs-lookup"><span data-stu-id="c8c96-494">CC003</span></span></td>
<td><span data-ttu-id="c8c96-495">Montagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-495">Assembly</span></span></td>
<td><span data-ttu-id="c8c96-496">65</span><span class="sxs-lookup"><span data-stu-id="c8c96-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-497">CC004</span><span class="sxs-lookup"><span data-stu-id="c8c96-497">CC004</span></span></td>
<td><span data-ttu-id="c8c96-498">Embalagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-498">Packaging</span></span></td>
<td><span data-ttu-id="c8c96-499">35</span><span class="sxs-lookup"><span data-stu-id="c8c96-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c8c96-500">O objeto de custo CC003 Montagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="c8c96-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="c8c96-501">Um membro de dimensão estatística que é chamado de serviços de Montagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="c8c96-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c8c96-502">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-502">Cost object</span></span></th>
<th><span data-ttu-id="c8c96-503">Serviços de montagem (horas)</span><span class="sxs-lookup"><span data-stu-id="c8c96-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-504">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-504">Prod 1</span></span></td>
<td><span data-ttu-id="c8c96-505">Produto 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-505">Product 1</span></span></td>
<td><span data-ttu-id="c8c96-506">60</span><span class="sxs-lookup"><span data-stu-id="c8c96-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-507">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-507">Prod 2</span></span></td>
<td><span data-ttu-id="c8c96-508">Produto 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-508">Product 2</span></span></td>
<td><span data-ttu-id="c8c96-509">20</span><span class="sxs-lookup"><span data-stu-id="c8c96-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c8c96-510">O objeto de custo CC004 Embalagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="c8c96-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="c8c96-511">Um membro de dimensão estatística que é chamado de serviços de Embalagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="c8c96-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c8c96-512">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-512">Cost object</span></span></th>
<th><span data-ttu-id="c8c96-513">Serviços de embalagem (horas)</span><span class="sxs-lookup"><span data-stu-id="c8c96-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-514">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-514">Prod 1</span></span></td>
<td><span data-ttu-id="c8c96-515">Produto 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-515">Product 1</span></span></td>
<td><span data-ttu-id="c8c96-516">80</span><span class="sxs-lookup"><span data-stu-id="c8c96-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-517">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-517">Prod 2</span></span></td>
<td><span data-ttu-id="c8c96-518">Produto 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-518">Product 2</span></span></td>
<td><span data-ttu-id="c8c96-519">15</span><span class="sxs-lookup"><span data-stu-id="c8c96-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="c8c96-520">Medidas estatísticas, como as horas de produção que um produto consome, podem ser derivadas dos dados de origem.</span><span class="sxs-lookup"><span data-stu-id="c8c96-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="c8c96-521">Para obter mais informações, consulte [Modelo de provedor de medidas estatísticas](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="c8c96-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="c8c96-522">A tabela a seguir mostra o resultado quando os serviços de RH são aplicados como base de alocação para custos totais (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="c8c96-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c8c96-523">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-523">Cost object</span></span></th>
<th><span data-ttu-id="c8c96-524">Magnitude</span><span class="sxs-lookup"><span data-stu-id="c8c96-524">Magnitude</span></span></th>
<th><span data-ttu-id="c8c96-525">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="c8c96-525">Allocation factor</span></span></th>
<th><span data-ttu-id="c8c96-526">Valor</span><span class="sxs-lookup"><span data-stu-id="c8c96-526">Amount</span></span></th>
<th><span data-ttu-id="c8c96-527">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-528">CC002</span><span class="sxs-lookup"><span data-stu-id="c8c96-528">CC002</span></span></td>
<td><span data-ttu-id="c8c96-529">Finanças</span><span class="sxs-lookup"><span data-stu-id="c8c96-529">Finance</span></span></td>
<td><span data-ttu-id="c8c96-530">35</span><span class="sxs-lookup"><span data-stu-id="c8c96-530">35</span></span></td>
<td><span data-ttu-id="c8c96-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="c8c96-532">175.00</span><span class="sxs-lookup"><span data-stu-id="c8c96-532">175.00</span></span></td>
<td><span data-ttu-id="c8c96-533">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-534">CC003</span><span class="sxs-lookup"><span data-stu-id="c8c96-534">CC003</span></span></td>
<td><span data-ttu-id="c8c96-535">Montagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-535">Assembly</span></span></td>
<td><span data-ttu-id="c8c96-536">55</span><span class="sxs-lookup"><span data-stu-id="c8c96-536">55</span></span></td>
<td><span data-ttu-id="c8c96-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="c8c96-538">275.00</span><span class="sxs-lookup"><span data-stu-id="c8c96-538">275.00</span></span></td>
<td><span data-ttu-id="c8c96-539">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-540">CC004</span><span class="sxs-lookup"><span data-stu-id="c8c96-540">CC004</span></span></td>
<td><span data-ttu-id="c8c96-541">Embalagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-541">Packaging</span></span></td>
<td><span data-ttu-id="c8c96-542">10</span><span class="sxs-lookup"><span data-stu-id="c8c96-542">10</span></span></td>
<td><span data-ttu-id="c8c96-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="c8c96-544">50,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-544">50.00</span></span></td>
<td><span data-ttu-id="c8c96-545">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-546">CC002</span><span class="sxs-lookup"><span data-stu-id="c8c96-546">CC002</span></span></td>
<td><span data-ttu-id="c8c96-547">Finanças</span><span class="sxs-lookup"><span data-stu-id="c8c96-547">Finance</span></span></td>
<td><span data-ttu-id="c8c96-548">35</span><span class="sxs-lookup"><span data-stu-id="c8c96-548">35</span></span></td>
<td><span data-ttu-id="c8c96-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="c8c96-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="c8c96-550">436.00</span><span class="sxs-lookup"><span data-stu-id="c8c96-550">436.00</span></span></td>
<td><span data-ttu-id="c8c96-551">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-552">CC003</span><span class="sxs-lookup"><span data-stu-id="c8c96-552">CC003</span></span></td>
<td><span data-ttu-id="c8c96-553">Montagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-553">Assembly</span></span></td>
<td><span data-ttu-id="c8c96-554">55</span><span class="sxs-lookup"><span data-stu-id="c8c96-554">55</span></span></td>
<td><span data-ttu-id="c8c96-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="c8c96-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="c8c96-556">685.14</span><span class="sxs-lookup"><span data-stu-id="c8c96-556">685.14</span></span></td>
<td><span data-ttu-id="c8c96-557">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-558">CC004</span><span class="sxs-lookup"><span data-stu-id="c8c96-558">CC004</span></span></td>
<td><span data-ttu-id="c8c96-559">Embalagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-559">Packaging</span></span></td>
<td><span data-ttu-id="c8c96-560">10</span><span class="sxs-lookup"><span data-stu-id="c8c96-560">10</span></span></td>
<td><span data-ttu-id="c8c96-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="c8c96-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="c8c96-562">124.57</span><span class="sxs-lookup"><span data-stu-id="c8c96-562">124.57</span></span></td>
<td><span data-ttu-id="c8c96-563">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c8c96-564">A tabela a seguir mostra o resultado quando os serviços financeiros são aplicados como base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="c8c96-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c8c96-565">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-565">Cost object</span></span></th>
<th><span data-ttu-id="c8c96-566">Magnitude</span><span class="sxs-lookup"><span data-stu-id="c8c96-566">Magnitude</span></span></th>
<th><span data-ttu-id="c8c96-567">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="c8c96-567">Allocation factor</span></span></th>
<th><span data-ttu-id="c8c96-568">Valor</span><span class="sxs-lookup"><span data-stu-id="c8c96-568">Amount</span></span></th>
<th><span data-ttu-id="c8c96-569">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-570">CC003</span><span class="sxs-lookup"><span data-stu-id="c8c96-570">CC003</span></span></td>
<td><span data-ttu-id="c8c96-571">Montagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-571">Assembly</span></span></td>
<td><span data-ttu-id="c8c96-572">65</span><span class="sxs-lookup"><span data-stu-id="c8c96-572">65</span></span></td>
<td><span data-ttu-id="c8c96-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="c8c96-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="c8c96-574">438.75</span><span class="sxs-lookup"><span data-stu-id="c8c96-574">438.75</span></span></td>
<td><span data-ttu-id="c8c96-575">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-576">CC004</span><span class="sxs-lookup"><span data-stu-id="c8c96-576">CC004</span></span></td>
<td><span data-ttu-id="c8c96-577">Embalagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-577">Packaging</span></span></td>
<td><span data-ttu-id="c8c96-578">35</span><span class="sxs-lookup"><span data-stu-id="c8c96-578">35</span></span></td>
<td><span data-ttu-id="c8c96-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="c8c96-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="c8c96-580">236.25</span><span class="sxs-lookup"><span data-stu-id="c8c96-580">236.25</span></span></td>
<td><span data-ttu-id="c8c96-581">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-582">CC003</span><span class="sxs-lookup"><span data-stu-id="c8c96-582">CC003</span></span></td>
<td><span data-ttu-id="c8c96-583">Montagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-583">Assembly</span></span></td>
<td><span data-ttu-id="c8c96-584">65</span><span class="sxs-lookup"><span data-stu-id="c8c96-584">65</span></span></td>
<td><span data-ttu-id="c8c96-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="c8c96-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="c8c96-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="c8c96-586">5,297.69</span></span></td>
<td><span data-ttu-id="c8c96-587">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-588">CC004</span><span class="sxs-lookup"><span data-stu-id="c8c96-588">CC004</span></span></td>
<td><span data-ttu-id="c8c96-589">Embalagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-589">Packaging</span></span></td>
<td><span data-ttu-id="c8c96-590">35</span><span class="sxs-lookup"><span data-stu-id="c8c96-590">35</span></span></td>
<td><span data-ttu-id="c8c96-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="c8c96-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="c8c96-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="c8c96-592">2,852.60</span></span></td>
<td><span data-ttu-id="c8c96-593">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c8c96-594">A tabela a seguir mostra o resultado quando os serviços de Montagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="c8c96-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c8c96-595">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-595">Cost object</span></span></th>
<th><span data-ttu-id="c8c96-596">Magnitude</span><span class="sxs-lookup"><span data-stu-id="c8c96-596">Magnitude</span></span></th>
<th><span data-ttu-id="c8c96-597">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="c8c96-597">Allocation factor</span></span></th>
<th><span data-ttu-id="c8c96-598">Valor</span><span class="sxs-lookup"><span data-stu-id="c8c96-598">Amount</span></span></th>
<th><span data-ttu-id="c8c96-599">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-600">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-600">Prod 1</span></span></td>
<td><span data-ttu-id="c8c96-601">Produto 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-601">Product 1</span></span></td>
<td><span data-ttu-id="c8c96-602">60</span><span class="sxs-lookup"><span data-stu-id="c8c96-602">60</span></span></td>
<td><span data-ttu-id="c8c96-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="c8c96-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="c8c96-604">535.31</span><span class="sxs-lookup"><span data-stu-id="c8c96-604">535.31</span></span></td>
<td><span data-ttu-id="c8c96-605">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-606">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-606">Prod 2</span></span></td>
<td><span data-ttu-id="c8c96-607">Produto 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-607">Product 2</span></span></td>
<td><span data-ttu-id="c8c96-608">20</span><span class="sxs-lookup"><span data-stu-id="c8c96-608">20</span></span></td>
<td><span data-ttu-id="c8c96-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="c8c96-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="c8c96-610">178.44</span><span class="sxs-lookup"><span data-stu-id="c8c96-610">178.44</span></span></td>
<td><span data-ttu-id="c8c96-611">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-612">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-612">Prod 1</span></span></td>
<td><span data-ttu-id="c8c96-613">Produto 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-613">Product 1</span></span></td>
<td><span data-ttu-id="c8c96-614">60</span><span class="sxs-lookup"><span data-stu-id="c8c96-614">60</span></span></td>
<td><span data-ttu-id="c8c96-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="c8c96-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="c8c96-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="c8c96-616">4,487.12</span></span></td>
<td><span data-ttu-id="c8c96-617">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-618">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-618">Prod 2</span></span></td>
<td><span data-ttu-id="c8c96-619">Produto 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-619">Product 2</span></span></td>
<td><span data-ttu-id="c8c96-620">20</span><span class="sxs-lookup"><span data-stu-id="c8c96-620">20</span></span></td>
<td><span data-ttu-id="c8c96-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="c8c96-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="c8c96-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="c8c96-622">1,495.71</span></span></td>
<td><span data-ttu-id="c8c96-623">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c8c96-624">A tabela a seguir mostra o resultado quando os serviços de Embalagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="c8c96-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c8c96-625">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-625">Cost object</span></span></th>
<th><span data-ttu-id="c8c96-626">Magnitude</span><span class="sxs-lookup"><span data-stu-id="c8c96-626">Magnitude</span></span></th>
<th><span data-ttu-id="c8c96-627">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="c8c96-627">Allocation factor</span></span></th>
<th><span data-ttu-id="c8c96-628">Valor</span><span class="sxs-lookup"><span data-stu-id="c8c96-628">Amount</span></span></th>
<th><span data-ttu-id="c8c96-629">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-630">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-630">Prod 1</span></span></td>
<td><span data-ttu-id="c8c96-631">Produto 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-631">Product 1</span></span></td>
<td><span data-ttu-id="c8c96-632">80</span><span class="sxs-lookup"><span data-stu-id="c8c96-632">80</span></span></td>
<td><span data-ttu-id="c8c96-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="c8c96-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="c8c96-634">241.05</span><span class="sxs-lookup"><span data-stu-id="c8c96-634">241.05</span></span></td>
<td><span data-ttu-id="c8c96-635">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-636">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-636">Prod 2</span></span></td>
<td><span data-ttu-id="c8c96-637">Produto 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-637">Product 2</span></span></td>
<td><span data-ttu-id="c8c96-638">15</span><span class="sxs-lookup"><span data-stu-id="c8c96-638">15</span></span></td>
<td><span data-ttu-id="c8c96-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="c8c96-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="c8c96-640">45.20</span><span class="sxs-lookup"><span data-stu-id="c8c96-640">45.20</span></span></td>
<td><span data-ttu-id="c8c96-641">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-642">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-642">Prod 1</span></span></td>
<td><span data-ttu-id="c8c96-643">Produto 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-643">Product 1</span></span></td>
<td><span data-ttu-id="c8c96-644">80</span><span class="sxs-lookup"><span data-stu-id="c8c96-644">80</span></span></td>
<td><span data-ttu-id="c8c96-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="c8c96-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="c8c96-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="c8c96-646">2,507.09</span></span></td>
<td><span data-ttu-id="c8c96-647">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-648">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-648">Prod 2</span></span></td>
<td><span data-ttu-id="c8c96-649">Produto 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-649">Product 2</span></span></td>
<td><span data-ttu-id="c8c96-650">15</span><span class="sxs-lookup"><span data-stu-id="c8c96-650">15</span></span></td>
<td><span data-ttu-id="c8c96-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="c8c96-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="c8c96-652">470.08</span><span class="sxs-lookup"><span data-stu-id="c8c96-652">470.08</span></span></td>
<td><span data-ttu-id="c8c96-653">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="c8c96-654">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="c8c96-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c8c96-655">Diário</span><span class="sxs-lookup"><span data-stu-id="c8c96-655">Journal</span></span></th>
<th><span data-ttu-id="c8c96-656">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="c8c96-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="c8c96-657">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="c8c96-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="c8c96-658">Versão</span><span class="sxs-lookup"><span data-stu-id="c8c96-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-659">00004</span><span class="sxs-lookup"><span data-stu-id="c8c96-659">00004</span></span></td>
<td><span data-ttu-id="c8c96-660">Diário de alocação de custos</span><span class="sxs-lookup"><span data-stu-id="c8c96-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="c8c96-661">fiscal</span><span class="sxs-lookup"><span data-stu-id="c8c96-661">Fiscal</span></span></td>
<td><span data-ttu-id="c8c96-662">2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-662">2017</span></span></td>
<td><span data-ttu-id="c8c96-663">Período 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-663">Period 1</span></span></td>
<td><span data-ttu-id="c8c96-664">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="c8c96-665">Linhas do diário</span><span class="sxs-lookup"><span data-stu-id="c8c96-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c8c96-666">Data contábil</span><span class="sxs-lookup"><span data-stu-id="c8c96-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c8c96-667">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c8c96-668">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-668">Cost element</span></span></th>
<th><span data-ttu-id="c8c96-669">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-669">Cost behavior</span></span></th>
<th><span data-ttu-id="c8c96-670">Valor</span><span class="sxs-lookup"><span data-stu-id="c8c96-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-671">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="c8c96-672">CC001</span><span class="sxs-lookup"><span data-stu-id="c8c96-672">CC001</span></span></td>
<td><span data-ttu-id="c8c96-673">RH</span><span class="sxs-lookup"><span data-stu-id="c8c96-673">HR</span></span></td>
<td><span data-ttu-id="c8c96-674">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-674">10001</span></span></td>
<td><span data-ttu-id="c8c96-675">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-675">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-676">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-676">Fixed cost</span></span></td>
<td><span data-ttu-id="c8c96-677">500,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-678">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="c8c96-679">CC001</span><span class="sxs-lookup"><span data-stu-id="c8c96-679">CC001</span></span></td>
<td><span data-ttu-id="c8c96-680">RH</span><span class="sxs-lookup"><span data-stu-id="c8c96-680">HR</span></span></td>
<td><span data-ttu-id="c8c96-681">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-681">10001</span></span></td>
<td><span data-ttu-id="c8c96-682">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-682">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-683">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-683">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="c8c96-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-685">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="c8c96-686">CC002</span><span class="sxs-lookup"><span data-stu-id="c8c96-686">CC002</span></span></td>
<td><span data-ttu-id="c8c96-687">Finanças</span><span class="sxs-lookup"><span data-stu-id="c8c96-687">Finance</span></span></td>
<td><span data-ttu-id="c8c96-688">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-688">10001</span></span></td>
<td><span data-ttu-id="c8c96-689">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-689">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-690">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-690">Fixed cost</span></span></td>
<td><span data-ttu-id="c8c96-691">675.00</span><span class="sxs-lookup"><span data-stu-id="c8c96-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-692">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="c8c96-693">CC002</span><span class="sxs-lookup"><span data-stu-id="c8c96-693">CC002</span></span></td>
<td><span data-ttu-id="c8c96-694">Finanças</span><span class="sxs-lookup"><span data-stu-id="c8c96-694">Finance</span></span></td>
<td><span data-ttu-id="c8c96-695">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-695">10001</span></span></td>
<td><span data-ttu-id="c8c96-696">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-696">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-697">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-697">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="c8c96-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-699">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="c8c96-700">CC003</span><span class="sxs-lookup"><span data-stu-id="c8c96-700">CC003</span></span></td>
<td><span data-ttu-id="c8c96-701">Montagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-701">Assembly</span></span></td>
<td><span data-ttu-id="c8c96-702">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-702">10001</span></span></td>
<td><span data-ttu-id="c8c96-703">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-703">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-704">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-704">Fixed cost</span></span></td>
<td><span data-ttu-id="c8c96-705">713.75</span><span class="sxs-lookup"><span data-stu-id="c8c96-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-706">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="c8c96-707">CC003</span><span class="sxs-lookup"><span data-stu-id="c8c96-707">CC003</span></span></td>
<td><span data-ttu-id="c8c96-708">Montagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-708">Assembly</span></span></td>
<td><span data-ttu-id="c8c96-709">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-709">10001</span></span></td>
<td><span data-ttu-id="c8c96-710">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-710">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-711">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-711">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="c8c96-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-713">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="c8c96-714">CC003</span><span class="sxs-lookup"><span data-stu-id="c8c96-714">CC003</span></span></td>
<td><span data-ttu-id="c8c96-715">Embalagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-715">Packaging</span></span></td>
<td><span data-ttu-id="c8c96-716">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-716">10001</span></span></td>
<td><span data-ttu-id="c8c96-717">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-717">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-718">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-718">Fixed cost</span></span></td>
<td><span data-ttu-id="c8c96-719">286.25</span><span class="sxs-lookup"><span data-stu-id="c8c96-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-720">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="c8c96-721">CC003</span><span class="sxs-lookup"><span data-stu-id="c8c96-721">CC003</span></span></td>
<td><span data-ttu-id="c8c96-722">Embalagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-722">Packaging</span></span></td>
<td><span data-ttu-id="c8c96-723">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-723">10001</span></span></td>
<td><span data-ttu-id="c8c96-724">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-724">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-725">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-725">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="c8c96-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-727">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="c8c96-728">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-728">Prod 1</span></span></td>
<td><span data-ttu-id="c8c96-729">Produto 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-729">Product 1</span></span></td>
<td><span data-ttu-id="c8c96-730">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-730">10001</span></span></td>
<td><span data-ttu-id="c8c96-731">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-731">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-732">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-732">Fixed cost</span></span></td>
<td><span data-ttu-id="c8c96-733">776.36</span><span class="sxs-lookup"><span data-stu-id="c8c96-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-734">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="c8c96-735">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-735">Prod 1</span></span></td>
<td><span data-ttu-id="c8c96-736">Produto 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-736">Product 1</span></span></td>
<td><span data-ttu-id="c8c96-737">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-737">10001</span></span></td>
<td><span data-ttu-id="c8c96-738">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-738">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-739">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-739">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="c8c96-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-741">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="c8c96-742">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-742">Prod 2</span></span></td>
<td><span data-ttu-id="c8c96-743">Produto 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-743">Product 1</span></span></td>
<td><span data-ttu-id="c8c96-744">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-744">10001</span></span></td>
<td><span data-ttu-id="c8c96-745">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-745">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-746">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-746">Fixed cost</span></span></td>
<td><span data-ttu-id="c8c96-747">223.64</span><span class="sxs-lookup"><span data-stu-id="c8c96-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-748">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="c8c96-749">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-749">Prod 2</span></span></td>
<td><span data-ttu-id="c8c96-750">Produto 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-750">Product 1</span></span></td>
<td><span data-ttu-id="c8c96-751">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-751">10001</span></span></td>
<td><span data-ttu-id="c8c96-752">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-752">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-753">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-753">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="c8c96-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="c8c96-755">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c8c96-756">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c8c96-757">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-757">Cost element</span></span></th>
<th><span data-ttu-id="c8c96-758">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-758">Cost behavior</span></span></th>
<th><span data-ttu-id="c8c96-759">Valor</span><span class="sxs-lookup"><span data-stu-id="c8c96-759">Amount</span></span></th>
<th><span data-ttu-id="c8c96-760">Data contábil</span><span class="sxs-lookup"><span data-stu-id="c8c96-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c8c96-761">CC001</span><span class="sxs-lookup"><span data-stu-id="c8c96-761">CC001</span></span></td>
<td><span data-ttu-id="c8c96-762">RH</span><span class="sxs-lookup"><span data-stu-id="c8c96-762">HR</span></span></td>
<td><span data-ttu-id="c8c96-763">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-763">10001</span></span></td>
<td><span data-ttu-id="c8c96-764">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-764">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-765">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-765">Fixed cost</span></span></td>
<td><span data-ttu-id="c8c96-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-766">-500.00</span></span></td>
<td><span data-ttu-id="c8c96-767">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-768">CC002</span><span class="sxs-lookup"><span data-stu-id="c8c96-768">CC002</span></span></td>
<td><span data-ttu-id="c8c96-769">Finanças</span><span class="sxs-lookup"><span data-stu-id="c8c96-769">Finance</span></span></td>
<td><span data-ttu-id="c8c96-770">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-770">10001</span></span></td>
<td><span data-ttu-id="c8c96-771">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-771">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-772">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-772">Fixed cost</span></span></td>
<td><span data-ttu-id="c8c96-773">175.00</span><span class="sxs-lookup"><span data-stu-id="c8c96-773">175.00</span></span></td>
<td><span data-ttu-id="c8c96-774">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-775">CC003</span><span class="sxs-lookup"><span data-stu-id="c8c96-775">CC003</span></span></td>
<td><span data-ttu-id="c8c96-776">Montagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-776">Assembly</span></span></td>
<td><span data-ttu-id="c8c96-777">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-777">10001</span></span></td>
<td><span data-ttu-id="c8c96-778">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-778">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-779">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-779">Fixed cost</span></span></td>
<td><span data-ttu-id="c8c96-780">275.00</span><span class="sxs-lookup"><span data-stu-id="c8c96-780">275.00</span></span></td>
<td><span data-ttu-id="c8c96-781">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-782">CC004</span><span class="sxs-lookup"><span data-stu-id="c8c96-782">CC004</span></span></td>
<td><span data-ttu-id="c8c96-783">Embalagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-783">Packaging</span></span></td>
<td><span data-ttu-id="c8c96-784">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-784">10001</span></span></td>
<td><span data-ttu-id="c8c96-785">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-785">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-786">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-786">Fixed cost</span></span></td>
<td><span data-ttu-id="c8c96-787">50,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-787">50,00</span></span></td>
<td><span data-ttu-id="c8c96-788">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-789">CC001</span><span class="sxs-lookup"><span data-stu-id="c8c96-789">CC001</span></span></td>
<td><span data-ttu-id="c8c96-790">RH</span><span class="sxs-lookup"><span data-stu-id="c8c96-790">HR</span></span></td>
<td><span data-ttu-id="c8c96-791">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-791">10001</span></span></td>
<td><span data-ttu-id="c8c96-792">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-792">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-793">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-793">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="c8c96-794">-1,245.71</span></span></td>
<td><span data-ttu-id="c8c96-795">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-796">CC002</span><span class="sxs-lookup"><span data-stu-id="c8c96-796">CC002</span></span></td>
<td><span data-ttu-id="c8c96-797">Finanças</span><span class="sxs-lookup"><span data-stu-id="c8c96-797">Finance</span></span></td>
<td><span data-ttu-id="c8c96-798">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-798">10001</span></span></td>
<td><span data-ttu-id="c8c96-799">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-799">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-800">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-800">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-801">436.00</span><span class="sxs-lookup"><span data-stu-id="c8c96-801">436.00</span></span></td>
<td><span data-ttu-id="c8c96-802">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-803">CC003</span><span class="sxs-lookup"><span data-stu-id="c8c96-803">CC003</span></span></td>
<td><span data-ttu-id="c8c96-804">Montagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-804">Assembly</span></span></td>
<td><span data-ttu-id="c8c96-805">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-805">10001</span></span></td>
<td><span data-ttu-id="c8c96-806">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-806">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-807">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-807">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-808">685.14</span><span class="sxs-lookup"><span data-stu-id="c8c96-808">685.14</span></span></td>
<td><span data-ttu-id="c8c96-809">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-810">CC004</span><span class="sxs-lookup"><span data-stu-id="c8c96-810">CC004</span></span></td>
<td><span data-ttu-id="c8c96-811">Embalagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-811">Packaging</span></span></td>
<td><span data-ttu-id="c8c96-812">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-812">10001</span></span></td>
<td><span data-ttu-id="c8c96-813">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-813">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-814">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-814">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-815">124.57</span><span class="sxs-lookup"><span data-stu-id="c8c96-815">124.57</span></span></td>
<td><span data-ttu-id="c8c96-816">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-817">CC002</span><span class="sxs-lookup"><span data-stu-id="c8c96-817">CC002</span></span></td>
<td><span data-ttu-id="c8c96-818">Finanças</span><span class="sxs-lookup"><span data-stu-id="c8c96-818">Finance</span></span></td>
<td><span data-ttu-id="c8c96-819">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-819">10001</span></span></td>
<td><span data-ttu-id="c8c96-820">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-820">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-821">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-821">Fixed cost</span></span></td>
<td><span data-ttu-id="c8c96-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-822">-675.00</span></span></td>
<td><span data-ttu-id="c8c96-823">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-824">CC003</span><span class="sxs-lookup"><span data-stu-id="c8c96-824">CC003</span></span></td>
<td><span data-ttu-id="c8c96-825">Montagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-825">Assembly</span></span></td>
<td><span data-ttu-id="c8c96-826">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-826">10001</span></span></td>
<td><span data-ttu-id="c8c96-827">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-827">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-828">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-828">Fixed cost</span></span></td>
<td><span data-ttu-id="c8c96-829">438.75</span><span class="sxs-lookup"><span data-stu-id="c8c96-829">438.75</span></span></td>
<td><span data-ttu-id="c8c96-830">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-831">CC004</span><span class="sxs-lookup"><span data-stu-id="c8c96-831">CC004</span></span></td>
<td><span data-ttu-id="c8c96-832">Embalagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-832">Packaging</span></span></td>
<td><span data-ttu-id="c8c96-833">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-833">10001</span></span></td>
<td><span data-ttu-id="c8c96-834">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-834">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-835">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-835">Fixed cost</span></span></td>
<td><span data-ttu-id="c8c96-836">236.25</span><span class="sxs-lookup"><span data-stu-id="c8c96-836">236.25</span></span></td>
<td><span data-ttu-id="c8c96-837">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-838">CC002</span><span class="sxs-lookup"><span data-stu-id="c8c96-838">CC002</span></span></td>
<td><span data-ttu-id="c8c96-839">Finanças</span><span class="sxs-lookup"><span data-stu-id="c8c96-839">Finance</span></span></td>
<td><span data-ttu-id="c8c96-840">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-840">10001</span></span></td>
<td><span data-ttu-id="c8c96-841">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-841">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-842">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-842">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="c8c96-843">-8,150.29</span></span></td>
<td><span data-ttu-id="c8c96-844">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-845">CC003</span><span class="sxs-lookup"><span data-stu-id="c8c96-845">CC003</span></span></td>
<td><span data-ttu-id="c8c96-846">Montagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-846">Assembly</span></span></td>
<td><span data-ttu-id="c8c96-847">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-847">10001</span></span></td>
<td><span data-ttu-id="c8c96-848">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-848">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-849">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-849">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="c8c96-850">5,297.69</span></span></td>
<td><span data-ttu-id="c8c96-851">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-852">CC004</span><span class="sxs-lookup"><span data-stu-id="c8c96-852">CC004</span></span></td>
<td><span data-ttu-id="c8c96-853">Embalagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-853">Packaging</span></span></td>
<td><span data-ttu-id="c8c96-854">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-854">10001</span></span></td>
<td><span data-ttu-id="c8c96-855">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-855">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-856">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-856">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="c8c96-857">2,852.60</span></span></td>
<td><span data-ttu-id="c8c96-858">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-859">CC003</span><span class="sxs-lookup"><span data-stu-id="c8c96-859">CC003</span></span></td>
<td><span data-ttu-id="c8c96-860">Montagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-860">Assembly</span></span></td>
<td><span data-ttu-id="c8c96-861">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-861">10001</span></span></td>
<td><span data-ttu-id="c8c96-862">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-862">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-863">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-863">Fixed cost</span></span></td>
<td><span data-ttu-id="c8c96-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="c8c96-864">-713.75</span></span></td>
<td><span data-ttu-id="c8c96-865">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-866">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-866">Prod 1</span></span></td>
<td><span data-ttu-id="c8c96-867">Produto 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-867">Product 1</span></span></td>
<td><span data-ttu-id="c8c96-868">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-868">10001</span></span></td>
<td><span data-ttu-id="c8c96-869">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-869">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-870">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-870">Fixed cost</span></span></td>
<td><span data-ttu-id="c8c96-871">535.31</span><span class="sxs-lookup"><span data-stu-id="c8c96-871">535.31</span></span></td>
<td><span data-ttu-id="c8c96-872">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-873">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-873">Prod 2</span></span></td>
<td><span data-ttu-id="c8c96-874">Produto 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-874">Product 2</span></span></td>
<td><span data-ttu-id="c8c96-875">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-875">10001</span></span></td>
<td><span data-ttu-id="c8c96-876">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-876">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-877">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-877">Fixed cost</span></span></td>
<td><span data-ttu-id="c8c96-878">178.44</span><span class="sxs-lookup"><span data-stu-id="c8c96-878">178.44</span></span></td>
<td><span data-ttu-id="c8c96-879">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-880">CC003</span><span class="sxs-lookup"><span data-stu-id="c8c96-880">CC003</span></span></td>
<td><span data-ttu-id="c8c96-881">Montagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-881">Assembly</span></span></td>
<td><span data-ttu-id="c8c96-882">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-882">10001</span></span></td>
<td><span data-ttu-id="c8c96-883">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-883">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-884">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-884">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="c8c96-885">-5,982.83</span></span></td>
<td><span data-ttu-id="c8c96-886">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-887">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-887">Prod 1</span></span></td>
<td><span data-ttu-id="c8c96-888">Produto 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-888">Product 1</span></span></td>
<td><span data-ttu-id="c8c96-889">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-889">10001</span></span></td>
<td><span data-ttu-id="c8c96-890">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-890">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-891">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-891">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="c8c96-892">4,487.12</span></span></td>
<td><span data-ttu-id="c8c96-893">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-894">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-894">Prod 2</span></span></td>
<td><span data-ttu-id="c8c96-895">Produto 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-895">Product 2</span></span></td>
<td><span data-ttu-id="c8c96-896">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-896">10001</span></span></td>
<td><span data-ttu-id="c8c96-897">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-897">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-898">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-898">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="c8c96-899">1,495.71</span></span></td>
<td><span data-ttu-id="c8c96-900">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-901">CC003</span><span class="sxs-lookup"><span data-stu-id="c8c96-901">CC003</span></span></td>
<td><span data-ttu-id="c8c96-902">Montagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-902">Assembly</span></span></td>
<td><span data-ttu-id="c8c96-903">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-903">10001</span></span></td>
<td><span data-ttu-id="c8c96-904">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-904">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-905">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-905">Fixed cost</span></span></td>
<td><span data-ttu-id="c8c96-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="c8c96-906">-286.25</span></span></td>
<td><span data-ttu-id="c8c96-907">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-908">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-908">Prod 1</span></span></td>
<td><span data-ttu-id="c8c96-909">Produto 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-909">Product 1</span></span></td>
<td><span data-ttu-id="c8c96-910">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-910">10001</span></span></td>
<td><span data-ttu-id="c8c96-911">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-911">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-912">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-912">Fixed cost</span></span></td>
<td><span data-ttu-id="c8c96-913">241.05</span><span class="sxs-lookup"><span data-stu-id="c8c96-913">241.05</span></span></td>
<td><span data-ttu-id="c8c96-914">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-915">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-915">Prod 2</span></span></td>
<td><span data-ttu-id="c8c96-916">Produto 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-916">Product 2</span></span></td>
<td><span data-ttu-id="c8c96-917">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-917">10001</span></span></td>
<td><span data-ttu-id="c8c96-918">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-918">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-919">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-919">Fixed cost</span></span></td>
<td><span data-ttu-id="c8c96-920">45.20</span><span class="sxs-lookup"><span data-stu-id="c8c96-920">45.20</span></span></td>
<td><span data-ttu-id="c8c96-921">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-922">CC003</span><span class="sxs-lookup"><span data-stu-id="c8c96-922">CC003</span></span></td>
<td><span data-ttu-id="c8c96-923">Montagem</span><span class="sxs-lookup"><span data-stu-id="c8c96-923">Assembly</span></span></td>
<td><span data-ttu-id="c8c96-924">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-924">10001</span></span></td>
<td><span data-ttu-id="c8c96-925">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-925">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-926">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-926">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="c8c96-927">-2,977.17</span></span></td>
<td><span data-ttu-id="c8c96-928">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-929">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-929">Prod 1</span></span></td>
<td><span data-ttu-id="c8c96-930">Produto 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-930">Product 1</span></span></td>
<td><span data-ttu-id="c8c96-931">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-931">10001</span></span></td>
<td><span data-ttu-id="c8c96-932">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-932">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-933">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-933">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="c8c96-934">2,507.09</span></span></td>
<td><span data-ttu-id="c8c96-935">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c8c96-936">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-936">Prod 2</span></span></td>
<td><span data-ttu-id="c8c96-937">Produto 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-937">Product 2</span></span></td>
<td><span data-ttu-id="c8c96-938">10001</span><span class="sxs-lookup"><span data-stu-id="c8c96-938">10001</span></span></td>
<td><span data-ttu-id="c8c96-939">eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-939">Electricity</span></span></td>
<td><span data-ttu-id="c8c96-940">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-940">Variable cost</span></span></td>
<td><span data-ttu-id="c8c96-941">470.08</span><span class="sxs-lookup"><span data-stu-id="c8c96-941">470.08</span></span></td>
<td><span data-ttu-id="c8c96-942">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="c8c96-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="c8c96-943">Conclusão</span><span class="sxs-lookup"><span data-stu-id="c8c96-943">Conclusion</span></span>
<span data-ttu-id="c8c96-944">Na contabilidade financeira, um custo de 10,000.00 para a eletricidade é lançado para um ID fictício de centro de custos.</span><span class="sxs-lookup"><span data-stu-id="c8c96-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="c8c96-945">Portanto, os contadores de custo saberão que esses custos devem ser alocados.</span><span class="sxs-lookup"><span data-stu-id="c8c96-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="c8c96-946">Na contabilização de custo, os custos fluem nas unidades organizacionais e nos níveis, com base nas políticas e regras que são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="c8c96-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="c8c96-947">Cada custo foi associado a uma base de alocação que fornece a melhor apuração para a alocação de custos.</span><span class="sxs-lookup"><span data-stu-id="c8c96-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="c8c96-948">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="c8c96-949">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="c8c96-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="c8c96-950">Total</span><span class="sxs-lookup"><span data-stu-id="c8c96-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="c8c96-951">CC099</span><span class="sxs-lookup"><span data-stu-id="c8c96-951">CC099</span></span></th>
<th><span data-ttu-id="c8c96-952">CC001</span><span class="sxs-lookup"><span data-stu-id="c8c96-952">CC001</span></span></th>
<th><span data-ttu-id="c8c96-953">CC002</span><span class="sxs-lookup"><span data-stu-id="c8c96-953">CC002</span></span></th>
<th><span data-ttu-id="c8c96-954">CC003</span><span class="sxs-lookup"><span data-stu-id="c8c96-954">CC003</span></span></th>
<th><span data-ttu-id="c8c96-955">CC004</span><span class="sxs-lookup"><span data-stu-id="c8c96-955">CC004</span></span></th>
<th><span data-ttu-id="c8c96-956">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-956">Proj 1</span></span></th>
<th><span data-ttu-id="c8c96-957">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-957">Proj 2</span></span></th>
<th><span data-ttu-id="c8c96-958">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="c8c96-958">Prod 1</span></span></th>
<th><span data-ttu-id="c8c96-959">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="c8c96-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="c8c96-960">10001 Eletricidade</span><span class="sxs-lookup"><span data-stu-id="c8c96-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="c8c96-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="c8c96-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="c8c96-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="c8c96-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="c8c96-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="c8c96-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="c8c96-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="c8c96-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="c8c96-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="c8c96-970">Não classificado</span><span class="sxs-lookup"><span data-stu-id="c8c96-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-971">0,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="c8c96-972">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="c8c96-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-973">0,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-974">0,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-975">0,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-976">0,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-977">0,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-978">776.36</span><span class="sxs-lookup"><span data-stu-id="c8c96-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-979">223.64</span><span class="sxs-lookup"><span data-stu-id="c8c96-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="c8c96-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="c8c96-981">Custo variável</span><span class="sxs-lookup"><span data-stu-id="c8c96-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-982">000</span><span class="sxs-lookup"><span data-stu-id="c8c96-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-983">0,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-984">0,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-985">0,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-986">0,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-987">30,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-988">10,00</span><span class="sxs-lookup"><span data-stu-id="c8c96-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="c8c96-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="c8c96-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c8c96-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="c8c96-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="c8c96-992">Esse tópico mostra como um elemento de custo principal, 10001 Eletricidade flui pelos objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="c8c96-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="c8c96-993">Portanto, esse custo geral indireto é alocado no nível mais baixo na organização.</span><span class="sxs-lookup"><span data-stu-id="c8c96-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="c8c96-994">Em outras palavras, os objetos de custo no nível mais baixo assumem o custo.</span><span class="sxs-lookup"><span data-stu-id="c8c96-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="c8c96-995">Se você exigir um fluxo visual de custo entre objetos de custo, é possível usar as regras de política de acúmulo de custos para visualizar o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="c8c96-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="c8c96-996">Para obter mais informações, consulte [Política de acúmulo de custo e cálculo de custos indiretos](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="c8c96-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



