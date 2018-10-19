---
title: "Cálculo de custos indiretos"
description: "Este tópico descreve processos comuns para calcular e alocar os custos gerais indiretos."
author: AndersGirke
manager: AnnBe
ms.date: 10/04/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 12ae99c15bafcd9cc08b30903fe3f251f446b17d
ms.openlocfilehash: 4de705324ac497cfb11fae3dadc6f57d038fd0b5
ms.contentlocale: pt-br
ms.lasthandoff: 10/05/2018

---

# <a name="overhead-calculation"></a><span data-ttu-id="bf608-103">Cálculo de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="bf608-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bf608-104">Este tópico descreve processos comuns para calcular e alocar os custos gerais indiretos.</span><span class="sxs-lookup"><span data-stu-id="bf608-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="bf608-105">Definição de termo</span><span class="sxs-lookup"><span data-stu-id="bf608-105">Term definition</span></span>
---------------

<span data-ttu-id="bf608-106">Os custos gerais indiretos são aqueles que foram incorridos para realizar um negócio, mas não podem ser diretamente atribuídos a qualquer atividade comercial, produto ou serviço específico.</span><span class="sxs-lookup"><span data-stu-id="bf608-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="bf608-107">Os custos gerais indiretos fornecem suporte crítico para geração de atividades produtivas.</span><span class="sxs-lookup"><span data-stu-id="bf608-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="bf608-108">Eis alguns exemplos de custos gerais:</span><span class="sxs-lookup"><span data-stu-id="bf608-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="bf608-109">Aluguel</span><span class="sxs-lookup"><span data-stu-id="bf608-109">Rent</span></span>
-   <span data-ttu-id="bf608-110">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-110">Electricity</span></span>
-   <span data-ttu-id="bf608-111">Salários administrativos</span><span class="sxs-lookup"><span data-stu-id="bf608-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="bf608-112">Visão geral do cálculo de custos gerais indiretos</span><span class="sxs-lookup"><span data-stu-id="bf608-112">Overhead calculation overview</span></span>
<span data-ttu-id="bf608-113">O cálculo de custos gerais indiretos executa as políticas de contabilização de custos na ordem correta.</span><span class="sxs-lookup"><span data-stu-id="bf608-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="bf608-114">Você pode executar o cálculo de custos gerais indiretos várias vezes para o mesmo período fiscal, se as políticas de contabilidade de custo foram modificadas ou foram detectados erros específicos.</span><span class="sxs-lookup"><span data-stu-id="bf608-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="bf608-115">Cada execução do cálculo de custos gerais indiretos é armazenada e recebe um ID exclusivo de versão que permite comparar os cálculos em várias versões.</span><span class="sxs-lookup"><span data-stu-id="bf608-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="bf608-116">As entradas de custo que o cálculo de custos indiretos gera recebe uma data contábil.</span><span class="sxs-lookup"><span data-stu-id="bf608-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="bf608-117">Essa data contábil corresponde à data final do período fiscal que é usada no cálculo.</span><span class="sxs-lookup"><span data-stu-id="bf608-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="bf608-118">A ID exclusiva de versão consiste nos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="bf608-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="bf608-119">Tipo de versão</span><span class="sxs-lookup"><span data-stu-id="bf608-119">Version type</span></span>
-   <span data-ttu-id="bf608-120">Data e hora</span><span class="sxs-lookup"><span data-stu-id="bf608-120">Date and time</span></span>
-   <span data-ttu-id="bf608-121">Razão de contabilização de custos</span><span class="sxs-lookup"><span data-stu-id="bf608-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="bf608-122">Ano fiscal</span><span class="sxs-lookup"><span data-stu-id="bf608-122">Fiscal year</span></span>
-   <span data-ttu-id="bf608-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="bf608-123">Fiscal period</span></span>

<span data-ttu-id="bf608-124">O cálculo de custos gerais indiretos é executado independentemente da versão.</span><span class="sxs-lookup"><span data-stu-id="bf608-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="bf608-125">Portanto, você pode calcular a versão de orçamento antes da versão atual.</span><span class="sxs-lookup"><span data-stu-id="bf608-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="bf608-126">O cálculo de custos gerais indiretos consiste em quatro etapas, conforme mostrado na ilustração.</span><span class="sxs-lookup"><span data-stu-id="bf608-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="bf608-127">Em cada etapa, um cabeçalho de diário é criado com entradas de diário.</span><span class="sxs-lookup"><span data-stu-id="bf608-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="bf608-128">Esse cabeçalho de diário mantém dados de entrada para cada etapa de cálculo.</span><span class="sxs-lookup"><span data-stu-id="bf608-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="bf608-129">As políticas e regras são aplicadas a cada linha do diário e as entradas de custo são geradas como saídas.</span><span class="sxs-lookup"><span data-stu-id="bf608-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="bf608-130">Portanto, você sempre terá rastreabilidade total.</span><span class="sxs-lookup"><span data-stu-id="bf608-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="bf608-131">[![Cálculo de custos gerais indiretos](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="bf608-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="bf608-132">Calcular e alocar os custos gerais indiretos de Eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="bf608-133">Na contabilidade financeira, alguns custos, como eletricidade, são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="bf608-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="bf608-134">Portanto, a visão administrativa detalhada não é fornecida para a contabilização de custo.</span><span class="sxs-lookup"><span data-stu-id="bf608-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="bf608-135">Na contabilização de custo, para fornecer a visão administrativa correta em todas as unidades organizacionais e níveis, os custos devem passar pelas unidades organizacionais.</span><span class="sxs-lookup"><span data-stu-id="bf608-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="bf608-136">Este fluxo deve ser baseado em qualquer um registro exato do consumo ou de uma previsão justa.</span><span class="sxs-lookup"><span data-stu-id="bf608-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="bf608-137">Na contabilidade, um custo de eletricidade pode ser lançado, conforme mostrado na tabela.</span><span class="sxs-lookup"><span data-stu-id="bf608-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bf608-138">Data contábil</span><span class="sxs-lookup"><span data-stu-id="bf608-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="bf608-139">Centro de custos</span><span class="sxs-lookup"><span data-stu-id="bf608-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="bf608-140">Conta principal</span><span class="sxs-lookup"><span data-stu-id="bf608-140">Main account</span></span></th>
<th><span data-ttu-id="bf608-141">Valor na moeda contábil</span><span class="sxs-lookup"><span data-stu-id="bf608-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-142">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="bf608-143">CC099</span><span class="sxs-lookup"><span data-stu-id="bf608-143">CC099</span></span></td>
<td><span data-ttu-id="bf608-144">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="bf608-144">Default cost center</span></span></td>
<td><span data-ttu-id="bf608-145">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-145">10001</span></span></td>
<td><span data-ttu-id="bf608-146">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-146">Electricity</span></span></td>
<td><span data-ttu-id="bf608-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="bf608-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="bf608-148">Etapa 1: Processar o cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="bf608-149">Por padrão, quando as entradas de custo previsto são importadas de dados de origem, elas recebem a classificação de comportamento de custo **Não classificado** na Contabilidade de custos.</span><span class="sxs-lookup"><span data-stu-id="bf608-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="bf608-150">Aplicando regras da política de comportamento de custo, é possível reclassificar entradas de custo como **Custo fixo** ou **Custo variável**.</span><span class="sxs-lookup"><span data-stu-id="bf608-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="bf608-151">Definir a regra de custo de comportamento</span><span class="sxs-lookup"><span data-stu-id="bf608-151">Define the cost behavior rule</span></span>

<span data-ttu-id="bf608-152">Em alguns casos, parte do custo é uma taxa fixa e o custos pendente é baseado no consumo.</span><span class="sxs-lookup"><span data-stu-id="bf608-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="bf608-153">Geralmente, as contas de eletricidade correspondem a esta definição.</span><span class="sxs-lookup"><span data-stu-id="bf608-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="bf608-154">Após você pagar uma taxa fixa específica, você paga por consumo, por hora de quilowatt (Kwh).</span><span class="sxs-lookup"><span data-stu-id="bf608-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="bf608-155">Por exemplo, se a taxa de custo fixa for 1.000.00, veja aqui como a regra de comportamento de custo é definida:</span><span class="sxs-lookup"><span data-stu-id="bf608-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="bf608-156">Valor fixo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="bf608-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="bf608-157">0 &lt;= 1.000,00 = Fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="bf608-158">1000.01 &lt; N = Variável</span><span class="sxs-lookup"><span data-stu-id="bf608-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="bf608-159">Diário</span><span class="sxs-lookup"><span data-stu-id="bf608-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bf608-160">Diário</span><span class="sxs-lookup"><span data-stu-id="bf608-160">Journal</span></span></th>
<th><span data-ttu-id="bf608-161">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="bf608-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="bf608-162">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="bf608-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="bf608-163">Versão</span><span class="sxs-lookup"><span data-stu-id="bf608-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-164">00001</span><span class="sxs-lookup"><span data-stu-id="bf608-164">00001</span></span></td>
<td><span data-ttu-id="bf608-165">Diário de cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="bf608-166">fiscal</span><span class="sxs-lookup"><span data-stu-id="bf608-166">Fiscal</span></span></td>
<td><span data-ttu-id="bf608-167">2017</span><span class="sxs-lookup"><span data-stu-id="bf608-167">2017</span></span></td>
<td><span data-ttu-id="bf608-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="bf608-168">Period 1</span></span></td>
<td><span data-ttu-id="bf608-169">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="bf608-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="bf608-170">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="bf608-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bf608-171">Data contábil</span><span class="sxs-lookup"><span data-stu-id="bf608-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="bf608-172">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="bf608-173">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-173">Cost element</span></span></th>
<th><span data-ttu-id="bf608-174">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-174">Cost behavior</span></span></th>
<th><span data-ttu-id="bf608-175">Valor</span><span class="sxs-lookup"><span data-stu-id="bf608-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-176">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="bf608-177">CC099</span><span class="sxs-lookup"><span data-stu-id="bf608-177">CC099</span></span></td>
<td><span data-ttu-id="bf608-178">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="bf608-178">Default cost center</span></span></td>
<td><span data-ttu-id="bf608-179">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-179">10001</span></span></td>
<td><span data-ttu-id="bf608-180">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-180">Electricity</span></span></td>
<td><span data-ttu-id="bf608-181">Não classificado</span><span class="sxs-lookup"><span data-stu-id="bf608-181">Unclassified</span></span></td>
<td><span data-ttu-id="bf608-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="bf608-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="bf608-183">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bf608-184">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="bf608-185">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-185">Cost element</span></span></th>
<th><span data-ttu-id="bf608-186">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-186">Cost behavior</span></span></th>
<th><span data-ttu-id="bf608-187">Valor</span><span class="sxs-lookup"><span data-stu-id="bf608-187">Amount</span></span></th>
<th><span data-ttu-id="bf608-188">Data contábil</span><span class="sxs-lookup"><span data-stu-id="bf608-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-189">CC099</span><span class="sxs-lookup"><span data-stu-id="bf608-189">CC099</span></span></td>
<td><span data-ttu-id="bf608-190">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="bf608-190">Default cost center</span></span></td>
<td><span data-ttu-id="bf608-191">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-191">10001</span></span></td>
<td><span data-ttu-id="bf608-192">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-192">Electricity</span></span></td>
<td><span data-ttu-id="bf608-193">Não classificado</span><span class="sxs-lookup"><span data-stu-id="bf608-193">Unclassified</span></span></td>
<td><span data-ttu-id="bf608-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="bf608-194">10,000.00</span></span></td>
<td><span data-ttu-id="bf608-195">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-196">CC099</span><span class="sxs-lookup"><span data-stu-id="bf608-196">CC099</span></span></td>
<td><span data-ttu-id="bf608-197">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="bf608-197">Default cost center</span></span></td>
<td><span data-ttu-id="bf608-198">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-198">10001</span></span></td>
<td><span data-ttu-id="bf608-199">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-199">Electricity</span></span></td>
<td><span data-ttu-id="bf608-200">Não classificado</span><span class="sxs-lookup"><span data-stu-id="bf608-200">Unclassified</span></span></td>
<td><span data-ttu-id="bf608-201">-10.000,00</span><span class="sxs-lookup"><span data-stu-id="bf608-201">-10,000.00</span></span></td>
<td><span data-ttu-id="bf608-202">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-203">CC099</span><span class="sxs-lookup"><span data-stu-id="bf608-203">CC099</span></span></td>
<td><span data-ttu-id="bf608-204">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="bf608-204">Default cost center</span></span></td>
<td><span data-ttu-id="bf608-205">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-205">10001</span></span></td>
<td><span data-ttu-id="bf608-206">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-206">Electricity</span></span></td>
<td><span data-ttu-id="bf608-207">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-207">Fixed cost</span></span></td>
<td><span data-ttu-id="bf608-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="bf608-208">1,000.00</span></span></td>
<td><span data-ttu-id="bf608-209">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-210">CC099</span><span class="sxs-lookup"><span data-stu-id="bf608-210">CC099</span></span></td>
<td><span data-ttu-id="bf608-211">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="bf608-211">Default cost center</span></span></td>
<td><span data-ttu-id="bf608-212">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-212">10001</span></span></td>
<td><span data-ttu-id="bf608-213">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-213">Electricity</span></span></td>
<td><span data-ttu-id="bf608-214">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-214">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="bf608-215">9,000.00</span></span></td>
<td><span data-ttu-id="bf608-216">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bf608-217">Para obter mais informações, consulte [Criar e atribuir uma política de comportamento de custos a uma unidade de controle de custos](tasks/create-assign-cost-behavior-policy-cost-control-unit.md)</span><span class="sxs-lookup"><span data-stu-id="bf608-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="bf608-218">Etapa 2: Processar o cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="bf608-219">A distribuição de custos é usada para redistribuir custo de um objeto de custo a um ou mais outros objetos de custo, aplicando uma base de alocação relevante.</span><span class="sxs-lookup"><span data-stu-id="bf608-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="bf608-220">A distribuição de custos e a alocação de custo são diferentes na distribuição de custos, sempre que ocorrer em nível de elemento de custo principal do custo original.</span><span class="sxs-lookup"><span data-stu-id="bf608-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="bf608-221">Definir a regra de distribuição de custos</span><span class="sxs-lookup"><span data-stu-id="bf608-221">Define the cost distribution rule</span></span>

<span data-ttu-id="bf608-222">Na contabilidade financeira, os custos de eletricidade geralmente são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="bf608-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="bf608-223">Na contabilização de custo, esta abordagem não é suficientemente detalhada.</span><span class="sxs-lookup"><span data-stu-id="bf608-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="bf608-224">O custo variável deve ser distribuído a objetos de custos individuais com base justa.</span><span class="sxs-lookup"><span data-stu-id="bf608-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="bf608-225">A base de alocação mais lógica é o consumo de eletricidade (Kwh).</span><span class="sxs-lookup"><span data-stu-id="bf608-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="bf608-226">O membro da dimensão estatística que é chamado Eletricidade é criado e o consumo de eletricidade é registrado.</span><span class="sxs-lookup"><span data-stu-id="bf608-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="bf608-227">Por padrão, todos os membros estatísticos da dimensão se tornam disponíveis como bases de alocação.</span><span class="sxs-lookup"><span data-stu-id="bf608-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bf608-228">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-228">Cost object</span></span></th>
<th><span data-ttu-id="bf608-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="bf608-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-230">CC001</span><span class="sxs-lookup"><span data-stu-id="bf608-230">CC001</span></span></td>
<td><span data-ttu-id="bf608-231">RH</span><span class="sxs-lookup"><span data-stu-id="bf608-231">HR</span></span></td>
<td><span data-ttu-id="bf608-232">1.000</span><span class="sxs-lookup"><span data-stu-id="bf608-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-233">CC002</span><span class="sxs-lookup"><span data-stu-id="bf608-233">CC002</span></span></td>
<td><span data-ttu-id="bf608-234">Finanças</span><span class="sxs-lookup"><span data-stu-id="bf608-234">Finance</span></span></td>
<td><span data-ttu-id="bf608-235">6,000</span><span class="sxs-lookup"><span data-stu-id="bf608-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-236">CC003</span><span class="sxs-lookup"><span data-stu-id="bf608-236">CC003</span></span></td>
<td><span data-ttu-id="bf608-237">Montagem</span><span class="sxs-lookup"><span data-stu-id="bf608-237">Assembly</span></span></td>
<td><span data-ttu-id="bf608-238">0</span><span class="sxs-lookup"><span data-stu-id="bf608-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bf608-239">A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação para custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="bf608-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bf608-240">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-240">Cost object</span></span></th>
<th><span data-ttu-id="bf608-241">Magnitude</span><span class="sxs-lookup"><span data-stu-id="bf608-241">Magnitude</span></span></th>
<th><span data-ttu-id="bf608-242">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="bf608-242">Allocation factor</span></span></th>
<th><span data-ttu-id="bf608-243">Valor</span><span class="sxs-lookup"><span data-stu-id="bf608-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-244">CC001</span><span class="sxs-lookup"><span data-stu-id="bf608-244">CC001</span></span></td>
<td><span data-ttu-id="bf608-245">RH</span><span class="sxs-lookup"><span data-stu-id="bf608-245">HR</span></span></td>
<td><span data-ttu-id="bf608-246">1.000</span><span class="sxs-lookup"><span data-stu-id="bf608-246">1,000</span></span></td>
<td><span data-ttu-id="bf608-247">(1.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="bf608-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="bf608-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="bf608-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-249">CC002</span><span class="sxs-lookup"><span data-stu-id="bf608-249">CC002</span></span></td>
<td><span data-ttu-id="bf608-250">Finanças</span><span class="sxs-lookup"><span data-stu-id="bf608-250">Finance</span></span></td>
<td><span data-ttu-id="bf608-251">6,000</span><span class="sxs-lookup"><span data-stu-id="bf608-251">6,000</span></span></td>
<td><span data-ttu-id="bf608-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="bf608-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="bf608-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="bf608-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-254">CC003</span><span class="sxs-lookup"><span data-stu-id="bf608-254">CC003</span></span></td>
<td><span data-ttu-id="bf608-255">Montagem</span><span class="sxs-lookup"><span data-stu-id="bf608-255">Assembly</span></span></td>
<td><span data-ttu-id="bf608-256">0</span><span class="sxs-lookup"><span data-stu-id="bf608-256">0</span></span></td>
<td><span data-ttu-id="bf608-257">(0 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="bf608-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="bf608-258">0,00</span><span class="sxs-lookup"><span data-stu-id="bf608-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bf608-259">Os custos fixos devem ser distribuídos igualmente a objetos de custo individuais que têm a eletricidade consumida.</span><span class="sxs-lookup"><span data-stu-id="bf608-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="bf608-260">Você pode obter esse resultado usando o membro estatístico de dimensão de eletricidade em uma base e alocação da fórmula: (Eletricidade &gt; 0,00) A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação de custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="bf608-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bf608-261">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-261">Cost object</span></span></th>
<th><span data-ttu-id="bf608-262">Fórmula</span><span class="sxs-lookup"><span data-stu-id="bf608-262">Formula</span></span></th>
<th><span data-ttu-id="bf608-263">Magnitude</span><span class="sxs-lookup"><span data-stu-id="bf608-263">Magnitude</span></span></th>
<th><span data-ttu-id="bf608-264">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="bf608-264">Allocation factor</span></span></th>
<th><span data-ttu-id="bf608-265">Valor</span><span class="sxs-lookup"><span data-stu-id="bf608-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-266">CC001</span><span class="sxs-lookup"><span data-stu-id="bf608-266">CC001</span></span></td>
<td><span data-ttu-id="bf608-267">RH</span><span class="sxs-lookup"><span data-stu-id="bf608-267">HR</span></span></td>
<td><span data-ttu-id="bf608-268">(1.000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="bf608-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="bf608-269">1</span><span class="sxs-lookup"><span data-stu-id="bf608-269">1</span></span></td>
<td><span data-ttu-id="bf608-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="bf608-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="bf608-271">500,00</span><span class="sxs-lookup"><span data-stu-id="bf608-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-272">CC002</span><span class="sxs-lookup"><span data-stu-id="bf608-272">CC002</span></span></td>
<td><span data-ttu-id="bf608-273">Finanças</span><span class="sxs-lookup"><span data-stu-id="bf608-273">Finance</span></span></td>
<td><span data-ttu-id="bf608-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="bf608-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="bf608-275">1</span><span class="sxs-lookup"><span data-stu-id="bf608-275">1</span></span></td>
<td><span data-ttu-id="bf608-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="bf608-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="bf608-277">500,00</span><span class="sxs-lookup"><span data-stu-id="bf608-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-278">CC003</span><span class="sxs-lookup"><span data-stu-id="bf608-278">CC003</span></span></td>
<td><span data-ttu-id="bf608-279">Montagem</span><span class="sxs-lookup"><span data-stu-id="bf608-279">Assembly</span></span></td>
<td><span data-ttu-id="bf608-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="bf608-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="bf608-281">0</span><span class="sxs-lookup"><span data-stu-id="bf608-281">0</span></span></td>
<td><span data-ttu-id="bf608-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="bf608-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="bf608-283">0,00</span><span class="sxs-lookup"><span data-stu-id="bf608-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="bf608-284">Diário</span><span class="sxs-lookup"><span data-stu-id="bf608-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bf608-285">Diário</span><span class="sxs-lookup"><span data-stu-id="bf608-285">Journal</span></span></th>
<th><span data-ttu-id="bf608-286">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="bf608-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="bf608-287">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="bf608-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="bf608-288">Versão</span><span class="sxs-lookup"><span data-stu-id="bf608-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-289">00002</span><span class="sxs-lookup"><span data-stu-id="bf608-289">00002</span></span></td>
<td><span data-ttu-id="bf608-290">Diário de cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="bf608-291">fiscal</span><span class="sxs-lookup"><span data-stu-id="bf608-291">Fiscal</span></span></td>
<td><span data-ttu-id="bf608-292">2017</span><span class="sxs-lookup"><span data-stu-id="bf608-292">2017</span></span></td>
<td><span data-ttu-id="bf608-293">Período 1</span><span class="sxs-lookup"><span data-stu-id="bf608-293">Period 1</span></span></td>
<td><span data-ttu-id="bf608-294">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="bf608-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="bf608-295">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="bf608-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bf608-296">Data contábil</span><span class="sxs-lookup"><span data-stu-id="bf608-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="bf608-297">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="bf608-298">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-298">Cost element</span></span></th>
<th><span data-ttu-id="bf608-299">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-299">Cost behavior</span></span></th>
<th><span data-ttu-id="bf608-300">Valor</span><span class="sxs-lookup"><span data-stu-id="bf608-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-301">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="bf608-302">CC099</span><span class="sxs-lookup"><span data-stu-id="bf608-302">CC099</span></span></td>
<td><span data-ttu-id="bf608-303">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="bf608-303">Default cost center</span></span></td>
<td><span data-ttu-id="bf608-304">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-304">10001</span></span></td>
<td><span data-ttu-id="bf608-305">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-305">Electricity</span></span></td>
<td><span data-ttu-id="bf608-306">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-306">Fixed cost</span></span></td>
<td><span data-ttu-id="bf608-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="bf608-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-308">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="bf608-309">CC099</span><span class="sxs-lookup"><span data-stu-id="bf608-309">CC099</span></span></td>
<td><span data-ttu-id="bf608-310">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="bf608-310">Default cost center</span></span></td>
<td><span data-ttu-id="bf608-311">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-311">10001</span></span></td>
<td><span data-ttu-id="bf608-312">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-312">Electricity</span></span></td>
<td><span data-ttu-id="bf608-313">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-313">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="bf608-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="bf608-315">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bf608-316">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="bf608-317">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-317">Cost element</span></span></th>
<th><span data-ttu-id="bf608-318">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-318">Cost behavior</span></span></th>
<th><span data-ttu-id="bf608-319">Valor</span><span class="sxs-lookup"><span data-stu-id="bf608-319">Amount</span></span></th>
<th><span data-ttu-id="bf608-320">Data contábil</span><span class="sxs-lookup"><span data-stu-id="bf608-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-321">CC099</span><span class="sxs-lookup"><span data-stu-id="bf608-321">CC099</span></span></td>
<td><span data-ttu-id="bf608-322">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="bf608-322">Default cost center</span></span></td>
<td><span data-ttu-id="bf608-323">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-323">10001</span></span></td>
<td><span data-ttu-id="bf608-324">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-324">Electricity</span></span></td>
<td><span data-ttu-id="bf608-325">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-325">Fixed cost</span></span></td>
<td><span data-ttu-id="bf608-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="bf608-326">-1,000.00</span></span></td>
<td><span data-ttu-id="bf608-327">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-328">CC001</span><span class="sxs-lookup"><span data-stu-id="bf608-328">CC001</span></span></td>
<td><span data-ttu-id="bf608-329">RH</span><span class="sxs-lookup"><span data-stu-id="bf608-329">HR</span></span></td>
<td><span data-ttu-id="bf608-330">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-330">10001</span></span></td>
<td><span data-ttu-id="bf608-331">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-331">Electricity</span></span></td>
<td><span data-ttu-id="bf608-332">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-332">Fixed cost</span></span></td>
<td><span data-ttu-id="bf608-333">500,00</span><span class="sxs-lookup"><span data-stu-id="bf608-333">500.00</span></span></td>
<td><span data-ttu-id="bf608-334">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-335">CC002</span><span class="sxs-lookup"><span data-stu-id="bf608-335">CC002</span></span></td>
<td><span data-ttu-id="bf608-336">Finanças</span><span class="sxs-lookup"><span data-stu-id="bf608-336">Finance</span></span></td>
<td><span data-ttu-id="bf608-337">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-337">10001</span></span></td>
<td><span data-ttu-id="bf608-338">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-338">Electricity</span></span></td>
<td><span data-ttu-id="bf608-339">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-339">Fixed cost</span></span></td>
<td><span data-ttu-id="bf608-340">500,00</span><span class="sxs-lookup"><span data-stu-id="bf608-340">500.00</span></span></td>
<td><span data-ttu-id="bf608-341">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-342">CC099</span><span class="sxs-lookup"><span data-stu-id="bf608-342">CC099</span></span></td>
<td><span data-ttu-id="bf608-343">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="bf608-343">Default cost center</span></span></td>
<td><span data-ttu-id="bf608-344">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-344">10001</span></span></td>
<td><span data-ttu-id="bf608-345">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-345">Electricity</span></span></td>
<td><span data-ttu-id="bf608-346">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-346">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="bf608-347">-9,000.00</span></span></td>
<td><span data-ttu-id="bf608-348">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-349">CC001</span><span class="sxs-lookup"><span data-stu-id="bf608-349">CC001</span></span></td>
<td><span data-ttu-id="bf608-350">RH</span><span class="sxs-lookup"><span data-stu-id="bf608-350">HR</span></span></td>
<td><span data-ttu-id="bf608-351">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-351">10001</span></span></td>
<td><span data-ttu-id="bf608-352">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-352">Electricity</span></span></td>
<td><span data-ttu-id="bf608-353">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-353">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="bf608-354">1,285.71</span></span></td>
<td><span data-ttu-id="bf608-355">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-356">CC002</span><span class="sxs-lookup"><span data-stu-id="bf608-356">CC002</span></span></td>
<td><span data-ttu-id="bf608-357">Finanças</span><span class="sxs-lookup"><span data-stu-id="bf608-357">Finance</span></span></td>
<td><span data-ttu-id="bf608-358">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-358">10001</span></span></td>
<td><span data-ttu-id="bf608-359">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-359">Electricity</span></span></td>
<td><span data-ttu-id="bf608-360">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-360">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="bf608-361">7,714.29</span></span></td>
<td><span data-ttu-id="bf608-362">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bf608-363">Para obter mais informações, consulte [Criar e atribuir uma política de distribuição de custos a uma unidade de controle de custos](tasks/create-assign-cost-distribution-policy-cost-control-unit.md)</span><span class="sxs-lookup"><span data-stu-id="bf608-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="bf608-364">Etapa 3: Processar o cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="bf608-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="bf608-365">A taxa de custos indiretos é usada para cobrar um ou mais objetos de custos específicos.</span><span class="sxs-lookup"><span data-stu-id="bf608-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="bf608-366">O encargo se baseia em uma taxa de custo predeterminada e a magnitude da básica de alocação atribuída.</span><span class="sxs-lookup"><span data-stu-id="bf608-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="bf608-367">Defina a taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="bf608-367">Define the overhead rate</span></span>

<span data-ttu-id="bf608-368">O objeto de custo CC001 HR contribui para um conjunto de projetos internos.</span><span class="sxs-lookup"><span data-stu-id="bf608-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="bf608-369">Um membro de dimensão estatística que é chamado de projetos de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="bf608-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bf608-370">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-370">Cost object</span></span></th>
<th><span data-ttu-id="bf608-371">Horas</span><span class="sxs-lookup"><span data-stu-id="bf608-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-372">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="bf608-372">Proj 1</span></span></td>
<td><span data-ttu-id="bf608-373">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="bf608-373">Project 1</span></span></td>
<td><span data-ttu-id="bf608-374">3</span><span class="sxs-lookup"><span data-stu-id="bf608-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-375">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="bf608-375">Proj 2</span></span></td>
<td><span data-ttu-id="bf608-376">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="bf608-376">Project 2</span></span></td>
<td><span data-ttu-id="bf608-377">1</span><span class="sxs-lookup"><span data-stu-id="bf608-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bf608-378">Uma taxa de custo predeterminada da contribuição de projetos de custo foi definida.</span><span class="sxs-lookup"><span data-stu-id="bf608-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bf608-379">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-379">Cost object</span></span></th>
<th><span data-ttu-id="bf608-380">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-380">Cost element</span></span></th>
<th><span data-ttu-id="bf608-381">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-381">Cost behavior</span></span></th>
<th><span data-ttu-id="bf608-382">Unidades</span><span class="sxs-lookup"><span data-stu-id="bf608-382">Units</span></span></th>
<th><span data-ttu-id="bf608-383">Taxa</span><span class="sxs-lookup"><span data-stu-id="bf608-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-384">CC001</span><span class="sxs-lookup"><span data-stu-id="bf608-384">CC001</span></span></td>
<td><span data-ttu-id="bf608-385">RH</span><span class="sxs-lookup"><span data-stu-id="bf608-385">HR</span></span></td>
<td><span data-ttu-id="bf608-386">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-386">10001</span></span></td>
<td><span data-ttu-id="bf608-387">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-387">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-388">1</span><span class="sxs-lookup"><span data-stu-id="bf608-388">1</span></span></td>
<td><span data-ttu-id="bf608-389">10</span><span class="sxs-lookup"><span data-stu-id="bf608-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bf608-390">A tabela a seguir mostra o resultado quando projetos de RH são aplicados como base de alocação.</span><span class="sxs-lookup"><span data-stu-id="bf608-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bf608-391">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-391">Cost object</span></span></th>
<th><span data-ttu-id="bf608-392">Magnitude</span><span class="sxs-lookup"><span data-stu-id="bf608-392">Magnitude</span></span></th>
<th><span data-ttu-id="bf608-393">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-393">Cost element</span></span></th>
<th><span data-ttu-id="bf608-394">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="bf608-394">Allocation factor</span></span></th>
<th><span data-ttu-id="bf608-395">Valor</span><span class="sxs-lookup"><span data-stu-id="bf608-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-396">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="bf608-396">Proj 1</span></span></td>
<td><span data-ttu-id="bf608-397">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="bf608-397">Project 1</span></span></td>
<td><span data-ttu-id="bf608-398">3</span><span class="sxs-lookup"><span data-stu-id="bf608-398">3</span></span></td>
<td><span data-ttu-id="bf608-399">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-399">10001</span></span></td>
<td><span data-ttu-id="bf608-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="bf608-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="bf608-401">30,00</span><span class="sxs-lookup"><span data-stu-id="bf608-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-402">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="bf608-402">Proj 2</span></span></td>
<td><span data-ttu-id="bf608-403">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="bf608-403">Project 2</span></span></td>
<td><span data-ttu-id="bf608-404">1</span><span class="sxs-lookup"><span data-stu-id="bf608-404">1</span></span></td>
<td><span data-ttu-id="bf608-405">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-405">10001</span></span></td>
<td><span data-ttu-id="bf608-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="bf608-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="bf608-407">10,00</span><span class="sxs-lookup"><span data-stu-id="bf608-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="bf608-408">Diário</span><span class="sxs-lookup"><span data-stu-id="bf608-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bf608-409">Diário</span><span class="sxs-lookup"><span data-stu-id="bf608-409">Journal</span></span></th>
<th><span data-ttu-id="bf608-410">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="bf608-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="bf608-411">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="bf608-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="bf608-412">Versão</span><span class="sxs-lookup"><span data-stu-id="bf608-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-413">00003</span><span class="sxs-lookup"><span data-stu-id="bf608-413">00003</span></span></td>
<td><span data-ttu-id="bf608-414">Diário de cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="bf608-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="bf608-415">fiscal</span><span class="sxs-lookup"><span data-stu-id="bf608-415">Fiscal</span></span></td>
<td><span data-ttu-id="bf608-416">2017</span><span class="sxs-lookup"><span data-stu-id="bf608-416">2017</span></span></td>
<td><span data-ttu-id="bf608-417">Período 1</span><span class="sxs-lookup"><span data-stu-id="bf608-417">Period 1</span></span></td>
<td><span data-ttu-id="bf608-418">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="bf608-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="bf608-419">Entradas de diário (As entradas de diário para cálculo da taxa de custos indiretos)</span><span class="sxs-lookup"><span data-stu-id="bf608-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bf608-420">Data contábil</span><span class="sxs-lookup"><span data-stu-id="bf608-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="bf608-421">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-421">Cost object</span></span></th>
<th><span data-ttu-id="bf608-422">Magnitude</span><span class="sxs-lookup"><span data-stu-id="bf608-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-423">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="bf608-424">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="bf608-424">Proj 1</span></span></td>
<td><span data-ttu-id="bf608-425">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="bf608-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="bf608-426">3,00</span><span class="sxs-lookup"><span data-stu-id="bf608-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-427">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="bf608-428">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="bf608-428">Proj 2</span></span></td>
<td><span data-ttu-id="bf608-429">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="bf608-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="bf608-430">1.00</span><span class="sxs-lookup"><span data-stu-id="bf608-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="bf608-431">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bf608-432">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="bf608-433">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-433">Cost element</span></span></th>
<th><span data-ttu-id="bf608-434">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-434">Cost behavior</span></span></th>
<th><span data-ttu-id="bf608-435">Valor</span><span class="sxs-lookup"><span data-stu-id="bf608-435">Amount</span></span></th>
<th><span data-ttu-id="bf608-436">Data contábil</span><span class="sxs-lookup"><span data-stu-id="bf608-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="bf608-437">CC0001</span></span></td>
<td><span data-ttu-id="bf608-438">RH</span><span class="sxs-lookup"><span data-stu-id="bf608-438">HR</span></span></td>
<td><span data-ttu-id="bf608-439">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-439">10001</span></span></td>
<td><span data-ttu-id="bf608-440">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-440">Electricity</span></span></td>
<td><span data-ttu-id="bf608-441">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-441">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="bf608-442">-30.00</span></span></td>
<td><span data-ttu-id="bf608-443">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-444">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="bf608-444">Proj 1</span></span></td>
<td><span data-ttu-id="bf608-445">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="bf608-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="bf608-446">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-446">10001</span></span></td>
<td><span data-ttu-id="bf608-447">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-447">Electricity</span></span></td>
<td><span data-ttu-id="bf608-448">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-448">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-449">30,00</span><span class="sxs-lookup"><span data-stu-id="bf608-449">30.00</span></span></td>
<td><span data-ttu-id="bf608-450">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-451">CC001</span><span class="sxs-lookup"><span data-stu-id="bf608-451">CC001</span></span></td>
<td><span data-ttu-id="bf608-452">RH</span><span class="sxs-lookup"><span data-stu-id="bf608-452">HR</span></span></td>
<td><span data-ttu-id="bf608-453">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-453">10001</span></span></td>
<td><span data-ttu-id="bf608-454">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-454">Electricity</span></span></td>
<td><span data-ttu-id="bf608-455">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-455">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="bf608-456">-10.00</span></span></td>
<td><span data-ttu-id="bf608-457">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-458">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="bf608-458">Proj 2</span></span></td>
<td><span data-ttu-id="bf608-459">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="bf608-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="bf608-460">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-460">10001</span></span></td>
<td><span data-ttu-id="bf608-461">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-461">Electricity</span></span></td>
<td><span data-ttu-id="bf608-462">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-462">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-463">10,00</span><span class="sxs-lookup"><span data-stu-id="bf608-463">10.00</span></span></td>
<td><span data-ttu-id="bf608-464">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bf608-465">Para obter mais informações, consulte [Realizar cálculo de custos indiretos](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="bf608-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="bf608-466">Etapa 4: Processar o cálculo de alocação de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="bf608-467">A alocação é usada para alocar o saldo de um objeto de custo a outros objetos de custo pela aplicação de uma base de alocação.</span><span class="sxs-lookup"><span data-stu-id="bf608-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="bf608-468">O Finance and Operations oferece suporte ao método de alocação recíproco.</span><span class="sxs-lookup"><span data-stu-id="bf608-468">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="bf608-469">No método de alocação recíproco, os serviços mútuos que os objetos de custo auxiliar trocam são totalmente reconhecidos.</span><span class="sxs-lookup"><span data-stu-id="bf608-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="bf608-470">O sistema determina automaticamente a ordem correta realizar as alocações.</span><span class="sxs-lookup"><span data-stu-id="bf608-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="bf608-471">O saldo de um objeto de custo é alocado por uma base de alocação única.</span><span class="sxs-lookup"><span data-stu-id="bf608-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="bf608-472">As alocações entre as dimensões de objetos de custo e os respectivos membros são suportadas.</span><span class="sxs-lookup"><span data-stu-id="bf608-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="bf608-473">A ordem de alocação é controlada pela unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="bf608-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="bf608-474">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="bf608-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="bf608-475">Defina a alocação de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-475">Define the cost allocation</span></span>

<span data-ttu-id="bf608-476">Aqui está um exemplo simples que explica como você pode rastrear o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="bf608-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="bf608-477">O objeto de custo previsto CC001 HR contribui a vários objetos de custo previsto.</span><span class="sxs-lookup"><span data-stu-id="bf608-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="bf608-478">Um membro de dimensão estatística que é chamado de serviços de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="bf608-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bf608-479">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-479">Cost object</span></span></th>
<th><span data-ttu-id="bf608-480">Serviços de RH</span><span class="sxs-lookup"><span data-stu-id="bf608-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-481">CC002</span><span class="sxs-lookup"><span data-stu-id="bf608-481">CC002</span></span></td>
<td><span data-ttu-id="bf608-482">Finanças</span><span class="sxs-lookup"><span data-stu-id="bf608-482">Finance</span></span></td>
<td><span data-ttu-id="bf608-483">35</span><span class="sxs-lookup"><span data-stu-id="bf608-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-484">CC003</span><span class="sxs-lookup"><span data-stu-id="bf608-484">CC003</span></span></td>
<td><span data-ttu-id="bf608-485">Montagem</span><span class="sxs-lookup"><span data-stu-id="bf608-485">Assembly</span></span></td>
<td><span data-ttu-id="bf608-486">55</span><span class="sxs-lookup"><span data-stu-id="bf608-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-487">CC004</span><span class="sxs-lookup"><span data-stu-id="bf608-487">CC004</span></span></td>
<td><span data-ttu-id="bf608-488">Embalagem</span><span class="sxs-lookup"><span data-stu-id="bf608-488">Packaging</span></span></td>
<td><span data-ttu-id="bf608-489">10</span><span class="sxs-lookup"><span data-stu-id="bf608-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bf608-490">O objeto de custo CC002 Finanças contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="bf608-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="bf608-491">Um membro de dimensão estatística que é chamado de serviços de Finanças foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="bf608-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bf608-492">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-492">Cost object</span></span></th>
<th><span data-ttu-id="bf608-493">Serviços financeiros</span><span class="sxs-lookup"><span data-stu-id="bf608-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-494">CC003</span><span class="sxs-lookup"><span data-stu-id="bf608-494">CC003</span></span></td>
<td><span data-ttu-id="bf608-495">Montagem</span><span class="sxs-lookup"><span data-stu-id="bf608-495">Assembly</span></span></td>
<td><span data-ttu-id="bf608-496">65</span><span class="sxs-lookup"><span data-stu-id="bf608-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-497">CC004</span><span class="sxs-lookup"><span data-stu-id="bf608-497">CC004</span></span></td>
<td><span data-ttu-id="bf608-498">Embalagem</span><span class="sxs-lookup"><span data-stu-id="bf608-498">Packaging</span></span></td>
<td><span data-ttu-id="bf608-499">35</span><span class="sxs-lookup"><span data-stu-id="bf608-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bf608-500">O objeto de custo CC003 Montagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="bf608-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="bf608-501">Um membro de dimensão estatística que é chamado de serviços de Montagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="bf608-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bf608-502">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-502">Cost object</span></span></th>
<th><span data-ttu-id="bf608-503">Serviços de montagem (horas)</span><span class="sxs-lookup"><span data-stu-id="bf608-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-504">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="bf608-504">Prod 1</span></span></td>
<td><span data-ttu-id="bf608-505">Produto 1</span><span class="sxs-lookup"><span data-stu-id="bf608-505">Product 1</span></span></td>
<td><span data-ttu-id="bf608-506">60</span><span class="sxs-lookup"><span data-stu-id="bf608-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-507">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="bf608-507">Prod 2</span></span></td>
<td><span data-ttu-id="bf608-508">Produto 2</span><span class="sxs-lookup"><span data-stu-id="bf608-508">Product 2</span></span></td>
<td><span data-ttu-id="bf608-509">20</span><span class="sxs-lookup"><span data-stu-id="bf608-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bf608-510">O objeto de custo CC004 Embalagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="bf608-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="bf608-511">Um membro de dimensão estatística que é chamado de serviços de Embalagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="bf608-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bf608-512">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-512">Cost object</span></span></th>
<th><span data-ttu-id="bf608-513">Serviços de embalagem (horas)</span><span class="sxs-lookup"><span data-stu-id="bf608-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-514">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="bf608-514">Prod 1</span></span></td>
<td><span data-ttu-id="bf608-515">Produto 1</span><span class="sxs-lookup"><span data-stu-id="bf608-515">Product 1</span></span></td>
<td><span data-ttu-id="bf608-516">80</span><span class="sxs-lookup"><span data-stu-id="bf608-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-517">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="bf608-517">Prod 2</span></span></td>
<td><span data-ttu-id="bf608-518">Produto 2</span><span class="sxs-lookup"><span data-stu-id="bf608-518">Product 2</span></span></td>
<td><span data-ttu-id="bf608-519">15</span><span class="sxs-lookup"><span data-stu-id="bf608-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="bf608-520">No Finance and Operations, as medidas estatísticas, como as horas de produção que um produto consome, podem ser derivadas dos dados de origem.</span><span class="sxs-lookup"><span data-stu-id="bf608-520">In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="bf608-521">Para obter mais informações, consulte [Modelo de provedor de medidas estatísticas](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="bf608-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="bf608-522">A tabela a seguir mostra o resultado quando os serviços de RH são aplicados como base de alocação para custos totais (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="bf608-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bf608-523">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-523">Cost object</span></span></th>
<th><span data-ttu-id="bf608-524">Magnitude</span><span class="sxs-lookup"><span data-stu-id="bf608-524">Magnitude</span></span></th>
<th><span data-ttu-id="bf608-525">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="bf608-525">Allocation factor</span></span></th>
<th><span data-ttu-id="bf608-526">Valor</span><span class="sxs-lookup"><span data-stu-id="bf608-526">Amount</span></span></th>
<th><span data-ttu-id="bf608-527">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-528">CC002</span><span class="sxs-lookup"><span data-stu-id="bf608-528">CC002</span></span></td>
<td><span data-ttu-id="bf608-529">Finanças</span><span class="sxs-lookup"><span data-stu-id="bf608-529">Finance</span></span></td>
<td><span data-ttu-id="bf608-530">35</span><span class="sxs-lookup"><span data-stu-id="bf608-530">35</span></span></td>
<td><span data-ttu-id="bf608-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="bf608-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="bf608-532">175.00</span><span class="sxs-lookup"><span data-stu-id="bf608-532">175.00</span></span></td>
<td><span data-ttu-id="bf608-533">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-534">CC003</span><span class="sxs-lookup"><span data-stu-id="bf608-534">CC003</span></span></td>
<td><span data-ttu-id="bf608-535">Montagem</span><span class="sxs-lookup"><span data-stu-id="bf608-535">Assembly</span></span></td>
<td><span data-ttu-id="bf608-536">55</span><span class="sxs-lookup"><span data-stu-id="bf608-536">55</span></span></td>
<td><span data-ttu-id="bf608-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="bf608-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="bf608-538">275.00</span><span class="sxs-lookup"><span data-stu-id="bf608-538">275.00</span></span></td>
<td><span data-ttu-id="bf608-539">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-540">CC004</span><span class="sxs-lookup"><span data-stu-id="bf608-540">CC004</span></span></td>
<td><span data-ttu-id="bf608-541">Embalagem</span><span class="sxs-lookup"><span data-stu-id="bf608-541">Packaging</span></span></td>
<td><span data-ttu-id="bf608-542">10</span><span class="sxs-lookup"><span data-stu-id="bf608-542">10</span></span></td>
<td><span data-ttu-id="bf608-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="bf608-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="bf608-544">50,00</span><span class="sxs-lookup"><span data-stu-id="bf608-544">50.00</span></span></td>
<td><span data-ttu-id="bf608-545">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-546">CC002</span><span class="sxs-lookup"><span data-stu-id="bf608-546">CC002</span></span></td>
<td><span data-ttu-id="bf608-547">Finanças</span><span class="sxs-lookup"><span data-stu-id="bf608-547">Finance</span></span></td>
<td><span data-ttu-id="bf608-548">35</span><span class="sxs-lookup"><span data-stu-id="bf608-548">35</span></span></td>
<td><span data-ttu-id="bf608-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="bf608-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="bf608-550">436.00</span><span class="sxs-lookup"><span data-stu-id="bf608-550">436.00</span></span></td>
<td><span data-ttu-id="bf608-551">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-552">CC003</span><span class="sxs-lookup"><span data-stu-id="bf608-552">CC003</span></span></td>
<td><span data-ttu-id="bf608-553">Montagem</span><span class="sxs-lookup"><span data-stu-id="bf608-553">Assembly</span></span></td>
<td><span data-ttu-id="bf608-554">55</span><span class="sxs-lookup"><span data-stu-id="bf608-554">55</span></span></td>
<td><span data-ttu-id="bf608-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="bf608-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="bf608-556">685.14</span><span class="sxs-lookup"><span data-stu-id="bf608-556">685.14</span></span></td>
<td><span data-ttu-id="bf608-557">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-558">CC004</span><span class="sxs-lookup"><span data-stu-id="bf608-558">CC004</span></span></td>
<td><span data-ttu-id="bf608-559">Embalagem</span><span class="sxs-lookup"><span data-stu-id="bf608-559">Packaging</span></span></td>
<td><span data-ttu-id="bf608-560">10</span><span class="sxs-lookup"><span data-stu-id="bf608-560">10</span></span></td>
<td><span data-ttu-id="bf608-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="bf608-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="bf608-562">124.57</span><span class="sxs-lookup"><span data-stu-id="bf608-562">124.57</span></span></td>
<td><span data-ttu-id="bf608-563">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bf608-564">A tabela a seguir mostra o resultado quando os serviços financeiros são aplicados como base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="bf608-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bf608-565">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-565">Cost object</span></span></th>
<th><span data-ttu-id="bf608-566">Magnitude</span><span class="sxs-lookup"><span data-stu-id="bf608-566">Magnitude</span></span></th>
<th><span data-ttu-id="bf608-567">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="bf608-567">Allocation factor</span></span></th>
<th><span data-ttu-id="bf608-568">Valor</span><span class="sxs-lookup"><span data-stu-id="bf608-568">Amount</span></span></th>
<th><span data-ttu-id="bf608-569">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-570">CC003</span><span class="sxs-lookup"><span data-stu-id="bf608-570">CC003</span></span></td>
<td><span data-ttu-id="bf608-571">Montagem</span><span class="sxs-lookup"><span data-stu-id="bf608-571">Assembly</span></span></td>
<td><span data-ttu-id="bf608-572">65</span><span class="sxs-lookup"><span data-stu-id="bf608-572">65</span></span></td>
<td><span data-ttu-id="bf608-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="bf608-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="bf608-574">438.75</span><span class="sxs-lookup"><span data-stu-id="bf608-574">438.75</span></span></td>
<td><span data-ttu-id="bf608-575">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-576">CC004</span><span class="sxs-lookup"><span data-stu-id="bf608-576">CC004</span></span></td>
<td><span data-ttu-id="bf608-577">Embalagem</span><span class="sxs-lookup"><span data-stu-id="bf608-577">Packaging</span></span></td>
<td><span data-ttu-id="bf608-578">35</span><span class="sxs-lookup"><span data-stu-id="bf608-578">35</span></span></td>
<td><span data-ttu-id="bf608-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="bf608-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="bf608-580">236.25</span><span class="sxs-lookup"><span data-stu-id="bf608-580">236.25</span></span></td>
<td><span data-ttu-id="bf608-581">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-582">CC003</span><span class="sxs-lookup"><span data-stu-id="bf608-582">CC003</span></span></td>
<td><span data-ttu-id="bf608-583">Montagem</span><span class="sxs-lookup"><span data-stu-id="bf608-583">Assembly</span></span></td>
<td><span data-ttu-id="bf608-584">65</span><span class="sxs-lookup"><span data-stu-id="bf608-584">65</span></span></td>
<td><span data-ttu-id="bf608-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="bf608-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="bf608-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="bf608-586">5,297.69</span></span></td>
<td><span data-ttu-id="bf608-587">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-588">CC004</span><span class="sxs-lookup"><span data-stu-id="bf608-588">CC004</span></span></td>
<td><span data-ttu-id="bf608-589">Embalagem</span><span class="sxs-lookup"><span data-stu-id="bf608-589">Packaging</span></span></td>
<td><span data-ttu-id="bf608-590">35</span><span class="sxs-lookup"><span data-stu-id="bf608-590">35</span></span></td>
<td><span data-ttu-id="bf608-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="bf608-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="bf608-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="bf608-592">2,852.60</span></span></td>
<td><span data-ttu-id="bf608-593">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bf608-594">A tabela a seguir mostra o resultado quando os serviços de Montagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="bf608-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bf608-595">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-595">Cost object</span></span></th>
<th><span data-ttu-id="bf608-596">Magnitude</span><span class="sxs-lookup"><span data-stu-id="bf608-596">Magnitude</span></span></th>
<th><span data-ttu-id="bf608-597">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="bf608-597">Allocation factor</span></span></th>
<th><span data-ttu-id="bf608-598">Valor</span><span class="sxs-lookup"><span data-stu-id="bf608-598">Amount</span></span></th>
<th><span data-ttu-id="bf608-599">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-600">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="bf608-600">Prod 1</span></span></td>
<td><span data-ttu-id="bf608-601">Produto 1</span><span class="sxs-lookup"><span data-stu-id="bf608-601">Product 1</span></span></td>
<td><span data-ttu-id="bf608-602">60</span><span class="sxs-lookup"><span data-stu-id="bf608-602">60</span></span></td>
<td><span data-ttu-id="bf608-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="bf608-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="bf608-604">535.31</span><span class="sxs-lookup"><span data-stu-id="bf608-604">535.31</span></span></td>
<td><span data-ttu-id="bf608-605">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-606">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="bf608-606">Prod 2</span></span></td>
<td><span data-ttu-id="bf608-607">Produto 2</span><span class="sxs-lookup"><span data-stu-id="bf608-607">Product 2</span></span></td>
<td><span data-ttu-id="bf608-608">20</span><span class="sxs-lookup"><span data-stu-id="bf608-608">20</span></span></td>
<td><span data-ttu-id="bf608-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="bf608-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="bf608-610">178.44</span><span class="sxs-lookup"><span data-stu-id="bf608-610">178.44</span></span></td>
<td><span data-ttu-id="bf608-611">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-612">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="bf608-612">Prod 1</span></span></td>
<td><span data-ttu-id="bf608-613">Produto 1</span><span class="sxs-lookup"><span data-stu-id="bf608-613">Product 1</span></span></td>
<td><span data-ttu-id="bf608-614">60</span><span class="sxs-lookup"><span data-stu-id="bf608-614">60</span></span></td>
<td><span data-ttu-id="bf608-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="bf608-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="bf608-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="bf608-616">4,487.12</span></span></td>
<td><span data-ttu-id="bf608-617">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-618">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="bf608-618">Prod 2</span></span></td>
<td><span data-ttu-id="bf608-619">Produto 2</span><span class="sxs-lookup"><span data-stu-id="bf608-619">Product 2</span></span></td>
<td><span data-ttu-id="bf608-620">20</span><span class="sxs-lookup"><span data-stu-id="bf608-620">20</span></span></td>
<td><span data-ttu-id="bf608-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="bf608-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="bf608-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="bf608-622">1,495.71</span></span></td>
<td><span data-ttu-id="bf608-623">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bf608-624">A tabela a seguir mostra o resultado quando os serviços de Embalagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="bf608-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bf608-625">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-625">Cost object</span></span></th>
<th><span data-ttu-id="bf608-626">Magnitude</span><span class="sxs-lookup"><span data-stu-id="bf608-626">Magnitude</span></span></th>
<th><span data-ttu-id="bf608-627">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="bf608-627">Allocation factor</span></span></th>
<th><span data-ttu-id="bf608-628">Valor</span><span class="sxs-lookup"><span data-stu-id="bf608-628">Amount</span></span></th>
<th><span data-ttu-id="bf608-629">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-630">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="bf608-630">Prod 1</span></span></td>
<td><span data-ttu-id="bf608-631">Produto 1</span><span class="sxs-lookup"><span data-stu-id="bf608-631">Product 1</span></span></td>
<td><span data-ttu-id="bf608-632">80</span><span class="sxs-lookup"><span data-stu-id="bf608-632">80</span></span></td>
<td><span data-ttu-id="bf608-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="bf608-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="bf608-634">241.05</span><span class="sxs-lookup"><span data-stu-id="bf608-634">241.05</span></span></td>
<td><span data-ttu-id="bf608-635">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-636">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="bf608-636">Prod 2</span></span></td>
<td><span data-ttu-id="bf608-637">Produto 2</span><span class="sxs-lookup"><span data-stu-id="bf608-637">Product 2</span></span></td>
<td><span data-ttu-id="bf608-638">15</span><span class="sxs-lookup"><span data-stu-id="bf608-638">15</span></span></td>
<td><span data-ttu-id="bf608-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="bf608-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="bf608-640">45.20</span><span class="sxs-lookup"><span data-stu-id="bf608-640">45.20</span></span></td>
<td><span data-ttu-id="bf608-641">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-642">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="bf608-642">Prod 1</span></span></td>
<td><span data-ttu-id="bf608-643">Produto 1</span><span class="sxs-lookup"><span data-stu-id="bf608-643">Product 1</span></span></td>
<td><span data-ttu-id="bf608-644">80</span><span class="sxs-lookup"><span data-stu-id="bf608-644">80</span></span></td>
<td><span data-ttu-id="bf608-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="bf608-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="bf608-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="bf608-646">2,507.09</span></span></td>
<td><span data-ttu-id="bf608-647">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-648">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="bf608-648">Prod 2</span></span></td>
<td><span data-ttu-id="bf608-649">Produto 2</span><span class="sxs-lookup"><span data-stu-id="bf608-649">Product 2</span></span></td>
<td><span data-ttu-id="bf608-650">15</span><span class="sxs-lookup"><span data-stu-id="bf608-650">15</span></span></td>
<td><span data-ttu-id="bf608-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="bf608-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="bf608-652">470.08</span><span class="sxs-lookup"><span data-stu-id="bf608-652">470.08</span></span></td>
<td><span data-ttu-id="bf608-653">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="bf608-654">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="bf608-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bf608-655">Diário</span><span class="sxs-lookup"><span data-stu-id="bf608-655">Journal</span></span></th>
<th><span data-ttu-id="bf608-656">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="bf608-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="bf608-657">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="bf608-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="bf608-658">Versão</span><span class="sxs-lookup"><span data-stu-id="bf608-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-659">00004</span><span class="sxs-lookup"><span data-stu-id="bf608-659">00004</span></span></td>
<td><span data-ttu-id="bf608-660">Diário de alocação de custos</span><span class="sxs-lookup"><span data-stu-id="bf608-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="bf608-661">fiscal</span><span class="sxs-lookup"><span data-stu-id="bf608-661">Fiscal</span></span></td>
<td><span data-ttu-id="bf608-662">2017</span><span class="sxs-lookup"><span data-stu-id="bf608-662">2017</span></span></td>
<td><span data-ttu-id="bf608-663">Período 1</span><span class="sxs-lookup"><span data-stu-id="bf608-663">Period 1</span></span></td>
<td><span data-ttu-id="bf608-664">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="bf608-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="bf608-665">Linhas do diário</span><span class="sxs-lookup"><span data-stu-id="bf608-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bf608-666">Data contábil</span><span class="sxs-lookup"><span data-stu-id="bf608-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="bf608-667">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="bf608-668">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-668">Cost element</span></span></th>
<th><span data-ttu-id="bf608-669">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-669">Cost behavior</span></span></th>
<th><span data-ttu-id="bf608-670">Valor</span><span class="sxs-lookup"><span data-stu-id="bf608-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-671">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="bf608-672">CC001</span><span class="sxs-lookup"><span data-stu-id="bf608-672">CC001</span></span></td>
<td><span data-ttu-id="bf608-673">RH</span><span class="sxs-lookup"><span data-stu-id="bf608-673">HR</span></span></td>
<td><span data-ttu-id="bf608-674">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-674">10001</span></span></td>
<td><span data-ttu-id="bf608-675">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-675">Electricity</span></span></td>
<td><span data-ttu-id="bf608-676">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-676">Fixed cost</span></span></td>
<td><span data-ttu-id="bf608-677">500,00</span><span class="sxs-lookup"><span data-stu-id="bf608-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-678">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="bf608-679">CC001</span><span class="sxs-lookup"><span data-stu-id="bf608-679">CC001</span></span></td>
<td><span data-ttu-id="bf608-680">RH</span><span class="sxs-lookup"><span data-stu-id="bf608-680">HR</span></span></td>
<td><span data-ttu-id="bf608-681">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-681">10001</span></span></td>
<td><span data-ttu-id="bf608-682">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-682">Electricity</span></span></td>
<td><span data-ttu-id="bf608-683">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-683">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="bf608-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-685">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="bf608-686">CC002</span><span class="sxs-lookup"><span data-stu-id="bf608-686">CC002</span></span></td>
<td><span data-ttu-id="bf608-687">Finanças</span><span class="sxs-lookup"><span data-stu-id="bf608-687">Finance</span></span></td>
<td><span data-ttu-id="bf608-688">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-688">10001</span></span></td>
<td><span data-ttu-id="bf608-689">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-689">Electricity</span></span></td>
<td><span data-ttu-id="bf608-690">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-690">Fixed cost</span></span></td>
<td><span data-ttu-id="bf608-691">675.00</span><span class="sxs-lookup"><span data-stu-id="bf608-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-692">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="bf608-693">CC002</span><span class="sxs-lookup"><span data-stu-id="bf608-693">CC002</span></span></td>
<td><span data-ttu-id="bf608-694">Finanças</span><span class="sxs-lookup"><span data-stu-id="bf608-694">Finance</span></span></td>
<td><span data-ttu-id="bf608-695">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-695">10001</span></span></td>
<td><span data-ttu-id="bf608-696">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-696">Electricity</span></span></td>
<td><span data-ttu-id="bf608-697">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-697">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="bf608-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-699">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="bf608-700">CC003</span><span class="sxs-lookup"><span data-stu-id="bf608-700">CC003</span></span></td>
<td><span data-ttu-id="bf608-701">Montagem</span><span class="sxs-lookup"><span data-stu-id="bf608-701">Assembly</span></span></td>
<td><span data-ttu-id="bf608-702">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-702">10001</span></span></td>
<td><span data-ttu-id="bf608-703">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-703">Electricity</span></span></td>
<td><span data-ttu-id="bf608-704">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-704">Fixed cost</span></span></td>
<td><span data-ttu-id="bf608-705">713.75</span><span class="sxs-lookup"><span data-stu-id="bf608-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-706">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="bf608-707">CC003</span><span class="sxs-lookup"><span data-stu-id="bf608-707">CC003</span></span></td>
<td><span data-ttu-id="bf608-708">Montagem</span><span class="sxs-lookup"><span data-stu-id="bf608-708">Assembly</span></span></td>
<td><span data-ttu-id="bf608-709">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-709">10001</span></span></td>
<td><span data-ttu-id="bf608-710">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-710">Electricity</span></span></td>
<td><span data-ttu-id="bf608-711">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-711">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="bf608-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-713">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="bf608-714">CC003</span><span class="sxs-lookup"><span data-stu-id="bf608-714">CC003</span></span></td>
<td><span data-ttu-id="bf608-715">Embalagem</span><span class="sxs-lookup"><span data-stu-id="bf608-715">Packaging</span></span></td>
<td><span data-ttu-id="bf608-716">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-716">10001</span></span></td>
<td><span data-ttu-id="bf608-717">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-717">Electricity</span></span></td>
<td><span data-ttu-id="bf608-718">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-718">Fixed cost</span></span></td>
<td><span data-ttu-id="bf608-719">286.25</span><span class="sxs-lookup"><span data-stu-id="bf608-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-720">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="bf608-721">CC003</span><span class="sxs-lookup"><span data-stu-id="bf608-721">CC003</span></span></td>
<td><span data-ttu-id="bf608-722">Embalagem</span><span class="sxs-lookup"><span data-stu-id="bf608-722">Packaging</span></span></td>
<td><span data-ttu-id="bf608-723">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-723">10001</span></span></td>
<td><span data-ttu-id="bf608-724">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-724">Electricity</span></span></td>
<td><span data-ttu-id="bf608-725">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-725">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="bf608-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-727">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="bf608-728">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="bf608-728">Prod 1</span></span></td>
<td><span data-ttu-id="bf608-729">Produto 1</span><span class="sxs-lookup"><span data-stu-id="bf608-729">Product 1</span></span></td>
<td><span data-ttu-id="bf608-730">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-730">10001</span></span></td>
<td><span data-ttu-id="bf608-731">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-731">Electricity</span></span></td>
<td><span data-ttu-id="bf608-732">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-732">Fixed cost</span></span></td>
<td><span data-ttu-id="bf608-733">776.36</span><span class="sxs-lookup"><span data-stu-id="bf608-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-734">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="bf608-735">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="bf608-735">Prod 1</span></span></td>
<td><span data-ttu-id="bf608-736">Produto 1</span><span class="sxs-lookup"><span data-stu-id="bf608-736">Product 1</span></span></td>
<td><span data-ttu-id="bf608-737">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-737">10001</span></span></td>
<td><span data-ttu-id="bf608-738">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-738">Electricity</span></span></td>
<td><span data-ttu-id="bf608-739">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-739">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="bf608-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-741">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="bf608-742">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="bf608-742">Prod 2</span></span></td>
<td><span data-ttu-id="bf608-743">Produto 1</span><span class="sxs-lookup"><span data-stu-id="bf608-743">Product 1</span></span></td>
<td><span data-ttu-id="bf608-744">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-744">10001</span></span></td>
<td><span data-ttu-id="bf608-745">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-745">Electricity</span></span></td>
<td><span data-ttu-id="bf608-746">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-746">Fixed cost</span></span></td>
<td><span data-ttu-id="bf608-747">223.64</span><span class="sxs-lookup"><span data-stu-id="bf608-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-748">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="bf608-749">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="bf608-749">Prod 2</span></span></td>
<td><span data-ttu-id="bf608-750">Produto 1</span><span class="sxs-lookup"><span data-stu-id="bf608-750">Product 1</span></span></td>
<td><span data-ttu-id="bf608-751">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-751">10001</span></span></td>
<td><span data-ttu-id="bf608-752">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-752">Electricity</span></span></td>
<td><span data-ttu-id="bf608-753">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-753">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="bf608-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="bf608-755">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="bf608-756">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="bf608-757">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-757">Cost element</span></span></th>
<th><span data-ttu-id="bf608-758">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-758">Cost behavior</span></span></th>
<th><span data-ttu-id="bf608-759">Valor</span><span class="sxs-lookup"><span data-stu-id="bf608-759">Amount</span></span></th>
<th><span data-ttu-id="bf608-760">Data contábil</span><span class="sxs-lookup"><span data-stu-id="bf608-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bf608-761">CC001</span><span class="sxs-lookup"><span data-stu-id="bf608-761">CC001</span></span></td>
<td><span data-ttu-id="bf608-762">RH</span><span class="sxs-lookup"><span data-stu-id="bf608-762">HR</span></span></td>
<td><span data-ttu-id="bf608-763">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-763">10001</span></span></td>
<td><span data-ttu-id="bf608-764">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-764">Electricity</span></span></td>
<td><span data-ttu-id="bf608-765">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-765">Fixed cost</span></span></td>
<td><span data-ttu-id="bf608-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="bf608-766">-500.00</span></span></td>
<td><span data-ttu-id="bf608-767">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-768">CC002</span><span class="sxs-lookup"><span data-stu-id="bf608-768">CC002</span></span></td>
<td><span data-ttu-id="bf608-769">Finanças</span><span class="sxs-lookup"><span data-stu-id="bf608-769">Finance</span></span></td>
<td><span data-ttu-id="bf608-770">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-770">10001</span></span></td>
<td><span data-ttu-id="bf608-771">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-771">Electricity</span></span></td>
<td><span data-ttu-id="bf608-772">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-772">Fixed cost</span></span></td>
<td><span data-ttu-id="bf608-773">175.00</span><span class="sxs-lookup"><span data-stu-id="bf608-773">175.00</span></span></td>
<td><span data-ttu-id="bf608-774">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-775">CC003</span><span class="sxs-lookup"><span data-stu-id="bf608-775">CC003</span></span></td>
<td><span data-ttu-id="bf608-776">Montagem</span><span class="sxs-lookup"><span data-stu-id="bf608-776">Assembly</span></span></td>
<td><span data-ttu-id="bf608-777">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-777">10001</span></span></td>
<td><span data-ttu-id="bf608-778">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-778">Electricity</span></span></td>
<td><span data-ttu-id="bf608-779">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-779">Fixed cost</span></span></td>
<td><span data-ttu-id="bf608-780">275.00</span><span class="sxs-lookup"><span data-stu-id="bf608-780">275.00</span></span></td>
<td><span data-ttu-id="bf608-781">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-782">CC004</span><span class="sxs-lookup"><span data-stu-id="bf608-782">CC004</span></span></td>
<td><span data-ttu-id="bf608-783">Embalagem</span><span class="sxs-lookup"><span data-stu-id="bf608-783">Packaging</span></span></td>
<td><span data-ttu-id="bf608-784">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-784">10001</span></span></td>
<td><span data-ttu-id="bf608-785">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-785">Electricity</span></span></td>
<td><span data-ttu-id="bf608-786">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-786">Fixed cost</span></span></td>
<td><span data-ttu-id="bf608-787">50,00</span><span class="sxs-lookup"><span data-stu-id="bf608-787">50,00</span></span></td>
<td><span data-ttu-id="bf608-788">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-789">CC001</span><span class="sxs-lookup"><span data-stu-id="bf608-789">CC001</span></span></td>
<td><span data-ttu-id="bf608-790">RH</span><span class="sxs-lookup"><span data-stu-id="bf608-790">HR</span></span></td>
<td><span data-ttu-id="bf608-791">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-791">10001</span></span></td>
<td><span data-ttu-id="bf608-792">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-792">Electricity</span></span></td>
<td><span data-ttu-id="bf608-793">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-793">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="bf608-794">-1,245.71</span></span></td>
<td><span data-ttu-id="bf608-795">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-796">CC002</span><span class="sxs-lookup"><span data-stu-id="bf608-796">CC002</span></span></td>
<td><span data-ttu-id="bf608-797">Finanças</span><span class="sxs-lookup"><span data-stu-id="bf608-797">Finance</span></span></td>
<td><span data-ttu-id="bf608-798">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-798">10001</span></span></td>
<td><span data-ttu-id="bf608-799">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-799">Electricity</span></span></td>
<td><span data-ttu-id="bf608-800">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-800">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-801">436.00</span><span class="sxs-lookup"><span data-stu-id="bf608-801">436.00</span></span></td>
<td><span data-ttu-id="bf608-802">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-803">CC003</span><span class="sxs-lookup"><span data-stu-id="bf608-803">CC003</span></span></td>
<td><span data-ttu-id="bf608-804">Montagem</span><span class="sxs-lookup"><span data-stu-id="bf608-804">Assembly</span></span></td>
<td><span data-ttu-id="bf608-805">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-805">10001</span></span></td>
<td><span data-ttu-id="bf608-806">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-806">Electricity</span></span></td>
<td><span data-ttu-id="bf608-807">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-807">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-808">685.14</span><span class="sxs-lookup"><span data-stu-id="bf608-808">685.14</span></span></td>
<td><span data-ttu-id="bf608-809">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-810">CC004</span><span class="sxs-lookup"><span data-stu-id="bf608-810">CC004</span></span></td>
<td><span data-ttu-id="bf608-811">Embalagem</span><span class="sxs-lookup"><span data-stu-id="bf608-811">Packaging</span></span></td>
<td><span data-ttu-id="bf608-812">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-812">10001</span></span></td>
<td><span data-ttu-id="bf608-813">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-813">Electricity</span></span></td>
<td><span data-ttu-id="bf608-814">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-814">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-815">124.57</span><span class="sxs-lookup"><span data-stu-id="bf608-815">124.57</span></span></td>
<td><span data-ttu-id="bf608-816">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-817">CC002</span><span class="sxs-lookup"><span data-stu-id="bf608-817">CC002</span></span></td>
<td><span data-ttu-id="bf608-818">Finanças</span><span class="sxs-lookup"><span data-stu-id="bf608-818">Finance</span></span></td>
<td><span data-ttu-id="bf608-819">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-819">10001</span></span></td>
<td><span data-ttu-id="bf608-820">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-820">Electricity</span></span></td>
<td><span data-ttu-id="bf608-821">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-821">Fixed cost</span></span></td>
<td><span data-ttu-id="bf608-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="bf608-822">-675.00</span></span></td>
<td><span data-ttu-id="bf608-823">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-824">CC003</span><span class="sxs-lookup"><span data-stu-id="bf608-824">CC003</span></span></td>
<td><span data-ttu-id="bf608-825">Montagem</span><span class="sxs-lookup"><span data-stu-id="bf608-825">Assembly</span></span></td>
<td><span data-ttu-id="bf608-826">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-826">10001</span></span></td>
<td><span data-ttu-id="bf608-827">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-827">Electricity</span></span></td>
<td><span data-ttu-id="bf608-828">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-828">Fixed cost</span></span></td>
<td><span data-ttu-id="bf608-829">438.75</span><span class="sxs-lookup"><span data-stu-id="bf608-829">438.75</span></span></td>
<td><span data-ttu-id="bf608-830">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-831">CC004</span><span class="sxs-lookup"><span data-stu-id="bf608-831">CC004</span></span></td>
<td><span data-ttu-id="bf608-832">Embalagem</span><span class="sxs-lookup"><span data-stu-id="bf608-832">Packaging</span></span></td>
<td><span data-ttu-id="bf608-833">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-833">10001</span></span></td>
<td><span data-ttu-id="bf608-834">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-834">Electricity</span></span></td>
<td><span data-ttu-id="bf608-835">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-835">Fixed cost</span></span></td>
<td><span data-ttu-id="bf608-836">236.25</span><span class="sxs-lookup"><span data-stu-id="bf608-836">236.25</span></span></td>
<td><span data-ttu-id="bf608-837">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-838">CC002</span><span class="sxs-lookup"><span data-stu-id="bf608-838">CC002</span></span></td>
<td><span data-ttu-id="bf608-839">Finanças</span><span class="sxs-lookup"><span data-stu-id="bf608-839">Finance</span></span></td>
<td><span data-ttu-id="bf608-840">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-840">10001</span></span></td>
<td><span data-ttu-id="bf608-841">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-841">Electricity</span></span></td>
<td><span data-ttu-id="bf608-842">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-842">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="bf608-843">-8,150.29</span></span></td>
<td><span data-ttu-id="bf608-844">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-845">CC003</span><span class="sxs-lookup"><span data-stu-id="bf608-845">CC003</span></span></td>
<td><span data-ttu-id="bf608-846">Montagem</span><span class="sxs-lookup"><span data-stu-id="bf608-846">Assembly</span></span></td>
<td><span data-ttu-id="bf608-847">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-847">10001</span></span></td>
<td><span data-ttu-id="bf608-848">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-848">Electricity</span></span></td>
<td><span data-ttu-id="bf608-849">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-849">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="bf608-850">5,297.69</span></span></td>
<td><span data-ttu-id="bf608-851">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-852">CC004</span><span class="sxs-lookup"><span data-stu-id="bf608-852">CC004</span></span></td>
<td><span data-ttu-id="bf608-853">Embalagem</span><span class="sxs-lookup"><span data-stu-id="bf608-853">Packaging</span></span></td>
<td><span data-ttu-id="bf608-854">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-854">10001</span></span></td>
<td><span data-ttu-id="bf608-855">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-855">Electricity</span></span></td>
<td><span data-ttu-id="bf608-856">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-856">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="bf608-857">2,852.60</span></span></td>
<td><span data-ttu-id="bf608-858">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-859">CC003</span><span class="sxs-lookup"><span data-stu-id="bf608-859">CC003</span></span></td>
<td><span data-ttu-id="bf608-860">Montagem</span><span class="sxs-lookup"><span data-stu-id="bf608-860">Assembly</span></span></td>
<td><span data-ttu-id="bf608-861">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-861">10001</span></span></td>
<td><span data-ttu-id="bf608-862">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-862">Electricity</span></span></td>
<td><span data-ttu-id="bf608-863">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-863">Fixed cost</span></span></td>
<td><span data-ttu-id="bf608-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="bf608-864">-713.75</span></span></td>
<td><span data-ttu-id="bf608-865">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-866">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="bf608-866">Prod 1</span></span></td>
<td><span data-ttu-id="bf608-867">Produto 1</span><span class="sxs-lookup"><span data-stu-id="bf608-867">Product 1</span></span></td>
<td><span data-ttu-id="bf608-868">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-868">10001</span></span></td>
<td><span data-ttu-id="bf608-869">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-869">Electricity</span></span></td>
<td><span data-ttu-id="bf608-870">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-870">Fixed cost</span></span></td>
<td><span data-ttu-id="bf608-871">535.31</span><span class="sxs-lookup"><span data-stu-id="bf608-871">535.31</span></span></td>
<td><span data-ttu-id="bf608-872">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-873">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="bf608-873">Prod 2</span></span></td>
<td><span data-ttu-id="bf608-874">Produto 2</span><span class="sxs-lookup"><span data-stu-id="bf608-874">Product 2</span></span></td>
<td><span data-ttu-id="bf608-875">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-875">10001</span></span></td>
<td><span data-ttu-id="bf608-876">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-876">Electricity</span></span></td>
<td><span data-ttu-id="bf608-877">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-877">Fixed cost</span></span></td>
<td><span data-ttu-id="bf608-878">178.44</span><span class="sxs-lookup"><span data-stu-id="bf608-878">178.44</span></span></td>
<td><span data-ttu-id="bf608-879">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-880">CC003</span><span class="sxs-lookup"><span data-stu-id="bf608-880">CC003</span></span></td>
<td><span data-ttu-id="bf608-881">Montagem</span><span class="sxs-lookup"><span data-stu-id="bf608-881">Assembly</span></span></td>
<td><span data-ttu-id="bf608-882">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-882">10001</span></span></td>
<td><span data-ttu-id="bf608-883">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-883">Electricity</span></span></td>
<td><span data-ttu-id="bf608-884">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-884">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="bf608-885">-5,982.83</span></span></td>
<td><span data-ttu-id="bf608-886">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-887">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="bf608-887">Prod 1</span></span></td>
<td><span data-ttu-id="bf608-888">Produto 1</span><span class="sxs-lookup"><span data-stu-id="bf608-888">Product 1</span></span></td>
<td><span data-ttu-id="bf608-889">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-889">10001</span></span></td>
<td><span data-ttu-id="bf608-890">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-890">Electricity</span></span></td>
<td><span data-ttu-id="bf608-891">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-891">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="bf608-892">4,487.12</span></span></td>
<td><span data-ttu-id="bf608-893">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-894">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="bf608-894">Prod 2</span></span></td>
<td><span data-ttu-id="bf608-895">Produto 2</span><span class="sxs-lookup"><span data-stu-id="bf608-895">Product 2</span></span></td>
<td><span data-ttu-id="bf608-896">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-896">10001</span></span></td>
<td><span data-ttu-id="bf608-897">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-897">Electricity</span></span></td>
<td><span data-ttu-id="bf608-898">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-898">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="bf608-899">1,495.71</span></span></td>
<td><span data-ttu-id="bf608-900">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-901">CC003</span><span class="sxs-lookup"><span data-stu-id="bf608-901">CC003</span></span></td>
<td><span data-ttu-id="bf608-902">Montagem</span><span class="sxs-lookup"><span data-stu-id="bf608-902">Assembly</span></span></td>
<td><span data-ttu-id="bf608-903">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-903">10001</span></span></td>
<td><span data-ttu-id="bf608-904">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-904">Electricity</span></span></td>
<td><span data-ttu-id="bf608-905">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-905">Fixed cost</span></span></td>
<td><span data-ttu-id="bf608-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="bf608-906">-286.25</span></span></td>
<td><span data-ttu-id="bf608-907">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-908">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="bf608-908">Prod 1</span></span></td>
<td><span data-ttu-id="bf608-909">Produto 1</span><span class="sxs-lookup"><span data-stu-id="bf608-909">Product 1</span></span></td>
<td><span data-ttu-id="bf608-910">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-910">10001</span></span></td>
<td><span data-ttu-id="bf608-911">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-911">Electricity</span></span></td>
<td><span data-ttu-id="bf608-912">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-912">Fixed cost</span></span></td>
<td><span data-ttu-id="bf608-913">241.05</span><span class="sxs-lookup"><span data-stu-id="bf608-913">241.05</span></span></td>
<td><span data-ttu-id="bf608-914">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-915">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="bf608-915">Prod 2</span></span></td>
<td><span data-ttu-id="bf608-916">Produto 2</span><span class="sxs-lookup"><span data-stu-id="bf608-916">Product 2</span></span></td>
<td><span data-ttu-id="bf608-917">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-917">10001</span></span></td>
<td><span data-ttu-id="bf608-918">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-918">Electricity</span></span></td>
<td><span data-ttu-id="bf608-919">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-919">Fixed cost</span></span></td>
<td><span data-ttu-id="bf608-920">45.20</span><span class="sxs-lookup"><span data-stu-id="bf608-920">45.20</span></span></td>
<td><span data-ttu-id="bf608-921">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-922">CC003</span><span class="sxs-lookup"><span data-stu-id="bf608-922">CC003</span></span></td>
<td><span data-ttu-id="bf608-923">Montagem</span><span class="sxs-lookup"><span data-stu-id="bf608-923">Assembly</span></span></td>
<td><span data-ttu-id="bf608-924">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-924">10001</span></span></td>
<td><span data-ttu-id="bf608-925">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-925">Electricity</span></span></td>
<td><span data-ttu-id="bf608-926">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-926">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="bf608-927">-2,977.17</span></span></td>
<td><span data-ttu-id="bf608-928">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-929">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="bf608-929">Prod 1</span></span></td>
<td><span data-ttu-id="bf608-930">Produto 1</span><span class="sxs-lookup"><span data-stu-id="bf608-930">Product 1</span></span></td>
<td><span data-ttu-id="bf608-931">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-931">10001</span></span></td>
<td><span data-ttu-id="bf608-932">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-932">Electricity</span></span></td>
<td><span data-ttu-id="bf608-933">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-933">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="bf608-934">2,507.09</span></span></td>
<td><span data-ttu-id="bf608-935">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bf608-936">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="bf608-936">Prod 2</span></span></td>
<td><span data-ttu-id="bf608-937">Produto 2</span><span class="sxs-lookup"><span data-stu-id="bf608-937">Product 2</span></span></td>
<td><span data-ttu-id="bf608-938">10001</span><span class="sxs-lookup"><span data-stu-id="bf608-938">10001</span></span></td>
<td><span data-ttu-id="bf608-939">eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-939">Electricity</span></span></td>
<td><span data-ttu-id="bf608-940">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-940">Variable cost</span></span></td>
<td><span data-ttu-id="bf608-941">470.08</span><span class="sxs-lookup"><span data-stu-id="bf608-941">470.08</span></span></td>
<td><span data-ttu-id="bf608-942">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="bf608-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="bf608-943">Conclusão</span><span class="sxs-lookup"><span data-stu-id="bf608-943">Conclusion</span></span>
<span data-ttu-id="bf608-944">Na contabilidade financeira, um custo de 10,000.00 para a eletricidade é lançado para um ID fictício de centro de custos.</span><span class="sxs-lookup"><span data-stu-id="bf608-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="bf608-945">Portanto, os contadores de custo saberão que esses custos devem ser alocados.</span><span class="sxs-lookup"><span data-stu-id="bf608-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="bf608-946">Na contabilização de custo, os custos fluem nas unidades organizacionais e nos níveis, com base nas políticas e regras que são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="bf608-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="bf608-947">Cada custo foi associado a uma base de alocação que fornece a melhor apuração para a alocação de custos.</span><span class="sxs-lookup"><span data-stu-id="bf608-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="bf608-948">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="bf608-949">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="bf608-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="bf608-950">Total</span><span class="sxs-lookup"><span data-stu-id="bf608-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="bf608-951">CC099</span><span class="sxs-lookup"><span data-stu-id="bf608-951">CC099</span></span></th>
<th><span data-ttu-id="bf608-952">CC001</span><span class="sxs-lookup"><span data-stu-id="bf608-952">CC001</span></span></th>
<th><span data-ttu-id="bf608-953">CC002</span><span class="sxs-lookup"><span data-stu-id="bf608-953">CC002</span></span></th>
<th><span data-ttu-id="bf608-954">CC003</span><span class="sxs-lookup"><span data-stu-id="bf608-954">CC003</span></span></th>
<th><span data-ttu-id="bf608-955">CC004</span><span class="sxs-lookup"><span data-stu-id="bf608-955">CC004</span></span></th>
<th><span data-ttu-id="bf608-956">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="bf608-956">Proj 1</span></span></th>
<th><span data-ttu-id="bf608-957">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="bf608-957">Proj 2</span></span></th>
<th><span data-ttu-id="bf608-958">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="bf608-958">Prod 1</span></span></th>
<th><span data-ttu-id="bf608-959">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="bf608-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="bf608-960">10001 Eletricidade</span><span class="sxs-lookup"><span data-stu-id="bf608-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="bf608-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="bf608-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="bf608-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="bf608-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="bf608-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="bf608-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="bf608-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="bf608-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="bf608-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="bf608-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="bf608-970">Não classificado</span><span class="sxs-lookup"><span data-stu-id="bf608-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-971">0,00</span><span class="sxs-lookup"><span data-stu-id="bf608-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="bf608-972">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="bf608-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-973">0,00</span><span class="sxs-lookup"><span data-stu-id="bf608-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-974">0,00</span><span class="sxs-lookup"><span data-stu-id="bf608-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-975">0,00</span><span class="sxs-lookup"><span data-stu-id="bf608-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-976">0,00</span><span class="sxs-lookup"><span data-stu-id="bf608-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-977">0,00</span><span class="sxs-lookup"><span data-stu-id="bf608-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="bf608-978">776.36</span><span class="sxs-lookup"><span data-stu-id="bf608-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-979">223.64</span><span class="sxs-lookup"><span data-stu-id="bf608-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="bf608-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="bf608-981">Custo variável</span><span class="sxs-lookup"><span data-stu-id="bf608-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-982">000</span><span class="sxs-lookup"><span data-stu-id="bf608-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-983">0,00</span><span class="sxs-lookup"><span data-stu-id="bf608-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-984">0,00</span><span class="sxs-lookup"><span data-stu-id="bf608-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-985">0,00</span><span class="sxs-lookup"><span data-stu-id="bf608-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-986">0,00</span><span class="sxs-lookup"><span data-stu-id="bf608-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-987">30,00</span><span class="sxs-lookup"><span data-stu-id="bf608-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-988">10,00</span><span class="sxs-lookup"><span data-stu-id="bf608-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="bf608-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="bf608-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="bf608-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="bf608-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="bf608-992">Esse tópico mostra como um elemento de custo principal, 10001 Eletricidade flui pelos objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="bf608-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="bf608-993">Portanto, esse custo geral indireto é alocado no nível mais baixo na organização.</span><span class="sxs-lookup"><span data-stu-id="bf608-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="bf608-994">Em outras palavras, os objetos de custo no nível mais baixo assumem o custo.</span><span class="sxs-lookup"><span data-stu-id="bf608-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="bf608-995">Se você exigir um fluxo visual de custo entre objetos de custo, é possível usar as regras de política de acúmulo de custos para visualizar o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="bf608-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="bf608-996">Para maiores informações, consulte [Acúmulo de custo](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="bf608-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>




