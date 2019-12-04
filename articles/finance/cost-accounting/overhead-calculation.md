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
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 954e0669c3d24bcc20fe667c22b7dcc367aba1e7
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770795"
---
# <a name="overhead-calculation"></a><span data-ttu-id="3ee1e-103">Cálculo de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="3ee1e-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3ee1e-104">Este tópico descreve processos comuns para calcular e alocar os custos gerais indiretos.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="3ee1e-105">Definição de termo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-105">Term definition</span></span>
---------------

<span data-ttu-id="3ee1e-106">Os custos gerais indiretos são aqueles que foram incorridos para realizar um negócio, mas não podem ser diretamente atribuídos a qualquer atividade comercial, produto ou serviço específico.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="3ee1e-107">Os custos gerais indiretos fornecem suporte crítico para geração de atividades produtivas.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="3ee1e-108">Eis alguns exemplos de custos gerais:</span><span class="sxs-lookup"><span data-stu-id="3ee1e-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="3ee1e-109">Aluguel</span><span class="sxs-lookup"><span data-stu-id="3ee1e-109">Rent</span></span>
-   <span data-ttu-id="3ee1e-110">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-110">Electricity</span></span>
-   <span data-ttu-id="3ee1e-111">Salários administrativos</span><span class="sxs-lookup"><span data-stu-id="3ee1e-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="3ee1e-112">Visão geral do cálculo de custos gerais indiretos</span><span class="sxs-lookup"><span data-stu-id="3ee1e-112">Overhead calculation overview</span></span>
<span data-ttu-id="3ee1e-113">O cálculo de custos gerais indiretos executa as políticas de contabilização de custos na ordem correta.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="3ee1e-114">Você pode executar o cálculo de custos gerais indiretos várias vezes para o mesmo período fiscal, se as políticas de contabilidade de custo foram modificadas ou foram detectados erros específicos.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="3ee1e-115">Cada execução do cálculo de custos gerais indiretos é armazenada e recebe um ID exclusivo de versão que permite comparar os cálculos em várias versões.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="3ee1e-116">As entradas de custo que o cálculo de custos indiretos gera recebe uma data contábil.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="3ee1e-117">Essa data contábil corresponde à data final do período fiscal que é usada no cálculo.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="3ee1e-118">A ID exclusiva de versão consiste nos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="3ee1e-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="3ee1e-119">Tipo de versão</span><span class="sxs-lookup"><span data-stu-id="3ee1e-119">Version type</span></span>
-   <span data-ttu-id="3ee1e-120">Data e hora</span><span class="sxs-lookup"><span data-stu-id="3ee1e-120">Date and time</span></span>
-   <span data-ttu-id="3ee1e-121">Razão de contabilização de custos</span><span class="sxs-lookup"><span data-stu-id="3ee1e-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="3ee1e-122">Ano fiscal</span><span class="sxs-lookup"><span data-stu-id="3ee1e-122">Fiscal year</span></span>
-   <span data-ttu-id="3ee1e-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="3ee1e-123">Fiscal period</span></span>

<span data-ttu-id="3ee1e-124">O cálculo de custos gerais indiretos é executado independentemente da versão.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="3ee1e-125">Portanto, você pode calcular a versão de orçamento antes da versão atual.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="3ee1e-126">O cálculo de custos gerais indiretos consiste em quatro etapas, conforme mostrado na ilustração.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="3ee1e-127">Em cada etapa, um cabeçalho de diário é criado com entradas de diário.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="3ee1e-128">Esse cabeçalho de diário mantém dados de entrada para cada etapa de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="3ee1e-129">As políticas e regras são aplicadas a cada linha do diário e as entradas de custo são geradas como saídas.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="3ee1e-130">Portanto, você sempre terá rastreabilidade total.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="3ee1e-131">[![Cálculo de custos gerais indiretos](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="3ee1e-132">Calcular e alocar os custos gerais indiretos de Eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="3ee1e-133">Na contabilidade financeira, alguns custos, como eletricidade, são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="3ee1e-134">Portanto, a visão administrativa detalhada não é fornecida para a contabilização de custo.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="3ee1e-135">Na contabilização de custo, para fornecer a visão administrativa correta em todas as unidades organizacionais e níveis, os custos devem passar pelas unidades organizacionais.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="3ee1e-136">Este fluxo deve ser baseado em qualquer um registro exato do consumo ou de uma previsão justa.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="3ee1e-137">Na contabilidade, um custo de eletricidade pode ser lançado, conforme mostrado na tabela.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3ee1e-138">Data contábil</span><span class="sxs-lookup"><span data-stu-id="3ee1e-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="3ee1e-139">Centro de custos</span><span class="sxs-lookup"><span data-stu-id="3ee1e-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="3ee1e-140">Conta principal</span><span class="sxs-lookup"><span data-stu-id="3ee1e-140">Main account</span></span></th>
<th><span data-ttu-id="3ee1e-141">Valor na moeda contábil</span><span class="sxs-lookup"><span data-stu-id="3ee1e-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-142">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="3ee1e-143">CC099</span><span class="sxs-lookup"><span data-stu-id="3ee1e-143">CC099</span></span></td>
<td><span data-ttu-id="3ee1e-144">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="3ee1e-144">Default cost center</span></span></td>
<td><span data-ttu-id="3ee1e-145">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-145">10001</span></span></td>
<td><span data-ttu-id="3ee1e-146">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-146">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="3ee1e-148">Etapa 1: Processar o cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="3ee1e-149">Por padrão, quando as entradas de custo previsto são importadas de dados de origem, elas recebem a classificação de comportamento de custo **Não classificado** na Contabilidade de custos.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="3ee1e-150">Aplicando regras da política de comportamento de custo, é possível reclassificar entradas de custo como **Custo fixo** ou **Custo variável**.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="3ee1e-151">Definir a regra de custo de comportamento</span><span class="sxs-lookup"><span data-stu-id="3ee1e-151">Define the cost behavior rule</span></span>

<span data-ttu-id="3ee1e-152">Em alguns casos, parte do custo é uma taxa fixa e o custos pendente é baseado no consumo.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="3ee1e-153">Geralmente, as contas de eletricidade correspondem a esta definição.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="3ee1e-154">Após você pagar uma taxa fixa específica, você paga por consumo, por hora de quilowatt (Kwh).</span><span class="sxs-lookup"><span data-stu-id="3ee1e-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="3ee1e-155">Por exemplo, se a taxa de custo fixa for 1.000.00, veja aqui como a regra de comportamento de custo é definida:</span><span class="sxs-lookup"><span data-stu-id="3ee1e-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="3ee1e-156">Valor fixo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="3ee1e-157">0 &lt;= 1.000,00 = Fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="3ee1e-158">1000.01 &lt; N = Variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="3ee1e-159">Diário</span><span class="sxs-lookup"><span data-stu-id="3ee1e-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3ee1e-160">Diário</span><span class="sxs-lookup"><span data-stu-id="3ee1e-160">Journal</span></span></th>
<th><span data-ttu-id="3ee1e-161">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="3ee1e-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="3ee1e-162">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="3ee1e-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="3ee1e-163">Versão</span><span class="sxs-lookup"><span data-stu-id="3ee1e-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-164">00001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-164">00001</span></span></td>
<td><span data-ttu-id="3ee1e-165">Diário de cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="3ee1e-166">fiscal</span><span class="sxs-lookup"><span data-stu-id="3ee1e-166">Fiscal</span></span></td>
<td><span data-ttu-id="3ee1e-167">2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-167">2017</span></span></td>
<td><span data-ttu-id="3ee1e-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-168">Period 1</span></span></td>
<td><span data-ttu-id="3ee1e-169">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="3ee1e-170">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3ee1e-171">Data contábil</span><span class="sxs-lookup"><span data-stu-id="3ee1e-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="3ee1e-172">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="3ee1e-173">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-173">Cost element</span></span></th>
<th><span data-ttu-id="3ee1e-174">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-174">Cost behavior</span></span></th>
<th><span data-ttu-id="3ee1e-175">Valor</span><span class="sxs-lookup"><span data-stu-id="3ee1e-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-176">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="3ee1e-177">CC099</span><span class="sxs-lookup"><span data-stu-id="3ee1e-177">CC099</span></span></td>
<td><span data-ttu-id="3ee1e-178">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="3ee1e-178">Default cost center</span></span></td>
<td><span data-ttu-id="3ee1e-179">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-179">10001</span></span></td>
<td><span data-ttu-id="3ee1e-180">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-180">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-181">Não classificado</span><span class="sxs-lookup"><span data-stu-id="3ee1e-181">Unclassified</span></span></td>
<td><span data-ttu-id="3ee1e-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="3ee1e-183">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3ee1e-184">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="3ee1e-185">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-185">Cost element</span></span></th>
<th><span data-ttu-id="3ee1e-186">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-186">Cost behavior</span></span></th>
<th><span data-ttu-id="3ee1e-187">Valor</span><span class="sxs-lookup"><span data-stu-id="3ee1e-187">Amount</span></span></th>
<th><span data-ttu-id="3ee1e-188">Data contábil</span><span class="sxs-lookup"><span data-stu-id="3ee1e-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-189">CC099</span><span class="sxs-lookup"><span data-stu-id="3ee1e-189">CC099</span></span></td>
<td><span data-ttu-id="3ee1e-190">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="3ee1e-190">Default cost center</span></span></td>
<td><span data-ttu-id="3ee1e-191">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-191">10001</span></span></td>
<td><span data-ttu-id="3ee1e-192">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-192">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-193">Não classificado</span><span class="sxs-lookup"><span data-stu-id="3ee1e-193">Unclassified</span></span></td>
<td><span data-ttu-id="3ee1e-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-194">10,000.00</span></span></td>
<td><span data-ttu-id="3ee1e-195">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-196">CC099</span><span class="sxs-lookup"><span data-stu-id="3ee1e-196">CC099</span></span></td>
<td><span data-ttu-id="3ee1e-197">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="3ee1e-197">Default cost center</span></span></td>
<td><span data-ttu-id="3ee1e-198">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-198">10001</span></span></td>
<td><span data-ttu-id="3ee1e-199">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-199">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-200">Não classificado</span><span class="sxs-lookup"><span data-stu-id="3ee1e-200">Unclassified</span></span></td>
<td><span data-ttu-id="3ee1e-201">-10.000,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-201">-10,000.00</span></span></td>
<td><span data-ttu-id="3ee1e-202">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-203">CC099</span><span class="sxs-lookup"><span data-stu-id="3ee1e-203">CC099</span></span></td>
<td><span data-ttu-id="3ee1e-204">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="3ee1e-204">Default cost center</span></span></td>
<td><span data-ttu-id="3ee1e-205">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-205">10001</span></span></td>
<td><span data-ttu-id="3ee1e-206">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-206">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-207">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-207">Fixed cost</span></span></td>
<td><span data-ttu-id="3ee1e-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-208">1,000.00</span></span></td>
<td><span data-ttu-id="3ee1e-209">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-210">CC099</span><span class="sxs-lookup"><span data-stu-id="3ee1e-210">CC099</span></span></td>
<td><span data-ttu-id="3ee1e-211">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="3ee1e-211">Default cost center</span></span></td>
<td><span data-ttu-id="3ee1e-212">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-212">10001</span></span></td>
<td><span data-ttu-id="3ee1e-213">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-213">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-214">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-214">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-215">9,000.00</span></span></td>
<td><span data-ttu-id="3ee1e-216">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3ee1e-217">Para obter mais informações, consulte [Criar e atribuir uma política de comportamento de custos a uma unidade de controle de custos](tasks/create-assign-cost-behavior-policy-cost-control-unit.md)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="3ee1e-218">Etapa 2: Processar o cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="3ee1e-219">A distribuição de custos é usada para redistribuir custo de um objeto de custo a um ou mais outros objetos de custo, aplicando uma base de alocação relevante.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="3ee1e-220">A distribuição de custos e a alocação de custo são diferentes na distribuição de custos, sempre que ocorrer em nível de elemento de custo principal do custo original.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="3ee1e-221">Definir a regra de distribuição de custos</span><span class="sxs-lookup"><span data-stu-id="3ee1e-221">Define the cost distribution rule</span></span>

<span data-ttu-id="3ee1e-222">Na contabilidade financeira, os custos de eletricidade geralmente são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="3ee1e-223">Na contabilização de custo, esta abordagem não é suficientemente detalhada.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="3ee1e-224">O custo variável deve ser distribuído a objetos de custos individuais com base justa.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="3ee1e-225">A base de alocação mais lógica é o consumo de eletricidade (Kwh).</span><span class="sxs-lookup"><span data-stu-id="3ee1e-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="3ee1e-226">O membro da dimensão estatística que é chamado Eletricidade é criado e o consumo de eletricidade é registrado.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="3ee1e-227">Por padrão, todos os membros estatísticos da dimensão se tornam disponíveis como bases de alocação.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3ee1e-228">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-228">Cost object</span></span></th>
<th><span data-ttu-id="3ee1e-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="3ee1e-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-230">CC001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-230">CC001</span></span></td>
<td><span data-ttu-id="3ee1e-231">RH</span><span class="sxs-lookup"><span data-stu-id="3ee1e-231">HR</span></span></td>
<td><span data-ttu-id="3ee1e-232">1.000</span><span class="sxs-lookup"><span data-stu-id="3ee1e-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-233">CC002</span><span class="sxs-lookup"><span data-stu-id="3ee1e-233">CC002</span></span></td>
<td><span data-ttu-id="3ee1e-234">Finanças</span><span class="sxs-lookup"><span data-stu-id="3ee1e-234">Finance</span></span></td>
<td><span data-ttu-id="3ee1e-235">6,000</span><span class="sxs-lookup"><span data-stu-id="3ee1e-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-236">CC003</span><span class="sxs-lookup"><span data-stu-id="3ee1e-236">CC003</span></span></td>
<td><span data-ttu-id="3ee1e-237">Montagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-237">Assembly</span></span></td>
<td><span data-ttu-id="3ee1e-238">0</span><span class="sxs-lookup"><span data-stu-id="3ee1e-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3ee1e-239">A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação para custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3ee1e-240">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-240">Cost object</span></span></th>
<th><span data-ttu-id="3ee1e-241">Magnitude</span><span class="sxs-lookup"><span data-stu-id="3ee1e-241">Magnitude</span></span></th>
<th><span data-ttu-id="3ee1e-242">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="3ee1e-242">Allocation factor</span></span></th>
<th><span data-ttu-id="3ee1e-243">Valor</span><span class="sxs-lookup"><span data-stu-id="3ee1e-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-244">CC001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-244">CC001</span></span></td>
<td><span data-ttu-id="3ee1e-245">RH</span><span class="sxs-lookup"><span data-stu-id="3ee1e-245">HR</span></span></td>
<td><span data-ttu-id="3ee1e-246">1.000</span><span class="sxs-lookup"><span data-stu-id="3ee1e-246">1,000</span></span></td>
<td><span data-ttu-id="3ee1e-247">(1.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="3ee1e-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="3ee1e-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-249">CC002</span><span class="sxs-lookup"><span data-stu-id="3ee1e-249">CC002</span></span></td>
<td><span data-ttu-id="3ee1e-250">Finanças</span><span class="sxs-lookup"><span data-stu-id="3ee1e-250">Finance</span></span></td>
<td><span data-ttu-id="3ee1e-251">6,000</span><span class="sxs-lookup"><span data-stu-id="3ee1e-251">6,000</span></span></td>
<td><span data-ttu-id="3ee1e-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="3ee1e-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="3ee1e-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-254">CC003</span><span class="sxs-lookup"><span data-stu-id="3ee1e-254">CC003</span></span></td>
<td><span data-ttu-id="3ee1e-255">Montagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-255">Assembly</span></span></td>
<td><span data-ttu-id="3ee1e-256">0</span><span class="sxs-lookup"><span data-stu-id="3ee1e-256">0</span></span></td>
<td><span data-ttu-id="3ee1e-257">(0 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="3ee1e-258">0,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3ee1e-259">Os custos fixos devem ser distribuídos igualmente a objetos de custo individuais que têm a eletricidade consumida.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="3ee1e-260">Você pode obter esse resultado usando o membro estatístico de dimensão de eletricidade em uma base e alocação da fórmula: (Eletricidade &gt; 0,00) A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação de custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3ee1e-261">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-261">Cost object</span></span></th>
<th><span data-ttu-id="3ee1e-262">Fórmula</span><span class="sxs-lookup"><span data-stu-id="3ee1e-262">Formula</span></span></th>
<th><span data-ttu-id="3ee1e-263">Magnitude</span><span class="sxs-lookup"><span data-stu-id="3ee1e-263">Magnitude</span></span></th>
<th><span data-ttu-id="3ee1e-264">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="3ee1e-264">Allocation factor</span></span></th>
<th><span data-ttu-id="3ee1e-265">Valor</span><span class="sxs-lookup"><span data-stu-id="3ee1e-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-266">CC001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-266">CC001</span></span></td>
<td><span data-ttu-id="3ee1e-267">RH</span><span class="sxs-lookup"><span data-stu-id="3ee1e-267">HR</span></span></td>
<td><span data-ttu-id="3ee1e-268">(1.000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="3ee1e-269">1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-269">1</span></span></td>
<td><span data-ttu-id="3ee1e-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="3ee1e-271">500,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-272">CC002</span><span class="sxs-lookup"><span data-stu-id="3ee1e-272">CC002</span></span></td>
<td><span data-ttu-id="3ee1e-273">Finanças</span><span class="sxs-lookup"><span data-stu-id="3ee1e-273">Finance</span></span></td>
<td><span data-ttu-id="3ee1e-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="3ee1e-275">1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-275">1</span></span></td>
<td><span data-ttu-id="3ee1e-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="3ee1e-277">500,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-278">CC003</span><span class="sxs-lookup"><span data-stu-id="3ee1e-278">CC003</span></span></td>
<td><span data-ttu-id="3ee1e-279">Montagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-279">Assembly</span></span></td>
<td><span data-ttu-id="3ee1e-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="3ee1e-281">0</span><span class="sxs-lookup"><span data-stu-id="3ee1e-281">0</span></span></td>
<td><span data-ttu-id="3ee1e-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="3ee1e-283">0,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="3ee1e-284">Diário</span><span class="sxs-lookup"><span data-stu-id="3ee1e-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3ee1e-285">Diário</span><span class="sxs-lookup"><span data-stu-id="3ee1e-285">Journal</span></span></th>
<th><span data-ttu-id="3ee1e-286">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="3ee1e-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="3ee1e-287">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="3ee1e-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="3ee1e-288">Versão</span><span class="sxs-lookup"><span data-stu-id="3ee1e-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-289">00002</span><span class="sxs-lookup"><span data-stu-id="3ee1e-289">00002</span></span></td>
<td><span data-ttu-id="3ee1e-290">Diário de cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="3ee1e-291">fiscal</span><span class="sxs-lookup"><span data-stu-id="3ee1e-291">Fiscal</span></span></td>
<td><span data-ttu-id="3ee1e-292">2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-292">2017</span></span></td>
<td><span data-ttu-id="3ee1e-293">Período 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-293">Period 1</span></span></td>
<td><span data-ttu-id="3ee1e-294">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="3ee1e-295">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3ee1e-296">Data contábil</span><span class="sxs-lookup"><span data-stu-id="3ee1e-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="3ee1e-297">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="3ee1e-298">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-298">Cost element</span></span></th>
<th><span data-ttu-id="3ee1e-299">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-299">Cost behavior</span></span></th>
<th><span data-ttu-id="3ee1e-300">Valor</span><span class="sxs-lookup"><span data-stu-id="3ee1e-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-301">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="3ee1e-302">CC099</span><span class="sxs-lookup"><span data-stu-id="3ee1e-302">CC099</span></span></td>
<td><span data-ttu-id="3ee1e-303">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="3ee1e-303">Default cost center</span></span></td>
<td><span data-ttu-id="3ee1e-304">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-304">10001</span></span></td>
<td><span data-ttu-id="3ee1e-305">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-305">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-306">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-306">Fixed cost</span></span></td>
<td><span data-ttu-id="3ee1e-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-308">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="3ee1e-309">CC099</span><span class="sxs-lookup"><span data-stu-id="3ee1e-309">CC099</span></span></td>
<td><span data-ttu-id="3ee1e-310">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="3ee1e-310">Default cost center</span></span></td>
<td><span data-ttu-id="3ee1e-311">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-311">10001</span></span></td>
<td><span data-ttu-id="3ee1e-312">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-312">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-313">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-313">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="3ee1e-315">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3ee1e-316">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="3ee1e-317">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-317">Cost element</span></span></th>
<th><span data-ttu-id="3ee1e-318">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-318">Cost behavior</span></span></th>
<th><span data-ttu-id="3ee1e-319">Valor</span><span class="sxs-lookup"><span data-stu-id="3ee1e-319">Amount</span></span></th>
<th><span data-ttu-id="3ee1e-320">Data contábil</span><span class="sxs-lookup"><span data-stu-id="3ee1e-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-321">CC099</span><span class="sxs-lookup"><span data-stu-id="3ee1e-321">CC099</span></span></td>
<td><span data-ttu-id="3ee1e-322">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="3ee1e-322">Default cost center</span></span></td>
<td><span data-ttu-id="3ee1e-323">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-323">10001</span></span></td>
<td><span data-ttu-id="3ee1e-324">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-324">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-325">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-325">Fixed cost</span></span></td>
<td><span data-ttu-id="3ee1e-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-326">-1,000.00</span></span></td>
<td><span data-ttu-id="3ee1e-327">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-328">CC001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-328">CC001</span></span></td>
<td><span data-ttu-id="3ee1e-329">RH</span><span class="sxs-lookup"><span data-stu-id="3ee1e-329">HR</span></span></td>
<td><span data-ttu-id="3ee1e-330">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-330">10001</span></span></td>
<td><span data-ttu-id="3ee1e-331">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-331">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-332">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-332">Fixed cost</span></span></td>
<td><span data-ttu-id="3ee1e-333">500,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-333">500.00</span></span></td>
<td><span data-ttu-id="3ee1e-334">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-335">CC002</span><span class="sxs-lookup"><span data-stu-id="3ee1e-335">CC002</span></span></td>
<td><span data-ttu-id="3ee1e-336">Finanças</span><span class="sxs-lookup"><span data-stu-id="3ee1e-336">Finance</span></span></td>
<td><span data-ttu-id="3ee1e-337">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-337">10001</span></span></td>
<td><span data-ttu-id="3ee1e-338">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-338">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-339">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-339">Fixed cost</span></span></td>
<td><span data-ttu-id="3ee1e-340">500,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-340">500.00</span></span></td>
<td><span data-ttu-id="3ee1e-341">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-342">CC099</span><span class="sxs-lookup"><span data-stu-id="3ee1e-342">CC099</span></span></td>
<td><span data-ttu-id="3ee1e-343">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="3ee1e-343">Default cost center</span></span></td>
<td><span data-ttu-id="3ee1e-344">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-344">10001</span></span></td>
<td><span data-ttu-id="3ee1e-345">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-345">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-346">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-346">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-347">-9,000.00</span></span></td>
<td><span data-ttu-id="3ee1e-348">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-349">CC001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-349">CC001</span></span></td>
<td><span data-ttu-id="3ee1e-350">RH</span><span class="sxs-lookup"><span data-stu-id="3ee1e-350">HR</span></span></td>
<td><span data-ttu-id="3ee1e-351">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-351">10001</span></span></td>
<td><span data-ttu-id="3ee1e-352">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-352">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-353">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-353">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="3ee1e-354">1,285.71</span></span></td>
<td><span data-ttu-id="3ee1e-355">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-356">CC002</span><span class="sxs-lookup"><span data-stu-id="3ee1e-356">CC002</span></span></td>
<td><span data-ttu-id="3ee1e-357">Finanças</span><span class="sxs-lookup"><span data-stu-id="3ee1e-357">Finance</span></span></td>
<td><span data-ttu-id="3ee1e-358">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-358">10001</span></span></td>
<td><span data-ttu-id="3ee1e-359">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-359">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-360">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-360">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="3ee1e-361">7,714.29</span></span></td>
<td><span data-ttu-id="3ee1e-362">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3ee1e-363">Para obter mais informações, consulte [Criar e atribuir uma política de distribuição de custos a uma unidade de controle de custos](tasks/create-assign-cost-distribution-policy-cost-control-unit.md)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="3ee1e-364">Etapa 3: Processar o cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="3ee1e-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="3ee1e-365">A taxa de custos indiretos é usada para cobrar um ou mais objetos de custos específicos.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="3ee1e-366">O encargo se baseia em uma taxa de custo predeterminada e a magnitude da básica de alocação atribuída.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="3ee1e-367">Defina a taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="3ee1e-367">Define the overhead rate</span></span>

<span data-ttu-id="3ee1e-368">O objeto de custo CC001 HR contribui para um conjunto de projetos internos.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="3ee1e-369">Um membro de dimensão estatística que é chamado de projetos de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3ee1e-370">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-370">Cost object</span></span></th>
<th><span data-ttu-id="3ee1e-371">Horas</span><span class="sxs-lookup"><span data-stu-id="3ee1e-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-372">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-372">Proj 1</span></span></td>
<td><span data-ttu-id="3ee1e-373">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-373">Project 1</span></span></td>
<td><span data-ttu-id="3ee1e-374">3</span><span class="sxs-lookup"><span data-stu-id="3ee1e-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-375">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-375">Proj 2</span></span></td>
<td><span data-ttu-id="3ee1e-376">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-376">Project 2</span></span></td>
<td><span data-ttu-id="3ee1e-377">1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3ee1e-378">Uma taxa de custo predeterminada da contribuição de projetos de custo foi definida.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3ee1e-379">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-379">Cost object</span></span></th>
<th><span data-ttu-id="3ee1e-380">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-380">Cost element</span></span></th>
<th><span data-ttu-id="3ee1e-381">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-381">Cost behavior</span></span></th>
<th><span data-ttu-id="3ee1e-382">Unidades</span><span class="sxs-lookup"><span data-stu-id="3ee1e-382">Units</span></span></th>
<th><span data-ttu-id="3ee1e-383">Taxa</span><span class="sxs-lookup"><span data-stu-id="3ee1e-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-384">CC001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-384">CC001</span></span></td>
<td><span data-ttu-id="3ee1e-385">RH</span><span class="sxs-lookup"><span data-stu-id="3ee1e-385">HR</span></span></td>
<td><span data-ttu-id="3ee1e-386">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-386">10001</span></span></td>
<td><span data-ttu-id="3ee1e-387">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-387">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-388">1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-388">1</span></span></td>
<td><span data-ttu-id="3ee1e-389">10</span><span class="sxs-lookup"><span data-stu-id="3ee1e-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3ee1e-390">A tabela a seguir mostra o resultado quando projetos de RH são aplicados como base de alocação.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3ee1e-391">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-391">Cost object</span></span></th>
<th><span data-ttu-id="3ee1e-392">Magnitude</span><span class="sxs-lookup"><span data-stu-id="3ee1e-392">Magnitude</span></span></th>
<th><span data-ttu-id="3ee1e-393">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-393">Cost element</span></span></th>
<th><span data-ttu-id="3ee1e-394">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="3ee1e-394">Allocation factor</span></span></th>
<th><span data-ttu-id="3ee1e-395">Valor</span><span class="sxs-lookup"><span data-stu-id="3ee1e-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-396">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-396">Proj 1</span></span></td>
<td><span data-ttu-id="3ee1e-397">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-397">Project 1</span></span></td>
<td><span data-ttu-id="3ee1e-398">3</span><span class="sxs-lookup"><span data-stu-id="3ee1e-398">3</span></span></td>
<td><span data-ttu-id="3ee1e-399">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-399">10001</span></span></td>
<td><span data-ttu-id="3ee1e-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="3ee1e-401">30,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-402">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-402">Proj 2</span></span></td>
<td><span data-ttu-id="3ee1e-403">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-403">Project 2</span></span></td>
<td><span data-ttu-id="3ee1e-404">1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-404">1</span></span></td>
<td><span data-ttu-id="3ee1e-405">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-405">10001</span></span></td>
<td><span data-ttu-id="3ee1e-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="3ee1e-407">10,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="3ee1e-408">Diário</span><span class="sxs-lookup"><span data-stu-id="3ee1e-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3ee1e-409">Diário</span><span class="sxs-lookup"><span data-stu-id="3ee1e-409">Journal</span></span></th>
<th><span data-ttu-id="3ee1e-410">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="3ee1e-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="3ee1e-411">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="3ee1e-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="3ee1e-412">Versão</span><span class="sxs-lookup"><span data-stu-id="3ee1e-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-413">00003</span><span class="sxs-lookup"><span data-stu-id="3ee1e-413">00003</span></span></td>
<td><span data-ttu-id="3ee1e-414">Diário de cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="3ee1e-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="3ee1e-415">fiscal</span><span class="sxs-lookup"><span data-stu-id="3ee1e-415">Fiscal</span></span></td>
<td><span data-ttu-id="3ee1e-416">2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-416">2017</span></span></td>
<td><span data-ttu-id="3ee1e-417">Período 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-417">Period 1</span></span></td>
<td><span data-ttu-id="3ee1e-418">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="3ee1e-419">Entradas de diário (As entradas de diário para cálculo da taxa de custos indiretos)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3ee1e-420">Data contábil</span><span class="sxs-lookup"><span data-stu-id="3ee1e-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="3ee1e-421">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-421">Cost object</span></span></th>
<th><span data-ttu-id="3ee1e-422">Magnitude</span><span class="sxs-lookup"><span data-stu-id="3ee1e-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-423">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="3ee1e-424">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-424">Proj 1</span></span></td>
<td><span data-ttu-id="3ee1e-425">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="3ee1e-426">3,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-427">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="3ee1e-428">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-428">Proj 2</span></span></td>
<td><span data-ttu-id="3ee1e-429">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="3ee1e-430">1.00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="3ee1e-431">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3ee1e-432">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="3ee1e-433">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-433">Cost element</span></span></th>
<th><span data-ttu-id="3ee1e-434">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-434">Cost behavior</span></span></th>
<th><span data-ttu-id="3ee1e-435">Valor</span><span class="sxs-lookup"><span data-stu-id="3ee1e-435">Amount</span></span></th>
<th><span data-ttu-id="3ee1e-436">Data contábil</span><span class="sxs-lookup"><span data-stu-id="3ee1e-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-437">CC0001</span></span></td>
<td><span data-ttu-id="3ee1e-438">RH</span><span class="sxs-lookup"><span data-stu-id="3ee1e-438">HR</span></span></td>
<td><span data-ttu-id="3ee1e-439">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-439">10001</span></span></td>
<td><span data-ttu-id="3ee1e-440">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-440">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-441">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-441">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-442">-30.00</span></span></td>
<td><span data-ttu-id="3ee1e-443">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-444">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-444">Proj 1</span></span></td>
<td><span data-ttu-id="3ee1e-445">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="3ee1e-446">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-446">10001</span></span></td>
<td><span data-ttu-id="3ee1e-447">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-447">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-448">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-448">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-449">30,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-449">30.00</span></span></td>
<td><span data-ttu-id="3ee1e-450">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-451">CC001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-451">CC001</span></span></td>
<td><span data-ttu-id="3ee1e-452">RH</span><span class="sxs-lookup"><span data-stu-id="3ee1e-452">HR</span></span></td>
<td><span data-ttu-id="3ee1e-453">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-453">10001</span></span></td>
<td><span data-ttu-id="3ee1e-454">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-454">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-455">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-455">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-456">-10.00</span></span></td>
<td><span data-ttu-id="3ee1e-457">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-458">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-458">Proj 2</span></span></td>
<td><span data-ttu-id="3ee1e-459">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="3ee1e-460">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-460">10001</span></span></td>
<td><span data-ttu-id="3ee1e-461">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-461">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-462">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-462">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-463">10,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-463">10.00</span></span></td>
<td><span data-ttu-id="3ee1e-464">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3ee1e-465">Para obter mais informações, consulte [Realizar cálculo de custos indiretos](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="3ee1e-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="3ee1e-466">Etapa 4: Processar o cálculo de alocação de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="3ee1e-467">A alocação é usada para alocar o saldo de um objeto de custo a outros objetos de custo pela aplicação de uma base de alocação.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="3ee1e-468">O Finance oferece suporte ao método de alocação recíproco.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="3ee1e-469">No método de alocação recíproco, os serviços mútuos que os objetos de custo auxiliar trocam são totalmente reconhecidos.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="3ee1e-470">O sistema determina automaticamente a ordem correta realizar as alocações.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="3ee1e-471">O saldo de um objeto de custo é alocado por uma base de alocação única.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="3ee1e-472">As alocações entre as dimensões de objetos de custo e os respectivos membros são suportadas.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="3ee1e-473">A ordem de alocação é controlada pela unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="3ee1e-474">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="3ee1e-475">Defina a alocação de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-475">Define the cost allocation</span></span>

<span data-ttu-id="3ee1e-476">Aqui está um exemplo simples que explica como você pode rastrear o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="3ee1e-477">O objeto de custo previsto CC001 HR contribui a vários objetos de custo previsto.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="3ee1e-478">Um membro de dimensão estatística que é chamado de serviços de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3ee1e-479">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-479">Cost object</span></span></th>
<th><span data-ttu-id="3ee1e-480">Serviços de RH</span><span class="sxs-lookup"><span data-stu-id="3ee1e-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-481">CC002</span><span class="sxs-lookup"><span data-stu-id="3ee1e-481">CC002</span></span></td>
<td><span data-ttu-id="3ee1e-482">Finanças</span><span class="sxs-lookup"><span data-stu-id="3ee1e-482">Finance</span></span></td>
<td><span data-ttu-id="3ee1e-483">35</span><span class="sxs-lookup"><span data-stu-id="3ee1e-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-484">CC003</span><span class="sxs-lookup"><span data-stu-id="3ee1e-484">CC003</span></span></td>
<td><span data-ttu-id="3ee1e-485">Montagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-485">Assembly</span></span></td>
<td><span data-ttu-id="3ee1e-486">55</span><span class="sxs-lookup"><span data-stu-id="3ee1e-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-487">CC004</span><span class="sxs-lookup"><span data-stu-id="3ee1e-487">CC004</span></span></td>
<td><span data-ttu-id="3ee1e-488">Embalagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-488">Packaging</span></span></td>
<td><span data-ttu-id="3ee1e-489">10</span><span class="sxs-lookup"><span data-stu-id="3ee1e-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3ee1e-490">O objeto de custo CC002 Finanças contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="3ee1e-491">Um membro de dimensão estatística que é chamado de serviços de Finanças foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3ee1e-492">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-492">Cost object</span></span></th>
<th><span data-ttu-id="3ee1e-493">Serviços financeiros</span><span class="sxs-lookup"><span data-stu-id="3ee1e-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-494">CC003</span><span class="sxs-lookup"><span data-stu-id="3ee1e-494">CC003</span></span></td>
<td><span data-ttu-id="3ee1e-495">Montagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-495">Assembly</span></span></td>
<td><span data-ttu-id="3ee1e-496">65</span><span class="sxs-lookup"><span data-stu-id="3ee1e-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-497">CC004</span><span class="sxs-lookup"><span data-stu-id="3ee1e-497">CC004</span></span></td>
<td><span data-ttu-id="3ee1e-498">Embalagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-498">Packaging</span></span></td>
<td><span data-ttu-id="3ee1e-499">35</span><span class="sxs-lookup"><span data-stu-id="3ee1e-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3ee1e-500">O objeto de custo CC003 Montagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="3ee1e-501">Um membro de dimensão estatística que é chamado de serviços de Montagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3ee1e-502">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-502">Cost object</span></span></th>
<th><span data-ttu-id="3ee1e-503">Serviços de montagem (horas)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-504">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-504">Prod 1</span></span></td>
<td><span data-ttu-id="3ee1e-505">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-505">Product 1</span></span></td>
<td><span data-ttu-id="3ee1e-506">60</span><span class="sxs-lookup"><span data-stu-id="3ee1e-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-507">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-507">Prod 2</span></span></td>
<td><span data-ttu-id="3ee1e-508">Produto 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-508">Product 2</span></span></td>
<td><span data-ttu-id="3ee1e-509">20</span><span class="sxs-lookup"><span data-stu-id="3ee1e-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3ee1e-510">O objeto de custo CC004 Embalagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="3ee1e-511">Um membro de dimensão estatística que é chamado de serviços de Embalagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3ee1e-512">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-512">Cost object</span></span></th>
<th><span data-ttu-id="3ee1e-513">Serviços de embalagem (horas)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-514">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-514">Prod 1</span></span></td>
<td><span data-ttu-id="3ee1e-515">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-515">Product 1</span></span></td>
<td><span data-ttu-id="3ee1e-516">80</span><span class="sxs-lookup"><span data-stu-id="3ee1e-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-517">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-517">Prod 2</span></span></td>
<td><span data-ttu-id="3ee1e-518">Produto 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-518">Product 2</span></span></td>
<td><span data-ttu-id="3ee1e-519">15</span><span class="sxs-lookup"><span data-stu-id="3ee1e-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="3ee1e-520">Medidas estatísticas, como as horas de produção que um produto consome, podem ser derivadas dos dados de origem.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="3ee1e-521">Para obter mais informações, consulte [Modelo de provedor de medidas estatísticas](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="3ee1e-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="3ee1e-522">A tabela a seguir mostra o resultado quando os serviços de RH são aplicados como base de alocação para custos totais (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3ee1e-523">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-523">Cost object</span></span></th>
<th><span data-ttu-id="3ee1e-524">Magnitude</span><span class="sxs-lookup"><span data-stu-id="3ee1e-524">Magnitude</span></span></th>
<th><span data-ttu-id="3ee1e-525">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="3ee1e-525">Allocation factor</span></span></th>
<th><span data-ttu-id="3ee1e-526">Valor</span><span class="sxs-lookup"><span data-stu-id="3ee1e-526">Amount</span></span></th>
<th><span data-ttu-id="3ee1e-527">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-528">CC002</span><span class="sxs-lookup"><span data-stu-id="3ee1e-528">CC002</span></span></td>
<td><span data-ttu-id="3ee1e-529">Finanças</span><span class="sxs-lookup"><span data-stu-id="3ee1e-529">Finance</span></span></td>
<td><span data-ttu-id="3ee1e-530">35</span><span class="sxs-lookup"><span data-stu-id="3ee1e-530">35</span></span></td>
<td><span data-ttu-id="3ee1e-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="3ee1e-532">175.00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-532">175.00</span></span></td>
<td><span data-ttu-id="3ee1e-533">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-534">CC003</span><span class="sxs-lookup"><span data-stu-id="3ee1e-534">CC003</span></span></td>
<td><span data-ttu-id="3ee1e-535">Montagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-535">Assembly</span></span></td>
<td><span data-ttu-id="3ee1e-536">55</span><span class="sxs-lookup"><span data-stu-id="3ee1e-536">55</span></span></td>
<td><span data-ttu-id="3ee1e-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="3ee1e-538">275.00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-538">275.00</span></span></td>
<td><span data-ttu-id="3ee1e-539">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-540">CC004</span><span class="sxs-lookup"><span data-stu-id="3ee1e-540">CC004</span></span></td>
<td><span data-ttu-id="3ee1e-541">Embalagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-541">Packaging</span></span></td>
<td><span data-ttu-id="3ee1e-542">10</span><span class="sxs-lookup"><span data-stu-id="3ee1e-542">10</span></span></td>
<td><span data-ttu-id="3ee1e-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="3ee1e-544">50,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-544">50.00</span></span></td>
<td><span data-ttu-id="3ee1e-545">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-546">CC002</span><span class="sxs-lookup"><span data-stu-id="3ee1e-546">CC002</span></span></td>
<td><span data-ttu-id="3ee1e-547">Finanças</span><span class="sxs-lookup"><span data-stu-id="3ee1e-547">Finance</span></span></td>
<td><span data-ttu-id="3ee1e-548">35</span><span class="sxs-lookup"><span data-stu-id="3ee1e-548">35</span></span></td>
<td><span data-ttu-id="3ee1e-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="3ee1e-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="3ee1e-550">436.00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-550">436.00</span></span></td>
<td><span data-ttu-id="3ee1e-551">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-552">CC003</span><span class="sxs-lookup"><span data-stu-id="3ee1e-552">CC003</span></span></td>
<td><span data-ttu-id="3ee1e-553">Montagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-553">Assembly</span></span></td>
<td><span data-ttu-id="3ee1e-554">55</span><span class="sxs-lookup"><span data-stu-id="3ee1e-554">55</span></span></td>
<td><span data-ttu-id="3ee1e-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="3ee1e-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="3ee1e-556">685.14</span><span class="sxs-lookup"><span data-stu-id="3ee1e-556">685.14</span></span></td>
<td><span data-ttu-id="3ee1e-557">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-558">CC004</span><span class="sxs-lookup"><span data-stu-id="3ee1e-558">CC004</span></span></td>
<td><span data-ttu-id="3ee1e-559">Embalagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-559">Packaging</span></span></td>
<td><span data-ttu-id="3ee1e-560">10</span><span class="sxs-lookup"><span data-stu-id="3ee1e-560">10</span></span></td>
<td><span data-ttu-id="3ee1e-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="3ee1e-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="3ee1e-562">124.57</span><span class="sxs-lookup"><span data-stu-id="3ee1e-562">124.57</span></span></td>
<td><span data-ttu-id="3ee1e-563">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3ee1e-564">A tabela a seguir mostra o resultado quando os serviços financeiros são aplicados como base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3ee1e-565">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-565">Cost object</span></span></th>
<th><span data-ttu-id="3ee1e-566">Magnitude</span><span class="sxs-lookup"><span data-stu-id="3ee1e-566">Magnitude</span></span></th>
<th><span data-ttu-id="3ee1e-567">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="3ee1e-567">Allocation factor</span></span></th>
<th><span data-ttu-id="3ee1e-568">Valor</span><span class="sxs-lookup"><span data-stu-id="3ee1e-568">Amount</span></span></th>
<th><span data-ttu-id="3ee1e-569">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-570">CC003</span><span class="sxs-lookup"><span data-stu-id="3ee1e-570">CC003</span></span></td>
<td><span data-ttu-id="3ee1e-571">Montagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-571">Assembly</span></span></td>
<td><span data-ttu-id="3ee1e-572">65</span><span class="sxs-lookup"><span data-stu-id="3ee1e-572">65</span></span></td>
<td><span data-ttu-id="3ee1e-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="3ee1e-574">438.75</span><span class="sxs-lookup"><span data-stu-id="3ee1e-574">438.75</span></span></td>
<td><span data-ttu-id="3ee1e-575">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-576">CC004</span><span class="sxs-lookup"><span data-stu-id="3ee1e-576">CC004</span></span></td>
<td><span data-ttu-id="3ee1e-577">Embalagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-577">Packaging</span></span></td>
<td><span data-ttu-id="3ee1e-578">35</span><span class="sxs-lookup"><span data-stu-id="3ee1e-578">35</span></span></td>
<td><span data-ttu-id="3ee1e-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="3ee1e-580">236.25</span><span class="sxs-lookup"><span data-stu-id="3ee1e-580">236.25</span></span></td>
<td><span data-ttu-id="3ee1e-581">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-582">CC003</span><span class="sxs-lookup"><span data-stu-id="3ee1e-582">CC003</span></span></td>
<td><span data-ttu-id="3ee1e-583">Montagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-583">Assembly</span></span></td>
<td><span data-ttu-id="3ee1e-584">65</span><span class="sxs-lookup"><span data-stu-id="3ee1e-584">65</span></span></td>
<td><span data-ttu-id="3ee1e-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="3ee1e-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="3ee1e-586">5,297.69</span></span></td>
<td><span data-ttu-id="3ee1e-587">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-588">CC004</span><span class="sxs-lookup"><span data-stu-id="3ee1e-588">CC004</span></span></td>
<td><span data-ttu-id="3ee1e-589">Embalagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-589">Packaging</span></span></td>
<td><span data-ttu-id="3ee1e-590">35</span><span class="sxs-lookup"><span data-stu-id="3ee1e-590">35</span></span></td>
<td><span data-ttu-id="3ee1e-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="3ee1e-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="3ee1e-592">2,852.60</span></span></td>
<td><span data-ttu-id="3ee1e-593">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3ee1e-594">A tabela a seguir mostra o resultado quando os serviços de Montagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3ee1e-595">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-595">Cost object</span></span></th>
<th><span data-ttu-id="3ee1e-596">Magnitude</span><span class="sxs-lookup"><span data-stu-id="3ee1e-596">Magnitude</span></span></th>
<th><span data-ttu-id="3ee1e-597">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="3ee1e-597">Allocation factor</span></span></th>
<th><span data-ttu-id="3ee1e-598">Valor</span><span class="sxs-lookup"><span data-stu-id="3ee1e-598">Amount</span></span></th>
<th><span data-ttu-id="3ee1e-599">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-600">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-600">Prod 1</span></span></td>
<td><span data-ttu-id="3ee1e-601">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-601">Product 1</span></span></td>
<td><span data-ttu-id="3ee1e-602">60</span><span class="sxs-lookup"><span data-stu-id="3ee1e-602">60</span></span></td>
<td><span data-ttu-id="3ee1e-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="3ee1e-604">535.31</span><span class="sxs-lookup"><span data-stu-id="3ee1e-604">535.31</span></span></td>
<td><span data-ttu-id="3ee1e-605">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-606">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-606">Prod 2</span></span></td>
<td><span data-ttu-id="3ee1e-607">Produto 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-607">Product 2</span></span></td>
<td><span data-ttu-id="3ee1e-608">20</span><span class="sxs-lookup"><span data-stu-id="3ee1e-608">20</span></span></td>
<td><span data-ttu-id="3ee1e-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="3ee1e-610">178.44</span><span class="sxs-lookup"><span data-stu-id="3ee1e-610">178.44</span></span></td>
<td><span data-ttu-id="3ee1e-611">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-612">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-612">Prod 1</span></span></td>
<td><span data-ttu-id="3ee1e-613">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-613">Product 1</span></span></td>
<td><span data-ttu-id="3ee1e-614">60</span><span class="sxs-lookup"><span data-stu-id="3ee1e-614">60</span></span></td>
<td><span data-ttu-id="3ee1e-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="3ee1e-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="3ee1e-616">4,487.12</span></span></td>
<td><span data-ttu-id="3ee1e-617">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-618">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-618">Prod 2</span></span></td>
<td><span data-ttu-id="3ee1e-619">Produto 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-619">Product 2</span></span></td>
<td><span data-ttu-id="3ee1e-620">20</span><span class="sxs-lookup"><span data-stu-id="3ee1e-620">20</span></span></td>
<td><span data-ttu-id="3ee1e-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="3ee1e-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="3ee1e-622">1,495.71</span></span></td>
<td><span data-ttu-id="3ee1e-623">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3ee1e-624">A tabela a seguir mostra o resultado quando os serviços de Embalagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3ee1e-625">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-625">Cost object</span></span></th>
<th><span data-ttu-id="3ee1e-626">Magnitude</span><span class="sxs-lookup"><span data-stu-id="3ee1e-626">Magnitude</span></span></th>
<th><span data-ttu-id="3ee1e-627">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="3ee1e-627">Allocation factor</span></span></th>
<th><span data-ttu-id="3ee1e-628">Valor</span><span class="sxs-lookup"><span data-stu-id="3ee1e-628">Amount</span></span></th>
<th><span data-ttu-id="3ee1e-629">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-630">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-630">Prod 1</span></span></td>
<td><span data-ttu-id="3ee1e-631">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-631">Product 1</span></span></td>
<td><span data-ttu-id="3ee1e-632">80</span><span class="sxs-lookup"><span data-stu-id="3ee1e-632">80</span></span></td>
<td><span data-ttu-id="3ee1e-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="3ee1e-634">241.05</span><span class="sxs-lookup"><span data-stu-id="3ee1e-634">241.05</span></span></td>
<td><span data-ttu-id="3ee1e-635">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-636">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-636">Prod 2</span></span></td>
<td><span data-ttu-id="3ee1e-637">Produto 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-637">Product 2</span></span></td>
<td><span data-ttu-id="3ee1e-638">15</span><span class="sxs-lookup"><span data-stu-id="3ee1e-638">15</span></span></td>
<td><span data-ttu-id="3ee1e-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="3ee1e-640">45.20</span><span class="sxs-lookup"><span data-stu-id="3ee1e-640">45.20</span></span></td>
<td><span data-ttu-id="3ee1e-641">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-642">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-642">Prod 1</span></span></td>
<td><span data-ttu-id="3ee1e-643">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-643">Product 1</span></span></td>
<td><span data-ttu-id="3ee1e-644">80</span><span class="sxs-lookup"><span data-stu-id="3ee1e-644">80</span></span></td>
<td><span data-ttu-id="3ee1e-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="3ee1e-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="3ee1e-646">2,507.09</span></span></td>
<td><span data-ttu-id="3ee1e-647">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-648">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-648">Prod 2</span></span></td>
<td><span data-ttu-id="3ee1e-649">Produto 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-649">Product 2</span></span></td>
<td><span data-ttu-id="3ee1e-650">15</span><span class="sxs-lookup"><span data-stu-id="3ee1e-650">15</span></span></td>
<td><span data-ttu-id="3ee1e-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="3ee1e-652">470.08</span><span class="sxs-lookup"><span data-stu-id="3ee1e-652">470.08</span></span></td>
<td><span data-ttu-id="3ee1e-653">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="3ee1e-654">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="3ee1e-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3ee1e-655">Diário</span><span class="sxs-lookup"><span data-stu-id="3ee1e-655">Journal</span></span></th>
<th><span data-ttu-id="3ee1e-656">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="3ee1e-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="3ee1e-657">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="3ee1e-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="3ee1e-658">Versão</span><span class="sxs-lookup"><span data-stu-id="3ee1e-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-659">00004</span><span class="sxs-lookup"><span data-stu-id="3ee1e-659">00004</span></span></td>
<td><span data-ttu-id="3ee1e-660">Diário de alocação de custos</span><span class="sxs-lookup"><span data-stu-id="3ee1e-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="3ee1e-661">fiscal</span><span class="sxs-lookup"><span data-stu-id="3ee1e-661">Fiscal</span></span></td>
<td><span data-ttu-id="3ee1e-662">2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-662">2017</span></span></td>
<td><span data-ttu-id="3ee1e-663">Período 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-663">Period 1</span></span></td>
<td><span data-ttu-id="3ee1e-664">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="3ee1e-665">Linhas do diário</span><span class="sxs-lookup"><span data-stu-id="3ee1e-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3ee1e-666">Data contábil</span><span class="sxs-lookup"><span data-stu-id="3ee1e-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="3ee1e-667">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="3ee1e-668">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-668">Cost element</span></span></th>
<th><span data-ttu-id="3ee1e-669">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-669">Cost behavior</span></span></th>
<th><span data-ttu-id="3ee1e-670">Valor</span><span class="sxs-lookup"><span data-stu-id="3ee1e-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-671">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="3ee1e-672">CC001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-672">CC001</span></span></td>
<td><span data-ttu-id="3ee1e-673">RH</span><span class="sxs-lookup"><span data-stu-id="3ee1e-673">HR</span></span></td>
<td><span data-ttu-id="3ee1e-674">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-674">10001</span></span></td>
<td><span data-ttu-id="3ee1e-675">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-675">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-676">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-676">Fixed cost</span></span></td>
<td><span data-ttu-id="3ee1e-677">500,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-678">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="3ee1e-679">CC001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-679">CC001</span></span></td>
<td><span data-ttu-id="3ee1e-680">RH</span><span class="sxs-lookup"><span data-stu-id="3ee1e-680">HR</span></span></td>
<td><span data-ttu-id="3ee1e-681">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-681">10001</span></span></td>
<td><span data-ttu-id="3ee1e-682">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-682">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-683">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-683">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="3ee1e-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-685">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="3ee1e-686">CC002</span><span class="sxs-lookup"><span data-stu-id="3ee1e-686">CC002</span></span></td>
<td><span data-ttu-id="3ee1e-687">Finanças</span><span class="sxs-lookup"><span data-stu-id="3ee1e-687">Finance</span></span></td>
<td><span data-ttu-id="3ee1e-688">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-688">10001</span></span></td>
<td><span data-ttu-id="3ee1e-689">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-689">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-690">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-690">Fixed cost</span></span></td>
<td><span data-ttu-id="3ee1e-691">675.00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-692">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="3ee1e-693">CC002</span><span class="sxs-lookup"><span data-stu-id="3ee1e-693">CC002</span></span></td>
<td><span data-ttu-id="3ee1e-694">Finanças</span><span class="sxs-lookup"><span data-stu-id="3ee1e-694">Finance</span></span></td>
<td><span data-ttu-id="3ee1e-695">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-695">10001</span></span></td>
<td><span data-ttu-id="3ee1e-696">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-696">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-697">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-697">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="3ee1e-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-699">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="3ee1e-700">CC003</span><span class="sxs-lookup"><span data-stu-id="3ee1e-700">CC003</span></span></td>
<td><span data-ttu-id="3ee1e-701">Montagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-701">Assembly</span></span></td>
<td><span data-ttu-id="3ee1e-702">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-702">10001</span></span></td>
<td><span data-ttu-id="3ee1e-703">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-703">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-704">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-704">Fixed cost</span></span></td>
<td><span data-ttu-id="3ee1e-705">713.75</span><span class="sxs-lookup"><span data-stu-id="3ee1e-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-706">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="3ee1e-707">CC003</span><span class="sxs-lookup"><span data-stu-id="3ee1e-707">CC003</span></span></td>
<td><span data-ttu-id="3ee1e-708">Montagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-708">Assembly</span></span></td>
<td><span data-ttu-id="3ee1e-709">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-709">10001</span></span></td>
<td><span data-ttu-id="3ee1e-710">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-710">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-711">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-711">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="3ee1e-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-713">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="3ee1e-714">CC003</span><span class="sxs-lookup"><span data-stu-id="3ee1e-714">CC003</span></span></td>
<td><span data-ttu-id="3ee1e-715">Embalagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-715">Packaging</span></span></td>
<td><span data-ttu-id="3ee1e-716">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-716">10001</span></span></td>
<td><span data-ttu-id="3ee1e-717">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-717">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-718">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-718">Fixed cost</span></span></td>
<td><span data-ttu-id="3ee1e-719">286.25</span><span class="sxs-lookup"><span data-stu-id="3ee1e-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-720">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="3ee1e-721">CC003</span><span class="sxs-lookup"><span data-stu-id="3ee1e-721">CC003</span></span></td>
<td><span data-ttu-id="3ee1e-722">Embalagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-722">Packaging</span></span></td>
<td><span data-ttu-id="3ee1e-723">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-723">10001</span></span></td>
<td><span data-ttu-id="3ee1e-724">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-724">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-725">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-725">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="3ee1e-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-727">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="3ee1e-728">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-728">Prod 1</span></span></td>
<td><span data-ttu-id="3ee1e-729">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-729">Product 1</span></span></td>
<td><span data-ttu-id="3ee1e-730">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-730">10001</span></span></td>
<td><span data-ttu-id="3ee1e-731">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-731">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-732">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-732">Fixed cost</span></span></td>
<td><span data-ttu-id="3ee1e-733">776.36</span><span class="sxs-lookup"><span data-stu-id="3ee1e-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-734">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="3ee1e-735">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-735">Prod 1</span></span></td>
<td><span data-ttu-id="3ee1e-736">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-736">Product 1</span></span></td>
<td><span data-ttu-id="3ee1e-737">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-737">10001</span></span></td>
<td><span data-ttu-id="3ee1e-738">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-738">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-739">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-739">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="3ee1e-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-741">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="3ee1e-742">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-742">Prod 2</span></span></td>
<td><span data-ttu-id="3ee1e-743">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-743">Product 1</span></span></td>
<td><span data-ttu-id="3ee1e-744">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-744">10001</span></span></td>
<td><span data-ttu-id="3ee1e-745">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-745">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-746">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-746">Fixed cost</span></span></td>
<td><span data-ttu-id="3ee1e-747">223.64</span><span class="sxs-lookup"><span data-stu-id="3ee1e-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-748">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="3ee1e-749">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-749">Prod 2</span></span></td>
<td><span data-ttu-id="3ee1e-750">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-750">Product 1</span></span></td>
<td><span data-ttu-id="3ee1e-751">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-751">10001</span></span></td>
<td><span data-ttu-id="3ee1e-752">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-752">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-753">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-753">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="3ee1e-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="3ee1e-755">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3ee1e-756">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="3ee1e-757">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-757">Cost element</span></span></th>
<th><span data-ttu-id="3ee1e-758">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-758">Cost behavior</span></span></th>
<th><span data-ttu-id="3ee1e-759">Valor</span><span class="sxs-lookup"><span data-stu-id="3ee1e-759">Amount</span></span></th>
<th><span data-ttu-id="3ee1e-760">Data contábil</span><span class="sxs-lookup"><span data-stu-id="3ee1e-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3ee1e-761">CC001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-761">CC001</span></span></td>
<td><span data-ttu-id="3ee1e-762">RH</span><span class="sxs-lookup"><span data-stu-id="3ee1e-762">HR</span></span></td>
<td><span data-ttu-id="3ee1e-763">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-763">10001</span></span></td>
<td><span data-ttu-id="3ee1e-764">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-764">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-765">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-765">Fixed cost</span></span></td>
<td><span data-ttu-id="3ee1e-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-766">-500.00</span></span></td>
<td><span data-ttu-id="3ee1e-767">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-768">CC002</span><span class="sxs-lookup"><span data-stu-id="3ee1e-768">CC002</span></span></td>
<td><span data-ttu-id="3ee1e-769">Finanças</span><span class="sxs-lookup"><span data-stu-id="3ee1e-769">Finance</span></span></td>
<td><span data-ttu-id="3ee1e-770">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-770">10001</span></span></td>
<td><span data-ttu-id="3ee1e-771">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-771">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-772">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-772">Fixed cost</span></span></td>
<td><span data-ttu-id="3ee1e-773">175.00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-773">175.00</span></span></td>
<td><span data-ttu-id="3ee1e-774">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-775">CC003</span><span class="sxs-lookup"><span data-stu-id="3ee1e-775">CC003</span></span></td>
<td><span data-ttu-id="3ee1e-776">Montagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-776">Assembly</span></span></td>
<td><span data-ttu-id="3ee1e-777">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-777">10001</span></span></td>
<td><span data-ttu-id="3ee1e-778">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-778">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-779">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-779">Fixed cost</span></span></td>
<td><span data-ttu-id="3ee1e-780">275.00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-780">275.00</span></span></td>
<td><span data-ttu-id="3ee1e-781">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-782">CC004</span><span class="sxs-lookup"><span data-stu-id="3ee1e-782">CC004</span></span></td>
<td><span data-ttu-id="3ee1e-783">Embalagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-783">Packaging</span></span></td>
<td><span data-ttu-id="3ee1e-784">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-784">10001</span></span></td>
<td><span data-ttu-id="3ee1e-785">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-785">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-786">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-786">Fixed cost</span></span></td>
<td><span data-ttu-id="3ee1e-787">50,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-787">50,00</span></span></td>
<td><span data-ttu-id="3ee1e-788">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-789">CC001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-789">CC001</span></span></td>
<td><span data-ttu-id="3ee1e-790">RH</span><span class="sxs-lookup"><span data-stu-id="3ee1e-790">HR</span></span></td>
<td><span data-ttu-id="3ee1e-791">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-791">10001</span></span></td>
<td><span data-ttu-id="3ee1e-792">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-792">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-793">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-793">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="3ee1e-794">-1,245.71</span></span></td>
<td><span data-ttu-id="3ee1e-795">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-796">CC002</span><span class="sxs-lookup"><span data-stu-id="3ee1e-796">CC002</span></span></td>
<td><span data-ttu-id="3ee1e-797">Finanças</span><span class="sxs-lookup"><span data-stu-id="3ee1e-797">Finance</span></span></td>
<td><span data-ttu-id="3ee1e-798">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-798">10001</span></span></td>
<td><span data-ttu-id="3ee1e-799">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-799">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-800">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-800">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-801">436.00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-801">436.00</span></span></td>
<td><span data-ttu-id="3ee1e-802">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-803">CC003</span><span class="sxs-lookup"><span data-stu-id="3ee1e-803">CC003</span></span></td>
<td><span data-ttu-id="3ee1e-804">Montagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-804">Assembly</span></span></td>
<td><span data-ttu-id="3ee1e-805">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-805">10001</span></span></td>
<td><span data-ttu-id="3ee1e-806">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-806">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-807">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-807">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-808">685.14</span><span class="sxs-lookup"><span data-stu-id="3ee1e-808">685.14</span></span></td>
<td><span data-ttu-id="3ee1e-809">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-810">CC004</span><span class="sxs-lookup"><span data-stu-id="3ee1e-810">CC004</span></span></td>
<td><span data-ttu-id="3ee1e-811">Embalagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-811">Packaging</span></span></td>
<td><span data-ttu-id="3ee1e-812">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-812">10001</span></span></td>
<td><span data-ttu-id="3ee1e-813">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-813">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-814">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-814">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-815">124.57</span><span class="sxs-lookup"><span data-stu-id="3ee1e-815">124.57</span></span></td>
<td><span data-ttu-id="3ee1e-816">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-817">CC002</span><span class="sxs-lookup"><span data-stu-id="3ee1e-817">CC002</span></span></td>
<td><span data-ttu-id="3ee1e-818">Finanças</span><span class="sxs-lookup"><span data-stu-id="3ee1e-818">Finance</span></span></td>
<td><span data-ttu-id="3ee1e-819">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-819">10001</span></span></td>
<td><span data-ttu-id="3ee1e-820">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-820">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-821">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-821">Fixed cost</span></span></td>
<td><span data-ttu-id="3ee1e-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-822">-675.00</span></span></td>
<td><span data-ttu-id="3ee1e-823">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-824">CC003</span><span class="sxs-lookup"><span data-stu-id="3ee1e-824">CC003</span></span></td>
<td><span data-ttu-id="3ee1e-825">Montagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-825">Assembly</span></span></td>
<td><span data-ttu-id="3ee1e-826">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-826">10001</span></span></td>
<td><span data-ttu-id="3ee1e-827">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-827">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-828">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-828">Fixed cost</span></span></td>
<td><span data-ttu-id="3ee1e-829">438.75</span><span class="sxs-lookup"><span data-stu-id="3ee1e-829">438.75</span></span></td>
<td><span data-ttu-id="3ee1e-830">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-831">CC004</span><span class="sxs-lookup"><span data-stu-id="3ee1e-831">CC004</span></span></td>
<td><span data-ttu-id="3ee1e-832">Embalagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-832">Packaging</span></span></td>
<td><span data-ttu-id="3ee1e-833">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-833">10001</span></span></td>
<td><span data-ttu-id="3ee1e-834">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-834">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-835">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-835">Fixed cost</span></span></td>
<td><span data-ttu-id="3ee1e-836">236.25</span><span class="sxs-lookup"><span data-stu-id="3ee1e-836">236.25</span></span></td>
<td><span data-ttu-id="3ee1e-837">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-838">CC002</span><span class="sxs-lookup"><span data-stu-id="3ee1e-838">CC002</span></span></td>
<td><span data-ttu-id="3ee1e-839">Finanças</span><span class="sxs-lookup"><span data-stu-id="3ee1e-839">Finance</span></span></td>
<td><span data-ttu-id="3ee1e-840">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-840">10001</span></span></td>
<td><span data-ttu-id="3ee1e-841">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-841">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-842">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-842">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="3ee1e-843">-8,150.29</span></span></td>
<td><span data-ttu-id="3ee1e-844">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-845">CC003</span><span class="sxs-lookup"><span data-stu-id="3ee1e-845">CC003</span></span></td>
<td><span data-ttu-id="3ee1e-846">Montagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-846">Assembly</span></span></td>
<td><span data-ttu-id="3ee1e-847">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-847">10001</span></span></td>
<td><span data-ttu-id="3ee1e-848">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-848">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-849">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-849">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="3ee1e-850">5,297.69</span></span></td>
<td><span data-ttu-id="3ee1e-851">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-852">CC004</span><span class="sxs-lookup"><span data-stu-id="3ee1e-852">CC004</span></span></td>
<td><span data-ttu-id="3ee1e-853">Embalagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-853">Packaging</span></span></td>
<td><span data-ttu-id="3ee1e-854">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-854">10001</span></span></td>
<td><span data-ttu-id="3ee1e-855">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-855">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-856">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-856">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="3ee1e-857">2,852.60</span></span></td>
<td><span data-ttu-id="3ee1e-858">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-859">CC003</span><span class="sxs-lookup"><span data-stu-id="3ee1e-859">CC003</span></span></td>
<td><span data-ttu-id="3ee1e-860">Montagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-860">Assembly</span></span></td>
<td><span data-ttu-id="3ee1e-861">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-861">10001</span></span></td>
<td><span data-ttu-id="3ee1e-862">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-862">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-863">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-863">Fixed cost</span></span></td>
<td><span data-ttu-id="3ee1e-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="3ee1e-864">-713.75</span></span></td>
<td><span data-ttu-id="3ee1e-865">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-866">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-866">Prod 1</span></span></td>
<td><span data-ttu-id="3ee1e-867">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-867">Product 1</span></span></td>
<td><span data-ttu-id="3ee1e-868">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-868">10001</span></span></td>
<td><span data-ttu-id="3ee1e-869">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-869">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-870">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-870">Fixed cost</span></span></td>
<td><span data-ttu-id="3ee1e-871">535.31</span><span class="sxs-lookup"><span data-stu-id="3ee1e-871">535.31</span></span></td>
<td><span data-ttu-id="3ee1e-872">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-873">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-873">Prod 2</span></span></td>
<td><span data-ttu-id="3ee1e-874">Produto 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-874">Product 2</span></span></td>
<td><span data-ttu-id="3ee1e-875">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-875">10001</span></span></td>
<td><span data-ttu-id="3ee1e-876">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-876">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-877">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-877">Fixed cost</span></span></td>
<td><span data-ttu-id="3ee1e-878">178.44</span><span class="sxs-lookup"><span data-stu-id="3ee1e-878">178.44</span></span></td>
<td><span data-ttu-id="3ee1e-879">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-880">CC003</span><span class="sxs-lookup"><span data-stu-id="3ee1e-880">CC003</span></span></td>
<td><span data-ttu-id="3ee1e-881">Montagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-881">Assembly</span></span></td>
<td><span data-ttu-id="3ee1e-882">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-882">10001</span></span></td>
<td><span data-ttu-id="3ee1e-883">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-883">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-884">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-884">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="3ee1e-885">-5,982.83</span></span></td>
<td><span data-ttu-id="3ee1e-886">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-887">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-887">Prod 1</span></span></td>
<td><span data-ttu-id="3ee1e-888">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-888">Product 1</span></span></td>
<td><span data-ttu-id="3ee1e-889">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-889">10001</span></span></td>
<td><span data-ttu-id="3ee1e-890">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-890">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-891">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-891">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="3ee1e-892">4,487.12</span></span></td>
<td><span data-ttu-id="3ee1e-893">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-894">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-894">Prod 2</span></span></td>
<td><span data-ttu-id="3ee1e-895">Produto 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-895">Product 2</span></span></td>
<td><span data-ttu-id="3ee1e-896">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-896">10001</span></span></td>
<td><span data-ttu-id="3ee1e-897">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-897">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-898">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-898">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="3ee1e-899">1,495.71</span></span></td>
<td><span data-ttu-id="3ee1e-900">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-901">CC003</span><span class="sxs-lookup"><span data-stu-id="3ee1e-901">CC003</span></span></td>
<td><span data-ttu-id="3ee1e-902">Montagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-902">Assembly</span></span></td>
<td><span data-ttu-id="3ee1e-903">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-903">10001</span></span></td>
<td><span data-ttu-id="3ee1e-904">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-904">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-905">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-905">Fixed cost</span></span></td>
<td><span data-ttu-id="3ee1e-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="3ee1e-906">-286.25</span></span></td>
<td><span data-ttu-id="3ee1e-907">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-908">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-908">Prod 1</span></span></td>
<td><span data-ttu-id="3ee1e-909">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-909">Product 1</span></span></td>
<td><span data-ttu-id="3ee1e-910">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-910">10001</span></span></td>
<td><span data-ttu-id="3ee1e-911">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-911">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-912">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-912">Fixed cost</span></span></td>
<td><span data-ttu-id="3ee1e-913">241.05</span><span class="sxs-lookup"><span data-stu-id="3ee1e-913">241.05</span></span></td>
<td><span data-ttu-id="3ee1e-914">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-915">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-915">Prod 2</span></span></td>
<td><span data-ttu-id="3ee1e-916">Produto 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-916">Product 2</span></span></td>
<td><span data-ttu-id="3ee1e-917">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-917">10001</span></span></td>
<td><span data-ttu-id="3ee1e-918">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-918">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-919">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-919">Fixed cost</span></span></td>
<td><span data-ttu-id="3ee1e-920">45.20</span><span class="sxs-lookup"><span data-stu-id="3ee1e-920">45.20</span></span></td>
<td><span data-ttu-id="3ee1e-921">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-922">CC003</span><span class="sxs-lookup"><span data-stu-id="3ee1e-922">CC003</span></span></td>
<td><span data-ttu-id="3ee1e-923">Montagem</span><span class="sxs-lookup"><span data-stu-id="3ee1e-923">Assembly</span></span></td>
<td><span data-ttu-id="3ee1e-924">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-924">10001</span></span></td>
<td><span data-ttu-id="3ee1e-925">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-925">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-926">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-926">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="3ee1e-927">-2,977.17</span></span></td>
<td><span data-ttu-id="3ee1e-928">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-929">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-929">Prod 1</span></span></td>
<td><span data-ttu-id="3ee1e-930">Produto 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-930">Product 1</span></span></td>
<td><span data-ttu-id="3ee1e-931">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-931">10001</span></span></td>
<td><span data-ttu-id="3ee1e-932">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-932">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-933">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-933">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="3ee1e-934">2,507.09</span></span></td>
<td><span data-ttu-id="3ee1e-935">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3ee1e-936">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-936">Prod 2</span></span></td>
<td><span data-ttu-id="3ee1e-937">Produto 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-937">Product 2</span></span></td>
<td><span data-ttu-id="3ee1e-938">10001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-938">10001</span></span></td>
<td><span data-ttu-id="3ee1e-939">eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-939">Electricity</span></span></td>
<td><span data-ttu-id="3ee1e-940">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-940">Variable cost</span></span></td>
<td><span data-ttu-id="3ee1e-941">470.08</span><span class="sxs-lookup"><span data-stu-id="3ee1e-941">470.08</span></span></td>
<td><span data-ttu-id="3ee1e-942">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="3ee1e-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="3ee1e-943">Conclusão</span><span class="sxs-lookup"><span data-stu-id="3ee1e-943">Conclusion</span></span>
<span data-ttu-id="3ee1e-944">Na contabilidade financeira, um custo de 10,000.00 para a eletricidade é lançado para um ID fictício de centro de custos.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="3ee1e-945">Portanto, os contadores de custo saberão que esses custos devem ser alocados.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="3ee1e-946">Na contabilização de custo, os custos fluem nas unidades organizacionais e nos níveis, com base nas políticas e regras que são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="3ee1e-947">Cada custo foi associado a uma base de alocação que fornece a melhor apuração para a alocação de custos.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="3ee1e-948">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="3ee1e-949">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="3ee1e-950">Total</span><span class="sxs-lookup"><span data-stu-id="3ee1e-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="3ee1e-951">CC099</span><span class="sxs-lookup"><span data-stu-id="3ee1e-951">CC099</span></span></th>
<th><span data-ttu-id="3ee1e-952">CC001</span><span class="sxs-lookup"><span data-stu-id="3ee1e-952">CC001</span></span></th>
<th><span data-ttu-id="3ee1e-953">CC002</span><span class="sxs-lookup"><span data-stu-id="3ee1e-953">CC002</span></span></th>
<th><span data-ttu-id="3ee1e-954">CC003</span><span class="sxs-lookup"><span data-stu-id="3ee1e-954">CC003</span></span></th>
<th><span data-ttu-id="3ee1e-955">CC004</span><span class="sxs-lookup"><span data-stu-id="3ee1e-955">CC004</span></span></th>
<th><span data-ttu-id="3ee1e-956">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-956">Proj 1</span></span></th>
<th><span data-ttu-id="3ee1e-957">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-957">Proj 2</span></span></th>
<th><span data-ttu-id="3ee1e-958">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="3ee1e-958">Prod 1</span></span></th>
<th><span data-ttu-id="3ee1e-959">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="3ee1e-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="3ee1e-960">10001 Eletricidade</span><span class="sxs-lookup"><span data-stu-id="3ee1e-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="3ee1e-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="3ee1e-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="3ee1e-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="3ee1e-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="3ee1e-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="3ee1e-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="3ee1e-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="3ee1e-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="3ee1e-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="3ee1e-970">Não classificado</span><span class="sxs-lookup"><span data-stu-id="3ee1e-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-971">0,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="3ee1e-972">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="3ee1e-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-973">0,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-974">0,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-975">0,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-976">0,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-977">0,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-978">776.36</span><span class="sxs-lookup"><span data-stu-id="3ee1e-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-979">223.64</span><span class="sxs-lookup"><span data-stu-id="3ee1e-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="3ee1e-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="3ee1e-981">Custo variável</span><span class="sxs-lookup"><span data-stu-id="3ee1e-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-982">000</span><span class="sxs-lookup"><span data-stu-id="3ee1e-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-983">0,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-984">0,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-985">0,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-986">0,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-987">30,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-988">10,00</span><span class="sxs-lookup"><span data-stu-id="3ee1e-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="3ee1e-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="3ee1e-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3ee1e-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="3ee1e-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="3ee1e-992">Esse tópico mostra como um elemento de custo principal, 10001 Eletricidade flui pelos objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="3ee1e-993">Portanto, esse custo geral indireto é alocado no nível mais baixo na organização.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="3ee1e-994">Em outras palavras, os objetos de custo no nível mais baixo assumem o custo.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="3ee1e-995">Se você exigir um fluxo visual de custo entre objetos de custo, é possível usar as regras de política de acúmulo de custos para visualizar o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="3ee1e-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="3ee1e-996">Para obter mais informações, consulte [Política de acúmulo de custo e cálculo de custos indiretos](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="3ee1e-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



