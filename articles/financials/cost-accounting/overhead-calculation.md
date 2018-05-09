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
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 2f37b5957974c927ade698fea65de7e3807d998a
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="overhead-calculation"></a><span data-ttu-id="95312-103">Cálculo de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="95312-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="95312-104">Este tópico descreve processos comuns para calcular e alocar os custos gerais indiretos.</span><span class="sxs-lookup"><span data-stu-id="95312-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="95312-105">Definição de termo</span><span class="sxs-lookup"><span data-stu-id="95312-105">Term definition</span></span>
---------------

<span data-ttu-id="95312-106">Os custos gerais indiretos são aqueles que foram incorridos para realizar um negócio, mas não podem ser diretamente atribuídos a qualquer atividade comercial, produto ou serviço específico.</span><span class="sxs-lookup"><span data-stu-id="95312-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="95312-107">Os custos gerais indiretos fornecem suporte crítico para geração de atividades produtivas.</span><span class="sxs-lookup"><span data-stu-id="95312-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="95312-108">Eis alguns exemplos de custos gerais:</span><span class="sxs-lookup"><span data-stu-id="95312-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="95312-109">Aluguel</span><span class="sxs-lookup"><span data-stu-id="95312-109">Rent</span></span>
-   <span data-ttu-id="95312-110">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-110">Electricity</span></span>
-   <span data-ttu-id="95312-111">Salários administrativos</span><span class="sxs-lookup"><span data-stu-id="95312-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="95312-112">Visão geral do cálculo de custos gerais indiretos</span><span class="sxs-lookup"><span data-stu-id="95312-112">Overhead calculation overview</span></span>
<span data-ttu-id="95312-113">O cálculo de custos gerais indiretos executa as políticas de contabilização de custos na ordem correta.</span><span class="sxs-lookup"><span data-stu-id="95312-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="95312-114">Você pode executar o cálculo de custos gerais indiretos várias vezes para o mesmo período fiscal, se as políticas de contabilidade de custo foram modificadas ou foram detectados erros específicos.</span><span class="sxs-lookup"><span data-stu-id="95312-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="95312-115">Cada execução do cálculo de custos gerais indiretos é armazenada e recebe um ID exclusivo de versão que permite comparar os cálculos em várias versões.</span><span class="sxs-lookup"><span data-stu-id="95312-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="95312-116">As entradas de custo que o cálculo de custos indiretos gera recebe uma data contábil.</span><span class="sxs-lookup"><span data-stu-id="95312-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="95312-117">Essa data contábil corresponde à data final do período fiscal que é usada no cálculo.</span><span class="sxs-lookup"><span data-stu-id="95312-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="95312-118">A ID exclusiva de versão consiste nos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="95312-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="95312-119">Tipo de versão</span><span class="sxs-lookup"><span data-stu-id="95312-119">Version type</span></span>
-   <span data-ttu-id="95312-120">Data e hora</span><span class="sxs-lookup"><span data-stu-id="95312-120">Date and time</span></span>
-   <span data-ttu-id="95312-121">Razão de contabilização de custos</span><span class="sxs-lookup"><span data-stu-id="95312-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="95312-122">Ano fiscal</span><span class="sxs-lookup"><span data-stu-id="95312-122">Fiscal year</span></span>
-   <span data-ttu-id="95312-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="95312-123">Fiscal period</span></span>

<span data-ttu-id="95312-124">O cálculo de custos gerais indiretos é executado independentemente da versão.</span><span class="sxs-lookup"><span data-stu-id="95312-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="95312-125">Portanto, você pode calcular a versão de orçamento antes da versão atual.</span><span class="sxs-lookup"><span data-stu-id="95312-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="95312-126">O cálculo de custos gerais indiretos consiste em quatro etapas, conforme mostrado na ilustração.</span><span class="sxs-lookup"><span data-stu-id="95312-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="95312-127">Em cada etapa, um cabeçalho de diário é criado com entradas de diário.</span><span class="sxs-lookup"><span data-stu-id="95312-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="95312-128">Esse cabeçalho de diário mantém dados de entrada para cada etapa de cálculo.</span><span class="sxs-lookup"><span data-stu-id="95312-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="95312-129">As políticas e regras são aplicadas a cada linha do diário e as entradas de custo são geradas como saídas.</span><span class="sxs-lookup"><span data-stu-id="95312-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="95312-130">Portanto, você sempre terá rastreabilidade total.</span><span class="sxs-lookup"><span data-stu-id="95312-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="95312-131">[![Cálculo de custos gerais indiretos](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="95312-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="95312-132">Calcular e alocar os custos gerais indiretos de Eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="95312-133">Na contabilidade financeira, alguns custos, como eletricidade, são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="95312-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="95312-134">Portanto, a visão administrativa detalhada não é fornecida para a contabilização de custo.</span><span class="sxs-lookup"><span data-stu-id="95312-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="95312-135">Na contabilização de custo, para fornecer a visão administrativa correta em todas as unidades organizacionais e níveis, os custos devem passar pelas unidades organizacionais.</span><span class="sxs-lookup"><span data-stu-id="95312-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="95312-136">Este fluxo deve ser baseado em qualquer um registro exato do consumo ou de uma previsão justa.</span><span class="sxs-lookup"><span data-stu-id="95312-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="95312-137">Na contabilidade, um custo de eletricidade pode ser lançado, conforme mostrado na tabela.</span><span class="sxs-lookup"><span data-stu-id="95312-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="95312-138">Data contábil</span><span class="sxs-lookup"><span data-stu-id="95312-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="95312-139">Centro de custos</span><span class="sxs-lookup"><span data-stu-id="95312-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="95312-140">Conta principal</span><span class="sxs-lookup"><span data-stu-id="95312-140">Main account</span></span></th>
<th><span data-ttu-id="95312-141">Valor na moeda contábil</span><span class="sxs-lookup"><span data-stu-id="95312-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-142">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="95312-143">CC099</span><span class="sxs-lookup"><span data-stu-id="95312-143">CC099</span></span></td>
<td><span data-ttu-id="95312-144">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="95312-144">Default cost center</span></span></td>
<td><span data-ttu-id="95312-145">10001</span><span class="sxs-lookup"><span data-stu-id="95312-145">10001</span></span></td>
<td><span data-ttu-id="95312-146">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-146">Electricity</span></span></td>
<td><span data-ttu-id="95312-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="95312-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="95312-148">Etapa 1: Processar o cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="95312-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="95312-149">Por padrão, quando as entradas de custo previsto são importadas de dados de origem, elas recebem a classificação de comportamento de custo **Não classificado** na Contabilidade de custos.</span><span class="sxs-lookup"><span data-stu-id="95312-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="95312-150">Aplicando regras da política de comportamento de custo, é possível reclassificar entradas de custo como **Custo fixo** ou **Custo variável**.</span><span class="sxs-lookup"><span data-stu-id="95312-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="95312-151">Definir a regra de custo de comportamento</span><span class="sxs-lookup"><span data-stu-id="95312-151">Define the cost behavior rule</span></span>

<span data-ttu-id="95312-152">Em alguns casos, parte do custo é uma taxa fixa e o custos pendente é baseado no consumo.</span><span class="sxs-lookup"><span data-stu-id="95312-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="95312-153">Geralmente, as contas de eletricidade correspondem a esta definição.</span><span class="sxs-lookup"><span data-stu-id="95312-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="95312-154">Após você pagar uma taxa fixa específica, você paga por consumo, por hora de quilowatt (Kwh).</span><span class="sxs-lookup"><span data-stu-id="95312-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="95312-155">Por exemplo, se a taxa de custo fixa for 1.000.00, veja aqui como a regra de comportamento de custo é definida:</span><span class="sxs-lookup"><span data-stu-id="95312-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="95312-156">Valor fixo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="95312-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="95312-157">0 &lt;= 1.000,00 = Fixo</span><span class="sxs-lookup"><span data-stu-id="95312-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="95312-158">1000.01 &lt; N = Variável</span><span class="sxs-lookup"><span data-stu-id="95312-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="95312-159">Diário</span><span class="sxs-lookup"><span data-stu-id="95312-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="95312-160">Diário</span><span class="sxs-lookup"><span data-stu-id="95312-160">Journal</span></span></th>
<th><span data-ttu-id="95312-161">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="95312-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="95312-162">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="95312-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="95312-163">Versão</span><span class="sxs-lookup"><span data-stu-id="95312-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-164">00001</span><span class="sxs-lookup"><span data-stu-id="95312-164">00001</span></span></td>
<td><span data-ttu-id="95312-165">Diário de cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="95312-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="95312-166">fiscal</span><span class="sxs-lookup"><span data-stu-id="95312-166">Fiscal</span></span></td>
<td><span data-ttu-id="95312-167">2017</span><span class="sxs-lookup"><span data-stu-id="95312-167">2017</span></span></td>
<td><span data-ttu-id="95312-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="95312-168">Period 1</span></span></td>
<td><span data-ttu-id="95312-169">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="95312-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="95312-170">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="95312-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="95312-171">Data contábil</span><span class="sxs-lookup"><span data-stu-id="95312-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="95312-172">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="95312-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="95312-173">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="95312-173">Cost element</span></span></th>
<th><span data-ttu-id="95312-174">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="95312-174">Cost behavior</span></span></th>
<th><span data-ttu-id="95312-175">Valor</span><span class="sxs-lookup"><span data-stu-id="95312-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-176">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="95312-177">CC099</span><span class="sxs-lookup"><span data-stu-id="95312-177">CC099</span></span></td>
<td><span data-ttu-id="95312-178">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="95312-178">Default cost center</span></span></td>
<td><span data-ttu-id="95312-179">10001</span><span class="sxs-lookup"><span data-stu-id="95312-179">10001</span></span></td>
<td><span data-ttu-id="95312-180">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-180">Electricity</span></span></td>
<td><span data-ttu-id="95312-181">Não classificado</span><span class="sxs-lookup"><span data-stu-id="95312-181">Unclassified</span></span></td>
<td><span data-ttu-id="95312-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="95312-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="95312-183">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="95312-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="95312-184">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="95312-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="95312-185">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="95312-185">Cost element</span></span></th>
<th><span data-ttu-id="95312-186">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="95312-186">Cost behavior</span></span></th>
<th><span data-ttu-id="95312-187">Valor</span><span class="sxs-lookup"><span data-stu-id="95312-187">Amount</span></span></th>
<th><span data-ttu-id="95312-188">Data contábil</span><span class="sxs-lookup"><span data-stu-id="95312-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-189">CC099</span><span class="sxs-lookup"><span data-stu-id="95312-189">CC099</span></span></td>
<td><span data-ttu-id="95312-190">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="95312-190">Default cost center</span></span></td>
<td><span data-ttu-id="95312-191">10001</span><span class="sxs-lookup"><span data-stu-id="95312-191">10001</span></span></td>
<td><span data-ttu-id="95312-192">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-192">Electricity</span></span></td>
<td><span data-ttu-id="95312-193">Não classificado</span><span class="sxs-lookup"><span data-stu-id="95312-193">Unclassified</span></span></td>
<td><span data-ttu-id="95312-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="95312-194">10,000.00</span></span></td>
<td><span data-ttu-id="95312-195">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-196">CC099</span><span class="sxs-lookup"><span data-stu-id="95312-196">CC099</span></span></td>
<td><span data-ttu-id="95312-197">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="95312-197">Default cost center</span></span></td>
<td><span data-ttu-id="95312-198">10001</span><span class="sxs-lookup"><span data-stu-id="95312-198">10001</span></span></td>
<td><span data-ttu-id="95312-199">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-199">Electricity</span></span></td>
<td><span data-ttu-id="95312-200">Não classificado</span><span class="sxs-lookup"><span data-stu-id="95312-200">Unclassified</span></span></td>
<td><span data-ttu-id="95312-201">-10.000,00</span><span class="sxs-lookup"><span data-stu-id="95312-201">-10,000.00</span></span></td>
<td><span data-ttu-id="95312-202">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-203">CC099</span><span class="sxs-lookup"><span data-stu-id="95312-203">CC099</span></span></td>
<td><span data-ttu-id="95312-204">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="95312-204">Default cost center</span></span></td>
<td><span data-ttu-id="95312-205">10001</span><span class="sxs-lookup"><span data-stu-id="95312-205">10001</span></span></td>
<td><span data-ttu-id="95312-206">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-206">Electricity</span></span></td>
<td><span data-ttu-id="95312-207">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-207">Fixed cost</span></span></td>
<td><span data-ttu-id="95312-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="95312-208">1,000.00</span></span></td>
<td><span data-ttu-id="95312-209">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-210">CC099</span><span class="sxs-lookup"><span data-stu-id="95312-210">CC099</span></span></td>
<td><span data-ttu-id="95312-211">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="95312-211">Default cost center</span></span></td>
<td><span data-ttu-id="95312-212">10001</span><span class="sxs-lookup"><span data-stu-id="95312-212">10001</span></span></td>
<td><span data-ttu-id="95312-213">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-213">Electricity</span></span></td>
<td><span data-ttu-id="95312-214">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-214">Variable cost</span></span></td>
<td><span data-ttu-id="95312-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="95312-215">9,000.00</span></span></td>
<td><span data-ttu-id="95312-216">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="95312-217">Para obter informações detalhadas sobre o comportamento de custo, consulte a política de comportamento de custo.</span><span class="sxs-lookup"><span data-stu-id="95312-217">For detailed information about cost behavior, see Cost behavior policy.</span></span> <span data-ttu-id="95312-218">(Observe que este tópico não está incluído, mas estará em breve).</span><span class="sxs-lookup"><span data-stu-id="95312-218">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="95312-219">Etapa 2: Processar o cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="95312-219">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="95312-220">A distribuição de custos é usada para redistribuir custo de um objeto de custo a um ou mais outros objetos de custo, aplicando uma base de alocação relevante.</span><span class="sxs-lookup"><span data-stu-id="95312-220">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="95312-221">A distribuição de custos e a alocação de custo são diferentes na distribuição de custos, sempre que ocorrer em nível de elemento de custo principal do custo original.</span><span class="sxs-lookup"><span data-stu-id="95312-221">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="95312-222">Definir a regra de distribuição de custos</span><span class="sxs-lookup"><span data-stu-id="95312-222">Define the cost distribution rule</span></span>

<span data-ttu-id="95312-223">Na contabilidade financeira, os custos de eletricidade geralmente são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="95312-223">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="95312-224">Na contabilização de custo, esta abordagem não é suficientemente detalhada.</span><span class="sxs-lookup"><span data-stu-id="95312-224">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="95312-225">O custo variável deve ser distribuído a objetos de custos individuais com base justa.</span><span class="sxs-lookup"><span data-stu-id="95312-225">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="95312-226">A base de alocação mais lógica é o consumo de eletricidade (Kwh).</span><span class="sxs-lookup"><span data-stu-id="95312-226">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="95312-227">O membro da dimensão estatística que é chamado Eletricidade é criado e o consumo de eletricidade é registrado.</span><span class="sxs-lookup"><span data-stu-id="95312-227">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="95312-228">Por padrão, todos os membros estatísticos da dimensão se tornam disponíveis como bases de alocação.</span><span class="sxs-lookup"><span data-stu-id="95312-228">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="95312-229">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="95312-229">Cost object</span></span></th>
<th><span data-ttu-id="95312-230">Kwh</span><span class="sxs-lookup"><span data-stu-id="95312-230">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-231">CC001</span><span class="sxs-lookup"><span data-stu-id="95312-231">CC001</span></span></td>
<td><span data-ttu-id="95312-232">RH</span><span class="sxs-lookup"><span data-stu-id="95312-232">HR</span></span></td>
<td><span data-ttu-id="95312-233">1.000</span><span class="sxs-lookup"><span data-stu-id="95312-233">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-234">CC002</span><span class="sxs-lookup"><span data-stu-id="95312-234">CC002</span></span></td>
<td><span data-ttu-id="95312-235">Finanças</span><span class="sxs-lookup"><span data-stu-id="95312-235">Finance</span></span></td>
<td><span data-ttu-id="95312-236">6,000</span><span class="sxs-lookup"><span data-stu-id="95312-236">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-237">CC003</span><span class="sxs-lookup"><span data-stu-id="95312-237">CC003</span></span></td>
<td><span data-ttu-id="95312-238">Montagem</span><span class="sxs-lookup"><span data-stu-id="95312-238">Assembly</span></span></td>
<td><span data-ttu-id="95312-239">0</span><span class="sxs-lookup"><span data-stu-id="95312-239">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="95312-240">A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação para custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="95312-240">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="95312-241">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="95312-241">Cost object</span></span></th>
<th><span data-ttu-id="95312-242">Magnitude</span><span class="sxs-lookup"><span data-stu-id="95312-242">Magnitude</span></span></th>
<th><span data-ttu-id="95312-243">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="95312-243">Allocation factor</span></span></th>
<th><span data-ttu-id="95312-244">Valor</span><span class="sxs-lookup"><span data-stu-id="95312-244">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-245">CC001</span><span class="sxs-lookup"><span data-stu-id="95312-245">CC001</span></span></td>
<td><span data-ttu-id="95312-246">RH</span><span class="sxs-lookup"><span data-stu-id="95312-246">HR</span></span></td>
<td><span data-ttu-id="95312-247">1.000</span><span class="sxs-lookup"><span data-stu-id="95312-247">1,000</span></span></td>
<td><span data-ttu-id="95312-248">(1.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="95312-248">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="95312-249">1,285.71</span><span class="sxs-lookup"><span data-stu-id="95312-249">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-250">CC002</span><span class="sxs-lookup"><span data-stu-id="95312-250">CC002</span></span></td>
<td><span data-ttu-id="95312-251">Finanças</span><span class="sxs-lookup"><span data-stu-id="95312-251">Finance</span></span></td>
<td><span data-ttu-id="95312-252">6,000</span><span class="sxs-lookup"><span data-stu-id="95312-252">6,000</span></span></td>
<td><span data-ttu-id="95312-253">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="95312-253">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="95312-254">7,714.29</span><span class="sxs-lookup"><span data-stu-id="95312-254">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-255">CC003</span><span class="sxs-lookup"><span data-stu-id="95312-255">CC003</span></span></td>
<td><span data-ttu-id="95312-256">Montagem</span><span class="sxs-lookup"><span data-stu-id="95312-256">Assembly</span></span></td>
<td><span data-ttu-id="95312-257">0</span><span class="sxs-lookup"><span data-stu-id="95312-257">0</span></span></td>
<td><span data-ttu-id="95312-258">(0 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="95312-258">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="95312-259">0,00</span><span class="sxs-lookup"><span data-stu-id="95312-259">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="95312-260">Os custos fixos devem ser distribuídos igualmente a objetos de custo individuais que têm a eletricidade consumida.</span><span class="sxs-lookup"><span data-stu-id="95312-260">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="95312-261">Você pode obter esse resultado usando o membro estatístico de dimensão de eletricidade em uma base e alocação da fórmula: (Eletricidade &gt; 0,00) A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação de custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="95312-261">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="95312-262">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="95312-262">Cost object</span></span></th>
<th><span data-ttu-id="95312-263">Fórmula</span><span class="sxs-lookup"><span data-stu-id="95312-263">Formula</span></span></th>
<th><span data-ttu-id="95312-264">Magnitude</span><span class="sxs-lookup"><span data-stu-id="95312-264">Magnitude</span></span></th>
<th><span data-ttu-id="95312-265">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="95312-265">Allocation factor</span></span></th>
<th><span data-ttu-id="95312-266">Valor</span><span class="sxs-lookup"><span data-stu-id="95312-266">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-267">CC001</span><span class="sxs-lookup"><span data-stu-id="95312-267">CC001</span></span></td>
<td><span data-ttu-id="95312-268">RH</span><span class="sxs-lookup"><span data-stu-id="95312-268">HR</span></span></td>
<td><span data-ttu-id="95312-269">(1.000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="95312-269">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="95312-270">1</span><span class="sxs-lookup"><span data-stu-id="95312-270">1</span></span></td>
<td><span data-ttu-id="95312-271">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="95312-271">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="95312-272">500,00</span><span class="sxs-lookup"><span data-stu-id="95312-272">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-273">CC002</span><span class="sxs-lookup"><span data-stu-id="95312-273">CC002</span></span></td>
<td><span data-ttu-id="95312-274">Finanças</span><span class="sxs-lookup"><span data-stu-id="95312-274">Finance</span></span></td>
<td><span data-ttu-id="95312-275">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="95312-275">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="95312-276">1</span><span class="sxs-lookup"><span data-stu-id="95312-276">1</span></span></td>
<td><span data-ttu-id="95312-277">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="95312-277">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="95312-278">500,00</span><span class="sxs-lookup"><span data-stu-id="95312-278">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-279">CC003</span><span class="sxs-lookup"><span data-stu-id="95312-279">CC003</span></span></td>
<td><span data-ttu-id="95312-280">Montagem</span><span class="sxs-lookup"><span data-stu-id="95312-280">Assembly</span></span></td>
<td><span data-ttu-id="95312-281">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="95312-281">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="95312-282">0</span><span class="sxs-lookup"><span data-stu-id="95312-282">0</span></span></td>
<td><span data-ttu-id="95312-283">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="95312-283">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="95312-284">0,00</span><span class="sxs-lookup"><span data-stu-id="95312-284">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="95312-285">Diário</span><span class="sxs-lookup"><span data-stu-id="95312-285">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="95312-286">Diário</span><span class="sxs-lookup"><span data-stu-id="95312-286">Journal</span></span></th>
<th><span data-ttu-id="95312-287">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="95312-287">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="95312-288">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="95312-288">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="95312-289">Versão</span><span class="sxs-lookup"><span data-stu-id="95312-289">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-290">00002</span><span class="sxs-lookup"><span data-stu-id="95312-290">00002</span></span></td>
<td><span data-ttu-id="95312-291">Diário de cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="95312-291">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="95312-292">fiscal</span><span class="sxs-lookup"><span data-stu-id="95312-292">Fiscal</span></span></td>
<td><span data-ttu-id="95312-293">2017</span><span class="sxs-lookup"><span data-stu-id="95312-293">2017</span></span></td>
<td><span data-ttu-id="95312-294">Período 1</span><span class="sxs-lookup"><span data-stu-id="95312-294">Period 1</span></span></td>
<td><span data-ttu-id="95312-295">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="95312-295">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="95312-296">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="95312-296">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="95312-297">Data contábil</span><span class="sxs-lookup"><span data-stu-id="95312-297">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="95312-298">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="95312-298">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="95312-299">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="95312-299">Cost element</span></span></th>
<th><span data-ttu-id="95312-300">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="95312-300">Cost behavior</span></span></th>
<th><span data-ttu-id="95312-301">Valor</span><span class="sxs-lookup"><span data-stu-id="95312-301">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-302">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-302">January 31, 2017</span></span></td>
<td><span data-ttu-id="95312-303">CC099</span><span class="sxs-lookup"><span data-stu-id="95312-303">CC099</span></span></td>
<td><span data-ttu-id="95312-304">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="95312-304">Default cost center</span></span></td>
<td><span data-ttu-id="95312-305">10001</span><span class="sxs-lookup"><span data-stu-id="95312-305">10001</span></span></td>
<td><span data-ttu-id="95312-306">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-306">Electricity</span></span></td>
<td><span data-ttu-id="95312-307">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-307">Fixed cost</span></span></td>
<td><span data-ttu-id="95312-308">1.000,00</span><span class="sxs-lookup"><span data-stu-id="95312-308">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-309">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-309">January 31, 2017</span></span></td>
<td><span data-ttu-id="95312-310">CC099</span><span class="sxs-lookup"><span data-stu-id="95312-310">CC099</span></span></td>
<td><span data-ttu-id="95312-311">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="95312-311">Default cost center</span></span></td>
<td><span data-ttu-id="95312-312">10001</span><span class="sxs-lookup"><span data-stu-id="95312-312">10001</span></span></td>
<td><span data-ttu-id="95312-313">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-313">Electricity</span></span></td>
<td><span data-ttu-id="95312-314">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-314">Variable cost</span></span></td>
<td><span data-ttu-id="95312-315">9,000.00</span><span class="sxs-lookup"><span data-stu-id="95312-315">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="95312-316">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="95312-316">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="95312-317">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="95312-317">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="95312-318">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="95312-318">Cost element</span></span></th>
<th><span data-ttu-id="95312-319">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="95312-319">Cost behavior</span></span></th>
<th><span data-ttu-id="95312-320">Valor</span><span class="sxs-lookup"><span data-stu-id="95312-320">Amount</span></span></th>
<th><span data-ttu-id="95312-321">Data contábil</span><span class="sxs-lookup"><span data-stu-id="95312-321">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-322">CC099</span><span class="sxs-lookup"><span data-stu-id="95312-322">CC099</span></span></td>
<td><span data-ttu-id="95312-323">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="95312-323">Default cost center</span></span></td>
<td><span data-ttu-id="95312-324">10001</span><span class="sxs-lookup"><span data-stu-id="95312-324">10001</span></span></td>
<td><span data-ttu-id="95312-325">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-325">Electricity</span></span></td>
<td><span data-ttu-id="95312-326">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-326">Fixed cost</span></span></td>
<td><span data-ttu-id="95312-327">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="95312-327">-1,000.00</span></span></td>
<td><span data-ttu-id="95312-328">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-328">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-329">CC001</span><span class="sxs-lookup"><span data-stu-id="95312-329">CC001</span></span></td>
<td><span data-ttu-id="95312-330">RH</span><span class="sxs-lookup"><span data-stu-id="95312-330">HR</span></span></td>
<td><span data-ttu-id="95312-331">10001</span><span class="sxs-lookup"><span data-stu-id="95312-331">10001</span></span></td>
<td><span data-ttu-id="95312-332">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-332">Electricity</span></span></td>
<td><span data-ttu-id="95312-333">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-333">Fixed cost</span></span></td>
<td><span data-ttu-id="95312-334">500,00</span><span class="sxs-lookup"><span data-stu-id="95312-334">500.00</span></span></td>
<td><span data-ttu-id="95312-335">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-335">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-336">CC002</span><span class="sxs-lookup"><span data-stu-id="95312-336">CC002</span></span></td>
<td><span data-ttu-id="95312-337">Finanças</span><span class="sxs-lookup"><span data-stu-id="95312-337">Finance</span></span></td>
<td><span data-ttu-id="95312-338">10001</span><span class="sxs-lookup"><span data-stu-id="95312-338">10001</span></span></td>
<td><span data-ttu-id="95312-339">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-339">Electricity</span></span></td>
<td><span data-ttu-id="95312-340">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-340">Fixed cost</span></span></td>
<td><span data-ttu-id="95312-341">500,00</span><span class="sxs-lookup"><span data-stu-id="95312-341">500.00</span></span></td>
<td><span data-ttu-id="95312-342">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-342">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-343">CC099</span><span class="sxs-lookup"><span data-stu-id="95312-343">CC099</span></span></td>
<td><span data-ttu-id="95312-344">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="95312-344">Default cost center</span></span></td>
<td><span data-ttu-id="95312-345">10001</span><span class="sxs-lookup"><span data-stu-id="95312-345">10001</span></span></td>
<td><span data-ttu-id="95312-346">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-346">Electricity</span></span></td>
<td><span data-ttu-id="95312-347">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-347">Variable cost</span></span></td>
<td><span data-ttu-id="95312-348">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="95312-348">-9,000.00</span></span></td>
<td><span data-ttu-id="95312-349">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-349">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-350">CC001</span><span class="sxs-lookup"><span data-stu-id="95312-350">CC001</span></span></td>
<td><span data-ttu-id="95312-351">RH</span><span class="sxs-lookup"><span data-stu-id="95312-351">HR</span></span></td>
<td><span data-ttu-id="95312-352">10001</span><span class="sxs-lookup"><span data-stu-id="95312-352">10001</span></span></td>
<td><span data-ttu-id="95312-353">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-353">Electricity</span></span></td>
<td><span data-ttu-id="95312-354">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-354">Variable cost</span></span></td>
<td><span data-ttu-id="95312-355">1,285.71</span><span class="sxs-lookup"><span data-stu-id="95312-355">1,285.71</span></span></td>
<td><span data-ttu-id="95312-356">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-356">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-357">CC002</span><span class="sxs-lookup"><span data-stu-id="95312-357">CC002</span></span></td>
<td><span data-ttu-id="95312-358">Finanças</span><span class="sxs-lookup"><span data-stu-id="95312-358">Finance</span></span></td>
<td><span data-ttu-id="95312-359">10001</span><span class="sxs-lookup"><span data-stu-id="95312-359">10001</span></span></td>
<td><span data-ttu-id="95312-360">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-360">Electricity</span></span></td>
<td><span data-ttu-id="95312-361">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-361">Variable cost</span></span></td>
<td><span data-ttu-id="95312-362">7,714.29</span><span class="sxs-lookup"><span data-stu-id="95312-362">7,714.29</span></span></td>
<td><span data-ttu-id="95312-363">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-363">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="95312-364">Para obter informações detalhadas sobre bases de alocação e distribuição de custos, consulte a política de custo e as bases de alocação.</span><span class="sxs-lookup"><span data-stu-id="95312-364">For detailed information about cost distribution and allocation bases, see Cost distribution policy and Allocation bases.</span></span> <span data-ttu-id="95312-365">(Observe que este tópico não está incluído, mas estará em breve).</span><span class="sxs-lookup"><span data-stu-id="95312-365">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="95312-366">Etapa 3: Processar o cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="95312-366">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="95312-367">A taxa de custos indiretos é usada para cobrar um ou mais objetos de custos específicos.</span><span class="sxs-lookup"><span data-stu-id="95312-367">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="95312-368">O encargo se baseia em uma taxa de custo predeterminada e a magnitude da básica de alocação atribuída.</span><span class="sxs-lookup"><span data-stu-id="95312-368">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="95312-369">Defina a taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="95312-369">Define the overhead rate</span></span>

<span data-ttu-id="95312-370">O objeto de custo CC001 HR contribui para um conjunto de projetos internos.</span><span class="sxs-lookup"><span data-stu-id="95312-370">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="95312-371">Um membro de dimensão estatística que é chamado de projetos de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="95312-371">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="95312-372">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="95312-372">Cost object</span></span></th>
<th><span data-ttu-id="95312-373">Horas</span><span class="sxs-lookup"><span data-stu-id="95312-373">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-374">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="95312-374">Proj 1</span></span></td>
<td><span data-ttu-id="95312-375">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="95312-375">Project 1</span></span></td>
<td><span data-ttu-id="95312-376">3</span><span class="sxs-lookup"><span data-stu-id="95312-376">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-377">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="95312-377">Proj 2</span></span></td>
<td><span data-ttu-id="95312-378">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="95312-378">Project 2</span></span></td>
<td><span data-ttu-id="95312-379">1</span><span class="sxs-lookup"><span data-stu-id="95312-379">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="95312-380">Uma taxa de custo predeterminada da contribuição de projetos de custo foi definida.</span><span class="sxs-lookup"><span data-stu-id="95312-380">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="95312-381">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="95312-381">Cost object</span></span></th>
<th><span data-ttu-id="95312-382">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="95312-382">Cost element</span></span></th>
<th><span data-ttu-id="95312-383">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="95312-383">Cost behavior</span></span></th>
<th><span data-ttu-id="95312-384">Unidades</span><span class="sxs-lookup"><span data-stu-id="95312-384">Units</span></span></th>
<th><span data-ttu-id="95312-385">Taxa</span><span class="sxs-lookup"><span data-stu-id="95312-385">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-386">CC001</span><span class="sxs-lookup"><span data-stu-id="95312-386">CC001</span></span></td>
<td><span data-ttu-id="95312-387">RH</span><span class="sxs-lookup"><span data-stu-id="95312-387">HR</span></span></td>
<td><span data-ttu-id="95312-388">10001</span><span class="sxs-lookup"><span data-stu-id="95312-388">10001</span></span></td>
<td><span data-ttu-id="95312-389">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-389">Variable cost</span></span></td>
<td><span data-ttu-id="95312-390">1</span><span class="sxs-lookup"><span data-stu-id="95312-390">1</span></span></td>
<td><span data-ttu-id="95312-391">10</span><span class="sxs-lookup"><span data-stu-id="95312-391">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="95312-392">A tabela a seguir mostra o resultado quando projetos de RH são aplicados como base de alocação.</span><span class="sxs-lookup"><span data-stu-id="95312-392">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="95312-393">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="95312-393">Cost object</span></span></th>
<th><span data-ttu-id="95312-394">Magnitude</span><span class="sxs-lookup"><span data-stu-id="95312-394">Magnitude</span></span></th>
<th><span data-ttu-id="95312-395">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="95312-395">Cost element</span></span></th>
<th><span data-ttu-id="95312-396">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="95312-396">Allocation factor</span></span></th>
<th><span data-ttu-id="95312-397">Valor</span><span class="sxs-lookup"><span data-stu-id="95312-397">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-398">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="95312-398">Proj 1</span></span></td>
<td><span data-ttu-id="95312-399">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="95312-399">Project 1</span></span></td>
<td><span data-ttu-id="95312-400">3</span><span class="sxs-lookup"><span data-stu-id="95312-400">3</span></span></td>
<td><span data-ttu-id="95312-401">10001</span><span class="sxs-lookup"><span data-stu-id="95312-401">10001</span></span></td>
<td><span data-ttu-id="95312-402">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="95312-402">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="95312-403">30,00</span><span class="sxs-lookup"><span data-stu-id="95312-403">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-404">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="95312-404">Proj 2</span></span></td>
<td><span data-ttu-id="95312-405">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="95312-405">Project 2</span></span></td>
<td><span data-ttu-id="95312-406">1</span><span class="sxs-lookup"><span data-stu-id="95312-406">1</span></span></td>
<td><span data-ttu-id="95312-407">10001</span><span class="sxs-lookup"><span data-stu-id="95312-407">10001</span></span></td>
<td><span data-ttu-id="95312-408">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="95312-408">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="95312-409">10,00</span><span class="sxs-lookup"><span data-stu-id="95312-409">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="95312-410">Diário</span><span class="sxs-lookup"><span data-stu-id="95312-410">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="95312-411">Diário</span><span class="sxs-lookup"><span data-stu-id="95312-411">Journal</span></span></th>
<th><span data-ttu-id="95312-412">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="95312-412">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="95312-413">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="95312-413">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="95312-414">Versão</span><span class="sxs-lookup"><span data-stu-id="95312-414">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-415">00003</span><span class="sxs-lookup"><span data-stu-id="95312-415">00003</span></span></td>
<td><span data-ttu-id="95312-416">Diário de cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="95312-416">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="95312-417">fiscal</span><span class="sxs-lookup"><span data-stu-id="95312-417">Fiscal</span></span></td>
<td><span data-ttu-id="95312-418">2017</span><span class="sxs-lookup"><span data-stu-id="95312-418">2017</span></span></td>
<td><span data-ttu-id="95312-419">Período 1</span><span class="sxs-lookup"><span data-stu-id="95312-419">Period 1</span></span></td>
<td><span data-ttu-id="95312-420">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="95312-420">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="95312-421">Entradas de diário (As entradas de diário para cálculo da taxa de custos indiretos)</span><span class="sxs-lookup"><span data-stu-id="95312-421">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="95312-422">Data contábil</span><span class="sxs-lookup"><span data-stu-id="95312-422">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="95312-423">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="95312-423">Cost object</span></span></th>
<th><span data-ttu-id="95312-424">Magnitude</span><span class="sxs-lookup"><span data-stu-id="95312-424">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-425">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-425">January 31, 2017</span></span></td>
<td><span data-ttu-id="95312-426">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="95312-426">Proj 1</span></span></td>
<td><span data-ttu-id="95312-427">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="95312-427">Internal Proj 1</span></span></td>
<td><span data-ttu-id="95312-428">3,00</span><span class="sxs-lookup"><span data-stu-id="95312-428">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-429">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-429">January 31, 2017</span></span></td>
<td><span data-ttu-id="95312-430">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="95312-430">Proj 2</span></span></td>
<td><span data-ttu-id="95312-431">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="95312-431">Internal Proj 2</span></span></td>
<td><span data-ttu-id="95312-432">1.00</span><span class="sxs-lookup"><span data-stu-id="95312-432">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="95312-433">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="95312-433">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="95312-434">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="95312-434">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="95312-435">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="95312-435">Cost element</span></span></th>
<th><span data-ttu-id="95312-436">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="95312-436">Cost behavior</span></span></th>
<th><span data-ttu-id="95312-437">Valor</span><span class="sxs-lookup"><span data-stu-id="95312-437">Amount</span></span></th>
<th><span data-ttu-id="95312-438">Data contábil</span><span class="sxs-lookup"><span data-stu-id="95312-438">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-439">CC0001</span><span class="sxs-lookup"><span data-stu-id="95312-439">CC0001</span></span></td>
<td><span data-ttu-id="95312-440">RH</span><span class="sxs-lookup"><span data-stu-id="95312-440">HR</span></span></td>
<td><span data-ttu-id="95312-441">10001</span><span class="sxs-lookup"><span data-stu-id="95312-441">10001</span></span></td>
<td><span data-ttu-id="95312-442">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-442">Electricity</span></span></td>
<td><span data-ttu-id="95312-443">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-443">Variable cost</span></span></td>
<td><span data-ttu-id="95312-444">-30,00</span><span class="sxs-lookup"><span data-stu-id="95312-444">-30.00</span></span></td>
<td><span data-ttu-id="95312-445">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-445">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-446">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="95312-446">Proj 1</span></span></td>
<td><span data-ttu-id="95312-447">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="95312-447">Internal Proj 1</span></span></td>
<td><span data-ttu-id="95312-448">10001</span><span class="sxs-lookup"><span data-stu-id="95312-448">10001</span></span></td>
<td><span data-ttu-id="95312-449">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-449">Electricity</span></span></td>
<td><span data-ttu-id="95312-450">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-450">Variable cost</span></span></td>
<td><span data-ttu-id="95312-451">30,00</span><span class="sxs-lookup"><span data-stu-id="95312-451">30.00</span></span></td>
<td><span data-ttu-id="95312-452">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-452">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-453">CC001</span><span class="sxs-lookup"><span data-stu-id="95312-453">CC001</span></span></td>
<td><span data-ttu-id="95312-454">RH</span><span class="sxs-lookup"><span data-stu-id="95312-454">HR</span></span></td>
<td><span data-ttu-id="95312-455">10001</span><span class="sxs-lookup"><span data-stu-id="95312-455">10001</span></span></td>
<td><span data-ttu-id="95312-456">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-456">Electricity</span></span></td>
<td><span data-ttu-id="95312-457">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-457">Variable cost</span></span></td>
<td><span data-ttu-id="95312-458">-10,00</span><span class="sxs-lookup"><span data-stu-id="95312-458">-10.00</span></span></td>
<td><span data-ttu-id="95312-459">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-459">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-460">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="95312-460">Proj 2</span></span></td>
<td><span data-ttu-id="95312-461">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="95312-461">Internal Proj 2</span></span></td>
<td><span data-ttu-id="95312-462">10001</span><span class="sxs-lookup"><span data-stu-id="95312-462">10001</span></span></td>
<td><span data-ttu-id="95312-463">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-463">Electricity</span></span></td>
<td><span data-ttu-id="95312-464">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-464">Variable cost</span></span></td>
<td><span data-ttu-id="95312-465">10,00</span><span class="sxs-lookup"><span data-stu-id="95312-465">10.00</span></span></td>
<td><span data-ttu-id="95312-466">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-466">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="95312-467">Para obter informações detalhadas sobre a política de taxa de custos indiretos, consulte a política de taxa de custos indiretos e as bases de alocação.</span><span class="sxs-lookup"><span data-stu-id="95312-467">For detailed information about overhead rate policy, see Overhead rate policy and Allocation bases.</span></span> <span data-ttu-id="95312-468">(Observe que este tópico não está incluído, mas estará em breve).</span><span class="sxs-lookup"><span data-stu-id="95312-468">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="95312-469">Etapa 4: Processar o cálculo de alocação de custo</span><span class="sxs-lookup"><span data-stu-id="95312-469">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="95312-470">A alocação é usada para alocar o saldo de um objeto de custo a outros objetos de custo pela aplicação de uma base de alocação.</span><span class="sxs-lookup"><span data-stu-id="95312-470">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="95312-471">O Finance and Operations oferece suporte ao método de alocação recíproco.</span><span class="sxs-lookup"><span data-stu-id="95312-471">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="95312-472">No método de alocação recíproco, os serviços mútuos que os objetos de custo auxiliar trocam são totalmente reconhecidos.</span><span class="sxs-lookup"><span data-stu-id="95312-472">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="95312-473">O sistema determina automaticamente a ordem correta realizar as alocações.</span><span class="sxs-lookup"><span data-stu-id="95312-473">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="95312-474">O saldo de um objeto de custo é alocado por uma base de alocação única.</span><span class="sxs-lookup"><span data-stu-id="95312-474">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="95312-475">As alocações entre as dimensões de objetos de custo e os respectivos membros são suportadas.</span><span class="sxs-lookup"><span data-stu-id="95312-475">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="95312-476">A ordem de alocação é controlada pela unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="95312-476">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="95312-477">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="95312-477">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="95312-478">Defina a alocação de custo</span><span class="sxs-lookup"><span data-stu-id="95312-478">Define the cost allocation</span></span>

<span data-ttu-id="95312-479">Aqui está um exemplo simples que explica como você pode rastrear o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="95312-479">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="95312-480">O objeto de custo previsto CC001 HR contribui a vários objetos de custo previsto.</span><span class="sxs-lookup"><span data-stu-id="95312-480">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="95312-481">Um membro de dimensão estatística que é chamado de serviços de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="95312-481">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="95312-482">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="95312-482">Cost object</span></span></th>
<th><span data-ttu-id="95312-483">Serviços de RH</span><span class="sxs-lookup"><span data-stu-id="95312-483">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-484">CC002</span><span class="sxs-lookup"><span data-stu-id="95312-484">CC002</span></span></td>
<td><span data-ttu-id="95312-485">Finanças</span><span class="sxs-lookup"><span data-stu-id="95312-485">Finance</span></span></td>
<td><span data-ttu-id="95312-486">35</span><span class="sxs-lookup"><span data-stu-id="95312-486">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-487">CC003</span><span class="sxs-lookup"><span data-stu-id="95312-487">CC003</span></span></td>
<td><span data-ttu-id="95312-488">Montagem</span><span class="sxs-lookup"><span data-stu-id="95312-488">Assembly</span></span></td>
<td><span data-ttu-id="95312-489">55</span><span class="sxs-lookup"><span data-stu-id="95312-489">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-490">CC004</span><span class="sxs-lookup"><span data-stu-id="95312-490">CC004</span></span></td>
<td><span data-ttu-id="95312-491">Embalagem</span><span class="sxs-lookup"><span data-stu-id="95312-491">Packaging</span></span></td>
<td><span data-ttu-id="95312-492">10</span><span class="sxs-lookup"><span data-stu-id="95312-492">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="95312-493">O objeto de custo CC002 Finanças contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="95312-493">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="95312-494">Um membro de dimensão estatística que é chamado de serviços de Finanças foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="95312-494">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="95312-495">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="95312-495">Cost object</span></span></th>
<th><span data-ttu-id="95312-496">Serviços financeiros</span><span class="sxs-lookup"><span data-stu-id="95312-496">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-497">CC003</span><span class="sxs-lookup"><span data-stu-id="95312-497">CC003</span></span></td>
<td><span data-ttu-id="95312-498">Montagem</span><span class="sxs-lookup"><span data-stu-id="95312-498">Assembly</span></span></td>
<td><span data-ttu-id="95312-499">65</span><span class="sxs-lookup"><span data-stu-id="95312-499">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-500">CC004</span><span class="sxs-lookup"><span data-stu-id="95312-500">CC004</span></span></td>
<td><span data-ttu-id="95312-501">Embalagem</span><span class="sxs-lookup"><span data-stu-id="95312-501">Packaging</span></span></td>
<td><span data-ttu-id="95312-502">35</span><span class="sxs-lookup"><span data-stu-id="95312-502">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="95312-503">O objeto de custo CC003 Montagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="95312-503">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="95312-504">Um membro de dimensão estatística que é chamado de serviços de Montagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="95312-504">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="95312-505">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="95312-505">Cost object</span></span></th>
<th><span data-ttu-id="95312-506">Serviços de montagem (horas)</span><span class="sxs-lookup"><span data-stu-id="95312-506">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-507">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="95312-507">Prod 1</span></span></td>
<td><span data-ttu-id="95312-508">Produto 1</span><span class="sxs-lookup"><span data-stu-id="95312-508">Product 1</span></span></td>
<td><span data-ttu-id="95312-509">60</span><span class="sxs-lookup"><span data-stu-id="95312-509">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-510">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="95312-510">Prod 2</span></span></td>
<td><span data-ttu-id="95312-511">Produto 2</span><span class="sxs-lookup"><span data-stu-id="95312-511">Product 2</span></span></td>
<td><span data-ttu-id="95312-512">20</span><span class="sxs-lookup"><span data-stu-id="95312-512">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="95312-513">O objeto de custo CC004 Embalagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="95312-513">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="95312-514">Um membro de dimensão estatística que é chamado de serviços de Embalagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="95312-514">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="95312-515">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="95312-515">Cost object</span></span></th>
<th><span data-ttu-id="95312-516">Serviços de embalagem (horas)</span><span class="sxs-lookup"><span data-stu-id="95312-516">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-517">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="95312-517">Prod 1</span></span></td>
<td><span data-ttu-id="95312-518">Produto 1</span><span class="sxs-lookup"><span data-stu-id="95312-518">Product 1</span></span></td>
<td><span data-ttu-id="95312-519">80</span><span class="sxs-lookup"><span data-stu-id="95312-519">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-520">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="95312-520">Prod 2</span></span></td>
<td><span data-ttu-id="95312-521">Produto 2</span><span class="sxs-lookup"><span data-stu-id="95312-521">Product 2</span></span></td>
<td><span data-ttu-id="95312-522">15</span><span class="sxs-lookup"><span data-stu-id="95312-522">15</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="95312-523">**Observação:** No Finance and Operations, as medições estatísticas, como as horas de produção que um produto consome podem ser derivadas dos dados de origem.</span><span class="sxs-lookup"><span data-stu-id="95312-523">**Note:** In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="95312-524">Para obter informações mais detalhadas sobre provedores de medidas estatísticas, consulte o modelo do provedor de medida estatística.</span><span class="sxs-lookup"><span data-stu-id="95312-524">For more detailed information about statistical measure providers, see Statistical measure provider template.</span></span> <span data-ttu-id="95312-525">(Observe que este tópico não está concluído ainda, mas estará em breve.) A tabela a seguir mostra o resultado quando os serviços de RH são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="95312-525">(Note that this topic isn't completed yet but is coming soon.) The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="95312-526">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="95312-526">Cost object</span></span></th>
<th><span data-ttu-id="95312-527">Magnitude</span><span class="sxs-lookup"><span data-stu-id="95312-527">Magnitude</span></span></th>
<th><span data-ttu-id="95312-528">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="95312-528">Allocation factor</span></span></th>
<th><span data-ttu-id="95312-529">Valor</span><span class="sxs-lookup"><span data-stu-id="95312-529">Amount</span></span></th>
<th><span data-ttu-id="95312-530">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="95312-530">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-531">CC002</span><span class="sxs-lookup"><span data-stu-id="95312-531">CC002</span></span></td>
<td><span data-ttu-id="95312-532">Finanças</span><span class="sxs-lookup"><span data-stu-id="95312-532">Finance</span></span></td>
<td><span data-ttu-id="95312-533">35</span><span class="sxs-lookup"><span data-stu-id="95312-533">35</span></span></td>
<td><span data-ttu-id="95312-534">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="95312-534">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="95312-535">175.00</span><span class="sxs-lookup"><span data-stu-id="95312-535">175.00</span></span></td>
<td><span data-ttu-id="95312-536">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-536">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-537">CC003</span><span class="sxs-lookup"><span data-stu-id="95312-537">CC003</span></span></td>
<td><span data-ttu-id="95312-538">Montagem</span><span class="sxs-lookup"><span data-stu-id="95312-538">Assembly</span></span></td>
<td><span data-ttu-id="95312-539">55</span><span class="sxs-lookup"><span data-stu-id="95312-539">55</span></span></td>
<td><span data-ttu-id="95312-540">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="95312-540">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="95312-541">275.00</span><span class="sxs-lookup"><span data-stu-id="95312-541">275.00</span></span></td>
<td><span data-ttu-id="95312-542">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-542">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-543">CC004</span><span class="sxs-lookup"><span data-stu-id="95312-543">CC004</span></span></td>
<td><span data-ttu-id="95312-544">Embalagem</span><span class="sxs-lookup"><span data-stu-id="95312-544">Packaging</span></span></td>
<td><span data-ttu-id="95312-545">10</span><span class="sxs-lookup"><span data-stu-id="95312-545">10</span></span></td>
<td><span data-ttu-id="95312-546">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="95312-546">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="95312-547">50,00</span><span class="sxs-lookup"><span data-stu-id="95312-547">50.00</span></span></td>
<td><span data-ttu-id="95312-548">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-548">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-549">CC002</span><span class="sxs-lookup"><span data-stu-id="95312-549">CC002</span></span></td>
<td><span data-ttu-id="95312-550">Finanças</span><span class="sxs-lookup"><span data-stu-id="95312-550">Finance</span></span></td>
<td><span data-ttu-id="95312-551">35</span><span class="sxs-lookup"><span data-stu-id="95312-551">35</span></span></td>
<td><span data-ttu-id="95312-552">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="95312-552">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="95312-553">436.00</span><span class="sxs-lookup"><span data-stu-id="95312-553">436.00</span></span></td>
<td><span data-ttu-id="95312-554">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-554">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-555">CC003</span><span class="sxs-lookup"><span data-stu-id="95312-555">CC003</span></span></td>
<td><span data-ttu-id="95312-556">Montagem</span><span class="sxs-lookup"><span data-stu-id="95312-556">Assembly</span></span></td>
<td><span data-ttu-id="95312-557">55</span><span class="sxs-lookup"><span data-stu-id="95312-557">55</span></span></td>
<td><span data-ttu-id="95312-558">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="95312-558">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="95312-559">685.14</span><span class="sxs-lookup"><span data-stu-id="95312-559">685.14</span></span></td>
<td><span data-ttu-id="95312-560">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-560">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-561">CC004</span><span class="sxs-lookup"><span data-stu-id="95312-561">CC004</span></span></td>
<td><span data-ttu-id="95312-562">Embalagem</span><span class="sxs-lookup"><span data-stu-id="95312-562">Packaging</span></span></td>
<td><span data-ttu-id="95312-563">10</span><span class="sxs-lookup"><span data-stu-id="95312-563">10</span></span></td>
<td><span data-ttu-id="95312-564">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="95312-564">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="95312-565">124.57</span><span class="sxs-lookup"><span data-stu-id="95312-565">124.57</span></span></td>
<td><span data-ttu-id="95312-566">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-566">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="95312-567">A tabela a seguir mostra o resultado quando os serviços financeiros são aplicados como base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="95312-567">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="95312-568">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="95312-568">Cost object</span></span></th>
<th><span data-ttu-id="95312-569">Magnitude</span><span class="sxs-lookup"><span data-stu-id="95312-569">Magnitude</span></span></th>
<th><span data-ttu-id="95312-570">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="95312-570">Allocation factor</span></span></th>
<th><span data-ttu-id="95312-571">Valor</span><span class="sxs-lookup"><span data-stu-id="95312-571">Amount</span></span></th>
<th><span data-ttu-id="95312-572">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="95312-572">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-573">CC003</span><span class="sxs-lookup"><span data-stu-id="95312-573">CC003</span></span></td>
<td><span data-ttu-id="95312-574">Montagem</span><span class="sxs-lookup"><span data-stu-id="95312-574">Assembly</span></span></td>
<td><span data-ttu-id="95312-575">65</span><span class="sxs-lookup"><span data-stu-id="95312-575">65</span></span></td>
<td><span data-ttu-id="95312-576">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="95312-576">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="95312-577">438.75</span><span class="sxs-lookup"><span data-stu-id="95312-577">438.75</span></span></td>
<td><span data-ttu-id="95312-578">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-578">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-579">CC004</span><span class="sxs-lookup"><span data-stu-id="95312-579">CC004</span></span></td>
<td><span data-ttu-id="95312-580">Embalagem</span><span class="sxs-lookup"><span data-stu-id="95312-580">Packaging</span></span></td>
<td><span data-ttu-id="95312-581">35</span><span class="sxs-lookup"><span data-stu-id="95312-581">35</span></span></td>
<td><span data-ttu-id="95312-582">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="95312-582">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="95312-583">236.25</span><span class="sxs-lookup"><span data-stu-id="95312-583">236.25</span></span></td>
<td><span data-ttu-id="95312-584">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-584">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-585">CC003</span><span class="sxs-lookup"><span data-stu-id="95312-585">CC003</span></span></td>
<td><span data-ttu-id="95312-586">Montagem</span><span class="sxs-lookup"><span data-stu-id="95312-586">Assembly</span></span></td>
<td><span data-ttu-id="95312-587">65</span><span class="sxs-lookup"><span data-stu-id="95312-587">65</span></span></td>
<td><span data-ttu-id="95312-588">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="95312-588">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="95312-589">5,297.69</span><span class="sxs-lookup"><span data-stu-id="95312-589">5,297.69</span></span></td>
<td><span data-ttu-id="95312-590">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-590">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-591">CC004</span><span class="sxs-lookup"><span data-stu-id="95312-591">CC004</span></span></td>
<td><span data-ttu-id="95312-592">Embalagem</span><span class="sxs-lookup"><span data-stu-id="95312-592">Packaging</span></span></td>
<td><span data-ttu-id="95312-593">35</span><span class="sxs-lookup"><span data-stu-id="95312-593">35</span></span></td>
<td><span data-ttu-id="95312-594">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="95312-594">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="95312-595">2,852.60</span><span class="sxs-lookup"><span data-stu-id="95312-595">2,852.60</span></span></td>
<td><span data-ttu-id="95312-596">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-596">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="95312-597">A tabela a seguir mostra o resultado quando os serviços de Montagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="95312-597">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="95312-598">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="95312-598">Cost object</span></span></th>
<th><span data-ttu-id="95312-599">Magnitude</span><span class="sxs-lookup"><span data-stu-id="95312-599">Magnitude</span></span></th>
<th><span data-ttu-id="95312-600">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="95312-600">Allocation factor</span></span></th>
<th><span data-ttu-id="95312-601">Valor</span><span class="sxs-lookup"><span data-stu-id="95312-601">Amount</span></span></th>
<th><span data-ttu-id="95312-602">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="95312-602">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-603">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="95312-603">Prod 1</span></span></td>
<td><span data-ttu-id="95312-604">Produto 1</span><span class="sxs-lookup"><span data-stu-id="95312-604">Product 1</span></span></td>
<td><span data-ttu-id="95312-605">60</span><span class="sxs-lookup"><span data-stu-id="95312-605">60</span></span></td>
<td><span data-ttu-id="95312-606">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="95312-606">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="95312-607">535.31</span><span class="sxs-lookup"><span data-stu-id="95312-607">535.31</span></span></td>
<td><span data-ttu-id="95312-608">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-608">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-609">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="95312-609">Prod 2</span></span></td>
<td><span data-ttu-id="95312-610">Produto 2</span><span class="sxs-lookup"><span data-stu-id="95312-610">Product 2</span></span></td>
<td><span data-ttu-id="95312-611">20</span><span class="sxs-lookup"><span data-stu-id="95312-611">20</span></span></td>
<td><span data-ttu-id="95312-612">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="95312-612">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="95312-613">178.44</span><span class="sxs-lookup"><span data-stu-id="95312-613">178.44</span></span></td>
<td><span data-ttu-id="95312-614">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-614">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-615">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="95312-615">Prod 1</span></span></td>
<td><span data-ttu-id="95312-616">Produto 1</span><span class="sxs-lookup"><span data-stu-id="95312-616">Product 1</span></span></td>
<td><span data-ttu-id="95312-617">60</span><span class="sxs-lookup"><span data-stu-id="95312-617">60</span></span></td>
<td><span data-ttu-id="95312-618">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="95312-618">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="95312-619">4,487.12</span><span class="sxs-lookup"><span data-stu-id="95312-619">4,487.12</span></span></td>
<td><span data-ttu-id="95312-620">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-620">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-621">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="95312-621">Prod 2</span></span></td>
<td><span data-ttu-id="95312-622">Produto 2</span><span class="sxs-lookup"><span data-stu-id="95312-622">Product 2</span></span></td>
<td><span data-ttu-id="95312-623">20</span><span class="sxs-lookup"><span data-stu-id="95312-623">20</span></span></td>
<td><span data-ttu-id="95312-624">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="95312-624">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="95312-625">1,495.71</span><span class="sxs-lookup"><span data-stu-id="95312-625">1,495.71</span></span></td>
<td><span data-ttu-id="95312-626">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-626">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="95312-627">A tabela a seguir mostra o resultado quando os serviços de Embalagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="95312-627">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="95312-628">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="95312-628">Cost object</span></span></th>
<th><span data-ttu-id="95312-629">Magnitude</span><span class="sxs-lookup"><span data-stu-id="95312-629">Magnitude</span></span></th>
<th><span data-ttu-id="95312-630">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="95312-630">Allocation factor</span></span></th>
<th><span data-ttu-id="95312-631">Valor</span><span class="sxs-lookup"><span data-stu-id="95312-631">Amount</span></span></th>
<th><span data-ttu-id="95312-632">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="95312-632">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-633">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="95312-633">Prod 1</span></span></td>
<td><span data-ttu-id="95312-634">Produto 1</span><span class="sxs-lookup"><span data-stu-id="95312-634">Product 1</span></span></td>
<td><span data-ttu-id="95312-635">80</span><span class="sxs-lookup"><span data-stu-id="95312-635">80</span></span></td>
<td><span data-ttu-id="95312-636">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="95312-636">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="95312-637">241.05</span><span class="sxs-lookup"><span data-stu-id="95312-637">241.05</span></span></td>
<td><span data-ttu-id="95312-638">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-638">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-639">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="95312-639">Prod 2</span></span></td>
<td><span data-ttu-id="95312-640">Produto 2</span><span class="sxs-lookup"><span data-stu-id="95312-640">Product 2</span></span></td>
<td><span data-ttu-id="95312-641">15</span><span class="sxs-lookup"><span data-stu-id="95312-641">15</span></span></td>
<td><span data-ttu-id="95312-642">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="95312-642">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="95312-643">45.20</span><span class="sxs-lookup"><span data-stu-id="95312-643">45.20</span></span></td>
<td><span data-ttu-id="95312-644">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-644">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-645">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="95312-645">Prod 1</span></span></td>
<td><span data-ttu-id="95312-646">Produto 1</span><span class="sxs-lookup"><span data-stu-id="95312-646">Product 1</span></span></td>
<td><span data-ttu-id="95312-647">80</span><span class="sxs-lookup"><span data-stu-id="95312-647">80</span></span></td>
<td><span data-ttu-id="95312-648">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="95312-648">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="95312-649">2,507.09</span><span class="sxs-lookup"><span data-stu-id="95312-649">2,507.09</span></span></td>
<td><span data-ttu-id="95312-650">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-650">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-651">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="95312-651">Prod 2</span></span></td>
<td><span data-ttu-id="95312-652">Produto 2</span><span class="sxs-lookup"><span data-stu-id="95312-652">Product 2</span></span></td>
<td><span data-ttu-id="95312-653">15</span><span class="sxs-lookup"><span data-stu-id="95312-653">15</span></span></td>
<td><span data-ttu-id="95312-654">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="95312-654">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="95312-655">470.08</span><span class="sxs-lookup"><span data-stu-id="95312-655">470.08</span></span></td>
<td><span data-ttu-id="95312-656">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-656">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="95312-657">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="95312-657">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="95312-658">Diário</span><span class="sxs-lookup"><span data-stu-id="95312-658">Journal</span></span></th>
<th><span data-ttu-id="95312-659">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="95312-659">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="95312-660">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="95312-660">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="95312-661">Versão</span><span class="sxs-lookup"><span data-stu-id="95312-661">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-662">00004</span><span class="sxs-lookup"><span data-stu-id="95312-662">00004</span></span></td>
<td><span data-ttu-id="95312-663">Diário de alocação de custos</span><span class="sxs-lookup"><span data-stu-id="95312-663">Cost allocation journal</span></span></td>
<td><span data-ttu-id="95312-664">fiscal</span><span class="sxs-lookup"><span data-stu-id="95312-664">Fiscal</span></span></td>
<td><span data-ttu-id="95312-665">2017</span><span class="sxs-lookup"><span data-stu-id="95312-665">2017</span></span></td>
<td><span data-ttu-id="95312-666">Período 1</span><span class="sxs-lookup"><span data-stu-id="95312-666">Period 1</span></span></td>
<td><span data-ttu-id="95312-667">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="95312-667">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="95312-668">Linhas do diário</span><span class="sxs-lookup"><span data-stu-id="95312-668">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="95312-669">Data contábil</span><span class="sxs-lookup"><span data-stu-id="95312-669">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="95312-670">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="95312-670">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="95312-671">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="95312-671">Cost element</span></span></th>
<th><span data-ttu-id="95312-672">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="95312-672">Cost behavior</span></span></th>
<th><span data-ttu-id="95312-673">Valor</span><span class="sxs-lookup"><span data-stu-id="95312-673">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-674">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-674">January 31, 2017</span></span></td>
<td><span data-ttu-id="95312-675">CC001</span><span class="sxs-lookup"><span data-stu-id="95312-675">CC001</span></span></td>
<td><span data-ttu-id="95312-676">RH</span><span class="sxs-lookup"><span data-stu-id="95312-676">HR</span></span></td>
<td><span data-ttu-id="95312-677">10001</span><span class="sxs-lookup"><span data-stu-id="95312-677">10001</span></span></td>
<td><span data-ttu-id="95312-678">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-678">Electricity</span></span></td>
<td><span data-ttu-id="95312-679">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-679">Fixed cost</span></span></td>
<td><span data-ttu-id="95312-680">500,00</span><span class="sxs-lookup"><span data-stu-id="95312-680">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-681">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-681">January 31, 2017</span></span></td>
<td><span data-ttu-id="95312-682">CC001</span><span class="sxs-lookup"><span data-stu-id="95312-682">CC001</span></span></td>
<td><span data-ttu-id="95312-683">RH</span><span class="sxs-lookup"><span data-stu-id="95312-683">HR</span></span></td>
<td><span data-ttu-id="95312-684">10001</span><span class="sxs-lookup"><span data-stu-id="95312-684">10001</span></span></td>
<td><span data-ttu-id="95312-685">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-685">Electricity</span></span></td>
<td><span data-ttu-id="95312-686">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-686">Variable cost</span></span></td>
<td><span data-ttu-id="95312-687">1,245.71</span><span class="sxs-lookup"><span data-stu-id="95312-687">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-688">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-688">January 31, 2017</span></span></td>
<td><span data-ttu-id="95312-689">CC002</span><span class="sxs-lookup"><span data-stu-id="95312-689">CC002</span></span></td>
<td><span data-ttu-id="95312-690">Finanças</span><span class="sxs-lookup"><span data-stu-id="95312-690">Finance</span></span></td>
<td><span data-ttu-id="95312-691">10001</span><span class="sxs-lookup"><span data-stu-id="95312-691">10001</span></span></td>
<td><span data-ttu-id="95312-692">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-692">Electricity</span></span></td>
<td><span data-ttu-id="95312-693">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-693">Fixed cost</span></span></td>
<td><span data-ttu-id="95312-694">675.00</span><span class="sxs-lookup"><span data-stu-id="95312-694">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-695">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-695">January 31, 2017</span></span></td>
<td><span data-ttu-id="95312-696">CC002</span><span class="sxs-lookup"><span data-stu-id="95312-696">CC002</span></span></td>
<td><span data-ttu-id="95312-697">Finanças</span><span class="sxs-lookup"><span data-stu-id="95312-697">Finance</span></span></td>
<td><span data-ttu-id="95312-698">10001</span><span class="sxs-lookup"><span data-stu-id="95312-698">10001</span></span></td>
<td><span data-ttu-id="95312-699">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-699">Electricity</span></span></td>
<td><span data-ttu-id="95312-700">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-700">Variable cost</span></span></td>
<td><span data-ttu-id="95312-701">8,150.29</span><span class="sxs-lookup"><span data-stu-id="95312-701">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-702">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-702">January 31, 2017</span></span></td>
<td><span data-ttu-id="95312-703">CC003</span><span class="sxs-lookup"><span data-stu-id="95312-703">CC003</span></span></td>
<td><span data-ttu-id="95312-704">Montagem</span><span class="sxs-lookup"><span data-stu-id="95312-704">Assembly</span></span></td>
<td><span data-ttu-id="95312-705">10001</span><span class="sxs-lookup"><span data-stu-id="95312-705">10001</span></span></td>
<td><span data-ttu-id="95312-706">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-706">Electricity</span></span></td>
<td><span data-ttu-id="95312-707">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-707">Fixed cost</span></span></td>
<td><span data-ttu-id="95312-708">713.75</span><span class="sxs-lookup"><span data-stu-id="95312-708">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-709">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-709">January 31, 2017</span></span></td>
<td><span data-ttu-id="95312-710">CC003</span><span class="sxs-lookup"><span data-stu-id="95312-710">CC003</span></span></td>
<td><span data-ttu-id="95312-711">Montagem</span><span class="sxs-lookup"><span data-stu-id="95312-711">Assembly</span></span></td>
<td><span data-ttu-id="95312-712">10001</span><span class="sxs-lookup"><span data-stu-id="95312-712">10001</span></span></td>
<td><span data-ttu-id="95312-713">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-713">Electricity</span></span></td>
<td><span data-ttu-id="95312-714">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-714">Variable cost</span></span></td>
<td><span data-ttu-id="95312-715">5,982.83</span><span class="sxs-lookup"><span data-stu-id="95312-715">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-716">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-716">January 31, 2017</span></span></td>
<td><span data-ttu-id="95312-717">CC003</span><span class="sxs-lookup"><span data-stu-id="95312-717">CC003</span></span></td>
<td><span data-ttu-id="95312-718">Embalagem</span><span class="sxs-lookup"><span data-stu-id="95312-718">Packaging</span></span></td>
<td><span data-ttu-id="95312-719">10001</span><span class="sxs-lookup"><span data-stu-id="95312-719">10001</span></span></td>
<td><span data-ttu-id="95312-720">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-720">Electricity</span></span></td>
<td><span data-ttu-id="95312-721">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-721">Fixed cost</span></span></td>
<td><span data-ttu-id="95312-722">286.25</span><span class="sxs-lookup"><span data-stu-id="95312-722">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-723">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-723">January 31, 2017</span></span></td>
<td><span data-ttu-id="95312-724">CC003</span><span class="sxs-lookup"><span data-stu-id="95312-724">CC003</span></span></td>
<td><span data-ttu-id="95312-725">Embalagem</span><span class="sxs-lookup"><span data-stu-id="95312-725">Packaging</span></span></td>
<td><span data-ttu-id="95312-726">10001</span><span class="sxs-lookup"><span data-stu-id="95312-726">10001</span></span></td>
<td><span data-ttu-id="95312-727">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-727">Electricity</span></span></td>
<td><span data-ttu-id="95312-728">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-728">Variable cost</span></span></td>
<td><span data-ttu-id="95312-729">2,977.17</span><span class="sxs-lookup"><span data-stu-id="95312-729">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-730">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-730">January 31, 2017</span></span></td>
<td><span data-ttu-id="95312-731">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="95312-731">Prod 1</span></span></td>
<td><span data-ttu-id="95312-732">Produto 1</span><span class="sxs-lookup"><span data-stu-id="95312-732">Product 1</span></span></td>
<td><span data-ttu-id="95312-733">10001</span><span class="sxs-lookup"><span data-stu-id="95312-733">10001</span></span></td>
<td><span data-ttu-id="95312-734">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-734">Electricity</span></span></td>
<td><span data-ttu-id="95312-735">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-735">Fixed cost</span></span></td>
<td><span data-ttu-id="95312-736">776.36</span><span class="sxs-lookup"><span data-stu-id="95312-736">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-737">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-737">January 31, 2017</span></span></td>
<td><span data-ttu-id="95312-738">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="95312-738">Prod 1</span></span></td>
<td><span data-ttu-id="95312-739">Produto 1</span><span class="sxs-lookup"><span data-stu-id="95312-739">Product 1</span></span></td>
<td><span data-ttu-id="95312-740">10001</span><span class="sxs-lookup"><span data-stu-id="95312-740">10001</span></span></td>
<td><span data-ttu-id="95312-741">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-741">Electricity</span></span></td>
<td><span data-ttu-id="95312-742">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-742">Variable cost</span></span></td>
<td><span data-ttu-id="95312-743">6,994.21</span><span class="sxs-lookup"><span data-stu-id="95312-743">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-744">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-744">January 31, 2017</span></span></td>
<td><span data-ttu-id="95312-745">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="95312-745">Prod 2</span></span></td>
<td><span data-ttu-id="95312-746">Produto 1</span><span class="sxs-lookup"><span data-stu-id="95312-746">Product 1</span></span></td>
<td><span data-ttu-id="95312-747">10001</span><span class="sxs-lookup"><span data-stu-id="95312-747">10001</span></span></td>
<td><span data-ttu-id="95312-748">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-748">Electricity</span></span></td>
<td><span data-ttu-id="95312-749">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-749">Fixed cost</span></span></td>
<td><span data-ttu-id="95312-750">223.64</span><span class="sxs-lookup"><span data-stu-id="95312-750">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-751">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-751">January 31, 2017</span></span></td>
<td><span data-ttu-id="95312-752">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="95312-752">Prod 2</span></span></td>
<td><span data-ttu-id="95312-753">Produto 1</span><span class="sxs-lookup"><span data-stu-id="95312-753">Product 1</span></span></td>
<td><span data-ttu-id="95312-754">10001</span><span class="sxs-lookup"><span data-stu-id="95312-754">10001</span></span></td>
<td><span data-ttu-id="95312-755">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-755">Electricity</span></span></td>
<td><span data-ttu-id="95312-756">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-756">Variable cost</span></span></td>
<td><span data-ttu-id="95312-757">1,965.79</span><span class="sxs-lookup"><span data-stu-id="95312-757">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="95312-758">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="95312-758">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="95312-759">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="95312-759">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="95312-760">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="95312-760">Cost element</span></span></th>
<th><span data-ttu-id="95312-761">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="95312-761">Cost behavior</span></span></th>
<th><span data-ttu-id="95312-762">Valor</span><span class="sxs-lookup"><span data-stu-id="95312-762">Amount</span></span></th>
<th><span data-ttu-id="95312-763">Data contábil</span><span class="sxs-lookup"><span data-stu-id="95312-763">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="95312-764">CC001</span><span class="sxs-lookup"><span data-stu-id="95312-764">CC001</span></span></td>
<td><span data-ttu-id="95312-765">RH</span><span class="sxs-lookup"><span data-stu-id="95312-765">HR</span></span></td>
<td><span data-ttu-id="95312-766">10001</span><span class="sxs-lookup"><span data-stu-id="95312-766">10001</span></span></td>
<td><span data-ttu-id="95312-767">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-767">Electricity</span></span></td>
<td><span data-ttu-id="95312-768">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-768">Fixed cost</span></span></td>
<td><span data-ttu-id="95312-769">-500,00</span><span class="sxs-lookup"><span data-stu-id="95312-769">-500.00</span></span></td>
<td><span data-ttu-id="95312-770">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-770">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-771">CC002</span><span class="sxs-lookup"><span data-stu-id="95312-771">CC002</span></span></td>
<td><span data-ttu-id="95312-772">Finanças</span><span class="sxs-lookup"><span data-stu-id="95312-772">Finance</span></span></td>
<td><span data-ttu-id="95312-773">10001</span><span class="sxs-lookup"><span data-stu-id="95312-773">10001</span></span></td>
<td><span data-ttu-id="95312-774">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-774">Electricity</span></span></td>
<td><span data-ttu-id="95312-775">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-775">Fixed cost</span></span></td>
<td><span data-ttu-id="95312-776">175.00</span><span class="sxs-lookup"><span data-stu-id="95312-776">175.00</span></span></td>
<td><span data-ttu-id="95312-777">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-777">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-778">CC003</span><span class="sxs-lookup"><span data-stu-id="95312-778">CC003</span></span></td>
<td><span data-ttu-id="95312-779">Montagem</span><span class="sxs-lookup"><span data-stu-id="95312-779">Assembly</span></span></td>
<td><span data-ttu-id="95312-780">10001</span><span class="sxs-lookup"><span data-stu-id="95312-780">10001</span></span></td>
<td><span data-ttu-id="95312-781">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-781">Electricity</span></span></td>
<td><span data-ttu-id="95312-782">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-782">Fixed cost</span></span></td>
<td><span data-ttu-id="95312-783">275.00</span><span class="sxs-lookup"><span data-stu-id="95312-783">275.00</span></span></td>
<td><span data-ttu-id="95312-784">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-784">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-785">CC004</span><span class="sxs-lookup"><span data-stu-id="95312-785">CC004</span></span></td>
<td><span data-ttu-id="95312-786">Embalagem</span><span class="sxs-lookup"><span data-stu-id="95312-786">Packaging</span></span></td>
<td><span data-ttu-id="95312-787">10001</span><span class="sxs-lookup"><span data-stu-id="95312-787">10001</span></span></td>
<td><span data-ttu-id="95312-788">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-788">Electricity</span></span></td>
<td><span data-ttu-id="95312-789">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-789">Fixed cost</span></span></td>
<td><span data-ttu-id="95312-790">50,00</span><span class="sxs-lookup"><span data-stu-id="95312-790">50,00</span></span></td>
<td><span data-ttu-id="95312-791">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-791">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-792">CC001</span><span class="sxs-lookup"><span data-stu-id="95312-792">CC001</span></span></td>
<td><span data-ttu-id="95312-793">RH</span><span class="sxs-lookup"><span data-stu-id="95312-793">HR</span></span></td>
<td><span data-ttu-id="95312-794">10001</span><span class="sxs-lookup"><span data-stu-id="95312-794">10001</span></span></td>
<td><span data-ttu-id="95312-795">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-795">Electricity</span></span></td>
<td><span data-ttu-id="95312-796">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-796">Variable cost</span></span></td>
<td><span data-ttu-id="95312-797">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="95312-797">-1,245.71</span></span></td>
<td><span data-ttu-id="95312-798">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-798">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-799">CC002</span><span class="sxs-lookup"><span data-stu-id="95312-799">CC002</span></span></td>
<td><span data-ttu-id="95312-800">Finanças</span><span class="sxs-lookup"><span data-stu-id="95312-800">Finance</span></span></td>
<td><span data-ttu-id="95312-801">10001</span><span class="sxs-lookup"><span data-stu-id="95312-801">10001</span></span></td>
<td><span data-ttu-id="95312-802">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-802">Electricity</span></span></td>
<td><span data-ttu-id="95312-803">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-803">Variable cost</span></span></td>
<td><span data-ttu-id="95312-804">436.00</span><span class="sxs-lookup"><span data-stu-id="95312-804">436.00</span></span></td>
<td><span data-ttu-id="95312-805">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-805">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-806">CC003</span><span class="sxs-lookup"><span data-stu-id="95312-806">CC003</span></span></td>
<td><span data-ttu-id="95312-807">Montagem</span><span class="sxs-lookup"><span data-stu-id="95312-807">Assembly</span></span></td>
<td><span data-ttu-id="95312-808">10001</span><span class="sxs-lookup"><span data-stu-id="95312-808">10001</span></span></td>
<td><span data-ttu-id="95312-809">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-809">Electricity</span></span></td>
<td><span data-ttu-id="95312-810">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-810">Variable cost</span></span></td>
<td><span data-ttu-id="95312-811">685.14</span><span class="sxs-lookup"><span data-stu-id="95312-811">685.14</span></span></td>
<td><span data-ttu-id="95312-812">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-812">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-813">CC004</span><span class="sxs-lookup"><span data-stu-id="95312-813">CC004</span></span></td>
<td><span data-ttu-id="95312-814">Embalagem</span><span class="sxs-lookup"><span data-stu-id="95312-814">Packaging</span></span></td>
<td><span data-ttu-id="95312-815">10001</span><span class="sxs-lookup"><span data-stu-id="95312-815">10001</span></span></td>
<td><span data-ttu-id="95312-816">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-816">Electricity</span></span></td>
<td><span data-ttu-id="95312-817">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-817">Variable cost</span></span></td>
<td><span data-ttu-id="95312-818">124.57</span><span class="sxs-lookup"><span data-stu-id="95312-818">124.57</span></span></td>
<td><span data-ttu-id="95312-819">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-819">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-820">CC002</span><span class="sxs-lookup"><span data-stu-id="95312-820">CC002</span></span></td>
<td><span data-ttu-id="95312-821">Finanças</span><span class="sxs-lookup"><span data-stu-id="95312-821">Finance</span></span></td>
<td><span data-ttu-id="95312-822">10001</span><span class="sxs-lookup"><span data-stu-id="95312-822">10001</span></span></td>
<td><span data-ttu-id="95312-823">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-823">Electricity</span></span></td>
<td><span data-ttu-id="95312-824">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-824">Fixed cost</span></span></td>
<td><span data-ttu-id="95312-825">-675,00</span><span class="sxs-lookup"><span data-stu-id="95312-825">-675.00</span></span></td>
<td><span data-ttu-id="95312-826">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-826">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-827">CC003</span><span class="sxs-lookup"><span data-stu-id="95312-827">CC003</span></span></td>
<td><span data-ttu-id="95312-828">Montagem</span><span class="sxs-lookup"><span data-stu-id="95312-828">Assembly</span></span></td>
<td><span data-ttu-id="95312-829">10001</span><span class="sxs-lookup"><span data-stu-id="95312-829">10001</span></span></td>
<td><span data-ttu-id="95312-830">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-830">Electricity</span></span></td>
<td><span data-ttu-id="95312-831">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-831">Fixed cost</span></span></td>
<td><span data-ttu-id="95312-832">438.75</span><span class="sxs-lookup"><span data-stu-id="95312-832">438.75</span></span></td>
<td><span data-ttu-id="95312-833">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-833">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-834">CC004</span><span class="sxs-lookup"><span data-stu-id="95312-834">CC004</span></span></td>
<td><span data-ttu-id="95312-835">Embalagem</span><span class="sxs-lookup"><span data-stu-id="95312-835">Packaging</span></span></td>
<td><span data-ttu-id="95312-836">10001</span><span class="sxs-lookup"><span data-stu-id="95312-836">10001</span></span></td>
<td><span data-ttu-id="95312-837">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-837">Electricity</span></span></td>
<td><span data-ttu-id="95312-838">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-838">Fixed cost</span></span></td>
<td><span data-ttu-id="95312-839">236.25</span><span class="sxs-lookup"><span data-stu-id="95312-839">236.25</span></span></td>
<td><span data-ttu-id="95312-840">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-840">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-841">CC002</span><span class="sxs-lookup"><span data-stu-id="95312-841">CC002</span></span></td>
<td><span data-ttu-id="95312-842">Finanças</span><span class="sxs-lookup"><span data-stu-id="95312-842">Finance</span></span></td>
<td><span data-ttu-id="95312-843">10001</span><span class="sxs-lookup"><span data-stu-id="95312-843">10001</span></span></td>
<td><span data-ttu-id="95312-844">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-844">Electricity</span></span></td>
<td><span data-ttu-id="95312-845">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-845">Variable cost</span></span></td>
<td><span data-ttu-id="95312-846">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="95312-846">-8,150.29</span></span></td>
<td><span data-ttu-id="95312-847">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-847">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-848">CC003</span><span class="sxs-lookup"><span data-stu-id="95312-848">CC003</span></span></td>
<td><span data-ttu-id="95312-849">Montagem</span><span class="sxs-lookup"><span data-stu-id="95312-849">Assembly</span></span></td>
<td><span data-ttu-id="95312-850">10001</span><span class="sxs-lookup"><span data-stu-id="95312-850">10001</span></span></td>
<td><span data-ttu-id="95312-851">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-851">Electricity</span></span></td>
<td><span data-ttu-id="95312-852">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-852">Variable cost</span></span></td>
<td><span data-ttu-id="95312-853">5,297.69</span><span class="sxs-lookup"><span data-stu-id="95312-853">5,297.69</span></span></td>
<td><span data-ttu-id="95312-854">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-854">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-855">CC004</span><span class="sxs-lookup"><span data-stu-id="95312-855">CC004</span></span></td>
<td><span data-ttu-id="95312-856">Embalagem</span><span class="sxs-lookup"><span data-stu-id="95312-856">Packaging</span></span></td>
<td><span data-ttu-id="95312-857">10001</span><span class="sxs-lookup"><span data-stu-id="95312-857">10001</span></span></td>
<td><span data-ttu-id="95312-858">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-858">Electricity</span></span></td>
<td><span data-ttu-id="95312-859">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-859">Variable cost</span></span></td>
<td><span data-ttu-id="95312-860">2,852.60</span><span class="sxs-lookup"><span data-stu-id="95312-860">2,852.60</span></span></td>
<td><span data-ttu-id="95312-861">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-861">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-862">CC003</span><span class="sxs-lookup"><span data-stu-id="95312-862">CC003</span></span></td>
<td><span data-ttu-id="95312-863">Montagem</span><span class="sxs-lookup"><span data-stu-id="95312-863">Assembly</span></span></td>
<td><span data-ttu-id="95312-864">10001</span><span class="sxs-lookup"><span data-stu-id="95312-864">10001</span></span></td>
<td><span data-ttu-id="95312-865">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-865">Electricity</span></span></td>
<td><span data-ttu-id="95312-866">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-866">Fixed cost</span></span></td>
<td><span data-ttu-id="95312-867">-713,75</span><span class="sxs-lookup"><span data-stu-id="95312-867">-713.75</span></span></td>
<td><span data-ttu-id="95312-868">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-868">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-869">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="95312-869">Prod 1</span></span></td>
<td><span data-ttu-id="95312-870">Produto 1</span><span class="sxs-lookup"><span data-stu-id="95312-870">Product 1</span></span></td>
<td><span data-ttu-id="95312-871">10001</span><span class="sxs-lookup"><span data-stu-id="95312-871">10001</span></span></td>
<td><span data-ttu-id="95312-872">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-872">Electricity</span></span></td>
<td><span data-ttu-id="95312-873">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-873">Fixed cost</span></span></td>
<td><span data-ttu-id="95312-874">535.31</span><span class="sxs-lookup"><span data-stu-id="95312-874">535.31</span></span></td>
<td><span data-ttu-id="95312-875">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-875">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-876">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="95312-876">Prod 2</span></span></td>
<td><span data-ttu-id="95312-877">Produto 2</span><span class="sxs-lookup"><span data-stu-id="95312-877">Product 2</span></span></td>
<td><span data-ttu-id="95312-878">10001</span><span class="sxs-lookup"><span data-stu-id="95312-878">10001</span></span></td>
<td><span data-ttu-id="95312-879">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-879">Electricity</span></span></td>
<td><span data-ttu-id="95312-880">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-880">Fixed cost</span></span></td>
<td><span data-ttu-id="95312-881">178.44</span><span class="sxs-lookup"><span data-stu-id="95312-881">178.44</span></span></td>
<td><span data-ttu-id="95312-882">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-882">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-883">CC003</span><span class="sxs-lookup"><span data-stu-id="95312-883">CC003</span></span></td>
<td><span data-ttu-id="95312-884">Montagem</span><span class="sxs-lookup"><span data-stu-id="95312-884">Assembly</span></span></td>
<td><span data-ttu-id="95312-885">10001</span><span class="sxs-lookup"><span data-stu-id="95312-885">10001</span></span></td>
<td><span data-ttu-id="95312-886">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-886">Electricity</span></span></td>
<td><span data-ttu-id="95312-887">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-887">Variable cost</span></span></td>
<td><span data-ttu-id="95312-888">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="95312-888">-5,982.83</span></span></td>
<td><span data-ttu-id="95312-889">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-889">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-890">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="95312-890">Prod 1</span></span></td>
<td><span data-ttu-id="95312-891">Produto 1</span><span class="sxs-lookup"><span data-stu-id="95312-891">Product 1</span></span></td>
<td><span data-ttu-id="95312-892">10001</span><span class="sxs-lookup"><span data-stu-id="95312-892">10001</span></span></td>
<td><span data-ttu-id="95312-893">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-893">Electricity</span></span></td>
<td><span data-ttu-id="95312-894">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-894">Variable cost</span></span></td>
<td><span data-ttu-id="95312-895">4,487.12</span><span class="sxs-lookup"><span data-stu-id="95312-895">4,487.12</span></span></td>
<td><span data-ttu-id="95312-896">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-896">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-897">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="95312-897">Prod 2</span></span></td>
<td><span data-ttu-id="95312-898">Produto 2</span><span class="sxs-lookup"><span data-stu-id="95312-898">Product 2</span></span></td>
<td><span data-ttu-id="95312-899">10001</span><span class="sxs-lookup"><span data-stu-id="95312-899">10001</span></span></td>
<td><span data-ttu-id="95312-900">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-900">Electricity</span></span></td>
<td><span data-ttu-id="95312-901">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-901">Variable cost</span></span></td>
<td><span data-ttu-id="95312-902">1,495.71</span><span class="sxs-lookup"><span data-stu-id="95312-902">1,495.71</span></span></td>
<td><span data-ttu-id="95312-903">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-903">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-904">CC003</span><span class="sxs-lookup"><span data-stu-id="95312-904">CC003</span></span></td>
<td><span data-ttu-id="95312-905">Montagem</span><span class="sxs-lookup"><span data-stu-id="95312-905">Assembly</span></span></td>
<td><span data-ttu-id="95312-906">10001</span><span class="sxs-lookup"><span data-stu-id="95312-906">10001</span></span></td>
<td><span data-ttu-id="95312-907">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-907">Electricity</span></span></td>
<td><span data-ttu-id="95312-908">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-908">Fixed cost</span></span></td>
<td><span data-ttu-id="95312-909">-286,25</span><span class="sxs-lookup"><span data-stu-id="95312-909">-286.25</span></span></td>
<td><span data-ttu-id="95312-910">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-910">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-911">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="95312-911">Prod 1</span></span></td>
<td><span data-ttu-id="95312-912">Produto 1</span><span class="sxs-lookup"><span data-stu-id="95312-912">Product 1</span></span></td>
<td><span data-ttu-id="95312-913">10001</span><span class="sxs-lookup"><span data-stu-id="95312-913">10001</span></span></td>
<td><span data-ttu-id="95312-914">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-914">Electricity</span></span></td>
<td><span data-ttu-id="95312-915">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-915">Fixed cost</span></span></td>
<td><span data-ttu-id="95312-916">241.05</span><span class="sxs-lookup"><span data-stu-id="95312-916">241.05</span></span></td>
<td><span data-ttu-id="95312-917">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-917">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-918">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="95312-918">Prod 2</span></span></td>
<td><span data-ttu-id="95312-919">Produto 2</span><span class="sxs-lookup"><span data-stu-id="95312-919">Product 2</span></span></td>
<td><span data-ttu-id="95312-920">10001</span><span class="sxs-lookup"><span data-stu-id="95312-920">10001</span></span></td>
<td><span data-ttu-id="95312-921">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-921">Electricity</span></span></td>
<td><span data-ttu-id="95312-922">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-922">Fixed cost</span></span></td>
<td><span data-ttu-id="95312-923">45.20</span><span class="sxs-lookup"><span data-stu-id="95312-923">45.20</span></span></td>
<td><span data-ttu-id="95312-924">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-924">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-925">CC003</span><span class="sxs-lookup"><span data-stu-id="95312-925">CC003</span></span></td>
<td><span data-ttu-id="95312-926">Montagem</span><span class="sxs-lookup"><span data-stu-id="95312-926">Assembly</span></span></td>
<td><span data-ttu-id="95312-927">10001</span><span class="sxs-lookup"><span data-stu-id="95312-927">10001</span></span></td>
<td><span data-ttu-id="95312-928">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-928">Electricity</span></span></td>
<td><span data-ttu-id="95312-929">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-929">Variable cost</span></span></td>
<td><span data-ttu-id="95312-930">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="95312-930">-2,977.17</span></span></td>
<td><span data-ttu-id="95312-931">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-931">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-932">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="95312-932">Prod 1</span></span></td>
<td><span data-ttu-id="95312-933">Produto 1</span><span class="sxs-lookup"><span data-stu-id="95312-933">Product 1</span></span></td>
<td><span data-ttu-id="95312-934">10001</span><span class="sxs-lookup"><span data-stu-id="95312-934">10001</span></span></td>
<td><span data-ttu-id="95312-935">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-935">Electricity</span></span></td>
<td><span data-ttu-id="95312-936">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-936">Variable cost</span></span></td>
<td><span data-ttu-id="95312-937">2,507.09</span><span class="sxs-lookup"><span data-stu-id="95312-937">2,507.09</span></span></td>
<td><span data-ttu-id="95312-938">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-938">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="95312-939">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="95312-939">Prod 2</span></span></td>
<td><span data-ttu-id="95312-940">Produto 2</span><span class="sxs-lookup"><span data-stu-id="95312-940">Product 2</span></span></td>
<td><span data-ttu-id="95312-941">10001</span><span class="sxs-lookup"><span data-stu-id="95312-941">10001</span></span></td>
<td><span data-ttu-id="95312-942">eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-942">Electricity</span></span></td>
<td><span data-ttu-id="95312-943">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-943">Variable cost</span></span></td>
<td><span data-ttu-id="95312-944">470.08</span><span class="sxs-lookup"><span data-stu-id="95312-944">470.08</span></span></td>
<td><span data-ttu-id="95312-945">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="95312-945">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="95312-946">Conclusão</span><span class="sxs-lookup"><span data-stu-id="95312-946">Conclusion</span></span>
<span data-ttu-id="95312-947">Na contabilidade financeira, um custo de 10,000.00 para a eletricidade é lançado para um ID fictício de centro de custos.</span><span class="sxs-lookup"><span data-stu-id="95312-947">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="95312-948">Portanto, os contadores de custo saberão que esses custos devem ser alocados.</span><span class="sxs-lookup"><span data-stu-id="95312-948">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="95312-949">Na contabilização de custo, os custos fluem nas unidades organizacionais e nos níveis, com base nas políticas e regras que são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="95312-949">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="95312-950">Cada custo foi associado a uma base de alocação que fornece a melhor apuração para a alocação de custos.</span><span class="sxs-lookup"><span data-stu-id="95312-950">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="95312-951">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="95312-951">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="95312-952">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="95312-952">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="95312-953">Total</span><span class="sxs-lookup"><span data-stu-id="95312-953">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="95312-954">CC099</span><span class="sxs-lookup"><span data-stu-id="95312-954">CC099</span></span></th>
<th><span data-ttu-id="95312-955">CC001</span><span class="sxs-lookup"><span data-stu-id="95312-955">CC001</span></span></th>
<th><span data-ttu-id="95312-956">CC002</span><span class="sxs-lookup"><span data-stu-id="95312-956">CC002</span></span></th>
<th><span data-ttu-id="95312-957">CC003</span><span class="sxs-lookup"><span data-stu-id="95312-957">CC003</span></span></th>
<th><span data-ttu-id="95312-958">CC004</span><span class="sxs-lookup"><span data-stu-id="95312-958">CC004</span></span></th>
<th><span data-ttu-id="95312-959">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="95312-959">Proj 1</span></span></th>
<th><span data-ttu-id="95312-960">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="95312-960">Proj 2</span></span></th>
<th><span data-ttu-id="95312-961">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="95312-961">Prod 1</span></span></th>
<th><span data-ttu-id="95312-962">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="95312-962">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="95312-963">10001 Eletricidade</span><span class="sxs-lookup"><span data-stu-id="95312-963">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="95312-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-965"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="95312-965"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-966"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="95312-966"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-967"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="95312-967"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="95312-968"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="95312-968"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-969"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="95312-969"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-970"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="95312-970"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-971"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="95312-971"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-972"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="95312-972"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="95312-973">Não classificado</span><span class="sxs-lookup"><span data-stu-id="95312-973">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-974">0,00</span><span class="sxs-lookup"><span data-stu-id="95312-974">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="95312-975">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="95312-975">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-976">0,00</span><span class="sxs-lookup"><span data-stu-id="95312-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-977">0,00</span><span class="sxs-lookup"><span data-stu-id="95312-977">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-978">0,00</span><span class="sxs-lookup"><span data-stu-id="95312-978">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-979">0,00</span><span class="sxs-lookup"><span data-stu-id="95312-979">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-980">0,00</span><span class="sxs-lookup"><span data-stu-id="95312-980">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="95312-981">776.36</span><span class="sxs-lookup"><span data-stu-id="95312-981">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-982">223.64</span><span class="sxs-lookup"><span data-stu-id="95312-982">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-983"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="95312-983"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="95312-984">Custo variável</span><span class="sxs-lookup"><span data-stu-id="95312-984">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-985">000</span><span class="sxs-lookup"><span data-stu-id="95312-985">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-986">0,00</span><span class="sxs-lookup"><span data-stu-id="95312-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-987">0,00</span><span class="sxs-lookup"><span data-stu-id="95312-987">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-988">0,00</span><span class="sxs-lookup"><span data-stu-id="95312-988">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-989">0,00</span><span class="sxs-lookup"><span data-stu-id="95312-989">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-990">30,00</span><span class="sxs-lookup"><span data-stu-id="95312-990">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-991">10,00</span><span class="sxs-lookup"><span data-stu-id="95312-991">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-992">6,994.21</span><span class="sxs-lookup"><span data-stu-id="95312-992">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-993">1,965.79</span><span class="sxs-lookup"><span data-stu-id="95312-993">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="95312-994"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="95312-994"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="95312-995">Esse tópico mostra como um elemento de custo principal, 10001 Eletricidade flui pelos objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="95312-995">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="95312-996">Portanto, esse custo geral indireto é alocado no nível mais baixo na organização.</span><span class="sxs-lookup"><span data-stu-id="95312-996">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="95312-997">Em outras palavras, os objetos de custo no nível mais baixo assumem o custo.</span><span class="sxs-lookup"><span data-stu-id="95312-997">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="95312-998">Se você exigir um fluxo visual de custo entre objetos de custo, é possível usar as regras de política de acúmulo de custos para visualizar o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="95312-998">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="95312-999">Para obter informações mais detalhadas, consulte a política de acúmulo de custos.</span><span class="sxs-lookup"><span data-stu-id="95312-999">For more detailed information, see Cost roll-up policy.</span></span> <span data-ttu-id="95312-1000">(Observe que este tópico não está incluído, mas estará em breve).</span><span class="sxs-lookup"><span data-stu-id="95312-1000">(Note that this topic isn't competed yet but is coming soon.)</span></span>




