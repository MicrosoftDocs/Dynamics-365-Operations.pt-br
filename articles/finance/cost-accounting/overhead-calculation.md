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
ms.openlocfilehash: 6c045f82f3288dba193721dd80c90e68750af9a7
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176427"
---
# <a name="overhead-calculation"></a><span data-ttu-id="d9c36-103">Cálculo de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="d9c36-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d9c36-104">Este tópico descreve processos comuns para calcular e alocar os custos gerais indiretos.</span><span class="sxs-lookup"><span data-stu-id="d9c36-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="d9c36-105">Definição de termo</span><span class="sxs-lookup"><span data-stu-id="d9c36-105">Term definition</span></span>
---------------

<span data-ttu-id="d9c36-106">Os custos gerais indiretos são aqueles que foram incorridos para realizar um negócio, mas não podem ser diretamente atribuídos a qualquer atividade comercial, produto ou serviço específico.</span><span class="sxs-lookup"><span data-stu-id="d9c36-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="d9c36-107">Os custos gerais indiretos fornecem suporte crítico para geração de atividades produtivas.</span><span class="sxs-lookup"><span data-stu-id="d9c36-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="d9c36-108">Eis alguns exemplos de custos gerais:</span><span class="sxs-lookup"><span data-stu-id="d9c36-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="d9c36-109">Aluguel</span><span class="sxs-lookup"><span data-stu-id="d9c36-109">Rent</span></span>
-   <span data-ttu-id="d9c36-110">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-110">Electricity</span></span>
-   <span data-ttu-id="d9c36-111">Salários administrativos</span><span class="sxs-lookup"><span data-stu-id="d9c36-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="d9c36-112">Visão geral do cálculo de custos gerais indiretos</span><span class="sxs-lookup"><span data-stu-id="d9c36-112">Overhead calculation overview</span></span>
<span data-ttu-id="d9c36-113">O cálculo de custos gerais indiretos executa as políticas de contabilização de custos na ordem correta.</span><span class="sxs-lookup"><span data-stu-id="d9c36-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="d9c36-114">Você pode executar o cálculo de custos gerais indiretos várias vezes para o mesmo período fiscal, se as políticas de contabilidade de custo foram modificadas ou foram detectados erros específicos.</span><span class="sxs-lookup"><span data-stu-id="d9c36-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="d9c36-115">Cada execução do cálculo de custos gerais indiretos é armazenada e recebe um ID exclusivo de versão que permite comparar os cálculos em várias versões.</span><span class="sxs-lookup"><span data-stu-id="d9c36-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="d9c36-116">As entradas de custo que o cálculo de custos indiretos gera recebe uma data contábil.</span><span class="sxs-lookup"><span data-stu-id="d9c36-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="d9c36-117">Essa data contábil corresponde à data final do período fiscal que é usada no cálculo.</span><span class="sxs-lookup"><span data-stu-id="d9c36-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="d9c36-118">A ID exclusiva de versão consiste nos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="d9c36-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="d9c36-119">Tipo de versão</span><span class="sxs-lookup"><span data-stu-id="d9c36-119">Version type</span></span>
-   <span data-ttu-id="d9c36-120">Data e hora</span><span class="sxs-lookup"><span data-stu-id="d9c36-120">Date and time</span></span>
-   <span data-ttu-id="d9c36-121">Razão de contabilização de custos</span><span class="sxs-lookup"><span data-stu-id="d9c36-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="d9c36-122">Ano fiscal</span><span class="sxs-lookup"><span data-stu-id="d9c36-122">Fiscal year</span></span>
-   <span data-ttu-id="d9c36-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="d9c36-123">Fiscal period</span></span>

<span data-ttu-id="d9c36-124">O cálculo de custos gerais indiretos é executado independentemente da versão.</span><span class="sxs-lookup"><span data-stu-id="d9c36-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="d9c36-125">Portanto, você pode calcular a versão de orçamento antes da versão atual.</span><span class="sxs-lookup"><span data-stu-id="d9c36-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="d9c36-126">O cálculo de custos gerais indiretos consiste em quatro etapas, conforme mostrado na ilustração.</span><span class="sxs-lookup"><span data-stu-id="d9c36-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="d9c36-127">Em cada etapa, um cabeçalho de diário é criado com entradas de diário.</span><span class="sxs-lookup"><span data-stu-id="d9c36-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="d9c36-128">Esse cabeçalho de diário mantém dados de entrada para cada etapa de cálculo.</span><span class="sxs-lookup"><span data-stu-id="d9c36-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="d9c36-129">As políticas e regras são aplicadas a cada linha do diário e as entradas de custo são geradas como saídas.</span><span class="sxs-lookup"><span data-stu-id="d9c36-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="d9c36-130">Portanto, você sempre terá rastreabilidade total.</span><span class="sxs-lookup"><span data-stu-id="d9c36-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="d9c36-131">[![Cálculo de custos gerais indiretos](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="d9c36-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="d9c36-132">Calcular e alocar os custos gerais indiretos de Eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="d9c36-133">Na contabilidade financeira, alguns custos, como eletricidade, são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="d9c36-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="d9c36-134">Portanto, a visão administrativa detalhada não é fornecida para a contabilização de custo.</span><span class="sxs-lookup"><span data-stu-id="d9c36-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="d9c36-135">Na contabilização de custo, para fornecer a visão administrativa correta em todas as unidades organizacionais e níveis, os custos devem passar pelas unidades organizacionais.</span><span class="sxs-lookup"><span data-stu-id="d9c36-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="d9c36-136">Este fluxo deve ser baseado em qualquer um registro exato do consumo ou de uma previsão justa.</span><span class="sxs-lookup"><span data-stu-id="d9c36-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="d9c36-137">Na contabilidade, um custo de eletricidade pode ser lançado, conforme mostrado na tabela.</span><span class="sxs-lookup"><span data-stu-id="d9c36-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d9c36-138">Data contábil</span><span class="sxs-lookup"><span data-stu-id="d9c36-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="d9c36-139">Centro de custos</span><span class="sxs-lookup"><span data-stu-id="d9c36-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="d9c36-140">Conta principal</span><span class="sxs-lookup"><span data-stu-id="d9c36-140">Main account</span></span></th>
<th><span data-ttu-id="d9c36-141">Valor na moeda contábil</span><span class="sxs-lookup"><span data-stu-id="d9c36-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-142">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="d9c36-143">CC099</span><span class="sxs-lookup"><span data-stu-id="d9c36-143">CC099</span></span></td>
<td><span data-ttu-id="d9c36-144">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="d9c36-144">Default cost center</span></span></td>
<td><span data-ttu-id="d9c36-145">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-145">10001</span></span></td>
<td><span data-ttu-id="d9c36-146">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-146">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="d9c36-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="d9c36-148">Etapa 1: Processar o cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="d9c36-149">Por padrão, quando as entradas de custo previsto são importadas de dados de origem, elas recebem a classificação de comportamento de custo **Não classificado** na Contabilidade de custos.</span><span class="sxs-lookup"><span data-stu-id="d9c36-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="d9c36-150">Aplicando regras da política de comportamento de custo, é possível reclassificar entradas de custo como **Custo fixo** ou **Custo variável**.</span><span class="sxs-lookup"><span data-stu-id="d9c36-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="d9c36-151">Definir a regra de custo de comportamento</span><span class="sxs-lookup"><span data-stu-id="d9c36-151">Define the cost behavior rule</span></span>

<span data-ttu-id="d9c36-152">Em alguns casos, parte do custo é uma taxa fixa e o custos pendente é baseado no consumo.</span><span class="sxs-lookup"><span data-stu-id="d9c36-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="d9c36-153">Geralmente, as contas de eletricidade correspondem a esta definição.</span><span class="sxs-lookup"><span data-stu-id="d9c36-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="d9c36-154">Após você pagar uma taxa fixa específica, você paga por consumo, por hora de quilowatt (Kwh).</span><span class="sxs-lookup"><span data-stu-id="d9c36-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="d9c36-155">Por exemplo, se a taxa de custo fixa for 1.000.00, veja aqui como a regra de comportamento de custo é definida:</span><span class="sxs-lookup"><span data-stu-id="d9c36-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="d9c36-156">Valor fixo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="d9c36-157">0 &lt;= 1.000,00 = Fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="d9c36-158">1000.01 &lt; N = Variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="d9c36-159">Diário</span><span class="sxs-lookup"><span data-stu-id="d9c36-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d9c36-160">Diário</span><span class="sxs-lookup"><span data-stu-id="d9c36-160">Journal</span></span></th>
<th><span data-ttu-id="d9c36-161">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="d9c36-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="d9c36-162">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="d9c36-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="d9c36-163">Versão</span><span class="sxs-lookup"><span data-stu-id="d9c36-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-164">00001</span><span class="sxs-lookup"><span data-stu-id="d9c36-164">00001</span></span></td>
<td><span data-ttu-id="d9c36-165">Diário de cálculo do comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="d9c36-166">fiscal</span><span class="sxs-lookup"><span data-stu-id="d9c36-166">Fiscal</span></span></td>
<td><span data-ttu-id="d9c36-167">2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-167">2017</span></span></td>
<td><span data-ttu-id="d9c36-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-168">Period 1</span></span></td>
<td><span data-ttu-id="d9c36-169">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="d9c36-170">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="d9c36-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d9c36-171">Data contábil</span><span class="sxs-lookup"><span data-stu-id="d9c36-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="d9c36-172">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d9c36-173">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-173">Cost element</span></span></th>
<th><span data-ttu-id="d9c36-174">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-174">Cost behavior</span></span></th>
<th><span data-ttu-id="d9c36-175">Valor</span><span class="sxs-lookup"><span data-stu-id="d9c36-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-176">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="d9c36-177">CC099</span><span class="sxs-lookup"><span data-stu-id="d9c36-177">CC099</span></span></td>
<td><span data-ttu-id="d9c36-178">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="d9c36-178">Default cost center</span></span></td>
<td><span data-ttu-id="d9c36-179">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-179">10001</span></span></td>
<td><span data-ttu-id="d9c36-180">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-180">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-181">Não classificado</span><span class="sxs-lookup"><span data-stu-id="d9c36-181">Unclassified</span></span></td>
<td><span data-ttu-id="d9c36-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="d9c36-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="d9c36-183">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d9c36-184">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d9c36-185">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-185">Cost element</span></span></th>
<th><span data-ttu-id="d9c36-186">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-186">Cost behavior</span></span></th>
<th><span data-ttu-id="d9c36-187">Valor</span><span class="sxs-lookup"><span data-stu-id="d9c36-187">Amount</span></span></th>
<th><span data-ttu-id="d9c36-188">Data contábil</span><span class="sxs-lookup"><span data-stu-id="d9c36-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-189">CC099</span><span class="sxs-lookup"><span data-stu-id="d9c36-189">CC099</span></span></td>
<td><span data-ttu-id="d9c36-190">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="d9c36-190">Default cost center</span></span></td>
<td><span data-ttu-id="d9c36-191">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-191">10001</span></span></td>
<td><span data-ttu-id="d9c36-192">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-192">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-193">Não classificado</span><span class="sxs-lookup"><span data-stu-id="d9c36-193">Unclassified</span></span></td>
<td><span data-ttu-id="d9c36-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="d9c36-194">10,000.00</span></span></td>
<td><span data-ttu-id="d9c36-195">3 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-196">CC099</span><span class="sxs-lookup"><span data-stu-id="d9c36-196">CC099</span></span></td>
<td><span data-ttu-id="d9c36-197">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="d9c36-197">Default cost center</span></span></td>
<td><span data-ttu-id="d9c36-198">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-198">10001</span></span></td>
<td><span data-ttu-id="d9c36-199">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-199">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-200">Não classificado</span><span class="sxs-lookup"><span data-stu-id="d9c36-200">Unclassified</span></span></td>
<td><span data-ttu-id="d9c36-201">-10.000,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-201">-10,000.00</span></span></td>
<td><span data-ttu-id="d9c36-202">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-203">CC099</span><span class="sxs-lookup"><span data-stu-id="d9c36-203">CC099</span></span></td>
<td><span data-ttu-id="d9c36-204">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="d9c36-204">Default cost center</span></span></td>
<td><span data-ttu-id="d9c36-205">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-205">10001</span></span></td>
<td><span data-ttu-id="d9c36-206">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-206">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-207">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-207">Fixed cost</span></span></td>
<td><span data-ttu-id="d9c36-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-208">1,000.00</span></span></td>
<td><span data-ttu-id="d9c36-209">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-210">CC099</span><span class="sxs-lookup"><span data-stu-id="d9c36-210">CC099</span></span></td>
<td><span data-ttu-id="d9c36-211">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="d9c36-211">Default cost center</span></span></td>
<td><span data-ttu-id="d9c36-212">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-212">10001</span></span></td>
<td><span data-ttu-id="d9c36-213">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-213">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-214">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-214">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="d9c36-215">9,000.00</span></span></td>
<td><span data-ttu-id="d9c36-216">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d9c36-217">Para obter mais informações, consulte [Criar e atribuir uma política de comportamento de custos a uma unidade de controle de custos](tasks/create-assign-cost-behavior-policy-cost-control-unit.md)</span><span class="sxs-lookup"><span data-stu-id="d9c36-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="d9c36-218">Etapa 2: Processar o cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="d9c36-219">A distribuição de custos é usada para redistribuir custo de um objeto de custo a um ou mais outros objetos de custo, aplicando uma base de alocação relevante.</span><span class="sxs-lookup"><span data-stu-id="d9c36-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="d9c36-220">A distribuição de custos e a alocação de custo são diferentes na distribuição de custos, sempre que ocorrer em nível de elemento de custo principal do custo original.</span><span class="sxs-lookup"><span data-stu-id="d9c36-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="d9c36-221">Definir a regra de distribuição de custos</span><span class="sxs-lookup"><span data-stu-id="d9c36-221">Define the cost distribution rule</span></span>

<span data-ttu-id="d9c36-222">Na contabilidade financeira, os custos de eletricidade geralmente são registrados como um valor total.</span><span class="sxs-lookup"><span data-stu-id="d9c36-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="d9c36-223">Na contabilização de custo, esta abordagem não é suficientemente detalhada.</span><span class="sxs-lookup"><span data-stu-id="d9c36-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="d9c36-224">O custo variável deve ser distribuído a objetos de custos individuais com base justa.</span><span class="sxs-lookup"><span data-stu-id="d9c36-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="d9c36-225">A base de alocação mais lógica é o consumo de eletricidade (Kwh).</span><span class="sxs-lookup"><span data-stu-id="d9c36-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="d9c36-226">O membro da dimensão estatística que é chamado Eletricidade é criado e o consumo de eletricidade é registrado.</span><span class="sxs-lookup"><span data-stu-id="d9c36-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="d9c36-227">Por padrão, todos os membros estatísticos da dimensão se tornam disponíveis como bases de alocação.</span><span class="sxs-lookup"><span data-stu-id="d9c36-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d9c36-228">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-228">Cost object</span></span></th>
<th><span data-ttu-id="d9c36-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="d9c36-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-230">CC001</span><span class="sxs-lookup"><span data-stu-id="d9c36-230">CC001</span></span></td>
<td><span data-ttu-id="d9c36-231">RH</span><span class="sxs-lookup"><span data-stu-id="d9c36-231">HR</span></span></td>
<td><span data-ttu-id="d9c36-232">1.000</span><span class="sxs-lookup"><span data-stu-id="d9c36-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-233">CC002</span><span class="sxs-lookup"><span data-stu-id="d9c36-233">CC002</span></span></td>
<td><span data-ttu-id="d9c36-234">Finanças</span><span class="sxs-lookup"><span data-stu-id="d9c36-234">Finance</span></span></td>
<td><span data-ttu-id="d9c36-235">6,000</span><span class="sxs-lookup"><span data-stu-id="d9c36-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-236">CC003</span><span class="sxs-lookup"><span data-stu-id="d9c36-236">CC003</span></span></td>
<td><span data-ttu-id="d9c36-237">Montagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-237">Assembly</span></span></td>
<td><span data-ttu-id="d9c36-238">0</span><span class="sxs-lookup"><span data-stu-id="d9c36-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d9c36-239">A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação para custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="d9c36-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d9c36-240">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-240">Cost object</span></span></th>
<th><span data-ttu-id="d9c36-241">Magnitude</span><span class="sxs-lookup"><span data-stu-id="d9c36-241">Magnitude</span></span></th>
<th><span data-ttu-id="d9c36-242">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="d9c36-242">Allocation factor</span></span></th>
<th><span data-ttu-id="d9c36-243">Valor</span><span class="sxs-lookup"><span data-stu-id="d9c36-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-244">CC001</span><span class="sxs-lookup"><span data-stu-id="d9c36-244">CC001</span></span></td>
<td><span data-ttu-id="d9c36-245">RH</span><span class="sxs-lookup"><span data-stu-id="d9c36-245">HR</span></span></td>
<td><span data-ttu-id="d9c36-246">1.000</span><span class="sxs-lookup"><span data-stu-id="d9c36-246">1,000</span></span></td>
<td><span data-ttu-id="d9c36-247">(1.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="d9c36-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="d9c36-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-249">CC002</span><span class="sxs-lookup"><span data-stu-id="d9c36-249">CC002</span></span></td>
<td><span data-ttu-id="d9c36-250">Finanças</span><span class="sxs-lookup"><span data-stu-id="d9c36-250">Finance</span></span></td>
<td><span data-ttu-id="d9c36-251">6,000</span><span class="sxs-lookup"><span data-stu-id="d9c36-251">6,000</span></span></td>
<td><span data-ttu-id="d9c36-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="d9c36-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="d9c36-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-254">CC003</span><span class="sxs-lookup"><span data-stu-id="d9c36-254">CC003</span></span></td>
<td><span data-ttu-id="d9c36-255">Montagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-255">Assembly</span></span></td>
<td><span data-ttu-id="d9c36-256">0</span><span class="sxs-lookup"><span data-stu-id="d9c36-256">0</span></span></td>
<td><span data-ttu-id="d9c36-257">(0 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="d9c36-258">0,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d9c36-259">Os custos fixos devem ser distribuídos igualmente a objetos de custo individuais que têm a eletricidade consumida.</span><span class="sxs-lookup"><span data-stu-id="d9c36-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="d9c36-260">Você pode obter esse resultado usando o membro estatístico de dimensão de eletricidade em uma base e alocação da fórmula: (Eletricidade &gt; 0,00) A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação de custos variáveis.</span><span class="sxs-lookup"><span data-stu-id="d9c36-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d9c36-261">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-261">Cost object</span></span></th>
<th><span data-ttu-id="d9c36-262">Fórmula</span><span class="sxs-lookup"><span data-stu-id="d9c36-262">Formula</span></span></th>
<th><span data-ttu-id="d9c36-263">Magnitude</span><span class="sxs-lookup"><span data-stu-id="d9c36-263">Magnitude</span></span></th>
<th><span data-ttu-id="d9c36-264">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="d9c36-264">Allocation factor</span></span></th>
<th><span data-ttu-id="d9c36-265">Valor</span><span class="sxs-lookup"><span data-stu-id="d9c36-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-266">CC001</span><span class="sxs-lookup"><span data-stu-id="d9c36-266">CC001</span></span></td>
<td><span data-ttu-id="d9c36-267">RH</span><span class="sxs-lookup"><span data-stu-id="d9c36-267">HR</span></span></td>
<td><span data-ttu-id="d9c36-268">(1.000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="d9c36-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="d9c36-269">1</span><span class="sxs-lookup"><span data-stu-id="d9c36-269">1</span></span></td>
<td><span data-ttu-id="d9c36-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="d9c36-271">500,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-272">CC002</span><span class="sxs-lookup"><span data-stu-id="d9c36-272">CC002</span></span></td>
<td><span data-ttu-id="d9c36-273">Finanças</span><span class="sxs-lookup"><span data-stu-id="d9c36-273">Finance</span></span></td>
<td><span data-ttu-id="d9c36-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="d9c36-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="d9c36-275">1</span><span class="sxs-lookup"><span data-stu-id="d9c36-275">1</span></span></td>
<td><span data-ttu-id="d9c36-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="d9c36-277">500,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-278">CC003</span><span class="sxs-lookup"><span data-stu-id="d9c36-278">CC003</span></span></td>
<td><span data-ttu-id="d9c36-279">Montagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-279">Assembly</span></span></td>
<td><span data-ttu-id="d9c36-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="d9c36-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="d9c36-281">0</span><span class="sxs-lookup"><span data-stu-id="d9c36-281">0</span></span></td>
<td><span data-ttu-id="d9c36-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="d9c36-283">0,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="d9c36-284">Diário</span><span class="sxs-lookup"><span data-stu-id="d9c36-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d9c36-285">Diário</span><span class="sxs-lookup"><span data-stu-id="d9c36-285">Journal</span></span></th>
<th><span data-ttu-id="d9c36-286">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="d9c36-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="d9c36-287">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="d9c36-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="d9c36-288">Versão</span><span class="sxs-lookup"><span data-stu-id="d9c36-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-289">00002</span><span class="sxs-lookup"><span data-stu-id="d9c36-289">00002</span></span></td>
<td><span data-ttu-id="d9c36-290">Diário de cálculo de distribuição de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="d9c36-291">fiscal</span><span class="sxs-lookup"><span data-stu-id="d9c36-291">Fiscal</span></span></td>
<td><span data-ttu-id="d9c36-292">2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-292">2017</span></span></td>
<td><span data-ttu-id="d9c36-293">Período 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-293">Period 1</span></span></td>
<td><span data-ttu-id="d9c36-294">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="d9c36-295">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="d9c36-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d9c36-296">Data contábil</span><span class="sxs-lookup"><span data-stu-id="d9c36-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="d9c36-297">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d9c36-298">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-298">Cost element</span></span></th>
<th><span data-ttu-id="d9c36-299">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-299">Cost behavior</span></span></th>
<th><span data-ttu-id="d9c36-300">Valor</span><span class="sxs-lookup"><span data-stu-id="d9c36-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-301">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="d9c36-302">CC099</span><span class="sxs-lookup"><span data-stu-id="d9c36-302">CC099</span></span></td>
<td><span data-ttu-id="d9c36-303">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="d9c36-303">Default cost center</span></span></td>
<td><span data-ttu-id="d9c36-304">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-304">10001</span></span></td>
<td><span data-ttu-id="d9c36-305">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-305">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-306">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-306">Fixed cost</span></span></td>
<td><span data-ttu-id="d9c36-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-308">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="d9c36-309">CC099</span><span class="sxs-lookup"><span data-stu-id="d9c36-309">CC099</span></span></td>
<td><span data-ttu-id="d9c36-310">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="d9c36-310">Default cost center</span></span></td>
<td><span data-ttu-id="d9c36-311">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-311">10001</span></span></td>
<td><span data-ttu-id="d9c36-312">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-312">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-313">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-313">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="d9c36-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="d9c36-315">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d9c36-316">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d9c36-317">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-317">Cost element</span></span></th>
<th><span data-ttu-id="d9c36-318">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-318">Cost behavior</span></span></th>
<th><span data-ttu-id="d9c36-319">Valor</span><span class="sxs-lookup"><span data-stu-id="d9c36-319">Amount</span></span></th>
<th><span data-ttu-id="d9c36-320">Data contábil</span><span class="sxs-lookup"><span data-stu-id="d9c36-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-321">CC099</span><span class="sxs-lookup"><span data-stu-id="d9c36-321">CC099</span></span></td>
<td><span data-ttu-id="d9c36-322">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="d9c36-322">Default cost center</span></span></td>
<td><span data-ttu-id="d9c36-323">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-323">10001</span></span></td>
<td><span data-ttu-id="d9c36-324">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-324">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-325">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-325">Fixed cost</span></span></td>
<td><span data-ttu-id="d9c36-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-326">-1,000.00</span></span></td>
<td><span data-ttu-id="d9c36-327">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-328">CC001</span><span class="sxs-lookup"><span data-stu-id="d9c36-328">CC001</span></span></td>
<td><span data-ttu-id="d9c36-329">RH</span><span class="sxs-lookup"><span data-stu-id="d9c36-329">HR</span></span></td>
<td><span data-ttu-id="d9c36-330">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-330">10001</span></span></td>
<td><span data-ttu-id="d9c36-331">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-331">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-332">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-332">Fixed cost</span></span></td>
<td><span data-ttu-id="d9c36-333">500,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-333">500.00</span></span></td>
<td><span data-ttu-id="d9c36-334">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-335">CC002</span><span class="sxs-lookup"><span data-stu-id="d9c36-335">CC002</span></span></td>
<td><span data-ttu-id="d9c36-336">Finanças</span><span class="sxs-lookup"><span data-stu-id="d9c36-336">Finance</span></span></td>
<td><span data-ttu-id="d9c36-337">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-337">10001</span></span></td>
<td><span data-ttu-id="d9c36-338">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-338">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-339">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-339">Fixed cost</span></span></td>
<td><span data-ttu-id="d9c36-340">500,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-340">500.00</span></span></td>
<td><span data-ttu-id="d9c36-341">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-342">CC099</span><span class="sxs-lookup"><span data-stu-id="d9c36-342">CC099</span></span></td>
<td><span data-ttu-id="d9c36-343">Centro de custos padrão</span><span class="sxs-lookup"><span data-stu-id="d9c36-343">Default cost center</span></span></td>
<td><span data-ttu-id="d9c36-344">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-344">10001</span></span></td>
<td><span data-ttu-id="d9c36-345">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-345">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-346">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-346">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-347">-9,000.00</span></span></td>
<td><span data-ttu-id="d9c36-348">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-349">CC001</span><span class="sxs-lookup"><span data-stu-id="d9c36-349">CC001</span></span></td>
<td><span data-ttu-id="d9c36-350">RH</span><span class="sxs-lookup"><span data-stu-id="d9c36-350">HR</span></span></td>
<td><span data-ttu-id="d9c36-351">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-351">10001</span></span></td>
<td><span data-ttu-id="d9c36-352">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-352">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-353">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-353">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="d9c36-354">1,285.71</span></span></td>
<td><span data-ttu-id="d9c36-355">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-356">CC002</span><span class="sxs-lookup"><span data-stu-id="d9c36-356">CC002</span></span></td>
<td><span data-ttu-id="d9c36-357">Finanças</span><span class="sxs-lookup"><span data-stu-id="d9c36-357">Finance</span></span></td>
<td><span data-ttu-id="d9c36-358">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-358">10001</span></span></td>
<td><span data-ttu-id="d9c36-359">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-359">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-360">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-360">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="d9c36-361">7,714.29</span></span></td>
<td><span data-ttu-id="d9c36-362">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d9c36-363">Para obter mais informações, consulte [Criar e atribuir uma política de distribuição de custos a uma unidade de controle de custos](tasks/create-assign-cost-distribution-policy-cost-control-unit.md)</span><span class="sxs-lookup"><span data-stu-id="d9c36-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="d9c36-364">Etapa 3: Processar o cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="d9c36-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="d9c36-365">A taxa de custos indiretos é usada para cobrar um ou mais objetos de custos específicos.</span><span class="sxs-lookup"><span data-stu-id="d9c36-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="d9c36-366">O encargo se baseia em uma taxa de custo predeterminada e a magnitude da básica de alocação atribuída.</span><span class="sxs-lookup"><span data-stu-id="d9c36-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="d9c36-367">Defina a taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="d9c36-367">Define the overhead rate</span></span>

<span data-ttu-id="d9c36-368">O objeto de custo CC001 HR contribui para um conjunto de projetos internos.</span><span class="sxs-lookup"><span data-stu-id="d9c36-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="d9c36-369">Um membro de dimensão estatística que é chamado de projetos de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="d9c36-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d9c36-370">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-370">Cost object</span></span></th>
<th><span data-ttu-id="d9c36-371">Horas</span><span class="sxs-lookup"><span data-stu-id="d9c36-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-372">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-372">Proj 1</span></span></td>
<td><span data-ttu-id="d9c36-373">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-373">Project 1</span></span></td>
<td><span data-ttu-id="d9c36-374">3</span><span class="sxs-lookup"><span data-stu-id="d9c36-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-375">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-375">Proj 2</span></span></td>
<td><span data-ttu-id="d9c36-376">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-376">Project 2</span></span></td>
<td><span data-ttu-id="d9c36-377">1</span><span class="sxs-lookup"><span data-stu-id="d9c36-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d9c36-378">Uma taxa de custo predeterminada da contribuição de projetos de custo foi definida.</span><span class="sxs-lookup"><span data-stu-id="d9c36-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d9c36-379">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-379">Cost object</span></span></th>
<th><span data-ttu-id="d9c36-380">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-380">Cost element</span></span></th>
<th><span data-ttu-id="d9c36-381">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-381">Cost behavior</span></span></th>
<th><span data-ttu-id="d9c36-382">Unidades</span><span class="sxs-lookup"><span data-stu-id="d9c36-382">Units</span></span></th>
<th><span data-ttu-id="d9c36-383">Taxa</span><span class="sxs-lookup"><span data-stu-id="d9c36-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-384">CC001</span><span class="sxs-lookup"><span data-stu-id="d9c36-384">CC001</span></span></td>
<td><span data-ttu-id="d9c36-385">RH</span><span class="sxs-lookup"><span data-stu-id="d9c36-385">HR</span></span></td>
<td><span data-ttu-id="d9c36-386">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-386">10001</span></span></td>
<td><span data-ttu-id="d9c36-387">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-387">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-388">1</span><span class="sxs-lookup"><span data-stu-id="d9c36-388">1</span></span></td>
<td><span data-ttu-id="d9c36-389">10</span><span class="sxs-lookup"><span data-stu-id="d9c36-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d9c36-390">A tabela a seguir mostra o resultado quando projetos de RH são aplicados como base de alocação.</span><span class="sxs-lookup"><span data-stu-id="d9c36-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d9c36-391">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-391">Cost object</span></span></th>
<th><span data-ttu-id="d9c36-392">Magnitude</span><span class="sxs-lookup"><span data-stu-id="d9c36-392">Magnitude</span></span></th>
<th><span data-ttu-id="d9c36-393">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-393">Cost element</span></span></th>
<th><span data-ttu-id="d9c36-394">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="d9c36-394">Allocation factor</span></span></th>
<th><span data-ttu-id="d9c36-395">Valor</span><span class="sxs-lookup"><span data-stu-id="d9c36-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-396">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-396">Proj 1</span></span></td>
<td><span data-ttu-id="d9c36-397">Projeto 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-397">Project 1</span></span></td>
<td><span data-ttu-id="d9c36-398">3</span><span class="sxs-lookup"><span data-stu-id="d9c36-398">3</span></span></td>
<td><span data-ttu-id="d9c36-399">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-399">10001</span></span></td>
<td><span data-ttu-id="d9c36-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="d9c36-401">30,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-402">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-402">Proj 2</span></span></td>
<td><span data-ttu-id="d9c36-403">Projeto 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-403">Project 2</span></span></td>
<td><span data-ttu-id="d9c36-404">1</span><span class="sxs-lookup"><span data-stu-id="d9c36-404">1</span></span></td>
<td><span data-ttu-id="d9c36-405">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-405">10001</span></span></td>
<td><span data-ttu-id="d9c36-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="d9c36-407">10,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="d9c36-408">Diário</span><span class="sxs-lookup"><span data-stu-id="d9c36-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d9c36-409">Diário</span><span class="sxs-lookup"><span data-stu-id="d9c36-409">Journal</span></span></th>
<th><span data-ttu-id="d9c36-410">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="d9c36-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="d9c36-411">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="d9c36-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="d9c36-412">Versão</span><span class="sxs-lookup"><span data-stu-id="d9c36-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-413">00003</span><span class="sxs-lookup"><span data-stu-id="d9c36-413">00003</span></span></td>
<td><span data-ttu-id="d9c36-414">Diário de cálculo de taxa de custos indiretos</span><span class="sxs-lookup"><span data-stu-id="d9c36-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="d9c36-415">fiscal</span><span class="sxs-lookup"><span data-stu-id="d9c36-415">Fiscal</span></span></td>
<td><span data-ttu-id="d9c36-416">2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-416">2017</span></span></td>
<td><span data-ttu-id="d9c36-417">Período 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-417">Period 1</span></span></td>
<td><span data-ttu-id="d9c36-418">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="d9c36-419">Entradas de diário (As entradas de diário para cálculo da taxa de custos indiretos)</span><span class="sxs-lookup"><span data-stu-id="d9c36-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d9c36-420">Data contábil</span><span class="sxs-lookup"><span data-stu-id="d9c36-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="d9c36-421">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-421">Cost object</span></span></th>
<th><span data-ttu-id="d9c36-422">Magnitude</span><span class="sxs-lookup"><span data-stu-id="d9c36-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-423">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="d9c36-424">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-424">Proj 1</span></span></td>
<td><span data-ttu-id="d9c36-425">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="d9c36-426">3,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-427">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="d9c36-428">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-428">Proj 2</span></span></td>
<td><span data-ttu-id="d9c36-429">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="d9c36-430">1.00</span><span class="sxs-lookup"><span data-stu-id="d9c36-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="d9c36-431">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d9c36-432">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d9c36-433">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-433">Cost element</span></span></th>
<th><span data-ttu-id="d9c36-434">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-434">Cost behavior</span></span></th>
<th><span data-ttu-id="d9c36-435">Valor</span><span class="sxs-lookup"><span data-stu-id="d9c36-435">Amount</span></span></th>
<th><span data-ttu-id="d9c36-436">Data contábil</span><span class="sxs-lookup"><span data-stu-id="d9c36-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="d9c36-437">CC0001</span></span></td>
<td><span data-ttu-id="d9c36-438">RH</span><span class="sxs-lookup"><span data-stu-id="d9c36-438">HR</span></span></td>
<td><span data-ttu-id="d9c36-439">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-439">10001</span></span></td>
<td><span data-ttu-id="d9c36-440">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-440">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-441">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-441">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-442">-30.00</span></span></td>
<td><span data-ttu-id="d9c36-443">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-444">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-444">Proj 1</span></span></td>
<td><span data-ttu-id="d9c36-445">Projeto interno 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="d9c36-446">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-446">10001</span></span></td>
<td><span data-ttu-id="d9c36-447">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-447">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-448">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-448">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-449">30,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-449">30.00</span></span></td>
<td><span data-ttu-id="d9c36-450">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-451">CC001</span><span class="sxs-lookup"><span data-stu-id="d9c36-451">CC001</span></span></td>
<td><span data-ttu-id="d9c36-452">RH</span><span class="sxs-lookup"><span data-stu-id="d9c36-452">HR</span></span></td>
<td><span data-ttu-id="d9c36-453">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-453">10001</span></span></td>
<td><span data-ttu-id="d9c36-454">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-454">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-455">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-455">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-456">-10.00</span></span></td>
<td><span data-ttu-id="d9c36-457">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-458">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-458">Proj 2</span></span></td>
<td><span data-ttu-id="d9c36-459">Projeto interno 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="d9c36-460">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-460">10001</span></span></td>
<td><span data-ttu-id="d9c36-461">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-461">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-462">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-462">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-463">10,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-463">10.00</span></span></td>
<td><span data-ttu-id="d9c36-464">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d9c36-465">Para obter mais informações, consulte [Realizar cálculo de custos indiretos](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="d9c36-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="d9c36-466">Etapa 4: Processar o cálculo de alocação de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="d9c36-467">A alocação é usada para alocar o saldo de um objeto de custo a outros objetos de custo pela aplicação de uma base de alocação.</span><span class="sxs-lookup"><span data-stu-id="d9c36-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="d9c36-468">O Finance oferece suporte ao método de alocação recíproco.</span><span class="sxs-lookup"><span data-stu-id="d9c36-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="d9c36-469">No método de alocação recíproco, os serviços mútuos que os objetos de custo auxiliar trocam são totalmente reconhecidos.</span><span class="sxs-lookup"><span data-stu-id="d9c36-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="d9c36-470">O sistema determina automaticamente a ordem correta realizar as alocações.</span><span class="sxs-lookup"><span data-stu-id="d9c36-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="d9c36-471">O saldo de um objeto de custo é alocado por uma base de alocação única.</span><span class="sxs-lookup"><span data-stu-id="d9c36-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="d9c36-472">As alocações entre as dimensões de objetos de custo e os respectivos membros são suportadas.</span><span class="sxs-lookup"><span data-stu-id="d9c36-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="d9c36-473">A ordem de alocação é controlada pela unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="d9c36-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="d9c36-474">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="d9c36-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="d9c36-475">Defina a alocação de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-475">Define the cost allocation</span></span>

<span data-ttu-id="d9c36-476">Aqui está um exemplo simples que explica como você pode rastrear o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="d9c36-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="d9c36-477">O objeto de custo previsto CC001 HR contribui a vários objetos de custo previsto.</span><span class="sxs-lookup"><span data-stu-id="d9c36-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="d9c36-478">Um membro de dimensão estatística que é chamado de serviços de RH foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="d9c36-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d9c36-479">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-479">Cost object</span></span></th>
<th><span data-ttu-id="d9c36-480">Serviços de RH</span><span class="sxs-lookup"><span data-stu-id="d9c36-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-481">CC002</span><span class="sxs-lookup"><span data-stu-id="d9c36-481">CC002</span></span></td>
<td><span data-ttu-id="d9c36-482">Finanças</span><span class="sxs-lookup"><span data-stu-id="d9c36-482">Finance</span></span></td>
<td><span data-ttu-id="d9c36-483">35</span><span class="sxs-lookup"><span data-stu-id="d9c36-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-484">CC003</span><span class="sxs-lookup"><span data-stu-id="d9c36-484">CC003</span></span></td>
<td><span data-ttu-id="d9c36-485">Montagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-485">Assembly</span></span></td>
<td><span data-ttu-id="d9c36-486">55</span><span class="sxs-lookup"><span data-stu-id="d9c36-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-487">CC004</span><span class="sxs-lookup"><span data-stu-id="d9c36-487">CC004</span></span></td>
<td><span data-ttu-id="d9c36-488">Embalagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-488">Packaging</span></span></td>
<td><span data-ttu-id="d9c36-489">10</span><span class="sxs-lookup"><span data-stu-id="d9c36-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d9c36-490">O objeto de custo CC002 Finanças contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="d9c36-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="d9c36-491">Um membro de dimensão estatística que é chamado de serviços de Finanças foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="d9c36-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d9c36-492">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-492">Cost object</span></span></th>
<th><span data-ttu-id="d9c36-493">Serviços financeiros</span><span class="sxs-lookup"><span data-stu-id="d9c36-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-494">CC003</span><span class="sxs-lookup"><span data-stu-id="d9c36-494">CC003</span></span></td>
<td><span data-ttu-id="d9c36-495">Montagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-495">Assembly</span></span></td>
<td><span data-ttu-id="d9c36-496">65</span><span class="sxs-lookup"><span data-stu-id="d9c36-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-497">CC004</span><span class="sxs-lookup"><span data-stu-id="d9c36-497">CC004</span></span></td>
<td><span data-ttu-id="d9c36-498">Embalagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-498">Packaging</span></span></td>
<td><span data-ttu-id="d9c36-499">35</span><span class="sxs-lookup"><span data-stu-id="d9c36-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d9c36-500">O objeto de custo CC003 Montagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="d9c36-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="d9c36-501">Um membro de dimensão estatística que é chamado de serviços de Montagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="d9c36-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d9c36-502">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-502">Cost object</span></span></th>
<th><span data-ttu-id="d9c36-503">Serviços de montagem (horas)</span><span class="sxs-lookup"><span data-stu-id="d9c36-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-504">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-504">Prod 1</span></span></td>
<td><span data-ttu-id="d9c36-505">Produto 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-505">Product 1</span></span></td>
<td><span data-ttu-id="d9c36-506">60</span><span class="sxs-lookup"><span data-stu-id="d9c36-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-507">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-507">Prod 2</span></span></td>
<td><span data-ttu-id="d9c36-508">Produto 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-508">Product 2</span></span></td>
<td><span data-ttu-id="d9c36-509">20</span><span class="sxs-lookup"><span data-stu-id="d9c36-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d9c36-510">O objeto de custo CC004 Embalagem contribui para vários objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="d9c36-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="d9c36-511">Um membro de dimensão estatística que é chamado de serviços de Embalagem foi criado para medir a magnitude consumida.</span><span class="sxs-lookup"><span data-stu-id="d9c36-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d9c36-512">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-512">Cost object</span></span></th>
<th><span data-ttu-id="d9c36-513">Serviços de embalagem (horas)</span><span class="sxs-lookup"><span data-stu-id="d9c36-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-514">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-514">Prod 1</span></span></td>
<td><span data-ttu-id="d9c36-515">Produto 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-515">Product 1</span></span></td>
<td><span data-ttu-id="d9c36-516">80</span><span class="sxs-lookup"><span data-stu-id="d9c36-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-517">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-517">Prod 2</span></span></td>
<td><span data-ttu-id="d9c36-518">Produto 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-518">Product 2</span></span></td>
<td><span data-ttu-id="d9c36-519">15</span><span class="sxs-lookup"><span data-stu-id="d9c36-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="d9c36-520">Medidas estatísticas, como as horas de produção que um produto consome, podem ser derivadas dos dados de origem.</span><span class="sxs-lookup"><span data-stu-id="d9c36-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="d9c36-521">Para obter mais informações, consulte [Modelo de provedor de medidas estatísticas](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="d9c36-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="d9c36-522">A tabela a seguir mostra o resultado quando os serviços de RH são aplicados como base de alocação para custos totais (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="d9c36-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d9c36-523">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-523">Cost object</span></span></th>
<th><span data-ttu-id="d9c36-524">Magnitude</span><span class="sxs-lookup"><span data-stu-id="d9c36-524">Magnitude</span></span></th>
<th><span data-ttu-id="d9c36-525">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="d9c36-525">Allocation factor</span></span></th>
<th><span data-ttu-id="d9c36-526">Valor</span><span class="sxs-lookup"><span data-stu-id="d9c36-526">Amount</span></span></th>
<th><span data-ttu-id="d9c36-527">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-528">CC002</span><span class="sxs-lookup"><span data-stu-id="d9c36-528">CC002</span></span></td>
<td><span data-ttu-id="d9c36-529">Finanças</span><span class="sxs-lookup"><span data-stu-id="d9c36-529">Finance</span></span></td>
<td><span data-ttu-id="d9c36-530">35</span><span class="sxs-lookup"><span data-stu-id="d9c36-530">35</span></span></td>
<td><span data-ttu-id="d9c36-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="d9c36-532">175.00</span><span class="sxs-lookup"><span data-stu-id="d9c36-532">175.00</span></span></td>
<td><span data-ttu-id="d9c36-533">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-534">CC003</span><span class="sxs-lookup"><span data-stu-id="d9c36-534">CC003</span></span></td>
<td><span data-ttu-id="d9c36-535">Montagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-535">Assembly</span></span></td>
<td><span data-ttu-id="d9c36-536">55</span><span class="sxs-lookup"><span data-stu-id="d9c36-536">55</span></span></td>
<td><span data-ttu-id="d9c36-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="d9c36-538">275.00</span><span class="sxs-lookup"><span data-stu-id="d9c36-538">275.00</span></span></td>
<td><span data-ttu-id="d9c36-539">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-540">CC004</span><span class="sxs-lookup"><span data-stu-id="d9c36-540">CC004</span></span></td>
<td><span data-ttu-id="d9c36-541">Embalagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-541">Packaging</span></span></td>
<td><span data-ttu-id="d9c36-542">10</span><span class="sxs-lookup"><span data-stu-id="d9c36-542">10</span></span></td>
<td><span data-ttu-id="d9c36-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="d9c36-544">50,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-544">50.00</span></span></td>
<td><span data-ttu-id="d9c36-545">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-546">CC002</span><span class="sxs-lookup"><span data-stu-id="d9c36-546">CC002</span></span></td>
<td><span data-ttu-id="d9c36-547">Finanças</span><span class="sxs-lookup"><span data-stu-id="d9c36-547">Finance</span></span></td>
<td><span data-ttu-id="d9c36-548">35</span><span class="sxs-lookup"><span data-stu-id="d9c36-548">35</span></span></td>
<td><span data-ttu-id="d9c36-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="d9c36-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="d9c36-550">436.00</span><span class="sxs-lookup"><span data-stu-id="d9c36-550">436.00</span></span></td>
<td><span data-ttu-id="d9c36-551">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-552">CC003</span><span class="sxs-lookup"><span data-stu-id="d9c36-552">CC003</span></span></td>
<td><span data-ttu-id="d9c36-553">Montagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-553">Assembly</span></span></td>
<td><span data-ttu-id="d9c36-554">55</span><span class="sxs-lookup"><span data-stu-id="d9c36-554">55</span></span></td>
<td><span data-ttu-id="d9c36-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="d9c36-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="d9c36-556">685.14</span><span class="sxs-lookup"><span data-stu-id="d9c36-556">685.14</span></span></td>
<td><span data-ttu-id="d9c36-557">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-558">CC004</span><span class="sxs-lookup"><span data-stu-id="d9c36-558">CC004</span></span></td>
<td><span data-ttu-id="d9c36-559">Embalagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-559">Packaging</span></span></td>
<td><span data-ttu-id="d9c36-560">10</span><span class="sxs-lookup"><span data-stu-id="d9c36-560">10</span></span></td>
<td><span data-ttu-id="d9c36-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="d9c36-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="d9c36-562">124.57</span><span class="sxs-lookup"><span data-stu-id="d9c36-562">124.57</span></span></td>
<td><span data-ttu-id="d9c36-563">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d9c36-564">A tabela a seguir mostra o resultado quando os serviços financeiros são aplicados como base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="d9c36-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d9c36-565">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-565">Cost object</span></span></th>
<th><span data-ttu-id="d9c36-566">Magnitude</span><span class="sxs-lookup"><span data-stu-id="d9c36-566">Magnitude</span></span></th>
<th><span data-ttu-id="d9c36-567">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="d9c36-567">Allocation factor</span></span></th>
<th><span data-ttu-id="d9c36-568">Valor</span><span class="sxs-lookup"><span data-stu-id="d9c36-568">Amount</span></span></th>
<th><span data-ttu-id="d9c36-569">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-570">CC003</span><span class="sxs-lookup"><span data-stu-id="d9c36-570">CC003</span></span></td>
<td><span data-ttu-id="d9c36-571">Montagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-571">Assembly</span></span></td>
<td><span data-ttu-id="d9c36-572">65</span><span class="sxs-lookup"><span data-stu-id="d9c36-572">65</span></span></td>
<td><span data-ttu-id="d9c36-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="d9c36-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="d9c36-574">438.75</span><span class="sxs-lookup"><span data-stu-id="d9c36-574">438.75</span></span></td>
<td><span data-ttu-id="d9c36-575">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-576">CC004</span><span class="sxs-lookup"><span data-stu-id="d9c36-576">CC004</span></span></td>
<td><span data-ttu-id="d9c36-577">Embalagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-577">Packaging</span></span></td>
<td><span data-ttu-id="d9c36-578">35</span><span class="sxs-lookup"><span data-stu-id="d9c36-578">35</span></span></td>
<td><span data-ttu-id="d9c36-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="d9c36-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="d9c36-580">236.25</span><span class="sxs-lookup"><span data-stu-id="d9c36-580">236.25</span></span></td>
<td><span data-ttu-id="d9c36-581">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-582">CC003</span><span class="sxs-lookup"><span data-stu-id="d9c36-582">CC003</span></span></td>
<td><span data-ttu-id="d9c36-583">Montagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-583">Assembly</span></span></td>
<td><span data-ttu-id="d9c36-584">65</span><span class="sxs-lookup"><span data-stu-id="d9c36-584">65</span></span></td>
<td><span data-ttu-id="d9c36-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="d9c36-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="d9c36-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="d9c36-586">5,297.69</span></span></td>
<td><span data-ttu-id="d9c36-587">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-588">CC004</span><span class="sxs-lookup"><span data-stu-id="d9c36-588">CC004</span></span></td>
<td><span data-ttu-id="d9c36-589">Embalagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-589">Packaging</span></span></td>
<td><span data-ttu-id="d9c36-590">35</span><span class="sxs-lookup"><span data-stu-id="d9c36-590">35</span></span></td>
<td><span data-ttu-id="d9c36-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="d9c36-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="d9c36-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="d9c36-592">2,852.60</span></span></td>
<td><span data-ttu-id="d9c36-593">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d9c36-594">A tabela a seguir mostra o resultado quando os serviços de Montagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="d9c36-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d9c36-595">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-595">Cost object</span></span></th>
<th><span data-ttu-id="d9c36-596">Magnitude</span><span class="sxs-lookup"><span data-stu-id="d9c36-596">Magnitude</span></span></th>
<th><span data-ttu-id="d9c36-597">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="d9c36-597">Allocation factor</span></span></th>
<th><span data-ttu-id="d9c36-598">Valor</span><span class="sxs-lookup"><span data-stu-id="d9c36-598">Amount</span></span></th>
<th><span data-ttu-id="d9c36-599">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-600">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-600">Prod 1</span></span></td>
<td><span data-ttu-id="d9c36-601">Produto 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-601">Product 1</span></span></td>
<td><span data-ttu-id="d9c36-602">60</span><span class="sxs-lookup"><span data-stu-id="d9c36-602">60</span></span></td>
<td><span data-ttu-id="d9c36-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="d9c36-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="d9c36-604">535.31</span><span class="sxs-lookup"><span data-stu-id="d9c36-604">535.31</span></span></td>
<td><span data-ttu-id="d9c36-605">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-606">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-606">Prod 2</span></span></td>
<td><span data-ttu-id="d9c36-607">Produto 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-607">Product 2</span></span></td>
<td><span data-ttu-id="d9c36-608">20</span><span class="sxs-lookup"><span data-stu-id="d9c36-608">20</span></span></td>
<td><span data-ttu-id="d9c36-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="d9c36-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="d9c36-610">178.44</span><span class="sxs-lookup"><span data-stu-id="d9c36-610">178.44</span></span></td>
<td><span data-ttu-id="d9c36-611">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-612">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-612">Prod 1</span></span></td>
<td><span data-ttu-id="d9c36-613">Produto 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-613">Product 1</span></span></td>
<td><span data-ttu-id="d9c36-614">60</span><span class="sxs-lookup"><span data-stu-id="d9c36-614">60</span></span></td>
<td><span data-ttu-id="d9c36-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="d9c36-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="d9c36-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="d9c36-616">4,487.12</span></span></td>
<td><span data-ttu-id="d9c36-617">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-618">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-618">Prod 2</span></span></td>
<td><span data-ttu-id="d9c36-619">Produto 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-619">Product 2</span></span></td>
<td><span data-ttu-id="d9c36-620">20</span><span class="sxs-lookup"><span data-stu-id="d9c36-620">20</span></span></td>
<td><span data-ttu-id="d9c36-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="d9c36-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="d9c36-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="d9c36-622">1,495.71</span></span></td>
<td><span data-ttu-id="d9c36-623">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d9c36-624">A tabela a seguir mostra o resultado quando os serviços de Embalagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)</span><span class="sxs-lookup"><span data-stu-id="d9c36-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d9c36-625">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-625">Cost object</span></span></th>
<th><span data-ttu-id="d9c36-626">Magnitude</span><span class="sxs-lookup"><span data-stu-id="d9c36-626">Magnitude</span></span></th>
<th><span data-ttu-id="d9c36-627">Fator de alocação</span><span class="sxs-lookup"><span data-stu-id="d9c36-627">Allocation factor</span></span></th>
<th><span data-ttu-id="d9c36-628">Valor</span><span class="sxs-lookup"><span data-stu-id="d9c36-628">Amount</span></span></th>
<th><span data-ttu-id="d9c36-629">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-630">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-630">Prod 1</span></span></td>
<td><span data-ttu-id="d9c36-631">Produto 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-631">Product 1</span></span></td>
<td><span data-ttu-id="d9c36-632">80</span><span class="sxs-lookup"><span data-stu-id="d9c36-632">80</span></span></td>
<td><span data-ttu-id="d9c36-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="d9c36-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="d9c36-634">241.05</span><span class="sxs-lookup"><span data-stu-id="d9c36-634">241.05</span></span></td>
<td><span data-ttu-id="d9c36-635">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-636">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-636">Prod 2</span></span></td>
<td><span data-ttu-id="d9c36-637">Produto 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-637">Product 2</span></span></td>
<td><span data-ttu-id="d9c36-638">15</span><span class="sxs-lookup"><span data-stu-id="d9c36-638">15</span></span></td>
<td><span data-ttu-id="d9c36-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="d9c36-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="d9c36-640">45.20</span><span class="sxs-lookup"><span data-stu-id="d9c36-640">45.20</span></span></td>
<td><span data-ttu-id="d9c36-641">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-642">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-642">Prod 1</span></span></td>
<td><span data-ttu-id="d9c36-643">Produto 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-643">Product 1</span></span></td>
<td><span data-ttu-id="d9c36-644">80</span><span class="sxs-lookup"><span data-stu-id="d9c36-644">80</span></span></td>
<td><span data-ttu-id="d9c36-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="d9c36-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="d9c36-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="d9c36-646">2,507.09</span></span></td>
<td><span data-ttu-id="d9c36-647">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-648">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-648">Prod 2</span></span></td>
<td><span data-ttu-id="d9c36-649">Produto 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-649">Product 2</span></span></td>
<td><span data-ttu-id="d9c36-650">15</span><span class="sxs-lookup"><span data-stu-id="d9c36-650">15</span></span></td>
<td><span data-ttu-id="d9c36-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="d9c36-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="d9c36-652">470.08</span><span class="sxs-lookup"><span data-stu-id="d9c36-652">470.08</span></span></td>
<td><span data-ttu-id="d9c36-653">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="d9c36-654">Entradas de diário (entradas de diário do saldo de objeto de custo)</span><span class="sxs-lookup"><span data-stu-id="d9c36-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d9c36-655">Diário</span><span class="sxs-lookup"><span data-stu-id="d9c36-655">Journal</span></span></th>
<th><span data-ttu-id="d9c36-656">Tipo de diário</span><span class="sxs-lookup"><span data-stu-id="d9c36-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="d9c36-657">Período do calendário fiscal</span><span class="sxs-lookup"><span data-stu-id="d9c36-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="d9c36-658">Versão</span><span class="sxs-lookup"><span data-stu-id="d9c36-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-659">00004</span><span class="sxs-lookup"><span data-stu-id="d9c36-659">00004</span></span></td>
<td><span data-ttu-id="d9c36-660">Diário de alocação de custos</span><span class="sxs-lookup"><span data-stu-id="d9c36-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="d9c36-661">fiscal</span><span class="sxs-lookup"><span data-stu-id="d9c36-661">Fiscal</span></span></td>
<td><span data-ttu-id="d9c36-662">2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-662">2017</span></span></td>
<td><span data-ttu-id="d9c36-663">Período 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-663">Period 1</span></span></td>
<td><span data-ttu-id="d9c36-664">Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="d9c36-665">Linhas do diário</span><span class="sxs-lookup"><span data-stu-id="d9c36-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d9c36-666">Data contábil</span><span class="sxs-lookup"><span data-stu-id="d9c36-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="d9c36-667">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d9c36-668">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-668">Cost element</span></span></th>
<th><span data-ttu-id="d9c36-669">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-669">Cost behavior</span></span></th>
<th><span data-ttu-id="d9c36-670">Valor</span><span class="sxs-lookup"><span data-stu-id="d9c36-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-671">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="d9c36-672">CC001</span><span class="sxs-lookup"><span data-stu-id="d9c36-672">CC001</span></span></td>
<td><span data-ttu-id="d9c36-673">RH</span><span class="sxs-lookup"><span data-stu-id="d9c36-673">HR</span></span></td>
<td><span data-ttu-id="d9c36-674">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-674">10001</span></span></td>
<td><span data-ttu-id="d9c36-675">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-675">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-676">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-676">Fixed cost</span></span></td>
<td><span data-ttu-id="d9c36-677">500,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-678">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="d9c36-679">CC001</span><span class="sxs-lookup"><span data-stu-id="d9c36-679">CC001</span></span></td>
<td><span data-ttu-id="d9c36-680">RH</span><span class="sxs-lookup"><span data-stu-id="d9c36-680">HR</span></span></td>
<td><span data-ttu-id="d9c36-681">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-681">10001</span></span></td>
<td><span data-ttu-id="d9c36-682">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-682">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-683">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-683">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="d9c36-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-685">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="d9c36-686">CC002</span><span class="sxs-lookup"><span data-stu-id="d9c36-686">CC002</span></span></td>
<td><span data-ttu-id="d9c36-687">Finanças</span><span class="sxs-lookup"><span data-stu-id="d9c36-687">Finance</span></span></td>
<td><span data-ttu-id="d9c36-688">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-688">10001</span></span></td>
<td><span data-ttu-id="d9c36-689">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-689">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-690">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-690">Fixed cost</span></span></td>
<td><span data-ttu-id="d9c36-691">675.00</span><span class="sxs-lookup"><span data-stu-id="d9c36-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-692">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="d9c36-693">CC002</span><span class="sxs-lookup"><span data-stu-id="d9c36-693">CC002</span></span></td>
<td><span data-ttu-id="d9c36-694">Finanças</span><span class="sxs-lookup"><span data-stu-id="d9c36-694">Finance</span></span></td>
<td><span data-ttu-id="d9c36-695">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-695">10001</span></span></td>
<td><span data-ttu-id="d9c36-696">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-696">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-697">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-697">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="d9c36-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-699">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="d9c36-700">CC003</span><span class="sxs-lookup"><span data-stu-id="d9c36-700">CC003</span></span></td>
<td><span data-ttu-id="d9c36-701">Montagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-701">Assembly</span></span></td>
<td><span data-ttu-id="d9c36-702">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-702">10001</span></span></td>
<td><span data-ttu-id="d9c36-703">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-703">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-704">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-704">Fixed cost</span></span></td>
<td><span data-ttu-id="d9c36-705">713.75</span><span class="sxs-lookup"><span data-stu-id="d9c36-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-706">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="d9c36-707">CC003</span><span class="sxs-lookup"><span data-stu-id="d9c36-707">CC003</span></span></td>
<td><span data-ttu-id="d9c36-708">Montagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-708">Assembly</span></span></td>
<td><span data-ttu-id="d9c36-709">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-709">10001</span></span></td>
<td><span data-ttu-id="d9c36-710">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-710">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-711">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-711">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="d9c36-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-713">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="d9c36-714">CC003</span><span class="sxs-lookup"><span data-stu-id="d9c36-714">CC003</span></span></td>
<td><span data-ttu-id="d9c36-715">Embalagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-715">Packaging</span></span></td>
<td><span data-ttu-id="d9c36-716">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-716">10001</span></span></td>
<td><span data-ttu-id="d9c36-717">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-717">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-718">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-718">Fixed cost</span></span></td>
<td><span data-ttu-id="d9c36-719">286.25</span><span class="sxs-lookup"><span data-stu-id="d9c36-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-720">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="d9c36-721">CC003</span><span class="sxs-lookup"><span data-stu-id="d9c36-721">CC003</span></span></td>
<td><span data-ttu-id="d9c36-722">Embalagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-722">Packaging</span></span></td>
<td><span data-ttu-id="d9c36-723">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-723">10001</span></span></td>
<td><span data-ttu-id="d9c36-724">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-724">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-725">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-725">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="d9c36-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-727">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="d9c36-728">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-728">Prod 1</span></span></td>
<td><span data-ttu-id="d9c36-729">Produto 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-729">Product 1</span></span></td>
<td><span data-ttu-id="d9c36-730">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-730">10001</span></span></td>
<td><span data-ttu-id="d9c36-731">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-731">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-732">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-732">Fixed cost</span></span></td>
<td><span data-ttu-id="d9c36-733">776.36</span><span class="sxs-lookup"><span data-stu-id="d9c36-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-734">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="d9c36-735">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-735">Prod 1</span></span></td>
<td><span data-ttu-id="d9c36-736">Produto 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-736">Product 1</span></span></td>
<td><span data-ttu-id="d9c36-737">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-737">10001</span></span></td>
<td><span data-ttu-id="d9c36-738">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-738">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-739">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-739">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="d9c36-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-741">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="d9c36-742">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-742">Prod 2</span></span></td>
<td><span data-ttu-id="d9c36-743">Produto 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-743">Product 1</span></span></td>
<td><span data-ttu-id="d9c36-744">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-744">10001</span></span></td>
<td><span data-ttu-id="d9c36-745">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-745">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-746">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-746">Fixed cost</span></span></td>
<td><span data-ttu-id="d9c36-747">223.64</span><span class="sxs-lookup"><span data-stu-id="d9c36-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-748">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="d9c36-749">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-749">Prod 2</span></span></td>
<td><span data-ttu-id="d9c36-750">Produto 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-750">Product 1</span></span></td>
<td><span data-ttu-id="d9c36-751">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-751">10001</span></span></td>
<td><span data-ttu-id="d9c36-752">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-752">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-753">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-753">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="d9c36-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="d9c36-755">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d9c36-756">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d9c36-757">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-757">Cost element</span></span></th>
<th><span data-ttu-id="d9c36-758">Comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-758">Cost behavior</span></span></th>
<th><span data-ttu-id="d9c36-759">Valor</span><span class="sxs-lookup"><span data-stu-id="d9c36-759">Amount</span></span></th>
<th><span data-ttu-id="d9c36-760">Data contábil</span><span class="sxs-lookup"><span data-stu-id="d9c36-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9c36-761">CC001</span><span class="sxs-lookup"><span data-stu-id="d9c36-761">CC001</span></span></td>
<td><span data-ttu-id="d9c36-762">RH</span><span class="sxs-lookup"><span data-stu-id="d9c36-762">HR</span></span></td>
<td><span data-ttu-id="d9c36-763">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-763">10001</span></span></td>
<td><span data-ttu-id="d9c36-764">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-764">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-765">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-765">Fixed cost</span></span></td>
<td><span data-ttu-id="d9c36-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-766">-500.00</span></span></td>
<td><span data-ttu-id="d9c36-767">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-768">CC002</span><span class="sxs-lookup"><span data-stu-id="d9c36-768">CC002</span></span></td>
<td><span data-ttu-id="d9c36-769">Finanças</span><span class="sxs-lookup"><span data-stu-id="d9c36-769">Finance</span></span></td>
<td><span data-ttu-id="d9c36-770">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-770">10001</span></span></td>
<td><span data-ttu-id="d9c36-771">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-771">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-772">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-772">Fixed cost</span></span></td>
<td><span data-ttu-id="d9c36-773">175.00</span><span class="sxs-lookup"><span data-stu-id="d9c36-773">175.00</span></span></td>
<td><span data-ttu-id="d9c36-774">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-775">CC003</span><span class="sxs-lookup"><span data-stu-id="d9c36-775">CC003</span></span></td>
<td><span data-ttu-id="d9c36-776">Montagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-776">Assembly</span></span></td>
<td><span data-ttu-id="d9c36-777">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-777">10001</span></span></td>
<td><span data-ttu-id="d9c36-778">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-778">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-779">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-779">Fixed cost</span></span></td>
<td><span data-ttu-id="d9c36-780">275.00</span><span class="sxs-lookup"><span data-stu-id="d9c36-780">275.00</span></span></td>
<td><span data-ttu-id="d9c36-781">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-782">CC004</span><span class="sxs-lookup"><span data-stu-id="d9c36-782">CC004</span></span></td>
<td><span data-ttu-id="d9c36-783">Embalagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-783">Packaging</span></span></td>
<td><span data-ttu-id="d9c36-784">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-784">10001</span></span></td>
<td><span data-ttu-id="d9c36-785">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-785">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-786">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-786">Fixed cost</span></span></td>
<td><span data-ttu-id="d9c36-787">50,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-787">50,00</span></span></td>
<td><span data-ttu-id="d9c36-788">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-789">CC001</span><span class="sxs-lookup"><span data-stu-id="d9c36-789">CC001</span></span></td>
<td><span data-ttu-id="d9c36-790">RH</span><span class="sxs-lookup"><span data-stu-id="d9c36-790">HR</span></span></td>
<td><span data-ttu-id="d9c36-791">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-791">10001</span></span></td>
<td><span data-ttu-id="d9c36-792">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-792">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-793">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-793">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="d9c36-794">-1,245.71</span></span></td>
<td><span data-ttu-id="d9c36-795">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-796">CC002</span><span class="sxs-lookup"><span data-stu-id="d9c36-796">CC002</span></span></td>
<td><span data-ttu-id="d9c36-797">Finanças</span><span class="sxs-lookup"><span data-stu-id="d9c36-797">Finance</span></span></td>
<td><span data-ttu-id="d9c36-798">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-798">10001</span></span></td>
<td><span data-ttu-id="d9c36-799">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-799">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-800">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-800">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-801">436.00</span><span class="sxs-lookup"><span data-stu-id="d9c36-801">436.00</span></span></td>
<td><span data-ttu-id="d9c36-802">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-803">CC003</span><span class="sxs-lookup"><span data-stu-id="d9c36-803">CC003</span></span></td>
<td><span data-ttu-id="d9c36-804">Montagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-804">Assembly</span></span></td>
<td><span data-ttu-id="d9c36-805">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-805">10001</span></span></td>
<td><span data-ttu-id="d9c36-806">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-806">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-807">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-807">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-808">685.14</span><span class="sxs-lookup"><span data-stu-id="d9c36-808">685.14</span></span></td>
<td><span data-ttu-id="d9c36-809">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-810">CC004</span><span class="sxs-lookup"><span data-stu-id="d9c36-810">CC004</span></span></td>
<td><span data-ttu-id="d9c36-811">Embalagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-811">Packaging</span></span></td>
<td><span data-ttu-id="d9c36-812">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-812">10001</span></span></td>
<td><span data-ttu-id="d9c36-813">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-813">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-814">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-814">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-815">124.57</span><span class="sxs-lookup"><span data-stu-id="d9c36-815">124.57</span></span></td>
<td><span data-ttu-id="d9c36-816">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-817">CC002</span><span class="sxs-lookup"><span data-stu-id="d9c36-817">CC002</span></span></td>
<td><span data-ttu-id="d9c36-818">Finanças</span><span class="sxs-lookup"><span data-stu-id="d9c36-818">Finance</span></span></td>
<td><span data-ttu-id="d9c36-819">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-819">10001</span></span></td>
<td><span data-ttu-id="d9c36-820">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-820">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-821">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-821">Fixed cost</span></span></td>
<td><span data-ttu-id="d9c36-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-822">-675.00</span></span></td>
<td><span data-ttu-id="d9c36-823">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-824">CC003</span><span class="sxs-lookup"><span data-stu-id="d9c36-824">CC003</span></span></td>
<td><span data-ttu-id="d9c36-825">Montagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-825">Assembly</span></span></td>
<td><span data-ttu-id="d9c36-826">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-826">10001</span></span></td>
<td><span data-ttu-id="d9c36-827">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-827">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-828">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-828">Fixed cost</span></span></td>
<td><span data-ttu-id="d9c36-829">438.75</span><span class="sxs-lookup"><span data-stu-id="d9c36-829">438.75</span></span></td>
<td><span data-ttu-id="d9c36-830">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-831">CC004</span><span class="sxs-lookup"><span data-stu-id="d9c36-831">CC004</span></span></td>
<td><span data-ttu-id="d9c36-832">Embalagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-832">Packaging</span></span></td>
<td><span data-ttu-id="d9c36-833">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-833">10001</span></span></td>
<td><span data-ttu-id="d9c36-834">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-834">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-835">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-835">Fixed cost</span></span></td>
<td><span data-ttu-id="d9c36-836">236.25</span><span class="sxs-lookup"><span data-stu-id="d9c36-836">236.25</span></span></td>
<td><span data-ttu-id="d9c36-837">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-838">CC002</span><span class="sxs-lookup"><span data-stu-id="d9c36-838">CC002</span></span></td>
<td><span data-ttu-id="d9c36-839">Finanças</span><span class="sxs-lookup"><span data-stu-id="d9c36-839">Finance</span></span></td>
<td><span data-ttu-id="d9c36-840">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-840">10001</span></span></td>
<td><span data-ttu-id="d9c36-841">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-841">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-842">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-842">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="d9c36-843">-8,150.29</span></span></td>
<td><span data-ttu-id="d9c36-844">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-845">CC003</span><span class="sxs-lookup"><span data-stu-id="d9c36-845">CC003</span></span></td>
<td><span data-ttu-id="d9c36-846">Montagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-846">Assembly</span></span></td>
<td><span data-ttu-id="d9c36-847">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-847">10001</span></span></td>
<td><span data-ttu-id="d9c36-848">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-848">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-849">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-849">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="d9c36-850">5,297.69</span></span></td>
<td><span data-ttu-id="d9c36-851">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-852">CC004</span><span class="sxs-lookup"><span data-stu-id="d9c36-852">CC004</span></span></td>
<td><span data-ttu-id="d9c36-853">Embalagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-853">Packaging</span></span></td>
<td><span data-ttu-id="d9c36-854">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-854">10001</span></span></td>
<td><span data-ttu-id="d9c36-855">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-855">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-856">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-856">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="d9c36-857">2,852.60</span></span></td>
<td><span data-ttu-id="d9c36-858">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-859">CC003</span><span class="sxs-lookup"><span data-stu-id="d9c36-859">CC003</span></span></td>
<td><span data-ttu-id="d9c36-860">Montagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-860">Assembly</span></span></td>
<td><span data-ttu-id="d9c36-861">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-861">10001</span></span></td>
<td><span data-ttu-id="d9c36-862">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-862">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-863">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-863">Fixed cost</span></span></td>
<td><span data-ttu-id="d9c36-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="d9c36-864">-713.75</span></span></td>
<td><span data-ttu-id="d9c36-865">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-866">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-866">Prod 1</span></span></td>
<td><span data-ttu-id="d9c36-867">Produto 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-867">Product 1</span></span></td>
<td><span data-ttu-id="d9c36-868">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-868">10001</span></span></td>
<td><span data-ttu-id="d9c36-869">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-869">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-870">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-870">Fixed cost</span></span></td>
<td><span data-ttu-id="d9c36-871">535.31</span><span class="sxs-lookup"><span data-stu-id="d9c36-871">535.31</span></span></td>
<td><span data-ttu-id="d9c36-872">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-873">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-873">Prod 2</span></span></td>
<td><span data-ttu-id="d9c36-874">Produto 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-874">Product 2</span></span></td>
<td><span data-ttu-id="d9c36-875">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-875">10001</span></span></td>
<td><span data-ttu-id="d9c36-876">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-876">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-877">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-877">Fixed cost</span></span></td>
<td><span data-ttu-id="d9c36-878">178.44</span><span class="sxs-lookup"><span data-stu-id="d9c36-878">178.44</span></span></td>
<td><span data-ttu-id="d9c36-879">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-880">CC003</span><span class="sxs-lookup"><span data-stu-id="d9c36-880">CC003</span></span></td>
<td><span data-ttu-id="d9c36-881">Montagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-881">Assembly</span></span></td>
<td><span data-ttu-id="d9c36-882">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-882">10001</span></span></td>
<td><span data-ttu-id="d9c36-883">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-883">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-884">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-884">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="d9c36-885">-5,982.83</span></span></td>
<td><span data-ttu-id="d9c36-886">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-887">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-887">Prod 1</span></span></td>
<td><span data-ttu-id="d9c36-888">Produto 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-888">Product 1</span></span></td>
<td><span data-ttu-id="d9c36-889">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-889">10001</span></span></td>
<td><span data-ttu-id="d9c36-890">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-890">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-891">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-891">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="d9c36-892">4,487.12</span></span></td>
<td><span data-ttu-id="d9c36-893">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-894">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-894">Prod 2</span></span></td>
<td><span data-ttu-id="d9c36-895">Produto 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-895">Product 2</span></span></td>
<td><span data-ttu-id="d9c36-896">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-896">10001</span></span></td>
<td><span data-ttu-id="d9c36-897">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-897">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-898">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-898">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="d9c36-899">1,495.71</span></span></td>
<td><span data-ttu-id="d9c36-900">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-901">CC003</span><span class="sxs-lookup"><span data-stu-id="d9c36-901">CC003</span></span></td>
<td><span data-ttu-id="d9c36-902">Montagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-902">Assembly</span></span></td>
<td><span data-ttu-id="d9c36-903">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-903">10001</span></span></td>
<td><span data-ttu-id="d9c36-904">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-904">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-905">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-905">Fixed cost</span></span></td>
<td><span data-ttu-id="d9c36-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="d9c36-906">-286.25</span></span></td>
<td><span data-ttu-id="d9c36-907">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-908">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-908">Prod 1</span></span></td>
<td><span data-ttu-id="d9c36-909">Produto 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-909">Product 1</span></span></td>
<td><span data-ttu-id="d9c36-910">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-910">10001</span></span></td>
<td><span data-ttu-id="d9c36-911">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-911">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-912">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-912">Fixed cost</span></span></td>
<td><span data-ttu-id="d9c36-913">241.05</span><span class="sxs-lookup"><span data-stu-id="d9c36-913">241.05</span></span></td>
<td><span data-ttu-id="d9c36-914">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-915">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-915">Prod 2</span></span></td>
<td><span data-ttu-id="d9c36-916">Produto 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-916">Product 2</span></span></td>
<td><span data-ttu-id="d9c36-917">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-917">10001</span></span></td>
<td><span data-ttu-id="d9c36-918">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-918">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-919">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-919">Fixed cost</span></span></td>
<td><span data-ttu-id="d9c36-920">45.20</span><span class="sxs-lookup"><span data-stu-id="d9c36-920">45.20</span></span></td>
<td><span data-ttu-id="d9c36-921">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-922">CC003</span><span class="sxs-lookup"><span data-stu-id="d9c36-922">CC003</span></span></td>
<td><span data-ttu-id="d9c36-923">Montagem</span><span class="sxs-lookup"><span data-stu-id="d9c36-923">Assembly</span></span></td>
<td><span data-ttu-id="d9c36-924">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-924">10001</span></span></td>
<td><span data-ttu-id="d9c36-925">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-925">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-926">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-926">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="d9c36-927">-2,977.17</span></span></td>
<td><span data-ttu-id="d9c36-928">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-929">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-929">Prod 1</span></span></td>
<td><span data-ttu-id="d9c36-930">Produto 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-930">Product 1</span></span></td>
<td><span data-ttu-id="d9c36-931">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-931">10001</span></span></td>
<td><span data-ttu-id="d9c36-932">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-932">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-933">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-933">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="d9c36-934">2,507.09</span></span></td>
<td><span data-ttu-id="d9c36-935">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d9c36-936">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-936">Prod 2</span></span></td>
<td><span data-ttu-id="d9c36-937">Produto 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-937">Product 2</span></span></td>
<td><span data-ttu-id="d9c36-938">10001</span><span class="sxs-lookup"><span data-stu-id="d9c36-938">10001</span></span></td>
<td><span data-ttu-id="d9c36-939">eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-939">Electricity</span></span></td>
<td><span data-ttu-id="d9c36-940">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-940">Variable cost</span></span></td>
<td><span data-ttu-id="d9c36-941">470.08</span><span class="sxs-lookup"><span data-stu-id="d9c36-941">470.08</span></span></td>
<td><span data-ttu-id="d9c36-942">31 de janeiro, 2017</span><span class="sxs-lookup"><span data-stu-id="d9c36-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="d9c36-943">Conclusão</span><span class="sxs-lookup"><span data-stu-id="d9c36-943">Conclusion</span></span>
<span data-ttu-id="d9c36-944">Na contabilidade financeira, um custo de 10,000.00 para a eletricidade é lançado para um ID fictício de centro de custos.</span><span class="sxs-lookup"><span data-stu-id="d9c36-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="d9c36-945">Portanto, os contadores de custo saberão que esses custos devem ser alocados.</span><span class="sxs-lookup"><span data-stu-id="d9c36-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="d9c36-946">Na contabilização de custo, os custos fluem nas unidades organizacionais e nos níveis, com base nas políticas e regras que são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="d9c36-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="d9c36-947">Cada custo foi associado a uma base de alocação que fornece a melhor apuração para a alocação de custos.</span><span class="sxs-lookup"><span data-stu-id="d9c36-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="d9c36-948">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="d9c36-949">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="d9c36-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="d9c36-950">Total</span><span class="sxs-lookup"><span data-stu-id="d9c36-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="d9c36-951">CC099</span><span class="sxs-lookup"><span data-stu-id="d9c36-951">CC099</span></span></th>
<th><span data-ttu-id="d9c36-952">CC001</span><span class="sxs-lookup"><span data-stu-id="d9c36-952">CC001</span></span></th>
<th><span data-ttu-id="d9c36-953">CC002</span><span class="sxs-lookup"><span data-stu-id="d9c36-953">CC002</span></span></th>
<th><span data-ttu-id="d9c36-954">CC003</span><span class="sxs-lookup"><span data-stu-id="d9c36-954">CC003</span></span></th>
<th><span data-ttu-id="d9c36-955">CC004</span><span class="sxs-lookup"><span data-stu-id="d9c36-955">CC004</span></span></th>
<th><span data-ttu-id="d9c36-956">Proj. 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-956">Proj 1</span></span></th>
<th><span data-ttu-id="d9c36-957">Proj. 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-957">Proj 2</span></span></th>
<th><span data-ttu-id="d9c36-958">Prod. 1</span><span class="sxs-lookup"><span data-stu-id="d9c36-958">Prod 1</span></span></th>
<th><span data-ttu-id="d9c36-959">Prod. 2</span><span class="sxs-lookup"><span data-stu-id="d9c36-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="d9c36-960">10001 Eletricidade</span><span class="sxs-lookup"><span data-stu-id="d9c36-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="d9c36-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="d9c36-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="d9c36-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="d9c36-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="d9c36-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="d9c36-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="d9c36-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="d9c36-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="d9c36-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="d9c36-970">Não classificado</span><span class="sxs-lookup"><span data-stu-id="d9c36-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-971">0,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="d9c36-972">Custo fixo</span><span class="sxs-lookup"><span data-stu-id="d9c36-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-973">0,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-974">0,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-975">0,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-976">0,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-977">0,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-978">776.36</span><span class="sxs-lookup"><span data-stu-id="d9c36-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-979">223.64</span><span class="sxs-lookup"><span data-stu-id="d9c36-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="d9c36-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="d9c36-981">Custo variável</span><span class="sxs-lookup"><span data-stu-id="d9c36-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-982">000</span><span class="sxs-lookup"><span data-stu-id="d9c36-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-983">0,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-984">0,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-985">0,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-986">0,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-987">30,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-988">10,00</span><span class="sxs-lookup"><span data-stu-id="d9c36-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="d9c36-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="d9c36-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d9c36-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="d9c36-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="d9c36-992">Esse tópico mostra como um elemento de custo principal, 10001 Eletricidade flui pelos objetos de custo.</span><span class="sxs-lookup"><span data-stu-id="d9c36-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="d9c36-993">Portanto, esse custo geral indireto é alocado no nível mais baixo na organização.</span><span class="sxs-lookup"><span data-stu-id="d9c36-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="d9c36-994">Em outras palavras, os objetos de custo no nível mais baixo assumem o custo.</span><span class="sxs-lookup"><span data-stu-id="d9c36-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="d9c36-995">Se você exigir um fluxo visual de custo entre objetos de custo, é possível usar as regras de política de acúmulo de custos para visualizar o fluxo de custo.</span><span class="sxs-lookup"><span data-stu-id="d9c36-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="d9c36-996">Para maiores informações, consulte [Acúmulo de custo](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="d9c36-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>



