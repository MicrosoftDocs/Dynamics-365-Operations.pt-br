---
title: Visão geral do gerenciamento de qualidade
description: Este tópico descreve como usar o gerenciamento de qualidade no Dynamics 365 Supply Chain Management para ajudar a melhorar a qualidade do produto na cadeia de suprimentos.
author: perlynne
manager: AnnBe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c2d51c659d9d06f075458359d81de978e7a6d14b
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2019
ms.locfileid: "2814389"
---
# <a name="quality-management-overview"></a><span data-ttu-id="9f65c-103">Visão geral do gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="9f65c-103">Quality management overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9f65c-104">Este tópico descreve como usar o gerenciamento de qualidade no Dynamics 365 Supply Chain Management para ajudar a melhorar a qualidade do produto na cadeia de suprimentos.</span><span class="sxs-lookup"><span data-stu-id="9f65c-104">This topic describes how you can use quality management in Dynamics 365 Supply Chain Management to help improve product quality within your supply chain.</span></span>

<span data-ttu-id="9f65c-105">O gerenciamento de qualidade pode ajudar a gerenciar o tempo de resposta ao lidar com produtos fora de conformidade, independentemente do ponto de origem.</span><span class="sxs-lookup"><span data-stu-id="9f65c-105">Quality management can help you manage turnaround times when you handle nonconforming products, regardless of their point of origin.</span></span> <span data-ttu-id="9f65c-106">Como os tipos de diagnóstico são vinculados ao relatório de correção, o Supply Chain Management pode agendar tarefas para corrigir problemas evitar que se repitam.</span><span class="sxs-lookup"><span data-stu-id="9f65c-106">Because diagnostic types are linked to correction reporting, Supply Chain Management can schedule tasks to correct problems and prevent them from recurring.</span></span>

<span data-ttu-id="9f65c-107">Além da funcionalidade para gerenciar a não conformidade, o gerenciamento de qualidade inclui a função de rastrear saídas por tipo de problema (até mesmo problemas internos), e para identificar soluções como a curto prazo ou a longo prazo.</span><span class="sxs-lookup"><span data-stu-id="9f65c-107">In addition to functionality for managing nonconformance, quality management includes functionality for tracking issues by problem type (even internal problems), and for identifying solutions as short-term or long-term.</span></span> <span data-ttu-id="9f65c-108">As estatísticas sobre os principais indicadores de desempenho (KPIs) fornecem ideias sobre o histórico de saídas anteriores de não conformidade e as soluções que foram usadas para corrigi-los.</span><span class="sxs-lookup"><span data-stu-id="9f65c-108">Statistics about key performance indicators (KPIs) provide insight into the history of previous nonconformance issues and the solutions that were used to correct them.</span></span> <span data-ttu-id="9f65c-109">Você pode usar dados históricos para revisar a eficácia das medidas de qualidade anteriores e determinar as medidas apropriadas a serem usadas no futuro.</span><span class="sxs-lookup"><span data-stu-id="9f65c-109">You can use historical data to review the effectiveness of previous quality measures and determine appropriate measures to use in the future.</span></span>

<span data-ttu-id="9f65c-110">Ao configurar uma associação de qualidade, o Supply Chain Management pode gerar ordens de qualidade para vários processos comerciais, eventos, e condições.</span><span class="sxs-lookup"><span data-stu-id="9f65c-110">When you set up a quality association, Supply Chain Management can generate quality orders for various business processes, events, and conditions.</span></span> <span data-ttu-id="9f65c-111">A associação de qualidade pode cobrir item específico, um grupo específico de itens ou todos os itens.</span><span class="sxs-lookup"><span data-stu-id="9f65c-111">The quality association can cover a specific item, a specific group of items, or all items.</span></span>

## <a name="examples-of-the-use-of-quality-management"></a><span data-ttu-id="9f65c-112">Exemplo de utilização do gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="9f65c-112">Examples of the use of quality management</span></span>
<span data-ttu-id="9f65c-113">O gerenciamento de qualidade é flexível e pode ser implementado de várias maneiras para atender aos requisitos de níveis específicos das operações da cadeia de suprimento.</span><span class="sxs-lookup"><span data-stu-id="9f65c-113">Quality management is flexible and can be implemented in various ways to meet the requirements of specific levels of supply chain operations.</span></span> <span data-ttu-id="9f65c-114">Os exemplos a seguir ilustram as possíveis aplicações destes recursos:</span><span class="sxs-lookup"><span data-stu-id="9f65c-114">The following examples illustrate possible uses of these features:</span></span>

-   <span data-ttu-id="9f65c-115">Iniciar automaticamente um processo de controle de qualidade com base em critérios pré-definidos (após o registro do depósito de uma ordem de compra de um fornecedor específico).</span><span class="sxs-lookup"><span data-stu-id="9f65c-115">Automatically start a quality control process, based on predefined criteria (upon warehouse registration of a purchase order from a specific vendor).</span></span>
-   <span data-ttu-id="9f65c-116">Bloquear o estoque durante a inspeção para evitar que o estoque não aprovado seja utilizado (bloqueio total das quantidades da ordem de compra).</span><span class="sxs-lookup"><span data-stu-id="9f65c-116">Block inventory during inspection to prevent non-approved inventory from being used (full blocking of purchase order quantities).</span></span>
-   <span data-ttu-id="9f65c-117">Use a amostragem do item como parte de uma associação de qualidade para definir o valor de estoque físico atual que deve ser inspecionado.</span><span class="sxs-lookup"><span data-stu-id="9f65c-117">Use item sampling as part of a quality association to define the amount of current physical inventory that must be inspected.</span></span> <span data-ttu-id="9f65c-118">A amostragem pode se basear em quantidades fixas ou em uma porcentagem.</span><span class="sxs-lookup"><span data-stu-id="9f65c-118">Sampling can be based on fixed quantities or a percentage.</span></span>
-   <span data-ttu-id="9f65c-119">Crie ordens de qualidade para recebimentos parciais.</span><span class="sxs-lookup"><span data-stu-id="9f65c-119">Create quality orders for partial receipts.</span></span> <span data-ttu-id="9f65c-120">Para criar uma ordem de qualidade baseada na quantidade fisicamente recebida com uma ordem, marque a caixa de seleção **Por quantidade atualizada** no formulário **Amostragem de itens**.</span><span class="sxs-lookup"><span data-stu-id="9f65c-120">To create a quality order that is based on the quantity that is physically received with an order, you must select the **Per updated quantity** check box on the **Item sampling** form.</span></span>
-   <span data-ttu-id="9f65c-121">Crie tipos de teste que incluem valores de teste mínimos, máximos, e de destino, e realizar testes qualitativos versos quantitativos que possuem resultados de validação pré-definidos.</span><span class="sxs-lookup"><span data-stu-id="9f65c-121">Create test types that include minimum, maximum, and target test values, and perform qualitative-versus-quantitative testing that has predefined validation results.</span></span>
-   <span data-ttu-id="9f65c-122">Especifique um nível de qualidade aceitável (AQL) para controlar as tolerâncias da medição de qualidade.</span><span class="sxs-lookup"><span data-stu-id="9f65c-122">Specify an acceptable quality level (AQL) to control quality measure tolerances.</span></span>
-   <span data-ttu-id="9f65c-123">Especifique os recursos que uma operação de inspeção requer, como uma área de teste e instrumentos de teste.</span><span class="sxs-lookup"><span data-stu-id="9f65c-123">Specify the resources that an inspection operation requires, such as a test area and test instruments.</span></span>

## <a name="working-with-quality-associations"></a><span data-ttu-id="9f65c-124">Trabalhando com associações de qualidade</span><span class="sxs-lookup"><span data-stu-id="9f65c-124">Working with quality associations</span></span>
<span data-ttu-id="9f65c-125">O processo comercial que utiliza uma associação de qualidade pode estar relacionado a diversos documentos de origem, como ordens de compra, ordens de venda, ou ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="9f65c-125">The business process that uses a quality association can be related to various source documents, such as purchase orders, sales orders, or production orders.</span></span>

<span data-ttu-id="9f65c-126">Cada registro de associação de qualidade também define o conjunto de testes, o nível de qualidade aceitável (AQL) e o plano de amostragem que se aplicam às ordens de qualidade geradas.</span><span class="sxs-lookup"><span data-stu-id="9f65c-126">Each quality association record defines the set of tests, the AQL, and the sampling plan that applies to the quality orders that are generated.</span></span> <span data-ttu-id="9f65c-127">Um registro de associação de qualidade deve ser definido para cada variação em um processo de negócios.</span><span class="sxs-lookup"><span data-stu-id="9f65c-127">You must define a quality association record for each variation in a business process.</span></span> <span data-ttu-id="9f65c-128">Por exemplo, você pode configurar uma associação de qualidade que gera uma ordem de qualidade quando um recebimento de produto da ordem de produção é atualizado.</span><span class="sxs-lookup"><span data-stu-id="9f65c-128">For example, you can set up a quality association that generates a quality order when a purchase order product receipt is updated.</span></span> <span data-ttu-id="9f65c-129">Dependendo da configuração do plano de execução, o próprio processo de disparo pode ser bloqueado quando houver uma ordem de qualidade aberta, ou os processos seguintes, como o faturamento de ordem de compra, puderem ser bloqueados.</span><span class="sxs-lookup"><span data-stu-id="9f65c-129">Depending on the setup of the execution plan, the triggering process itself can be blocked while there is an open quality order, or the next processes, such as purchase order invoicing, can be blocked.</span></span>

<span data-ttu-id="9f65c-130">**Observação:** Enquanto houver ordens de qualidade abertas, as quantidades de destoque serão automaticamente impedidas de serem usadas.</span><span class="sxs-lookup"><span data-stu-id="9f65c-130">**Note:** While there are open quality orders, inventory quantities are automatically blocked from being issued.</span></span> <span data-ttu-id="9f65c-131">Dependendo da configuração de **Bloqueio total** na página **Amostragens de item**, a quantidade será a quantidade na ordem de qualidade ou a quantidade na linha do documento de origem.</span><span class="sxs-lookup"><span data-stu-id="9f65c-131">Depending on the **Full blocking** setting on the **Item samplings** page, the quantity is either the quantity on the quality order or the quantity on the source document line.</span></span>

<span data-ttu-id="9f65c-132">Para um dado processo comercial, o registro de associação de qualidade identifica o evento e as condições para as quais uma ordem de qualidade é gerada.</span><span class="sxs-lookup"><span data-stu-id="9f65c-132">For a given business process, the quality association record identifies the event and the conditions that a quality order is generated for.</span></span> <span data-ttu-id="9f65c-133">As condições podem ser específicas para um site ou uma entidade legal.</span><span class="sxs-lookup"><span data-stu-id="9f65c-133">The conditions can be specific to either a site or a legal entity.</span></span> <span data-ttu-id="9f65c-134">Uma ordem de qualidade que envolve testes destrutivos podem ser geradas somente quando existir um estoque para o evento.</span><span class="sxs-lookup"><span data-stu-id="9f65c-134">A quality order that involves destructive tests can be generated only when on-hand inventory exists for the event.</span></span>

<span data-ttu-id="9f65c-135">Os exemplos a seguir ilustram como um registro de associação de qualidade é definido para as variações em cada processo comercial.</span><span class="sxs-lookup"><span data-stu-id="9f65c-135">The following examples illustrate how a quality association record is defined for the variations in each business process.</span></span> <span data-ttu-id="9f65c-136">Para cada exemplo, a tabela a seguir resume os eventos e as condições que são definidas por um registro de associação de qualidade.</span><span class="sxs-lookup"><span data-stu-id="9f65c-136">For each example, the following table summarizes the events and conditions that are defined by a quality association record.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="9f65c-137">Tipo de referência</span><span class="sxs-lookup"><span data-stu-id="9f65c-137">Reference type</span></span></th>
<th><span data-ttu-id="9f65c-138">Tipo de evento</span><span class="sxs-lookup"><span data-stu-id="9f65c-138">Event type</span></span></th>
<th><span data-ttu-id="9f65c-139">Execução</span><span class="sxs-lookup"><span data-stu-id="9f65c-139">Execution</span></span></th>
<th><span data-ttu-id="9f65c-140">Bloqueio do evento</span><span class="sxs-lookup"><span data-stu-id="9f65c-140">Event blocking</span></span></th>
<th><span data-ttu-id="9f65c-141">Referência de documento</span><span class="sxs-lookup"><span data-stu-id="9f65c-141">Document reference</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="9f65c-142">Estoque</span><span class="sxs-lookup"><span data-stu-id="9f65c-142">Inventory</span></span></td>
<td><span data-ttu-id="9f65c-143">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="9f65c-143">Not applicable</span></span></td>
<td><span data-ttu-id="9f65c-144">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="9f65c-144">Not applicable</span></span></td>
<td><span data-ttu-id="9f65c-145">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9f65c-145">None</span></span></td>
<td><span data-ttu-id="9f65c-146">Tudo</span><span class="sxs-lookup"><span data-stu-id="9f65c-146">All</span></span></td>
</tr>
<tr>
<td rowspan="7"><span data-ttu-id="9f65c-147">Venda</span><span class="sxs-lookup"><span data-stu-id="9f65c-147">Sales</span></span></td>
<td rowspan="4"><span data-ttu-id="9f65c-148">O processo de separação está agendado</span><span class="sxs-lookup"><span data-stu-id="9f65c-148">Picking process is scheduled</span></span></td>
<td rowspan="4"><span data-ttu-id="9f65c-149">Antes</span><span class="sxs-lookup"><span data-stu-id="9f65c-149">Before</span></span></td>
<td><span data-ttu-id="9f65c-150">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9f65c-150">None</span></span></td>
<td rowspan="22"><span data-ttu-id="9f65c-151">ID específica, Grupo, ou Todos apenas</span><span class="sxs-lookup"><span data-stu-id="9f65c-151">Specific ID, Group, or All only</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-152">Processo de separação</span><span class="sxs-lookup"><span data-stu-id="9f65c-152">Picking process</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-153">Guia de remessa</span><span class="sxs-lookup"><span data-stu-id="9f65c-153">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-154">Fatura</span><span class="sxs-lookup"><span data-stu-id="9f65c-154">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="9f65c-155">Guia de remessa</span><span class="sxs-lookup"><span data-stu-id="9f65c-155">Packing slip</span></span></td>
<td rowspan="3"><span data-ttu-id="9f65c-156">Antes</span><span class="sxs-lookup"><span data-stu-id="9f65c-156">Before</span></span></td>
<td><span data-ttu-id="9f65c-157">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9f65c-157">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-158">Guia de remessa</span><span class="sxs-lookup"><span data-stu-id="9f65c-158">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-159">Fatura</span><span class="sxs-lookup"><span data-stu-id="9f65c-159">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="15"><span data-ttu-id="9f65c-160">Compra</span><span class="sxs-lookup"><span data-stu-id="9f65c-160">Purchase</span></span></td>
<td rowspan="7"><span data-ttu-id="9f65c-161">Lista de recebimentos</span><span class="sxs-lookup"><span data-stu-id="9f65c-161">Receipt list</span></span></td>
<td rowspan="4"><span data-ttu-id="9f65c-162">Antes</span><span class="sxs-lookup"><span data-stu-id="9f65c-162">Before</span></span></td>
<td><span data-ttu-id="9f65c-163">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9f65c-163">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-164">Lista de recebimentos</span><span class="sxs-lookup"><span data-stu-id="9f65c-164">Receipt list</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-165">Recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="9f65c-165">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-166">Fatura</span><span class="sxs-lookup"><span data-stu-id="9f65c-166">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="9f65c-167">Depois</span><span class="sxs-lookup"><span data-stu-id="9f65c-167">After</span></span></td>
<td><span data-ttu-id="9f65c-168">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9f65c-168">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-169">Recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="9f65c-169">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-170">Fatura</span><span class="sxs-lookup"><span data-stu-id="9f65c-170">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="9f65c-171">Registro</span><span class="sxs-lookup"><span data-stu-id="9f65c-171">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="9f65c-172">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="9f65c-172">Not applicable</span></span></td>
<td><span data-ttu-id="9f65c-173">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9f65c-173">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-174">Recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="9f65c-174">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-175">Fatura</span><span class="sxs-lookup"><span data-stu-id="9f65c-175">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="9f65c-176">Recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="9f65c-176">Product receipt</span></span></td>
<td rowspan="3"><span data-ttu-id="9f65c-177">Antes</span><span class="sxs-lookup"><span data-stu-id="9f65c-177">Before</span></span></td>
<td><span data-ttu-id="9f65c-178">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9f65c-178">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-179">Recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="9f65c-179">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-180">Fatura</span><span class="sxs-lookup"><span data-stu-id="9f65c-180">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="9f65c-181">Depois</span><span class="sxs-lookup"><span data-stu-id="9f65c-181">After</span></span></td>
<td><span data-ttu-id="9f65c-182">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9f65c-182">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-183">Fatura</span><span class="sxs-lookup"><span data-stu-id="9f65c-183">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="8"><span data-ttu-id="9f65c-184">Produção</span><span class="sxs-lookup"><span data-stu-id="9f65c-184">Production</span></span></td>
<td rowspan="3"><span data-ttu-id="9f65c-185">Registro</span><span class="sxs-lookup"><span data-stu-id="9f65c-185">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="9f65c-186">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="9f65c-186">Not applicable</span></span></td>
<td><span data-ttu-id="9f65c-187">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9f65c-187">None</span></span></td>
<td rowspan="12"><span data-ttu-id="9f65c-188">Tudo</span><span class="sxs-lookup"><span data-stu-id="9f65c-188">All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-189">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="9f65c-189">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-190">Encerrar</span><span class="sxs-lookup"><span data-stu-id="9f65c-190">End</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="9f65c-191">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="9f65c-191">Report as finished</span></span></td>
<td rowspan="3"><span data-ttu-id="9f65c-192">Antes</span><span class="sxs-lookup"><span data-stu-id="9f65c-192">Before</span></span></td>
<td><span data-ttu-id="9f65c-193">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9f65c-193">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-194">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="9f65c-194">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-195">Encerrar</span><span class="sxs-lookup"><span data-stu-id="9f65c-195">End</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="9f65c-196">Depois</span><span class="sxs-lookup"><span data-stu-id="9f65c-196">After</span></span></td>
<td><span data-ttu-id="9f65c-197">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9f65c-197">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-198">Encerrar</span><span class="sxs-lookup"><span data-stu-id="9f65c-198">End</span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="9f65c-199">Quarentena</span><span class="sxs-lookup"><span data-stu-id="9f65c-199">Quarantine</span></span></td>
<td rowspan="3"><span data-ttu-id="9f65c-200">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="9f65c-200">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="9f65c-201">Antes</span><span class="sxs-lookup"><span data-stu-id="9f65c-201">Before</span></span></td>
<td><span data-ttu-id="9f65c-202">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="9f65c-202">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-203">Encerrar</span><span class="sxs-lookup"><span data-stu-id="9f65c-203">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-204">Depois</span><span class="sxs-lookup"><span data-stu-id="9f65c-204">After</span></span></td>
<td><span data-ttu-id="9f65c-205">Encerrar</span><span class="sxs-lookup"><span data-stu-id="9f65c-205">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-206">Encerrar</span><span class="sxs-lookup"><span data-stu-id="9f65c-206">End</span></span></td>
<td><span data-ttu-id="9f65c-207">Antes</span><span class="sxs-lookup"><span data-stu-id="9f65c-207">Before</span></span></td>
<td><span data-ttu-id="9f65c-208">Encerrar</span><span class="sxs-lookup"><span data-stu-id="9f65c-208">End</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="9f65c-209">Operação do roteiro</span><span class="sxs-lookup"><span data-stu-id="9f65c-209">Route operation</span></span></td>
<td rowspan="3"><span data-ttu-id="9f65c-210">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="9f65c-210">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="9f65c-211">Antes</span><span class="sxs-lookup"><span data-stu-id="9f65c-211">Before</span></span></td>
<td><span data-ttu-id="9f65c-212">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9f65c-212">None</span></span></td>
<td rowspan="3"><span data-ttu-id="9f65c-213">ID específica, Grupo, ou Todos, e Específico de recurso, Grupo, ou Todos</span><span class="sxs-lookup"><span data-stu-id="9f65c-213">Specific ID, Group, or All, and Resource specific, Group, or All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-214">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="9f65c-214">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-215">Depois</span><span class="sxs-lookup"><span data-stu-id="9f65c-215">After</span></span></td>
<td><span data-ttu-id="9f65c-216">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9f65c-216">None</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="9f65c-217">Produção de coprodutos</span><span class="sxs-lookup"><span data-stu-id="9f65c-217">Co-product production</span></span></td>
<td><span data-ttu-id="9f65c-218">Registro</span><span class="sxs-lookup"><span data-stu-id="9f65c-218">Registration</span></span></td>
<td><span data-ttu-id="9f65c-219">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="9f65c-219">Not applicable</span></span></td>
<td rowspan="3"><span data-ttu-id="9f65c-220">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9f65c-220">None</span></span></td>
<td rowspan="3"><span data-ttu-id="9f65c-221">Tudo</span><span class="sxs-lookup"><span data-stu-id="9f65c-221">All</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="9f65c-222">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="9f65c-222">Report as finished</span></span></td>
<td><span data-ttu-id="9f65c-223">Antes</span><span class="sxs-lookup"><span data-stu-id="9f65c-223">Before</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-224">Depois</span><span class="sxs-lookup"><span data-stu-id="9f65c-224">After</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9f65c-225">A tabela a seguir fornece mais informações sobre como as ordens de qualidade podem ser geradas para tipos específicos de processos.</span><span class="sxs-lookup"><span data-stu-id="9f65c-225">The following table provides more information about how quality orders can be generated for specific types of processes.</span></span>
<div class="tableSection">

<table>
<tbody>
<tr>
<th><span data-ttu-id="9f65c-226">Tipo de processo</span><span class="sxs-lookup"><span data-stu-id="9f65c-226">Type of process</span></span></th>
<th><span data-ttu-id="9f65c-227">Quando as ordens de qualidade podem ser geradas automaticamente</span><span class="sxs-lookup"><span data-stu-id="9f65c-227">When quality orders can be automatically generated</span></span></th>
<th><span data-ttu-id="9f65c-228">Quando as ordens de qualidade podem ser geradas se o teste destrutivo for exigido</span><span class="sxs-lookup"><span data-stu-id="9f65c-228">When quality orders can be generated if destructive testing is required</span></span></th>
<th><span data-ttu-id="9f65c-229">Informações de condição</span><span class="sxs-lookup"><span data-stu-id="9f65c-229">Condition information</span></span></th>
<th><span data-ttu-id="9f65c-230">Informações de geração manual</span><span class="sxs-lookup"><span data-stu-id="9f65c-230">Manual generation information</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="9f65c-231">Ordem de compra</span><span class="sxs-lookup"><span data-stu-id="9f65c-231">Purchase order</span></span></td>
<td><span data-ttu-id="9f65c-232">Antes ou depois de uma lista de recebimentos ou de um recebimento de produtos para o material recebido é lançado</span><span class="sxs-lookup"><span data-stu-id="9f65c-232">Before or after a receipts list or product receipt for the material that is received is posted</span></span></td>
<td><span data-ttu-id="9f65c-233">Após o recebimento de produtos para o material recebido é lançado, porque o material deve estar disponível para testes destrutivos</span><span class="sxs-lookup"><span data-stu-id="9f65c-233">After the product receipt for the material that is received is posted, because the material must be available for destructive testing</span></span></td>
<td><span data-ttu-id="9f65c-234">O requisito para uma ordem de qualidade pode refletir um site, item ou fornecedores específicos ou uma combinação destas condições.</span><span class="sxs-lookup"><span data-stu-id="9f65c-234">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="9f65c-235">Uma ordem de qualidade gerada manualmente que se refere a uma ordem de compra pode usar as informações em um registro de associação, como o planejamento de amostragem de teste.</span><span class="sxs-lookup"><span data-stu-id="9f65c-235">A manually generated quality order that refers to a purchase order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-236">Ordem de quarentena</span><span class="sxs-lookup"><span data-stu-id="9f65c-236">Quarantine order</span></span></td>
<td><span data-ttu-id="9f65c-237">Antes ou depois, a ordem de quarentena é relatada como concluída ou terminada</span><span class="sxs-lookup"><span data-stu-id="9f65c-237">Before or after the quarantine order is reported as finished or ended</span></span></td>
<td><span data-ttu-id="9f65c-238">Ordens de qualidade que exigem testes destrutivos não podem ser geradas.</span><span class="sxs-lookup"><span data-stu-id="9f65c-238">Quality orders that require destructive tests can&#39;t be generated.</span></span> <span data-ttu-id="9f65c-239">Presume-se que a funcionalidade de ordem de quarentena controla o descarte do material destruído.</span><span class="sxs-lookup"><span data-stu-id="9f65c-239">It&#39;s assumed that the quarantine order functionality handles the disposition of the material that is destroyed.</span></span></td>
<td><span data-ttu-id="9f65c-240">O requisito para uma ordem de qualidade pode refletir um site, item ou fornecedores específicos ou uma combinação destas condições.</span><span class="sxs-lookup"><span data-stu-id="9f65c-240">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="9f65c-241">Uma ordem de qualidade gerada manualmente que se refere a uma ordem de quarentena pode usar as informações em um registro de associação, como o planejamento de amostragem de teste.</span><span class="sxs-lookup"><span data-stu-id="9f65c-241">A manually generated quality order that refers to a quarantine order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-242">Ordem de venda</span><span class="sxs-lookup"><span data-stu-id="9f65c-242">Sales order</span></span></td>
<td><span data-ttu-id="9f65c-243">Antes de uma atualização programada do processo de separação ou da guia de remessa dos itens que estão sendo enviados</span><span class="sxs-lookup"><span data-stu-id="9f65c-243">Before a scheduled picking process or packing slip update for the items that are being shipped</span></span></td>
<td><span data-ttu-id="9f65c-244">Em qualquer etapa</span><span class="sxs-lookup"><span data-stu-id="9f65c-244">At any step</span></span></td>
<td><span data-ttu-id="9f65c-245">O requisito para uma ordem de qualidade pode refletir um determinado site, ou cliente ou uma combinação dessas condições.</span><span class="sxs-lookup"><span data-stu-id="9f65c-245">The requirement for a quality order can reflect a particular site, item, or customer, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="9f65c-246">Uma ordem de qualidade gerada manualmente que se refere à ordem de compra pode usar informações em um registro de associação de qualidade, como o planejamento de amostragem de teste.</span><span class="sxs-lookup"><span data-stu-id="9f65c-246">A manually generated quality order that refers to a sales order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-247">Ordem de produção</span><span class="sxs-lookup"><span data-stu-id="9f65c-247">Production order</span></span></td>
<td><span data-ttu-id="9f65c-248">Antes ou depois, a quantidade concluída para a ordem de produção é relatada</span><span class="sxs-lookup"><span data-stu-id="9f65c-248">Before or after the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="9f65c-249">Depois que a quantidade concluída para a ordem de produção é relatada</span><span class="sxs-lookup"><span data-stu-id="9f65c-249">After the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="9f65c-250">O requisito para uma ordem de qualidade pode refletir um site ou item particulares ou uma combinação dessas condições.</span><span class="sxs-lookup"><span data-stu-id="9f65c-250">The requirement for a quality order can reflect a particular site or item, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="9f65c-251">Uma ordem de qualidade gerada manualmente que se refere a uma ordem de produção em um registro de associação de qualidade, como o plano de amostragem de teste.</span><span class="sxs-lookup"><span data-stu-id="9f65c-251">A manually generated quality order that refers to a production order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-252">Ordem de produção que tem uma operação de rota</span><span class="sxs-lookup"><span data-stu-id="9f65c-252">Production order that has a route operation</span></span></td>
<td><span data-ttu-id="9f65c-253">Antes ou depois da conclusão do relatório para uma operação</span><span class="sxs-lookup"><span data-stu-id="9f65c-253">Before or after the report is finished for an operation</span></span></td>
<td><span data-ttu-id="9f65c-254">Depois da conclusão de produção de relatório para a última operação</span><span class="sxs-lookup"><span data-stu-id="9f65c-254">After the reporting production is finished for the last operation</span></span></td>
<td><span data-ttu-id="9f65c-255">O requisito para uma ordem de qualidade pode refletir em um site, item ou recursos de operações ou a combinação dessas condições.</span><span class="sxs-lookup"><span data-stu-id="9f65c-255">The requirement for a quality order can reflect a particular, site, item, or operations resource, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="9f65c-256">Uma ordem de qualidade gerada manualmente que se refere a uma operação de rota em um registro de associação de qualidade, como o plano de amostragem de teste.</span><span class="sxs-lookup"><span data-stu-id="9f65c-256">A manually generated quality order that refers to a route operation can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-257">Estoque</span><span class="sxs-lookup"><span data-stu-id="9f65c-257">Inventory</span></span></td>
<td><span data-ttu-id="9f65c-258">Uma ordem de qualidade não pode ser gerada automaticamente para uma transação em um diário de estoque ou para a transação de ordem de transferências.</span><span class="sxs-lookup"><span data-stu-id="9f65c-258">A quality order cannot be automatically generated for a transaction in an inventory journal or for transfer order transactions.</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="9f65c-259">Uma ordem de qualidade deve ser criada manualmente para a quantidade em estoque de um item.</span><span class="sxs-lookup"><span data-stu-id="9f65c-259">A quality order must be created manually for an item&#39;s inventory quantity.</span></span> <span data-ttu-id="9f65c-260">O estoque físico disponível do item é necessário.</span><span class="sxs-lookup"><span data-stu-id="9f65c-260">Physical on-hand inventory is required.</span></span></td>
</tr>
</tbody>
</table>

## <a name="quality-order-auto-generation-examples"></a><span data-ttu-id="9f65c-261">Exemplos de geração automática de ordens de qualidade</span><span class="sxs-lookup"><span data-stu-id="9f65c-261">Quality order auto-generation examples</span></span>

### <a name="purchasing"></a><span data-ttu-id="9f65c-262">Comprando</span><span class="sxs-lookup"><span data-stu-id="9f65c-262">Purchasing</span></span>

<span data-ttu-id="9f65c-263">Na compra, se você definir o campo **Tipo de evento** como **Recebimento de produtos** e o campo **Execução** como **Após** na página **Associações de qualidade**, você obterá os seguintes resultados:</span><span class="sxs-lookup"><span data-stu-id="9f65c-263">In purchasing, if you set the **Event type** field to **Product receipt** and the **Execution** field to **After** on the **Quality associations** page, you get the following results:</span></span> 

- <span data-ttu-id="9f65c-264">Se a opção **Quantidade por atualização** for definida como **Yes**, uma ordem de qualidade é gerada para cada recebimento em relação à ordem de qualidade, com base na quantidade e nas configurações recebidas na amostra do item.</span><span class="sxs-lookup"><span data-stu-id="9f65c-264">If the **Per updated quantity** option is set to **Yes**, a quality order is generated for every receipt against the purchase order, based on the received quantity and settings in the item sampling.</span></span> <span data-ttu-id="9f65c-265">Sempre que uma quantidade é recebida em relação à ordem de compra, novos pedidos de qualidade são gerados com base na quantidade recém-recebida.</span><span class="sxs-lookup"><span data-stu-id="9f65c-265">Every time that a quantity is received against the purchase order, new quality orders are generated based on the newly received quantity.</span></span>
- <span data-ttu-id="9f65c-266">Se a opção **Quantidade por atualização** for definida como **Não**, uma ordem de qualidade será gerada para o primeiro recebimento em relação à ordem de qualidade, com base na quantidade recebida.</span><span class="sxs-lookup"><span data-stu-id="9f65c-266">If the **Per updated quantity** option is set to **No**, a quality order is generated for the first receipt against the purchase order, based on the received quantity.</span></span> <span data-ttu-id="9f65c-267">Além disso, uma ou mais ordens de qualidade são criadas com base na quantidade restante, dependendo das dimensões de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="9f65c-267">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions.</span></span> <span data-ttu-id="9f65c-268">Os pedidos de qualidade não são gerados para recebimentos subsequentes em relação à ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="9f65c-268">Quality orders aren't generated for subsequent receipts against the purchase order.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="9f65c-269">Especificação de qualidade</span><span class="sxs-lookup"><span data-stu-id="9f65c-269">Quality specification</span></span></th>
<th><span data-ttu-id="9f65c-270">Quantidade por atualização</span><span class="sxs-lookup"><span data-stu-id="9f65c-270">Per updated quantity</span></span></th>
<th><span data-ttu-id="9f65c-271">Por dimensão de rastreamento</span><span class="sxs-lookup"><span data-stu-id="9f65c-271">Per tracking dimension</span></span></th>
<th><span data-ttu-id="9f65c-272">Resultado</span><span class="sxs-lookup"><span data-stu-id="9f65c-272">Result</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="9f65c-273">Porcentagem: 10%</span><span class="sxs-lookup"><span data-stu-id="9f65c-273">Percentage: 10%</span></span></td>
<td><span data-ttu-id="9f65c-274">Sim</span><span class="sxs-lookup"><span data-stu-id="9f65c-274">Yes</span></span></td>
<td>
<p><span data-ttu-id="9f65c-275">Nº do lote: não</span><span class="sxs-lookup"><span data-stu-id="9f65c-275">Batch number: No</span></span></p>
<p><span data-ttu-id="9f65c-276">Número de série: não</span><span class="sxs-lookup"><span data-stu-id="9f65c-276">Serial number: No</span></span></p>
</td>
<td>
<p><span data-ttu-id="9f65c-277">Quantidade da ordem: 100</span><span class="sxs-lookup"><span data-stu-id="9f65c-277">Order quantity: 100</span></span></p>
<ol>
<li><span data-ttu-id="9f65c-278">Relatar como concluído para 30</span><span class="sxs-lookup"><span data-stu-id="9f65c-278">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="9f65c-279">Ordem de qualidade nº 1 para 3 (10% de 30)</span><span class="sxs-lookup"><span data-stu-id="9f65c-279">Quality order #1 for 3 (10% of 30)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="9f65c-280">Relatar como concluído para 70</span><span class="sxs-lookup"><span data-stu-id="9f65c-280">Report as finished for 70</span></span>
<ul>
<li><span data-ttu-id="9f65c-281">Ordem de qualidade nº 2 para 7 (10% da quantidade restante da ordem, que é igual a 70 neste caso)</span><span class="sxs-lookup"><span data-stu-id="9f65c-281">Quality order #2 for 7 (10% of the remaining order quantity, which equals 70 in this case)</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-282">Quantidade fixa: 1</span><span class="sxs-lookup"><span data-stu-id="9f65c-282">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="9f65c-283">Não</span><span class="sxs-lookup"><span data-stu-id="9f65c-283">No</span></span></td>
<td>
<p><span data-ttu-id="9f65c-284">Nº do lote: não</span><span class="sxs-lookup"><span data-stu-id="9f65c-284">Batch number: No</span></span></p>
<p><span data-ttu-id="9f65c-285">Número de série: não</span><span class="sxs-lookup"><span data-stu-id="9f65c-285">Serial number: No</span></span></p>
</td>
<td><span data-ttu-id="9f65c-286">Quantidade da ordem: 100</span><span class="sxs-lookup"><span data-stu-id="9f65c-286">Order quantity: 100</span></span>
<ol>
<li><span data-ttu-id="9f65c-287">Relatar como concluído para 30</span><span class="sxs-lookup"><span data-stu-id="9f65c-287">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="9f65c-288">A ordem de qualidade nº 1 é criado para 1 (para a primeira quantidade relatada como concluída, que tem um valor fixo de 1).</span><span class="sxs-lookup"><span data-stu-id="9f65c-288">Quality order #1 is created for 1 (for the first reported-as-finished quantity, which has a fixed value of 1).</span></span></li>
<li><span data-ttu-id="9f65c-289">Não são mais criadas ordens de qualidade em relação à quantidade restante.</span><span class="sxs-lookup"><span data-stu-id="9f65c-289">No more quality orders are created against the remaining quantity.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="9f65c-290">Relatar como concluído para 10</span><span class="sxs-lookup"><span data-stu-id="9f65c-290">Report as finished for 10</span></span>
<ul>
<li><span data-ttu-id="9f65c-291">Nenhuma ordem de qualidade é criada.</span><span class="sxs-lookup"><span data-stu-id="9f65c-291">No quality orders are created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="9f65c-292">Relatar como concluído para 60</span><span class="sxs-lookup"><span data-stu-id="9f65c-292">Report as finished for 60</span></span>
<ul>
<li><span data-ttu-id="9f65c-293">Nenhuma ordem de qualidade é criada.</span><span class="sxs-lookup"><span data-stu-id="9f65c-293">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-294">Quantidade fixa: 1</span><span class="sxs-lookup"><span data-stu-id="9f65c-294">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="9f65c-295">Sim</span><span class="sxs-lookup"><span data-stu-id="9f65c-295">Yes</span></span></td>
<td>
<p><span data-ttu-id="9f65c-296">Nº do lote: sim</span><span class="sxs-lookup"><span data-stu-id="9f65c-296">Batch number: Yes</span></span></p>
<p><span data-ttu-id="9f65c-297">Número de série: sim</span><span class="sxs-lookup"><span data-stu-id="9f65c-297">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="9f65c-298">Quantidade da ordem: 10</span><span class="sxs-lookup"><span data-stu-id="9f65c-298">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="9f65c-299">Relatar como concluído para 3</span><span class="sxs-lookup"><span data-stu-id="9f65c-299">Report as finished for 3</span></span>
<ul>
<li><span data-ttu-id="9f65c-300">Ordem de qualidade nº 1 para 1 do lote nº b1, série nº s1</span><span class="sxs-lookup"><span data-stu-id="9f65c-300">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="9f65c-301">Ordem de qualidade nº 2 para 1 do lote nº b2, série nº s2</span><span class="sxs-lookup"><span data-stu-id="9f65c-301">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="9f65c-302">Ordem de qualidade nº 3 para 1 do lote nº b3, série nº s3</span><span class="sxs-lookup"><span data-stu-id="9f65c-302">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
</ul>
</li>
<li><span data-ttu-id="9f65c-303">Relatar como concluído para 2</span><span class="sxs-lookup"><span data-stu-id="9f65c-303">Report as finished for 2</span></span>
<ul>
<li><span data-ttu-id="9f65c-304">Ordem de qualidade nº 4 para 1 do lote nº b4, série nº s4</span><span class="sxs-lookup"><span data-stu-id="9f65c-304">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
<li><span data-ttu-id="9f65c-305">Ordem de qualidade nº 5 para 1 do lote nº b5, série nº s5</span><span class="sxs-lookup"><span data-stu-id="9f65c-305">Quality order #5 for 1 of batch #b5, serial #s5</span></span></li>
</ul>
</li>
</ol>
<p><span data-ttu-id="9f65c-306"><strong>Observação:</strong> o lote pode ser reutilizado.</span><span class="sxs-lookup"><span data-stu-id="9f65c-306"><strong>Note:</strong> The batch can be reused.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-307">Quantidade fixa: 2</span><span class="sxs-lookup"><span data-stu-id="9f65c-307">Fixed quantity: 2</span></span></td>
<td><span data-ttu-id="9f65c-308">Não</span><span class="sxs-lookup"><span data-stu-id="9f65c-308">No</span></span></td>
<td>
<p><span data-ttu-id="9f65c-309">Nº do lote: sim</span><span class="sxs-lookup"><span data-stu-id="9f65c-309">Batch number: Yes</span></span></p>
<p><span data-ttu-id="9f65c-310">Número de série: sim</span><span class="sxs-lookup"><span data-stu-id="9f65c-310">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="9f65c-311">Quantidade da ordem: 10</span><span class="sxs-lookup"><span data-stu-id="9f65c-311">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="9f65c-312">Relatar como concluído para 4</span><span class="sxs-lookup"><span data-stu-id="9f65c-312">Report as finished for 4</span></span>
<ul>
<li><span data-ttu-id="9f65c-313">Ordem de qualidade nº 1 para 1 do lote nº b1, série nº s1.</span><span class="sxs-lookup"><span data-stu-id="9f65c-313">Quality order #1 for 1 of batch #b1, serial #s1.</span></span></li>
<li><span data-ttu-id="9f65c-314">Ordem de qualidade nº 2 para 1 do lote nº b2, série nº s2.</span><span class="sxs-lookup"><span data-stu-id="9f65c-314">Quality order #2 for 1 of batch #b2, serial #s2.</span></span></li>
<li><span data-ttu-id="9f65c-315">Ordem de qualidade nº 3 para 1 do lote nº b3, série nº s3.</span><span class="sxs-lookup"><span data-stu-id="9f65c-315">Quality order #3 for 1 of batch #b3, serial #s3.</span></span></li>
<li><span data-ttu-id="9f65c-316">Ordem de qualidade nº 4 para 1 do lote nº b4, série nº s4.</span><span class="sxs-lookup"><span data-stu-id="9f65c-316">Quality order #4 for 1 of batch #b4, serial #s4.</span></span></li>
<li><span data-ttu-id="9f65c-317">Não são mais criadas ordens de qualidade em relação à quantidade restante.</span><span class="sxs-lookup"><span data-stu-id="9f65c-317">No more quality orders are created against the remaining quantity.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="9f65c-318">Relatar como concluído para 6</span><span class="sxs-lookup"><span data-stu-id="9f65c-318">Report as finished for 6</span></span>
<ul>
<li><span data-ttu-id="9f65c-319">Nenhuma ordem de qualidade é criada.</span><span class="sxs-lookup"><span data-stu-id="9f65c-319">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

### <a name="production"></a><span data-ttu-id="9f65c-320">Produção</span><span class="sxs-lookup"><span data-stu-id="9f65c-320">Production</span></span>

<span data-ttu-id="9f65c-321">Na produção, se você definir o campo **Tipo de evento** como **Relatar como concluído** e o campo **Execução** como **Após** na página **Associações de qualidade**, você obterá os seguintes resultados:</span><span class="sxs-lookup"><span data-stu-id="9f65c-321">In production, if you set the **Event type** field to **Report as finished** and the **Execution** field to **After** on the **Quality associations** page, you get the following results:</span></span>

- <span data-ttu-id="9f65c-322">Se a opção **Quantidade por atualização** for definida como **Yes**, uma ordem de qualidade é gerada com base em todas as quantidades e configurações finalizadas na amostra do item.</span><span class="sxs-lookup"><span data-stu-id="9f65c-322">If the **Per updated quantity** option is set to **Yes**, a quality order is generated based on every finished quantity and settings in the item sampling.</span></span> <span data-ttu-id="9f65c-323">Sempre que uma quantidade é relatada como concluída em relação à ordem de produção, novas ordens de qualidade são geradas com base na quantidade recém-concluída.</span><span class="sxs-lookup"><span data-stu-id="9f65c-323">Every time that a quantity is reported as finished against the production order, new quality orders are generated based on newly finished quantity.</span></span> <span data-ttu-id="9f65c-324">Essa lógica de geração é consistente com a compra.</span><span class="sxs-lookup"><span data-stu-id="9f65c-324">This generation logic is consistent with purchasing.</span></span>
- <span data-ttu-id="9f65c-325">Se a opção **Quantidade por atualização** for definida como **Não**, uma ordem de qualidade é gerada na primeira vez que uma quantidade é relatada como concluída, com base na quantidade concluída.</span><span class="sxs-lookup"><span data-stu-id="9f65c-325">If the **Per updated quantity** option is set to **No**, a quality order is generated the first time that a quantity is reported as finished, based on the finished quantity.</span></span> <span data-ttu-id="9f65c-326">Além disso, uma ou mais ordens de qualidade são criadas com base na quantidade restante, dependendo das dimensões de rastreamento da amostra do item.</span><span class="sxs-lookup"><span data-stu-id="9f65c-326">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions of the item sampling.</span></span> <span data-ttu-id="9f65c-327">As ordens de qualidade não são geradas para quantidades concluídas subsequentes.</span><span class="sxs-lookup"><span data-stu-id="9f65c-327">Quality orders aren't generated for subsequent finished quantities.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="9f65c-328">Especificação de qualidade</span><span class="sxs-lookup"><span data-stu-id="9f65c-328">Quality specification</span></span></th>
<th><span data-ttu-id="9f65c-329">Quantidade por atualização</span><span class="sxs-lookup"><span data-stu-id="9f65c-329">Per updated quantity</span></span></th>
<th><span data-ttu-id="9f65c-330">Por dimensão de rastreamento</span><span class="sxs-lookup"><span data-stu-id="9f65c-330">Per tracking dimension</span></span></th>
<th><span data-ttu-id="9f65c-331">Resultado</span><span class="sxs-lookup"><span data-stu-id="9f65c-331">Result</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="9f65c-332">Porcentagem: 10%</span><span class="sxs-lookup"><span data-stu-id="9f65c-332">Percentage: 10%</span></span></td>
<td><span data-ttu-id="9f65c-333">Sim</span><span class="sxs-lookup"><span data-stu-id="9f65c-333">Yes</span></span></td>
<td>
<p><span data-ttu-id="9f65c-334">Nº do lote: não</span><span class="sxs-lookup"><span data-stu-id="9f65c-334">Batch number: No</span></span></p>
<p><span data-ttu-id="9f65c-335">Número de série: não</span><span class="sxs-lookup"><span data-stu-id="9f65c-335">Serial number: No</span></span></p>
</td>
<td>
<p><span data-ttu-id="9f65c-336">Quantidade da ordem: 100</span><span class="sxs-lookup"><span data-stu-id="9f65c-336">Order quantity: 100</span></span></p>
<ol>
<li><span data-ttu-id="9f65c-337">Relatar como concluído para 30</span><span class="sxs-lookup"><span data-stu-id="9f65c-337">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="9f65c-338">Ordem de qualidade nº 1 para 3 (10% de 30)</span><span class="sxs-lookup"><span data-stu-id="9f65c-338">Quality order #1 for 3 (10% of 30)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="9f65c-339">Relatar como concluído para 70</span><span class="sxs-lookup"><span data-stu-id="9f65c-339">Report as finished for 70</span></span>
<ul>
<li><span data-ttu-id="9f65c-340">Ordem de qualidade nº 2 para 7 (10% da quantidade restante da ordem, que é igual a 70 neste caso)</span><span class="sxs-lookup"><span data-stu-id="9f65c-340">Quality order #2 for 7 (10% of the remaining order quantity, which equals 70 in this case)</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-341">Quantidade fixa: 1</span><span class="sxs-lookup"><span data-stu-id="9f65c-341">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="9f65c-342">Não</span><span class="sxs-lookup"><span data-stu-id="9f65c-342">No</span></span></td>
<td>
<p><span data-ttu-id="9f65c-343">Nº do lote: não</span><span class="sxs-lookup"><span data-stu-id="9f65c-343">Batch number: No</span></span></p>
<p><span data-ttu-id="9f65c-344">Número de série: não</span><span class="sxs-lookup"><span data-stu-id="9f65c-344">Serial number: No</span></span></p>
</td>
<td><span data-ttu-id="9f65c-345">Quantidade da ordem: 100</span><span class="sxs-lookup"><span data-stu-id="9f65c-345">Order quantity: 100</span></span>
<ol>
<li><span data-ttu-id="9f65c-346">Relatar como concluído para 30</span><span class="sxs-lookup"><span data-stu-id="9f65c-346">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="9f65c-347">Ordem de qualidade nº 1 para 1 (para a primeira quantidade relatada como concluída, que tem um valor fixo de 1)</span><span class="sxs-lookup"><span data-stu-id="9f65c-347">Quality order #1 for 1 (for the first reported-as-finished quantity, which has a fixed value of 1)</span></span></li>
<li><span data-ttu-id="9f65c-348">Ordem de qualidade nº 2 para 1 (para a quantidade restante, que ainda possui um valor fixo de 1)</span><span class="sxs-lookup"><span data-stu-id="9f65c-348">Quality order #2 for 1 (for the remaining quantity, which still has a fixed value of 1)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="9f65c-349">Relatar como concluído para 10</span><span class="sxs-lookup"><span data-stu-id="9f65c-349">Report as finished for 10</span></span>
<ul>
<li><span data-ttu-id="9f65c-350">Nenhuma ordem de qualidade é criada.</span><span class="sxs-lookup"><span data-stu-id="9f65c-350">No quality orders are created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="9f65c-351">Relatar como concluído para 60</span><span class="sxs-lookup"><span data-stu-id="9f65c-351">Report as finished for 60</span></span>
<ul>
<li><span data-ttu-id="9f65c-352">Nenhuma ordem de qualidade é criada.</span><span class="sxs-lookup"><span data-stu-id="9f65c-352">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-353">Quantidade fixa: 1</span><span class="sxs-lookup"><span data-stu-id="9f65c-353">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="9f65c-354">Sim</span><span class="sxs-lookup"><span data-stu-id="9f65c-354">Yes</span></span></td>
<td>
<p><span data-ttu-id="9f65c-355">Nº do lote: sim</span><span class="sxs-lookup"><span data-stu-id="9f65c-355">Batch number: Yes</span></span></p>
<p><span data-ttu-id="9f65c-356">Número de série: sim</span><span class="sxs-lookup"><span data-stu-id="9f65c-356">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="9f65c-357">Quantidade da ordem: 10</span><span class="sxs-lookup"><span data-stu-id="9f65c-357">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="9f65c-358">Relatar como concluído para 3: 1 para nº b1, nº s1; 1 para nº b2, nº s2; e 1 para nº b3, nº s3</span><span class="sxs-lookup"><span data-stu-id="9f65c-358">Report as finished for 3: 1 for #b1, #s1; 1 for #b2, #s2; and 1 for #b3, #s3</span></span>
<ul>
<li><span data-ttu-id="9f65c-359">Ordem de qualidade nº 1 para 1 do lote nº b1, série nº s1</span><span class="sxs-lookup"><span data-stu-id="9f65c-359">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="9f65c-360">Ordem de qualidade nº 2 para 1 do lote nº b2, série nº s2</span><span class="sxs-lookup"><span data-stu-id="9f65c-360">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="9f65c-361">Ordem de qualidade nº 3 para 1 do lote nº b3, série nº s3</span><span class="sxs-lookup"><span data-stu-id="9f65c-361">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
</ul>
</li>
<li><span data-ttu-id="9f65c-362">Relatar como concluído para 2: 1 para nº b4, nº s4; e 1 para nº b5, nº s5</span><span class="sxs-lookup"><span data-stu-id="9f65c-362">Report as finished for 2: 1 for #b4, #s4; and 1 for #b5, #s5</span></span>
<ul>
<li><span data-ttu-id="9f65c-363">Ordem de qualidade nº 4 para 1 do lote nº b4, série nº s4</span><span class="sxs-lookup"><span data-stu-id="9f65c-363">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
<li><span data-ttu-id="9f65c-364">Ordem de qualidade nº 5 para 1 do lote nº b5, série nº s5</span><span class="sxs-lookup"><span data-stu-id="9f65c-364">Quality order #5 for 1 of batch #b5, serial #s5</span></span></li>
</ul>
</li>
</ol>
<p><span data-ttu-id="9f65c-365"><strong>Observação:</strong> o lote pode ser reutilizado.</span><span class="sxs-lookup"><span data-stu-id="9f65c-365"><strong>Note:</strong> The batch can be reused.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="9f65c-366">Quantidade fixa: 2</span><span class="sxs-lookup"><span data-stu-id="9f65c-366">Fixed quantity: 2</span></span></td>
<td><span data-ttu-id="9f65c-367">Não</span><span class="sxs-lookup"><span data-stu-id="9f65c-367">No</span></span></td>
<td>
<p><span data-ttu-id="9f65c-368">Nº do lote: sim</span><span class="sxs-lookup"><span data-stu-id="9f65c-368">Batch number: Yes</span></span></p>
<p><span data-ttu-id="9f65c-369">Número de série: sim</span><span class="sxs-lookup"><span data-stu-id="9f65c-369">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="9f65c-370">Quantidade da ordem: 10</span><span class="sxs-lookup"><span data-stu-id="9f65c-370">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="9f65c-371">Relatar como concluído para 4: 1 para nº b1, nº s1; 1 para nº b2, nº s2; 1 para nº b3, nº s3; e 1 para nº b4, nº s4</span><span class="sxs-lookup"><span data-stu-id="9f65c-371">Report as finished for 4: 1 for #b1, #s1; 1 for #b2, #s2; 1 for #b3, #s3; and 1 for #b4, #s4</span></span>
<ul>
<li><span data-ttu-id="9f65c-372">Ordem de qualidade nº 1 para 1 do lote nº b1, série nº s1</span><span class="sxs-lookup"><span data-stu-id="9f65c-372">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="9f65c-373">Ordem de qualidade nº 2 para 1 do lote nº b2, série nº s2</span><span class="sxs-lookup"><span data-stu-id="9f65c-373">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="9f65c-374">Ordem de qualidade nº 3 para 1 do lote nº b3, série nº s3</span><span class="sxs-lookup"><span data-stu-id="9f65c-374">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
<li><span data-ttu-id="9f65c-375">Ordem de qualidade nº 4 para 1 do lote nº b4, série nº s4</span><span class="sxs-lookup"><span data-stu-id="9f65c-375">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
</ul>
<ul>
<li><span data-ttu-id="9f65c-376">Ordem de qualidade nº 5 para 2, sem referência a um lote e um número de série</span><span class="sxs-lookup"><span data-stu-id="9f65c-376">Quality order #5 for 2, without a reference to a batch and a serial number</span></span></li>
</ul>
</li>
<li><span data-ttu-id="9f65c-377">Relatar como concluído para 6: 1 para nº b5, nº s5; 1 para nº b6, nº s6; 1 para nº b7, nº s7; 1 para nº b8, nº s8; 1 para nº b9, nº s9; e 1 para nº b10, nº s10</span><span class="sxs-lookup"><span data-stu-id="9f65c-377">Report as finished for 6: 1 for #b5, #s5; 1 for #b6, #s6; 1 for #b7, #s7; 1 for #b8, #s8; 1 for #b9, #s9; and 1 for #b10, #s10</span></span>
<ul>
<li><span data-ttu-id="9f65c-378">Nenhuma ordem de qualidade é criada.</span><span class="sxs-lookup"><span data-stu-id="9f65c-378">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

## <a name="quality-management-pages"></a><span data-ttu-id="9f65c-379">Páginas de gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="9f65c-379">Quality management pages</span></span>
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f65c-380">Página</span><span class="sxs-lookup"><span data-stu-id="9f65c-380">Page</span></span></th>
<th><span data-ttu-id="9f65c-381">Descrição</span><span class="sxs-lookup"><span data-stu-id="9f65c-381">Description</span></span></th>
<th><span data-ttu-id="9f65c-382">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9f65c-382">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9f65c-383">Associações de qualidade</span><span class="sxs-lookup"><span data-stu-id="9f65c-383">Quality associations</span></span></td>
<td><span data-ttu-id="9f65c-384">Consulte as seções anteriores deste artigo.</span><span class="sxs-lookup"><span data-stu-id="9f65c-384">See the previous sections of this article.</span></span></td>
<td><span data-ttu-id="9f65c-385">Uma associação de qualidade define todas as informações a seguir para uma ordem de qualidade que é gerada:</span><span class="sxs-lookup"><span data-stu-id="9f65c-385">A quality association defines all the following information for a quality order that is generated:</span></span>
<ul>
<li><span data-ttu-id="9f65c-386">O evento da transação</span><span class="sxs-lookup"><span data-stu-id="9f65c-386">The transaction event</span></span></li>
<li><span data-ttu-id="9f65c-387">O conjunto de testes que devem ser executados nos itens</span><span class="sxs-lookup"><span data-stu-id="9f65c-387">The set of tests that must be performed on the items</span></span></li>
<li><span data-ttu-id="9f65c-388">O AQL</span><span class="sxs-lookup"><span data-stu-id="9f65c-388">The AQL</span></span></li>
<li><span data-ttu-id="9f65c-389">O plano de amostragem</span><span class="sxs-lookup"><span data-stu-id="9f65c-389">The sampling plan</span></span></li>
</ul>
<span data-ttu-id="9f65c-390">É necessário definir uma associação de qualidade para cada variação em um processo comercial que requer a geração automática de ordens de qualidade.</span><span class="sxs-lookup"><span data-stu-id="9f65c-390">You must define a quality association for each variation in a business process that requires automatic generation of quality orders.</span></span> <span data-ttu-id="9f65c-391">Por exemplo, uma ordem de qualidade pode ser gerada nos processos comerciais para ordens de compra, ordens de quarentena, ordens de venda, e ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="9f65c-391">For example, a quality order can be generated in the business processes for purchase orders, quarantine orders, sales orders, and production orders.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9f65c-392">Testes</span><span class="sxs-lookup"><span data-stu-id="9f65c-392">Tests</span></span></td>
<td><span data-ttu-id="9f65c-393">Use esta página para definir e exibir os testes individuais que determinam se seus produtos atendem às especificações de qualidade.</span><span class="sxs-lookup"><span data-stu-id="9f65c-393">Use this page to define and view the individual tests that determine whether your products meet quality specifications.</span></span> <span data-ttu-id="9f65c-394">Você pode atribuir um ou mais testes individuais a um grupo de teste.</span><span class="sxs-lookup"><span data-stu-id="9f65c-394">You can assign one or more individual tests to a test group.</span></span> <span data-ttu-id="9f65c-395">Nesse caso, você também pode especificar informações específicas, como os valores de medida aceitáveis.</span><span class="sxs-lookup"><span data-stu-id="9f65c-395">In this case, you also specify test-specific information, such as the acceptable measurement values.</span></span> <span data-ttu-id="9f65c-396">Os valores de medição são usados para testes quantitativos, e as variáveis de teste são usadas para testes qualitativos.</span><span class="sxs-lookup"><span data-stu-id="9f65c-396">Measurement values are used for quantitative tests, and test variables are used for qualitative tests.</span></span>
<ul>
<li><span data-ttu-id="9f65c-397">Um teste quantitativo tem um tipo de teste <strong>Inteiro</strong> ou <strong>Fração</strong>, e também tem uma unidade de medida designada.</span><span class="sxs-lookup"><span data-stu-id="9f65c-397">A quantitative test has a test type of <strong>Integer</strong> or <strong>Fraction</strong>, and also has a designated unit of measure.</span></span> <span data-ttu-id="9f65c-398">As especificações de qualidade e os resultados de teste são expressos em números.</span><span class="sxs-lookup"><span data-stu-id="9f65c-398">Quality specifications and test results are expressed as numbers.</span></span></li>
<li><span data-ttu-id="9f65c-399">Um teste qualitativo tem o tipo de teste <strong>Opção</strong>.</span><span class="sxs-lookup"><span data-stu-id="9f65c-399">A qualitative test has a test type of <strong>Option</strong>.</span></span> <span data-ttu-id="9f65c-400">Os testes qualitativos requerem informações adicionais sobre a variável de teste que está sendo medida e suas opções enumeradas.</span><span class="sxs-lookup"><span data-stu-id="9f65c-400">Qualitative tests require additional information about the test variable that is being measured and its enumerated options.</span></span> <span data-ttu-id="9f65c-401">As especificações de qualidade e os resultados de teste são expressos de acordo com um resultado.</span><span class="sxs-lookup"><span data-stu-id="9f65c-401">Quality specifications and test results are expressed according to an outcome.</span></span></li>
</ul></td>
<td><span data-ttu-id="9f65c-402">Uma fábrica realiza dois testes em material adquirido: um teste quantitativo sobre a qualidade do material e um teste qualitativo sobre danos de embalagem.</span><span class="sxs-lookup"><span data-stu-id="9f65c-402">A manufacturing company performs two tests on purchased material: a quantitative test about material quality and a qualitative test about packaging damage.</span></span> <span data-ttu-id="9f65c-403">A empresa define informações adicionais sobre o teste qualitativo para identificar a variável de teste (embalagem danificada) e seus resultados.</span><span class="sxs-lookup"><span data-stu-id="9f65c-403">The company defines additional information about the qualitative test to identify the test variable (damaged packaging) and its outcomes.</span></span> <span data-ttu-id="9f65c-404">A empresa usa a página <strong>Grupos de teste</strong> para atribuir os dois testes a um grupo de testes e especificar informações específicas do teste.</span><span class="sxs-lookup"><span data-stu-id="9f65c-404">The company uses the <strong>Test groups</strong> page to assign the two tests to a test group and to specify the test-specific information.</span></span> <span data-ttu-id="9f65c-405">O grupo de testes é atribuído a uma ordem de qualidade, de tal modo que a empresa possa informar resultados de teste para os dois testes.</span><span class="sxs-lookup"><span data-stu-id="9f65c-405">The test group is assigned to a quality order, so that the company can report test results for the two tests.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9f65c-406">Grupos de teste</span><span class="sxs-lookup"><span data-stu-id="9f65c-406">Test groups</span></span></td>
<td><span data-ttu-id="9f65c-407">Use esta página para configurar, editar e exibir grupos de testes e testes individuais atribuídos a um grupo de testes.</span><span class="sxs-lookup"><span data-stu-id="9f65c-407">Use this page to set up, edit, and view test groups and the individual tests that are assigned to a test group.</span></span> <span data-ttu-id="9f65c-408">O painel superior exibe grupos de testes e o painel inferior exibe os testes atribuídos a um grupo de testes selecionado.</span><span class="sxs-lookup"><span data-stu-id="9f65c-408">The upper pane displays test groups, and the lower pane displays the tests that are assigned to a selected test group.</span></span> <span data-ttu-id="9f65c-409">Você atribui várias políticas a um grupo de testes, como um plano de amostragem, um AQL, e o requisito para testes destrutivos.</span><span class="sxs-lookup"><span data-stu-id="9f65c-409">You assign several policies to a test group, such as a sampling plan, an AQL, and the requirement for destructive testing.</span></span> <span data-ttu-id="9f65c-410">Quando você atribui um teste individual a um grupo de testes, você define informações adicionais, como a sequência, os documentos, e as datas de validade.</span><span class="sxs-lookup"><span data-stu-id="9f65c-410">When you assign an individual test to a test group, you define additional information, such as the sequence, documents, and validity dates.</span></span> <span data-ttu-id="9f65c-411">Para um teste quantitativo, as informações que você define também incluem os valores de medida aceitáveis.</span><span class="sxs-lookup"><span data-stu-id="9f65c-411">For a quantitative test, the information that you define also includes the acceptable measurement values.</span></span> <span data-ttu-id="9f65c-412">Para um teste qualitativo, as informações incluem a variável de teste e o resultado padrão.</span><span class="sxs-lookup"><span data-stu-id="9f65c-412">For a qualitative test, the information includes the test variable and default outcome.</span></span> <span data-ttu-id="9f65c-413">O grupo de testes atribuído a uma ordem de qualidade define o conjunto padrão de testes que devem ser realizados no item específico.</span><span class="sxs-lookup"><span data-stu-id="9f65c-413">The test group that is assigned to a quality order defines the default set of tests that must be performed on the specified item.</span></span> <span data-ttu-id="9f65c-414">No entanto, você pode adicionar, excluir, ou alterar os testes na ordem de qualidade.</span><span class="sxs-lookup"><span data-stu-id="9f65c-414">However, you can add, delete, or change tests on the quality order.</span></span> <span data-ttu-id="9f65c-415">Os resultados do teste são relatados para cada teste em uma ordem de qualidade.</span><span class="sxs-lookup"><span data-stu-id="9f65c-415">Test results are reported for each test on a quality order.</span></span></td>
<td><span data-ttu-id="9f65c-416">Uma fábrica define um grupo de testes para cada variação de suas diretrizes de qualidade.</span><span class="sxs-lookup"><span data-stu-id="9f65c-416">A manufacturing company defines a test group for each variation of its quality guidelines.</span></span> <span data-ttu-id="9f65c-417">Os vários grupos de testes refletem diferenças nos planos de amostragem, nos conjuntos de testes que precisam ser executados juntos, na AQL, e em outros fatores.</span><span class="sxs-lookup"><span data-stu-id="9f65c-417">The various test groups reflect differences in the sampling plans, the sets of tests that must be performed together, the AQL, and other factors.</span></span> <span data-ttu-id="9f65c-418">Para testes quantitativos, também existem diferenças nos valores de medida aceitáveis.</span><span class="sxs-lookup"><span data-stu-id="9f65c-418">For quantitative tests, there are also differences in the acceptable measurement values.</span></span> <span data-ttu-id="9f65c-419">Para impor suas diretrizes de qualidade, a empresa atribui um grupo de testes a cada regra para gerar automaticamente ordens de qualidade na página <strong>Associações de qualidade</strong>, e também atribui um grupo de testes às ordens de qualidade criadas manualmente.</span><span class="sxs-lookup"><span data-stu-id="9f65c-419">To enforce its quality guidelines, the company assigns a test group to each rule for automatically generating quality orders on the <strong>Quality associations</strong> page, and also assigns a test group to quality orders that are manually created.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9f65c-420">Grupos de qualidade de item</span><span class="sxs-lookup"><span data-stu-id="9f65c-420">Item quality groups</span></span></td>
<td><span data-ttu-id="9f65c-421">Use esta página para configurar, editar e exibir os itens atribuídos a um grupo de qualidade ou os grupos de qualidade atribuídos a um item.</span><span class="sxs-lookup"><span data-stu-id="9f65c-421">Use this page to set up, edit, and view the items that are assigned to a quality group or the quality groups that are assigned to an item.</span></span> <span data-ttu-id="9f65c-422">Um grupo de qualidade representa requisitos de teste comuns para itens.</span><span class="sxs-lookup"><span data-stu-id="9f65c-422">A quality group represents common testing requirements for items.</span></span> <span data-ttu-id="9f65c-423">Após definir os requisitos de teste da página <strong>Grupos de teste</strong>, você pode definir as regras para gerar automaticamente as ordens de qualidade.</span><span class="sxs-lookup"><span data-stu-id="9f65c-423">After you define the test requirements on the <strong>Test groups</strong> page, you can define the rules for automatically generating quality orders.</span></span> <span data-ttu-id="9f65c-424">Para simplificar o processo, você não define regras para itens individuais.</span><span class="sxs-lookup"><span data-stu-id="9f65c-424">To simplify the process, you don&#39;t define rules for individual items.</span></span> <span data-ttu-id="9f65c-425">Em vez disso, defina regras para um grupo de qualidade, usando a página <strong>Associações de qualidade</strong>.</span><span class="sxs-lookup"><span data-stu-id="9f65c-425">Instead, you define rules for a quality group, by using the <strong>Quality associations</strong> page.</span></span> <span data-ttu-id="9f65c-426">Você também pode usar a página <strong>Grupos de qualidade de item</strong> para que um grupo de qualidade selecionado atribua itens relevantes ao grupo.</span><span class="sxs-lookup"><span data-stu-id="9f65c-426">You can also use the <strong>Item quality groups</strong> page for a selected quality group to assign relevant items to that group.</span></span> <span data-ttu-id="9f65c-427">Você também pode usar a página <strong>Grupos de qualidade de item</strong> para que um item selecionado atribua grupos de qualidade relevantes ao item.</span><span class="sxs-lookup"><span data-stu-id="9f65c-427">You can also use the <strong>Item quality groups</strong> page for a selected item to assign relevant quality groups to that item.</span></span></td>
<td><span data-ttu-id="9f65c-428">Uma fábrica compra diversas matérias-primas que têm os mesmos requisitos de teste para inspeção de entrada.</span><span class="sxs-lookup"><span data-stu-id="9f65c-428">A manufacturing company purchases various raw materials that have the same testing requirements for incoming inspection.</span></span> <span data-ttu-id="9f65c-429">A empresa define um grupo de qualidade e então atribui os números de item associados com as matérias-primas ao grupo.</span><span class="sxs-lookup"><span data-stu-id="9f65c-429">The company defines a quality group and then assigns the item numbers that are associated with the raw materials to that group.</span></span> <span data-ttu-id="9f65c-430">Posteriormente, a empresa compra um novo tipo de matéria-prima que têm os mesmos requisitos de teste.</span><span class="sxs-lookup"><span data-stu-id="9f65c-430">Later, the company purchases a new type of raw material that has the same testing requirements.</span></span> <span data-ttu-id="9f65c-431">Em vez de configurar novos requisitos de teste para o novo material, a empresa adiciona o número do item para o novo material no grupo de qualidade existente.</span><span class="sxs-lookup"><span data-stu-id="9f65c-431">Instead of setting up new testing requirements for the new material, the company adds the item number for the new material to the existing quality group.</span></span> <span data-ttu-id="9f65c-432">A mesma fábrica também produz itens com os mesmos requisitos de teste de produção e remete os itens com o mesmo requisito para a execução de testes antes da remessa.</span><span class="sxs-lookup"><span data-stu-id="9f65c-432">The same manufacturing company also produces items that have the same production testing requirements and ships items that have the same requirement for pre-shipment testing.</span></span> <span data-ttu-id="9f65c-433">A fábrica define dois grupos de qualidade adicionais e então atribui os números de item relevantes a cada grupo.</span><span class="sxs-lookup"><span data-stu-id="9f65c-433">The company defines two additional quality groups and then assigns the relevant item numbers to each group.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9f65c-434">Teste de variáveis</span><span class="sxs-lookup"><span data-stu-id="9f65c-434">Test variables</span></span></td>
<td><span data-ttu-id="9f65c-435">Use esta página para definir e exibir as variáveis associadas a um teste qualitativo.</span><span class="sxs-lookup"><span data-stu-id="9f65c-435">Use this page to define and view the variables that are associated with a qualitative test.</span></span> <span data-ttu-id="9f65c-436">Para cada variável, você define os resultados enumerados que representam as opções possíveis.</span><span class="sxs-lookup"><span data-stu-id="9f65c-436">For each variable, you define enumerated outcomes that represent the possible options.</span></span> <span data-ttu-id="9f65c-437">Você define os testes na página <strong>Testes</strong>.</span><span class="sxs-lookup"><span data-stu-id="9f65c-437">You define tests on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="9f65c-438">Para testes qualitativos, você deve definir o tipo de teste como <strong>Opção</strong>.</span><span class="sxs-lookup"><span data-stu-id="9f65c-438">For qualitative tests, you must set the test type to <strong>Option</strong>.</span></span> <span data-ttu-id="9f65c-439">Use a página <strong>Grupos de teste</strong> para atribuir uma variável de teste a um teste individual.</span><span class="sxs-lookup"><span data-stu-id="9f65c-439">Use the <strong>Test groups</strong> page to assign a test variable to an individual test.</span></span></td>
<td><span data-ttu-id="9f65c-440">Uma fábrica que produz biscoitos usa um teste de inspeção para o produto acabado.</span><span class="sxs-lookup"><span data-stu-id="9f65c-440">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="9f65c-441">Esse teste de inspeção tem várias variáveis.</span><span class="sxs-lookup"><span data-stu-id="9f65c-441">This inspection test has several variables.</span></span> <span data-ttu-id="9f65c-442">Uma variável é sabor, e os possíveis resultados para essa variável são: bom e ruim.</span><span class="sxs-lookup"><span data-stu-id="9f65c-442">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="9f65c-443">Uma segunda variável é cor, e os possíveis resultados são: muito escuro, muito claro e correto.</span><span class="sxs-lookup"><span data-stu-id="9f65c-443">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9f65c-444">Resultados do teste de variável</span><span class="sxs-lookup"><span data-stu-id="9f65c-444">Test variable outcomes</span></span></td>
<td><span data-ttu-id="9f65c-445">Use esta página para configurar, editar e exibir os possíveis resultados de teste de uma variável de teste associada a um teste qualitativo.</span><span class="sxs-lookup"><span data-stu-id="9f65c-445">Use this page to set up, edit, and to view the possible test results for a test variable that is associated with a qualitative test.</span></span> <span data-ttu-id="9f65c-446">Para cada resultado, você atribui um status de <strong>aprovado</strong> ou <strong>reprovado</strong>.</span><span class="sxs-lookup"><span data-stu-id="9f65c-446">For each outcome, you assign a <strong>pass</strong> or <strong>fail</strong> status.</span></span> <span data-ttu-id="9f65c-447">Você deve definir uma variável e seus resultados para cada teste qualitativo definido na página <strong>Testes</strong>.</span><span class="sxs-lookup"><span data-stu-id="9f65c-447">You must define a variable and its outcomes for each qualitative test that is defined on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="9f65c-448">(Para testes qualitativos, o tipo de teste é definido como <strong>Opção</strong> na página <strong>Testes</strong>.) Use os <strong>Grupos de testes</strong> para atribuir uma variável de teste e o resultado padrão a um teste qualitativo individual.</span><span class="sxs-lookup"><span data-stu-id="9f65c-448">(For qualitative tests, the test type is set to <strong>Option</strong> on the <strong>Tests</strong> page.) Use the <strong>Test groups</strong> page to assign a test variable and the default outcome to an individual qualitative test.</span></span></td>
<td><span data-ttu-id="9f65c-449">Uma fábrica que produz biscoitos usa um teste de inspeção para o produto acabado.</span><span class="sxs-lookup"><span data-stu-id="9f65c-449">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="9f65c-450">Esse teste de inspeção tem várias variáveis.</span><span class="sxs-lookup"><span data-stu-id="9f65c-450">This inspection test has of several variables.</span></span> <span data-ttu-id="9f65c-451">Uma variável é sabor, e os possíveis resultados para essa variável são: bom e ruim.</span><span class="sxs-lookup"><span data-stu-id="9f65c-451">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="9f65c-452">Uma segunda variável é cor, e os possíveis resultados são: muito escuro, muito claro e correto.</span><span class="sxs-lookup"><span data-stu-id="9f65c-452">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span> <span data-ttu-id="9f65c-453">Um status de <strong>aprovado</strong> ou <strong>reprovado</strong> é atribuído a cada resultado.</span><span class="sxs-lookup"><span data-stu-id="9f65c-453">A status of <strong>pass</strong> or <strong>fail</strong> is assigned to each outcome.</span></span> <span data-ttu-id="9f65c-454">Durante o teste de inspeção de cada variável, o inspetor informa o resultado do teste selecionando um dos resultados.</span><span class="sxs-lookup"><span data-stu-id="9f65c-454">During the inspection test for each variable, the inspector reports the test result by selecting one of the outcomes.</span></span></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a><span data-ttu-id="9f65c-455">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="9f65c-455">Additional resources</span></span>
--------

[<span data-ttu-id="9f65c-456">Processos de gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="9f65c-456">Quality management processes</span></span>](quality-management-processes.md)

[<span data-ttu-id="9f65c-457">​Gerenciamento de não conformidade​</span><span class="sxs-lookup"><span data-stu-id="9f65c-457">Nonconformance management</span></span>](enable-nonconformance-management.md)
