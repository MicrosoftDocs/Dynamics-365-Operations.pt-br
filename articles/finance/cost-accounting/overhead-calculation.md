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
ms.openlocfilehash: d60248f2bd6774b2e9afdb3632b6eb31d67349ce
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009509"
---
# <a name="overhead-calculation"></a><span data-ttu-id="6a308-103">Cálculo de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="6a308-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6a308-104">Este tópico descreve processos comuns para calcular e alocar os custos gerais indiretos.</span><span class="sxs-lookup"><span data-stu-id="6a308-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="6a308-105">Definição de termo</span><span class="sxs-lookup"><span data-stu-id="6a308-105">Term definition</span></span>
---------------

<span data-ttu-id="6a308-106">Os custos gerais indiretos são aqueles que foram incorridos para realizar um negócio, mas não podem ser diretamente atribuídos a qualquer atividade comercial, produto ou serviço específico.</span><span class="sxs-lookup"><span data-stu-id="6a308-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="6a308-107">Os custos gerais indiretos fornecem suporte crítico para geração de atividades produtivas.</span><span class="sxs-lookup"><span data-stu-id="6a308-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="6a308-108">Eis alguns exemplos de custos gerais:</span><span class="sxs-lookup"><span data-stu-id="6a308-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="6a308-109">Aluguel</span><span class="sxs-lookup"><span data-stu-id="6a308-109">Rent</span></span>
-   <span data-ttu-id="6a308-110">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-110">Electricity</span></span>
-   <span data-ttu-id="6a308-111">Salários administrativos</span><span class="sxs-lookup"><span data-stu-id="6a308-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="6a308-112">Visão geral do cálculo de custos gerais indiretos</span><span class="sxs-lookup"><span data-stu-id="6a308-112">Overhead calculation overview</span></span>
<span data-ttu-id="6a308-113">O cálculo de custos gerais indiretos executa as políticas de contabilização de custos na ordem correta.</span><span class="sxs-lookup"><span data-stu-id="6a308-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="6a308-114">Você pode executar o cálculo de custos gerais indiretos várias vezes para o mesmo período fiscal, se as políticas de contabilidade de custo foram modificadas ou foram detectados erros específicos.</span><span class="sxs-lookup"><span data-stu-id="6a308-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="6a308-115">Cada execução do cálculo de custos gerais indiretos é armazenada e recebe um ID exclusivo de versão que permite comparar os cálculos em várias versões.</span><span class="sxs-lookup"><span data-stu-id="6a308-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="6a308-116">As entradas de custo que o cálculo de custos indiretos gera recebe uma data contábil.</span><span class="sxs-lookup"><span data-stu-id="6a308-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="6a308-117">Essa data contábil corresponde à data final do período fiscal que é usada no cálculo.</span><span class="sxs-lookup"><span data-stu-id="6a308-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="6a308-118">A ID exclusiva de versão consiste nos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="6a308-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="6a308-119">Tipo de versão</span><span class="sxs-lookup"><span data-stu-id="6a308-119">Version type</span></span>
-   <span data-ttu-id="6a308-120">Data e hora</span><span class="sxs-lookup"><span data-stu-id="6a308-120">Date and time</span></span>
-   <span data-ttu-id="6a308-121">Razão de contabilização de custos</span><span class="sxs-lookup"><span data-stu-id="6a308-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="6a308-122">Ano fiscal</span><span class="sxs-lookup"><span data-stu-id="6a308-122">Fiscal year</span></span>
-   <span data-ttu-id="6a308-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="6a308-123">Fiscal period</span></span>

<span data-ttu-id="6a308-124">O cálculo de custos gerais indiretos é executado independentemente da versão.</span><span class="sxs-lookup"><span data-stu-id="6a308-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="6a308-125">Portanto, você pode calcular a versão de orçamento antes da versão atual.</span><span class="sxs-lookup"><span data-stu-id="6a308-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="6a308-126">O cálculo de custos gerais indiretos consiste em quatro etapas, conforme mostrado na ilustração.</span><span class="sxs-lookup"><span data-stu-id="6a308-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="6a308-127">Em cada etapa, um cabeçalho de diário é criado com entradas de diário.</span><span class="sxs-lookup"><span data-stu-id="6a308-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="6a308-128">Esse cabeçalho de diário mantém dados de entrada para cada etapa de cálculo.</span><span class="sxs-lookup"><span data-stu-id="6a308-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="6a308-129">As políticas e regras são aplicadas a cada linha do diário e as entradas de custo são geradas como saídas.</span><span class="sxs-lookup"><span data-stu-id="6a308-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="6a308-130">Portanto, você sempre terá rastreabilidade total.</span><span class="sxs-lookup"><span data-stu-id="6a308-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="6a308-131">[![Cálculo de custos gerais indiretos](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="6a308-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="6a308-132">Calcular e alocar os custos gerais indiretos de Eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="6a308-133">Na contabilidade financeira, alguns custos, como eletricidade, são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="6a308-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="6a308-134">Portanto, a visão administrativa detalhada não é fornecida para a contabilização de custo.</span><span class="sxs-lookup"><span data-stu-id="6a308-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="6a308-135">Na contabilização de custo, para fornecer a visão administrativa correta em todas as unidades organizacionais e níveis, os custos devem passar pelas unidades organizacionais.</span><span class="sxs-lookup"><span data-stu-id="6a308-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="6a308-136">Este fluxo deve ser baseado em qualquer um registro exato do consumo ou de uma previsão justa.</span><span class="sxs-lookup"><span data-stu-id="6a308-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="6a308-137">Na contabilidade, um custo de eletricidade pode ser lançado, conforme mostrado na tabela.</span><span class="sxs-lookup"><span data-stu-id="6a308-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="6a308-138">Data contábil</span><span class="sxs-lookup"><span data-stu-id="6a308-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="6a308-139">Centro de custos</span><span class="sxs-lookup"><span data-stu-id="6a308-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="6a308-140">Conta principal</span><span class="sxs-lookup"><span data-stu-id="6a308-140">Main account</span></span></th>
<th><span data-ttu-id="6a308-141">Valor na moeda contábil</span><span class="sxs-lookup"><span data-stu-id="6a308-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-142">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="6a308-143">CC099</span><span class="sxs-lookup"><span data-stu-id="6a308-143">CC099</span></span></td>
<td><span data-ttu-id="6a308-144">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="6a308-144">Default cost center</span></span></td>
<td><span data-ttu-id="6a308-145">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-145">10001</span></span></td>
<td><span data-ttu-id="6a308-146">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-146">Electricity</span></span></td>
<td><span data-ttu-id="6a308-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="6a308-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="6a308-148">Etapa 1: Processar o cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="6a308-149">Por padrão, quando as entradas de custo previsto são importadas de dados de origem, elas recebem a classificação de comportamento de custo **Não classificado** na Contabilidade de custos.</span><span class="sxs-lookup"><span data-stu-id="6a308-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="6a308-150">Aplicando regras da política de comportamento de custo, é possível reclassificar entradas de custo como **Custo fixo** ou **Custo variável**.</span><span class="sxs-lookup"><span data-stu-id="6a308-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="6a308-151">Definir a regra de custo de comportamento</span><span class="sxs-lookup"><span data-stu-id="6a308-151">Define the cost behavior rule</span></span>

<span data-ttu-id="6a308-152">Em alguns casos, parte do custo é uma taxa fixa e o custos pendente é baseado no consumo.</span><span class="sxs-lookup"><span data-stu-id="6a308-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="6a308-153">Geralmente, as contas de eletricidade correspondem a esta definição.</span><span class="sxs-lookup"><span data-stu-id="6a308-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="6a308-154">Após você pagar uma taxa fixa específica, você paga por consumo, por hora de quilowatt (Kwh).</span><span class="sxs-lookup"><span data-stu-id="6a308-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="6a308-155">Por exemplo, se a taxa de custo fixa for 1.000.00, veja aqui como a regra de comportamento de custo é definida:</span><span class="sxs-lookup"><span data-stu-id="6a308-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="6a308-156">Valor fixo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="6a308-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="6a308-157">0 &lt;= 1.000,00 = Fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="6a308-158">1000.01 &lt; N = Variável</span><span class="sxs-lookup"><span data-stu-id="6a308-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="6a308-159">Diário</span><span class="sxs-lookup"><span data-stu-id="6a308-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="6a308-160">Diário</span><span class="sxs-lookup"><span data-stu-id="6a308-160">Journal</span></span></th>
<th><span data-ttu-id="6a308-161">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="6a308-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="6a308-162">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="6a308-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="6a308-163">Versão</span><span class="sxs-lookup"><span data-stu-id="6a308-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-164">00001</span><span class="sxs-lookup"><span data-stu-id="6a308-164">00001</span></span></td>
<td><span data-ttu-id="6a308-165">Diário de cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="6a308-166">fiscal</span><span class="sxs-lookup"><span data-stu-id="6a308-166">Fiscal</span></span></td>
<td><span data-ttu-id="6a308-167">2017</span><span class="sxs-lookup"><span data-stu-id="6a308-167">2017</span></span></td>
<td><span data-ttu-id="6a308-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="6a308-168">Period 1</span></span></td>
<td><span data-ttu-id="6a308-169">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="6a308-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="6a308-170">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="6a308-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="6a308-171">Data contábil</span><span class="sxs-lookup"><span data-stu-id="6a308-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="6a308-172">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="6a308-173">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-173">Cost element</span></span></th>
<th><span data-ttu-id="6a308-174">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-174">Cost behavior</span></span></th>
<th><span data-ttu-id="6a308-175">Valor</span><span class="sxs-lookup"><span data-stu-id="6a308-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-176">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="6a308-177">CC099</span><span class="sxs-lookup"><span data-stu-id="6a308-177">CC099</span></span></td>
<td><span data-ttu-id="6a308-178">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="6a308-178">Default cost center</span></span></td>
<td><span data-ttu-id="6a308-179">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-179">10001</span></span></td>
<td><span data-ttu-id="6a308-180">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-180">Electricity</span></span></td>
<td><span data-ttu-id="6a308-181">Não classificado</span><span class="sxs-lookup"><span data-stu-id="6a308-181">Unclassified</span></span></td>
<td><span data-ttu-id="6a308-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="6a308-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="6a308-183">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6a308-184">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="6a308-185">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-185">Cost element</span></span></th>
<th><span data-ttu-id="6a308-186">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-186">Cost behavior</span></span></th>
<th><span data-ttu-id="6a308-187">Valor</span><span class="sxs-lookup"><span data-stu-id="6a308-187">Amount</span></span></th>
<th><span data-ttu-id="6a308-188">Data contábil</span><span class="sxs-lookup"><span data-stu-id="6a308-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-189">CC099</span><span class="sxs-lookup"><span data-stu-id="6a308-189">CC099</span></span></td>
<td><span data-ttu-id="6a308-190">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="6a308-190">Default cost center</span></span></td>
<td><span data-ttu-id="6a308-191">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-191">10001</span></span></td>
<td><span data-ttu-id="6a308-192">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-192">Electricity</span></span></td>
<td><span data-ttu-id="6a308-193">Não classificado</span><span class="sxs-lookup"><span data-stu-id="6a308-193">Unclassified</span></span></td>
<td><span data-ttu-id="6a308-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="6a308-194">10,000.00</span></span></td>
<td><span data-ttu-id="6a308-195">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-196">CC099</span><span class="sxs-lookup"><span data-stu-id="6a308-196">CC099</span></span></td>
<td><span data-ttu-id="6a308-197">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="6a308-197">Default cost center</span></span></td>
<td><span data-ttu-id="6a308-198">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-198">10001</span></span></td>
<td><span data-ttu-id="6a308-199">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-199">Electricity</span></span></td>
<td><span data-ttu-id="6a308-200">Não classificado</span><span class="sxs-lookup"><span data-stu-id="6a308-200">Unclassified</span></span></td>
<td><span data-ttu-id="6a308-201">-10.000,00</span><span class="sxs-lookup"><span data-stu-id="6a308-201">-10,000.00</span></span></td>
<td><span data-ttu-id="6a308-202">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-203">CC099</span><span class="sxs-lookup"><span data-stu-id="6a308-203">CC099</span></span></td>
<td><span data-ttu-id="6a308-204">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="6a308-204">Default cost center</span></span></td>
<td><span data-ttu-id="6a308-205">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-205">10001</span></span></td>
<td><span data-ttu-id="6a308-206">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-206">Electricity</span></span></td>
<td><span data-ttu-id="6a308-207">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-207">Fixed cost</span></span></td>
<td><span data-ttu-id="6a308-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="6a308-208">1,000.00</span></span></td>
<td><span data-ttu-id="6a308-209">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-210">CC099</span><span class="sxs-lookup"><span data-stu-id="6a308-210">CC099</span></span></td>
<td><span data-ttu-id="6a308-211">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="6a308-211">Default cost center</span></span></td>
<td><span data-ttu-id="6a308-212">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-212">10001</span></span></td>
<td><span data-ttu-id="6a308-213">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-213">Electricity</span></span></td>
<td><span data-ttu-id="6a308-214">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-214">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="6a308-215">9,000.00</span></span></td>
<td><span data-ttu-id="6a308-216">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6a308-217">Para obter mais informações, consulte [Criar e atribuir uma política de comportamento de custos a uma unidade de controle de custos](tasks/create-assign-cost-behavior-policy-cost-control-unit.md)</span><span class="sxs-lookup"><span data-stu-id="6a308-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="6a308-218">Etapa 2: Processar o cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="6a308-219">A distribuição de custos é usada para redistribuir custo de um objeto de custo a um ou mais outros objetos de custo, aplicando uma base de alocação relevante.</span><span class="sxs-lookup"><span data-stu-id="6a308-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="6a308-220">A distribuição de custos e a alocação de custo são diferentes na distribuição de custos, sempre que ocorrer em nível de elemento de custo principal do custo original.</span><span class="sxs-lookup"><span data-stu-id="6a308-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="6a308-221">Definir a regra de distribuição de custos</span><span class="sxs-lookup"><span data-stu-id="6a308-221">Define the cost distribution rule</span></span>

<span data-ttu-id="6a308-222">Na contabilidade financeira, os custos de eletricidade geralmente são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="6a308-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="6a308-223">Na contabilização de custo, esta abordagem não é suficientemente detalhada.</span><span class="sxs-lookup"><span data-stu-id="6a308-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="6a308-224">O custo variável deve ser distribuído a objetos de custos individuais com base justa.</span><span class="sxs-lookup"><span data-stu-id="6a308-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="6a308-225">A base de alocação mais lógica é o consumo de eletricidade (Kwh).</span><span class="sxs-lookup"><span data-stu-id="6a308-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="6a308-226">O membro da dimensão estatística que é chamado Eletricidade é criado e o consumo de eletricidade é registrado.</span><span class="sxs-lookup"><span data-stu-id="6a308-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="6a308-227">Por padrão, todos os membros estatísticos da dimensão se tornam disponíveis como bases de alocação.</span><span class="sxs-lookup"><span data-stu-id="6a308-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6a308-228">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-228">Cost object</span></span></th>
<th><span data-ttu-id="6a308-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="6a308-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-230">CC001</span><span class="sxs-lookup"><span data-stu-id="6a308-230">CC001</span></span></td>
<td><span data-ttu-id="6a308-231">RH</span><span class="sxs-lookup"><span data-stu-id="6a308-231">HR</span></span></td>
<td><span data-ttu-id="6a308-232">1.000</span><span class="sxs-lookup"><span data-stu-id="6a308-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-233">CC002</span><span class="sxs-lookup"><span data-stu-id="6a308-233">CC002</span></span></td>
<td><span data-ttu-id="6a308-234">Finanças</span><span class="sxs-lookup"><span data-stu-id="6a308-234">Finance</span></span></td>
<td><span data-ttu-id="6a308-235">6,000</span><span class="sxs-lookup"><span data-stu-id="6a308-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-236">CC003</span><span class="sxs-lookup"><span data-stu-id="6a308-236">CC003</span></span></td>
<td><span data-ttu-id="6a308-237">Montagem</span><span class="sxs-lookup"><span data-stu-id="6a308-237">Assembly</span></span></td>
<td><span data-ttu-id="6a308-238">0</span><span class="sxs-lookup"><span data-stu-id="6a308-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6a308-239">A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação para custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="6a308-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6a308-240">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-240">Cost object</span></span></th>
<th><span data-ttu-id="6a308-241">Magnitude</span><span class="sxs-lookup"><span data-stu-id="6a308-241">Magnitude</span></span></th>
<th><span data-ttu-id="6a308-242">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="6a308-242">Allocation factor</span></span></th>
<th><span data-ttu-id="6a308-243">Valor</span><span class="sxs-lookup"><span data-stu-id="6a308-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-244">CC001</span><span class="sxs-lookup"><span data-stu-id="6a308-244">CC001</span></span></td>
<td><span data-ttu-id="6a308-245">RH</span><span class="sxs-lookup"><span data-stu-id="6a308-245">HR</span></span></td>
<td><span data-ttu-id="6a308-246">1.000</span><span class="sxs-lookup"><span data-stu-id="6a308-246">1,000</span></span></td>
<td><span data-ttu-id="6a308-247">(1.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="6a308-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="6a308-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="6a308-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-249">CC002</span><span class="sxs-lookup"><span data-stu-id="6a308-249">CC002</span></span></td>
<td><span data-ttu-id="6a308-250">Finanças</span><span class="sxs-lookup"><span data-stu-id="6a308-250">Finance</span></span></td>
<td><span data-ttu-id="6a308-251">6,000</span><span class="sxs-lookup"><span data-stu-id="6a308-251">6,000</span></span></td>
<td><span data-ttu-id="6a308-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="6a308-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="6a308-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="6a308-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-254">CC003</span><span class="sxs-lookup"><span data-stu-id="6a308-254">CC003</span></span></td>
<td><span data-ttu-id="6a308-255">Montagem</span><span class="sxs-lookup"><span data-stu-id="6a308-255">Assembly</span></span></td>
<td><span data-ttu-id="6a308-256">0</span><span class="sxs-lookup"><span data-stu-id="6a308-256">0</span></span></td>
<td><span data-ttu-id="6a308-257">(0 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="6a308-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="6a308-258">0,00</span><span class="sxs-lookup"><span data-stu-id="6a308-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6a308-259">Os custos fixos devem ser distribuídos igualmente a objetos de custo individuais que têm a eletricidade consumida.</span><span class="sxs-lookup"><span data-stu-id="6a308-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="6a308-260">Você pode obter esse resultado usando o membro estatístico de dimensão de eletricidade em uma base e alocação da fórmula: (Eletricidade &gt; 0,00) A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação de custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="6a308-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6a308-261">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-261">Cost object</span></span></th>
<th><span data-ttu-id="6a308-262">Fórmula</span><span class="sxs-lookup"><span data-stu-id="6a308-262">Formula</span></span></th>
<th><span data-ttu-id="6a308-263">Magnitude</span><span class="sxs-lookup"><span data-stu-id="6a308-263">Magnitude</span></span></th>
<th><span data-ttu-id="6a308-264">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="6a308-264">Allocation factor</span></span></th>
<th><span data-ttu-id="6a308-265">Valor</span><span class="sxs-lookup"><span data-stu-id="6a308-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-266">CC001</span><span class="sxs-lookup"><span data-stu-id="6a308-266">CC001</span></span></td>
<td><span data-ttu-id="6a308-267">RH</span><span class="sxs-lookup"><span data-stu-id="6a308-267">HR</span></span></td>
<td><span data-ttu-id="6a308-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="6a308-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="6a308-269">1</span><span class="sxs-lookup"><span data-stu-id="6a308-269">1</span></span></td>
<td><span data-ttu-id="6a308-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="6a308-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="6a308-271">500,00</span><span class="sxs-lookup"><span data-stu-id="6a308-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-272">CC002</span><span class="sxs-lookup"><span data-stu-id="6a308-272">CC002</span></span></td>
<td><span data-ttu-id="6a308-273">Finanças</span><span class="sxs-lookup"><span data-stu-id="6a308-273">Finance</span></span></td>
<td><span data-ttu-id="6a308-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="6a308-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="6a308-275">1</span><span class="sxs-lookup"><span data-stu-id="6a308-275">1</span></span></td>
<td><span data-ttu-id="6a308-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="6a308-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="6a308-277">500,00</span><span class="sxs-lookup"><span data-stu-id="6a308-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-278">CC003</span><span class="sxs-lookup"><span data-stu-id="6a308-278">CC003</span></span></td>
<td><span data-ttu-id="6a308-279">Montagem</span><span class="sxs-lookup"><span data-stu-id="6a308-279">Assembly</span></span></td>
<td><span data-ttu-id="6a308-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="6a308-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="6a308-281">0</span><span class="sxs-lookup"><span data-stu-id="6a308-281">0</span></span></td>
<td><span data-ttu-id="6a308-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="6a308-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="6a308-283">0,00</span><span class="sxs-lookup"><span data-stu-id="6a308-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="6a308-284">Diário</span><span class="sxs-lookup"><span data-stu-id="6a308-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="6a308-285">Diário</span><span class="sxs-lookup"><span data-stu-id="6a308-285">Journal</span></span></th>
<th><span data-ttu-id="6a308-286">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="6a308-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="6a308-287">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="6a308-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="6a308-288">Versão</span><span class="sxs-lookup"><span data-stu-id="6a308-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-289">00002</span><span class="sxs-lookup"><span data-stu-id="6a308-289">00002</span></span></td>
<td><span data-ttu-id="6a308-290">Diário de cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="6a308-291">fiscal</span><span class="sxs-lookup"><span data-stu-id="6a308-291">Fiscal</span></span></td>
<td><span data-ttu-id="6a308-292">2017</span><span class="sxs-lookup"><span data-stu-id="6a308-292">2017</span></span></td>
<td><span data-ttu-id="6a308-293">Período 1</span><span class="sxs-lookup"><span data-stu-id="6a308-293">Period 1</span></span></td>
<td><span data-ttu-id="6a308-294">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="6a308-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="6a308-295">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="6a308-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="6a308-296">Data contábil</span><span class="sxs-lookup"><span data-stu-id="6a308-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="6a308-297">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="6a308-298">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-298">Cost element</span></span></th>
<th><span data-ttu-id="6a308-299">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-299">Cost behavior</span></span></th>
<th><span data-ttu-id="6a308-300">Valor</span><span class="sxs-lookup"><span data-stu-id="6a308-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-301">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="6a308-302">CC099</span><span class="sxs-lookup"><span data-stu-id="6a308-302">CC099</span></span></td>
<td><span data-ttu-id="6a308-303">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="6a308-303">Default cost center</span></span></td>
<td><span data-ttu-id="6a308-304">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-304">10001</span></span></td>
<td><span data-ttu-id="6a308-305">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-305">Electricity</span></span></td>
<td><span data-ttu-id="6a308-306">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-306">Fixed cost</span></span></td>
<td><span data-ttu-id="6a308-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="6a308-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-308">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="6a308-309">CC099</span><span class="sxs-lookup"><span data-stu-id="6a308-309">CC099</span></span></td>
<td><span data-ttu-id="6a308-310">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="6a308-310">Default cost center</span></span></td>
<td><span data-ttu-id="6a308-311">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-311">10001</span></span></td>
<td><span data-ttu-id="6a308-312">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-312">Electricity</span></span></td>
<td><span data-ttu-id="6a308-313">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-313">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="6a308-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="6a308-315">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6a308-316">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="6a308-317">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-317">Cost element</span></span></th>
<th><span data-ttu-id="6a308-318">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-318">Cost behavior</span></span></th>
<th><span data-ttu-id="6a308-319">Valor</span><span class="sxs-lookup"><span data-stu-id="6a308-319">Amount</span></span></th>
<th><span data-ttu-id="6a308-320">Data contábil</span><span class="sxs-lookup"><span data-stu-id="6a308-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-321">CC099</span><span class="sxs-lookup"><span data-stu-id="6a308-321">CC099</span></span></td>
<td><span data-ttu-id="6a308-322">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="6a308-322">Default cost center</span></span></td>
<td><span data-ttu-id="6a308-323">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-323">10001</span></span></td>
<td><span data-ttu-id="6a308-324">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-324">Electricity</span></span></td>
<td><span data-ttu-id="6a308-325">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-325">Fixed cost</span></span></td>
<td><span data-ttu-id="6a308-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="6a308-326">-1,000.00</span></span></td>
<td><span data-ttu-id="6a308-327">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-328">CC001</span><span class="sxs-lookup"><span data-stu-id="6a308-328">CC001</span></span></td>
<td><span data-ttu-id="6a308-329">RH</span><span class="sxs-lookup"><span data-stu-id="6a308-329">HR</span></span></td>
<td><span data-ttu-id="6a308-330">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-330">10001</span></span></td>
<td><span data-ttu-id="6a308-331">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-331">Electricity</span></span></td>
<td><span data-ttu-id="6a308-332">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-332">Fixed cost</span></span></td>
<td><span data-ttu-id="6a308-333">500,00</span><span class="sxs-lookup"><span data-stu-id="6a308-333">500.00</span></span></td>
<td><span data-ttu-id="6a308-334">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-335">CC002</span><span class="sxs-lookup"><span data-stu-id="6a308-335">CC002</span></span></td>
<td><span data-ttu-id="6a308-336">Finanças</span><span class="sxs-lookup"><span data-stu-id="6a308-336">Finance</span></span></td>
<td><span data-ttu-id="6a308-337">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-337">10001</span></span></td>
<td><span data-ttu-id="6a308-338">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-338">Electricity</span></span></td>
<td><span data-ttu-id="6a308-339">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-339">Fixed cost</span></span></td>
<td><span data-ttu-id="6a308-340">500,00</span><span class="sxs-lookup"><span data-stu-id="6a308-340">500.00</span></span></td>
<td><span data-ttu-id="6a308-341">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-342">CC099</span><span class="sxs-lookup"><span data-stu-id="6a308-342">CC099</span></span></td>
<td><span data-ttu-id="6a308-343">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="6a308-343">Default cost center</span></span></td>
<td><span data-ttu-id="6a308-344">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-344">10001</span></span></td>
<td><span data-ttu-id="6a308-345">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-345">Electricity</span></span></td>
<td><span data-ttu-id="6a308-346">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-346">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="6a308-347">-9,000.00</span></span></td>
<td><span data-ttu-id="6a308-348">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-349">CC001</span><span class="sxs-lookup"><span data-stu-id="6a308-349">CC001</span></span></td>
<td><span data-ttu-id="6a308-350">RH</span><span class="sxs-lookup"><span data-stu-id="6a308-350">HR</span></span></td>
<td><span data-ttu-id="6a308-351">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-351">10001</span></span></td>
<td><span data-ttu-id="6a308-352">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-352">Electricity</span></span></td>
<td><span data-ttu-id="6a308-353">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-353">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="6a308-354">1,285.71</span></span></td>
<td><span data-ttu-id="6a308-355">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-356">CC002</span><span class="sxs-lookup"><span data-stu-id="6a308-356">CC002</span></span></td>
<td><span data-ttu-id="6a308-357">Finanças</span><span class="sxs-lookup"><span data-stu-id="6a308-357">Finance</span></span></td>
<td><span data-ttu-id="6a308-358">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-358">10001</span></span></td>
<td><span data-ttu-id="6a308-359">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-359">Electricity</span></span></td>
<td><span data-ttu-id="6a308-360">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-360">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="6a308-361">7,714.29</span></span></td>
<td><span data-ttu-id="6a308-362">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6a308-363">Para obter mais informações, consulte [Criar e atribuir uma política de distribuição de custos a uma unidade de controle de custos](tasks/create-assign-cost-distribution-policy-cost-control-unit.md)</span><span class="sxs-lookup"><span data-stu-id="6a308-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="6a308-364">Etapa 3: Processar o cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="6a308-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="6a308-365">A taxa de custos indiretos é usada para cobrar um ou mais objetos de custos específicos.</span><span class="sxs-lookup"><span data-stu-id="6a308-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="6a308-366">O encargo se baseia em uma taxa de custo predeterminada e a magnitude da básica de alocação atribuída.</span><span class="sxs-lookup"><span data-stu-id="6a308-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="6a308-367">Defina a taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="6a308-367">Define the overhead rate</span></span>

<span data-ttu-id="6a308-368">O objeto de custo CC001 HR contribui para um conjunto de projetos internos.</span><span class="sxs-lookup"><span data-stu-id="6a308-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="6a308-369">Um membro de dimensão estatística que é chamado de projetos de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="6a308-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6a308-370">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-370">Cost object</span></span></th>
<th><span data-ttu-id="6a308-371">Horas</span><span class="sxs-lookup"><span data-stu-id="6a308-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-372">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="6a308-372">Proj 1</span></span></td>
<td><span data-ttu-id="6a308-373">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="6a308-373">Project 1</span></span></td>
<td><span data-ttu-id="6a308-374">3</span><span class="sxs-lookup"><span data-stu-id="6a308-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-375">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="6a308-375">Proj 2</span></span></td>
<td><span data-ttu-id="6a308-376">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="6a308-376">Project 2</span></span></td>
<td><span data-ttu-id="6a308-377">1</span><span class="sxs-lookup"><span data-stu-id="6a308-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6a308-378">Uma taxa de custo predeterminada da contribuição de projetos de custo foi definida.</span><span class="sxs-lookup"><span data-stu-id="6a308-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6a308-379">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-379">Cost object</span></span></th>
<th><span data-ttu-id="6a308-380">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-380">Cost element</span></span></th>
<th><span data-ttu-id="6a308-381">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-381">Cost behavior</span></span></th>
<th><span data-ttu-id="6a308-382">Unidades</span><span class="sxs-lookup"><span data-stu-id="6a308-382">Units</span></span></th>
<th><span data-ttu-id="6a308-383">Taxa</span><span class="sxs-lookup"><span data-stu-id="6a308-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-384">CC001</span><span class="sxs-lookup"><span data-stu-id="6a308-384">CC001</span></span></td>
<td><span data-ttu-id="6a308-385">RH</span><span class="sxs-lookup"><span data-stu-id="6a308-385">HR</span></span></td>
<td><span data-ttu-id="6a308-386">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-386">10001</span></span></td>
<td><span data-ttu-id="6a308-387">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-387">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-388">1</span><span class="sxs-lookup"><span data-stu-id="6a308-388">1</span></span></td>
<td><span data-ttu-id="6a308-389">10</span><span class="sxs-lookup"><span data-stu-id="6a308-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6a308-390">A tabela a seguir mostra o resultado quando projetos de RH são aplicados como base de alocação.</span><span class="sxs-lookup"><span data-stu-id="6a308-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6a308-391">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-391">Cost object</span></span></th>
<th><span data-ttu-id="6a308-392">Magnitude</span><span class="sxs-lookup"><span data-stu-id="6a308-392">Magnitude</span></span></th>
<th><span data-ttu-id="6a308-393">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-393">Cost element</span></span></th>
<th><span data-ttu-id="6a308-394">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="6a308-394">Allocation factor</span></span></th>
<th><span data-ttu-id="6a308-395">Valor</span><span class="sxs-lookup"><span data-stu-id="6a308-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-396">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="6a308-396">Proj 1</span></span></td>
<td><span data-ttu-id="6a308-397">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="6a308-397">Project 1</span></span></td>
<td><span data-ttu-id="6a308-398">3</span><span class="sxs-lookup"><span data-stu-id="6a308-398">3</span></span></td>
<td><span data-ttu-id="6a308-399">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-399">10001</span></span></td>
<td><span data-ttu-id="6a308-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="6a308-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="6a308-401">30,00</span><span class="sxs-lookup"><span data-stu-id="6a308-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-402">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="6a308-402">Proj 2</span></span></td>
<td><span data-ttu-id="6a308-403">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="6a308-403">Project 2</span></span></td>
<td><span data-ttu-id="6a308-404">1</span><span class="sxs-lookup"><span data-stu-id="6a308-404">1</span></span></td>
<td><span data-ttu-id="6a308-405">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-405">10001</span></span></td>
<td><span data-ttu-id="6a308-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="6a308-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="6a308-407">10,00</span><span class="sxs-lookup"><span data-stu-id="6a308-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="6a308-408">Diário</span><span class="sxs-lookup"><span data-stu-id="6a308-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="6a308-409">Diário</span><span class="sxs-lookup"><span data-stu-id="6a308-409">Journal</span></span></th>
<th><span data-ttu-id="6a308-410">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="6a308-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="6a308-411">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="6a308-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="6a308-412">Versão</span><span class="sxs-lookup"><span data-stu-id="6a308-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-413">00003</span><span class="sxs-lookup"><span data-stu-id="6a308-413">00003</span></span></td>
<td><span data-ttu-id="6a308-414">Diário de cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="6a308-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="6a308-415">fiscal</span><span class="sxs-lookup"><span data-stu-id="6a308-415">Fiscal</span></span></td>
<td><span data-ttu-id="6a308-416">2017</span><span class="sxs-lookup"><span data-stu-id="6a308-416">2017</span></span></td>
<td><span data-ttu-id="6a308-417">Período 1</span><span class="sxs-lookup"><span data-stu-id="6a308-417">Period 1</span></span></td>
<td><span data-ttu-id="6a308-418">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="6a308-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="6a308-419">Entradas de diário (As entradas de diário para cálculo da taxa de custos indiretos)</span><span class="sxs-lookup"><span data-stu-id="6a308-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="6a308-420">Data contábil</span><span class="sxs-lookup"><span data-stu-id="6a308-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="6a308-421">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-421">Cost object</span></span></th>
<th><span data-ttu-id="6a308-422">Magnitude</span><span class="sxs-lookup"><span data-stu-id="6a308-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-423">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="6a308-424">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="6a308-424">Proj 1</span></span></td>
<td><span data-ttu-id="6a308-425">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="6a308-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="6a308-426">3,00</span><span class="sxs-lookup"><span data-stu-id="6a308-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-427">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="6a308-428">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="6a308-428">Proj 2</span></span></td>
<td><span data-ttu-id="6a308-429">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="6a308-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="6a308-430">1.00</span><span class="sxs-lookup"><span data-stu-id="6a308-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="6a308-431">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6a308-432">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="6a308-433">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-433">Cost element</span></span></th>
<th><span data-ttu-id="6a308-434">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-434">Cost behavior</span></span></th>
<th><span data-ttu-id="6a308-435">Valor</span><span class="sxs-lookup"><span data-stu-id="6a308-435">Amount</span></span></th>
<th><span data-ttu-id="6a308-436">Data contábil</span><span class="sxs-lookup"><span data-stu-id="6a308-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="6a308-437">CC0001</span></span></td>
<td><span data-ttu-id="6a308-438">RH</span><span class="sxs-lookup"><span data-stu-id="6a308-438">HR</span></span></td>
<td><span data-ttu-id="6a308-439">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-439">10001</span></span></td>
<td><span data-ttu-id="6a308-440">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-440">Electricity</span></span></td>
<td><span data-ttu-id="6a308-441">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-441">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="6a308-442">-30.00</span></span></td>
<td><span data-ttu-id="6a308-443">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-444">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="6a308-444">Proj 1</span></span></td>
<td><span data-ttu-id="6a308-445">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="6a308-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="6a308-446">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-446">10001</span></span></td>
<td><span data-ttu-id="6a308-447">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-447">Electricity</span></span></td>
<td><span data-ttu-id="6a308-448">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-448">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-449">30,00</span><span class="sxs-lookup"><span data-stu-id="6a308-449">30.00</span></span></td>
<td><span data-ttu-id="6a308-450">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-451">CC001</span><span class="sxs-lookup"><span data-stu-id="6a308-451">CC001</span></span></td>
<td><span data-ttu-id="6a308-452">RH</span><span class="sxs-lookup"><span data-stu-id="6a308-452">HR</span></span></td>
<td><span data-ttu-id="6a308-453">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-453">10001</span></span></td>
<td><span data-ttu-id="6a308-454">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-454">Electricity</span></span></td>
<td><span data-ttu-id="6a308-455">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-455">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="6a308-456">-10.00</span></span></td>
<td><span data-ttu-id="6a308-457">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-458">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="6a308-458">Proj 2</span></span></td>
<td><span data-ttu-id="6a308-459">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="6a308-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="6a308-460">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-460">10001</span></span></td>
<td><span data-ttu-id="6a308-461">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-461">Electricity</span></span></td>
<td><span data-ttu-id="6a308-462">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-462">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-463">10,00</span><span class="sxs-lookup"><span data-stu-id="6a308-463">10.00</span></span></td>
<td><span data-ttu-id="6a308-464">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6a308-465">Para obter mais informações, consulte [Realizar cálculo de custos indiretos](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="6a308-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="6a308-466">Etapa 4: Processar o cálculo de alocação de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="6a308-467">A alocação é usada para alocar o saldo de um objeto de custo a outros objetos de custo pela aplicação de uma base de alocação.</span><span class="sxs-lookup"><span data-stu-id="6a308-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="6a308-468">O Finance oferece suporte ao método de alocação recíproco.</span><span class="sxs-lookup"><span data-stu-id="6a308-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="6a308-469">No método de alocação recíproco, os serviços mútuos que os objetos de custo auxiliar trocam são totalmente reconhecidos.</span><span class="sxs-lookup"><span data-stu-id="6a308-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="6a308-470">O sistema determina automaticamente a ordem correta realizar as alocações.</span><span class="sxs-lookup"><span data-stu-id="6a308-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="6a308-471">O saldo de um objeto de custo é alocado por uma base de alocação única.</span><span class="sxs-lookup"><span data-stu-id="6a308-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="6a308-472">As alocações entre as dimensões de objetos de custo e os respectivos membros são suportadas.</span><span class="sxs-lookup"><span data-stu-id="6a308-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="6a308-473">A ordem de alocação é controlada pela unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="6a308-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="6a308-474">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="6a308-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="6a308-475">Defina a alocação de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-475">Define the cost allocation</span></span>

<span data-ttu-id="6a308-476">Aqui está um exemplo simples que explica como você pode rastrear o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="6a308-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="6a308-477">O objeto de custo previsto CC001 HR contribui a vários objetos de custo previsto.</span><span class="sxs-lookup"><span data-stu-id="6a308-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="6a308-478">Um membro de dimensão estatística que é chamado de serviços de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="6a308-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6a308-479">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-479">Cost object</span></span></th>
<th><span data-ttu-id="6a308-480">Serviços de RH</span><span class="sxs-lookup"><span data-stu-id="6a308-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-481">CC002</span><span class="sxs-lookup"><span data-stu-id="6a308-481">CC002</span></span></td>
<td><span data-ttu-id="6a308-482">Finanças</span><span class="sxs-lookup"><span data-stu-id="6a308-482">Finance</span></span></td>
<td><span data-ttu-id="6a308-483">35</span><span class="sxs-lookup"><span data-stu-id="6a308-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-484">CC003</span><span class="sxs-lookup"><span data-stu-id="6a308-484">CC003</span></span></td>
<td><span data-ttu-id="6a308-485">Montagem</span><span class="sxs-lookup"><span data-stu-id="6a308-485">Assembly</span></span></td>
<td><span data-ttu-id="6a308-486">55</span><span class="sxs-lookup"><span data-stu-id="6a308-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-487">CC004</span><span class="sxs-lookup"><span data-stu-id="6a308-487">CC004</span></span></td>
<td><span data-ttu-id="6a308-488">Embalagem</span><span class="sxs-lookup"><span data-stu-id="6a308-488">Packaging</span></span></td>
<td><span data-ttu-id="6a308-489">10</span><span class="sxs-lookup"><span data-stu-id="6a308-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6a308-490">O objeto de custo CC002 Finanças contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="6a308-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="6a308-491">Um membro de dimensão estatística que é chamado de serviços de Finanças foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="6a308-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6a308-492">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-492">Cost object</span></span></th>
<th><span data-ttu-id="6a308-493">Serviços financeiros</span><span class="sxs-lookup"><span data-stu-id="6a308-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-494">CC003</span><span class="sxs-lookup"><span data-stu-id="6a308-494">CC003</span></span></td>
<td><span data-ttu-id="6a308-495">Montagem</span><span class="sxs-lookup"><span data-stu-id="6a308-495">Assembly</span></span></td>
<td><span data-ttu-id="6a308-496">65</span><span class="sxs-lookup"><span data-stu-id="6a308-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-497">CC004</span><span class="sxs-lookup"><span data-stu-id="6a308-497">CC004</span></span></td>
<td><span data-ttu-id="6a308-498">Embalagem</span><span class="sxs-lookup"><span data-stu-id="6a308-498">Packaging</span></span></td>
<td><span data-ttu-id="6a308-499">35</span><span class="sxs-lookup"><span data-stu-id="6a308-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6a308-500">O objeto de custo CC003 Montagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="6a308-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="6a308-501">Um membro de dimensão estatística que é chamado de serviços de Montagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="6a308-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6a308-502">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-502">Cost object</span></span></th>
<th><span data-ttu-id="6a308-503">Serviços de montagem (horas)</span><span class="sxs-lookup"><span data-stu-id="6a308-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-504">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="6a308-504">Prod 1</span></span></td>
<td><span data-ttu-id="6a308-505">Produto 1</span><span class="sxs-lookup"><span data-stu-id="6a308-505">Product 1</span></span></td>
<td><span data-ttu-id="6a308-506">60</span><span class="sxs-lookup"><span data-stu-id="6a308-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-507">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="6a308-507">Prod 2</span></span></td>
<td><span data-ttu-id="6a308-508">Produto 2</span><span class="sxs-lookup"><span data-stu-id="6a308-508">Product 2</span></span></td>
<td><span data-ttu-id="6a308-509">20</span><span class="sxs-lookup"><span data-stu-id="6a308-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6a308-510">O objeto de custo CC004 Embalagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="6a308-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="6a308-511">Um membro de dimensão estatística que é chamado de serviços de Embalagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="6a308-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6a308-512">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-512">Cost object</span></span></th>
<th><span data-ttu-id="6a308-513">Serviços de embalagem (horas)</span><span class="sxs-lookup"><span data-stu-id="6a308-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-514">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="6a308-514">Prod 1</span></span></td>
<td><span data-ttu-id="6a308-515">Produto 1</span><span class="sxs-lookup"><span data-stu-id="6a308-515">Product 1</span></span></td>
<td><span data-ttu-id="6a308-516">80</span><span class="sxs-lookup"><span data-stu-id="6a308-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-517">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="6a308-517">Prod 2</span></span></td>
<td><span data-ttu-id="6a308-518">Produto 2</span><span class="sxs-lookup"><span data-stu-id="6a308-518">Product 2</span></span></td>
<td><span data-ttu-id="6a308-519">15</span><span class="sxs-lookup"><span data-stu-id="6a308-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="6a308-520">Medidas estatísticas, como as horas de produção que um produto consome, podem ser derivadas dos dados de origem.</span><span class="sxs-lookup"><span data-stu-id="6a308-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="6a308-521">Para obter mais informações, consulte [Modelo de provedor de medidas estatísticas](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="6a308-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="6a308-522">A tabela a seguir mostra o resultado quando os serviços de RH são aplicados como base de alocação para custos totais (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="6a308-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6a308-523">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-523">Cost object</span></span></th>
<th><span data-ttu-id="6a308-524">Magnitude</span><span class="sxs-lookup"><span data-stu-id="6a308-524">Magnitude</span></span></th>
<th><span data-ttu-id="6a308-525">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="6a308-525">Allocation factor</span></span></th>
<th><span data-ttu-id="6a308-526">Valor</span><span class="sxs-lookup"><span data-stu-id="6a308-526">Amount</span></span></th>
<th><span data-ttu-id="6a308-527">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-528">CC002</span><span class="sxs-lookup"><span data-stu-id="6a308-528">CC002</span></span></td>
<td><span data-ttu-id="6a308-529">Finanças</span><span class="sxs-lookup"><span data-stu-id="6a308-529">Finance</span></span></td>
<td><span data-ttu-id="6a308-530">35</span><span class="sxs-lookup"><span data-stu-id="6a308-530">35</span></span></td>
<td><span data-ttu-id="6a308-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="6a308-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="6a308-532">175.00</span><span class="sxs-lookup"><span data-stu-id="6a308-532">175.00</span></span></td>
<td><span data-ttu-id="6a308-533">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-534">CC003</span><span class="sxs-lookup"><span data-stu-id="6a308-534">CC003</span></span></td>
<td><span data-ttu-id="6a308-535">Montagem</span><span class="sxs-lookup"><span data-stu-id="6a308-535">Assembly</span></span></td>
<td><span data-ttu-id="6a308-536">55</span><span class="sxs-lookup"><span data-stu-id="6a308-536">55</span></span></td>
<td><span data-ttu-id="6a308-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="6a308-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="6a308-538">275.00</span><span class="sxs-lookup"><span data-stu-id="6a308-538">275.00</span></span></td>
<td><span data-ttu-id="6a308-539">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-540">CC004</span><span class="sxs-lookup"><span data-stu-id="6a308-540">CC004</span></span></td>
<td><span data-ttu-id="6a308-541">Embalagem</span><span class="sxs-lookup"><span data-stu-id="6a308-541">Packaging</span></span></td>
<td><span data-ttu-id="6a308-542">10</span><span class="sxs-lookup"><span data-stu-id="6a308-542">10</span></span></td>
<td><span data-ttu-id="6a308-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="6a308-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="6a308-544">50,00</span><span class="sxs-lookup"><span data-stu-id="6a308-544">50.00</span></span></td>
<td><span data-ttu-id="6a308-545">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-546">CC002</span><span class="sxs-lookup"><span data-stu-id="6a308-546">CC002</span></span></td>
<td><span data-ttu-id="6a308-547">Finanças</span><span class="sxs-lookup"><span data-stu-id="6a308-547">Finance</span></span></td>
<td><span data-ttu-id="6a308-548">35</span><span class="sxs-lookup"><span data-stu-id="6a308-548">35</span></span></td>
<td><span data-ttu-id="6a308-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="6a308-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="6a308-550">436.00</span><span class="sxs-lookup"><span data-stu-id="6a308-550">436.00</span></span></td>
<td><span data-ttu-id="6a308-551">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-552">CC003</span><span class="sxs-lookup"><span data-stu-id="6a308-552">CC003</span></span></td>
<td><span data-ttu-id="6a308-553">Montagem</span><span class="sxs-lookup"><span data-stu-id="6a308-553">Assembly</span></span></td>
<td><span data-ttu-id="6a308-554">55</span><span class="sxs-lookup"><span data-stu-id="6a308-554">55</span></span></td>
<td><span data-ttu-id="6a308-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="6a308-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="6a308-556">685.14</span><span class="sxs-lookup"><span data-stu-id="6a308-556">685.14</span></span></td>
<td><span data-ttu-id="6a308-557">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-558">CC004</span><span class="sxs-lookup"><span data-stu-id="6a308-558">CC004</span></span></td>
<td><span data-ttu-id="6a308-559">Embalagem</span><span class="sxs-lookup"><span data-stu-id="6a308-559">Packaging</span></span></td>
<td><span data-ttu-id="6a308-560">10</span><span class="sxs-lookup"><span data-stu-id="6a308-560">10</span></span></td>
<td><span data-ttu-id="6a308-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="6a308-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="6a308-562">124.57</span><span class="sxs-lookup"><span data-stu-id="6a308-562">124.57</span></span></td>
<td><span data-ttu-id="6a308-563">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6a308-564">A tabela a seguir mostra o resultado quando os serviços financeiros são aplicados como base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="6a308-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6a308-565">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-565">Cost object</span></span></th>
<th><span data-ttu-id="6a308-566">Magnitude</span><span class="sxs-lookup"><span data-stu-id="6a308-566">Magnitude</span></span></th>
<th><span data-ttu-id="6a308-567">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="6a308-567">Allocation factor</span></span></th>
<th><span data-ttu-id="6a308-568">Valor</span><span class="sxs-lookup"><span data-stu-id="6a308-568">Amount</span></span></th>
<th><span data-ttu-id="6a308-569">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-570">CC003</span><span class="sxs-lookup"><span data-stu-id="6a308-570">CC003</span></span></td>
<td><span data-ttu-id="6a308-571">Montagem</span><span class="sxs-lookup"><span data-stu-id="6a308-571">Assembly</span></span></td>
<td><span data-ttu-id="6a308-572">65</span><span class="sxs-lookup"><span data-stu-id="6a308-572">65</span></span></td>
<td><span data-ttu-id="6a308-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="6a308-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="6a308-574">438.75</span><span class="sxs-lookup"><span data-stu-id="6a308-574">438.75</span></span></td>
<td><span data-ttu-id="6a308-575">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-576">CC004</span><span class="sxs-lookup"><span data-stu-id="6a308-576">CC004</span></span></td>
<td><span data-ttu-id="6a308-577">Embalagem</span><span class="sxs-lookup"><span data-stu-id="6a308-577">Packaging</span></span></td>
<td><span data-ttu-id="6a308-578">35</span><span class="sxs-lookup"><span data-stu-id="6a308-578">35</span></span></td>
<td><span data-ttu-id="6a308-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="6a308-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="6a308-580">236.25</span><span class="sxs-lookup"><span data-stu-id="6a308-580">236.25</span></span></td>
<td><span data-ttu-id="6a308-581">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-582">CC003</span><span class="sxs-lookup"><span data-stu-id="6a308-582">CC003</span></span></td>
<td><span data-ttu-id="6a308-583">Montagem</span><span class="sxs-lookup"><span data-stu-id="6a308-583">Assembly</span></span></td>
<td><span data-ttu-id="6a308-584">65</span><span class="sxs-lookup"><span data-stu-id="6a308-584">65</span></span></td>
<td><span data-ttu-id="6a308-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="6a308-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="6a308-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="6a308-586">5,297.69</span></span></td>
<td><span data-ttu-id="6a308-587">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-588">CC004</span><span class="sxs-lookup"><span data-stu-id="6a308-588">CC004</span></span></td>
<td><span data-ttu-id="6a308-589">Embalagem</span><span class="sxs-lookup"><span data-stu-id="6a308-589">Packaging</span></span></td>
<td><span data-ttu-id="6a308-590">35</span><span class="sxs-lookup"><span data-stu-id="6a308-590">35</span></span></td>
<td><span data-ttu-id="6a308-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="6a308-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="6a308-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="6a308-592">2,852.60</span></span></td>
<td><span data-ttu-id="6a308-593">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6a308-594">A tabela a seguir mostra o resultado quando os serviços de Montagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="6a308-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6a308-595">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-595">Cost object</span></span></th>
<th><span data-ttu-id="6a308-596">Magnitude</span><span class="sxs-lookup"><span data-stu-id="6a308-596">Magnitude</span></span></th>
<th><span data-ttu-id="6a308-597">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="6a308-597">Allocation factor</span></span></th>
<th><span data-ttu-id="6a308-598">Valor</span><span class="sxs-lookup"><span data-stu-id="6a308-598">Amount</span></span></th>
<th><span data-ttu-id="6a308-599">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-600">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="6a308-600">Prod 1</span></span></td>
<td><span data-ttu-id="6a308-601">Produto 1</span><span class="sxs-lookup"><span data-stu-id="6a308-601">Product 1</span></span></td>
<td><span data-ttu-id="6a308-602">60</span><span class="sxs-lookup"><span data-stu-id="6a308-602">60</span></span></td>
<td><span data-ttu-id="6a308-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="6a308-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="6a308-604">535.31</span><span class="sxs-lookup"><span data-stu-id="6a308-604">535.31</span></span></td>
<td><span data-ttu-id="6a308-605">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-606">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="6a308-606">Prod 2</span></span></td>
<td><span data-ttu-id="6a308-607">Produto 2</span><span class="sxs-lookup"><span data-stu-id="6a308-607">Product 2</span></span></td>
<td><span data-ttu-id="6a308-608">20</span><span class="sxs-lookup"><span data-stu-id="6a308-608">20</span></span></td>
<td><span data-ttu-id="6a308-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="6a308-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="6a308-610">178.44</span><span class="sxs-lookup"><span data-stu-id="6a308-610">178.44</span></span></td>
<td><span data-ttu-id="6a308-611">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-612">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="6a308-612">Prod 1</span></span></td>
<td><span data-ttu-id="6a308-613">Produto 1</span><span class="sxs-lookup"><span data-stu-id="6a308-613">Product 1</span></span></td>
<td><span data-ttu-id="6a308-614">60</span><span class="sxs-lookup"><span data-stu-id="6a308-614">60</span></span></td>
<td><span data-ttu-id="6a308-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="6a308-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="6a308-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="6a308-616">4,487.12</span></span></td>
<td><span data-ttu-id="6a308-617">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-618">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="6a308-618">Prod 2</span></span></td>
<td><span data-ttu-id="6a308-619">Produto 2</span><span class="sxs-lookup"><span data-stu-id="6a308-619">Product 2</span></span></td>
<td><span data-ttu-id="6a308-620">20</span><span class="sxs-lookup"><span data-stu-id="6a308-620">20</span></span></td>
<td><span data-ttu-id="6a308-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="6a308-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="6a308-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="6a308-622">1,495.71</span></span></td>
<td><span data-ttu-id="6a308-623">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6a308-624">A tabela a seguir mostra o resultado quando os serviços de Embalagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="6a308-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6a308-625">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-625">Cost object</span></span></th>
<th><span data-ttu-id="6a308-626">Magnitude</span><span class="sxs-lookup"><span data-stu-id="6a308-626">Magnitude</span></span></th>
<th><span data-ttu-id="6a308-627">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="6a308-627">Allocation factor</span></span></th>
<th><span data-ttu-id="6a308-628">Valor</span><span class="sxs-lookup"><span data-stu-id="6a308-628">Amount</span></span></th>
<th><span data-ttu-id="6a308-629">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-630">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="6a308-630">Prod 1</span></span></td>
<td><span data-ttu-id="6a308-631">Produto 1</span><span class="sxs-lookup"><span data-stu-id="6a308-631">Product 1</span></span></td>
<td><span data-ttu-id="6a308-632">80</span><span class="sxs-lookup"><span data-stu-id="6a308-632">80</span></span></td>
<td><span data-ttu-id="6a308-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="6a308-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="6a308-634">241.05</span><span class="sxs-lookup"><span data-stu-id="6a308-634">241.05</span></span></td>
<td><span data-ttu-id="6a308-635">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-636">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="6a308-636">Prod 2</span></span></td>
<td><span data-ttu-id="6a308-637">Produto 2</span><span class="sxs-lookup"><span data-stu-id="6a308-637">Product 2</span></span></td>
<td><span data-ttu-id="6a308-638">15</span><span class="sxs-lookup"><span data-stu-id="6a308-638">15</span></span></td>
<td><span data-ttu-id="6a308-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="6a308-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="6a308-640">45.20</span><span class="sxs-lookup"><span data-stu-id="6a308-640">45.20</span></span></td>
<td><span data-ttu-id="6a308-641">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-642">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="6a308-642">Prod 1</span></span></td>
<td><span data-ttu-id="6a308-643">Produto 1</span><span class="sxs-lookup"><span data-stu-id="6a308-643">Product 1</span></span></td>
<td><span data-ttu-id="6a308-644">80</span><span class="sxs-lookup"><span data-stu-id="6a308-644">80</span></span></td>
<td><span data-ttu-id="6a308-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="6a308-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="6a308-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="6a308-646">2,507.09</span></span></td>
<td><span data-ttu-id="6a308-647">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-648">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="6a308-648">Prod 2</span></span></td>
<td><span data-ttu-id="6a308-649">Produto 2</span><span class="sxs-lookup"><span data-stu-id="6a308-649">Product 2</span></span></td>
<td><span data-ttu-id="6a308-650">15</span><span class="sxs-lookup"><span data-stu-id="6a308-650">15</span></span></td>
<td><span data-ttu-id="6a308-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="6a308-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="6a308-652">470.08</span><span class="sxs-lookup"><span data-stu-id="6a308-652">470.08</span></span></td>
<td><span data-ttu-id="6a308-653">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="6a308-654">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="6a308-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="6a308-655">Diário</span><span class="sxs-lookup"><span data-stu-id="6a308-655">Journal</span></span></th>
<th><span data-ttu-id="6a308-656">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="6a308-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="6a308-657">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="6a308-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="6a308-658">Versão</span><span class="sxs-lookup"><span data-stu-id="6a308-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-659">00004</span><span class="sxs-lookup"><span data-stu-id="6a308-659">00004</span></span></td>
<td><span data-ttu-id="6a308-660">Diário de alocação de custos</span><span class="sxs-lookup"><span data-stu-id="6a308-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="6a308-661">fiscal</span><span class="sxs-lookup"><span data-stu-id="6a308-661">Fiscal</span></span></td>
<td><span data-ttu-id="6a308-662">2017</span><span class="sxs-lookup"><span data-stu-id="6a308-662">2017</span></span></td>
<td><span data-ttu-id="6a308-663">Período 1</span><span class="sxs-lookup"><span data-stu-id="6a308-663">Period 1</span></span></td>
<td><span data-ttu-id="6a308-664">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="6a308-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="6a308-665">Linhas do diário</span><span class="sxs-lookup"><span data-stu-id="6a308-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="6a308-666">Data contábil</span><span class="sxs-lookup"><span data-stu-id="6a308-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="6a308-667">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="6a308-668">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-668">Cost element</span></span></th>
<th><span data-ttu-id="6a308-669">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-669">Cost behavior</span></span></th>
<th><span data-ttu-id="6a308-670">Valor</span><span class="sxs-lookup"><span data-stu-id="6a308-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-671">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="6a308-672">CC001</span><span class="sxs-lookup"><span data-stu-id="6a308-672">CC001</span></span></td>
<td><span data-ttu-id="6a308-673">RH</span><span class="sxs-lookup"><span data-stu-id="6a308-673">HR</span></span></td>
<td><span data-ttu-id="6a308-674">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-674">10001</span></span></td>
<td><span data-ttu-id="6a308-675">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-675">Electricity</span></span></td>
<td><span data-ttu-id="6a308-676">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-676">Fixed cost</span></span></td>
<td><span data-ttu-id="6a308-677">500,00</span><span class="sxs-lookup"><span data-stu-id="6a308-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-678">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="6a308-679">CC001</span><span class="sxs-lookup"><span data-stu-id="6a308-679">CC001</span></span></td>
<td><span data-ttu-id="6a308-680">RH</span><span class="sxs-lookup"><span data-stu-id="6a308-680">HR</span></span></td>
<td><span data-ttu-id="6a308-681">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-681">10001</span></span></td>
<td><span data-ttu-id="6a308-682">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-682">Electricity</span></span></td>
<td><span data-ttu-id="6a308-683">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-683">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="6a308-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-685">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="6a308-686">CC002</span><span class="sxs-lookup"><span data-stu-id="6a308-686">CC002</span></span></td>
<td><span data-ttu-id="6a308-687">Finanças</span><span class="sxs-lookup"><span data-stu-id="6a308-687">Finance</span></span></td>
<td><span data-ttu-id="6a308-688">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-688">10001</span></span></td>
<td><span data-ttu-id="6a308-689">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-689">Electricity</span></span></td>
<td><span data-ttu-id="6a308-690">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-690">Fixed cost</span></span></td>
<td><span data-ttu-id="6a308-691">675.00</span><span class="sxs-lookup"><span data-stu-id="6a308-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-692">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="6a308-693">CC002</span><span class="sxs-lookup"><span data-stu-id="6a308-693">CC002</span></span></td>
<td><span data-ttu-id="6a308-694">Finanças</span><span class="sxs-lookup"><span data-stu-id="6a308-694">Finance</span></span></td>
<td><span data-ttu-id="6a308-695">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-695">10001</span></span></td>
<td><span data-ttu-id="6a308-696">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-696">Electricity</span></span></td>
<td><span data-ttu-id="6a308-697">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-697">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="6a308-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-699">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="6a308-700">CC003</span><span class="sxs-lookup"><span data-stu-id="6a308-700">CC003</span></span></td>
<td><span data-ttu-id="6a308-701">Montagem</span><span class="sxs-lookup"><span data-stu-id="6a308-701">Assembly</span></span></td>
<td><span data-ttu-id="6a308-702">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-702">10001</span></span></td>
<td><span data-ttu-id="6a308-703">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-703">Electricity</span></span></td>
<td><span data-ttu-id="6a308-704">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-704">Fixed cost</span></span></td>
<td><span data-ttu-id="6a308-705">713.75</span><span class="sxs-lookup"><span data-stu-id="6a308-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-706">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="6a308-707">CC003</span><span class="sxs-lookup"><span data-stu-id="6a308-707">CC003</span></span></td>
<td><span data-ttu-id="6a308-708">Montagem</span><span class="sxs-lookup"><span data-stu-id="6a308-708">Assembly</span></span></td>
<td><span data-ttu-id="6a308-709">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-709">10001</span></span></td>
<td><span data-ttu-id="6a308-710">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-710">Electricity</span></span></td>
<td><span data-ttu-id="6a308-711">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-711">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="6a308-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-713">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="6a308-714">CC003</span><span class="sxs-lookup"><span data-stu-id="6a308-714">CC003</span></span></td>
<td><span data-ttu-id="6a308-715">Embalagem</span><span class="sxs-lookup"><span data-stu-id="6a308-715">Packaging</span></span></td>
<td><span data-ttu-id="6a308-716">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-716">10001</span></span></td>
<td><span data-ttu-id="6a308-717">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-717">Electricity</span></span></td>
<td><span data-ttu-id="6a308-718">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-718">Fixed cost</span></span></td>
<td><span data-ttu-id="6a308-719">286.25</span><span class="sxs-lookup"><span data-stu-id="6a308-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-720">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="6a308-721">CC003</span><span class="sxs-lookup"><span data-stu-id="6a308-721">CC003</span></span></td>
<td><span data-ttu-id="6a308-722">Embalagem</span><span class="sxs-lookup"><span data-stu-id="6a308-722">Packaging</span></span></td>
<td><span data-ttu-id="6a308-723">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-723">10001</span></span></td>
<td><span data-ttu-id="6a308-724">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-724">Electricity</span></span></td>
<td><span data-ttu-id="6a308-725">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-725">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="6a308-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-727">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="6a308-728">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="6a308-728">Prod 1</span></span></td>
<td><span data-ttu-id="6a308-729">Produto 1</span><span class="sxs-lookup"><span data-stu-id="6a308-729">Product 1</span></span></td>
<td><span data-ttu-id="6a308-730">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-730">10001</span></span></td>
<td><span data-ttu-id="6a308-731">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-731">Electricity</span></span></td>
<td><span data-ttu-id="6a308-732">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-732">Fixed cost</span></span></td>
<td><span data-ttu-id="6a308-733">776.36</span><span class="sxs-lookup"><span data-stu-id="6a308-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-734">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="6a308-735">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="6a308-735">Prod 1</span></span></td>
<td><span data-ttu-id="6a308-736">Produto 1</span><span class="sxs-lookup"><span data-stu-id="6a308-736">Product 1</span></span></td>
<td><span data-ttu-id="6a308-737">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-737">10001</span></span></td>
<td><span data-ttu-id="6a308-738">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-738">Electricity</span></span></td>
<td><span data-ttu-id="6a308-739">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-739">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="6a308-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-741">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="6a308-742">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="6a308-742">Prod 2</span></span></td>
<td><span data-ttu-id="6a308-743">Produto 1</span><span class="sxs-lookup"><span data-stu-id="6a308-743">Product 1</span></span></td>
<td><span data-ttu-id="6a308-744">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-744">10001</span></span></td>
<td><span data-ttu-id="6a308-745">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-745">Electricity</span></span></td>
<td><span data-ttu-id="6a308-746">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-746">Fixed cost</span></span></td>
<td><span data-ttu-id="6a308-747">223.64</span><span class="sxs-lookup"><span data-stu-id="6a308-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-748">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="6a308-749">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="6a308-749">Prod 2</span></span></td>
<td><span data-ttu-id="6a308-750">Produto 1</span><span class="sxs-lookup"><span data-stu-id="6a308-750">Product 1</span></span></td>
<td><span data-ttu-id="6a308-751">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-751">10001</span></span></td>
<td><span data-ttu-id="6a308-752">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-752">Electricity</span></span></td>
<td><span data-ttu-id="6a308-753">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-753">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="6a308-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="6a308-755">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="6a308-756">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="6a308-757">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-757">Cost element</span></span></th>
<th><span data-ttu-id="6a308-758">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-758">Cost behavior</span></span></th>
<th><span data-ttu-id="6a308-759">Valor</span><span class="sxs-lookup"><span data-stu-id="6a308-759">Amount</span></span></th>
<th><span data-ttu-id="6a308-760">Data contábil</span><span class="sxs-lookup"><span data-stu-id="6a308-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="6a308-761">CC001</span><span class="sxs-lookup"><span data-stu-id="6a308-761">CC001</span></span></td>
<td><span data-ttu-id="6a308-762">RH</span><span class="sxs-lookup"><span data-stu-id="6a308-762">HR</span></span></td>
<td><span data-ttu-id="6a308-763">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-763">10001</span></span></td>
<td><span data-ttu-id="6a308-764">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-764">Electricity</span></span></td>
<td><span data-ttu-id="6a308-765">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-765">Fixed cost</span></span></td>
<td><span data-ttu-id="6a308-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="6a308-766">-500.00</span></span></td>
<td><span data-ttu-id="6a308-767">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-768">CC002</span><span class="sxs-lookup"><span data-stu-id="6a308-768">CC002</span></span></td>
<td><span data-ttu-id="6a308-769">Finanças</span><span class="sxs-lookup"><span data-stu-id="6a308-769">Finance</span></span></td>
<td><span data-ttu-id="6a308-770">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-770">10001</span></span></td>
<td><span data-ttu-id="6a308-771">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-771">Electricity</span></span></td>
<td><span data-ttu-id="6a308-772">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-772">Fixed cost</span></span></td>
<td><span data-ttu-id="6a308-773">175.00</span><span class="sxs-lookup"><span data-stu-id="6a308-773">175.00</span></span></td>
<td><span data-ttu-id="6a308-774">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-775">CC003</span><span class="sxs-lookup"><span data-stu-id="6a308-775">CC003</span></span></td>
<td><span data-ttu-id="6a308-776">Montagem</span><span class="sxs-lookup"><span data-stu-id="6a308-776">Assembly</span></span></td>
<td><span data-ttu-id="6a308-777">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-777">10001</span></span></td>
<td><span data-ttu-id="6a308-778">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-778">Electricity</span></span></td>
<td><span data-ttu-id="6a308-779">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-779">Fixed cost</span></span></td>
<td><span data-ttu-id="6a308-780">275.00</span><span class="sxs-lookup"><span data-stu-id="6a308-780">275.00</span></span></td>
<td><span data-ttu-id="6a308-781">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-782">CC004</span><span class="sxs-lookup"><span data-stu-id="6a308-782">CC004</span></span></td>
<td><span data-ttu-id="6a308-783">Embalagem</span><span class="sxs-lookup"><span data-stu-id="6a308-783">Packaging</span></span></td>
<td><span data-ttu-id="6a308-784">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-784">10001</span></span></td>
<td><span data-ttu-id="6a308-785">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-785">Electricity</span></span></td>
<td><span data-ttu-id="6a308-786">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-786">Fixed cost</span></span></td>
<td><span data-ttu-id="6a308-787">50,00</span><span class="sxs-lookup"><span data-stu-id="6a308-787">50,00</span></span></td>
<td><span data-ttu-id="6a308-788">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-789">CC001</span><span class="sxs-lookup"><span data-stu-id="6a308-789">CC001</span></span></td>
<td><span data-ttu-id="6a308-790">RH</span><span class="sxs-lookup"><span data-stu-id="6a308-790">HR</span></span></td>
<td><span data-ttu-id="6a308-791">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-791">10001</span></span></td>
<td><span data-ttu-id="6a308-792">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-792">Electricity</span></span></td>
<td><span data-ttu-id="6a308-793">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-793">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="6a308-794">-1,245.71</span></span></td>
<td><span data-ttu-id="6a308-795">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-796">CC002</span><span class="sxs-lookup"><span data-stu-id="6a308-796">CC002</span></span></td>
<td><span data-ttu-id="6a308-797">Finanças</span><span class="sxs-lookup"><span data-stu-id="6a308-797">Finance</span></span></td>
<td><span data-ttu-id="6a308-798">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-798">10001</span></span></td>
<td><span data-ttu-id="6a308-799">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-799">Electricity</span></span></td>
<td><span data-ttu-id="6a308-800">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-800">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-801">436.00</span><span class="sxs-lookup"><span data-stu-id="6a308-801">436.00</span></span></td>
<td><span data-ttu-id="6a308-802">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-803">CC003</span><span class="sxs-lookup"><span data-stu-id="6a308-803">CC003</span></span></td>
<td><span data-ttu-id="6a308-804">Montagem</span><span class="sxs-lookup"><span data-stu-id="6a308-804">Assembly</span></span></td>
<td><span data-ttu-id="6a308-805">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-805">10001</span></span></td>
<td><span data-ttu-id="6a308-806">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-806">Electricity</span></span></td>
<td><span data-ttu-id="6a308-807">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-807">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-808">685.14</span><span class="sxs-lookup"><span data-stu-id="6a308-808">685.14</span></span></td>
<td><span data-ttu-id="6a308-809">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-810">CC004</span><span class="sxs-lookup"><span data-stu-id="6a308-810">CC004</span></span></td>
<td><span data-ttu-id="6a308-811">Embalagem</span><span class="sxs-lookup"><span data-stu-id="6a308-811">Packaging</span></span></td>
<td><span data-ttu-id="6a308-812">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-812">10001</span></span></td>
<td><span data-ttu-id="6a308-813">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-813">Electricity</span></span></td>
<td><span data-ttu-id="6a308-814">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-814">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-815">124.57</span><span class="sxs-lookup"><span data-stu-id="6a308-815">124.57</span></span></td>
<td><span data-ttu-id="6a308-816">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-817">CC002</span><span class="sxs-lookup"><span data-stu-id="6a308-817">CC002</span></span></td>
<td><span data-ttu-id="6a308-818">Finanças</span><span class="sxs-lookup"><span data-stu-id="6a308-818">Finance</span></span></td>
<td><span data-ttu-id="6a308-819">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-819">10001</span></span></td>
<td><span data-ttu-id="6a308-820">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-820">Electricity</span></span></td>
<td><span data-ttu-id="6a308-821">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-821">Fixed cost</span></span></td>
<td><span data-ttu-id="6a308-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="6a308-822">-675.00</span></span></td>
<td><span data-ttu-id="6a308-823">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-824">CC003</span><span class="sxs-lookup"><span data-stu-id="6a308-824">CC003</span></span></td>
<td><span data-ttu-id="6a308-825">Montagem</span><span class="sxs-lookup"><span data-stu-id="6a308-825">Assembly</span></span></td>
<td><span data-ttu-id="6a308-826">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-826">10001</span></span></td>
<td><span data-ttu-id="6a308-827">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-827">Electricity</span></span></td>
<td><span data-ttu-id="6a308-828">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-828">Fixed cost</span></span></td>
<td><span data-ttu-id="6a308-829">438.75</span><span class="sxs-lookup"><span data-stu-id="6a308-829">438.75</span></span></td>
<td><span data-ttu-id="6a308-830">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-831">CC004</span><span class="sxs-lookup"><span data-stu-id="6a308-831">CC004</span></span></td>
<td><span data-ttu-id="6a308-832">Embalagem</span><span class="sxs-lookup"><span data-stu-id="6a308-832">Packaging</span></span></td>
<td><span data-ttu-id="6a308-833">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-833">10001</span></span></td>
<td><span data-ttu-id="6a308-834">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-834">Electricity</span></span></td>
<td><span data-ttu-id="6a308-835">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-835">Fixed cost</span></span></td>
<td><span data-ttu-id="6a308-836">236.25</span><span class="sxs-lookup"><span data-stu-id="6a308-836">236.25</span></span></td>
<td><span data-ttu-id="6a308-837">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-838">CC002</span><span class="sxs-lookup"><span data-stu-id="6a308-838">CC002</span></span></td>
<td><span data-ttu-id="6a308-839">Finanças</span><span class="sxs-lookup"><span data-stu-id="6a308-839">Finance</span></span></td>
<td><span data-ttu-id="6a308-840">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-840">10001</span></span></td>
<td><span data-ttu-id="6a308-841">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-841">Electricity</span></span></td>
<td><span data-ttu-id="6a308-842">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-842">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="6a308-843">-8,150.29</span></span></td>
<td><span data-ttu-id="6a308-844">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-845">CC003</span><span class="sxs-lookup"><span data-stu-id="6a308-845">CC003</span></span></td>
<td><span data-ttu-id="6a308-846">Montagem</span><span class="sxs-lookup"><span data-stu-id="6a308-846">Assembly</span></span></td>
<td><span data-ttu-id="6a308-847">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-847">10001</span></span></td>
<td><span data-ttu-id="6a308-848">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-848">Electricity</span></span></td>
<td><span data-ttu-id="6a308-849">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-849">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="6a308-850">5,297.69</span></span></td>
<td><span data-ttu-id="6a308-851">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-852">CC004</span><span class="sxs-lookup"><span data-stu-id="6a308-852">CC004</span></span></td>
<td><span data-ttu-id="6a308-853">Embalagem</span><span class="sxs-lookup"><span data-stu-id="6a308-853">Packaging</span></span></td>
<td><span data-ttu-id="6a308-854">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-854">10001</span></span></td>
<td><span data-ttu-id="6a308-855">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-855">Electricity</span></span></td>
<td><span data-ttu-id="6a308-856">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-856">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="6a308-857">2,852.60</span></span></td>
<td><span data-ttu-id="6a308-858">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-859">CC003</span><span class="sxs-lookup"><span data-stu-id="6a308-859">CC003</span></span></td>
<td><span data-ttu-id="6a308-860">Montagem</span><span class="sxs-lookup"><span data-stu-id="6a308-860">Assembly</span></span></td>
<td><span data-ttu-id="6a308-861">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-861">10001</span></span></td>
<td><span data-ttu-id="6a308-862">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-862">Electricity</span></span></td>
<td><span data-ttu-id="6a308-863">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-863">Fixed cost</span></span></td>
<td><span data-ttu-id="6a308-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="6a308-864">-713.75</span></span></td>
<td><span data-ttu-id="6a308-865">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-866">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="6a308-866">Prod 1</span></span></td>
<td><span data-ttu-id="6a308-867">Produto 1</span><span class="sxs-lookup"><span data-stu-id="6a308-867">Product 1</span></span></td>
<td><span data-ttu-id="6a308-868">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-868">10001</span></span></td>
<td><span data-ttu-id="6a308-869">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-869">Electricity</span></span></td>
<td><span data-ttu-id="6a308-870">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-870">Fixed cost</span></span></td>
<td><span data-ttu-id="6a308-871">535.31</span><span class="sxs-lookup"><span data-stu-id="6a308-871">535.31</span></span></td>
<td><span data-ttu-id="6a308-872">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-873">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="6a308-873">Prod 2</span></span></td>
<td><span data-ttu-id="6a308-874">Produto 2</span><span class="sxs-lookup"><span data-stu-id="6a308-874">Product 2</span></span></td>
<td><span data-ttu-id="6a308-875">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-875">10001</span></span></td>
<td><span data-ttu-id="6a308-876">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-876">Electricity</span></span></td>
<td><span data-ttu-id="6a308-877">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-877">Fixed cost</span></span></td>
<td><span data-ttu-id="6a308-878">178.44</span><span class="sxs-lookup"><span data-stu-id="6a308-878">178.44</span></span></td>
<td><span data-ttu-id="6a308-879">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-880">CC003</span><span class="sxs-lookup"><span data-stu-id="6a308-880">CC003</span></span></td>
<td><span data-ttu-id="6a308-881">Montagem</span><span class="sxs-lookup"><span data-stu-id="6a308-881">Assembly</span></span></td>
<td><span data-ttu-id="6a308-882">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-882">10001</span></span></td>
<td><span data-ttu-id="6a308-883">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-883">Electricity</span></span></td>
<td><span data-ttu-id="6a308-884">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-884">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="6a308-885">-5,982.83</span></span></td>
<td><span data-ttu-id="6a308-886">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-887">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="6a308-887">Prod 1</span></span></td>
<td><span data-ttu-id="6a308-888">Produto 1</span><span class="sxs-lookup"><span data-stu-id="6a308-888">Product 1</span></span></td>
<td><span data-ttu-id="6a308-889">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-889">10001</span></span></td>
<td><span data-ttu-id="6a308-890">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-890">Electricity</span></span></td>
<td><span data-ttu-id="6a308-891">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-891">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="6a308-892">4,487.12</span></span></td>
<td><span data-ttu-id="6a308-893">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-894">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="6a308-894">Prod 2</span></span></td>
<td><span data-ttu-id="6a308-895">Produto 2</span><span class="sxs-lookup"><span data-stu-id="6a308-895">Product 2</span></span></td>
<td><span data-ttu-id="6a308-896">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-896">10001</span></span></td>
<td><span data-ttu-id="6a308-897">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-897">Electricity</span></span></td>
<td><span data-ttu-id="6a308-898">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-898">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="6a308-899">1,495.71</span></span></td>
<td><span data-ttu-id="6a308-900">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-901">CC003</span><span class="sxs-lookup"><span data-stu-id="6a308-901">CC003</span></span></td>
<td><span data-ttu-id="6a308-902">Montagem</span><span class="sxs-lookup"><span data-stu-id="6a308-902">Assembly</span></span></td>
<td><span data-ttu-id="6a308-903">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-903">10001</span></span></td>
<td><span data-ttu-id="6a308-904">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-904">Electricity</span></span></td>
<td><span data-ttu-id="6a308-905">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-905">Fixed cost</span></span></td>
<td><span data-ttu-id="6a308-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="6a308-906">-286.25</span></span></td>
<td><span data-ttu-id="6a308-907">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-908">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="6a308-908">Prod 1</span></span></td>
<td><span data-ttu-id="6a308-909">Produto 1</span><span class="sxs-lookup"><span data-stu-id="6a308-909">Product 1</span></span></td>
<td><span data-ttu-id="6a308-910">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-910">10001</span></span></td>
<td><span data-ttu-id="6a308-911">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-911">Electricity</span></span></td>
<td><span data-ttu-id="6a308-912">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-912">Fixed cost</span></span></td>
<td><span data-ttu-id="6a308-913">241.05</span><span class="sxs-lookup"><span data-stu-id="6a308-913">241.05</span></span></td>
<td><span data-ttu-id="6a308-914">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-915">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="6a308-915">Prod 2</span></span></td>
<td><span data-ttu-id="6a308-916">Produto 2</span><span class="sxs-lookup"><span data-stu-id="6a308-916">Product 2</span></span></td>
<td><span data-ttu-id="6a308-917">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-917">10001</span></span></td>
<td><span data-ttu-id="6a308-918">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-918">Electricity</span></span></td>
<td><span data-ttu-id="6a308-919">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-919">Fixed cost</span></span></td>
<td><span data-ttu-id="6a308-920">45.20</span><span class="sxs-lookup"><span data-stu-id="6a308-920">45.20</span></span></td>
<td><span data-ttu-id="6a308-921">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-922">CC003</span><span class="sxs-lookup"><span data-stu-id="6a308-922">CC003</span></span></td>
<td><span data-ttu-id="6a308-923">Montagem</span><span class="sxs-lookup"><span data-stu-id="6a308-923">Assembly</span></span></td>
<td><span data-ttu-id="6a308-924">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-924">10001</span></span></td>
<td><span data-ttu-id="6a308-925">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-925">Electricity</span></span></td>
<td><span data-ttu-id="6a308-926">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-926">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="6a308-927">-2,977.17</span></span></td>
<td><span data-ttu-id="6a308-928">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-929">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="6a308-929">Prod 1</span></span></td>
<td><span data-ttu-id="6a308-930">Produto 1</span><span class="sxs-lookup"><span data-stu-id="6a308-930">Product 1</span></span></td>
<td><span data-ttu-id="6a308-931">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-931">10001</span></span></td>
<td><span data-ttu-id="6a308-932">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-932">Electricity</span></span></td>
<td><span data-ttu-id="6a308-933">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-933">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="6a308-934">2,507.09</span></span></td>
<td><span data-ttu-id="6a308-935">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="6a308-936">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="6a308-936">Prod 2</span></span></td>
<td><span data-ttu-id="6a308-937">Produto 2</span><span class="sxs-lookup"><span data-stu-id="6a308-937">Product 2</span></span></td>
<td><span data-ttu-id="6a308-938">10001</span><span class="sxs-lookup"><span data-stu-id="6a308-938">10001</span></span></td>
<td><span data-ttu-id="6a308-939">eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-939">Electricity</span></span></td>
<td><span data-ttu-id="6a308-940">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-940">Variable cost</span></span></td>
<td><span data-ttu-id="6a308-941">470.08</span><span class="sxs-lookup"><span data-stu-id="6a308-941">470.08</span></span></td>
<td><span data-ttu-id="6a308-942">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="6a308-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="6a308-943">Conclusão</span><span class="sxs-lookup"><span data-stu-id="6a308-943">Conclusion</span></span>
<span data-ttu-id="6a308-944">Na contabilidade financeira, um custo de 10,000.00 para a eletricidade é lançado para um ID fictício de centro de custos.</span><span class="sxs-lookup"><span data-stu-id="6a308-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="6a308-945">Portanto, os contadores de custo saberão que esses custos devem ser alocados.</span><span class="sxs-lookup"><span data-stu-id="6a308-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="6a308-946">Na contabilização de custo, os custos fluem nas unidades organizacionais e nos níveis, com base nas políticas e regras que são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="6a308-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="6a308-947">Cada custo foi associado a uma base de alocação que fornece a melhor apuração para a alocação de custos.</span><span class="sxs-lookup"><span data-stu-id="6a308-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="6a308-948">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="6a308-949">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="6a308-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="6a308-950">Total</span><span class="sxs-lookup"><span data-stu-id="6a308-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="6a308-951">CC099</span><span class="sxs-lookup"><span data-stu-id="6a308-951">CC099</span></span></th>
<th><span data-ttu-id="6a308-952">CC001</span><span class="sxs-lookup"><span data-stu-id="6a308-952">CC001</span></span></th>
<th><span data-ttu-id="6a308-953">CC002</span><span class="sxs-lookup"><span data-stu-id="6a308-953">CC002</span></span></th>
<th><span data-ttu-id="6a308-954">CC003</span><span class="sxs-lookup"><span data-stu-id="6a308-954">CC003</span></span></th>
<th><span data-ttu-id="6a308-955">CC004</span><span class="sxs-lookup"><span data-stu-id="6a308-955">CC004</span></span></th>
<th><span data-ttu-id="6a308-956">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="6a308-956">Proj 1</span></span></th>
<th><span data-ttu-id="6a308-957">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="6a308-957">Proj 2</span></span></th>
<th><span data-ttu-id="6a308-958">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="6a308-958">Prod 1</span></span></th>
<th><span data-ttu-id="6a308-959">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="6a308-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="6a308-960">10001 Eletricidade</span><span class="sxs-lookup"><span data-stu-id="6a308-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="6a308-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="6a308-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="6a308-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="6a308-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="6a308-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="6a308-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="6a308-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="6a308-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="6a308-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="6a308-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="6a308-970">Não classificado</span><span class="sxs-lookup"><span data-stu-id="6a308-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-971">0,00</span><span class="sxs-lookup"><span data-stu-id="6a308-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="6a308-972">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="6a308-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-973">0,00</span><span class="sxs-lookup"><span data-stu-id="6a308-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-974">0,00</span><span class="sxs-lookup"><span data-stu-id="6a308-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-975">0,00</span><span class="sxs-lookup"><span data-stu-id="6a308-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-976">0,00</span><span class="sxs-lookup"><span data-stu-id="6a308-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-977">0,00</span><span class="sxs-lookup"><span data-stu-id="6a308-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="6a308-978">776.36</span><span class="sxs-lookup"><span data-stu-id="6a308-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-979">223.64</span><span class="sxs-lookup"><span data-stu-id="6a308-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="6a308-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="6a308-981">Custo variável</span><span class="sxs-lookup"><span data-stu-id="6a308-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-982">000</span><span class="sxs-lookup"><span data-stu-id="6a308-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-983">0,00</span><span class="sxs-lookup"><span data-stu-id="6a308-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-984">0,00</span><span class="sxs-lookup"><span data-stu-id="6a308-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-985">0,00</span><span class="sxs-lookup"><span data-stu-id="6a308-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-986">0,00</span><span class="sxs-lookup"><span data-stu-id="6a308-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-987">30,00</span><span class="sxs-lookup"><span data-stu-id="6a308-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-988">10,00</span><span class="sxs-lookup"><span data-stu-id="6a308-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="6a308-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="6a308-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="6a308-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="6a308-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="6a308-992">Esse tópico mostra como um elemento de custo principal, 10001 Eletricidade flui pelos objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="6a308-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="6a308-993">Portanto, esse custo geral indireto é alocado no nível mais baixo na organização.</span><span class="sxs-lookup"><span data-stu-id="6a308-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="6a308-994">Em outras palavras, os objetos de custo no nível mais baixo assumem o custo.</span><span class="sxs-lookup"><span data-stu-id="6a308-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="6a308-995">Se você exigir um fluxo visual de custo entre objetos de custo, é possível usar as regras de política de acúmulo de custos para visualizar o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="6a308-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="6a308-996">Para obter mais informações, consulte [Política de acúmulo de custo e cálculo de custos indiretos](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="6a308-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



