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
ms.openlocfilehash: 4de705324ac497cfb11fae3dadc6f57d038fd0b5
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544046"
---
# <a name="overhead-calculation"></a><span data-ttu-id="4b759-103">Cálculo de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="4b759-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4b759-104">Este tópico descreve processos comuns para calcular e alocar os custos gerais indiretos.</span><span class="sxs-lookup"><span data-stu-id="4b759-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="4b759-105">Definição de termo</span><span class="sxs-lookup"><span data-stu-id="4b759-105">Term definition</span></span>
---------------

<span data-ttu-id="4b759-106">Os custos gerais indiretos são aqueles que foram incorridos para realizar um negócio, mas não podem ser diretamente atribuídos a qualquer atividade comercial, produto ou serviço específico.</span><span class="sxs-lookup"><span data-stu-id="4b759-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="4b759-107">Os custos gerais indiretos fornecem suporte crítico para geração de atividades produtivas.</span><span class="sxs-lookup"><span data-stu-id="4b759-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="4b759-108">Eis alguns exemplos de custos gerais:</span><span class="sxs-lookup"><span data-stu-id="4b759-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="4b759-109">Aluguel</span><span class="sxs-lookup"><span data-stu-id="4b759-109">Rent</span></span>
-   <span data-ttu-id="4b759-110">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-110">Electricity</span></span>
-   <span data-ttu-id="4b759-111">Salários administrativos</span><span class="sxs-lookup"><span data-stu-id="4b759-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="4b759-112">Visão geral do cálculo de custos gerais indiretos</span><span class="sxs-lookup"><span data-stu-id="4b759-112">Overhead calculation overview</span></span>
<span data-ttu-id="4b759-113">O cálculo de custos gerais indiretos executa as políticas de contabilização de custos na ordem correta.</span><span class="sxs-lookup"><span data-stu-id="4b759-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="4b759-114">Você pode executar o cálculo de custos gerais indiretos várias vezes para o mesmo período fiscal, se as políticas de contabilidade de custo foram modificadas ou foram detectados erros específicos.</span><span class="sxs-lookup"><span data-stu-id="4b759-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="4b759-115">Cada execução do cálculo de custos gerais indiretos é armazenada e recebe um ID exclusivo de versão que permite comparar os cálculos em várias versões.</span><span class="sxs-lookup"><span data-stu-id="4b759-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="4b759-116">As entradas de custo que o cálculo de custos indiretos gera recebe uma data contábil.</span><span class="sxs-lookup"><span data-stu-id="4b759-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="4b759-117">Essa data contábil corresponde à data final do período fiscal que é usada no cálculo.</span><span class="sxs-lookup"><span data-stu-id="4b759-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="4b759-118">A ID exclusiva de versão consiste nos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="4b759-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="4b759-119">Tipo de versão</span><span class="sxs-lookup"><span data-stu-id="4b759-119">Version type</span></span>
-   <span data-ttu-id="4b759-120">Data e hora</span><span class="sxs-lookup"><span data-stu-id="4b759-120">Date and time</span></span>
-   <span data-ttu-id="4b759-121">Razão de contabilização de custos</span><span class="sxs-lookup"><span data-stu-id="4b759-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="4b759-122">Ano fiscal</span><span class="sxs-lookup"><span data-stu-id="4b759-122">Fiscal year</span></span>
-   <span data-ttu-id="4b759-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="4b759-123">Fiscal period</span></span>

<span data-ttu-id="4b759-124">O cálculo de custos gerais indiretos é executado independentemente da versão.</span><span class="sxs-lookup"><span data-stu-id="4b759-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="4b759-125">Portanto, você pode calcular a versão de orçamento antes da versão atual.</span><span class="sxs-lookup"><span data-stu-id="4b759-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="4b759-126">O cálculo de custos gerais indiretos consiste em quatro etapas, conforme mostrado na ilustração.</span><span class="sxs-lookup"><span data-stu-id="4b759-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="4b759-127">Em cada etapa, um cabeçalho de diário é criado com entradas de diário.</span><span class="sxs-lookup"><span data-stu-id="4b759-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="4b759-128">Esse cabeçalho de diário mantém dados de entrada para cada etapa de cálculo.</span><span class="sxs-lookup"><span data-stu-id="4b759-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="4b759-129">As políticas e regras são aplicadas a cada linha do diário e as entradas de custo são geradas como saídas.</span><span class="sxs-lookup"><span data-stu-id="4b759-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="4b759-130">Portanto, você sempre terá rastreabilidade total.</span><span class="sxs-lookup"><span data-stu-id="4b759-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="4b759-131">[![Cálculo de custos gerais indiretos](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="4b759-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="4b759-132">Calcular e alocar os custos gerais indiretos de Eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="4b759-133">Na contabilidade financeira, alguns custos, como eletricidade, são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="4b759-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="4b759-134">Portanto, a visão administrativa detalhada não é fornecida para a contabilização de custo.</span><span class="sxs-lookup"><span data-stu-id="4b759-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="4b759-135">Na contabilização de custo, para fornecer a visão administrativa correta em todas as unidades organizacionais e níveis, os custos devem passar pelas unidades organizacionais.</span><span class="sxs-lookup"><span data-stu-id="4b759-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="4b759-136">Este fluxo deve ser baseado em qualquer um registro exato do consumo ou de uma previsão justa.</span><span class="sxs-lookup"><span data-stu-id="4b759-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="4b759-137">Na contabilidade, um custo de eletricidade pode ser lançado, conforme mostrado na tabela.</span><span class="sxs-lookup"><span data-stu-id="4b759-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4b759-138">Data contábil</span><span class="sxs-lookup"><span data-stu-id="4b759-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="4b759-139">Centro de custos</span><span class="sxs-lookup"><span data-stu-id="4b759-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="4b759-140">Conta principal</span><span class="sxs-lookup"><span data-stu-id="4b759-140">Main account</span></span></th>
<th><span data-ttu-id="4b759-141">Valor na moeda contábil</span><span class="sxs-lookup"><span data-stu-id="4b759-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-142">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="4b759-143">CC099</span><span class="sxs-lookup"><span data-stu-id="4b759-143">CC099</span></span></td>
<td><span data-ttu-id="4b759-144">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="4b759-144">Default cost center</span></span></td>
<td><span data-ttu-id="4b759-145">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-145">10001</span></span></td>
<td><span data-ttu-id="4b759-146">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-146">Electricity</span></span></td>
<td><span data-ttu-id="4b759-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="4b759-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="4b759-148">Etapa 1: Processar o cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="4b759-149">Por padrão, quando as entradas de custo previsto são importadas de dados de origem, elas recebem a classificação de comportamento de custo **Não classificado** na Contabilidade de custos.</span><span class="sxs-lookup"><span data-stu-id="4b759-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="4b759-150">Aplicando regras da política de comportamento de custo, é possível reclassificar entradas de custo como **Custo fixo** ou **Custo variável**.</span><span class="sxs-lookup"><span data-stu-id="4b759-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="4b759-151">Definir a regra de custo de comportamento</span><span class="sxs-lookup"><span data-stu-id="4b759-151">Define the cost behavior rule</span></span>

<span data-ttu-id="4b759-152">Em alguns casos, parte do custo é uma taxa fixa e o custos pendente é baseado no consumo.</span><span class="sxs-lookup"><span data-stu-id="4b759-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="4b759-153">Geralmente, as contas de eletricidade correspondem a esta definição.</span><span class="sxs-lookup"><span data-stu-id="4b759-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="4b759-154">Após você pagar uma taxa fixa específica, você paga por consumo, por hora de quilowatt (Kwh).</span><span class="sxs-lookup"><span data-stu-id="4b759-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="4b759-155">Por exemplo, se a taxa de custo fixa for 1.000.00, veja aqui como a regra de comportamento de custo é definida:</span><span class="sxs-lookup"><span data-stu-id="4b759-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="4b759-156">Valor fixo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="4b759-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="4b759-157">0 &lt;= 1.000,00 = Fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="4b759-158">1000.01 &lt; N = Variável</span><span class="sxs-lookup"><span data-stu-id="4b759-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="4b759-159">Diário</span><span class="sxs-lookup"><span data-stu-id="4b759-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4b759-160">Diário</span><span class="sxs-lookup"><span data-stu-id="4b759-160">Journal</span></span></th>
<th><span data-ttu-id="4b759-161">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="4b759-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="4b759-162">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="4b759-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="4b759-163">Versão</span><span class="sxs-lookup"><span data-stu-id="4b759-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-164">00001</span><span class="sxs-lookup"><span data-stu-id="4b759-164">00001</span></span></td>
<td><span data-ttu-id="4b759-165">Diário de cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="4b759-166">fiscal</span><span class="sxs-lookup"><span data-stu-id="4b759-166">Fiscal</span></span></td>
<td><span data-ttu-id="4b759-167">2017</span><span class="sxs-lookup"><span data-stu-id="4b759-167">2017</span></span></td>
<td><span data-ttu-id="4b759-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="4b759-168">Period 1</span></span></td>
<td><span data-ttu-id="4b759-169">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="4b759-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="4b759-170">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="4b759-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4b759-171">Data contábil</span><span class="sxs-lookup"><span data-stu-id="4b759-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="4b759-172">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4b759-173">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-173">Cost element</span></span></th>
<th><span data-ttu-id="4b759-174">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-174">Cost behavior</span></span></th>
<th><span data-ttu-id="4b759-175">Valor</span><span class="sxs-lookup"><span data-stu-id="4b759-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-176">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="4b759-177">CC099</span><span class="sxs-lookup"><span data-stu-id="4b759-177">CC099</span></span></td>
<td><span data-ttu-id="4b759-178">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="4b759-178">Default cost center</span></span></td>
<td><span data-ttu-id="4b759-179">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-179">10001</span></span></td>
<td><span data-ttu-id="4b759-180">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-180">Electricity</span></span></td>
<td><span data-ttu-id="4b759-181">Não classificado</span><span class="sxs-lookup"><span data-stu-id="4b759-181">Unclassified</span></span></td>
<td><span data-ttu-id="4b759-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="4b759-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="4b759-183">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b759-184">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4b759-185">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-185">Cost element</span></span></th>
<th><span data-ttu-id="4b759-186">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-186">Cost behavior</span></span></th>
<th><span data-ttu-id="4b759-187">Valor</span><span class="sxs-lookup"><span data-stu-id="4b759-187">Amount</span></span></th>
<th><span data-ttu-id="4b759-188">Data contábil</span><span class="sxs-lookup"><span data-stu-id="4b759-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-189">CC099</span><span class="sxs-lookup"><span data-stu-id="4b759-189">CC099</span></span></td>
<td><span data-ttu-id="4b759-190">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="4b759-190">Default cost center</span></span></td>
<td><span data-ttu-id="4b759-191">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-191">10001</span></span></td>
<td><span data-ttu-id="4b759-192">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-192">Electricity</span></span></td>
<td><span data-ttu-id="4b759-193">Não classificado</span><span class="sxs-lookup"><span data-stu-id="4b759-193">Unclassified</span></span></td>
<td><span data-ttu-id="4b759-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="4b759-194">10,000.00</span></span></td>
<td><span data-ttu-id="4b759-195">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-196">CC099</span><span class="sxs-lookup"><span data-stu-id="4b759-196">CC099</span></span></td>
<td><span data-ttu-id="4b759-197">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="4b759-197">Default cost center</span></span></td>
<td><span data-ttu-id="4b759-198">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-198">10001</span></span></td>
<td><span data-ttu-id="4b759-199">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-199">Electricity</span></span></td>
<td><span data-ttu-id="4b759-200">Não classificado</span><span class="sxs-lookup"><span data-stu-id="4b759-200">Unclassified</span></span></td>
<td><span data-ttu-id="4b759-201">-10.000,00</span><span class="sxs-lookup"><span data-stu-id="4b759-201">-10,000.00</span></span></td>
<td><span data-ttu-id="4b759-202">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-203">CC099</span><span class="sxs-lookup"><span data-stu-id="4b759-203">CC099</span></span></td>
<td><span data-ttu-id="4b759-204">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="4b759-204">Default cost center</span></span></td>
<td><span data-ttu-id="4b759-205">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-205">10001</span></span></td>
<td><span data-ttu-id="4b759-206">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-206">Electricity</span></span></td>
<td><span data-ttu-id="4b759-207">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-207">Fixed cost</span></span></td>
<td><span data-ttu-id="4b759-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="4b759-208">1,000.00</span></span></td>
<td><span data-ttu-id="4b759-209">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-210">CC099</span><span class="sxs-lookup"><span data-stu-id="4b759-210">CC099</span></span></td>
<td><span data-ttu-id="4b759-211">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="4b759-211">Default cost center</span></span></td>
<td><span data-ttu-id="4b759-212">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-212">10001</span></span></td>
<td><span data-ttu-id="4b759-213">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-213">Electricity</span></span></td>
<td><span data-ttu-id="4b759-214">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-214">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="4b759-215">9,000.00</span></span></td>
<td><span data-ttu-id="4b759-216">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b759-217">Para obter mais informações, consulte [Criar e atribuir uma política de comportamento de custos a uma unidade de controle de custos](tasks/create-assign-cost-behavior-policy-cost-control-unit.md)</span><span class="sxs-lookup"><span data-stu-id="4b759-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="4b759-218">Etapa 2: Processar o cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="4b759-219">A distribuição de custos é usada para redistribuir custo de um objeto de custo a um ou mais outros objetos de custo, aplicando uma base de alocação relevante.</span><span class="sxs-lookup"><span data-stu-id="4b759-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="4b759-220">A distribuição de custos e a alocação de custo são diferentes na distribuição de custos, sempre que ocorrer em nível de elemento de custo principal do custo original.</span><span class="sxs-lookup"><span data-stu-id="4b759-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="4b759-221">Definir a regra de distribuição de custos</span><span class="sxs-lookup"><span data-stu-id="4b759-221">Define the cost distribution rule</span></span>

<span data-ttu-id="4b759-222">Na contabilidade financeira, os custos de eletricidade geralmente são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="4b759-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="4b759-223">Na contabilização de custo, esta abordagem não é suficientemente detalhada.</span><span class="sxs-lookup"><span data-stu-id="4b759-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="4b759-224">O custo variável deve ser distribuído a objetos de custos individuais com base justa.</span><span class="sxs-lookup"><span data-stu-id="4b759-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="4b759-225">A base de alocação mais lógica é o consumo de eletricidade (Kwh).</span><span class="sxs-lookup"><span data-stu-id="4b759-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="4b759-226">O membro da dimensão estatística que é chamado Eletricidade é criado e o consumo de eletricidade é registrado.</span><span class="sxs-lookup"><span data-stu-id="4b759-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="4b759-227">Por padrão, todos os membros estatísticos da dimensão se tornam disponíveis como bases de alocação.</span><span class="sxs-lookup"><span data-stu-id="4b759-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b759-228">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-228">Cost object</span></span></th>
<th><span data-ttu-id="4b759-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="4b759-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-230">CC001</span><span class="sxs-lookup"><span data-stu-id="4b759-230">CC001</span></span></td>
<td><span data-ttu-id="4b759-231">RH</span><span class="sxs-lookup"><span data-stu-id="4b759-231">HR</span></span></td>
<td><span data-ttu-id="4b759-232">1.000</span><span class="sxs-lookup"><span data-stu-id="4b759-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-233">CC002</span><span class="sxs-lookup"><span data-stu-id="4b759-233">CC002</span></span></td>
<td><span data-ttu-id="4b759-234">Finanças</span><span class="sxs-lookup"><span data-stu-id="4b759-234">Finance</span></span></td>
<td><span data-ttu-id="4b759-235">6,000</span><span class="sxs-lookup"><span data-stu-id="4b759-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-236">CC003</span><span class="sxs-lookup"><span data-stu-id="4b759-236">CC003</span></span></td>
<td><span data-ttu-id="4b759-237">Montagem</span><span class="sxs-lookup"><span data-stu-id="4b759-237">Assembly</span></span></td>
<td><span data-ttu-id="4b759-238">0</span><span class="sxs-lookup"><span data-stu-id="4b759-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b759-239">A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação para custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="4b759-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b759-240">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-240">Cost object</span></span></th>
<th><span data-ttu-id="4b759-241">Magnitude</span><span class="sxs-lookup"><span data-stu-id="4b759-241">Magnitude</span></span></th>
<th><span data-ttu-id="4b759-242">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="4b759-242">Allocation factor</span></span></th>
<th><span data-ttu-id="4b759-243">Valor</span><span class="sxs-lookup"><span data-stu-id="4b759-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-244">CC001</span><span class="sxs-lookup"><span data-stu-id="4b759-244">CC001</span></span></td>
<td><span data-ttu-id="4b759-245">RH</span><span class="sxs-lookup"><span data-stu-id="4b759-245">HR</span></span></td>
<td><span data-ttu-id="4b759-246">1.000</span><span class="sxs-lookup"><span data-stu-id="4b759-246">1,000</span></span></td>
<td><span data-ttu-id="4b759-247">(1.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="4b759-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="4b759-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="4b759-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-249">CC002</span><span class="sxs-lookup"><span data-stu-id="4b759-249">CC002</span></span></td>
<td><span data-ttu-id="4b759-250">Finanças</span><span class="sxs-lookup"><span data-stu-id="4b759-250">Finance</span></span></td>
<td><span data-ttu-id="4b759-251">6,000</span><span class="sxs-lookup"><span data-stu-id="4b759-251">6,000</span></span></td>
<td><span data-ttu-id="4b759-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="4b759-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="4b759-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="4b759-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-254">CC003</span><span class="sxs-lookup"><span data-stu-id="4b759-254">CC003</span></span></td>
<td><span data-ttu-id="4b759-255">Montagem</span><span class="sxs-lookup"><span data-stu-id="4b759-255">Assembly</span></span></td>
<td><span data-ttu-id="4b759-256">0</span><span class="sxs-lookup"><span data-stu-id="4b759-256">0</span></span></td>
<td><span data-ttu-id="4b759-257">(0 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="4b759-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="4b759-258">0,00</span><span class="sxs-lookup"><span data-stu-id="4b759-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b759-259">Os custos fixos devem ser distribuídos igualmente a objetos de custo individuais que têm a eletricidade consumida.</span><span class="sxs-lookup"><span data-stu-id="4b759-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="4b759-260">Você pode obter esse resultado usando o membro estatístico de dimensão de eletricidade em uma base e alocação da fórmula: (Eletricidade &gt; 0,00) A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação de custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="4b759-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b759-261">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-261">Cost object</span></span></th>
<th><span data-ttu-id="4b759-262">Fórmula</span><span class="sxs-lookup"><span data-stu-id="4b759-262">Formula</span></span></th>
<th><span data-ttu-id="4b759-263">Magnitude</span><span class="sxs-lookup"><span data-stu-id="4b759-263">Magnitude</span></span></th>
<th><span data-ttu-id="4b759-264">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="4b759-264">Allocation factor</span></span></th>
<th><span data-ttu-id="4b759-265">Valor</span><span class="sxs-lookup"><span data-stu-id="4b759-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-266">CC001</span><span class="sxs-lookup"><span data-stu-id="4b759-266">CC001</span></span></td>
<td><span data-ttu-id="4b759-267">RH</span><span class="sxs-lookup"><span data-stu-id="4b759-267">HR</span></span></td>
<td><span data-ttu-id="4b759-268">(1.000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="4b759-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="4b759-269">1</span><span class="sxs-lookup"><span data-stu-id="4b759-269">1</span></span></td>
<td><span data-ttu-id="4b759-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="4b759-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="4b759-271">500,00</span><span class="sxs-lookup"><span data-stu-id="4b759-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-272">CC002</span><span class="sxs-lookup"><span data-stu-id="4b759-272">CC002</span></span></td>
<td><span data-ttu-id="4b759-273">Finanças</span><span class="sxs-lookup"><span data-stu-id="4b759-273">Finance</span></span></td>
<td><span data-ttu-id="4b759-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="4b759-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="4b759-275">1</span><span class="sxs-lookup"><span data-stu-id="4b759-275">1</span></span></td>
<td><span data-ttu-id="4b759-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="4b759-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="4b759-277">500,00</span><span class="sxs-lookup"><span data-stu-id="4b759-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-278">CC003</span><span class="sxs-lookup"><span data-stu-id="4b759-278">CC003</span></span></td>
<td><span data-ttu-id="4b759-279">Montagem</span><span class="sxs-lookup"><span data-stu-id="4b759-279">Assembly</span></span></td>
<td><span data-ttu-id="4b759-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="4b759-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="4b759-281">0</span><span class="sxs-lookup"><span data-stu-id="4b759-281">0</span></span></td>
<td><span data-ttu-id="4b759-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="4b759-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="4b759-283">0,00</span><span class="sxs-lookup"><span data-stu-id="4b759-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="4b759-284">Diário</span><span class="sxs-lookup"><span data-stu-id="4b759-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4b759-285">Diário</span><span class="sxs-lookup"><span data-stu-id="4b759-285">Journal</span></span></th>
<th><span data-ttu-id="4b759-286">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="4b759-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="4b759-287">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="4b759-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="4b759-288">Versão</span><span class="sxs-lookup"><span data-stu-id="4b759-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-289">00002</span><span class="sxs-lookup"><span data-stu-id="4b759-289">00002</span></span></td>
<td><span data-ttu-id="4b759-290">Diário de cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="4b759-291">fiscal</span><span class="sxs-lookup"><span data-stu-id="4b759-291">Fiscal</span></span></td>
<td><span data-ttu-id="4b759-292">2017</span><span class="sxs-lookup"><span data-stu-id="4b759-292">2017</span></span></td>
<td><span data-ttu-id="4b759-293">Período 1</span><span class="sxs-lookup"><span data-stu-id="4b759-293">Period 1</span></span></td>
<td><span data-ttu-id="4b759-294">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="4b759-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="4b759-295">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="4b759-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4b759-296">Data contábil</span><span class="sxs-lookup"><span data-stu-id="4b759-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="4b759-297">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4b759-298">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-298">Cost element</span></span></th>
<th><span data-ttu-id="4b759-299">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-299">Cost behavior</span></span></th>
<th><span data-ttu-id="4b759-300">Valor</span><span class="sxs-lookup"><span data-stu-id="4b759-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-301">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b759-302">CC099</span><span class="sxs-lookup"><span data-stu-id="4b759-302">CC099</span></span></td>
<td><span data-ttu-id="4b759-303">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="4b759-303">Default cost center</span></span></td>
<td><span data-ttu-id="4b759-304">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-304">10001</span></span></td>
<td><span data-ttu-id="4b759-305">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-305">Electricity</span></span></td>
<td><span data-ttu-id="4b759-306">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-306">Fixed cost</span></span></td>
<td><span data-ttu-id="4b759-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="4b759-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-308">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b759-309">CC099</span><span class="sxs-lookup"><span data-stu-id="4b759-309">CC099</span></span></td>
<td><span data-ttu-id="4b759-310">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="4b759-310">Default cost center</span></span></td>
<td><span data-ttu-id="4b759-311">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-311">10001</span></span></td>
<td><span data-ttu-id="4b759-312">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-312">Electricity</span></span></td>
<td><span data-ttu-id="4b759-313">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-313">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="4b759-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="4b759-315">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b759-316">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4b759-317">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-317">Cost element</span></span></th>
<th><span data-ttu-id="4b759-318">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-318">Cost behavior</span></span></th>
<th><span data-ttu-id="4b759-319">Valor</span><span class="sxs-lookup"><span data-stu-id="4b759-319">Amount</span></span></th>
<th><span data-ttu-id="4b759-320">Data contábil</span><span class="sxs-lookup"><span data-stu-id="4b759-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-321">CC099</span><span class="sxs-lookup"><span data-stu-id="4b759-321">CC099</span></span></td>
<td><span data-ttu-id="4b759-322">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="4b759-322">Default cost center</span></span></td>
<td><span data-ttu-id="4b759-323">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-323">10001</span></span></td>
<td><span data-ttu-id="4b759-324">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-324">Electricity</span></span></td>
<td><span data-ttu-id="4b759-325">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-325">Fixed cost</span></span></td>
<td><span data-ttu-id="4b759-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="4b759-326">-1,000.00</span></span></td>
<td><span data-ttu-id="4b759-327">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-328">CC001</span><span class="sxs-lookup"><span data-stu-id="4b759-328">CC001</span></span></td>
<td><span data-ttu-id="4b759-329">RH</span><span class="sxs-lookup"><span data-stu-id="4b759-329">HR</span></span></td>
<td><span data-ttu-id="4b759-330">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-330">10001</span></span></td>
<td><span data-ttu-id="4b759-331">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-331">Electricity</span></span></td>
<td><span data-ttu-id="4b759-332">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-332">Fixed cost</span></span></td>
<td><span data-ttu-id="4b759-333">500,00</span><span class="sxs-lookup"><span data-stu-id="4b759-333">500.00</span></span></td>
<td><span data-ttu-id="4b759-334">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-335">CC002</span><span class="sxs-lookup"><span data-stu-id="4b759-335">CC002</span></span></td>
<td><span data-ttu-id="4b759-336">Finanças</span><span class="sxs-lookup"><span data-stu-id="4b759-336">Finance</span></span></td>
<td><span data-ttu-id="4b759-337">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-337">10001</span></span></td>
<td><span data-ttu-id="4b759-338">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-338">Electricity</span></span></td>
<td><span data-ttu-id="4b759-339">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-339">Fixed cost</span></span></td>
<td><span data-ttu-id="4b759-340">500,00</span><span class="sxs-lookup"><span data-stu-id="4b759-340">500.00</span></span></td>
<td><span data-ttu-id="4b759-341">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-342">CC099</span><span class="sxs-lookup"><span data-stu-id="4b759-342">CC099</span></span></td>
<td><span data-ttu-id="4b759-343">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="4b759-343">Default cost center</span></span></td>
<td><span data-ttu-id="4b759-344">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-344">10001</span></span></td>
<td><span data-ttu-id="4b759-345">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-345">Electricity</span></span></td>
<td><span data-ttu-id="4b759-346">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-346">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="4b759-347">-9,000.00</span></span></td>
<td><span data-ttu-id="4b759-348">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-349">CC001</span><span class="sxs-lookup"><span data-stu-id="4b759-349">CC001</span></span></td>
<td><span data-ttu-id="4b759-350">RH</span><span class="sxs-lookup"><span data-stu-id="4b759-350">HR</span></span></td>
<td><span data-ttu-id="4b759-351">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-351">10001</span></span></td>
<td><span data-ttu-id="4b759-352">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-352">Electricity</span></span></td>
<td><span data-ttu-id="4b759-353">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-353">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="4b759-354">1,285.71</span></span></td>
<td><span data-ttu-id="4b759-355">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-356">CC002</span><span class="sxs-lookup"><span data-stu-id="4b759-356">CC002</span></span></td>
<td><span data-ttu-id="4b759-357">Finanças</span><span class="sxs-lookup"><span data-stu-id="4b759-357">Finance</span></span></td>
<td><span data-ttu-id="4b759-358">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-358">10001</span></span></td>
<td><span data-ttu-id="4b759-359">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-359">Electricity</span></span></td>
<td><span data-ttu-id="4b759-360">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-360">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="4b759-361">7,714.29</span></span></td>
<td><span data-ttu-id="4b759-362">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b759-363">Para obter mais informações, consulte [Criar e atribuir uma política de distribuição de custos a uma unidade de controle de custos](tasks/create-assign-cost-distribution-policy-cost-control-unit.md)</span><span class="sxs-lookup"><span data-stu-id="4b759-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="4b759-364">Etapa 3: Processar o cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="4b759-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="4b759-365">A taxa de custos indiretos é usada para cobrar um ou mais objetos de custos específicos.</span><span class="sxs-lookup"><span data-stu-id="4b759-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="4b759-366">O encargo se baseia em uma taxa de custo predeterminada e a magnitude da básica de alocação atribuída.</span><span class="sxs-lookup"><span data-stu-id="4b759-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="4b759-367">Defina a taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="4b759-367">Define the overhead rate</span></span>

<span data-ttu-id="4b759-368">O objeto de custo CC001 HR contribui para um conjunto de projetos internos.</span><span class="sxs-lookup"><span data-stu-id="4b759-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="4b759-369">Um membro de dimensão estatística que é chamado de projetos de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="4b759-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b759-370">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-370">Cost object</span></span></th>
<th><span data-ttu-id="4b759-371">Horas</span><span class="sxs-lookup"><span data-stu-id="4b759-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-372">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="4b759-372">Proj 1</span></span></td>
<td><span data-ttu-id="4b759-373">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="4b759-373">Project 1</span></span></td>
<td><span data-ttu-id="4b759-374">3</span><span class="sxs-lookup"><span data-stu-id="4b759-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-375">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="4b759-375">Proj 2</span></span></td>
<td><span data-ttu-id="4b759-376">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="4b759-376">Project 2</span></span></td>
<td><span data-ttu-id="4b759-377">1</span><span class="sxs-lookup"><span data-stu-id="4b759-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b759-378">Uma taxa de custo predeterminada da contribuição de projetos de custo foi definida.</span><span class="sxs-lookup"><span data-stu-id="4b759-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b759-379">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-379">Cost object</span></span></th>
<th><span data-ttu-id="4b759-380">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-380">Cost element</span></span></th>
<th><span data-ttu-id="4b759-381">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-381">Cost behavior</span></span></th>
<th><span data-ttu-id="4b759-382">Unidades</span><span class="sxs-lookup"><span data-stu-id="4b759-382">Units</span></span></th>
<th><span data-ttu-id="4b759-383">Taxa</span><span class="sxs-lookup"><span data-stu-id="4b759-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-384">CC001</span><span class="sxs-lookup"><span data-stu-id="4b759-384">CC001</span></span></td>
<td><span data-ttu-id="4b759-385">RH</span><span class="sxs-lookup"><span data-stu-id="4b759-385">HR</span></span></td>
<td><span data-ttu-id="4b759-386">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-386">10001</span></span></td>
<td><span data-ttu-id="4b759-387">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-387">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-388">1</span><span class="sxs-lookup"><span data-stu-id="4b759-388">1</span></span></td>
<td><span data-ttu-id="4b759-389">10</span><span class="sxs-lookup"><span data-stu-id="4b759-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b759-390">A tabela a seguir mostra o resultado quando projetos de RH são aplicados como base de alocação.</span><span class="sxs-lookup"><span data-stu-id="4b759-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b759-391">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-391">Cost object</span></span></th>
<th><span data-ttu-id="4b759-392">Magnitude</span><span class="sxs-lookup"><span data-stu-id="4b759-392">Magnitude</span></span></th>
<th><span data-ttu-id="4b759-393">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-393">Cost element</span></span></th>
<th><span data-ttu-id="4b759-394">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="4b759-394">Allocation factor</span></span></th>
<th><span data-ttu-id="4b759-395">Valor</span><span class="sxs-lookup"><span data-stu-id="4b759-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-396">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="4b759-396">Proj 1</span></span></td>
<td><span data-ttu-id="4b759-397">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="4b759-397">Project 1</span></span></td>
<td><span data-ttu-id="4b759-398">3</span><span class="sxs-lookup"><span data-stu-id="4b759-398">3</span></span></td>
<td><span data-ttu-id="4b759-399">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-399">10001</span></span></td>
<td><span data-ttu-id="4b759-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="4b759-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="4b759-401">30,00</span><span class="sxs-lookup"><span data-stu-id="4b759-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-402">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="4b759-402">Proj 2</span></span></td>
<td><span data-ttu-id="4b759-403">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="4b759-403">Project 2</span></span></td>
<td><span data-ttu-id="4b759-404">1</span><span class="sxs-lookup"><span data-stu-id="4b759-404">1</span></span></td>
<td><span data-ttu-id="4b759-405">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-405">10001</span></span></td>
<td><span data-ttu-id="4b759-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="4b759-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="4b759-407">10,00</span><span class="sxs-lookup"><span data-stu-id="4b759-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="4b759-408">Diário</span><span class="sxs-lookup"><span data-stu-id="4b759-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4b759-409">Diário</span><span class="sxs-lookup"><span data-stu-id="4b759-409">Journal</span></span></th>
<th><span data-ttu-id="4b759-410">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="4b759-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="4b759-411">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="4b759-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="4b759-412">Versão</span><span class="sxs-lookup"><span data-stu-id="4b759-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-413">00003</span><span class="sxs-lookup"><span data-stu-id="4b759-413">00003</span></span></td>
<td><span data-ttu-id="4b759-414">Diário de cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="4b759-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="4b759-415">fiscal</span><span class="sxs-lookup"><span data-stu-id="4b759-415">Fiscal</span></span></td>
<td><span data-ttu-id="4b759-416">2017</span><span class="sxs-lookup"><span data-stu-id="4b759-416">2017</span></span></td>
<td><span data-ttu-id="4b759-417">Período 1</span><span class="sxs-lookup"><span data-stu-id="4b759-417">Period 1</span></span></td>
<td><span data-ttu-id="4b759-418">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="4b759-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="4b759-419">Entradas de diário (As entradas de diário para cálculo da taxa de custos indiretos)</span><span class="sxs-lookup"><span data-stu-id="4b759-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4b759-420">Data contábil</span><span class="sxs-lookup"><span data-stu-id="4b759-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="4b759-421">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-421">Cost object</span></span></th>
<th><span data-ttu-id="4b759-422">Magnitude</span><span class="sxs-lookup"><span data-stu-id="4b759-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-423">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b759-424">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="4b759-424">Proj 1</span></span></td>
<td><span data-ttu-id="4b759-425">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="4b759-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="4b759-426">3,00</span><span class="sxs-lookup"><span data-stu-id="4b759-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-427">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b759-428">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="4b759-428">Proj 2</span></span></td>
<td><span data-ttu-id="4b759-429">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="4b759-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="4b759-430">1.00</span><span class="sxs-lookup"><span data-stu-id="4b759-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="4b759-431">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b759-432">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4b759-433">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-433">Cost element</span></span></th>
<th><span data-ttu-id="4b759-434">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-434">Cost behavior</span></span></th>
<th><span data-ttu-id="4b759-435">Valor</span><span class="sxs-lookup"><span data-stu-id="4b759-435">Amount</span></span></th>
<th><span data-ttu-id="4b759-436">Data contábil</span><span class="sxs-lookup"><span data-stu-id="4b759-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="4b759-437">CC0001</span></span></td>
<td><span data-ttu-id="4b759-438">RH</span><span class="sxs-lookup"><span data-stu-id="4b759-438">HR</span></span></td>
<td><span data-ttu-id="4b759-439">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-439">10001</span></span></td>
<td><span data-ttu-id="4b759-440">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-440">Electricity</span></span></td>
<td><span data-ttu-id="4b759-441">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-441">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="4b759-442">-30.00</span></span></td>
<td><span data-ttu-id="4b759-443">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-444">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="4b759-444">Proj 1</span></span></td>
<td><span data-ttu-id="4b759-445">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="4b759-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="4b759-446">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-446">10001</span></span></td>
<td><span data-ttu-id="4b759-447">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-447">Electricity</span></span></td>
<td><span data-ttu-id="4b759-448">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-448">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-449">30,00</span><span class="sxs-lookup"><span data-stu-id="4b759-449">30.00</span></span></td>
<td><span data-ttu-id="4b759-450">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-451">CC001</span><span class="sxs-lookup"><span data-stu-id="4b759-451">CC001</span></span></td>
<td><span data-ttu-id="4b759-452">RH</span><span class="sxs-lookup"><span data-stu-id="4b759-452">HR</span></span></td>
<td><span data-ttu-id="4b759-453">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-453">10001</span></span></td>
<td><span data-ttu-id="4b759-454">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-454">Electricity</span></span></td>
<td><span data-ttu-id="4b759-455">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-455">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="4b759-456">-10.00</span></span></td>
<td><span data-ttu-id="4b759-457">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-458">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="4b759-458">Proj 2</span></span></td>
<td><span data-ttu-id="4b759-459">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="4b759-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="4b759-460">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-460">10001</span></span></td>
<td><span data-ttu-id="4b759-461">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-461">Electricity</span></span></td>
<td><span data-ttu-id="4b759-462">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-462">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-463">10,00</span><span class="sxs-lookup"><span data-stu-id="4b759-463">10.00</span></span></td>
<td><span data-ttu-id="4b759-464">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b759-465">Para obter mais informações, consulte [Realizar cálculo de custos indiretos](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="4b759-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="4b759-466">Etapa 4: Processar o cálculo de alocação de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="4b759-467">A alocação é usada para alocar o saldo de um objeto de custo a outros objetos de custo pela aplicação de uma base de alocação.</span><span class="sxs-lookup"><span data-stu-id="4b759-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="4b759-468">O Finance and Operations oferece suporte ao método de alocação recíproco.</span><span class="sxs-lookup"><span data-stu-id="4b759-468">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="4b759-469">No método de alocação recíproco, os serviços mútuos que os objetos de custo auxiliar trocam são totalmente reconhecidos.</span><span class="sxs-lookup"><span data-stu-id="4b759-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="4b759-470">O sistema determina automaticamente a ordem correta realizar as alocações.</span><span class="sxs-lookup"><span data-stu-id="4b759-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="4b759-471">O saldo de um objeto de custo é alocado por uma base de alocação única.</span><span class="sxs-lookup"><span data-stu-id="4b759-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="4b759-472">As alocações entre as dimensões de objetos de custo e os respectivos membros são suportadas.</span><span class="sxs-lookup"><span data-stu-id="4b759-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="4b759-473">A ordem de alocação é controlada pela unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="4b759-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="4b759-474">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="4b759-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="4b759-475">Defina a alocação de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-475">Define the cost allocation</span></span>

<span data-ttu-id="4b759-476">Aqui está um exemplo simples que explica como você pode rastrear o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="4b759-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="4b759-477">O objeto de custo previsto CC001 HR contribui a vários objetos de custo previsto.</span><span class="sxs-lookup"><span data-stu-id="4b759-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="4b759-478">Um membro de dimensão estatística que é chamado de serviços de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="4b759-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b759-479">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-479">Cost object</span></span></th>
<th><span data-ttu-id="4b759-480">Serviços de RH</span><span class="sxs-lookup"><span data-stu-id="4b759-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-481">CC002</span><span class="sxs-lookup"><span data-stu-id="4b759-481">CC002</span></span></td>
<td><span data-ttu-id="4b759-482">Finanças</span><span class="sxs-lookup"><span data-stu-id="4b759-482">Finance</span></span></td>
<td><span data-ttu-id="4b759-483">35</span><span class="sxs-lookup"><span data-stu-id="4b759-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-484">CC003</span><span class="sxs-lookup"><span data-stu-id="4b759-484">CC003</span></span></td>
<td><span data-ttu-id="4b759-485">Montagem</span><span class="sxs-lookup"><span data-stu-id="4b759-485">Assembly</span></span></td>
<td><span data-ttu-id="4b759-486">55</span><span class="sxs-lookup"><span data-stu-id="4b759-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-487">CC004</span><span class="sxs-lookup"><span data-stu-id="4b759-487">CC004</span></span></td>
<td><span data-ttu-id="4b759-488">Embalagem</span><span class="sxs-lookup"><span data-stu-id="4b759-488">Packaging</span></span></td>
<td><span data-ttu-id="4b759-489">10</span><span class="sxs-lookup"><span data-stu-id="4b759-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b759-490">O objeto de custo CC002 Finanças contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="4b759-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="4b759-491">Um membro de dimensão estatística que é chamado de serviços de Finanças foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="4b759-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b759-492">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-492">Cost object</span></span></th>
<th><span data-ttu-id="4b759-493">Serviços financeiros</span><span class="sxs-lookup"><span data-stu-id="4b759-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-494">CC003</span><span class="sxs-lookup"><span data-stu-id="4b759-494">CC003</span></span></td>
<td><span data-ttu-id="4b759-495">Montagem</span><span class="sxs-lookup"><span data-stu-id="4b759-495">Assembly</span></span></td>
<td><span data-ttu-id="4b759-496">65</span><span class="sxs-lookup"><span data-stu-id="4b759-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-497">CC004</span><span class="sxs-lookup"><span data-stu-id="4b759-497">CC004</span></span></td>
<td><span data-ttu-id="4b759-498">Embalagem</span><span class="sxs-lookup"><span data-stu-id="4b759-498">Packaging</span></span></td>
<td><span data-ttu-id="4b759-499">35</span><span class="sxs-lookup"><span data-stu-id="4b759-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b759-500">O objeto de custo CC003 Montagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="4b759-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="4b759-501">Um membro de dimensão estatística que é chamado de serviços de Montagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="4b759-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b759-502">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-502">Cost object</span></span></th>
<th><span data-ttu-id="4b759-503">Serviços de montagem (horas)</span><span class="sxs-lookup"><span data-stu-id="4b759-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-504">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="4b759-504">Prod 1</span></span></td>
<td><span data-ttu-id="4b759-505">Produto 1</span><span class="sxs-lookup"><span data-stu-id="4b759-505">Product 1</span></span></td>
<td><span data-ttu-id="4b759-506">60</span><span class="sxs-lookup"><span data-stu-id="4b759-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-507">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="4b759-507">Prod 2</span></span></td>
<td><span data-ttu-id="4b759-508">Produto 2</span><span class="sxs-lookup"><span data-stu-id="4b759-508">Product 2</span></span></td>
<td><span data-ttu-id="4b759-509">20</span><span class="sxs-lookup"><span data-stu-id="4b759-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b759-510">O objeto de custo CC004 Embalagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="4b759-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="4b759-511">Um membro de dimensão estatística que é chamado de serviços de Embalagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="4b759-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b759-512">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-512">Cost object</span></span></th>
<th><span data-ttu-id="4b759-513">Serviços de embalagem (horas)</span><span class="sxs-lookup"><span data-stu-id="4b759-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-514">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="4b759-514">Prod 1</span></span></td>
<td><span data-ttu-id="4b759-515">Produto 1</span><span class="sxs-lookup"><span data-stu-id="4b759-515">Product 1</span></span></td>
<td><span data-ttu-id="4b759-516">80</span><span class="sxs-lookup"><span data-stu-id="4b759-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-517">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="4b759-517">Prod 2</span></span></td>
<td><span data-ttu-id="4b759-518">Produto 2</span><span class="sxs-lookup"><span data-stu-id="4b759-518">Product 2</span></span></td>
<td><span data-ttu-id="4b759-519">15</span><span class="sxs-lookup"><span data-stu-id="4b759-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="4b759-520">No Finance and Operations, as medidas estatísticas, como as horas de produção que um produto consome, podem ser derivadas dos dados de origem.</span><span class="sxs-lookup"><span data-stu-id="4b759-520">In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="4b759-521">Para obter mais informações, consulte [Modelo de provedor de medidas estatísticas](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="4b759-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="4b759-522">A tabela a seguir mostra o resultado quando os serviços de RH são aplicados como base de alocação para custos totais (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="4b759-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b759-523">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-523">Cost object</span></span></th>
<th><span data-ttu-id="4b759-524">Magnitude</span><span class="sxs-lookup"><span data-stu-id="4b759-524">Magnitude</span></span></th>
<th><span data-ttu-id="4b759-525">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="4b759-525">Allocation factor</span></span></th>
<th><span data-ttu-id="4b759-526">Valor</span><span class="sxs-lookup"><span data-stu-id="4b759-526">Amount</span></span></th>
<th><span data-ttu-id="4b759-527">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-528">CC002</span><span class="sxs-lookup"><span data-stu-id="4b759-528">CC002</span></span></td>
<td><span data-ttu-id="4b759-529">Finanças</span><span class="sxs-lookup"><span data-stu-id="4b759-529">Finance</span></span></td>
<td><span data-ttu-id="4b759-530">35</span><span class="sxs-lookup"><span data-stu-id="4b759-530">35</span></span></td>
<td><span data-ttu-id="4b759-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="4b759-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="4b759-532">175.00</span><span class="sxs-lookup"><span data-stu-id="4b759-532">175.00</span></span></td>
<td><span data-ttu-id="4b759-533">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-534">CC003</span><span class="sxs-lookup"><span data-stu-id="4b759-534">CC003</span></span></td>
<td><span data-ttu-id="4b759-535">Montagem</span><span class="sxs-lookup"><span data-stu-id="4b759-535">Assembly</span></span></td>
<td><span data-ttu-id="4b759-536">55</span><span class="sxs-lookup"><span data-stu-id="4b759-536">55</span></span></td>
<td><span data-ttu-id="4b759-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="4b759-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="4b759-538">275.00</span><span class="sxs-lookup"><span data-stu-id="4b759-538">275.00</span></span></td>
<td><span data-ttu-id="4b759-539">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-540">CC004</span><span class="sxs-lookup"><span data-stu-id="4b759-540">CC004</span></span></td>
<td><span data-ttu-id="4b759-541">Embalagem</span><span class="sxs-lookup"><span data-stu-id="4b759-541">Packaging</span></span></td>
<td><span data-ttu-id="4b759-542">10</span><span class="sxs-lookup"><span data-stu-id="4b759-542">10</span></span></td>
<td><span data-ttu-id="4b759-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="4b759-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="4b759-544">50,00</span><span class="sxs-lookup"><span data-stu-id="4b759-544">50.00</span></span></td>
<td><span data-ttu-id="4b759-545">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-546">CC002</span><span class="sxs-lookup"><span data-stu-id="4b759-546">CC002</span></span></td>
<td><span data-ttu-id="4b759-547">Finanças</span><span class="sxs-lookup"><span data-stu-id="4b759-547">Finance</span></span></td>
<td><span data-ttu-id="4b759-548">35</span><span class="sxs-lookup"><span data-stu-id="4b759-548">35</span></span></td>
<td><span data-ttu-id="4b759-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="4b759-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="4b759-550">436.00</span><span class="sxs-lookup"><span data-stu-id="4b759-550">436.00</span></span></td>
<td><span data-ttu-id="4b759-551">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-552">CC003</span><span class="sxs-lookup"><span data-stu-id="4b759-552">CC003</span></span></td>
<td><span data-ttu-id="4b759-553">Montagem</span><span class="sxs-lookup"><span data-stu-id="4b759-553">Assembly</span></span></td>
<td><span data-ttu-id="4b759-554">55</span><span class="sxs-lookup"><span data-stu-id="4b759-554">55</span></span></td>
<td><span data-ttu-id="4b759-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="4b759-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="4b759-556">685.14</span><span class="sxs-lookup"><span data-stu-id="4b759-556">685.14</span></span></td>
<td><span data-ttu-id="4b759-557">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-558">CC004</span><span class="sxs-lookup"><span data-stu-id="4b759-558">CC004</span></span></td>
<td><span data-ttu-id="4b759-559">Embalagem</span><span class="sxs-lookup"><span data-stu-id="4b759-559">Packaging</span></span></td>
<td><span data-ttu-id="4b759-560">10</span><span class="sxs-lookup"><span data-stu-id="4b759-560">10</span></span></td>
<td><span data-ttu-id="4b759-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="4b759-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="4b759-562">124.57</span><span class="sxs-lookup"><span data-stu-id="4b759-562">124.57</span></span></td>
<td><span data-ttu-id="4b759-563">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b759-564">A tabela a seguir mostra o resultado quando os serviços financeiros são aplicados como base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="4b759-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b759-565">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-565">Cost object</span></span></th>
<th><span data-ttu-id="4b759-566">Magnitude</span><span class="sxs-lookup"><span data-stu-id="4b759-566">Magnitude</span></span></th>
<th><span data-ttu-id="4b759-567">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="4b759-567">Allocation factor</span></span></th>
<th><span data-ttu-id="4b759-568">Valor</span><span class="sxs-lookup"><span data-stu-id="4b759-568">Amount</span></span></th>
<th><span data-ttu-id="4b759-569">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-570">CC003</span><span class="sxs-lookup"><span data-stu-id="4b759-570">CC003</span></span></td>
<td><span data-ttu-id="4b759-571">Montagem</span><span class="sxs-lookup"><span data-stu-id="4b759-571">Assembly</span></span></td>
<td><span data-ttu-id="4b759-572">65</span><span class="sxs-lookup"><span data-stu-id="4b759-572">65</span></span></td>
<td><span data-ttu-id="4b759-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="4b759-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="4b759-574">438.75</span><span class="sxs-lookup"><span data-stu-id="4b759-574">438.75</span></span></td>
<td><span data-ttu-id="4b759-575">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-576">CC004</span><span class="sxs-lookup"><span data-stu-id="4b759-576">CC004</span></span></td>
<td><span data-ttu-id="4b759-577">Embalagem</span><span class="sxs-lookup"><span data-stu-id="4b759-577">Packaging</span></span></td>
<td><span data-ttu-id="4b759-578">35</span><span class="sxs-lookup"><span data-stu-id="4b759-578">35</span></span></td>
<td><span data-ttu-id="4b759-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="4b759-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="4b759-580">236.25</span><span class="sxs-lookup"><span data-stu-id="4b759-580">236.25</span></span></td>
<td><span data-ttu-id="4b759-581">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-582">CC003</span><span class="sxs-lookup"><span data-stu-id="4b759-582">CC003</span></span></td>
<td><span data-ttu-id="4b759-583">Montagem</span><span class="sxs-lookup"><span data-stu-id="4b759-583">Assembly</span></span></td>
<td><span data-ttu-id="4b759-584">65</span><span class="sxs-lookup"><span data-stu-id="4b759-584">65</span></span></td>
<td><span data-ttu-id="4b759-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="4b759-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="4b759-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="4b759-586">5,297.69</span></span></td>
<td><span data-ttu-id="4b759-587">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-588">CC004</span><span class="sxs-lookup"><span data-stu-id="4b759-588">CC004</span></span></td>
<td><span data-ttu-id="4b759-589">Embalagem</span><span class="sxs-lookup"><span data-stu-id="4b759-589">Packaging</span></span></td>
<td><span data-ttu-id="4b759-590">35</span><span class="sxs-lookup"><span data-stu-id="4b759-590">35</span></span></td>
<td><span data-ttu-id="4b759-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="4b759-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="4b759-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="4b759-592">2,852.60</span></span></td>
<td><span data-ttu-id="4b759-593">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b759-594">A tabela a seguir mostra o resultado quando os serviços de Montagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="4b759-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b759-595">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-595">Cost object</span></span></th>
<th><span data-ttu-id="4b759-596">Magnitude</span><span class="sxs-lookup"><span data-stu-id="4b759-596">Magnitude</span></span></th>
<th><span data-ttu-id="4b759-597">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="4b759-597">Allocation factor</span></span></th>
<th><span data-ttu-id="4b759-598">Valor</span><span class="sxs-lookup"><span data-stu-id="4b759-598">Amount</span></span></th>
<th><span data-ttu-id="4b759-599">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-600">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="4b759-600">Prod 1</span></span></td>
<td><span data-ttu-id="4b759-601">Produto 1</span><span class="sxs-lookup"><span data-stu-id="4b759-601">Product 1</span></span></td>
<td><span data-ttu-id="4b759-602">60</span><span class="sxs-lookup"><span data-stu-id="4b759-602">60</span></span></td>
<td><span data-ttu-id="4b759-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="4b759-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="4b759-604">535.31</span><span class="sxs-lookup"><span data-stu-id="4b759-604">535.31</span></span></td>
<td><span data-ttu-id="4b759-605">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-606">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="4b759-606">Prod 2</span></span></td>
<td><span data-ttu-id="4b759-607">Produto 2</span><span class="sxs-lookup"><span data-stu-id="4b759-607">Product 2</span></span></td>
<td><span data-ttu-id="4b759-608">20</span><span class="sxs-lookup"><span data-stu-id="4b759-608">20</span></span></td>
<td><span data-ttu-id="4b759-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="4b759-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="4b759-610">178.44</span><span class="sxs-lookup"><span data-stu-id="4b759-610">178.44</span></span></td>
<td><span data-ttu-id="4b759-611">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-612">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="4b759-612">Prod 1</span></span></td>
<td><span data-ttu-id="4b759-613">Produto 1</span><span class="sxs-lookup"><span data-stu-id="4b759-613">Product 1</span></span></td>
<td><span data-ttu-id="4b759-614">60</span><span class="sxs-lookup"><span data-stu-id="4b759-614">60</span></span></td>
<td><span data-ttu-id="4b759-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="4b759-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="4b759-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="4b759-616">4,487.12</span></span></td>
<td><span data-ttu-id="4b759-617">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-618">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="4b759-618">Prod 2</span></span></td>
<td><span data-ttu-id="4b759-619">Produto 2</span><span class="sxs-lookup"><span data-stu-id="4b759-619">Product 2</span></span></td>
<td><span data-ttu-id="4b759-620">20</span><span class="sxs-lookup"><span data-stu-id="4b759-620">20</span></span></td>
<td><span data-ttu-id="4b759-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="4b759-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="4b759-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="4b759-622">1,495.71</span></span></td>
<td><span data-ttu-id="4b759-623">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b759-624">A tabela a seguir mostra o resultado quando os serviços de Embalagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="4b759-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b759-625">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-625">Cost object</span></span></th>
<th><span data-ttu-id="4b759-626">Magnitude</span><span class="sxs-lookup"><span data-stu-id="4b759-626">Magnitude</span></span></th>
<th><span data-ttu-id="4b759-627">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="4b759-627">Allocation factor</span></span></th>
<th><span data-ttu-id="4b759-628">Valor</span><span class="sxs-lookup"><span data-stu-id="4b759-628">Amount</span></span></th>
<th><span data-ttu-id="4b759-629">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-630">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="4b759-630">Prod 1</span></span></td>
<td><span data-ttu-id="4b759-631">Produto 1</span><span class="sxs-lookup"><span data-stu-id="4b759-631">Product 1</span></span></td>
<td><span data-ttu-id="4b759-632">80</span><span class="sxs-lookup"><span data-stu-id="4b759-632">80</span></span></td>
<td><span data-ttu-id="4b759-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="4b759-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="4b759-634">241.05</span><span class="sxs-lookup"><span data-stu-id="4b759-634">241.05</span></span></td>
<td><span data-ttu-id="4b759-635">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-636">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="4b759-636">Prod 2</span></span></td>
<td><span data-ttu-id="4b759-637">Produto 2</span><span class="sxs-lookup"><span data-stu-id="4b759-637">Product 2</span></span></td>
<td><span data-ttu-id="4b759-638">15</span><span class="sxs-lookup"><span data-stu-id="4b759-638">15</span></span></td>
<td><span data-ttu-id="4b759-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="4b759-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="4b759-640">45.20</span><span class="sxs-lookup"><span data-stu-id="4b759-640">45.20</span></span></td>
<td><span data-ttu-id="4b759-641">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-642">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="4b759-642">Prod 1</span></span></td>
<td><span data-ttu-id="4b759-643">Produto 1</span><span class="sxs-lookup"><span data-stu-id="4b759-643">Product 1</span></span></td>
<td><span data-ttu-id="4b759-644">80</span><span class="sxs-lookup"><span data-stu-id="4b759-644">80</span></span></td>
<td><span data-ttu-id="4b759-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="4b759-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="4b759-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="4b759-646">2,507.09</span></span></td>
<td><span data-ttu-id="4b759-647">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-648">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="4b759-648">Prod 2</span></span></td>
<td><span data-ttu-id="4b759-649">Produto 2</span><span class="sxs-lookup"><span data-stu-id="4b759-649">Product 2</span></span></td>
<td><span data-ttu-id="4b759-650">15</span><span class="sxs-lookup"><span data-stu-id="4b759-650">15</span></span></td>
<td><span data-ttu-id="4b759-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="4b759-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="4b759-652">470.08</span><span class="sxs-lookup"><span data-stu-id="4b759-652">470.08</span></span></td>
<td><span data-ttu-id="4b759-653">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="4b759-654">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="4b759-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4b759-655">Diário</span><span class="sxs-lookup"><span data-stu-id="4b759-655">Journal</span></span></th>
<th><span data-ttu-id="4b759-656">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="4b759-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="4b759-657">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="4b759-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="4b759-658">Versão</span><span class="sxs-lookup"><span data-stu-id="4b759-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-659">00004</span><span class="sxs-lookup"><span data-stu-id="4b759-659">00004</span></span></td>
<td><span data-ttu-id="4b759-660">Diário de alocação de custos</span><span class="sxs-lookup"><span data-stu-id="4b759-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="4b759-661">fiscal</span><span class="sxs-lookup"><span data-stu-id="4b759-661">Fiscal</span></span></td>
<td><span data-ttu-id="4b759-662">2017</span><span class="sxs-lookup"><span data-stu-id="4b759-662">2017</span></span></td>
<td><span data-ttu-id="4b759-663">Período 1</span><span class="sxs-lookup"><span data-stu-id="4b759-663">Period 1</span></span></td>
<td><span data-ttu-id="4b759-664">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="4b759-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="4b759-665">Linhas do diário</span><span class="sxs-lookup"><span data-stu-id="4b759-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4b759-666">Data contábil</span><span class="sxs-lookup"><span data-stu-id="4b759-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="4b759-667">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4b759-668">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-668">Cost element</span></span></th>
<th><span data-ttu-id="4b759-669">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-669">Cost behavior</span></span></th>
<th><span data-ttu-id="4b759-670">Valor</span><span class="sxs-lookup"><span data-stu-id="4b759-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-671">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b759-672">CC001</span><span class="sxs-lookup"><span data-stu-id="4b759-672">CC001</span></span></td>
<td><span data-ttu-id="4b759-673">RH</span><span class="sxs-lookup"><span data-stu-id="4b759-673">HR</span></span></td>
<td><span data-ttu-id="4b759-674">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-674">10001</span></span></td>
<td><span data-ttu-id="4b759-675">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-675">Electricity</span></span></td>
<td><span data-ttu-id="4b759-676">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-676">Fixed cost</span></span></td>
<td><span data-ttu-id="4b759-677">500,00</span><span class="sxs-lookup"><span data-stu-id="4b759-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-678">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b759-679">CC001</span><span class="sxs-lookup"><span data-stu-id="4b759-679">CC001</span></span></td>
<td><span data-ttu-id="4b759-680">RH</span><span class="sxs-lookup"><span data-stu-id="4b759-680">HR</span></span></td>
<td><span data-ttu-id="4b759-681">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-681">10001</span></span></td>
<td><span data-ttu-id="4b759-682">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-682">Electricity</span></span></td>
<td><span data-ttu-id="4b759-683">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-683">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="4b759-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-685">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b759-686">CC002</span><span class="sxs-lookup"><span data-stu-id="4b759-686">CC002</span></span></td>
<td><span data-ttu-id="4b759-687">Finanças</span><span class="sxs-lookup"><span data-stu-id="4b759-687">Finance</span></span></td>
<td><span data-ttu-id="4b759-688">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-688">10001</span></span></td>
<td><span data-ttu-id="4b759-689">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-689">Electricity</span></span></td>
<td><span data-ttu-id="4b759-690">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-690">Fixed cost</span></span></td>
<td><span data-ttu-id="4b759-691">675.00</span><span class="sxs-lookup"><span data-stu-id="4b759-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-692">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b759-693">CC002</span><span class="sxs-lookup"><span data-stu-id="4b759-693">CC002</span></span></td>
<td><span data-ttu-id="4b759-694">Finanças</span><span class="sxs-lookup"><span data-stu-id="4b759-694">Finance</span></span></td>
<td><span data-ttu-id="4b759-695">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-695">10001</span></span></td>
<td><span data-ttu-id="4b759-696">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-696">Electricity</span></span></td>
<td><span data-ttu-id="4b759-697">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-697">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="4b759-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-699">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b759-700">CC003</span><span class="sxs-lookup"><span data-stu-id="4b759-700">CC003</span></span></td>
<td><span data-ttu-id="4b759-701">Montagem</span><span class="sxs-lookup"><span data-stu-id="4b759-701">Assembly</span></span></td>
<td><span data-ttu-id="4b759-702">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-702">10001</span></span></td>
<td><span data-ttu-id="4b759-703">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-703">Electricity</span></span></td>
<td><span data-ttu-id="4b759-704">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-704">Fixed cost</span></span></td>
<td><span data-ttu-id="4b759-705">713.75</span><span class="sxs-lookup"><span data-stu-id="4b759-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-706">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b759-707">CC003</span><span class="sxs-lookup"><span data-stu-id="4b759-707">CC003</span></span></td>
<td><span data-ttu-id="4b759-708">Montagem</span><span class="sxs-lookup"><span data-stu-id="4b759-708">Assembly</span></span></td>
<td><span data-ttu-id="4b759-709">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-709">10001</span></span></td>
<td><span data-ttu-id="4b759-710">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-710">Electricity</span></span></td>
<td><span data-ttu-id="4b759-711">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-711">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="4b759-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-713">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b759-714">CC003</span><span class="sxs-lookup"><span data-stu-id="4b759-714">CC003</span></span></td>
<td><span data-ttu-id="4b759-715">Embalagem</span><span class="sxs-lookup"><span data-stu-id="4b759-715">Packaging</span></span></td>
<td><span data-ttu-id="4b759-716">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-716">10001</span></span></td>
<td><span data-ttu-id="4b759-717">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-717">Electricity</span></span></td>
<td><span data-ttu-id="4b759-718">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-718">Fixed cost</span></span></td>
<td><span data-ttu-id="4b759-719">286.25</span><span class="sxs-lookup"><span data-stu-id="4b759-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-720">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b759-721">CC003</span><span class="sxs-lookup"><span data-stu-id="4b759-721">CC003</span></span></td>
<td><span data-ttu-id="4b759-722">Embalagem</span><span class="sxs-lookup"><span data-stu-id="4b759-722">Packaging</span></span></td>
<td><span data-ttu-id="4b759-723">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-723">10001</span></span></td>
<td><span data-ttu-id="4b759-724">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-724">Electricity</span></span></td>
<td><span data-ttu-id="4b759-725">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-725">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="4b759-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-727">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b759-728">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="4b759-728">Prod 1</span></span></td>
<td><span data-ttu-id="4b759-729">Produto 1</span><span class="sxs-lookup"><span data-stu-id="4b759-729">Product 1</span></span></td>
<td><span data-ttu-id="4b759-730">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-730">10001</span></span></td>
<td><span data-ttu-id="4b759-731">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-731">Electricity</span></span></td>
<td><span data-ttu-id="4b759-732">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-732">Fixed cost</span></span></td>
<td><span data-ttu-id="4b759-733">776.36</span><span class="sxs-lookup"><span data-stu-id="4b759-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-734">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b759-735">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="4b759-735">Prod 1</span></span></td>
<td><span data-ttu-id="4b759-736">Produto 1</span><span class="sxs-lookup"><span data-stu-id="4b759-736">Product 1</span></span></td>
<td><span data-ttu-id="4b759-737">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-737">10001</span></span></td>
<td><span data-ttu-id="4b759-738">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-738">Electricity</span></span></td>
<td><span data-ttu-id="4b759-739">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-739">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="4b759-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-741">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b759-742">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="4b759-742">Prod 2</span></span></td>
<td><span data-ttu-id="4b759-743">Produto 1</span><span class="sxs-lookup"><span data-stu-id="4b759-743">Product 1</span></span></td>
<td><span data-ttu-id="4b759-744">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-744">10001</span></span></td>
<td><span data-ttu-id="4b759-745">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-745">Electricity</span></span></td>
<td><span data-ttu-id="4b759-746">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-746">Fixed cost</span></span></td>
<td><span data-ttu-id="4b759-747">223.64</span><span class="sxs-lookup"><span data-stu-id="4b759-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-748">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b759-749">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="4b759-749">Prod 2</span></span></td>
<td><span data-ttu-id="4b759-750">Produto 1</span><span class="sxs-lookup"><span data-stu-id="4b759-750">Product 1</span></span></td>
<td><span data-ttu-id="4b759-751">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-751">10001</span></span></td>
<td><span data-ttu-id="4b759-752">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-752">Electricity</span></span></td>
<td><span data-ttu-id="4b759-753">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-753">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="4b759-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="4b759-755">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b759-756">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4b759-757">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-757">Cost element</span></span></th>
<th><span data-ttu-id="4b759-758">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-758">Cost behavior</span></span></th>
<th><span data-ttu-id="4b759-759">Valor</span><span class="sxs-lookup"><span data-stu-id="4b759-759">Amount</span></span></th>
<th><span data-ttu-id="4b759-760">Data contábil</span><span class="sxs-lookup"><span data-stu-id="4b759-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b759-761">CC001</span><span class="sxs-lookup"><span data-stu-id="4b759-761">CC001</span></span></td>
<td><span data-ttu-id="4b759-762">RH</span><span class="sxs-lookup"><span data-stu-id="4b759-762">HR</span></span></td>
<td><span data-ttu-id="4b759-763">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-763">10001</span></span></td>
<td><span data-ttu-id="4b759-764">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-764">Electricity</span></span></td>
<td><span data-ttu-id="4b759-765">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-765">Fixed cost</span></span></td>
<td><span data-ttu-id="4b759-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="4b759-766">-500.00</span></span></td>
<td><span data-ttu-id="4b759-767">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-768">CC002</span><span class="sxs-lookup"><span data-stu-id="4b759-768">CC002</span></span></td>
<td><span data-ttu-id="4b759-769">Finanças</span><span class="sxs-lookup"><span data-stu-id="4b759-769">Finance</span></span></td>
<td><span data-ttu-id="4b759-770">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-770">10001</span></span></td>
<td><span data-ttu-id="4b759-771">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-771">Electricity</span></span></td>
<td><span data-ttu-id="4b759-772">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-772">Fixed cost</span></span></td>
<td><span data-ttu-id="4b759-773">175.00</span><span class="sxs-lookup"><span data-stu-id="4b759-773">175.00</span></span></td>
<td><span data-ttu-id="4b759-774">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-775">CC003</span><span class="sxs-lookup"><span data-stu-id="4b759-775">CC003</span></span></td>
<td><span data-ttu-id="4b759-776">Montagem</span><span class="sxs-lookup"><span data-stu-id="4b759-776">Assembly</span></span></td>
<td><span data-ttu-id="4b759-777">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-777">10001</span></span></td>
<td><span data-ttu-id="4b759-778">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-778">Electricity</span></span></td>
<td><span data-ttu-id="4b759-779">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-779">Fixed cost</span></span></td>
<td><span data-ttu-id="4b759-780">275.00</span><span class="sxs-lookup"><span data-stu-id="4b759-780">275.00</span></span></td>
<td><span data-ttu-id="4b759-781">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-782">CC004</span><span class="sxs-lookup"><span data-stu-id="4b759-782">CC004</span></span></td>
<td><span data-ttu-id="4b759-783">Embalagem</span><span class="sxs-lookup"><span data-stu-id="4b759-783">Packaging</span></span></td>
<td><span data-ttu-id="4b759-784">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-784">10001</span></span></td>
<td><span data-ttu-id="4b759-785">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-785">Electricity</span></span></td>
<td><span data-ttu-id="4b759-786">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-786">Fixed cost</span></span></td>
<td><span data-ttu-id="4b759-787">50,00</span><span class="sxs-lookup"><span data-stu-id="4b759-787">50,00</span></span></td>
<td><span data-ttu-id="4b759-788">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-789">CC001</span><span class="sxs-lookup"><span data-stu-id="4b759-789">CC001</span></span></td>
<td><span data-ttu-id="4b759-790">RH</span><span class="sxs-lookup"><span data-stu-id="4b759-790">HR</span></span></td>
<td><span data-ttu-id="4b759-791">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-791">10001</span></span></td>
<td><span data-ttu-id="4b759-792">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-792">Electricity</span></span></td>
<td><span data-ttu-id="4b759-793">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-793">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="4b759-794">-1,245.71</span></span></td>
<td><span data-ttu-id="4b759-795">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-796">CC002</span><span class="sxs-lookup"><span data-stu-id="4b759-796">CC002</span></span></td>
<td><span data-ttu-id="4b759-797">Finanças</span><span class="sxs-lookup"><span data-stu-id="4b759-797">Finance</span></span></td>
<td><span data-ttu-id="4b759-798">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-798">10001</span></span></td>
<td><span data-ttu-id="4b759-799">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-799">Electricity</span></span></td>
<td><span data-ttu-id="4b759-800">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-800">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-801">436.00</span><span class="sxs-lookup"><span data-stu-id="4b759-801">436.00</span></span></td>
<td><span data-ttu-id="4b759-802">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-803">CC003</span><span class="sxs-lookup"><span data-stu-id="4b759-803">CC003</span></span></td>
<td><span data-ttu-id="4b759-804">Montagem</span><span class="sxs-lookup"><span data-stu-id="4b759-804">Assembly</span></span></td>
<td><span data-ttu-id="4b759-805">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-805">10001</span></span></td>
<td><span data-ttu-id="4b759-806">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-806">Electricity</span></span></td>
<td><span data-ttu-id="4b759-807">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-807">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-808">685.14</span><span class="sxs-lookup"><span data-stu-id="4b759-808">685.14</span></span></td>
<td><span data-ttu-id="4b759-809">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-810">CC004</span><span class="sxs-lookup"><span data-stu-id="4b759-810">CC004</span></span></td>
<td><span data-ttu-id="4b759-811">Embalagem</span><span class="sxs-lookup"><span data-stu-id="4b759-811">Packaging</span></span></td>
<td><span data-ttu-id="4b759-812">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-812">10001</span></span></td>
<td><span data-ttu-id="4b759-813">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-813">Electricity</span></span></td>
<td><span data-ttu-id="4b759-814">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-814">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-815">124.57</span><span class="sxs-lookup"><span data-stu-id="4b759-815">124.57</span></span></td>
<td><span data-ttu-id="4b759-816">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-817">CC002</span><span class="sxs-lookup"><span data-stu-id="4b759-817">CC002</span></span></td>
<td><span data-ttu-id="4b759-818">Finanças</span><span class="sxs-lookup"><span data-stu-id="4b759-818">Finance</span></span></td>
<td><span data-ttu-id="4b759-819">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-819">10001</span></span></td>
<td><span data-ttu-id="4b759-820">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-820">Electricity</span></span></td>
<td><span data-ttu-id="4b759-821">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-821">Fixed cost</span></span></td>
<td><span data-ttu-id="4b759-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="4b759-822">-675.00</span></span></td>
<td><span data-ttu-id="4b759-823">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-824">CC003</span><span class="sxs-lookup"><span data-stu-id="4b759-824">CC003</span></span></td>
<td><span data-ttu-id="4b759-825">Montagem</span><span class="sxs-lookup"><span data-stu-id="4b759-825">Assembly</span></span></td>
<td><span data-ttu-id="4b759-826">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-826">10001</span></span></td>
<td><span data-ttu-id="4b759-827">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-827">Electricity</span></span></td>
<td><span data-ttu-id="4b759-828">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-828">Fixed cost</span></span></td>
<td><span data-ttu-id="4b759-829">438.75</span><span class="sxs-lookup"><span data-stu-id="4b759-829">438.75</span></span></td>
<td><span data-ttu-id="4b759-830">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-831">CC004</span><span class="sxs-lookup"><span data-stu-id="4b759-831">CC004</span></span></td>
<td><span data-ttu-id="4b759-832">Embalagem</span><span class="sxs-lookup"><span data-stu-id="4b759-832">Packaging</span></span></td>
<td><span data-ttu-id="4b759-833">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-833">10001</span></span></td>
<td><span data-ttu-id="4b759-834">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-834">Electricity</span></span></td>
<td><span data-ttu-id="4b759-835">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-835">Fixed cost</span></span></td>
<td><span data-ttu-id="4b759-836">236.25</span><span class="sxs-lookup"><span data-stu-id="4b759-836">236.25</span></span></td>
<td><span data-ttu-id="4b759-837">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-838">CC002</span><span class="sxs-lookup"><span data-stu-id="4b759-838">CC002</span></span></td>
<td><span data-ttu-id="4b759-839">Finanças</span><span class="sxs-lookup"><span data-stu-id="4b759-839">Finance</span></span></td>
<td><span data-ttu-id="4b759-840">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-840">10001</span></span></td>
<td><span data-ttu-id="4b759-841">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-841">Electricity</span></span></td>
<td><span data-ttu-id="4b759-842">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-842">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="4b759-843">-8,150.29</span></span></td>
<td><span data-ttu-id="4b759-844">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-845">CC003</span><span class="sxs-lookup"><span data-stu-id="4b759-845">CC003</span></span></td>
<td><span data-ttu-id="4b759-846">Montagem</span><span class="sxs-lookup"><span data-stu-id="4b759-846">Assembly</span></span></td>
<td><span data-ttu-id="4b759-847">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-847">10001</span></span></td>
<td><span data-ttu-id="4b759-848">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-848">Electricity</span></span></td>
<td><span data-ttu-id="4b759-849">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-849">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="4b759-850">5,297.69</span></span></td>
<td><span data-ttu-id="4b759-851">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-852">CC004</span><span class="sxs-lookup"><span data-stu-id="4b759-852">CC004</span></span></td>
<td><span data-ttu-id="4b759-853">Embalagem</span><span class="sxs-lookup"><span data-stu-id="4b759-853">Packaging</span></span></td>
<td><span data-ttu-id="4b759-854">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-854">10001</span></span></td>
<td><span data-ttu-id="4b759-855">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-855">Electricity</span></span></td>
<td><span data-ttu-id="4b759-856">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-856">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="4b759-857">2,852.60</span></span></td>
<td><span data-ttu-id="4b759-858">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-859">CC003</span><span class="sxs-lookup"><span data-stu-id="4b759-859">CC003</span></span></td>
<td><span data-ttu-id="4b759-860">Montagem</span><span class="sxs-lookup"><span data-stu-id="4b759-860">Assembly</span></span></td>
<td><span data-ttu-id="4b759-861">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-861">10001</span></span></td>
<td><span data-ttu-id="4b759-862">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-862">Electricity</span></span></td>
<td><span data-ttu-id="4b759-863">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-863">Fixed cost</span></span></td>
<td><span data-ttu-id="4b759-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="4b759-864">-713.75</span></span></td>
<td><span data-ttu-id="4b759-865">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-866">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="4b759-866">Prod 1</span></span></td>
<td><span data-ttu-id="4b759-867">Produto 1</span><span class="sxs-lookup"><span data-stu-id="4b759-867">Product 1</span></span></td>
<td><span data-ttu-id="4b759-868">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-868">10001</span></span></td>
<td><span data-ttu-id="4b759-869">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-869">Electricity</span></span></td>
<td><span data-ttu-id="4b759-870">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-870">Fixed cost</span></span></td>
<td><span data-ttu-id="4b759-871">535.31</span><span class="sxs-lookup"><span data-stu-id="4b759-871">535.31</span></span></td>
<td><span data-ttu-id="4b759-872">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-873">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="4b759-873">Prod 2</span></span></td>
<td><span data-ttu-id="4b759-874">Produto 2</span><span class="sxs-lookup"><span data-stu-id="4b759-874">Product 2</span></span></td>
<td><span data-ttu-id="4b759-875">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-875">10001</span></span></td>
<td><span data-ttu-id="4b759-876">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-876">Electricity</span></span></td>
<td><span data-ttu-id="4b759-877">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-877">Fixed cost</span></span></td>
<td><span data-ttu-id="4b759-878">178.44</span><span class="sxs-lookup"><span data-stu-id="4b759-878">178.44</span></span></td>
<td><span data-ttu-id="4b759-879">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-880">CC003</span><span class="sxs-lookup"><span data-stu-id="4b759-880">CC003</span></span></td>
<td><span data-ttu-id="4b759-881">Montagem</span><span class="sxs-lookup"><span data-stu-id="4b759-881">Assembly</span></span></td>
<td><span data-ttu-id="4b759-882">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-882">10001</span></span></td>
<td><span data-ttu-id="4b759-883">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-883">Electricity</span></span></td>
<td><span data-ttu-id="4b759-884">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-884">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="4b759-885">-5,982.83</span></span></td>
<td><span data-ttu-id="4b759-886">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-887">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="4b759-887">Prod 1</span></span></td>
<td><span data-ttu-id="4b759-888">Produto 1</span><span class="sxs-lookup"><span data-stu-id="4b759-888">Product 1</span></span></td>
<td><span data-ttu-id="4b759-889">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-889">10001</span></span></td>
<td><span data-ttu-id="4b759-890">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-890">Electricity</span></span></td>
<td><span data-ttu-id="4b759-891">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-891">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="4b759-892">4,487.12</span></span></td>
<td><span data-ttu-id="4b759-893">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-894">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="4b759-894">Prod 2</span></span></td>
<td><span data-ttu-id="4b759-895">Produto 2</span><span class="sxs-lookup"><span data-stu-id="4b759-895">Product 2</span></span></td>
<td><span data-ttu-id="4b759-896">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-896">10001</span></span></td>
<td><span data-ttu-id="4b759-897">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-897">Electricity</span></span></td>
<td><span data-ttu-id="4b759-898">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-898">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="4b759-899">1,495.71</span></span></td>
<td><span data-ttu-id="4b759-900">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-901">CC003</span><span class="sxs-lookup"><span data-stu-id="4b759-901">CC003</span></span></td>
<td><span data-ttu-id="4b759-902">Montagem</span><span class="sxs-lookup"><span data-stu-id="4b759-902">Assembly</span></span></td>
<td><span data-ttu-id="4b759-903">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-903">10001</span></span></td>
<td><span data-ttu-id="4b759-904">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-904">Electricity</span></span></td>
<td><span data-ttu-id="4b759-905">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-905">Fixed cost</span></span></td>
<td><span data-ttu-id="4b759-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="4b759-906">-286.25</span></span></td>
<td><span data-ttu-id="4b759-907">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-908">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="4b759-908">Prod 1</span></span></td>
<td><span data-ttu-id="4b759-909">Produto 1</span><span class="sxs-lookup"><span data-stu-id="4b759-909">Product 1</span></span></td>
<td><span data-ttu-id="4b759-910">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-910">10001</span></span></td>
<td><span data-ttu-id="4b759-911">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-911">Electricity</span></span></td>
<td><span data-ttu-id="4b759-912">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-912">Fixed cost</span></span></td>
<td><span data-ttu-id="4b759-913">241.05</span><span class="sxs-lookup"><span data-stu-id="4b759-913">241.05</span></span></td>
<td><span data-ttu-id="4b759-914">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-915">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="4b759-915">Prod 2</span></span></td>
<td><span data-ttu-id="4b759-916">Produto 2</span><span class="sxs-lookup"><span data-stu-id="4b759-916">Product 2</span></span></td>
<td><span data-ttu-id="4b759-917">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-917">10001</span></span></td>
<td><span data-ttu-id="4b759-918">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-918">Electricity</span></span></td>
<td><span data-ttu-id="4b759-919">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-919">Fixed cost</span></span></td>
<td><span data-ttu-id="4b759-920">45.20</span><span class="sxs-lookup"><span data-stu-id="4b759-920">45.20</span></span></td>
<td><span data-ttu-id="4b759-921">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-922">CC003</span><span class="sxs-lookup"><span data-stu-id="4b759-922">CC003</span></span></td>
<td><span data-ttu-id="4b759-923">Montagem</span><span class="sxs-lookup"><span data-stu-id="4b759-923">Assembly</span></span></td>
<td><span data-ttu-id="4b759-924">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-924">10001</span></span></td>
<td><span data-ttu-id="4b759-925">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-925">Electricity</span></span></td>
<td><span data-ttu-id="4b759-926">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-926">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="4b759-927">-2,977.17</span></span></td>
<td><span data-ttu-id="4b759-928">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-929">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="4b759-929">Prod 1</span></span></td>
<td><span data-ttu-id="4b759-930">Produto 1</span><span class="sxs-lookup"><span data-stu-id="4b759-930">Product 1</span></span></td>
<td><span data-ttu-id="4b759-931">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-931">10001</span></span></td>
<td><span data-ttu-id="4b759-932">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-932">Electricity</span></span></td>
<td><span data-ttu-id="4b759-933">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-933">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="4b759-934">2,507.09</span></span></td>
<td><span data-ttu-id="4b759-935">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b759-936">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="4b759-936">Prod 2</span></span></td>
<td><span data-ttu-id="4b759-937">Produto 2</span><span class="sxs-lookup"><span data-stu-id="4b759-937">Product 2</span></span></td>
<td><span data-ttu-id="4b759-938">10001</span><span class="sxs-lookup"><span data-stu-id="4b759-938">10001</span></span></td>
<td><span data-ttu-id="4b759-939">eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-939">Electricity</span></span></td>
<td><span data-ttu-id="4b759-940">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-940">Variable cost</span></span></td>
<td><span data-ttu-id="4b759-941">470.08</span><span class="sxs-lookup"><span data-stu-id="4b759-941">470.08</span></span></td>
<td><span data-ttu-id="4b759-942">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="4b759-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="4b759-943">Conclusão</span><span class="sxs-lookup"><span data-stu-id="4b759-943">Conclusion</span></span>
<span data-ttu-id="4b759-944">Na contabilidade financeira, um custo de 10,000.00 para a eletricidade é lançado para um ID fictício de centro de custos.</span><span class="sxs-lookup"><span data-stu-id="4b759-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="4b759-945">Portanto, os contadores de custo saberão que esses custos devem ser alocados.</span><span class="sxs-lookup"><span data-stu-id="4b759-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="4b759-946">Na contabilização de custo, os custos fluem nas unidades organizacionais e nos níveis, com base nas políticas e regras que são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="4b759-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="4b759-947">Cada custo foi associado a uma base de alocação que fornece a melhor apuração para a alocação de custos.</span><span class="sxs-lookup"><span data-stu-id="4b759-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="4b759-948">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="4b759-949">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="4b759-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="4b759-950">Total</span><span class="sxs-lookup"><span data-stu-id="4b759-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="4b759-951">CC099</span><span class="sxs-lookup"><span data-stu-id="4b759-951">CC099</span></span></th>
<th><span data-ttu-id="4b759-952">CC001</span><span class="sxs-lookup"><span data-stu-id="4b759-952">CC001</span></span></th>
<th><span data-ttu-id="4b759-953">CC002</span><span class="sxs-lookup"><span data-stu-id="4b759-953">CC002</span></span></th>
<th><span data-ttu-id="4b759-954">CC003</span><span class="sxs-lookup"><span data-stu-id="4b759-954">CC003</span></span></th>
<th><span data-ttu-id="4b759-955">CC004</span><span class="sxs-lookup"><span data-stu-id="4b759-955">CC004</span></span></th>
<th><span data-ttu-id="4b759-956">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="4b759-956">Proj 1</span></span></th>
<th><span data-ttu-id="4b759-957">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="4b759-957">Proj 2</span></span></th>
<th><span data-ttu-id="4b759-958">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="4b759-958">Prod 1</span></span></th>
<th><span data-ttu-id="4b759-959">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="4b759-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="4b759-960">10001 Eletricidade</span><span class="sxs-lookup"><span data-stu-id="4b759-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="4b759-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="4b759-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="4b759-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="4b759-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="4b759-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="4b759-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="4b759-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="4b759-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="4b759-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="4b759-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="4b759-970">Não classificado</span><span class="sxs-lookup"><span data-stu-id="4b759-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-971">0,00</span><span class="sxs-lookup"><span data-stu-id="4b759-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="4b759-972">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="4b759-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-973">0,00</span><span class="sxs-lookup"><span data-stu-id="4b759-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-974">0,00</span><span class="sxs-lookup"><span data-stu-id="4b759-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-975">0,00</span><span class="sxs-lookup"><span data-stu-id="4b759-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-976">0,00</span><span class="sxs-lookup"><span data-stu-id="4b759-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-977">0,00</span><span class="sxs-lookup"><span data-stu-id="4b759-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="4b759-978">776.36</span><span class="sxs-lookup"><span data-stu-id="4b759-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-979">223.64</span><span class="sxs-lookup"><span data-stu-id="4b759-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="4b759-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="4b759-981">Custo variável</span><span class="sxs-lookup"><span data-stu-id="4b759-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-982">000</span><span class="sxs-lookup"><span data-stu-id="4b759-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-983">0,00</span><span class="sxs-lookup"><span data-stu-id="4b759-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-984">0,00</span><span class="sxs-lookup"><span data-stu-id="4b759-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-985">0,00</span><span class="sxs-lookup"><span data-stu-id="4b759-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-986">0,00</span><span class="sxs-lookup"><span data-stu-id="4b759-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-987">30,00</span><span class="sxs-lookup"><span data-stu-id="4b759-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-988">10,00</span><span class="sxs-lookup"><span data-stu-id="4b759-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="4b759-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="4b759-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b759-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="4b759-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="4b759-992">Esse tópico mostra como um elemento de custo principal, 10001 Eletricidade flui pelos objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="4b759-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="4b759-993">Portanto, esse custo geral indireto é alocado no nível mais baixo na organização.</span><span class="sxs-lookup"><span data-stu-id="4b759-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="4b759-994">Em outras palavras, os objetos de custo no nível mais baixo assumem o custo.</span><span class="sxs-lookup"><span data-stu-id="4b759-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="4b759-995">Se você exigir um fluxo visual de custo entre objetos de custo, é possível usar as regras de política de acúmulo de custos para visualizar o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="4b759-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="4b759-996">Para maiores informações, consulte [Acúmulo de custo](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="4b759-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>



