---
title: "Visão geral do gerenciamento de qualidade"
description: "Este tópico descreve como você pode usar o gerenciamento de qualidade no Microsoft Dynamics 365 for Finance and Operations para ajudar a melhorar a qualidade do produto na sua cadeia de suprimentos."
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, Operations
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c8961d1c62167192fcf32d17c2941b8813ea0629
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="quality-management-overview"></a><span data-ttu-id="8c781-103">Visão geral do gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="8c781-103">Quality management overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="8c781-104">Este tópico descreve como você pode usar o gerenciamento de qualidade no Microsoft Dynamics 365 for Finance and Operations para ajudar a melhorar a qualidade do produto na sua cadeia de suprimentos.</span><span class="sxs-lookup"><span data-stu-id="8c781-104">This topic describes how you can use quality management in Microsoft Dynamics 365 for Finance and Operations to help improve product quality within your supply chain.</span></span>

<span data-ttu-id="8c781-105">O gerenciamento de qualidade pode ajudar a gerenciar o tempo de resposta ao lidar com produtos fora de conformidade, independentemente do ponto de origem.</span><span class="sxs-lookup"><span data-stu-id="8c781-105">Quality management can help you manage turnaround times when you handle nonconforming products, regardless of their point of origin.</span></span> <span data-ttu-id="8c781-106">Como os tipos de diagnóstico são vinculados ao relatório de correção, o Microsoft Dynamics 365 for Finance and Operations pode planejar tarefas para corrigir as saídas e impedir a recorrência.</span><span class="sxs-lookup"><span data-stu-id="8c781-106">Because diagnostic types are linked to correction reporting, Microsoft Dynamics 365 for Finance and Operations can schedule tasks to correct problems and prevent them from recurring.</span></span>

<span data-ttu-id="8c781-107">Além da funcionalidade para gerenciar a não conformidade, o gerenciamento de qualidade inclui a função de rastrear saídas por tipo de problema (até mesmo problemas internos), e para identificar soluções como a curto prazo ou a longo prazo.</span><span class="sxs-lookup"><span data-stu-id="8c781-107">In addition to functionality for managing nonconformance, quality management includes functionality for tracking issues by problem type (even internal problems), and for identifying solutions as short-term or long-term.</span></span> <span data-ttu-id="8c781-108">As estatísticas sobre os principais indicadores de desempenho (KPIs) fornecem ideias sobre o histórico de saídas anteriores de não conformidade e as soluções que foram usadas para corrigi-los.</span><span class="sxs-lookup"><span data-stu-id="8c781-108">Statistics about key performance indicators (KPIs) provide insight into the history of previous nonconformance issues and the solutions that were used to correct them.</span></span> <span data-ttu-id="8c781-109">Você pode usar dados históricos para revisar a eficácia das medidas de qualidade anteriores e determinar as medidas apropriadas a serem usadas no futuro.</span><span class="sxs-lookup"><span data-stu-id="8c781-109">You can use historical data to review the effectiveness of previous quality measures and determine appropriate measures to use in the future.</span></span>

<span data-ttu-id="8c781-110">Ao configurar uma associação de qualidade, o Finance and Operations pode gerar ordens de qualidade para vários processos comerciais, eventos, e condições.</span><span class="sxs-lookup"><span data-stu-id="8c781-110">When you set up a quality association, Finance and Operations can generate quality orders for various business processes, events, and conditions.</span></span> <span data-ttu-id="8c781-111">A associação de qualidade pode cobrir item específico, um grupo específico de itens ou todos os itens.</span><span class="sxs-lookup"><span data-stu-id="8c781-111">The quality association can cover a specific item, a specific group of items, or all items.</span></span>

## <a name="examples-of-the-use-of-quality-management"></a><span data-ttu-id="8c781-112">Exemplo de utilização do gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="8c781-112">Examples of the use of quality management</span></span>
<span data-ttu-id="8c781-113">O gerenciamento de qualidade é flexível e pode ser implementado de várias maneiras para atender aos requisitos de níveis específicos das operações da cadeia de suprimento.</span><span class="sxs-lookup"><span data-stu-id="8c781-113">Quality management is flexible and can be implemented in various ways to meet the requirements of specific levels of supply chain operations.</span></span> <span data-ttu-id="8c781-114">Os exemplos a seguir ilustram as possíveis aplicações destes recursos:</span><span class="sxs-lookup"><span data-stu-id="8c781-114">The following examples illustrate possible uses of these features:</span></span>

-   <span data-ttu-id="8c781-115">Iniciar automaticamente um processo de controle de qualidade com base em critérios pré-definidos (após o registro do depósito de uma ordem de compra de um fornecedor específico).</span><span class="sxs-lookup"><span data-stu-id="8c781-115">Automatically start a quality control process, based on predefined criteria (upon warehouse registration of a purchase order from a specific vendor).</span></span>
-   <span data-ttu-id="8c781-116">Bloquear o estoque durante a inspeção para evitar que o estoque não aprovado seja utilizado (bloqueio total das quantidades da ordem de compra).</span><span class="sxs-lookup"><span data-stu-id="8c781-116">Block inventory during inspection to prevent non-approved inventory from being used (full blocking of purchase order quantities).</span></span>
-   <span data-ttu-id="8c781-117">Use a amostragem do item como parte de uma associação de qualidade para definir o valor de estoque físico atual que deve ser inspecionado.</span><span class="sxs-lookup"><span data-stu-id="8c781-117">Use item sampling as part of a quality association to define the amount of current physical inventory that must be inspected.</span></span> <span data-ttu-id="8c781-118">A amostragem pode se basear em quantidades fixas ou em uma porcentagem.</span><span class="sxs-lookup"><span data-stu-id="8c781-118">Sampling can be based on fixed quantities or a percentage.</span></span>
-   <span data-ttu-id="8c781-119">Crie ordens de qualidade para recebimentos parciais.</span><span class="sxs-lookup"><span data-stu-id="8c781-119">Create quality orders for partial receipts.</span></span> <span data-ttu-id="8c781-120">Para criar uma ordem de qualidade baseada na quantidade fisicamente recebida com uma ordem, marque a caixa de seleção **Por quantidade atualizada** no formulário **Amostragem de itens**.</span><span class="sxs-lookup"><span data-stu-id="8c781-120">To create a quality order that is based on the quantity that is physically received with an order, you must select the **Per updated quantity** check box on the **Item sampling** form.</span></span>
-   <span data-ttu-id="8c781-121">Crie tipos de teste que incluem valores de teste mínimos, máximos, e de destino, e realizar testes qualitativos versos quantitativos que possuem resultados de validação pré-definidos.</span><span class="sxs-lookup"><span data-stu-id="8c781-121">Create test types that include minimum, maximum, and target test values, and perform qualitative-versus-quantitative testing that has predefined validation results.</span></span>
-   <span data-ttu-id="8c781-122">Especifique um nível de qualidade aceitável (AQL) para controlar as tolerâncias da medição de qualidade.</span><span class="sxs-lookup"><span data-stu-id="8c781-122">Specify an acceptable quality level (AQL) to control quality measure tolerances.</span></span>
-   <span data-ttu-id="8c781-123">Especifique os recursos que uma operação de inspeção requer, como uma área de teste e instrumentos de teste.</span><span class="sxs-lookup"><span data-stu-id="8c781-123">Specify the resources that an inspection operation requires, such as a test area and test instruments.</span></span>

## <a name="working-with-quality-associations"></a><span data-ttu-id="8c781-124">Trabalhando com associações de qualidade</span><span class="sxs-lookup"><span data-stu-id="8c781-124">Working with quality associations</span></span>
<span data-ttu-id="8c781-125">O processo comercial que utiliza uma associação de qualidade pode estar relacionado a diversos documentos de origem, como ordens de compra, ordens de venda, ou ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="8c781-125">The business process that uses a quality association can be related to various source documents, such as purchase orders, sales orders, or production orders.</span></span>

<span data-ttu-id="8c781-126">Cada registro de associação de qualidade também define o conjunto de testes, o nível de qualidade aceitável (AQL) e o plano de amostragem que se aplicam às ordens de qualidade geradas.</span><span class="sxs-lookup"><span data-stu-id="8c781-126">Each quality association record defines the set of tests, the AQL, and the sampling plan that applies to the quality orders that are generated.</span></span> <span data-ttu-id="8c781-127">Um registro de associação de qualidade deve ser definido para cada variação em um processo de negócios.</span><span class="sxs-lookup"><span data-stu-id="8c781-127">You must define a quality association record for each variation in a business process.</span></span> <span data-ttu-id="8c781-128">Por exemplo, você pode configurar uma associação de qualidade que gera uma ordem de qualidade quando um recebimento de produto da ordem de produção é atualizado.</span><span class="sxs-lookup"><span data-stu-id="8c781-128">For example, you can set up a quality association that generates a quality order when a purchase order product receipt is updated.</span></span> <span data-ttu-id="8c781-129">Dependendo da configuração do plano de execução, o próprio processo de disparo pode ser bloqueado quando houver uma ordem de qualidade aberta, ou os processos seguintes, como o faturamento de ordem de compra, puderem ser bloqueados.</span><span class="sxs-lookup"><span data-stu-id="8c781-129">Depending on the setup of the execution plan, the triggering process itself can be blocked while there is an open quality order, or the next processes, such as purchase order invoicing, can be blocked.</span></span>

<span data-ttu-id="8c781-130">**Observação:** Enquanto houver ordens de qualidade abertas, as quantidades de destoque serão automaticamente impedidas de serem usadas.</span><span class="sxs-lookup"><span data-stu-id="8c781-130">**Note:** While there are open quality orders, inventory quantities are automatically blocked from being issued.</span></span> <span data-ttu-id="8c781-131">Dependendo da configuração de **Bloqueio total** na página **Amostragens de item**, a quantidade será a quantidade na ordem de qualidade ou a quantidade na linha do documento de origem.</span><span class="sxs-lookup"><span data-stu-id="8c781-131">Depending on the **Full blocking** setting on the **Item samplings** page, the quantity is either the quantity on the quality order or the quantity on the source document line.</span></span>

<span data-ttu-id="8c781-132">Para um dado processo comercial, o registro de associação de qualidade identifica o evento e as condições para as quais uma ordem de qualidade é gerada.</span><span class="sxs-lookup"><span data-stu-id="8c781-132">For a given business process, the quality association record identifies the event and the conditions that a quality order is generated for.</span></span> <span data-ttu-id="8c781-133">As condições podem ser específicas para um site ou uma entidade legal.</span><span class="sxs-lookup"><span data-stu-id="8c781-133">The conditions can be specific to either a site or a legal entity.</span></span> <span data-ttu-id="8c781-134">Uma ordem de qualidade que envolve testes destrutivos podem ser geradas somente quando existir um estoque para o evento.</span><span class="sxs-lookup"><span data-stu-id="8c781-134">A quality order that involves destructive tests can be generated only when on-hand inventory exists for the event.</span></span>

<span data-ttu-id="8c781-135">Os exemplos a seguir ilustram como um registro de associação de qualidade é definido para as variações em cada processo comercial.</span><span class="sxs-lookup"><span data-stu-id="8c781-135">The following examples illustrate how a quality association record is defined for the variations in each business process.</span></span> <span data-ttu-id="8c781-136">Para cada exemplo, a tabela a seguir resume os eventos e as condições que são definidas por um registro de associação de qualidade.</span><span class="sxs-lookup"><span data-stu-id="8c781-136">For each example, the following table summarizes the events and conditions that are defined by a quality association record.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="8c781-137">Tipo de referência</span><span class="sxs-lookup"><span data-stu-id="8c781-137">Reference type</span></span></th>
<th><span data-ttu-id="8c781-138">Tipo de evento</span><span class="sxs-lookup"><span data-stu-id="8c781-138">Event type</span></span></th>
<th><span data-ttu-id="8c781-139">Execução</span><span class="sxs-lookup"><span data-stu-id="8c781-139">Execution</span></span></th>
<th><span data-ttu-id="8c781-140">Bloqueio do evento</span><span class="sxs-lookup"><span data-stu-id="8c781-140">Event blocking</span></span></th>
<th><span data-ttu-id="8c781-141">Referência de documento</span><span class="sxs-lookup"><span data-stu-id="8c781-141">Document reference</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="8c781-142">Estoque</span><span class="sxs-lookup"><span data-stu-id="8c781-142">Inventory</span></span></td>
<td><span data-ttu-id="8c781-143">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="8c781-143">Not applicable</span></span></td>
<td><span data-ttu-id="8c781-144">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="8c781-144">Not applicable</span></span></td>
<td><span data-ttu-id="8c781-145">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8c781-145">None</span></span></td>
<td><span data-ttu-id="8c781-146">Tudo</span><span class="sxs-lookup"><span data-stu-id="8c781-146">All</span></span></td>
</tr>
<tr>
<td rowspan="7"><span data-ttu-id="8c781-147">Venda</span><span class="sxs-lookup"><span data-stu-id="8c781-147">Sales</span></span></td>
<td rowspan="4"><span data-ttu-id="8c781-148">O processo de separação está agendado</span><span class="sxs-lookup"><span data-stu-id="8c781-148">Picking process is scheduled</span></span></td>
<td rowspan="4"><span data-ttu-id="8c781-149">Antes</span><span class="sxs-lookup"><span data-stu-id="8c781-149">Before</span></span></td>
<td><span data-ttu-id="8c781-150">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8c781-150">None</span></span></td>
<td rowspan="22"><span data-ttu-id="8c781-151">ID específica, Grupo, ou Todos apenas</span><span class="sxs-lookup"><span data-stu-id="8c781-151">Specific ID, Group, or All only</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-152">Processo de separação</span><span class="sxs-lookup"><span data-stu-id="8c781-152">Picking process</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-153">Guia de remessa</span><span class="sxs-lookup"><span data-stu-id="8c781-153">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-154">Fatura</span><span class="sxs-lookup"><span data-stu-id="8c781-154">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="8c781-155">Guia de remessa</span><span class="sxs-lookup"><span data-stu-id="8c781-155">Packing slip</span></span></td>
<td rowspan="3"><span data-ttu-id="8c781-156">Antes</span><span class="sxs-lookup"><span data-stu-id="8c781-156">Before</span></span></td>
<td><span data-ttu-id="8c781-157">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8c781-157">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-158">Guia de remessa</span><span class="sxs-lookup"><span data-stu-id="8c781-158">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-159">Fatura</span><span class="sxs-lookup"><span data-stu-id="8c781-159">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="15"><span data-ttu-id="8c781-160">Compra</span><span class="sxs-lookup"><span data-stu-id="8c781-160">Purchase</span></span></td>
<td rowspan="7"><span data-ttu-id="8c781-161">Lista de recebimentos</span><span class="sxs-lookup"><span data-stu-id="8c781-161">Receipt list</span></span></td>
<td rowspan="4"><span data-ttu-id="8c781-162">Antes</span><span class="sxs-lookup"><span data-stu-id="8c781-162">Before</span></span></td>
<td><span data-ttu-id="8c781-163">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8c781-163">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-164">Lista de recebimentos</span><span class="sxs-lookup"><span data-stu-id="8c781-164">Receipt list</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-165">Recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="8c781-165">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-166">Fatura</span><span class="sxs-lookup"><span data-stu-id="8c781-166">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="8c781-167">Depois</span><span class="sxs-lookup"><span data-stu-id="8c781-167">After</span></span></td>
<td><span data-ttu-id="8c781-168">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8c781-168">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-169">Recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="8c781-169">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-170">Fatura</span><span class="sxs-lookup"><span data-stu-id="8c781-170">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="8c781-171">Registro</span><span class="sxs-lookup"><span data-stu-id="8c781-171">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="8c781-172">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="8c781-172">Not applicable</span></span></td>
<td><span data-ttu-id="8c781-173">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8c781-173">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-174">Recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="8c781-174">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-175">Fatura</span><span class="sxs-lookup"><span data-stu-id="8c781-175">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="8c781-176">Recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="8c781-176">Product receipt</span></span></td>
<td rowspan="3"><span data-ttu-id="8c781-177">Antes</span><span class="sxs-lookup"><span data-stu-id="8c781-177">Before</span></span></td>
<td><span data-ttu-id="8c781-178">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8c781-178">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-179">Recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="8c781-179">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-180">Fatura</span><span class="sxs-lookup"><span data-stu-id="8c781-180">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="8c781-181">Depois</span><span class="sxs-lookup"><span data-stu-id="8c781-181">After</span></span></td>
<td><span data-ttu-id="8c781-182">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8c781-182">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-183">Fatura</span><span class="sxs-lookup"><span data-stu-id="8c781-183">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="8"><span data-ttu-id="8c781-184">Produção</span><span class="sxs-lookup"><span data-stu-id="8c781-184">Production</span></span></td>
<td rowspan="3"><span data-ttu-id="8c781-185">Registro</span><span class="sxs-lookup"><span data-stu-id="8c781-185">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="8c781-186">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="8c781-186">Not applicable</span></span></td>
<td><span data-ttu-id="8c781-187">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8c781-187">None</span></span></td>
<td rowspan="12"><span data-ttu-id="8c781-188">Tudo</span><span class="sxs-lookup"><span data-stu-id="8c781-188">All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-189">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="8c781-189">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-190">Encerrar</span><span class="sxs-lookup"><span data-stu-id="8c781-190">End</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="8c781-191">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="8c781-191">Report as finished</span></span></td>
<td rowspan="3"><span data-ttu-id="8c781-192">Antes</span><span class="sxs-lookup"><span data-stu-id="8c781-192">Before</span></span></td>
<td><span data-ttu-id="8c781-193">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8c781-193">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-194">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="8c781-194">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-195">Encerrar</span><span class="sxs-lookup"><span data-stu-id="8c781-195">End</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="8c781-196">Depois</span><span class="sxs-lookup"><span data-stu-id="8c781-196">After</span></span></td>
<td><span data-ttu-id="8c781-197">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8c781-197">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-198">Encerrar</span><span class="sxs-lookup"><span data-stu-id="8c781-198">End</span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="8c781-199">Quarentena</span><span class="sxs-lookup"><span data-stu-id="8c781-199">Quarantine</span></span></td>
<td rowspan="3"><span data-ttu-id="8c781-200">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="8c781-200">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="8c781-201">Antes</span><span class="sxs-lookup"><span data-stu-id="8c781-201">Before</span></span></td>
<td><span data-ttu-id="8c781-202">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="8c781-202">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-203">Encerrar</span><span class="sxs-lookup"><span data-stu-id="8c781-203">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-204">Depois</span><span class="sxs-lookup"><span data-stu-id="8c781-204">After</span></span></td>
<td><span data-ttu-id="8c781-205">Encerrar</span><span class="sxs-lookup"><span data-stu-id="8c781-205">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-206">Encerrar</span><span class="sxs-lookup"><span data-stu-id="8c781-206">End</span></span></td>
<td><span data-ttu-id="8c781-207">Antes</span><span class="sxs-lookup"><span data-stu-id="8c781-207">Before</span></span></td>
<td><span data-ttu-id="8c781-208">Encerrar</span><span class="sxs-lookup"><span data-stu-id="8c781-208">End</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="8c781-209">Operação do roteiro</span><span class="sxs-lookup"><span data-stu-id="8c781-209">Route operation</span></span></td>
<td rowspan="3"><span data-ttu-id="8c781-210">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="8c781-210">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="8c781-211">Antes</span><span class="sxs-lookup"><span data-stu-id="8c781-211">Before</span></span></td>
<td><span data-ttu-id="8c781-212">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8c781-212">None</span></span></td>
<td rowspan="3"><span data-ttu-id="8c781-213">ID específica, Grupo, ou Todos, e Específico de recurso, Grupo, ou Todos</span><span class="sxs-lookup"><span data-stu-id="8c781-213">Specific ID, Group, or All, and Resource specific, Group, or All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-214">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="8c781-214">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-215">Depois</span><span class="sxs-lookup"><span data-stu-id="8c781-215">After</span></span></td>
<td><span data-ttu-id="8c781-216">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8c781-216">None</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="8c781-217">Produção de coprodutos</span><span class="sxs-lookup"><span data-stu-id="8c781-217">Co-product production</span></span></td>
<td><span data-ttu-id="8c781-218">Registro</span><span class="sxs-lookup"><span data-stu-id="8c781-218">Registration</span></span></td>
<td><span data-ttu-id="8c781-219">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="8c781-219">Not applicable</span></span></td>
<td rowspan="3"><span data-ttu-id="8c781-220">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8c781-220">None</span></span></td>
<td rowspan="3"><span data-ttu-id="8c781-221">Tudo</span><span class="sxs-lookup"><span data-stu-id="8c781-221">All</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="8c781-222">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="8c781-222">Report as finished</span></span></td>
<td><span data-ttu-id="8c781-223">Antes</span><span class="sxs-lookup"><span data-stu-id="8c781-223">Before</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-224">Depois</span><span class="sxs-lookup"><span data-stu-id="8c781-224">After</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="8c781-225">A tabela a seguir fornece mais informações sobre como as ordens de qualidade podem ser geradas para tipos específicos de processos.</span><span class="sxs-lookup"><span data-stu-id="8c781-225">The following table provides more information about how quality orders can be generated for specific types of processes.</span></span>
<div class="tableSection">

<table>
<tbody>
<tr>
<th><span data-ttu-id="8c781-226">Tipo de processo</span><span class="sxs-lookup"><span data-stu-id="8c781-226">Type of process</span></span></th>
<th><span data-ttu-id="8c781-227">Quando as ordens de qualidade podem ser geradas automaticamente</span><span class="sxs-lookup"><span data-stu-id="8c781-227">When quality orders can be automatically generated</span></span></th>
<th><span data-ttu-id="8c781-228">Quando as ordens de qualidade podem ser geradas se o teste destrutivo for exigido</span><span class="sxs-lookup"><span data-stu-id="8c781-228">When quality orders can be generated if destructive testing is required</span></span></th>
<th><span data-ttu-id="8c781-229">Informações de condição</span><span class="sxs-lookup"><span data-stu-id="8c781-229">Condition information</span></span></th>
<th><span data-ttu-id="8c781-230">Informações de geração manual</span><span class="sxs-lookup"><span data-stu-id="8c781-230">Manual generation information</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="8c781-231">Ordem de compra</span><span class="sxs-lookup"><span data-stu-id="8c781-231">Purchase order</span></span></td>
<td><span data-ttu-id="8c781-232">Antes ou depois de uma lista de recebimentos ou de um recebimento de produtos para o material recebido é lançado</span><span class="sxs-lookup"><span data-stu-id="8c781-232">Before or after a receipts list or product receipt for the material that is received is posted</span></span></td>
<td><span data-ttu-id="8c781-233">Após o recebimento de produtos para o material recebido é lançado, porque o material deve estar disponível para testes destrutivos</span><span class="sxs-lookup"><span data-stu-id="8c781-233">After the product receipt for the material that is received is posted, because the material must be available for destructive testing</span></span></td>
<td><span data-ttu-id="8c781-234">O requisito para uma ordem de qualidade pode refletir um site, item ou fornecedores específicos ou uma combinação destas condições.</span><span class="sxs-lookup"><span data-stu-id="8c781-234">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="8c781-235">Uma ordem de qualidade gerada manualmente que se refere a uma ordem de compra pode usar as informações em um registro de associação, como o planejamento de amostragem de teste.</span><span class="sxs-lookup"><span data-stu-id="8c781-235">A manually generated quality order that refers to a purchase order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-236">Ordem de quarentena</span><span class="sxs-lookup"><span data-stu-id="8c781-236">Quarantine order</span></span></td>
<td><span data-ttu-id="8c781-237">Antes ou depois, a ordem de quarentena é relatada como concluída ou terminada</span><span class="sxs-lookup"><span data-stu-id="8c781-237">Before or after the quarantine order is reported as finished or ended</span></span></td>
<td><span data-ttu-id="8c781-238">Ordens de qualidade que exigem testes destrutivos não podem ser geradas.</span><span class="sxs-lookup"><span data-stu-id="8c781-238">Quality orders that require destructive tests can't be generated.</span></span> <span data-ttu-id="8c781-239">Presume-se que a funcionalidade da ordem de quarentena controla a disposição do material que for destruída.</span><span class="sxs-lookup"><span data-stu-id="8c781-239">It's assumed that the quarantine order functionality handles the disposition of the material that is destroyed.</span></span></td>
<td><span data-ttu-id="8c781-240">O requisito para uma ordem de qualidade pode refletir um site, item ou fornecedores específicos ou uma combinação destas condições.</span><span class="sxs-lookup"><span data-stu-id="8c781-240">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="8c781-241">Uma ordem de qualidade gerada manualmente que se refere a uma ordem de quarentena pode usar as informações em um registro de associação, como o planejamento de amostragem de teste.</span><span class="sxs-lookup"><span data-stu-id="8c781-241">A manually generated quality order that refers to a quarantine order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-242">Ordem de venda</span><span class="sxs-lookup"><span data-stu-id="8c781-242">Sales order</span></span></td>
<td><span data-ttu-id="8c781-243">Antes de uma atualização programada do processo de separação ou da guia de remessa dos itens que estão sendo enviados</span><span class="sxs-lookup"><span data-stu-id="8c781-243">Before a scheduled picking process or packing slip update for the items that are being shipped</span></span></td>
<td><span data-ttu-id="8c781-244">Em qualquer etapa</span><span class="sxs-lookup"><span data-stu-id="8c781-244">At any step</span></span></td>
<td><span data-ttu-id="8c781-245">O requisito para uma ordem de qualidade pode refletir um determinado site, ou cliente ou uma combinação dessas condições.</span><span class="sxs-lookup"><span data-stu-id="8c781-245">The requirement for a quality order can reflect a particular site, item, or customer, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="8c781-246">Uma ordem de qualidade gerada manualmente que se refere à ordem de compra pode usar informações em um registro de associação de qualidade, como o planejamento de amostragem de teste.</span><span class="sxs-lookup"><span data-stu-id="8c781-246">A manually generated quality order that refers to a sales order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-247">Ordem de produção</span><span class="sxs-lookup"><span data-stu-id="8c781-247">Production order</span></span></td>
<td><span data-ttu-id="8c781-248">Antes ou depois, a quantidade concluída para a ordem de produção é relatada</span><span class="sxs-lookup"><span data-stu-id="8c781-248">Before or after the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="8c781-249">Depois que a quantidade concluída para a ordem de produção é relatada</span><span class="sxs-lookup"><span data-stu-id="8c781-249">After the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="8c781-250">O requisito para uma ordem de qualidade pode refletir um site ou item particulares ou uma combinação dessas condições.</span><span class="sxs-lookup"><span data-stu-id="8c781-250">The requirement for a quality order can reflect a particular site or item, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="8c781-251">Uma ordem de qualidade gerada manualmente que se refere a uma ordem de produção em um registro de associação de qualidade, como o plano de amostragem de teste.</span><span class="sxs-lookup"><span data-stu-id="8c781-251">A manually generated quality order that refers to a production order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-252">Ordem de produção que tem uma operação de rota</span><span class="sxs-lookup"><span data-stu-id="8c781-252">Production order that has a route operation</span></span></td>
<td><span data-ttu-id="8c781-253">Antes ou depois da conclusão do relatório para uma operação</span><span class="sxs-lookup"><span data-stu-id="8c781-253">Before or after the report is finished for an operation</span></span></td>
<td><span data-ttu-id="8c781-254">Depois da conclusão de produção de relatório para a última operação</span><span class="sxs-lookup"><span data-stu-id="8c781-254">After the reporting production is finished for the last operation</span></span></td>
<td><span data-ttu-id="8c781-255">O requisito para uma ordem de qualidade pode refletir em um site, item ou recursos de operações ou a combinação dessas condições.</span><span class="sxs-lookup"><span data-stu-id="8c781-255">The requirement for a quality order can reflect a particular, site, item, or operations resource, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="8c781-256">Uma ordem de qualidade gerada manualmente que se refere a uma operação de rota em um registro de associação de qualidade, como o plano de amostragem de teste.</span><span class="sxs-lookup"><span data-stu-id="8c781-256">A manually generated quality order that refers to a route operation can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8c781-257">Estoque</span><span class="sxs-lookup"><span data-stu-id="8c781-257">Inventory</span></span></td>
<td><span data-ttu-id="8c781-258">Uma ordem de qualidade não pode ser gerada automaticamente para uma transação em um diário de estoque ou para a transação de ordem de transferências.</span><span class="sxs-lookup"><span data-stu-id="8c781-258">A quality order cannot be automatically generated for a transaction in an inventory journal or for transfer order transactions.</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="8c781-259">Uma ordem de qualidade deve ser criada manualmente para a quantidade do estoque de um item.</span><span class="sxs-lookup"><span data-stu-id="8c781-259">A quality order must be created manually for an item's inventory quantity.</span></span> <span data-ttu-id="8c781-260">O estoque físico disponível do item é necessário.</span><span class="sxs-lookup"><span data-stu-id="8c781-260">Physical on-hand inventory is required.</span></span></td>
</tr>
</tbody>
</table>

## <a name="quality-management-pages"></a><span data-ttu-id="8c781-261">Páginas de gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="8c781-261">Quality management pages</span></span>
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c781-262">Página</span><span class="sxs-lookup"><span data-stu-id="8c781-262">Page</span></span></th>
<th><span data-ttu-id="8c781-263">Descrição</span><span class="sxs-lookup"><span data-stu-id="8c781-263">Description</span></span></th>
<th><span data-ttu-id="8c781-264">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8c781-264">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="8c781-265">Associações de qualidade</span><span class="sxs-lookup"><span data-stu-id="8c781-265">Quality associations</span></span></td>
<td><span data-ttu-id="8c781-266">Consulte as seções anteriores deste artigo.</span><span class="sxs-lookup"><span data-stu-id="8c781-266">See the previous sections of this article.</span></span></td>
<td><span data-ttu-id="8c781-267">Uma associação de qualidade define todas as informações a seguir para uma ordem de qualidade que é gerada:</span><span class="sxs-lookup"><span data-stu-id="8c781-267">A quality association defines all the following information for a quality order that is generated:</span></span>
<ul>
<li><span data-ttu-id="8c781-268">O evento da transação</span><span class="sxs-lookup"><span data-stu-id="8c781-268">The transaction event</span></span></li>
<li><span data-ttu-id="8c781-269">O conjunto de testes que devem ser executados nos itens</span><span class="sxs-lookup"><span data-stu-id="8c781-269">The set of tests that must be performed on the items</span></span></li>
<li><span data-ttu-id="8c781-270">O AQL</span><span class="sxs-lookup"><span data-stu-id="8c781-270">The AQL</span></span></li>
<li><span data-ttu-id="8c781-271">O plano de amostragem</span><span class="sxs-lookup"><span data-stu-id="8c781-271">The sampling plan</span></span></li>
</ul>
<span data-ttu-id="8c781-272">É necessário definir uma associação de qualidade para cada variação em um processo comercial que requer a geração automática de ordens de qualidade.</span><span class="sxs-lookup"><span data-stu-id="8c781-272">You must define a quality association for each variation in a business process that requires automatic generation of quality orders.</span></span> <span data-ttu-id="8c781-273">Por exemplo, uma ordem de qualidade pode ser gerada nos processos comerciais para ordens de compra, ordens de quarentena, ordens de venda, e ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="8c781-273">For example, a quality order can be generated in the business processes for purchase orders, quarantine orders, sales orders, and production orders.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8c781-274">Testes</span><span class="sxs-lookup"><span data-stu-id="8c781-274">Tests</span></span></td>
<td><span data-ttu-id="8c781-275">Use esta página para definir e exibir os testes individuais que determinam se seus produtos atendem às especificações de qualidade.</span><span class="sxs-lookup"><span data-stu-id="8c781-275">Use this page to define and view the individual tests that determine whether your products meet quality specifications.</span></span> <span data-ttu-id="8c781-276">Você pode atribuir um ou mais testes individuais a um grupo de teste.</span><span class="sxs-lookup"><span data-stu-id="8c781-276">You can assign one or more individual tests to a test group.</span></span> <span data-ttu-id="8c781-277">Nesse caso, você também pode especificar informações específicas, como os valores de medida aceitáveis.</span><span class="sxs-lookup"><span data-stu-id="8c781-277">In this case, you also specify test-specific information, such as the acceptable measurement values.</span></span> <span data-ttu-id="8c781-278">Os valores de medição são usados para testes quantitativos, e as variáveis de teste são usadas para testes qualitativos.</span><span class="sxs-lookup"><span data-stu-id="8c781-278">Measurement values are used for quantitative tests, and test variables are used for qualitative tests.</span></span>
<ul>
<li><span data-ttu-id="8c781-279">Um teste quantitativo tem um tipo de teste <strong>Inteiro</strong> ou <strong>Fração</strong>, e também tem uma unidade de medida designada.</span><span class="sxs-lookup"><span data-stu-id="8c781-279">A quantitative test has a test type of <strong>Integer</strong> or <strong>Fraction</strong>, and also has a designated unit of measure.</span></span> <span data-ttu-id="8c781-280">As especificações de qualidade e os resultados de teste são expressos em números.</span><span class="sxs-lookup"><span data-stu-id="8c781-280">Quality specifications and test results are expressed as numbers.</span></span></li>
<li><span data-ttu-id="8c781-281">Um teste qualitativo tem o tipo de teste <strong>Opção</strong>.</span><span class="sxs-lookup"><span data-stu-id="8c781-281">A qualitative test has a test type of <strong>Option</strong>.</span></span> <span data-ttu-id="8c781-282">Os testes qualitativos requerem informações adicionais sobre a variável de teste que está sendo medida e suas opções enumeradas.</span><span class="sxs-lookup"><span data-stu-id="8c781-282">Qualitative tests require additional information about the test variable that is being measured and its enumerated options.</span></span> <span data-ttu-id="8c781-283">As especificações de qualidade e os resultados de teste são expressos de acordo com um resultado.</span><span class="sxs-lookup"><span data-stu-id="8c781-283">Quality specifications and test results are expressed according to an outcome.</span></span></li>
</ul></td>
<td><span data-ttu-id="8c781-284">Uma fábrica realiza dois testes em material adquirido: um teste quantitativo sobre a qualidade do material e um teste qualitativo sobre danos de embalagem.</span><span class="sxs-lookup"><span data-stu-id="8c781-284">A manufacturing company performs two tests on purchased material: a quantitative test about material quality and a qualitative test about packaging damage.</span></span> <span data-ttu-id="8c781-285">A empresa define informações adicionais sobre o teste qualitativo para identificar a variável de teste (embalagem danificada) e seus resultados.</span><span class="sxs-lookup"><span data-stu-id="8c781-285">The company defines additional information about the qualitative test to identify the test variable (damaged packaging) and its outcomes.</span></span> <span data-ttu-id="8c781-286">A empresa usa a página <strong>Grupos de teste</strong> para atribuir os dois testes a um grupo de testes e especificar informações específicas do teste.</span><span class="sxs-lookup"><span data-stu-id="8c781-286">The company uses the <strong>Test groups</strong> page to assign the two tests to a test group and to specify the test-specific information.</span></span> <span data-ttu-id="8c781-287">O grupo de testes é atribuído a uma ordem de qualidade, de tal modo que a empresa possa informar resultados de teste para os dois testes.</span><span class="sxs-lookup"><span data-stu-id="8c781-287">The test group is assigned to a quality order, so that the company can report test results for the two tests.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8c781-288">Grupos de teste</span><span class="sxs-lookup"><span data-stu-id="8c781-288">Test groups</span></span></td>
<td><span data-ttu-id="8c781-289">Use esta página para configurar, editar e exibir grupos de testes e testes individuais atribuídos a um grupo de testes.</span><span class="sxs-lookup"><span data-stu-id="8c781-289">Use this page to set up, edit, and view test groups and the individual tests that are assigned to a test group.</span></span> <span data-ttu-id="8c781-290">O painel superior exibe grupos de testes e o painel inferior exibe os testes atribuídos a um grupo de testes selecionado.</span><span class="sxs-lookup"><span data-stu-id="8c781-290">The upper pane displays test groups, and the lower pane displays the tests that are assigned to a selected test group.</span></span> <span data-ttu-id="8c781-291">Você atribui várias políticas a um grupo de testes, como um plano de amostragem, um AQL, e o requisito para testes destrutivos.</span><span class="sxs-lookup"><span data-stu-id="8c781-291">You assign several policies to a test group, such as a sampling plan, an AQL, and the requirement for destructive testing.</span></span> <span data-ttu-id="8c781-292">Quando você atribui um teste individual a um grupo de testes, você define informações adicionais, como a sequência, os documentos, e as datas de validade.</span><span class="sxs-lookup"><span data-stu-id="8c781-292">When you assign an individual test to a test group, you define additional information, such as the sequence, documents, and validity dates.</span></span> <span data-ttu-id="8c781-293">Para um teste quantitativo, as informações que você define também incluem os valores de medida aceitáveis.</span><span class="sxs-lookup"><span data-stu-id="8c781-293">For a quantitative test, the information that you define also includes the acceptable measurement values.</span></span> <span data-ttu-id="8c781-294">Para um teste qualitativo, as informações incluem a variável de teste e o resultado padrão.</span><span class="sxs-lookup"><span data-stu-id="8c781-294">For a qualitative test, the information includes the test variable and default outcome.</span></span> <span data-ttu-id="8c781-295">O grupo de testes atribuído a uma ordem de qualidade define o conjunto padrão de testes que devem ser realizados no item específico.</span><span class="sxs-lookup"><span data-stu-id="8c781-295">The test group that is assigned to a quality order defines the default set of tests that must be performed on the specified item.</span></span> <span data-ttu-id="8c781-296">No entanto, você pode adicionar, excluir, ou alterar os testes na ordem de qualidade.</span><span class="sxs-lookup"><span data-stu-id="8c781-296">However, you can add, delete, or change tests on the quality order.</span></span> <span data-ttu-id="8c781-297">Os resultados do teste são relatados para cada teste em uma ordem de qualidade.</span><span class="sxs-lookup"><span data-stu-id="8c781-297">Test results are reported for each test on a quality order.</span></span></td>
<td><span data-ttu-id="8c781-298">Uma fábrica define um grupo de testes para cada variação de suas diretrizes de qualidade.</span><span class="sxs-lookup"><span data-stu-id="8c781-298">A manufacturing company defines a test group for each variation of its quality guidelines.</span></span> <span data-ttu-id="8c781-299">Os vários grupos de testes refletem diferenças nos planos de amostragem, nos conjuntos de testes que precisam ser executados juntos, na AQL, e em outros fatores.</span><span class="sxs-lookup"><span data-stu-id="8c781-299">The various test groups reflect differences in the sampling plans, the sets of tests that must be performed together, the AQL, and other factors.</span></span> <span data-ttu-id="8c781-300">Para testes quantitativos, também existem diferenças nos valores de medida aceitáveis.</span><span class="sxs-lookup"><span data-stu-id="8c781-300">For quantitative tests, there are also differences in the acceptable measurement values.</span></span> <span data-ttu-id="8c781-301">Para impor suas diretrizes de qualidade, a empresa atribui um grupo de testes a cada regra para gerar automaticamente ordens de qualidade na página <strong>Associações de qualidade</strong>, e também atribui um grupo de testes às ordens de qualidade criadas manualmente.</span><span class="sxs-lookup"><span data-stu-id="8c781-301">To enforce its quality guidelines, the company assigns a test group to each rule for automatically generating quality orders on the <strong>Quality associations</strong> page, and also assigns a test group to quality orders that are manually created.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8c781-302">Grupos de qualidade de item</span><span class="sxs-lookup"><span data-stu-id="8c781-302">Item quality groups</span></span></td>
<td><span data-ttu-id="8c781-303">Use esta página para configurar, editar e exibir os itens atribuídos a um grupo de qualidade ou os grupos de qualidade atribuídos a um item.</span><span class="sxs-lookup"><span data-stu-id="8c781-303">Use this page to set up, edit, and view the items that are assigned to a quality group or the quality groups that are assigned to an item.</span></span> <span data-ttu-id="8c781-304">Um grupo de qualidade representa requisitos de teste comuns para itens.</span><span class="sxs-lookup"><span data-stu-id="8c781-304">A quality group represents common testing requirements for items.</span></span> <span data-ttu-id="8c781-305">Após definir os requisitos de teste da página <strong>Grupos de teste</strong>, você pode definir as regras para gerar automaticamente as ordens de qualidade.</span><span class="sxs-lookup"><span data-stu-id="8c781-305">After you define the test requirements on the <strong>Test groups</strong> page, you can define the rules for automatically generating quality orders.</span></span> <span data-ttu-id="8c781-306">Para simplificar o processo, você não define regras para itens individuais.</span><span class="sxs-lookup"><span data-stu-id="8c781-306">To simplify the process, you don't define rules for individual items.</span></span> <span data-ttu-id="8c781-307">Em vez disso, defina regras para um grupo de qualidade, usando a página <strong>Associações de qualidade</strong>.</span><span class="sxs-lookup"><span data-stu-id="8c781-307">Instead, you define rules for a quality group, by using the <strong>Quality associations</strong> page.</span></span> <span data-ttu-id="8c781-308">Você também pode usar a página <strong>Grupos de qualidade de item</strong> para que um grupo de qualidade selecionado atribua itens relevantes ao grupo.</span><span class="sxs-lookup"><span data-stu-id="8c781-308">You can also use the <strong>Item quality groups</strong> page for a selected quality group to assign relevant items to that group.</span></span> <span data-ttu-id="8c781-309">Você também pode usar a página <strong>Grupos de qualidade de item</strong> para que um item selecionado atribua grupos de qualidade relevantes ao item.</span><span class="sxs-lookup"><span data-stu-id="8c781-309">You can also use the <strong>Item quality groups</strong> page for a selected item to assign relevant quality groups to that item.</span></span></td>
<td><span data-ttu-id="8c781-310">Uma fábrica compra diversas matérias-primas que têm os mesmos requisitos de teste para inspeção de entrada.</span><span class="sxs-lookup"><span data-stu-id="8c781-310">A manufacturing company purchases various raw materials that have the same testing requirements for incoming inspection.</span></span> <span data-ttu-id="8c781-311">A empresa define um grupo de qualidade e então atribui os números de item associados com as matérias-primas ao grupo.</span><span class="sxs-lookup"><span data-stu-id="8c781-311">The company defines a quality group and then assigns the item numbers that are associated with the raw materials to that group.</span></span> <span data-ttu-id="8c781-312">Posteriormente, a empresa compra um novo tipo de matéria-prima que têm os mesmos requisitos de teste.</span><span class="sxs-lookup"><span data-stu-id="8c781-312">Later, the company purchases a new type of raw material that has the same testing requirements.</span></span> <span data-ttu-id="8c781-313">Em vez de configurar novos requisitos de teste para o novo material, a empresa adiciona o número do item para o novo material no grupo de qualidade existente.</span><span class="sxs-lookup"><span data-stu-id="8c781-313">Instead of setting up new testing requirements for the new material, the company adds the item number for the new material to the existing quality group.</span></span> <span data-ttu-id="8c781-314">A mesma fábrica também produz itens com os mesmos requisitos de teste de produção e remete os itens com o mesmo requisito para a execução de testes antes da remessa.</span><span class="sxs-lookup"><span data-stu-id="8c781-314">The same manufacturing company also produces items that have the same production testing requirements and ships items that have the same requirement for pre-shipment testing.</span></span> <span data-ttu-id="8c781-315">A fábrica define dois grupos de qualidade adicionais e então atribui os números de item relevantes a cada grupo.</span><span class="sxs-lookup"><span data-stu-id="8c781-315">The company defines two additional quality groups and then assigns the relevant item numbers to each group.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8c781-316">Teste de variáveis</span><span class="sxs-lookup"><span data-stu-id="8c781-316">Test variables</span></span></td>
<td><span data-ttu-id="8c781-317">Use esta página para definir e exibir as variáveis associadas a um teste qualitativo.</span><span class="sxs-lookup"><span data-stu-id="8c781-317">Use this page to define and view the variables that are associated with a qualitative test.</span></span> <span data-ttu-id="8c781-318">Para cada variável, você define os resultados enumerados que representam as opções possíveis.</span><span class="sxs-lookup"><span data-stu-id="8c781-318">For each variable, you define enumerated outcomes that represent the possible options.</span></span> <span data-ttu-id="8c781-319">Você define os testes na página <strong>Testes</strong>.</span><span class="sxs-lookup"><span data-stu-id="8c781-319">You define tests on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="8c781-320">Para testes qualitativos, você deve definir o tipo de teste como <strong>Opção</strong>.</span><span class="sxs-lookup"><span data-stu-id="8c781-320">For qualitative tests, you must set the test type to <strong>Option</strong>.</span></span> <span data-ttu-id="8c781-321">Use a página <strong>Grupos de teste</strong> para atribuir uma variável de teste a um teste individual.</span><span class="sxs-lookup"><span data-stu-id="8c781-321">Use the <strong>Test groups</strong> page to assign a test variable to an individual test.</span></span></td>
<td><span data-ttu-id="8c781-322">Uma fábrica que produz biscoitos usa um teste de inspeção para o produto acabado.</span><span class="sxs-lookup"><span data-stu-id="8c781-322">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="8c781-323">Esse teste de inspeção tem várias variáveis.</span><span class="sxs-lookup"><span data-stu-id="8c781-323">This inspection test has several variables.</span></span> <span data-ttu-id="8c781-324">Uma variável é sabor, e os possíveis resultados para essa variável são: bom e ruim.</span><span class="sxs-lookup"><span data-stu-id="8c781-324">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="8c781-325">Uma segunda variável é cor, e os possíveis resultados são: muito escuro, muito claro e correto.</span><span class="sxs-lookup"><span data-stu-id="8c781-325">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8c781-326">Resultados do teste de variável</span><span class="sxs-lookup"><span data-stu-id="8c781-326">Test variable outcomes</span></span></td>
<td><span data-ttu-id="8c781-327">Use esta página para configurar, editar e exibir os possíveis resultados de teste de uma variável de teste associada a um teste qualitativo.</span><span class="sxs-lookup"><span data-stu-id="8c781-327">Use this page to set up, edit, and to view the possible test results for a test variable that is associated with a qualitative test.</span></span> <span data-ttu-id="8c781-328">Para cada resultado, você atribui um status de <strong>aprovado</strong> ou <strong>reprovado</strong>.</span><span class="sxs-lookup"><span data-stu-id="8c781-328">For each outcome, you assign a <strong>pass</strong> or <strong>fail</strong> status.</span></span> <span data-ttu-id="8c781-329">Você deve definir uma variável e seus resultados para cada teste qualitativo definido na página <strong>Testes</strong>.</span><span class="sxs-lookup"><span data-stu-id="8c781-329">You must define a variable and its outcomes for each qualitative test that is defined on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="8c781-330">(Para testes qualitativos, o tipo de teste é definido como <strong>Opção</strong> na página <strong>Testes</strong>.) Use os <strong>Grupos de testes</strong> para atribuir uma variável de teste e o resultado padrão a um teste qualitativo individual.</span><span class="sxs-lookup"><span data-stu-id="8c781-330">(For qualitative tests, the test type is set to <strong>Option</strong> on the <strong>Tests</strong> page.) Use the <strong>Test groups</strong> page to assign a test variable and the default outcome to an individual qualitative test.</span></span></td>
<td><span data-ttu-id="8c781-331">Uma fábrica que produz biscoitos usa um teste de inspeção para o produto acabado.</span><span class="sxs-lookup"><span data-stu-id="8c781-331">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="8c781-332">Esse teste de inspeção tem várias variáveis.</span><span class="sxs-lookup"><span data-stu-id="8c781-332">This inspection test has of several variables.</span></span> <span data-ttu-id="8c781-333">Uma variável é sabor, e os possíveis resultados para essa variável são: bom e ruim.</span><span class="sxs-lookup"><span data-stu-id="8c781-333">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="8c781-334">Uma segunda variável é cor, e os possíveis resultados são: muito escuro, muito claro e correto.</span><span class="sxs-lookup"><span data-stu-id="8c781-334">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span> <span data-ttu-id="8c781-335">Um status de <strong>aprovado</strong> ou <strong>reprovado</strong> é atribuído a cada resultado.</span><span class="sxs-lookup"><span data-stu-id="8c781-335">A status of <strong>pass</strong> or <strong>fail</strong> is assigned to each outcome.</span></span> <span data-ttu-id="8c781-336">Durante o teste de inspeção de cada variável, o inspetor informa o resultado do teste selecionando um dos resultados.</span><span class="sxs-lookup"><span data-stu-id="8c781-336">During the inspection test for each variable, the inspector reports the test result by selecting one of the outcomes.</span></span></td>
</tr>
</tbody>
</table>



<a name="see-also"></a><span data-ttu-id="8c781-337">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8c781-337">See also</span></span>
--------

[<span data-ttu-id="8c781-338">Processos de gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="8c781-338">Quality management processes</span></span>](quality-management-processes.md)

[<span data-ttu-id="8c781-339">Habilitando o gerenciamento de não conformidade</span><span class="sxs-lookup"><span data-stu-id="8c781-339">Enabling nonconformance management</span></span>](enable-nonconformance-management.md)

