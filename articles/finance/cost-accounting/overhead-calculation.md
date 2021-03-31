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
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 882804141a6b520e2420343958c7a6b02a7e09ae
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208838"
---
# <a name="overhead-calculation"></a><span data-ttu-id="dd57f-103">Cálculo de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="dd57f-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dd57f-104">Este tópico descreve processos comuns para calcular e alocar os custos gerais indiretos.</span><span class="sxs-lookup"><span data-stu-id="dd57f-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="dd57f-105">Definição de termo</span><span class="sxs-lookup"><span data-stu-id="dd57f-105">Term definition</span></span>
---------------

<span data-ttu-id="dd57f-106">Os custos gerais indiretos são aqueles que foram incorridos para realizar um negócio, mas não podem ser diretamente atribuídos a qualquer atividade comercial, produto ou serviço específico.</span><span class="sxs-lookup"><span data-stu-id="dd57f-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="dd57f-107">Os custos gerais indiretos fornecem suporte crítico para geração de atividades produtivas.</span><span class="sxs-lookup"><span data-stu-id="dd57f-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="dd57f-108">Eis alguns exemplos de custos gerais:</span><span class="sxs-lookup"><span data-stu-id="dd57f-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="dd57f-109">Aluguel</span><span class="sxs-lookup"><span data-stu-id="dd57f-109">Rent</span></span>
-   <span data-ttu-id="dd57f-110">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-110">Electricity</span></span>
-   <span data-ttu-id="dd57f-111">Salários administrativos</span><span class="sxs-lookup"><span data-stu-id="dd57f-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="dd57f-112">Visão geral do cálculo de custos gerais indiretos</span><span class="sxs-lookup"><span data-stu-id="dd57f-112">Overhead calculation overview</span></span>
<span data-ttu-id="dd57f-113">O cálculo de custos gerais indiretos executa as políticas de contabilização de custos na ordem correta.</span><span class="sxs-lookup"><span data-stu-id="dd57f-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="dd57f-114">Você pode executar o cálculo de custos gerais indiretos várias vezes para o mesmo período fiscal, se as políticas de contabilidade de custo foram modificadas ou foram detectados erros específicos.</span><span class="sxs-lookup"><span data-stu-id="dd57f-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="dd57f-115">Cada execução do cálculo de custos gerais indiretos é armazenada e recebe um ID exclusivo de versão que permite comparar os cálculos em várias versões.</span><span class="sxs-lookup"><span data-stu-id="dd57f-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="dd57f-116">As entradas de custo que o cálculo de custos indiretos gera recebe uma data contábil.</span><span class="sxs-lookup"><span data-stu-id="dd57f-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="dd57f-117">Essa data contábil corresponde à data final do período fiscal que é usada no cálculo.</span><span class="sxs-lookup"><span data-stu-id="dd57f-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="dd57f-118">A ID exclusiva de versão consiste nos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="dd57f-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="dd57f-119">Tipo de versão</span><span class="sxs-lookup"><span data-stu-id="dd57f-119">Version type</span></span>
-   <span data-ttu-id="dd57f-120">Data e hora</span><span class="sxs-lookup"><span data-stu-id="dd57f-120">Date and time</span></span>
-   <span data-ttu-id="dd57f-121">Razão de contabilização de custos</span><span class="sxs-lookup"><span data-stu-id="dd57f-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="dd57f-122">Ano fiscal</span><span class="sxs-lookup"><span data-stu-id="dd57f-122">Fiscal year</span></span>
-   <span data-ttu-id="dd57f-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="dd57f-123">Fiscal period</span></span>

<span data-ttu-id="dd57f-124">O cálculo de custos gerais indiretos é executado independentemente da versão.</span><span class="sxs-lookup"><span data-stu-id="dd57f-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="dd57f-125">Portanto, você pode calcular a versão de orçamento antes da versão atual.</span><span class="sxs-lookup"><span data-stu-id="dd57f-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="dd57f-126">O cálculo de custos gerais indiretos consiste em quatro etapas, conforme mostrado na ilustração.</span><span class="sxs-lookup"><span data-stu-id="dd57f-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="dd57f-127">Em cada etapa, um cabeçalho de diário é criado com entradas de diário.</span><span class="sxs-lookup"><span data-stu-id="dd57f-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="dd57f-128">Esse cabeçalho de diário mantém dados de entrada para cada etapa de cálculo.</span><span class="sxs-lookup"><span data-stu-id="dd57f-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="dd57f-129">As políticas e regras são aplicadas a cada linha do diário e as entradas de custo são geradas como saídas.</span><span class="sxs-lookup"><span data-stu-id="dd57f-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="dd57f-130">Portanto, você sempre terá rastreabilidade total.</span><span class="sxs-lookup"><span data-stu-id="dd57f-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="dd57f-131">[![Cálculo de custos gerais indiretos](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="dd57f-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="dd57f-132">Calcular e alocar os custos gerais indiretos de Eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="dd57f-133">Na contabilidade financeira, alguns custos, como eletricidade, são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="dd57f-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="dd57f-134">Portanto, a visão administrativa detalhada não é fornecida para a contabilização de custo.</span><span class="sxs-lookup"><span data-stu-id="dd57f-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="dd57f-135">Na contabilização de custo, para fornecer a visão administrativa correta em todas as unidades organizacionais e níveis, os custos devem passar pelas unidades organizacionais.</span><span class="sxs-lookup"><span data-stu-id="dd57f-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="dd57f-136">Este fluxo deve ser baseado em qualquer um registro exato do consumo ou de uma previsão justa.</span><span class="sxs-lookup"><span data-stu-id="dd57f-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="dd57f-137">Na contabilidade, um custo de eletricidade pode ser lançado, conforme mostrado na tabela.</span><span class="sxs-lookup"><span data-stu-id="dd57f-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dd57f-138">Data contábil</span><span class="sxs-lookup"><span data-stu-id="dd57f-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="dd57f-139">Centro de custos</span><span class="sxs-lookup"><span data-stu-id="dd57f-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="dd57f-140">Conta principal</span><span class="sxs-lookup"><span data-stu-id="dd57f-140">Main account</span></span></th>
<th><span data-ttu-id="dd57f-141">Valor na moeda contábil</span><span class="sxs-lookup"><span data-stu-id="dd57f-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-142">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="dd57f-143">CC099</span><span class="sxs-lookup"><span data-stu-id="dd57f-143">CC099</span></span></td>
<td><span data-ttu-id="dd57f-144">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="dd57f-144">Default cost center</span></span></td>
<td><span data-ttu-id="dd57f-145">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-145">10001</span></span></td>
<td><span data-ttu-id="dd57f-146">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-146">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="dd57f-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="dd57f-148">Etapa 1: Processar o cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="dd57f-149">Por padrão, quando as entradas de custo previsto são importadas de dados de origem, elas recebem a classificação de comportamento de custo **Não classificado** na Contabilidade de custos.</span><span class="sxs-lookup"><span data-stu-id="dd57f-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="dd57f-150">Aplicando regras da política de comportamento de custo, é possível reclassificar entradas de custo como **Custo fixo** ou **Custo variável**.</span><span class="sxs-lookup"><span data-stu-id="dd57f-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="dd57f-151">Definir a regra de custo de comportamento</span><span class="sxs-lookup"><span data-stu-id="dd57f-151">Define the cost behavior rule</span></span>

<span data-ttu-id="dd57f-152">Em alguns casos, parte do custo é uma taxa fixa e o custos pendente é baseado no consumo.</span><span class="sxs-lookup"><span data-stu-id="dd57f-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="dd57f-153">Geralmente, as contas de eletricidade correspondem a esta definição.</span><span class="sxs-lookup"><span data-stu-id="dd57f-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="dd57f-154">Após você pagar uma taxa fixa específica, você paga por consumo, por hora de quilowatt (Kwh).</span><span class="sxs-lookup"><span data-stu-id="dd57f-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="dd57f-155">Por exemplo, se a taxa de custo fixa for 1.000.00, veja aqui como a regra de comportamento de custo é definida:</span><span class="sxs-lookup"><span data-stu-id="dd57f-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="dd57f-156">Valor fixo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="dd57f-157">0 &lt;= 1.000,00 = Fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="dd57f-158">1000.01 &lt; N = Variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="dd57f-159">Diário</span><span class="sxs-lookup"><span data-stu-id="dd57f-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dd57f-160">Diário</span><span class="sxs-lookup"><span data-stu-id="dd57f-160">Journal</span></span></th>
<th><span data-ttu-id="dd57f-161">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="dd57f-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="dd57f-162">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="dd57f-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="dd57f-163">Versão</span><span class="sxs-lookup"><span data-stu-id="dd57f-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-164">00001</span><span class="sxs-lookup"><span data-stu-id="dd57f-164">00001</span></span></td>
<td><span data-ttu-id="dd57f-165">Diário de cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="dd57f-166">fiscal</span><span class="sxs-lookup"><span data-stu-id="dd57f-166">Fiscal</span></span></td>
<td><span data-ttu-id="dd57f-167">2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-167">2017</span></span></td>
<td><span data-ttu-id="dd57f-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-168">Period 1</span></span></td>
<td><span data-ttu-id="dd57f-169">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="dd57f-170">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="dd57f-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dd57f-171">Data contábil</span><span class="sxs-lookup"><span data-stu-id="dd57f-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="dd57f-172">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="dd57f-173">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-173">Cost element</span></span></th>
<th><span data-ttu-id="dd57f-174">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-174">Cost behavior</span></span></th>
<th><span data-ttu-id="dd57f-175">Valor</span><span class="sxs-lookup"><span data-stu-id="dd57f-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-176">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="dd57f-177">CC099</span><span class="sxs-lookup"><span data-stu-id="dd57f-177">CC099</span></span></td>
<td><span data-ttu-id="dd57f-178">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="dd57f-178">Default cost center</span></span></td>
<td><span data-ttu-id="dd57f-179">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-179">10001</span></span></td>
<td><span data-ttu-id="dd57f-180">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-180">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-181">Não classificado</span><span class="sxs-lookup"><span data-stu-id="dd57f-181">Unclassified</span></span></td>
<td><span data-ttu-id="dd57f-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="dd57f-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="dd57f-183">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dd57f-184">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="dd57f-185">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-185">Cost element</span></span></th>
<th><span data-ttu-id="dd57f-186">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-186">Cost behavior</span></span></th>
<th><span data-ttu-id="dd57f-187">Valor</span><span class="sxs-lookup"><span data-stu-id="dd57f-187">Amount</span></span></th>
<th><span data-ttu-id="dd57f-188">Data contábil</span><span class="sxs-lookup"><span data-stu-id="dd57f-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-189">CC099</span><span class="sxs-lookup"><span data-stu-id="dd57f-189">CC099</span></span></td>
<td><span data-ttu-id="dd57f-190">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="dd57f-190">Default cost center</span></span></td>
<td><span data-ttu-id="dd57f-191">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-191">10001</span></span></td>
<td><span data-ttu-id="dd57f-192">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-192">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-193">Não classificado</span><span class="sxs-lookup"><span data-stu-id="dd57f-193">Unclassified</span></span></td>
<td><span data-ttu-id="dd57f-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="dd57f-194">10,000.00</span></span></td>
<td><span data-ttu-id="dd57f-195">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-196">CC099</span><span class="sxs-lookup"><span data-stu-id="dd57f-196">CC099</span></span></td>
<td><span data-ttu-id="dd57f-197">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="dd57f-197">Default cost center</span></span></td>
<td><span data-ttu-id="dd57f-198">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-198">10001</span></span></td>
<td><span data-ttu-id="dd57f-199">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-199">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-200">Não classificado</span><span class="sxs-lookup"><span data-stu-id="dd57f-200">Unclassified</span></span></td>
<td><span data-ttu-id="dd57f-201">-10.000,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-201">-10,000.00</span></span></td>
<td><span data-ttu-id="dd57f-202">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-203">CC099</span><span class="sxs-lookup"><span data-stu-id="dd57f-203">CC099</span></span></td>
<td><span data-ttu-id="dd57f-204">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="dd57f-204">Default cost center</span></span></td>
<td><span data-ttu-id="dd57f-205">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-205">10001</span></span></td>
<td><span data-ttu-id="dd57f-206">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-206">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-207">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-207">Fixed cost</span></span></td>
<td><span data-ttu-id="dd57f-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-208">1,000.00</span></span></td>
<td><span data-ttu-id="dd57f-209">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-210">CC099</span><span class="sxs-lookup"><span data-stu-id="dd57f-210">CC099</span></span></td>
<td><span data-ttu-id="dd57f-211">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="dd57f-211">Default cost center</span></span></td>
<td><span data-ttu-id="dd57f-212">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-212">10001</span></span></td>
<td><span data-ttu-id="dd57f-213">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-213">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-214">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-214">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="dd57f-215">9,000.00</span></span></td>
<td><span data-ttu-id="dd57f-216">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dd57f-217">Para obter mais informações, consulte [Criar e atribuir uma política de comportamento de custos a uma unidade de controle de custos](tasks/create-assign-cost-behavior-policy-cost-control-unit.md)</span><span class="sxs-lookup"><span data-stu-id="dd57f-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="dd57f-218">Etapa 2: Processar o cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="dd57f-219">A distribuição de custos é usada para redistribuir custo de um objeto de custo a um ou mais outros objetos de custo, aplicando uma base de alocação relevante.</span><span class="sxs-lookup"><span data-stu-id="dd57f-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="dd57f-220">A distribuição de custos e a alocação de custo são diferentes na distribuição de custos, sempre que ocorrer em nível de elemento de custo principal do custo original.</span><span class="sxs-lookup"><span data-stu-id="dd57f-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="dd57f-221">Definir a regra de distribuição de custos</span><span class="sxs-lookup"><span data-stu-id="dd57f-221">Define the cost distribution rule</span></span>

<span data-ttu-id="dd57f-222">Na contabilidade financeira, os custos de eletricidade geralmente são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="dd57f-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="dd57f-223">Na contabilização de custo, esta abordagem não é suficientemente detalhada.</span><span class="sxs-lookup"><span data-stu-id="dd57f-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="dd57f-224">O custo variável deve ser distribuído a objetos de custos individuais com base justa.</span><span class="sxs-lookup"><span data-stu-id="dd57f-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="dd57f-225">A base de alocação mais lógica é o consumo de eletricidade (Kwh).</span><span class="sxs-lookup"><span data-stu-id="dd57f-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="dd57f-226">O membro da dimensão estatística que é chamado Eletricidade é criado e o consumo de eletricidade é registrado.</span><span class="sxs-lookup"><span data-stu-id="dd57f-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="dd57f-227">Por padrão, todos os membros estatísticos da dimensão se tornam disponíveis como bases de alocação.</span><span class="sxs-lookup"><span data-stu-id="dd57f-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dd57f-228">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-228">Cost object</span></span></th>
<th><span data-ttu-id="dd57f-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="dd57f-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-230">CC001</span><span class="sxs-lookup"><span data-stu-id="dd57f-230">CC001</span></span></td>
<td><span data-ttu-id="dd57f-231">RH</span><span class="sxs-lookup"><span data-stu-id="dd57f-231">HR</span></span></td>
<td><span data-ttu-id="dd57f-232">1.000</span><span class="sxs-lookup"><span data-stu-id="dd57f-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-233">CC002</span><span class="sxs-lookup"><span data-stu-id="dd57f-233">CC002</span></span></td>
<td><span data-ttu-id="dd57f-234">Finanças</span><span class="sxs-lookup"><span data-stu-id="dd57f-234">Finance</span></span></td>
<td><span data-ttu-id="dd57f-235">6,000</span><span class="sxs-lookup"><span data-stu-id="dd57f-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-236">CC003</span><span class="sxs-lookup"><span data-stu-id="dd57f-236">CC003</span></span></td>
<td><span data-ttu-id="dd57f-237">Montagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-237">Assembly</span></span></td>
<td><span data-ttu-id="dd57f-238">0</span><span class="sxs-lookup"><span data-stu-id="dd57f-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dd57f-239">A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação para custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="dd57f-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dd57f-240">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-240">Cost object</span></span></th>
<th><span data-ttu-id="dd57f-241">Magnitude</span><span class="sxs-lookup"><span data-stu-id="dd57f-241">Magnitude</span></span></th>
<th><span data-ttu-id="dd57f-242">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="dd57f-242">Allocation factor</span></span></th>
<th><span data-ttu-id="dd57f-243">Valor</span><span class="sxs-lookup"><span data-stu-id="dd57f-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-244">CC001</span><span class="sxs-lookup"><span data-stu-id="dd57f-244">CC001</span></span></td>
<td><span data-ttu-id="dd57f-245">RH</span><span class="sxs-lookup"><span data-stu-id="dd57f-245">HR</span></span></td>
<td><span data-ttu-id="dd57f-246">1.000</span><span class="sxs-lookup"><span data-stu-id="dd57f-246">1,000</span></span></td>
<td><span data-ttu-id="dd57f-247">(1.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="dd57f-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="dd57f-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-249">CC002</span><span class="sxs-lookup"><span data-stu-id="dd57f-249">CC002</span></span></td>
<td><span data-ttu-id="dd57f-250">Finanças</span><span class="sxs-lookup"><span data-stu-id="dd57f-250">Finance</span></span></td>
<td><span data-ttu-id="dd57f-251">6,000</span><span class="sxs-lookup"><span data-stu-id="dd57f-251">6,000</span></span></td>
<td><span data-ttu-id="dd57f-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="dd57f-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="dd57f-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-254">CC003</span><span class="sxs-lookup"><span data-stu-id="dd57f-254">CC003</span></span></td>
<td><span data-ttu-id="dd57f-255">Montagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-255">Assembly</span></span></td>
<td><span data-ttu-id="dd57f-256">0</span><span class="sxs-lookup"><span data-stu-id="dd57f-256">0</span></span></td>
<td><span data-ttu-id="dd57f-257">(0 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="dd57f-258">0,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dd57f-259">Os custos fixos devem ser distribuídos igualmente a objetos de custo individuais que têm a eletricidade consumida.</span><span class="sxs-lookup"><span data-stu-id="dd57f-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="dd57f-260">Você pode obter esse resultado usando o membro estatístico de dimensão de eletricidade em uma base e alocação da fórmula: (Eletricidade &gt; 0,00) A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação de custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="dd57f-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dd57f-261">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-261">Cost object</span></span></th>
<th><span data-ttu-id="dd57f-262">Fórmula</span><span class="sxs-lookup"><span data-stu-id="dd57f-262">Formula</span></span></th>
<th><span data-ttu-id="dd57f-263">Magnitude</span><span class="sxs-lookup"><span data-stu-id="dd57f-263">Magnitude</span></span></th>
<th><span data-ttu-id="dd57f-264">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="dd57f-264">Allocation factor</span></span></th>
<th><span data-ttu-id="dd57f-265">Valor</span><span class="sxs-lookup"><span data-stu-id="dd57f-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-266">CC001</span><span class="sxs-lookup"><span data-stu-id="dd57f-266">CC001</span></span></td>
<td><span data-ttu-id="dd57f-267">RH</span><span class="sxs-lookup"><span data-stu-id="dd57f-267">HR</span></span></td>
<td><span data-ttu-id="dd57f-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="dd57f-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="dd57f-269">1</span><span class="sxs-lookup"><span data-stu-id="dd57f-269">1</span></span></td>
<td><span data-ttu-id="dd57f-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="dd57f-271">500,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-272">CC002</span><span class="sxs-lookup"><span data-stu-id="dd57f-272">CC002</span></span></td>
<td><span data-ttu-id="dd57f-273">Finanças</span><span class="sxs-lookup"><span data-stu-id="dd57f-273">Finance</span></span></td>
<td><span data-ttu-id="dd57f-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="dd57f-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="dd57f-275">1</span><span class="sxs-lookup"><span data-stu-id="dd57f-275">1</span></span></td>
<td><span data-ttu-id="dd57f-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="dd57f-277">500,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-278">CC003</span><span class="sxs-lookup"><span data-stu-id="dd57f-278">CC003</span></span></td>
<td><span data-ttu-id="dd57f-279">Montagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-279">Assembly</span></span></td>
<td><span data-ttu-id="dd57f-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="dd57f-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="dd57f-281">0</span><span class="sxs-lookup"><span data-stu-id="dd57f-281">0</span></span></td>
<td><span data-ttu-id="dd57f-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="dd57f-283">0,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="dd57f-284">Diário</span><span class="sxs-lookup"><span data-stu-id="dd57f-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dd57f-285">Diário</span><span class="sxs-lookup"><span data-stu-id="dd57f-285">Journal</span></span></th>
<th><span data-ttu-id="dd57f-286">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="dd57f-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="dd57f-287">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="dd57f-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="dd57f-288">Versão</span><span class="sxs-lookup"><span data-stu-id="dd57f-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-289">00002</span><span class="sxs-lookup"><span data-stu-id="dd57f-289">00002</span></span></td>
<td><span data-ttu-id="dd57f-290">Diário de cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="dd57f-291">fiscal</span><span class="sxs-lookup"><span data-stu-id="dd57f-291">Fiscal</span></span></td>
<td><span data-ttu-id="dd57f-292">2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-292">2017</span></span></td>
<td><span data-ttu-id="dd57f-293">Período 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-293">Period 1</span></span></td>
<td><span data-ttu-id="dd57f-294">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="dd57f-295">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="dd57f-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dd57f-296">Data contábil</span><span class="sxs-lookup"><span data-stu-id="dd57f-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="dd57f-297">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="dd57f-298">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-298">Cost element</span></span></th>
<th><span data-ttu-id="dd57f-299">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-299">Cost behavior</span></span></th>
<th><span data-ttu-id="dd57f-300">Valor</span><span class="sxs-lookup"><span data-stu-id="dd57f-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-301">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="dd57f-302">CC099</span><span class="sxs-lookup"><span data-stu-id="dd57f-302">CC099</span></span></td>
<td><span data-ttu-id="dd57f-303">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="dd57f-303">Default cost center</span></span></td>
<td><span data-ttu-id="dd57f-304">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-304">10001</span></span></td>
<td><span data-ttu-id="dd57f-305">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-305">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-306">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-306">Fixed cost</span></span></td>
<td><span data-ttu-id="dd57f-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-308">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="dd57f-309">CC099</span><span class="sxs-lookup"><span data-stu-id="dd57f-309">CC099</span></span></td>
<td><span data-ttu-id="dd57f-310">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="dd57f-310">Default cost center</span></span></td>
<td><span data-ttu-id="dd57f-311">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-311">10001</span></span></td>
<td><span data-ttu-id="dd57f-312">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-312">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-313">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-313">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="dd57f-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="dd57f-315">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dd57f-316">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="dd57f-317">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-317">Cost element</span></span></th>
<th><span data-ttu-id="dd57f-318">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-318">Cost behavior</span></span></th>
<th><span data-ttu-id="dd57f-319">Valor</span><span class="sxs-lookup"><span data-stu-id="dd57f-319">Amount</span></span></th>
<th><span data-ttu-id="dd57f-320">Data contábil</span><span class="sxs-lookup"><span data-stu-id="dd57f-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-321">CC099</span><span class="sxs-lookup"><span data-stu-id="dd57f-321">CC099</span></span></td>
<td><span data-ttu-id="dd57f-322">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="dd57f-322">Default cost center</span></span></td>
<td><span data-ttu-id="dd57f-323">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-323">10001</span></span></td>
<td><span data-ttu-id="dd57f-324">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-324">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-325">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-325">Fixed cost</span></span></td>
<td><span data-ttu-id="dd57f-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-326">-1,000.00</span></span></td>
<td><span data-ttu-id="dd57f-327">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-328">CC001</span><span class="sxs-lookup"><span data-stu-id="dd57f-328">CC001</span></span></td>
<td><span data-ttu-id="dd57f-329">RH</span><span class="sxs-lookup"><span data-stu-id="dd57f-329">HR</span></span></td>
<td><span data-ttu-id="dd57f-330">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-330">10001</span></span></td>
<td><span data-ttu-id="dd57f-331">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-331">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-332">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-332">Fixed cost</span></span></td>
<td><span data-ttu-id="dd57f-333">500,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-333">500.00</span></span></td>
<td><span data-ttu-id="dd57f-334">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-335">CC002</span><span class="sxs-lookup"><span data-stu-id="dd57f-335">CC002</span></span></td>
<td><span data-ttu-id="dd57f-336">Finanças</span><span class="sxs-lookup"><span data-stu-id="dd57f-336">Finance</span></span></td>
<td><span data-ttu-id="dd57f-337">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-337">10001</span></span></td>
<td><span data-ttu-id="dd57f-338">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-338">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-339">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-339">Fixed cost</span></span></td>
<td><span data-ttu-id="dd57f-340">500,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-340">500.00</span></span></td>
<td><span data-ttu-id="dd57f-341">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-342">CC099</span><span class="sxs-lookup"><span data-stu-id="dd57f-342">CC099</span></span></td>
<td><span data-ttu-id="dd57f-343">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="dd57f-343">Default cost center</span></span></td>
<td><span data-ttu-id="dd57f-344">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-344">10001</span></span></td>
<td><span data-ttu-id="dd57f-345">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-345">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-346">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-346">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-347">-9,000.00</span></span></td>
<td><span data-ttu-id="dd57f-348">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-349">CC001</span><span class="sxs-lookup"><span data-stu-id="dd57f-349">CC001</span></span></td>
<td><span data-ttu-id="dd57f-350">RH</span><span class="sxs-lookup"><span data-stu-id="dd57f-350">HR</span></span></td>
<td><span data-ttu-id="dd57f-351">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-351">10001</span></span></td>
<td><span data-ttu-id="dd57f-352">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-352">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-353">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-353">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="dd57f-354">1,285.71</span></span></td>
<td><span data-ttu-id="dd57f-355">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-356">CC002</span><span class="sxs-lookup"><span data-stu-id="dd57f-356">CC002</span></span></td>
<td><span data-ttu-id="dd57f-357">Finanças</span><span class="sxs-lookup"><span data-stu-id="dd57f-357">Finance</span></span></td>
<td><span data-ttu-id="dd57f-358">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-358">10001</span></span></td>
<td><span data-ttu-id="dd57f-359">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-359">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-360">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-360">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="dd57f-361">7,714.29</span></span></td>
<td><span data-ttu-id="dd57f-362">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dd57f-363">Para obter mais informações, consulte [Criar e atribuir uma política de distribuição de custos a uma unidade de controle de custos](tasks/create-assign-cost-distribution-policy-cost-control-unit.md)</span><span class="sxs-lookup"><span data-stu-id="dd57f-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="dd57f-364">Etapa 3: Processar o cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="dd57f-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="dd57f-365">A taxa de custos indiretos é usada para cobrar um ou mais objetos de custos específicos.</span><span class="sxs-lookup"><span data-stu-id="dd57f-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="dd57f-366">O encargo se baseia em uma taxa de custo predeterminada e a magnitude da básica de alocação atribuída.</span><span class="sxs-lookup"><span data-stu-id="dd57f-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="dd57f-367">Defina a taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="dd57f-367">Define the overhead rate</span></span>

<span data-ttu-id="dd57f-368">O objeto de custo CC001 HR contribui para um conjunto de projetos internos.</span><span class="sxs-lookup"><span data-stu-id="dd57f-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="dd57f-369">Um membro de dimensão estatística que é chamado de projetos de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="dd57f-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dd57f-370">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-370">Cost object</span></span></th>
<th><span data-ttu-id="dd57f-371">Horas</span><span class="sxs-lookup"><span data-stu-id="dd57f-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-372">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-372">Proj 1</span></span></td>
<td><span data-ttu-id="dd57f-373">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-373">Project 1</span></span></td>
<td><span data-ttu-id="dd57f-374">3</span><span class="sxs-lookup"><span data-stu-id="dd57f-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-375">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-375">Proj 2</span></span></td>
<td><span data-ttu-id="dd57f-376">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-376">Project 2</span></span></td>
<td><span data-ttu-id="dd57f-377">1</span><span class="sxs-lookup"><span data-stu-id="dd57f-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dd57f-378">Uma taxa de custo predeterminada da contribuição de projetos de custo foi definida.</span><span class="sxs-lookup"><span data-stu-id="dd57f-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dd57f-379">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-379">Cost object</span></span></th>
<th><span data-ttu-id="dd57f-380">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-380">Cost element</span></span></th>
<th><span data-ttu-id="dd57f-381">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-381">Cost behavior</span></span></th>
<th><span data-ttu-id="dd57f-382">Unidades</span><span class="sxs-lookup"><span data-stu-id="dd57f-382">Units</span></span></th>
<th><span data-ttu-id="dd57f-383">Taxa</span><span class="sxs-lookup"><span data-stu-id="dd57f-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-384">CC001</span><span class="sxs-lookup"><span data-stu-id="dd57f-384">CC001</span></span></td>
<td><span data-ttu-id="dd57f-385">RH</span><span class="sxs-lookup"><span data-stu-id="dd57f-385">HR</span></span></td>
<td><span data-ttu-id="dd57f-386">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-386">10001</span></span></td>
<td><span data-ttu-id="dd57f-387">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-387">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-388">1</span><span class="sxs-lookup"><span data-stu-id="dd57f-388">1</span></span></td>
<td><span data-ttu-id="dd57f-389">10</span><span class="sxs-lookup"><span data-stu-id="dd57f-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dd57f-390">A tabela a seguir mostra o resultado quando projetos de RH são aplicados como base de alocação.</span><span class="sxs-lookup"><span data-stu-id="dd57f-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dd57f-391">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-391">Cost object</span></span></th>
<th><span data-ttu-id="dd57f-392">Magnitude</span><span class="sxs-lookup"><span data-stu-id="dd57f-392">Magnitude</span></span></th>
<th><span data-ttu-id="dd57f-393">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-393">Cost element</span></span></th>
<th><span data-ttu-id="dd57f-394">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="dd57f-394">Allocation factor</span></span></th>
<th><span data-ttu-id="dd57f-395">Valor</span><span class="sxs-lookup"><span data-stu-id="dd57f-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-396">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-396">Proj 1</span></span></td>
<td><span data-ttu-id="dd57f-397">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-397">Project 1</span></span></td>
<td><span data-ttu-id="dd57f-398">3</span><span class="sxs-lookup"><span data-stu-id="dd57f-398">3</span></span></td>
<td><span data-ttu-id="dd57f-399">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-399">10001</span></span></td>
<td><span data-ttu-id="dd57f-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="dd57f-401">30,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-402">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-402">Proj 2</span></span></td>
<td><span data-ttu-id="dd57f-403">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-403">Project 2</span></span></td>
<td><span data-ttu-id="dd57f-404">1</span><span class="sxs-lookup"><span data-stu-id="dd57f-404">1</span></span></td>
<td><span data-ttu-id="dd57f-405">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-405">10001</span></span></td>
<td><span data-ttu-id="dd57f-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="dd57f-407">10,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="dd57f-408">Diário</span><span class="sxs-lookup"><span data-stu-id="dd57f-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dd57f-409">Diário</span><span class="sxs-lookup"><span data-stu-id="dd57f-409">Journal</span></span></th>
<th><span data-ttu-id="dd57f-410">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="dd57f-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="dd57f-411">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="dd57f-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="dd57f-412">Versão</span><span class="sxs-lookup"><span data-stu-id="dd57f-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-413">00003</span><span class="sxs-lookup"><span data-stu-id="dd57f-413">00003</span></span></td>
<td><span data-ttu-id="dd57f-414">Diário de cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="dd57f-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="dd57f-415">fiscal</span><span class="sxs-lookup"><span data-stu-id="dd57f-415">Fiscal</span></span></td>
<td><span data-ttu-id="dd57f-416">2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-416">2017</span></span></td>
<td><span data-ttu-id="dd57f-417">Período 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-417">Period 1</span></span></td>
<td><span data-ttu-id="dd57f-418">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="dd57f-419">Entradas de diário (As entradas de diário para cálculo da taxa de custos indiretos)</span><span class="sxs-lookup"><span data-stu-id="dd57f-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dd57f-420">Data contábil</span><span class="sxs-lookup"><span data-stu-id="dd57f-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="dd57f-421">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-421">Cost object</span></span></th>
<th><span data-ttu-id="dd57f-422">Magnitude</span><span class="sxs-lookup"><span data-stu-id="dd57f-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-423">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="dd57f-424">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-424">Proj 1</span></span></td>
<td><span data-ttu-id="dd57f-425">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="dd57f-426">3,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-427">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="dd57f-428">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-428">Proj 2</span></span></td>
<td><span data-ttu-id="dd57f-429">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="dd57f-430">1.00</span><span class="sxs-lookup"><span data-stu-id="dd57f-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="dd57f-431">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dd57f-432">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="dd57f-433">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-433">Cost element</span></span></th>
<th><span data-ttu-id="dd57f-434">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-434">Cost behavior</span></span></th>
<th><span data-ttu-id="dd57f-435">Valor</span><span class="sxs-lookup"><span data-stu-id="dd57f-435">Amount</span></span></th>
<th><span data-ttu-id="dd57f-436">Data contábil</span><span class="sxs-lookup"><span data-stu-id="dd57f-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="dd57f-437">CC0001</span></span></td>
<td><span data-ttu-id="dd57f-438">RH</span><span class="sxs-lookup"><span data-stu-id="dd57f-438">HR</span></span></td>
<td><span data-ttu-id="dd57f-439">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-439">10001</span></span></td>
<td><span data-ttu-id="dd57f-440">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-440">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-441">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-441">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-442">-30.00</span></span></td>
<td><span data-ttu-id="dd57f-443">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-444">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-444">Proj 1</span></span></td>
<td><span data-ttu-id="dd57f-445">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="dd57f-446">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-446">10001</span></span></td>
<td><span data-ttu-id="dd57f-447">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-447">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-448">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-448">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-449">30,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-449">30.00</span></span></td>
<td><span data-ttu-id="dd57f-450">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-451">CC001</span><span class="sxs-lookup"><span data-stu-id="dd57f-451">CC001</span></span></td>
<td><span data-ttu-id="dd57f-452">RH</span><span class="sxs-lookup"><span data-stu-id="dd57f-452">HR</span></span></td>
<td><span data-ttu-id="dd57f-453">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-453">10001</span></span></td>
<td><span data-ttu-id="dd57f-454">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-454">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-455">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-455">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-456">-10.00</span></span></td>
<td><span data-ttu-id="dd57f-457">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-458">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-458">Proj 2</span></span></td>
<td><span data-ttu-id="dd57f-459">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="dd57f-460">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-460">10001</span></span></td>
<td><span data-ttu-id="dd57f-461">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-461">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-462">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-462">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-463">10,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-463">10.00</span></span></td>
<td><span data-ttu-id="dd57f-464">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dd57f-465">Para obter mais informações, consulte [Realizar cálculo de custos indiretos](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="dd57f-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="dd57f-466">Etapa 4: Processar o cálculo de alocação de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="dd57f-467">A alocação é usada para alocar o saldo de um objeto de custo a outros objetos de custo pela aplicação de uma base de alocação.</span><span class="sxs-lookup"><span data-stu-id="dd57f-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="dd57f-468">O Finance oferece suporte ao método de alocação recíproco.</span><span class="sxs-lookup"><span data-stu-id="dd57f-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="dd57f-469">No método de alocação recíproco, os serviços mútuos que os objetos de custo auxiliar trocam são totalmente reconhecidos.</span><span class="sxs-lookup"><span data-stu-id="dd57f-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="dd57f-470">O sistema determina automaticamente a ordem correta realizar as alocações.</span><span class="sxs-lookup"><span data-stu-id="dd57f-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="dd57f-471">O saldo de um objeto de custo é alocado por uma base de alocação única.</span><span class="sxs-lookup"><span data-stu-id="dd57f-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="dd57f-472">As alocações entre as dimensões de objetos de custo e os respectivos membros são suportadas.</span><span class="sxs-lookup"><span data-stu-id="dd57f-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="dd57f-473">A ordem de alocação é controlada pela unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="dd57f-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="dd57f-474">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="dd57f-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="dd57f-475">Defina a alocação de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-475">Define the cost allocation</span></span>

<span data-ttu-id="dd57f-476">Aqui está um exemplo simples que explica como você pode rastrear o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="dd57f-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="dd57f-477">O objeto de custo previsto CC001 HR contribui a vários objetos de custo previsto.</span><span class="sxs-lookup"><span data-stu-id="dd57f-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="dd57f-478">Um membro de dimensão estatística que é chamado de serviços de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="dd57f-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dd57f-479">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-479">Cost object</span></span></th>
<th><span data-ttu-id="dd57f-480">Serviços de RH</span><span class="sxs-lookup"><span data-stu-id="dd57f-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-481">CC002</span><span class="sxs-lookup"><span data-stu-id="dd57f-481">CC002</span></span></td>
<td><span data-ttu-id="dd57f-482">Finanças</span><span class="sxs-lookup"><span data-stu-id="dd57f-482">Finance</span></span></td>
<td><span data-ttu-id="dd57f-483">35</span><span class="sxs-lookup"><span data-stu-id="dd57f-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-484">CC003</span><span class="sxs-lookup"><span data-stu-id="dd57f-484">CC003</span></span></td>
<td><span data-ttu-id="dd57f-485">Montagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-485">Assembly</span></span></td>
<td><span data-ttu-id="dd57f-486">55</span><span class="sxs-lookup"><span data-stu-id="dd57f-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-487">CC004</span><span class="sxs-lookup"><span data-stu-id="dd57f-487">CC004</span></span></td>
<td><span data-ttu-id="dd57f-488">Embalagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-488">Packaging</span></span></td>
<td><span data-ttu-id="dd57f-489">10</span><span class="sxs-lookup"><span data-stu-id="dd57f-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dd57f-490">O objeto de custo CC002 Finanças contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="dd57f-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="dd57f-491">Um membro de dimensão estatística que é chamado de serviços de Finanças foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="dd57f-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dd57f-492">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-492">Cost object</span></span></th>
<th><span data-ttu-id="dd57f-493">Serviços financeiros</span><span class="sxs-lookup"><span data-stu-id="dd57f-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-494">CC003</span><span class="sxs-lookup"><span data-stu-id="dd57f-494">CC003</span></span></td>
<td><span data-ttu-id="dd57f-495">Montagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-495">Assembly</span></span></td>
<td><span data-ttu-id="dd57f-496">65</span><span class="sxs-lookup"><span data-stu-id="dd57f-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-497">CC004</span><span class="sxs-lookup"><span data-stu-id="dd57f-497">CC004</span></span></td>
<td><span data-ttu-id="dd57f-498">Embalagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-498">Packaging</span></span></td>
<td><span data-ttu-id="dd57f-499">35</span><span class="sxs-lookup"><span data-stu-id="dd57f-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dd57f-500">O objeto de custo CC003 Montagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="dd57f-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="dd57f-501">Um membro de dimensão estatística que é chamado de serviços de Montagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="dd57f-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dd57f-502">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-502">Cost object</span></span></th>
<th><span data-ttu-id="dd57f-503">Serviços de montagem (horas)</span><span class="sxs-lookup"><span data-stu-id="dd57f-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-504">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-504">Prod 1</span></span></td>
<td><span data-ttu-id="dd57f-505">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-505">Product 1</span></span></td>
<td><span data-ttu-id="dd57f-506">60</span><span class="sxs-lookup"><span data-stu-id="dd57f-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-507">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-507">Prod 2</span></span></td>
<td><span data-ttu-id="dd57f-508">Produto 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-508">Product 2</span></span></td>
<td><span data-ttu-id="dd57f-509">20</span><span class="sxs-lookup"><span data-stu-id="dd57f-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dd57f-510">O objeto de custo CC004 Embalagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="dd57f-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="dd57f-511">Um membro de dimensão estatística que é chamado de serviços de Embalagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="dd57f-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dd57f-512">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-512">Cost object</span></span></th>
<th><span data-ttu-id="dd57f-513">Serviços de embalagem (horas)</span><span class="sxs-lookup"><span data-stu-id="dd57f-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-514">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-514">Prod 1</span></span></td>
<td><span data-ttu-id="dd57f-515">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-515">Product 1</span></span></td>
<td><span data-ttu-id="dd57f-516">80</span><span class="sxs-lookup"><span data-stu-id="dd57f-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-517">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-517">Prod 2</span></span></td>
<td><span data-ttu-id="dd57f-518">Produto 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-518">Product 2</span></span></td>
<td><span data-ttu-id="dd57f-519">15</span><span class="sxs-lookup"><span data-stu-id="dd57f-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="dd57f-520">Medidas estatísticas, como as horas de produção que um produto consome, podem ser derivadas dos dados de origem.</span><span class="sxs-lookup"><span data-stu-id="dd57f-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="dd57f-521">Para obter mais informações, consulte [Modelo de provedor de medidas estatísticas](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="dd57f-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="dd57f-522">A tabela a seguir mostra o resultado quando os serviços de RH são aplicados como base de alocação para custos totais (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="dd57f-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dd57f-523">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-523">Cost object</span></span></th>
<th><span data-ttu-id="dd57f-524">Magnitude</span><span class="sxs-lookup"><span data-stu-id="dd57f-524">Magnitude</span></span></th>
<th><span data-ttu-id="dd57f-525">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="dd57f-525">Allocation factor</span></span></th>
<th><span data-ttu-id="dd57f-526">Valor</span><span class="sxs-lookup"><span data-stu-id="dd57f-526">Amount</span></span></th>
<th><span data-ttu-id="dd57f-527">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-528">CC002</span><span class="sxs-lookup"><span data-stu-id="dd57f-528">CC002</span></span></td>
<td><span data-ttu-id="dd57f-529">Finanças</span><span class="sxs-lookup"><span data-stu-id="dd57f-529">Finance</span></span></td>
<td><span data-ttu-id="dd57f-530">35</span><span class="sxs-lookup"><span data-stu-id="dd57f-530">35</span></span></td>
<td><span data-ttu-id="dd57f-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="dd57f-532">175.00</span><span class="sxs-lookup"><span data-stu-id="dd57f-532">175.00</span></span></td>
<td><span data-ttu-id="dd57f-533">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-534">CC003</span><span class="sxs-lookup"><span data-stu-id="dd57f-534">CC003</span></span></td>
<td><span data-ttu-id="dd57f-535">Montagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-535">Assembly</span></span></td>
<td><span data-ttu-id="dd57f-536">55</span><span class="sxs-lookup"><span data-stu-id="dd57f-536">55</span></span></td>
<td><span data-ttu-id="dd57f-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="dd57f-538">275.00</span><span class="sxs-lookup"><span data-stu-id="dd57f-538">275.00</span></span></td>
<td><span data-ttu-id="dd57f-539">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-540">CC004</span><span class="sxs-lookup"><span data-stu-id="dd57f-540">CC004</span></span></td>
<td><span data-ttu-id="dd57f-541">Embalagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-541">Packaging</span></span></td>
<td><span data-ttu-id="dd57f-542">10</span><span class="sxs-lookup"><span data-stu-id="dd57f-542">10</span></span></td>
<td><span data-ttu-id="dd57f-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="dd57f-544">50,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-544">50.00</span></span></td>
<td><span data-ttu-id="dd57f-545">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-546">CC002</span><span class="sxs-lookup"><span data-stu-id="dd57f-546">CC002</span></span></td>
<td><span data-ttu-id="dd57f-547">Finanças</span><span class="sxs-lookup"><span data-stu-id="dd57f-547">Finance</span></span></td>
<td><span data-ttu-id="dd57f-548">35</span><span class="sxs-lookup"><span data-stu-id="dd57f-548">35</span></span></td>
<td><span data-ttu-id="dd57f-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="dd57f-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="dd57f-550">436.00</span><span class="sxs-lookup"><span data-stu-id="dd57f-550">436.00</span></span></td>
<td><span data-ttu-id="dd57f-551">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-552">CC003</span><span class="sxs-lookup"><span data-stu-id="dd57f-552">CC003</span></span></td>
<td><span data-ttu-id="dd57f-553">Montagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-553">Assembly</span></span></td>
<td><span data-ttu-id="dd57f-554">55</span><span class="sxs-lookup"><span data-stu-id="dd57f-554">55</span></span></td>
<td><span data-ttu-id="dd57f-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="dd57f-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="dd57f-556">685.14</span><span class="sxs-lookup"><span data-stu-id="dd57f-556">685.14</span></span></td>
<td><span data-ttu-id="dd57f-557">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-558">CC004</span><span class="sxs-lookup"><span data-stu-id="dd57f-558">CC004</span></span></td>
<td><span data-ttu-id="dd57f-559">Embalagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-559">Packaging</span></span></td>
<td><span data-ttu-id="dd57f-560">10</span><span class="sxs-lookup"><span data-stu-id="dd57f-560">10</span></span></td>
<td><span data-ttu-id="dd57f-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="dd57f-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="dd57f-562">124.57</span><span class="sxs-lookup"><span data-stu-id="dd57f-562">124.57</span></span></td>
<td><span data-ttu-id="dd57f-563">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dd57f-564">A tabela a seguir mostra o resultado quando os serviços financeiros são aplicados como base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="dd57f-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dd57f-565">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-565">Cost object</span></span></th>
<th><span data-ttu-id="dd57f-566">Magnitude</span><span class="sxs-lookup"><span data-stu-id="dd57f-566">Magnitude</span></span></th>
<th><span data-ttu-id="dd57f-567">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="dd57f-567">Allocation factor</span></span></th>
<th><span data-ttu-id="dd57f-568">Valor</span><span class="sxs-lookup"><span data-stu-id="dd57f-568">Amount</span></span></th>
<th><span data-ttu-id="dd57f-569">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-570">CC003</span><span class="sxs-lookup"><span data-stu-id="dd57f-570">CC003</span></span></td>
<td><span data-ttu-id="dd57f-571">Montagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-571">Assembly</span></span></td>
<td><span data-ttu-id="dd57f-572">65</span><span class="sxs-lookup"><span data-stu-id="dd57f-572">65</span></span></td>
<td><span data-ttu-id="dd57f-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="dd57f-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="dd57f-574">438.75</span><span class="sxs-lookup"><span data-stu-id="dd57f-574">438.75</span></span></td>
<td><span data-ttu-id="dd57f-575">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-576">CC004</span><span class="sxs-lookup"><span data-stu-id="dd57f-576">CC004</span></span></td>
<td><span data-ttu-id="dd57f-577">Embalagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-577">Packaging</span></span></td>
<td><span data-ttu-id="dd57f-578">35</span><span class="sxs-lookup"><span data-stu-id="dd57f-578">35</span></span></td>
<td><span data-ttu-id="dd57f-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="dd57f-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="dd57f-580">236.25</span><span class="sxs-lookup"><span data-stu-id="dd57f-580">236.25</span></span></td>
<td><span data-ttu-id="dd57f-581">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-582">CC003</span><span class="sxs-lookup"><span data-stu-id="dd57f-582">CC003</span></span></td>
<td><span data-ttu-id="dd57f-583">Montagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-583">Assembly</span></span></td>
<td><span data-ttu-id="dd57f-584">65</span><span class="sxs-lookup"><span data-stu-id="dd57f-584">65</span></span></td>
<td><span data-ttu-id="dd57f-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="dd57f-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="dd57f-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="dd57f-586">5,297.69</span></span></td>
<td><span data-ttu-id="dd57f-587">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-588">CC004</span><span class="sxs-lookup"><span data-stu-id="dd57f-588">CC004</span></span></td>
<td><span data-ttu-id="dd57f-589">Embalagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-589">Packaging</span></span></td>
<td><span data-ttu-id="dd57f-590">35</span><span class="sxs-lookup"><span data-stu-id="dd57f-590">35</span></span></td>
<td><span data-ttu-id="dd57f-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="dd57f-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="dd57f-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="dd57f-592">2,852.60</span></span></td>
<td><span data-ttu-id="dd57f-593">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dd57f-594">A tabela a seguir mostra o resultado quando os serviços de Montagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="dd57f-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dd57f-595">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-595">Cost object</span></span></th>
<th><span data-ttu-id="dd57f-596">Magnitude</span><span class="sxs-lookup"><span data-stu-id="dd57f-596">Magnitude</span></span></th>
<th><span data-ttu-id="dd57f-597">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="dd57f-597">Allocation factor</span></span></th>
<th><span data-ttu-id="dd57f-598">Valor</span><span class="sxs-lookup"><span data-stu-id="dd57f-598">Amount</span></span></th>
<th><span data-ttu-id="dd57f-599">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-600">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-600">Prod 1</span></span></td>
<td><span data-ttu-id="dd57f-601">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-601">Product 1</span></span></td>
<td><span data-ttu-id="dd57f-602">60</span><span class="sxs-lookup"><span data-stu-id="dd57f-602">60</span></span></td>
<td><span data-ttu-id="dd57f-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="dd57f-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="dd57f-604">535.31</span><span class="sxs-lookup"><span data-stu-id="dd57f-604">535.31</span></span></td>
<td><span data-ttu-id="dd57f-605">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-606">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-606">Prod 2</span></span></td>
<td><span data-ttu-id="dd57f-607">Produto 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-607">Product 2</span></span></td>
<td><span data-ttu-id="dd57f-608">20</span><span class="sxs-lookup"><span data-stu-id="dd57f-608">20</span></span></td>
<td><span data-ttu-id="dd57f-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="dd57f-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="dd57f-610">178.44</span><span class="sxs-lookup"><span data-stu-id="dd57f-610">178.44</span></span></td>
<td><span data-ttu-id="dd57f-611">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-612">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-612">Prod 1</span></span></td>
<td><span data-ttu-id="dd57f-613">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-613">Product 1</span></span></td>
<td><span data-ttu-id="dd57f-614">60</span><span class="sxs-lookup"><span data-stu-id="dd57f-614">60</span></span></td>
<td><span data-ttu-id="dd57f-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="dd57f-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="dd57f-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="dd57f-616">4,487.12</span></span></td>
<td><span data-ttu-id="dd57f-617">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-618">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-618">Prod 2</span></span></td>
<td><span data-ttu-id="dd57f-619">Produto 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-619">Product 2</span></span></td>
<td><span data-ttu-id="dd57f-620">20</span><span class="sxs-lookup"><span data-stu-id="dd57f-620">20</span></span></td>
<td><span data-ttu-id="dd57f-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="dd57f-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="dd57f-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="dd57f-622">1,495.71</span></span></td>
<td><span data-ttu-id="dd57f-623">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dd57f-624">A tabela a seguir mostra o resultado quando os serviços de Embalagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="dd57f-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dd57f-625">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-625">Cost object</span></span></th>
<th><span data-ttu-id="dd57f-626">Magnitude</span><span class="sxs-lookup"><span data-stu-id="dd57f-626">Magnitude</span></span></th>
<th><span data-ttu-id="dd57f-627">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="dd57f-627">Allocation factor</span></span></th>
<th><span data-ttu-id="dd57f-628">Valor</span><span class="sxs-lookup"><span data-stu-id="dd57f-628">Amount</span></span></th>
<th><span data-ttu-id="dd57f-629">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-630">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-630">Prod 1</span></span></td>
<td><span data-ttu-id="dd57f-631">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-631">Product 1</span></span></td>
<td><span data-ttu-id="dd57f-632">80</span><span class="sxs-lookup"><span data-stu-id="dd57f-632">80</span></span></td>
<td><span data-ttu-id="dd57f-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="dd57f-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="dd57f-634">241.05</span><span class="sxs-lookup"><span data-stu-id="dd57f-634">241.05</span></span></td>
<td><span data-ttu-id="dd57f-635">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-636">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-636">Prod 2</span></span></td>
<td><span data-ttu-id="dd57f-637">Produto 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-637">Product 2</span></span></td>
<td><span data-ttu-id="dd57f-638">15</span><span class="sxs-lookup"><span data-stu-id="dd57f-638">15</span></span></td>
<td><span data-ttu-id="dd57f-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="dd57f-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="dd57f-640">45.20</span><span class="sxs-lookup"><span data-stu-id="dd57f-640">45.20</span></span></td>
<td><span data-ttu-id="dd57f-641">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-642">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-642">Prod 1</span></span></td>
<td><span data-ttu-id="dd57f-643">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-643">Product 1</span></span></td>
<td><span data-ttu-id="dd57f-644">80</span><span class="sxs-lookup"><span data-stu-id="dd57f-644">80</span></span></td>
<td><span data-ttu-id="dd57f-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="dd57f-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="dd57f-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="dd57f-646">2,507.09</span></span></td>
<td><span data-ttu-id="dd57f-647">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-648">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-648">Prod 2</span></span></td>
<td><span data-ttu-id="dd57f-649">Produto 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-649">Product 2</span></span></td>
<td><span data-ttu-id="dd57f-650">15</span><span class="sxs-lookup"><span data-stu-id="dd57f-650">15</span></span></td>
<td><span data-ttu-id="dd57f-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="dd57f-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="dd57f-652">470.08</span><span class="sxs-lookup"><span data-stu-id="dd57f-652">470.08</span></span></td>
<td><span data-ttu-id="dd57f-653">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="dd57f-654">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="dd57f-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dd57f-655">Diário</span><span class="sxs-lookup"><span data-stu-id="dd57f-655">Journal</span></span></th>
<th><span data-ttu-id="dd57f-656">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="dd57f-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="dd57f-657">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="dd57f-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="dd57f-658">Versão</span><span class="sxs-lookup"><span data-stu-id="dd57f-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-659">00004</span><span class="sxs-lookup"><span data-stu-id="dd57f-659">00004</span></span></td>
<td><span data-ttu-id="dd57f-660">Diário de alocação de custos</span><span class="sxs-lookup"><span data-stu-id="dd57f-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="dd57f-661">fiscal</span><span class="sxs-lookup"><span data-stu-id="dd57f-661">Fiscal</span></span></td>
<td><span data-ttu-id="dd57f-662">2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-662">2017</span></span></td>
<td><span data-ttu-id="dd57f-663">Período 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-663">Period 1</span></span></td>
<td><span data-ttu-id="dd57f-664">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="dd57f-665">Linhas do diário</span><span class="sxs-lookup"><span data-stu-id="dd57f-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dd57f-666">Data contábil</span><span class="sxs-lookup"><span data-stu-id="dd57f-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="dd57f-667">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="dd57f-668">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-668">Cost element</span></span></th>
<th><span data-ttu-id="dd57f-669">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-669">Cost behavior</span></span></th>
<th><span data-ttu-id="dd57f-670">Valor</span><span class="sxs-lookup"><span data-stu-id="dd57f-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-671">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="dd57f-672">CC001</span><span class="sxs-lookup"><span data-stu-id="dd57f-672">CC001</span></span></td>
<td><span data-ttu-id="dd57f-673">RH</span><span class="sxs-lookup"><span data-stu-id="dd57f-673">HR</span></span></td>
<td><span data-ttu-id="dd57f-674">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-674">10001</span></span></td>
<td><span data-ttu-id="dd57f-675">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-675">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-676">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-676">Fixed cost</span></span></td>
<td><span data-ttu-id="dd57f-677">500,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-678">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="dd57f-679">CC001</span><span class="sxs-lookup"><span data-stu-id="dd57f-679">CC001</span></span></td>
<td><span data-ttu-id="dd57f-680">RH</span><span class="sxs-lookup"><span data-stu-id="dd57f-680">HR</span></span></td>
<td><span data-ttu-id="dd57f-681">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-681">10001</span></span></td>
<td><span data-ttu-id="dd57f-682">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-682">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-683">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-683">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="dd57f-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-685">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="dd57f-686">CC002</span><span class="sxs-lookup"><span data-stu-id="dd57f-686">CC002</span></span></td>
<td><span data-ttu-id="dd57f-687">Finanças</span><span class="sxs-lookup"><span data-stu-id="dd57f-687">Finance</span></span></td>
<td><span data-ttu-id="dd57f-688">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-688">10001</span></span></td>
<td><span data-ttu-id="dd57f-689">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-689">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-690">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-690">Fixed cost</span></span></td>
<td><span data-ttu-id="dd57f-691">675.00</span><span class="sxs-lookup"><span data-stu-id="dd57f-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-692">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="dd57f-693">CC002</span><span class="sxs-lookup"><span data-stu-id="dd57f-693">CC002</span></span></td>
<td><span data-ttu-id="dd57f-694">Finanças</span><span class="sxs-lookup"><span data-stu-id="dd57f-694">Finance</span></span></td>
<td><span data-ttu-id="dd57f-695">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-695">10001</span></span></td>
<td><span data-ttu-id="dd57f-696">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-696">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-697">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-697">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="dd57f-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-699">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="dd57f-700">CC003</span><span class="sxs-lookup"><span data-stu-id="dd57f-700">CC003</span></span></td>
<td><span data-ttu-id="dd57f-701">Montagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-701">Assembly</span></span></td>
<td><span data-ttu-id="dd57f-702">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-702">10001</span></span></td>
<td><span data-ttu-id="dd57f-703">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-703">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-704">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-704">Fixed cost</span></span></td>
<td><span data-ttu-id="dd57f-705">713.75</span><span class="sxs-lookup"><span data-stu-id="dd57f-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-706">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="dd57f-707">CC003</span><span class="sxs-lookup"><span data-stu-id="dd57f-707">CC003</span></span></td>
<td><span data-ttu-id="dd57f-708">Montagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-708">Assembly</span></span></td>
<td><span data-ttu-id="dd57f-709">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-709">10001</span></span></td>
<td><span data-ttu-id="dd57f-710">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-710">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-711">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-711">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="dd57f-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-713">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="dd57f-714">CC003</span><span class="sxs-lookup"><span data-stu-id="dd57f-714">CC003</span></span></td>
<td><span data-ttu-id="dd57f-715">Embalagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-715">Packaging</span></span></td>
<td><span data-ttu-id="dd57f-716">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-716">10001</span></span></td>
<td><span data-ttu-id="dd57f-717">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-717">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-718">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-718">Fixed cost</span></span></td>
<td><span data-ttu-id="dd57f-719">286.25</span><span class="sxs-lookup"><span data-stu-id="dd57f-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-720">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="dd57f-721">CC003</span><span class="sxs-lookup"><span data-stu-id="dd57f-721">CC003</span></span></td>
<td><span data-ttu-id="dd57f-722">Embalagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-722">Packaging</span></span></td>
<td><span data-ttu-id="dd57f-723">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-723">10001</span></span></td>
<td><span data-ttu-id="dd57f-724">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-724">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-725">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-725">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="dd57f-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-727">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="dd57f-728">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-728">Prod 1</span></span></td>
<td><span data-ttu-id="dd57f-729">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-729">Product 1</span></span></td>
<td><span data-ttu-id="dd57f-730">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-730">10001</span></span></td>
<td><span data-ttu-id="dd57f-731">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-731">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-732">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-732">Fixed cost</span></span></td>
<td><span data-ttu-id="dd57f-733">776.36</span><span class="sxs-lookup"><span data-stu-id="dd57f-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-734">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="dd57f-735">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-735">Prod 1</span></span></td>
<td><span data-ttu-id="dd57f-736">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-736">Product 1</span></span></td>
<td><span data-ttu-id="dd57f-737">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-737">10001</span></span></td>
<td><span data-ttu-id="dd57f-738">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-738">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-739">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-739">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="dd57f-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-741">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="dd57f-742">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-742">Prod 2</span></span></td>
<td><span data-ttu-id="dd57f-743">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-743">Product 1</span></span></td>
<td><span data-ttu-id="dd57f-744">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-744">10001</span></span></td>
<td><span data-ttu-id="dd57f-745">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-745">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-746">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-746">Fixed cost</span></span></td>
<td><span data-ttu-id="dd57f-747">223.64</span><span class="sxs-lookup"><span data-stu-id="dd57f-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-748">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="dd57f-749">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-749">Prod 2</span></span></td>
<td><span data-ttu-id="dd57f-750">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-750">Product 1</span></span></td>
<td><span data-ttu-id="dd57f-751">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-751">10001</span></span></td>
<td><span data-ttu-id="dd57f-752">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-752">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-753">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-753">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="dd57f-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="dd57f-755">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dd57f-756">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="dd57f-757">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-757">Cost element</span></span></th>
<th><span data-ttu-id="dd57f-758">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-758">Cost behavior</span></span></th>
<th><span data-ttu-id="dd57f-759">Valor</span><span class="sxs-lookup"><span data-stu-id="dd57f-759">Amount</span></span></th>
<th><span data-ttu-id="dd57f-760">Data contábil</span><span class="sxs-lookup"><span data-stu-id="dd57f-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dd57f-761">CC001</span><span class="sxs-lookup"><span data-stu-id="dd57f-761">CC001</span></span></td>
<td><span data-ttu-id="dd57f-762">RH</span><span class="sxs-lookup"><span data-stu-id="dd57f-762">HR</span></span></td>
<td><span data-ttu-id="dd57f-763">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-763">10001</span></span></td>
<td><span data-ttu-id="dd57f-764">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-764">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-765">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-765">Fixed cost</span></span></td>
<td><span data-ttu-id="dd57f-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-766">-500.00</span></span></td>
<td><span data-ttu-id="dd57f-767">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-768">CC002</span><span class="sxs-lookup"><span data-stu-id="dd57f-768">CC002</span></span></td>
<td><span data-ttu-id="dd57f-769">Finanças</span><span class="sxs-lookup"><span data-stu-id="dd57f-769">Finance</span></span></td>
<td><span data-ttu-id="dd57f-770">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-770">10001</span></span></td>
<td><span data-ttu-id="dd57f-771">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-771">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-772">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-772">Fixed cost</span></span></td>
<td><span data-ttu-id="dd57f-773">175.00</span><span class="sxs-lookup"><span data-stu-id="dd57f-773">175.00</span></span></td>
<td><span data-ttu-id="dd57f-774">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-775">CC003</span><span class="sxs-lookup"><span data-stu-id="dd57f-775">CC003</span></span></td>
<td><span data-ttu-id="dd57f-776">Montagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-776">Assembly</span></span></td>
<td><span data-ttu-id="dd57f-777">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-777">10001</span></span></td>
<td><span data-ttu-id="dd57f-778">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-778">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-779">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-779">Fixed cost</span></span></td>
<td><span data-ttu-id="dd57f-780">275.00</span><span class="sxs-lookup"><span data-stu-id="dd57f-780">275.00</span></span></td>
<td><span data-ttu-id="dd57f-781">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-782">CC004</span><span class="sxs-lookup"><span data-stu-id="dd57f-782">CC004</span></span></td>
<td><span data-ttu-id="dd57f-783">Embalagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-783">Packaging</span></span></td>
<td><span data-ttu-id="dd57f-784">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-784">10001</span></span></td>
<td><span data-ttu-id="dd57f-785">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-785">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-786">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-786">Fixed cost</span></span></td>
<td><span data-ttu-id="dd57f-787">50,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-787">50,00</span></span></td>
<td><span data-ttu-id="dd57f-788">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-789">CC001</span><span class="sxs-lookup"><span data-stu-id="dd57f-789">CC001</span></span></td>
<td><span data-ttu-id="dd57f-790">RH</span><span class="sxs-lookup"><span data-stu-id="dd57f-790">HR</span></span></td>
<td><span data-ttu-id="dd57f-791">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-791">10001</span></span></td>
<td><span data-ttu-id="dd57f-792">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-792">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-793">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-793">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="dd57f-794">-1,245.71</span></span></td>
<td><span data-ttu-id="dd57f-795">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-796">CC002</span><span class="sxs-lookup"><span data-stu-id="dd57f-796">CC002</span></span></td>
<td><span data-ttu-id="dd57f-797">Finanças</span><span class="sxs-lookup"><span data-stu-id="dd57f-797">Finance</span></span></td>
<td><span data-ttu-id="dd57f-798">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-798">10001</span></span></td>
<td><span data-ttu-id="dd57f-799">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-799">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-800">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-800">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-801">436.00</span><span class="sxs-lookup"><span data-stu-id="dd57f-801">436.00</span></span></td>
<td><span data-ttu-id="dd57f-802">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-803">CC003</span><span class="sxs-lookup"><span data-stu-id="dd57f-803">CC003</span></span></td>
<td><span data-ttu-id="dd57f-804">Montagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-804">Assembly</span></span></td>
<td><span data-ttu-id="dd57f-805">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-805">10001</span></span></td>
<td><span data-ttu-id="dd57f-806">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-806">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-807">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-807">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-808">685.14</span><span class="sxs-lookup"><span data-stu-id="dd57f-808">685.14</span></span></td>
<td><span data-ttu-id="dd57f-809">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-810">CC004</span><span class="sxs-lookup"><span data-stu-id="dd57f-810">CC004</span></span></td>
<td><span data-ttu-id="dd57f-811">Embalagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-811">Packaging</span></span></td>
<td><span data-ttu-id="dd57f-812">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-812">10001</span></span></td>
<td><span data-ttu-id="dd57f-813">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-813">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-814">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-814">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-815">124.57</span><span class="sxs-lookup"><span data-stu-id="dd57f-815">124.57</span></span></td>
<td><span data-ttu-id="dd57f-816">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-817">CC002</span><span class="sxs-lookup"><span data-stu-id="dd57f-817">CC002</span></span></td>
<td><span data-ttu-id="dd57f-818">Finanças</span><span class="sxs-lookup"><span data-stu-id="dd57f-818">Finance</span></span></td>
<td><span data-ttu-id="dd57f-819">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-819">10001</span></span></td>
<td><span data-ttu-id="dd57f-820">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-820">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-821">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-821">Fixed cost</span></span></td>
<td><span data-ttu-id="dd57f-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-822">-675.00</span></span></td>
<td><span data-ttu-id="dd57f-823">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-824">CC003</span><span class="sxs-lookup"><span data-stu-id="dd57f-824">CC003</span></span></td>
<td><span data-ttu-id="dd57f-825">Montagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-825">Assembly</span></span></td>
<td><span data-ttu-id="dd57f-826">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-826">10001</span></span></td>
<td><span data-ttu-id="dd57f-827">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-827">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-828">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-828">Fixed cost</span></span></td>
<td><span data-ttu-id="dd57f-829">438.75</span><span class="sxs-lookup"><span data-stu-id="dd57f-829">438.75</span></span></td>
<td><span data-ttu-id="dd57f-830">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-831">CC004</span><span class="sxs-lookup"><span data-stu-id="dd57f-831">CC004</span></span></td>
<td><span data-ttu-id="dd57f-832">Embalagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-832">Packaging</span></span></td>
<td><span data-ttu-id="dd57f-833">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-833">10001</span></span></td>
<td><span data-ttu-id="dd57f-834">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-834">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-835">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-835">Fixed cost</span></span></td>
<td><span data-ttu-id="dd57f-836">236.25</span><span class="sxs-lookup"><span data-stu-id="dd57f-836">236.25</span></span></td>
<td><span data-ttu-id="dd57f-837">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-838">CC002</span><span class="sxs-lookup"><span data-stu-id="dd57f-838">CC002</span></span></td>
<td><span data-ttu-id="dd57f-839">Finanças</span><span class="sxs-lookup"><span data-stu-id="dd57f-839">Finance</span></span></td>
<td><span data-ttu-id="dd57f-840">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-840">10001</span></span></td>
<td><span data-ttu-id="dd57f-841">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-841">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-842">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-842">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="dd57f-843">-8,150.29</span></span></td>
<td><span data-ttu-id="dd57f-844">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-845">CC003</span><span class="sxs-lookup"><span data-stu-id="dd57f-845">CC003</span></span></td>
<td><span data-ttu-id="dd57f-846">Montagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-846">Assembly</span></span></td>
<td><span data-ttu-id="dd57f-847">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-847">10001</span></span></td>
<td><span data-ttu-id="dd57f-848">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-848">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-849">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-849">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="dd57f-850">5,297.69</span></span></td>
<td><span data-ttu-id="dd57f-851">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-852">CC004</span><span class="sxs-lookup"><span data-stu-id="dd57f-852">CC004</span></span></td>
<td><span data-ttu-id="dd57f-853">Embalagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-853">Packaging</span></span></td>
<td><span data-ttu-id="dd57f-854">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-854">10001</span></span></td>
<td><span data-ttu-id="dd57f-855">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-855">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-856">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-856">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="dd57f-857">2,852.60</span></span></td>
<td><span data-ttu-id="dd57f-858">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-859">CC003</span><span class="sxs-lookup"><span data-stu-id="dd57f-859">CC003</span></span></td>
<td><span data-ttu-id="dd57f-860">Montagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-860">Assembly</span></span></td>
<td><span data-ttu-id="dd57f-861">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-861">10001</span></span></td>
<td><span data-ttu-id="dd57f-862">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-862">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-863">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-863">Fixed cost</span></span></td>
<td><span data-ttu-id="dd57f-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="dd57f-864">-713.75</span></span></td>
<td><span data-ttu-id="dd57f-865">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-866">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-866">Prod 1</span></span></td>
<td><span data-ttu-id="dd57f-867">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-867">Product 1</span></span></td>
<td><span data-ttu-id="dd57f-868">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-868">10001</span></span></td>
<td><span data-ttu-id="dd57f-869">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-869">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-870">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-870">Fixed cost</span></span></td>
<td><span data-ttu-id="dd57f-871">535.31</span><span class="sxs-lookup"><span data-stu-id="dd57f-871">535.31</span></span></td>
<td><span data-ttu-id="dd57f-872">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-873">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-873">Prod 2</span></span></td>
<td><span data-ttu-id="dd57f-874">Produto 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-874">Product 2</span></span></td>
<td><span data-ttu-id="dd57f-875">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-875">10001</span></span></td>
<td><span data-ttu-id="dd57f-876">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-876">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-877">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-877">Fixed cost</span></span></td>
<td><span data-ttu-id="dd57f-878">178.44</span><span class="sxs-lookup"><span data-stu-id="dd57f-878">178.44</span></span></td>
<td><span data-ttu-id="dd57f-879">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-880">CC003</span><span class="sxs-lookup"><span data-stu-id="dd57f-880">CC003</span></span></td>
<td><span data-ttu-id="dd57f-881">Montagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-881">Assembly</span></span></td>
<td><span data-ttu-id="dd57f-882">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-882">10001</span></span></td>
<td><span data-ttu-id="dd57f-883">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-883">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-884">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-884">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="dd57f-885">-5,982.83</span></span></td>
<td><span data-ttu-id="dd57f-886">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-887">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-887">Prod 1</span></span></td>
<td><span data-ttu-id="dd57f-888">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-888">Product 1</span></span></td>
<td><span data-ttu-id="dd57f-889">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-889">10001</span></span></td>
<td><span data-ttu-id="dd57f-890">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-890">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-891">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-891">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="dd57f-892">4,487.12</span></span></td>
<td><span data-ttu-id="dd57f-893">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-894">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-894">Prod 2</span></span></td>
<td><span data-ttu-id="dd57f-895">Produto 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-895">Product 2</span></span></td>
<td><span data-ttu-id="dd57f-896">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-896">10001</span></span></td>
<td><span data-ttu-id="dd57f-897">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-897">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-898">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-898">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="dd57f-899">1,495.71</span></span></td>
<td><span data-ttu-id="dd57f-900">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-901">CC003</span><span class="sxs-lookup"><span data-stu-id="dd57f-901">CC003</span></span></td>
<td><span data-ttu-id="dd57f-902">Montagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-902">Assembly</span></span></td>
<td><span data-ttu-id="dd57f-903">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-903">10001</span></span></td>
<td><span data-ttu-id="dd57f-904">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-904">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-905">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-905">Fixed cost</span></span></td>
<td><span data-ttu-id="dd57f-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="dd57f-906">-286.25</span></span></td>
<td><span data-ttu-id="dd57f-907">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-908">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-908">Prod 1</span></span></td>
<td><span data-ttu-id="dd57f-909">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-909">Product 1</span></span></td>
<td><span data-ttu-id="dd57f-910">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-910">10001</span></span></td>
<td><span data-ttu-id="dd57f-911">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-911">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-912">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-912">Fixed cost</span></span></td>
<td><span data-ttu-id="dd57f-913">241.05</span><span class="sxs-lookup"><span data-stu-id="dd57f-913">241.05</span></span></td>
<td><span data-ttu-id="dd57f-914">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-915">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-915">Prod 2</span></span></td>
<td><span data-ttu-id="dd57f-916">Produto 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-916">Product 2</span></span></td>
<td><span data-ttu-id="dd57f-917">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-917">10001</span></span></td>
<td><span data-ttu-id="dd57f-918">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-918">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-919">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-919">Fixed cost</span></span></td>
<td><span data-ttu-id="dd57f-920">45.20</span><span class="sxs-lookup"><span data-stu-id="dd57f-920">45.20</span></span></td>
<td><span data-ttu-id="dd57f-921">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-922">CC003</span><span class="sxs-lookup"><span data-stu-id="dd57f-922">CC003</span></span></td>
<td><span data-ttu-id="dd57f-923">Montagem</span><span class="sxs-lookup"><span data-stu-id="dd57f-923">Assembly</span></span></td>
<td><span data-ttu-id="dd57f-924">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-924">10001</span></span></td>
<td><span data-ttu-id="dd57f-925">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-925">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-926">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-926">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="dd57f-927">-2,977.17</span></span></td>
<td><span data-ttu-id="dd57f-928">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-929">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-929">Prod 1</span></span></td>
<td><span data-ttu-id="dd57f-930">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-930">Product 1</span></span></td>
<td><span data-ttu-id="dd57f-931">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-931">10001</span></span></td>
<td><span data-ttu-id="dd57f-932">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-932">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-933">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-933">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="dd57f-934">2,507.09</span></span></td>
<td><span data-ttu-id="dd57f-935">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dd57f-936">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-936">Prod 2</span></span></td>
<td><span data-ttu-id="dd57f-937">Produto 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-937">Product 2</span></span></td>
<td><span data-ttu-id="dd57f-938">10001</span><span class="sxs-lookup"><span data-stu-id="dd57f-938">10001</span></span></td>
<td><span data-ttu-id="dd57f-939">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-939">Electricity</span></span></td>
<td><span data-ttu-id="dd57f-940">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-940">Variable cost</span></span></td>
<td><span data-ttu-id="dd57f-941">470.08</span><span class="sxs-lookup"><span data-stu-id="dd57f-941">470.08</span></span></td>
<td><span data-ttu-id="dd57f-942">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dd57f-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="dd57f-943">Conclusão</span><span class="sxs-lookup"><span data-stu-id="dd57f-943">Conclusion</span></span>
<span data-ttu-id="dd57f-944">Na contabilidade financeira, um custo de 10,000.00 para a eletricidade é lançado para um ID fictício de centro de custos.</span><span class="sxs-lookup"><span data-stu-id="dd57f-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="dd57f-945">Portanto, os contadores de custo saberão que esses custos devem ser alocados.</span><span class="sxs-lookup"><span data-stu-id="dd57f-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="dd57f-946">Na contabilização de custo, os custos fluem nas unidades organizacionais e nos níveis, com base nas políticas e regras que são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="dd57f-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="dd57f-947">Cada custo foi associado a uma base de alocação que fornece a melhor apuração para a alocação de custos.</span><span class="sxs-lookup"><span data-stu-id="dd57f-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="dd57f-948">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="dd57f-949">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dd57f-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="dd57f-950">Total</span><span class="sxs-lookup"><span data-stu-id="dd57f-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="dd57f-951">CC099</span><span class="sxs-lookup"><span data-stu-id="dd57f-951">CC099</span></span></th>
<th><span data-ttu-id="dd57f-952">CC001</span><span class="sxs-lookup"><span data-stu-id="dd57f-952">CC001</span></span></th>
<th><span data-ttu-id="dd57f-953">CC002</span><span class="sxs-lookup"><span data-stu-id="dd57f-953">CC002</span></span></th>
<th><span data-ttu-id="dd57f-954">CC003</span><span class="sxs-lookup"><span data-stu-id="dd57f-954">CC003</span></span></th>
<th><span data-ttu-id="dd57f-955">CC004</span><span class="sxs-lookup"><span data-stu-id="dd57f-955">CC004</span></span></th>
<th><span data-ttu-id="dd57f-956">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-956">Proj 1</span></span></th>
<th><span data-ttu-id="dd57f-957">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-957">Proj 2</span></span></th>
<th><span data-ttu-id="dd57f-958">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dd57f-958">Prod 1</span></span></th>
<th><span data-ttu-id="dd57f-959">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dd57f-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="dd57f-960">10001 Eletricidade</span><span class="sxs-lookup"><span data-stu-id="dd57f-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="dd57f-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="dd57f-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="dd57f-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="dd57f-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="dd57f-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="dd57f-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="dd57f-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="dd57f-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="dd57f-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="dd57f-970">Não classificado</span><span class="sxs-lookup"><span data-stu-id="dd57f-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-971">0,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="dd57f-972">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dd57f-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-973">0,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-974">0,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-975">0,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-976">0,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-977">0,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-978">776.36</span><span class="sxs-lookup"><span data-stu-id="dd57f-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-979">223.64</span><span class="sxs-lookup"><span data-stu-id="dd57f-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="dd57f-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="dd57f-981">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dd57f-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-982">000</span><span class="sxs-lookup"><span data-stu-id="dd57f-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-983">0,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-984">0,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-985">0,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-986">0,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-987">30,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-988">10,00</span><span class="sxs-lookup"><span data-stu-id="dd57f-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="dd57f-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="dd57f-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dd57f-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="dd57f-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="dd57f-992">Esse tópico mostra como um elemento de custo principal, 10001 Eletricidade flui pelos objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="dd57f-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="dd57f-993">Portanto, esse custo geral indireto é alocado no nível mais baixo na organização.</span><span class="sxs-lookup"><span data-stu-id="dd57f-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="dd57f-994">Em outras palavras, os objetos de custo no nível mais baixo assumem o custo.</span><span class="sxs-lookup"><span data-stu-id="dd57f-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="dd57f-995">Se você exigir um fluxo visual de custo entre objetos de custo, é possível usar as regras de política de acúmulo de custos para visualizar o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="dd57f-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="dd57f-996">Para obter mais informações, consulte [Política de acúmulo de custo e cálculo de custos indiretos](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="dd57f-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]