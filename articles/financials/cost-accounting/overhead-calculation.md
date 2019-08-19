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
ms.openlocfilehash: cef4a80aa12927fdbffea4bb6bcb108ad81494a6
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841480"
---
# <a name="overhead-calculation"></a><span data-ttu-id="dbf5b-103">Cálculo de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="dbf5b-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dbf5b-104">Este tópico descreve processos comuns para calcular e alocar os custos gerais indiretos.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="dbf5b-105">Definição de termo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-105">Term definition</span></span>
---------------

<span data-ttu-id="dbf5b-106">Os custos gerais indiretos são aqueles que foram incorridos para realizar um negócio, mas não podem ser diretamente atribuídos a qualquer atividade comercial, produto ou serviço específico.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="dbf5b-107">Os custos gerais indiretos fornecem suporte crítico para geração de atividades produtivas.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="dbf5b-108">Eis alguns exemplos de custos gerais:</span><span class="sxs-lookup"><span data-stu-id="dbf5b-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="dbf5b-109">Aluguel</span><span class="sxs-lookup"><span data-stu-id="dbf5b-109">Rent</span></span>
-   <span data-ttu-id="dbf5b-110">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-110">Electricity</span></span>
-   <span data-ttu-id="dbf5b-111">Salários administrativos</span><span class="sxs-lookup"><span data-stu-id="dbf5b-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="dbf5b-112">Visão geral do cálculo de custos gerais indiretos</span><span class="sxs-lookup"><span data-stu-id="dbf5b-112">Overhead calculation overview</span></span>
<span data-ttu-id="dbf5b-113">O cálculo de custos gerais indiretos executa as políticas de contabilização de custos na ordem correta.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="dbf5b-114">Você pode executar o cálculo de custos gerais indiretos várias vezes para o mesmo período fiscal, se as políticas de contabilidade de custo foram modificadas ou foram detectados erros específicos.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="dbf5b-115">Cada execução do cálculo de custos gerais indiretos é armazenada e recebe um ID exclusivo de versão que permite comparar os cálculos em várias versões.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="dbf5b-116">As entradas de custo que o cálculo de custos indiretos gera recebe uma data contábil.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="dbf5b-117">Essa data contábil corresponde à data final do período fiscal que é usada no cálculo.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="dbf5b-118">A ID exclusiva de versão consiste nos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="dbf5b-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="dbf5b-119">Tipo de versão</span><span class="sxs-lookup"><span data-stu-id="dbf5b-119">Version type</span></span>
-   <span data-ttu-id="dbf5b-120">Data e hora</span><span class="sxs-lookup"><span data-stu-id="dbf5b-120">Date and time</span></span>
-   <span data-ttu-id="dbf5b-121">Razão de contabilização de custos</span><span class="sxs-lookup"><span data-stu-id="dbf5b-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="dbf5b-122">Ano fiscal</span><span class="sxs-lookup"><span data-stu-id="dbf5b-122">Fiscal year</span></span>
-   <span data-ttu-id="dbf5b-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="dbf5b-123">Fiscal period</span></span>

<span data-ttu-id="dbf5b-124">O cálculo de custos gerais indiretos é executado independentemente da versão.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="dbf5b-125">Portanto, você pode calcular a versão de orçamento antes da versão atual.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="dbf5b-126">O cálculo de custos gerais indiretos consiste em quatro etapas, conforme mostrado na ilustração.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="dbf5b-127">Em cada etapa, um cabeçalho de diário é criado com entradas de diário.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="dbf5b-128">Esse cabeçalho de diário mantém dados de entrada para cada etapa de cálculo.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="dbf5b-129">As políticas e regras são aplicadas a cada linha do diário e as entradas de custo são geradas como saídas.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="dbf5b-130">Portanto, você sempre terá rastreabilidade total.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="dbf5b-131">[![Cálculo de custos gerais indiretos](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="dbf5b-132">Calcular e alocar os custos gerais indiretos de Eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="dbf5b-133">Na contabilidade financeira, alguns custos, como eletricidade, são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="dbf5b-134">Portanto, a visão administrativa detalhada não é fornecida para a contabilização de custo.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="dbf5b-135">Na contabilização de custo, para fornecer a visão administrativa correta em todas as unidades organizacionais e níveis, os custos devem passar pelas unidades organizacionais.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="dbf5b-136">Este fluxo deve ser baseado em qualquer um registro exato do consumo ou de uma previsão justa.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="dbf5b-137">Na contabilidade, um custo de eletricidade pode ser lançado, conforme mostrado na tabela.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dbf5b-138">Data contábil</span><span class="sxs-lookup"><span data-stu-id="dbf5b-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="dbf5b-139">Centro de custos</span><span class="sxs-lookup"><span data-stu-id="dbf5b-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="dbf5b-140">Conta principal</span><span class="sxs-lookup"><span data-stu-id="dbf5b-140">Main account</span></span></th>
<th><span data-ttu-id="dbf5b-141">Valor na moeda contábil</span><span class="sxs-lookup"><span data-stu-id="dbf5b-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-142">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="dbf5b-143">CC099</span><span class="sxs-lookup"><span data-stu-id="dbf5b-143">CC099</span></span></td>
<td><span data-ttu-id="dbf5b-144">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="dbf5b-144">Default cost center</span></span></td>
<td><span data-ttu-id="dbf5b-145">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-145">10001</span></span></td>
<td><span data-ttu-id="dbf5b-146">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-146">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="dbf5b-148">Etapa 1: Processar o cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="dbf5b-149">Por padrão, quando as entradas de custo previsto são importadas de dados de origem, elas recebem a classificação de comportamento de custo **Não classificado** na Contabilidade de custos.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="dbf5b-150">Aplicando regras da política de comportamento de custo, é possível reclassificar entradas de custo como **Custo fixo** ou **Custo variável**.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="dbf5b-151">Definir a regra de custo de comportamento</span><span class="sxs-lookup"><span data-stu-id="dbf5b-151">Define the cost behavior rule</span></span>

<span data-ttu-id="dbf5b-152">Em alguns casos, parte do custo é uma taxa fixa e o custos pendente é baseado no consumo.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="dbf5b-153">Geralmente, as contas de eletricidade correspondem a esta definição.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="dbf5b-154">Após você pagar uma taxa fixa específica, você paga por consumo, por hora de quilowatt (Kwh).</span><span class="sxs-lookup"><span data-stu-id="dbf5b-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="dbf5b-155">Por exemplo, se a taxa de custo fixa for 1.000.00, veja aqui como a regra de comportamento de custo é definida:</span><span class="sxs-lookup"><span data-stu-id="dbf5b-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="dbf5b-156">Valor fixo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="dbf5b-157">0 &lt;= 1.000,00 = Fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="dbf5b-158">1000.01 &lt; N = Variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="dbf5b-159">Diário</span><span class="sxs-lookup"><span data-stu-id="dbf5b-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dbf5b-160">Diário</span><span class="sxs-lookup"><span data-stu-id="dbf5b-160">Journal</span></span></th>
<th><span data-ttu-id="dbf5b-161">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="dbf5b-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="dbf5b-162">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="dbf5b-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="dbf5b-163">Versão</span><span class="sxs-lookup"><span data-stu-id="dbf5b-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-164">00001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-164">00001</span></span></td>
<td><span data-ttu-id="dbf5b-165">Diário de cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="dbf5b-166">fiscal</span><span class="sxs-lookup"><span data-stu-id="dbf5b-166">Fiscal</span></span></td>
<td><span data-ttu-id="dbf5b-167">2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-167">2017</span></span></td>
<td><span data-ttu-id="dbf5b-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-168">Period 1</span></span></td>
<td><span data-ttu-id="dbf5b-169">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="dbf5b-170">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dbf5b-171">Data contábil</span><span class="sxs-lookup"><span data-stu-id="dbf5b-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="dbf5b-172">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="dbf5b-173">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-173">Cost element</span></span></th>
<th><span data-ttu-id="dbf5b-174">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-174">Cost behavior</span></span></th>
<th><span data-ttu-id="dbf5b-175">Valor</span><span class="sxs-lookup"><span data-stu-id="dbf5b-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-176">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="dbf5b-177">CC099</span><span class="sxs-lookup"><span data-stu-id="dbf5b-177">CC099</span></span></td>
<td><span data-ttu-id="dbf5b-178">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="dbf5b-178">Default cost center</span></span></td>
<td><span data-ttu-id="dbf5b-179">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-179">10001</span></span></td>
<td><span data-ttu-id="dbf5b-180">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-180">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-181">Não classificado</span><span class="sxs-lookup"><span data-stu-id="dbf5b-181">Unclassified</span></span></td>
<td><span data-ttu-id="dbf5b-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="dbf5b-183">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dbf5b-184">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="dbf5b-185">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-185">Cost element</span></span></th>
<th><span data-ttu-id="dbf5b-186">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-186">Cost behavior</span></span></th>
<th><span data-ttu-id="dbf5b-187">Valor</span><span class="sxs-lookup"><span data-stu-id="dbf5b-187">Amount</span></span></th>
<th><span data-ttu-id="dbf5b-188">Data contábil</span><span class="sxs-lookup"><span data-stu-id="dbf5b-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-189">CC099</span><span class="sxs-lookup"><span data-stu-id="dbf5b-189">CC099</span></span></td>
<td><span data-ttu-id="dbf5b-190">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="dbf5b-190">Default cost center</span></span></td>
<td><span data-ttu-id="dbf5b-191">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-191">10001</span></span></td>
<td><span data-ttu-id="dbf5b-192">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-192">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-193">Não classificado</span><span class="sxs-lookup"><span data-stu-id="dbf5b-193">Unclassified</span></span></td>
<td><span data-ttu-id="dbf5b-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-194">10,000.00</span></span></td>
<td><span data-ttu-id="dbf5b-195">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-196">CC099</span><span class="sxs-lookup"><span data-stu-id="dbf5b-196">CC099</span></span></td>
<td><span data-ttu-id="dbf5b-197">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="dbf5b-197">Default cost center</span></span></td>
<td><span data-ttu-id="dbf5b-198">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-198">10001</span></span></td>
<td><span data-ttu-id="dbf5b-199">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-199">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-200">Não classificado</span><span class="sxs-lookup"><span data-stu-id="dbf5b-200">Unclassified</span></span></td>
<td><span data-ttu-id="dbf5b-201">-10.000,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-201">-10,000.00</span></span></td>
<td><span data-ttu-id="dbf5b-202">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-203">CC099</span><span class="sxs-lookup"><span data-stu-id="dbf5b-203">CC099</span></span></td>
<td><span data-ttu-id="dbf5b-204">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="dbf5b-204">Default cost center</span></span></td>
<td><span data-ttu-id="dbf5b-205">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-205">10001</span></span></td>
<td><span data-ttu-id="dbf5b-206">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-206">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-207">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-207">Fixed cost</span></span></td>
<td><span data-ttu-id="dbf5b-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-208">1,000.00</span></span></td>
<td><span data-ttu-id="dbf5b-209">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-210">CC099</span><span class="sxs-lookup"><span data-stu-id="dbf5b-210">CC099</span></span></td>
<td><span data-ttu-id="dbf5b-211">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="dbf5b-211">Default cost center</span></span></td>
<td><span data-ttu-id="dbf5b-212">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-212">10001</span></span></td>
<td><span data-ttu-id="dbf5b-213">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-213">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-214">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-214">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-215">9,000.00</span></span></td>
<td><span data-ttu-id="dbf5b-216">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dbf5b-217">Para obter mais informações, consulte [Criar e atribuir uma política de comportamento de custos a uma unidade de controle de custos](tasks/create-assign-cost-behavior-policy-cost-control-unit.md)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="dbf5b-218">Etapa 2: Processar o cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="dbf5b-219">A distribuição de custos é usada para redistribuir custo de um objeto de custo a um ou mais outros objetos de custo, aplicando uma base de alocação relevante.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="dbf5b-220">A distribuição de custos e a alocação de custo são diferentes na distribuição de custos, sempre que ocorrer em nível de elemento de custo principal do custo original.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="dbf5b-221">Definir a regra de distribuição de custos</span><span class="sxs-lookup"><span data-stu-id="dbf5b-221">Define the cost distribution rule</span></span>

<span data-ttu-id="dbf5b-222">Na contabilidade financeira, os custos de eletricidade geralmente são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="dbf5b-223">Na contabilização de custo, esta abordagem não é suficientemente detalhada.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="dbf5b-224">O custo variável deve ser distribuído a objetos de custos individuais com base justa.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="dbf5b-225">A base de alocação mais lógica é o consumo de eletricidade (Kwh).</span><span class="sxs-lookup"><span data-stu-id="dbf5b-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="dbf5b-226">O membro da dimensão estatística que é chamado Eletricidade é criado e o consumo de eletricidade é registrado.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="dbf5b-227">Por padrão, todos os membros estatísticos da dimensão se tornam disponíveis como bases de alocação.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dbf5b-228">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-228">Cost object</span></span></th>
<th><span data-ttu-id="dbf5b-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="dbf5b-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-230">CC001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-230">CC001</span></span></td>
<td><span data-ttu-id="dbf5b-231">RH</span><span class="sxs-lookup"><span data-stu-id="dbf5b-231">HR</span></span></td>
<td><span data-ttu-id="dbf5b-232">1.000</span><span class="sxs-lookup"><span data-stu-id="dbf5b-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-233">CC002</span><span class="sxs-lookup"><span data-stu-id="dbf5b-233">CC002</span></span></td>
<td><span data-ttu-id="dbf5b-234">Finanças</span><span class="sxs-lookup"><span data-stu-id="dbf5b-234">Finance</span></span></td>
<td><span data-ttu-id="dbf5b-235">6,000</span><span class="sxs-lookup"><span data-stu-id="dbf5b-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-236">CC003</span><span class="sxs-lookup"><span data-stu-id="dbf5b-236">CC003</span></span></td>
<td><span data-ttu-id="dbf5b-237">Montagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-237">Assembly</span></span></td>
<td><span data-ttu-id="dbf5b-238">0</span><span class="sxs-lookup"><span data-stu-id="dbf5b-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dbf5b-239">A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação para custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dbf5b-240">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-240">Cost object</span></span></th>
<th><span data-ttu-id="dbf5b-241">Magnitude</span><span class="sxs-lookup"><span data-stu-id="dbf5b-241">Magnitude</span></span></th>
<th><span data-ttu-id="dbf5b-242">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="dbf5b-242">Allocation factor</span></span></th>
<th><span data-ttu-id="dbf5b-243">Valor</span><span class="sxs-lookup"><span data-stu-id="dbf5b-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-244">CC001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-244">CC001</span></span></td>
<td><span data-ttu-id="dbf5b-245">RH</span><span class="sxs-lookup"><span data-stu-id="dbf5b-245">HR</span></span></td>
<td><span data-ttu-id="dbf5b-246">1.000</span><span class="sxs-lookup"><span data-stu-id="dbf5b-246">1,000</span></span></td>
<td><span data-ttu-id="dbf5b-247">(1.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="dbf5b-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="dbf5b-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-249">CC002</span><span class="sxs-lookup"><span data-stu-id="dbf5b-249">CC002</span></span></td>
<td><span data-ttu-id="dbf5b-250">Finanças</span><span class="sxs-lookup"><span data-stu-id="dbf5b-250">Finance</span></span></td>
<td><span data-ttu-id="dbf5b-251">6,000</span><span class="sxs-lookup"><span data-stu-id="dbf5b-251">6,000</span></span></td>
<td><span data-ttu-id="dbf5b-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="dbf5b-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="dbf5b-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-254">CC003</span><span class="sxs-lookup"><span data-stu-id="dbf5b-254">CC003</span></span></td>
<td><span data-ttu-id="dbf5b-255">Montagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-255">Assembly</span></span></td>
<td><span data-ttu-id="dbf5b-256">0</span><span class="sxs-lookup"><span data-stu-id="dbf5b-256">0</span></span></td>
<td><span data-ttu-id="dbf5b-257">(0 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="dbf5b-258">0,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dbf5b-259">Os custos fixos devem ser distribuídos igualmente a objetos de custo individuais que têm a eletricidade consumida.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="dbf5b-260">Você pode obter esse resultado usando o membro estatístico de dimensão de eletricidade em uma base e alocação da fórmula: (Eletricidade &gt; 0,00) A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação de custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dbf5b-261">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-261">Cost object</span></span></th>
<th><span data-ttu-id="dbf5b-262">Fórmula</span><span class="sxs-lookup"><span data-stu-id="dbf5b-262">Formula</span></span></th>
<th><span data-ttu-id="dbf5b-263">Magnitude</span><span class="sxs-lookup"><span data-stu-id="dbf5b-263">Magnitude</span></span></th>
<th><span data-ttu-id="dbf5b-264">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="dbf5b-264">Allocation factor</span></span></th>
<th><span data-ttu-id="dbf5b-265">Valor</span><span class="sxs-lookup"><span data-stu-id="dbf5b-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-266">CC001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-266">CC001</span></span></td>
<td><span data-ttu-id="dbf5b-267">RH</span><span class="sxs-lookup"><span data-stu-id="dbf5b-267">HR</span></span></td>
<td><span data-ttu-id="dbf5b-268">(1.000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="dbf5b-269">1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-269">1</span></span></td>
<td><span data-ttu-id="dbf5b-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="dbf5b-271">500,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-272">CC002</span><span class="sxs-lookup"><span data-stu-id="dbf5b-272">CC002</span></span></td>
<td><span data-ttu-id="dbf5b-273">Finanças</span><span class="sxs-lookup"><span data-stu-id="dbf5b-273">Finance</span></span></td>
<td><span data-ttu-id="dbf5b-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="dbf5b-275">1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-275">1</span></span></td>
<td><span data-ttu-id="dbf5b-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="dbf5b-277">500,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-278">CC003</span><span class="sxs-lookup"><span data-stu-id="dbf5b-278">CC003</span></span></td>
<td><span data-ttu-id="dbf5b-279">Montagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-279">Assembly</span></span></td>
<td><span data-ttu-id="dbf5b-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="dbf5b-281">0</span><span class="sxs-lookup"><span data-stu-id="dbf5b-281">0</span></span></td>
<td><span data-ttu-id="dbf5b-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="dbf5b-283">0,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="dbf5b-284">Diário</span><span class="sxs-lookup"><span data-stu-id="dbf5b-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dbf5b-285">Diário</span><span class="sxs-lookup"><span data-stu-id="dbf5b-285">Journal</span></span></th>
<th><span data-ttu-id="dbf5b-286">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="dbf5b-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="dbf5b-287">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="dbf5b-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="dbf5b-288">Versão</span><span class="sxs-lookup"><span data-stu-id="dbf5b-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-289">00002</span><span class="sxs-lookup"><span data-stu-id="dbf5b-289">00002</span></span></td>
<td><span data-ttu-id="dbf5b-290">Diário de cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="dbf5b-291">fiscal</span><span class="sxs-lookup"><span data-stu-id="dbf5b-291">Fiscal</span></span></td>
<td><span data-ttu-id="dbf5b-292">2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-292">2017</span></span></td>
<td><span data-ttu-id="dbf5b-293">Período 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-293">Period 1</span></span></td>
<td><span data-ttu-id="dbf5b-294">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="dbf5b-295">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dbf5b-296">Data contábil</span><span class="sxs-lookup"><span data-stu-id="dbf5b-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="dbf5b-297">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="dbf5b-298">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-298">Cost element</span></span></th>
<th><span data-ttu-id="dbf5b-299">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-299">Cost behavior</span></span></th>
<th><span data-ttu-id="dbf5b-300">Valor</span><span class="sxs-lookup"><span data-stu-id="dbf5b-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-301">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="dbf5b-302">CC099</span><span class="sxs-lookup"><span data-stu-id="dbf5b-302">CC099</span></span></td>
<td><span data-ttu-id="dbf5b-303">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="dbf5b-303">Default cost center</span></span></td>
<td><span data-ttu-id="dbf5b-304">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-304">10001</span></span></td>
<td><span data-ttu-id="dbf5b-305">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-305">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-306">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-306">Fixed cost</span></span></td>
<td><span data-ttu-id="dbf5b-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-308">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="dbf5b-309">CC099</span><span class="sxs-lookup"><span data-stu-id="dbf5b-309">CC099</span></span></td>
<td><span data-ttu-id="dbf5b-310">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="dbf5b-310">Default cost center</span></span></td>
<td><span data-ttu-id="dbf5b-311">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-311">10001</span></span></td>
<td><span data-ttu-id="dbf5b-312">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-312">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-313">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-313">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="dbf5b-315">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dbf5b-316">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="dbf5b-317">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-317">Cost element</span></span></th>
<th><span data-ttu-id="dbf5b-318">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-318">Cost behavior</span></span></th>
<th><span data-ttu-id="dbf5b-319">Valor</span><span class="sxs-lookup"><span data-stu-id="dbf5b-319">Amount</span></span></th>
<th><span data-ttu-id="dbf5b-320">Data contábil</span><span class="sxs-lookup"><span data-stu-id="dbf5b-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-321">CC099</span><span class="sxs-lookup"><span data-stu-id="dbf5b-321">CC099</span></span></td>
<td><span data-ttu-id="dbf5b-322">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="dbf5b-322">Default cost center</span></span></td>
<td><span data-ttu-id="dbf5b-323">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-323">10001</span></span></td>
<td><span data-ttu-id="dbf5b-324">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-324">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-325">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-325">Fixed cost</span></span></td>
<td><span data-ttu-id="dbf5b-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-326">-1,000.00</span></span></td>
<td><span data-ttu-id="dbf5b-327">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-328">CC001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-328">CC001</span></span></td>
<td><span data-ttu-id="dbf5b-329">RH</span><span class="sxs-lookup"><span data-stu-id="dbf5b-329">HR</span></span></td>
<td><span data-ttu-id="dbf5b-330">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-330">10001</span></span></td>
<td><span data-ttu-id="dbf5b-331">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-331">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-332">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-332">Fixed cost</span></span></td>
<td><span data-ttu-id="dbf5b-333">500,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-333">500.00</span></span></td>
<td><span data-ttu-id="dbf5b-334">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-335">CC002</span><span class="sxs-lookup"><span data-stu-id="dbf5b-335">CC002</span></span></td>
<td><span data-ttu-id="dbf5b-336">Finanças</span><span class="sxs-lookup"><span data-stu-id="dbf5b-336">Finance</span></span></td>
<td><span data-ttu-id="dbf5b-337">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-337">10001</span></span></td>
<td><span data-ttu-id="dbf5b-338">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-338">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-339">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-339">Fixed cost</span></span></td>
<td><span data-ttu-id="dbf5b-340">500,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-340">500.00</span></span></td>
<td><span data-ttu-id="dbf5b-341">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-342">CC099</span><span class="sxs-lookup"><span data-stu-id="dbf5b-342">CC099</span></span></td>
<td><span data-ttu-id="dbf5b-343">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="dbf5b-343">Default cost center</span></span></td>
<td><span data-ttu-id="dbf5b-344">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-344">10001</span></span></td>
<td><span data-ttu-id="dbf5b-345">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-345">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-346">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-346">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-347">-9,000.00</span></span></td>
<td><span data-ttu-id="dbf5b-348">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-349">CC001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-349">CC001</span></span></td>
<td><span data-ttu-id="dbf5b-350">RH</span><span class="sxs-lookup"><span data-stu-id="dbf5b-350">HR</span></span></td>
<td><span data-ttu-id="dbf5b-351">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-351">10001</span></span></td>
<td><span data-ttu-id="dbf5b-352">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-352">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-353">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-353">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="dbf5b-354">1,285.71</span></span></td>
<td><span data-ttu-id="dbf5b-355">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-356">CC002</span><span class="sxs-lookup"><span data-stu-id="dbf5b-356">CC002</span></span></td>
<td><span data-ttu-id="dbf5b-357">Finanças</span><span class="sxs-lookup"><span data-stu-id="dbf5b-357">Finance</span></span></td>
<td><span data-ttu-id="dbf5b-358">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-358">10001</span></span></td>
<td><span data-ttu-id="dbf5b-359">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-359">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-360">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-360">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="dbf5b-361">7,714.29</span></span></td>
<td><span data-ttu-id="dbf5b-362">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dbf5b-363">Para obter mais informações, consulte [Criar e atribuir uma política de distribuição de custos a uma unidade de controle de custos](tasks/create-assign-cost-distribution-policy-cost-control-unit.md)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="dbf5b-364">Etapa 3: Processar o cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="dbf5b-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="dbf5b-365">A taxa de custos indiretos é usada para cobrar um ou mais objetos de custos específicos.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="dbf5b-366">O encargo se baseia em uma taxa de custo predeterminada e a magnitude da básica de alocação atribuída.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="dbf5b-367">Defina a taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="dbf5b-367">Define the overhead rate</span></span>

<span data-ttu-id="dbf5b-368">O objeto de custo CC001 HR contribui para um conjunto de projetos internos.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="dbf5b-369">Um membro de dimensão estatística que é chamado de projetos de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dbf5b-370">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-370">Cost object</span></span></th>
<th><span data-ttu-id="dbf5b-371">Horas</span><span class="sxs-lookup"><span data-stu-id="dbf5b-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-372">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-372">Proj 1</span></span></td>
<td><span data-ttu-id="dbf5b-373">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-373">Project 1</span></span></td>
<td><span data-ttu-id="dbf5b-374">3</span><span class="sxs-lookup"><span data-stu-id="dbf5b-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-375">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-375">Proj 2</span></span></td>
<td><span data-ttu-id="dbf5b-376">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-376">Project 2</span></span></td>
<td><span data-ttu-id="dbf5b-377">1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dbf5b-378">Uma taxa de custo predeterminada da contribuição de projetos de custo foi definida.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dbf5b-379">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-379">Cost object</span></span></th>
<th><span data-ttu-id="dbf5b-380">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-380">Cost element</span></span></th>
<th><span data-ttu-id="dbf5b-381">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-381">Cost behavior</span></span></th>
<th><span data-ttu-id="dbf5b-382">Unidades</span><span class="sxs-lookup"><span data-stu-id="dbf5b-382">Units</span></span></th>
<th><span data-ttu-id="dbf5b-383">Taxa</span><span class="sxs-lookup"><span data-stu-id="dbf5b-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-384">CC001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-384">CC001</span></span></td>
<td><span data-ttu-id="dbf5b-385">RH</span><span class="sxs-lookup"><span data-stu-id="dbf5b-385">HR</span></span></td>
<td><span data-ttu-id="dbf5b-386">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-386">10001</span></span></td>
<td><span data-ttu-id="dbf5b-387">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-387">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-388">1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-388">1</span></span></td>
<td><span data-ttu-id="dbf5b-389">10</span><span class="sxs-lookup"><span data-stu-id="dbf5b-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dbf5b-390">A tabela a seguir mostra o resultado quando projetos de RH são aplicados como base de alocação.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dbf5b-391">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-391">Cost object</span></span></th>
<th><span data-ttu-id="dbf5b-392">Magnitude</span><span class="sxs-lookup"><span data-stu-id="dbf5b-392">Magnitude</span></span></th>
<th><span data-ttu-id="dbf5b-393">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-393">Cost element</span></span></th>
<th><span data-ttu-id="dbf5b-394">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="dbf5b-394">Allocation factor</span></span></th>
<th><span data-ttu-id="dbf5b-395">Valor</span><span class="sxs-lookup"><span data-stu-id="dbf5b-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-396">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-396">Proj 1</span></span></td>
<td><span data-ttu-id="dbf5b-397">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-397">Project 1</span></span></td>
<td><span data-ttu-id="dbf5b-398">3</span><span class="sxs-lookup"><span data-stu-id="dbf5b-398">3</span></span></td>
<td><span data-ttu-id="dbf5b-399">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-399">10001</span></span></td>
<td><span data-ttu-id="dbf5b-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="dbf5b-401">30,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-402">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-402">Proj 2</span></span></td>
<td><span data-ttu-id="dbf5b-403">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-403">Project 2</span></span></td>
<td><span data-ttu-id="dbf5b-404">1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-404">1</span></span></td>
<td><span data-ttu-id="dbf5b-405">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-405">10001</span></span></td>
<td><span data-ttu-id="dbf5b-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="dbf5b-407">10,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="dbf5b-408">Diário</span><span class="sxs-lookup"><span data-stu-id="dbf5b-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dbf5b-409">Diário</span><span class="sxs-lookup"><span data-stu-id="dbf5b-409">Journal</span></span></th>
<th><span data-ttu-id="dbf5b-410">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="dbf5b-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="dbf5b-411">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="dbf5b-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="dbf5b-412">Versão</span><span class="sxs-lookup"><span data-stu-id="dbf5b-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-413">00003</span><span class="sxs-lookup"><span data-stu-id="dbf5b-413">00003</span></span></td>
<td><span data-ttu-id="dbf5b-414">Diário de cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="dbf5b-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="dbf5b-415">fiscal</span><span class="sxs-lookup"><span data-stu-id="dbf5b-415">Fiscal</span></span></td>
<td><span data-ttu-id="dbf5b-416">2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-416">2017</span></span></td>
<td><span data-ttu-id="dbf5b-417">Período 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-417">Period 1</span></span></td>
<td><span data-ttu-id="dbf5b-418">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="dbf5b-419">Entradas de diário (As entradas de diário para cálculo da taxa de custos indiretos)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dbf5b-420">Data contábil</span><span class="sxs-lookup"><span data-stu-id="dbf5b-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="dbf5b-421">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-421">Cost object</span></span></th>
<th><span data-ttu-id="dbf5b-422">Magnitude</span><span class="sxs-lookup"><span data-stu-id="dbf5b-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-423">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="dbf5b-424">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-424">Proj 1</span></span></td>
<td><span data-ttu-id="dbf5b-425">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="dbf5b-426">3,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-427">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="dbf5b-428">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-428">Proj 2</span></span></td>
<td><span data-ttu-id="dbf5b-429">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="dbf5b-430">1.00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="dbf5b-431">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dbf5b-432">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="dbf5b-433">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-433">Cost element</span></span></th>
<th><span data-ttu-id="dbf5b-434">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-434">Cost behavior</span></span></th>
<th><span data-ttu-id="dbf5b-435">Valor</span><span class="sxs-lookup"><span data-stu-id="dbf5b-435">Amount</span></span></th>
<th><span data-ttu-id="dbf5b-436">Data contábil</span><span class="sxs-lookup"><span data-stu-id="dbf5b-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-437">CC0001</span></span></td>
<td><span data-ttu-id="dbf5b-438">RH</span><span class="sxs-lookup"><span data-stu-id="dbf5b-438">HR</span></span></td>
<td><span data-ttu-id="dbf5b-439">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-439">10001</span></span></td>
<td><span data-ttu-id="dbf5b-440">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-440">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-441">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-441">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-442">-30.00</span></span></td>
<td><span data-ttu-id="dbf5b-443">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-444">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-444">Proj 1</span></span></td>
<td><span data-ttu-id="dbf5b-445">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="dbf5b-446">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-446">10001</span></span></td>
<td><span data-ttu-id="dbf5b-447">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-447">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-448">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-448">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-449">30,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-449">30.00</span></span></td>
<td><span data-ttu-id="dbf5b-450">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-451">CC001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-451">CC001</span></span></td>
<td><span data-ttu-id="dbf5b-452">RH</span><span class="sxs-lookup"><span data-stu-id="dbf5b-452">HR</span></span></td>
<td><span data-ttu-id="dbf5b-453">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-453">10001</span></span></td>
<td><span data-ttu-id="dbf5b-454">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-454">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-455">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-455">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-456">-10.00</span></span></td>
<td><span data-ttu-id="dbf5b-457">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-458">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-458">Proj 2</span></span></td>
<td><span data-ttu-id="dbf5b-459">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="dbf5b-460">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-460">10001</span></span></td>
<td><span data-ttu-id="dbf5b-461">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-461">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-462">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-462">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-463">10,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-463">10.00</span></span></td>
<td><span data-ttu-id="dbf5b-464">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dbf5b-465">Para obter mais informações, consulte [Realizar cálculo de custos indiretos](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="dbf5b-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="dbf5b-466">Etapa 4: Processar o cálculo de alocação de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="dbf5b-467">A alocação é usada para alocar o saldo de um objeto de custo a outros objetos de custo pela aplicação de uma base de alocação.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="dbf5b-468">O Finance and Operations oferece suporte ao método de alocação recíproco.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-468">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="dbf5b-469">No método de alocação recíproco, os serviços mútuos que os objetos de custo auxiliar trocam são totalmente reconhecidos.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="dbf5b-470">O sistema determina automaticamente a ordem correta realizar as alocações.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="dbf5b-471">O saldo de um objeto de custo é alocado por uma base de alocação única.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="dbf5b-472">As alocações entre as dimensões de objetos de custo e os respectivos membros são suportadas.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="dbf5b-473">A ordem de alocação é controlada pela unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="dbf5b-474">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="dbf5b-475">Defina a alocação de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-475">Define the cost allocation</span></span>

<span data-ttu-id="dbf5b-476">Aqui está um exemplo simples que explica como você pode rastrear o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="dbf5b-477">O objeto de custo previsto CC001 HR contribui a vários objetos de custo previsto.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="dbf5b-478">Um membro de dimensão estatística que é chamado de serviços de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dbf5b-479">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-479">Cost object</span></span></th>
<th><span data-ttu-id="dbf5b-480">Serviços de RH</span><span class="sxs-lookup"><span data-stu-id="dbf5b-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-481">CC002</span><span class="sxs-lookup"><span data-stu-id="dbf5b-481">CC002</span></span></td>
<td><span data-ttu-id="dbf5b-482">Finanças</span><span class="sxs-lookup"><span data-stu-id="dbf5b-482">Finance</span></span></td>
<td><span data-ttu-id="dbf5b-483">35</span><span class="sxs-lookup"><span data-stu-id="dbf5b-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-484">CC003</span><span class="sxs-lookup"><span data-stu-id="dbf5b-484">CC003</span></span></td>
<td><span data-ttu-id="dbf5b-485">Montagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-485">Assembly</span></span></td>
<td><span data-ttu-id="dbf5b-486">55</span><span class="sxs-lookup"><span data-stu-id="dbf5b-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-487">CC004</span><span class="sxs-lookup"><span data-stu-id="dbf5b-487">CC004</span></span></td>
<td><span data-ttu-id="dbf5b-488">Embalagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-488">Packaging</span></span></td>
<td><span data-ttu-id="dbf5b-489">10</span><span class="sxs-lookup"><span data-stu-id="dbf5b-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dbf5b-490">O objeto de custo CC002 Finanças contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="dbf5b-491">Um membro de dimensão estatística que é chamado de serviços de Finanças foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dbf5b-492">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-492">Cost object</span></span></th>
<th><span data-ttu-id="dbf5b-493">Serviços financeiros</span><span class="sxs-lookup"><span data-stu-id="dbf5b-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-494">CC003</span><span class="sxs-lookup"><span data-stu-id="dbf5b-494">CC003</span></span></td>
<td><span data-ttu-id="dbf5b-495">Montagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-495">Assembly</span></span></td>
<td><span data-ttu-id="dbf5b-496">65</span><span class="sxs-lookup"><span data-stu-id="dbf5b-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-497">CC004</span><span class="sxs-lookup"><span data-stu-id="dbf5b-497">CC004</span></span></td>
<td><span data-ttu-id="dbf5b-498">Embalagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-498">Packaging</span></span></td>
<td><span data-ttu-id="dbf5b-499">35</span><span class="sxs-lookup"><span data-stu-id="dbf5b-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dbf5b-500">O objeto de custo CC003 Montagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="dbf5b-501">Um membro de dimensão estatística que é chamado de serviços de Montagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dbf5b-502">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-502">Cost object</span></span></th>
<th><span data-ttu-id="dbf5b-503">Serviços de montagem (horas)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-504">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-504">Prod 1</span></span></td>
<td><span data-ttu-id="dbf5b-505">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-505">Product 1</span></span></td>
<td><span data-ttu-id="dbf5b-506">60</span><span class="sxs-lookup"><span data-stu-id="dbf5b-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-507">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-507">Prod 2</span></span></td>
<td><span data-ttu-id="dbf5b-508">Produto 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-508">Product 2</span></span></td>
<td><span data-ttu-id="dbf5b-509">20</span><span class="sxs-lookup"><span data-stu-id="dbf5b-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dbf5b-510">O objeto de custo CC004 Embalagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="dbf5b-511">Um membro de dimensão estatística que é chamado de serviços de Embalagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dbf5b-512">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-512">Cost object</span></span></th>
<th><span data-ttu-id="dbf5b-513">Serviços de embalagem (horas)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-514">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-514">Prod 1</span></span></td>
<td><span data-ttu-id="dbf5b-515">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-515">Product 1</span></span></td>
<td><span data-ttu-id="dbf5b-516">80</span><span class="sxs-lookup"><span data-stu-id="dbf5b-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-517">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-517">Prod 2</span></span></td>
<td><span data-ttu-id="dbf5b-518">Produto 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-518">Product 2</span></span></td>
<td><span data-ttu-id="dbf5b-519">15</span><span class="sxs-lookup"><span data-stu-id="dbf5b-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="dbf5b-520">No Finance and Operations, as medidas estatísticas, como as horas de produção que um produto consome, podem ser derivadas dos dados de origem.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-520">In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="dbf5b-521">Para obter mais informações, consulte [Modelo de provedor de medidas estatísticas](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="dbf5b-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="dbf5b-522">A tabela a seguir mostra o resultado quando os serviços de RH são aplicados como base de alocação para custos totais (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dbf5b-523">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-523">Cost object</span></span></th>
<th><span data-ttu-id="dbf5b-524">Magnitude</span><span class="sxs-lookup"><span data-stu-id="dbf5b-524">Magnitude</span></span></th>
<th><span data-ttu-id="dbf5b-525">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="dbf5b-525">Allocation factor</span></span></th>
<th><span data-ttu-id="dbf5b-526">Valor</span><span class="sxs-lookup"><span data-stu-id="dbf5b-526">Amount</span></span></th>
<th><span data-ttu-id="dbf5b-527">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-528">CC002</span><span class="sxs-lookup"><span data-stu-id="dbf5b-528">CC002</span></span></td>
<td><span data-ttu-id="dbf5b-529">Finanças</span><span class="sxs-lookup"><span data-stu-id="dbf5b-529">Finance</span></span></td>
<td><span data-ttu-id="dbf5b-530">35</span><span class="sxs-lookup"><span data-stu-id="dbf5b-530">35</span></span></td>
<td><span data-ttu-id="dbf5b-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="dbf5b-532">175.00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-532">175.00</span></span></td>
<td><span data-ttu-id="dbf5b-533">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-534">CC003</span><span class="sxs-lookup"><span data-stu-id="dbf5b-534">CC003</span></span></td>
<td><span data-ttu-id="dbf5b-535">Montagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-535">Assembly</span></span></td>
<td><span data-ttu-id="dbf5b-536">55</span><span class="sxs-lookup"><span data-stu-id="dbf5b-536">55</span></span></td>
<td><span data-ttu-id="dbf5b-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="dbf5b-538">275.00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-538">275.00</span></span></td>
<td><span data-ttu-id="dbf5b-539">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-540">CC004</span><span class="sxs-lookup"><span data-stu-id="dbf5b-540">CC004</span></span></td>
<td><span data-ttu-id="dbf5b-541">Embalagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-541">Packaging</span></span></td>
<td><span data-ttu-id="dbf5b-542">10</span><span class="sxs-lookup"><span data-stu-id="dbf5b-542">10</span></span></td>
<td><span data-ttu-id="dbf5b-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="dbf5b-544">50,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-544">50.00</span></span></td>
<td><span data-ttu-id="dbf5b-545">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-546">CC002</span><span class="sxs-lookup"><span data-stu-id="dbf5b-546">CC002</span></span></td>
<td><span data-ttu-id="dbf5b-547">Finanças</span><span class="sxs-lookup"><span data-stu-id="dbf5b-547">Finance</span></span></td>
<td><span data-ttu-id="dbf5b-548">35</span><span class="sxs-lookup"><span data-stu-id="dbf5b-548">35</span></span></td>
<td><span data-ttu-id="dbf5b-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="dbf5b-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="dbf5b-550">436.00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-550">436.00</span></span></td>
<td><span data-ttu-id="dbf5b-551">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-552">CC003</span><span class="sxs-lookup"><span data-stu-id="dbf5b-552">CC003</span></span></td>
<td><span data-ttu-id="dbf5b-553">Montagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-553">Assembly</span></span></td>
<td><span data-ttu-id="dbf5b-554">55</span><span class="sxs-lookup"><span data-stu-id="dbf5b-554">55</span></span></td>
<td><span data-ttu-id="dbf5b-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="dbf5b-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="dbf5b-556">685.14</span><span class="sxs-lookup"><span data-stu-id="dbf5b-556">685.14</span></span></td>
<td><span data-ttu-id="dbf5b-557">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-558">CC004</span><span class="sxs-lookup"><span data-stu-id="dbf5b-558">CC004</span></span></td>
<td><span data-ttu-id="dbf5b-559">Embalagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-559">Packaging</span></span></td>
<td><span data-ttu-id="dbf5b-560">10</span><span class="sxs-lookup"><span data-stu-id="dbf5b-560">10</span></span></td>
<td><span data-ttu-id="dbf5b-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="dbf5b-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="dbf5b-562">124.57</span><span class="sxs-lookup"><span data-stu-id="dbf5b-562">124.57</span></span></td>
<td><span data-ttu-id="dbf5b-563">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dbf5b-564">A tabela a seguir mostra o resultado quando os serviços financeiros são aplicados como base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dbf5b-565">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-565">Cost object</span></span></th>
<th><span data-ttu-id="dbf5b-566">Magnitude</span><span class="sxs-lookup"><span data-stu-id="dbf5b-566">Magnitude</span></span></th>
<th><span data-ttu-id="dbf5b-567">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="dbf5b-567">Allocation factor</span></span></th>
<th><span data-ttu-id="dbf5b-568">Valor</span><span class="sxs-lookup"><span data-stu-id="dbf5b-568">Amount</span></span></th>
<th><span data-ttu-id="dbf5b-569">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-570">CC003</span><span class="sxs-lookup"><span data-stu-id="dbf5b-570">CC003</span></span></td>
<td><span data-ttu-id="dbf5b-571">Montagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-571">Assembly</span></span></td>
<td><span data-ttu-id="dbf5b-572">65</span><span class="sxs-lookup"><span data-stu-id="dbf5b-572">65</span></span></td>
<td><span data-ttu-id="dbf5b-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="dbf5b-574">438.75</span><span class="sxs-lookup"><span data-stu-id="dbf5b-574">438.75</span></span></td>
<td><span data-ttu-id="dbf5b-575">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-576">CC004</span><span class="sxs-lookup"><span data-stu-id="dbf5b-576">CC004</span></span></td>
<td><span data-ttu-id="dbf5b-577">Embalagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-577">Packaging</span></span></td>
<td><span data-ttu-id="dbf5b-578">35</span><span class="sxs-lookup"><span data-stu-id="dbf5b-578">35</span></span></td>
<td><span data-ttu-id="dbf5b-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="dbf5b-580">236.25</span><span class="sxs-lookup"><span data-stu-id="dbf5b-580">236.25</span></span></td>
<td><span data-ttu-id="dbf5b-581">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-582">CC003</span><span class="sxs-lookup"><span data-stu-id="dbf5b-582">CC003</span></span></td>
<td><span data-ttu-id="dbf5b-583">Montagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-583">Assembly</span></span></td>
<td><span data-ttu-id="dbf5b-584">65</span><span class="sxs-lookup"><span data-stu-id="dbf5b-584">65</span></span></td>
<td><span data-ttu-id="dbf5b-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="dbf5b-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="dbf5b-586">5,297.69</span></span></td>
<td><span data-ttu-id="dbf5b-587">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-588">CC004</span><span class="sxs-lookup"><span data-stu-id="dbf5b-588">CC004</span></span></td>
<td><span data-ttu-id="dbf5b-589">Embalagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-589">Packaging</span></span></td>
<td><span data-ttu-id="dbf5b-590">35</span><span class="sxs-lookup"><span data-stu-id="dbf5b-590">35</span></span></td>
<td><span data-ttu-id="dbf5b-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="dbf5b-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="dbf5b-592">2,852.60</span></span></td>
<td><span data-ttu-id="dbf5b-593">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dbf5b-594">A tabela a seguir mostra o resultado quando os serviços de Montagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dbf5b-595">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-595">Cost object</span></span></th>
<th><span data-ttu-id="dbf5b-596">Magnitude</span><span class="sxs-lookup"><span data-stu-id="dbf5b-596">Magnitude</span></span></th>
<th><span data-ttu-id="dbf5b-597">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="dbf5b-597">Allocation factor</span></span></th>
<th><span data-ttu-id="dbf5b-598">Valor</span><span class="sxs-lookup"><span data-stu-id="dbf5b-598">Amount</span></span></th>
<th><span data-ttu-id="dbf5b-599">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-600">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-600">Prod 1</span></span></td>
<td><span data-ttu-id="dbf5b-601">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-601">Product 1</span></span></td>
<td><span data-ttu-id="dbf5b-602">60</span><span class="sxs-lookup"><span data-stu-id="dbf5b-602">60</span></span></td>
<td><span data-ttu-id="dbf5b-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="dbf5b-604">535.31</span><span class="sxs-lookup"><span data-stu-id="dbf5b-604">535.31</span></span></td>
<td><span data-ttu-id="dbf5b-605">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-606">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-606">Prod 2</span></span></td>
<td><span data-ttu-id="dbf5b-607">Produto 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-607">Product 2</span></span></td>
<td><span data-ttu-id="dbf5b-608">20</span><span class="sxs-lookup"><span data-stu-id="dbf5b-608">20</span></span></td>
<td><span data-ttu-id="dbf5b-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="dbf5b-610">178.44</span><span class="sxs-lookup"><span data-stu-id="dbf5b-610">178.44</span></span></td>
<td><span data-ttu-id="dbf5b-611">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-612">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-612">Prod 1</span></span></td>
<td><span data-ttu-id="dbf5b-613">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-613">Product 1</span></span></td>
<td><span data-ttu-id="dbf5b-614">60</span><span class="sxs-lookup"><span data-stu-id="dbf5b-614">60</span></span></td>
<td><span data-ttu-id="dbf5b-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="dbf5b-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="dbf5b-616">4,487.12</span></span></td>
<td><span data-ttu-id="dbf5b-617">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-618">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-618">Prod 2</span></span></td>
<td><span data-ttu-id="dbf5b-619">Produto 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-619">Product 2</span></span></td>
<td><span data-ttu-id="dbf5b-620">20</span><span class="sxs-lookup"><span data-stu-id="dbf5b-620">20</span></span></td>
<td><span data-ttu-id="dbf5b-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="dbf5b-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="dbf5b-622">1,495.71</span></span></td>
<td><span data-ttu-id="dbf5b-623">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dbf5b-624">A tabela a seguir mostra o resultado quando os serviços de Embalagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dbf5b-625">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-625">Cost object</span></span></th>
<th><span data-ttu-id="dbf5b-626">Magnitude</span><span class="sxs-lookup"><span data-stu-id="dbf5b-626">Magnitude</span></span></th>
<th><span data-ttu-id="dbf5b-627">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="dbf5b-627">Allocation factor</span></span></th>
<th><span data-ttu-id="dbf5b-628">Valor</span><span class="sxs-lookup"><span data-stu-id="dbf5b-628">Amount</span></span></th>
<th><span data-ttu-id="dbf5b-629">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-630">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-630">Prod 1</span></span></td>
<td><span data-ttu-id="dbf5b-631">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-631">Product 1</span></span></td>
<td><span data-ttu-id="dbf5b-632">80</span><span class="sxs-lookup"><span data-stu-id="dbf5b-632">80</span></span></td>
<td><span data-ttu-id="dbf5b-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="dbf5b-634">241.05</span><span class="sxs-lookup"><span data-stu-id="dbf5b-634">241.05</span></span></td>
<td><span data-ttu-id="dbf5b-635">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-636">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-636">Prod 2</span></span></td>
<td><span data-ttu-id="dbf5b-637">Produto 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-637">Product 2</span></span></td>
<td><span data-ttu-id="dbf5b-638">15</span><span class="sxs-lookup"><span data-stu-id="dbf5b-638">15</span></span></td>
<td><span data-ttu-id="dbf5b-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="dbf5b-640">45.20</span><span class="sxs-lookup"><span data-stu-id="dbf5b-640">45.20</span></span></td>
<td><span data-ttu-id="dbf5b-641">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-642">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-642">Prod 1</span></span></td>
<td><span data-ttu-id="dbf5b-643">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-643">Product 1</span></span></td>
<td><span data-ttu-id="dbf5b-644">80</span><span class="sxs-lookup"><span data-stu-id="dbf5b-644">80</span></span></td>
<td><span data-ttu-id="dbf5b-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="dbf5b-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="dbf5b-646">2,507.09</span></span></td>
<td><span data-ttu-id="dbf5b-647">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-648">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-648">Prod 2</span></span></td>
<td><span data-ttu-id="dbf5b-649">Produto 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-649">Product 2</span></span></td>
<td><span data-ttu-id="dbf5b-650">15</span><span class="sxs-lookup"><span data-stu-id="dbf5b-650">15</span></span></td>
<td><span data-ttu-id="dbf5b-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="dbf5b-652">470.08</span><span class="sxs-lookup"><span data-stu-id="dbf5b-652">470.08</span></span></td>
<td><span data-ttu-id="dbf5b-653">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="dbf5b-654">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="dbf5b-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dbf5b-655">Diário</span><span class="sxs-lookup"><span data-stu-id="dbf5b-655">Journal</span></span></th>
<th><span data-ttu-id="dbf5b-656">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="dbf5b-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="dbf5b-657">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="dbf5b-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="dbf5b-658">Versão</span><span class="sxs-lookup"><span data-stu-id="dbf5b-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-659">00004</span><span class="sxs-lookup"><span data-stu-id="dbf5b-659">00004</span></span></td>
<td><span data-ttu-id="dbf5b-660">Diário de alocação de custos</span><span class="sxs-lookup"><span data-stu-id="dbf5b-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="dbf5b-661">fiscal</span><span class="sxs-lookup"><span data-stu-id="dbf5b-661">Fiscal</span></span></td>
<td><span data-ttu-id="dbf5b-662">2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-662">2017</span></span></td>
<td><span data-ttu-id="dbf5b-663">Período 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-663">Period 1</span></span></td>
<td><span data-ttu-id="dbf5b-664">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="dbf5b-665">Linhas do diário</span><span class="sxs-lookup"><span data-stu-id="dbf5b-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="dbf5b-666">Data contábil</span><span class="sxs-lookup"><span data-stu-id="dbf5b-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="dbf5b-667">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="dbf5b-668">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-668">Cost element</span></span></th>
<th><span data-ttu-id="dbf5b-669">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-669">Cost behavior</span></span></th>
<th><span data-ttu-id="dbf5b-670">Valor</span><span class="sxs-lookup"><span data-stu-id="dbf5b-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-671">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="dbf5b-672">CC001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-672">CC001</span></span></td>
<td><span data-ttu-id="dbf5b-673">RH</span><span class="sxs-lookup"><span data-stu-id="dbf5b-673">HR</span></span></td>
<td><span data-ttu-id="dbf5b-674">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-674">10001</span></span></td>
<td><span data-ttu-id="dbf5b-675">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-675">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-676">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-676">Fixed cost</span></span></td>
<td><span data-ttu-id="dbf5b-677">500,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-678">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="dbf5b-679">CC001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-679">CC001</span></span></td>
<td><span data-ttu-id="dbf5b-680">RH</span><span class="sxs-lookup"><span data-stu-id="dbf5b-680">HR</span></span></td>
<td><span data-ttu-id="dbf5b-681">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-681">10001</span></span></td>
<td><span data-ttu-id="dbf5b-682">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-682">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-683">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-683">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="dbf5b-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-685">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="dbf5b-686">CC002</span><span class="sxs-lookup"><span data-stu-id="dbf5b-686">CC002</span></span></td>
<td><span data-ttu-id="dbf5b-687">Finanças</span><span class="sxs-lookup"><span data-stu-id="dbf5b-687">Finance</span></span></td>
<td><span data-ttu-id="dbf5b-688">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-688">10001</span></span></td>
<td><span data-ttu-id="dbf5b-689">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-689">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-690">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-690">Fixed cost</span></span></td>
<td><span data-ttu-id="dbf5b-691">675.00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-692">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="dbf5b-693">CC002</span><span class="sxs-lookup"><span data-stu-id="dbf5b-693">CC002</span></span></td>
<td><span data-ttu-id="dbf5b-694">Finanças</span><span class="sxs-lookup"><span data-stu-id="dbf5b-694">Finance</span></span></td>
<td><span data-ttu-id="dbf5b-695">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-695">10001</span></span></td>
<td><span data-ttu-id="dbf5b-696">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-696">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-697">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-697">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="dbf5b-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-699">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="dbf5b-700">CC003</span><span class="sxs-lookup"><span data-stu-id="dbf5b-700">CC003</span></span></td>
<td><span data-ttu-id="dbf5b-701">Montagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-701">Assembly</span></span></td>
<td><span data-ttu-id="dbf5b-702">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-702">10001</span></span></td>
<td><span data-ttu-id="dbf5b-703">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-703">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-704">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-704">Fixed cost</span></span></td>
<td><span data-ttu-id="dbf5b-705">713.75</span><span class="sxs-lookup"><span data-stu-id="dbf5b-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-706">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="dbf5b-707">CC003</span><span class="sxs-lookup"><span data-stu-id="dbf5b-707">CC003</span></span></td>
<td><span data-ttu-id="dbf5b-708">Montagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-708">Assembly</span></span></td>
<td><span data-ttu-id="dbf5b-709">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-709">10001</span></span></td>
<td><span data-ttu-id="dbf5b-710">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-710">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-711">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-711">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="dbf5b-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-713">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="dbf5b-714">CC003</span><span class="sxs-lookup"><span data-stu-id="dbf5b-714">CC003</span></span></td>
<td><span data-ttu-id="dbf5b-715">Embalagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-715">Packaging</span></span></td>
<td><span data-ttu-id="dbf5b-716">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-716">10001</span></span></td>
<td><span data-ttu-id="dbf5b-717">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-717">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-718">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-718">Fixed cost</span></span></td>
<td><span data-ttu-id="dbf5b-719">286.25</span><span class="sxs-lookup"><span data-stu-id="dbf5b-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-720">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="dbf5b-721">CC003</span><span class="sxs-lookup"><span data-stu-id="dbf5b-721">CC003</span></span></td>
<td><span data-ttu-id="dbf5b-722">Embalagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-722">Packaging</span></span></td>
<td><span data-ttu-id="dbf5b-723">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-723">10001</span></span></td>
<td><span data-ttu-id="dbf5b-724">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-724">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-725">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-725">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="dbf5b-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-727">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="dbf5b-728">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-728">Prod 1</span></span></td>
<td><span data-ttu-id="dbf5b-729">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-729">Product 1</span></span></td>
<td><span data-ttu-id="dbf5b-730">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-730">10001</span></span></td>
<td><span data-ttu-id="dbf5b-731">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-731">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-732">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-732">Fixed cost</span></span></td>
<td><span data-ttu-id="dbf5b-733">776.36</span><span class="sxs-lookup"><span data-stu-id="dbf5b-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-734">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="dbf5b-735">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-735">Prod 1</span></span></td>
<td><span data-ttu-id="dbf5b-736">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-736">Product 1</span></span></td>
<td><span data-ttu-id="dbf5b-737">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-737">10001</span></span></td>
<td><span data-ttu-id="dbf5b-738">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-738">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-739">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-739">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="dbf5b-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-741">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="dbf5b-742">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-742">Prod 2</span></span></td>
<td><span data-ttu-id="dbf5b-743">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-743">Product 1</span></span></td>
<td><span data-ttu-id="dbf5b-744">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-744">10001</span></span></td>
<td><span data-ttu-id="dbf5b-745">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-745">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-746">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-746">Fixed cost</span></span></td>
<td><span data-ttu-id="dbf5b-747">223.64</span><span class="sxs-lookup"><span data-stu-id="dbf5b-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-748">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="dbf5b-749">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-749">Prod 2</span></span></td>
<td><span data-ttu-id="dbf5b-750">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-750">Product 1</span></span></td>
<td><span data-ttu-id="dbf5b-751">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-751">10001</span></span></td>
<td><span data-ttu-id="dbf5b-752">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-752">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-753">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-753">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="dbf5b-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="dbf5b-755">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="dbf5b-756">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="dbf5b-757">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-757">Cost element</span></span></th>
<th><span data-ttu-id="dbf5b-758">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-758">Cost behavior</span></span></th>
<th><span data-ttu-id="dbf5b-759">Valor</span><span class="sxs-lookup"><span data-stu-id="dbf5b-759">Amount</span></span></th>
<th><span data-ttu-id="dbf5b-760">Data contábil</span><span class="sxs-lookup"><span data-stu-id="dbf5b-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="dbf5b-761">CC001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-761">CC001</span></span></td>
<td><span data-ttu-id="dbf5b-762">RH</span><span class="sxs-lookup"><span data-stu-id="dbf5b-762">HR</span></span></td>
<td><span data-ttu-id="dbf5b-763">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-763">10001</span></span></td>
<td><span data-ttu-id="dbf5b-764">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-764">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-765">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-765">Fixed cost</span></span></td>
<td><span data-ttu-id="dbf5b-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-766">-500.00</span></span></td>
<td><span data-ttu-id="dbf5b-767">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-768">CC002</span><span class="sxs-lookup"><span data-stu-id="dbf5b-768">CC002</span></span></td>
<td><span data-ttu-id="dbf5b-769">Finanças</span><span class="sxs-lookup"><span data-stu-id="dbf5b-769">Finance</span></span></td>
<td><span data-ttu-id="dbf5b-770">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-770">10001</span></span></td>
<td><span data-ttu-id="dbf5b-771">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-771">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-772">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-772">Fixed cost</span></span></td>
<td><span data-ttu-id="dbf5b-773">175.00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-773">175.00</span></span></td>
<td><span data-ttu-id="dbf5b-774">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-775">CC003</span><span class="sxs-lookup"><span data-stu-id="dbf5b-775">CC003</span></span></td>
<td><span data-ttu-id="dbf5b-776">Montagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-776">Assembly</span></span></td>
<td><span data-ttu-id="dbf5b-777">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-777">10001</span></span></td>
<td><span data-ttu-id="dbf5b-778">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-778">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-779">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-779">Fixed cost</span></span></td>
<td><span data-ttu-id="dbf5b-780">275.00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-780">275.00</span></span></td>
<td><span data-ttu-id="dbf5b-781">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-782">CC004</span><span class="sxs-lookup"><span data-stu-id="dbf5b-782">CC004</span></span></td>
<td><span data-ttu-id="dbf5b-783">Embalagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-783">Packaging</span></span></td>
<td><span data-ttu-id="dbf5b-784">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-784">10001</span></span></td>
<td><span data-ttu-id="dbf5b-785">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-785">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-786">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-786">Fixed cost</span></span></td>
<td><span data-ttu-id="dbf5b-787">50,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-787">50,00</span></span></td>
<td><span data-ttu-id="dbf5b-788">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-789">CC001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-789">CC001</span></span></td>
<td><span data-ttu-id="dbf5b-790">RH</span><span class="sxs-lookup"><span data-stu-id="dbf5b-790">HR</span></span></td>
<td><span data-ttu-id="dbf5b-791">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-791">10001</span></span></td>
<td><span data-ttu-id="dbf5b-792">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-792">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-793">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-793">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="dbf5b-794">-1,245.71</span></span></td>
<td><span data-ttu-id="dbf5b-795">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-796">CC002</span><span class="sxs-lookup"><span data-stu-id="dbf5b-796">CC002</span></span></td>
<td><span data-ttu-id="dbf5b-797">Finanças</span><span class="sxs-lookup"><span data-stu-id="dbf5b-797">Finance</span></span></td>
<td><span data-ttu-id="dbf5b-798">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-798">10001</span></span></td>
<td><span data-ttu-id="dbf5b-799">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-799">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-800">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-800">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-801">436.00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-801">436.00</span></span></td>
<td><span data-ttu-id="dbf5b-802">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-803">CC003</span><span class="sxs-lookup"><span data-stu-id="dbf5b-803">CC003</span></span></td>
<td><span data-ttu-id="dbf5b-804">Montagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-804">Assembly</span></span></td>
<td><span data-ttu-id="dbf5b-805">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-805">10001</span></span></td>
<td><span data-ttu-id="dbf5b-806">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-806">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-807">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-807">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-808">685.14</span><span class="sxs-lookup"><span data-stu-id="dbf5b-808">685.14</span></span></td>
<td><span data-ttu-id="dbf5b-809">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-810">CC004</span><span class="sxs-lookup"><span data-stu-id="dbf5b-810">CC004</span></span></td>
<td><span data-ttu-id="dbf5b-811">Embalagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-811">Packaging</span></span></td>
<td><span data-ttu-id="dbf5b-812">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-812">10001</span></span></td>
<td><span data-ttu-id="dbf5b-813">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-813">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-814">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-814">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-815">124.57</span><span class="sxs-lookup"><span data-stu-id="dbf5b-815">124.57</span></span></td>
<td><span data-ttu-id="dbf5b-816">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-817">CC002</span><span class="sxs-lookup"><span data-stu-id="dbf5b-817">CC002</span></span></td>
<td><span data-ttu-id="dbf5b-818">Finanças</span><span class="sxs-lookup"><span data-stu-id="dbf5b-818">Finance</span></span></td>
<td><span data-ttu-id="dbf5b-819">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-819">10001</span></span></td>
<td><span data-ttu-id="dbf5b-820">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-820">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-821">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-821">Fixed cost</span></span></td>
<td><span data-ttu-id="dbf5b-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-822">-675.00</span></span></td>
<td><span data-ttu-id="dbf5b-823">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-824">CC003</span><span class="sxs-lookup"><span data-stu-id="dbf5b-824">CC003</span></span></td>
<td><span data-ttu-id="dbf5b-825">Montagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-825">Assembly</span></span></td>
<td><span data-ttu-id="dbf5b-826">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-826">10001</span></span></td>
<td><span data-ttu-id="dbf5b-827">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-827">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-828">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-828">Fixed cost</span></span></td>
<td><span data-ttu-id="dbf5b-829">438.75</span><span class="sxs-lookup"><span data-stu-id="dbf5b-829">438.75</span></span></td>
<td><span data-ttu-id="dbf5b-830">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-831">CC004</span><span class="sxs-lookup"><span data-stu-id="dbf5b-831">CC004</span></span></td>
<td><span data-ttu-id="dbf5b-832">Embalagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-832">Packaging</span></span></td>
<td><span data-ttu-id="dbf5b-833">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-833">10001</span></span></td>
<td><span data-ttu-id="dbf5b-834">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-834">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-835">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-835">Fixed cost</span></span></td>
<td><span data-ttu-id="dbf5b-836">236.25</span><span class="sxs-lookup"><span data-stu-id="dbf5b-836">236.25</span></span></td>
<td><span data-ttu-id="dbf5b-837">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-838">CC002</span><span class="sxs-lookup"><span data-stu-id="dbf5b-838">CC002</span></span></td>
<td><span data-ttu-id="dbf5b-839">Finanças</span><span class="sxs-lookup"><span data-stu-id="dbf5b-839">Finance</span></span></td>
<td><span data-ttu-id="dbf5b-840">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-840">10001</span></span></td>
<td><span data-ttu-id="dbf5b-841">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-841">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-842">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-842">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="dbf5b-843">-8,150.29</span></span></td>
<td><span data-ttu-id="dbf5b-844">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-845">CC003</span><span class="sxs-lookup"><span data-stu-id="dbf5b-845">CC003</span></span></td>
<td><span data-ttu-id="dbf5b-846">Montagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-846">Assembly</span></span></td>
<td><span data-ttu-id="dbf5b-847">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-847">10001</span></span></td>
<td><span data-ttu-id="dbf5b-848">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-848">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-849">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-849">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="dbf5b-850">5,297.69</span></span></td>
<td><span data-ttu-id="dbf5b-851">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-852">CC004</span><span class="sxs-lookup"><span data-stu-id="dbf5b-852">CC004</span></span></td>
<td><span data-ttu-id="dbf5b-853">Embalagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-853">Packaging</span></span></td>
<td><span data-ttu-id="dbf5b-854">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-854">10001</span></span></td>
<td><span data-ttu-id="dbf5b-855">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-855">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-856">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-856">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="dbf5b-857">2,852.60</span></span></td>
<td><span data-ttu-id="dbf5b-858">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-859">CC003</span><span class="sxs-lookup"><span data-stu-id="dbf5b-859">CC003</span></span></td>
<td><span data-ttu-id="dbf5b-860">Montagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-860">Assembly</span></span></td>
<td><span data-ttu-id="dbf5b-861">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-861">10001</span></span></td>
<td><span data-ttu-id="dbf5b-862">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-862">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-863">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-863">Fixed cost</span></span></td>
<td><span data-ttu-id="dbf5b-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="dbf5b-864">-713.75</span></span></td>
<td><span data-ttu-id="dbf5b-865">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-866">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-866">Prod 1</span></span></td>
<td><span data-ttu-id="dbf5b-867">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-867">Product 1</span></span></td>
<td><span data-ttu-id="dbf5b-868">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-868">10001</span></span></td>
<td><span data-ttu-id="dbf5b-869">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-869">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-870">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-870">Fixed cost</span></span></td>
<td><span data-ttu-id="dbf5b-871">535.31</span><span class="sxs-lookup"><span data-stu-id="dbf5b-871">535.31</span></span></td>
<td><span data-ttu-id="dbf5b-872">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-873">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-873">Prod 2</span></span></td>
<td><span data-ttu-id="dbf5b-874">Produto 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-874">Product 2</span></span></td>
<td><span data-ttu-id="dbf5b-875">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-875">10001</span></span></td>
<td><span data-ttu-id="dbf5b-876">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-876">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-877">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-877">Fixed cost</span></span></td>
<td><span data-ttu-id="dbf5b-878">178.44</span><span class="sxs-lookup"><span data-stu-id="dbf5b-878">178.44</span></span></td>
<td><span data-ttu-id="dbf5b-879">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-880">CC003</span><span class="sxs-lookup"><span data-stu-id="dbf5b-880">CC003</span></span></td>
<td><span data-ttu-id="dbf5b-881">Montagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-881">Assembly</span></span></td>
<td><span data-ttu-id="dbf5b-882">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-882">10001</span></span></td>
<td><span data-ttu-id="dbf5b-883">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-883">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-884">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-884">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="dbf5b-885">-5,982.83</span></span></td>
<td><span data-ttu-id="dbf5b-886">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-887">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-887">Prod 1</span></span></td>
<td><span data-ttu-id="dbf5b-888">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-888">Product 1</span></span></td>
<td><span data-ttu-id="dbf5b-889">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-889">10001</span></span></td>
<td><span data-ttu-id="dbf5b-890">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-890">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-891">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-891">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="dbf5b-892">4,487.12</span></span></td>
<td><span data-ttu-id="dbf5b-893">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-894">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-894">Prod 2</span></span></td>
<td><span data-ttu-id="dbf5b-895">Produto 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-895">Product 2</span></span></td>
<td><span data-ttu-id="dbf5b-896">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-896">10001</span></span></td>
<td><span data-ttu-id="dbf5b-897">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-897">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-898">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-898">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="dbf5b-899">1,495.71</span></span></td>
<td><span data-ttu-id="dbf5b-900">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-901">CC003</span><span class="sxs-lookup"><span data-stu-id="dbf5b-901">CC003</span></span></td>
<td><span data-ttu-id="dbf5b-902">Montagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-902">Assembly</span></span></td>
<td><span data-ttu-id="dbf5b-903">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-903">10001</span></span></td>
<td><span data-ttu-id="dbf5b-904">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-904">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-905">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-905">Fixed cost</span></span></td>
<td><span data-ttu-id="dbf5b-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="dbf5b-906">-286.25</span></span></td>
<td><span data-ttu-id="dbf5b-907">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-908">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-908">Prod 1</span></span></td>
<td><span data-ttu-id="dbf5b-909">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-909">Product 1</span></span></td>
<td><span data-ttu-id="dbf5b-910">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-910">10001</span></span></td>
<td><span data-ttu-id="dbf5b-911">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-911">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-912">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-912">Fixed cost</span></span></td>
<td><span data-ttu-id="dbf5b-913">241.05</span><span class="sxs-lookup"><span data-stu-id="dbf5b-913">241.05</span></span></td>
<td><span data-ttu-id="dbf5b-914">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-915">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-915">Prod 2</span></span></td>
<td><span data-ttu-id="dbf5b-916">Produto 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-916">Product 2</span></span></td>
<td><span data-ttu-id="dbf5b-917">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-917">10001</span></span></td>
<td><span data-ttu-id="dbf5b-918">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-918">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-919">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-919">Fixed cost</span></span></td>
<td><span data-ttu-id="dbf5b-920">45.20</span><span class="sxs-lookup"><span data-stu-id="dbf5b-920">45.20</span></span></td>
<td><span data-ttu-id="dbf5b-921">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-922">CC003</span><span class="sxs-lookup"><span data-stu-id="dbf5b-922">CC003</span></span></td>
<td><span data-ttu-id="dbf5b-923">Montagem</span><span class="sxs-lookup"><span data-stu-id="dbf5b-923">Assembly</span></span></td>
<td><span data-ttu-id="dbf5b-924">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-924">10001</span></span></td>
<td><span data-ttu-id="dbf5b-925">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-925">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-926">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-926">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="dbf5b-927">-2,977.17</span></span></td>
<td><span data-ttu-id="dbf5b-928">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-929">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-929">Prod 1</span></span></td>
<td><span data-ttu-id="dbf5b-930">Produto 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-930">Product 1</span></span></td>
<td><span data-ttu-id="dbf5b-931">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-931">10001</span></span></td>
<td><span data-ttu-id="dbf5b-932">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-932">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-933">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-933">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="dbf5b-934">2,507.09</span></span></td>
<td><span data-ttu-id="dbf5b-935">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dbf5b-936">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-936">Prod 2</span></span></td>
<td><span data-ttu-id="dbf5b-937">Produto 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-937">Product 2</span></span></td>
<td><span data-ttu-id="dbf5b-938">10001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-938">10001</span></span></td>
<td><span data-ttu-id="dbf5b-939">eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-939">Electricity</span></span></td>
<td><span data-ttu-id="dbf5b-940">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-940">Variable cost</span></span></td>
<td><span data-ttu-id="dbf5b-941">470.08</span><span class="sxs-lookup"><span data-stu-id="dbf5b-941">470.08</span></span></td>
<td><span data-ttu-id="dbf5b-942">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="dbf5b-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="dbf5b-943">Conclusão</span><span class="sxs-lookup"><span data-stu-id="dbf5b-943">Conclusion</span></span>
<span data-ttu-id="dbf5b-944">Na contabilidade financeira, um custo de 10,000.00 para a eletricidade é lançado para um ID fictício de centro de custos.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="dbf5b-945">Portanto, os contadores de custo saberão que esses custos devem ser alocados.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="dbf5b-946">Na contabilização de custo, os custos fluem nas unidades organizacionais e nos níveis, com base nas políticas e regras que são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="dbf5b-947">Cada custo foi associado a uma base de alocação que fornece a melhor apuração para a alocação de custos.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="dbf5b-948">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="dbf5b-949">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="dbf5b-950">Total</span><span class="sxs-lookup"><span data-stu-id="dbf5b-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="dbf5b-951">CC099</span><span class="sxs-lookup"><span data-stu-id="dbf5b-951">CC099</span></span></th>
<th><span data-ttu-id="dbf5b-952">CC001</span><span class="sxs-lookup"><span data-stu-id="dbf5b-952">CC001</span></span></th>
<th><span data-ttu-id="dbf5b-953">CC002</span><span class="sxs-lookup"><span data-stu-id="dbf5b-953">CC002</span></span></th>
<th><span data-ttu-id="dbf5b-954">CC003</span><span class="sxs-lookup"><span data-stu-id="dbf5b-954">CC003</span></span></th>
<th><span data-ttu-id="dbf5b-955">CC004</span><span class="sxs-lookup"><span data-stu-id="dbf5b-955">CC004</span></span></th>
<th><span data-ttu-id="dbf5b-956">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-956">Proj 1</span></span></th>
<th><span data-ttu-id="dbf5b-957">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-957">Proj 2</span></span></th>
<th><span data-ttu-id="dbf5b-958">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="dbf5b-958">Prod 1</span></span></th>
<th><span data-ttu-id="dbf5b-959">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="dbf5b-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="dbf5b-960">10001 Eletricidade</span><span class="sxs-lookup"><span data-stu-id="dbf5b-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="dbf5b-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="dbf5b-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="dbf5b-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="dbf5b-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="dbf5b-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="dbf5b-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="dbf5b-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="dbf5b-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="dbf5b-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="dbf5b-970">Não classificado</span><span class="sxs-lookup"><span data-stu-id="dbf5b-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-971">0,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="dbf5b-972">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="dbf5b-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-973">0,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-974">0,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-975">0,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-976">0,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-977">0,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-978">776.36</span><span class="sxs-lookup"><span data-stu-id="dbf5b-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-979">223.64</span><span class="sxs-lookup"><span data-stu-id="dbf5b-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="dbf5b-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="dbf5b-981">Custo variável</span><span class="sxs-lookup"><span data-stu-id="dbf5b-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-982">000</span><span class="sxs-lookup"><span data-stu-id="dbf5b-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-983">0,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-984">0,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-985">0,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-986">0,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-987">30,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-988">10,00</span><span class="sxs-lookup"><span data-stu-id="dbf5b-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="dbf5b-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="dbf5b-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="dbf5b-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="dbf5b-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="dbf5b-992">Esse tópico mostra como um elemento de custo principal, 10001 Eletricidade flui pelos objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="dbf5b-993">Portanto, esse custo geral indireto é alocado no nível mais baixo na organização.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="dbf5b-994">Em outras palavras, os objetos de custo no nível mais baixo assumem o custo.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="dbf5b-995">Se você exigir um fluxo visual de custo entre objetos de custo, é possível usar as regras de política de acúmulo de custos para visualizar o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="dbf5b-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="dbf5b-996">Para maiores informações, consulte [Acúmulo de custo](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="dbf5b-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>



