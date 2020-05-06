---
title: Visão geral do gerenciamento de qualidade
description: Este tópico descreve como usar o gerenciamento de qualidade no Dynamics 365 Supply Chain Management para ajudar a melhorar a qualidade do produto na cadeia de suprimentos.
author: perlynne
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e1d7828e6bb9a3684c1d76e2cfac96174a8dfbf4
ms.sourcegitcommit: 6d6aa016c4971b0673d461b82fd80b060ae5f7a1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/17/2020
ms.locfileid: "3268807"
---
# <a name="quality-management-overview"></a><span data-ttu-id="dc185-103">Visão geral do gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="dc185-103">Quality management overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dc185-104">Este tópico descreve como usar o gerenciamento de qualidade no Dynamics 365 Supply Chain Management para ajudar a melhorar a qualidade do produto na cadeia de suprimentos.</span><span class="sxs-lookup"><span data-stu-id="dc185-104">This topic describes how you can use quality management in Dynamics 365 Supply Chain Management to help improve product quality within your supply chain.</span></span>

<span data-ttu-id="dc185-105">O gerenciamento de qualidade pode ajudar a gerenciar o tempo de resposta ao lidar com produtos fora de conformidade, independentemente do ponto de origem.</span><span class="sxs-lookup"><span data-stu-id="dc185-105">Quality management can help you manage turnaround times when you handle nonconforming products, regardless of their point of origin.</span></span> <span data-ttu-id="dc185-106">Como os tipos de diagnóstico são vinculados ao relatório de correção, o Supply Chain Management pode agendar tarefas para corrigir problemas evitar que se repitam.</span><span class="sxs-lookup"><span data-stu-id="dc185-106">Because diagnostic types are linked to correction reporting, Supply Chain Management can schedule tasks to correct problems and prevent them from recurring.</span></span>

<span data-ttu-id="dc185-107">Além da funcionalidade para gerenciar a não conformidade, o gerenciamento de qualidade inclui a função de rastrear saídas por tipo de problema (até mesmo problemas internos), e para identificar soluções como a curto prazo ou a longo prazo.</span><span class="sxs-lookup"><span data-stu-id="dc185-107">In addition to functionality for managing nonconformance, quality management includes functionality for tracking issues by problem type (even internal problems), and for identifying solutions as short-term or long-term.</span></span> <span data-ttu-id="dc185-108">As estatísticas sobre os principais indicadores de desempenho (KPIs) fornecem ideias sobre o histórico de saídas anteriores de não conformidade e as soluções que foram usadas para corrigi-los.</span><span class="sxs-lookup"><span data-stu-id="dc185-108">Statistics about key performance indicators (KPIs) provide insight into the history of previous nonconformance issues and the solutions that were used to correct them.</span></span> <span data-ttu-id="dc185-109">Você pode usar dados históricos para revisar a eficácia das medidas de qualidade anteriores e determinar as medidas apropriadas a serem usadas no futuro.</span><span class="sxs-lookup"><span data-stu-id="dc185-109">You can use historical data to review the effectiveness of previous quality measures and determine appropriate measures to use in the future.</span></span>

<span data-ttu-id="dc185-110">Ao configurar uma associação de qualidade, o Supply Chain Management pode gerar ordens de qualidade para vários processos comerciais, eventos, e condições.</span><span class="sxs-lookup"><span data-stu-id="dc185-110">When you set up a quality association, Supply Chain Management can generate quality orders for various business processes, events, and conditions.</span></span> <span data-ttu-id="dc185-111">A associação de qualidade pode cobrir item específico, um grupo específico de itens ou todos os itens.</span><span class="sxs-lookup"><span data-stu-id="dc185-111">The quality association can cover a specific item, a specific group of items, or all items.</span></span>

## <a name="examples-of-the-use-of-quality-management"></a><span data-ttu-id="dc185-112">Exemplo de utilização do gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="dc185-112">Examples of the use of quality management</span></span>
<span data-ttu-id="dc185-113">O gerenciamento de qualidade é flexível e pode ser implementado de várias maneiras para atender aos requisitos de níveis específicos das operações da cadeia de suprimento.</span><span class="sxs-lookup"><span data-stu-id="dc185-113">Quality management is flexible and can be implemented in various ways to meet the requirements of specific levels of supply chain operations.</span></span> <span data-ttu-id="dc185-114">Os exemplos a seguir ilustram as possíveis aplicações destes recursos:</span><span class="sxs-lookup"><span data-stu-id="dc185-114">The following examples illustrate possible uses of these features:</span></span>

-   <span data-ttu-id="dc185-115">Iniciar automaticamente um processo de controle de qualidade com base em critérios pré-definidos (após o registro do depósito de uma ordem de compra de um fornecedor específico).</span><span class="sxs-lookup"><span data-stu-id="dc185-115">Automatically start a quality control process, based on predefined criteria (upon warehouse registration of a purchase order from a specific vendor).</span></span>
-   <span data-ttu-id="dc185-116">Bloquear o estoque durante a inspeção para evitar que o estoque não aprovado seja utilizado (bloqueio total das quantidades da ordem de compra).</span><span class="sxs-lookup"><span data-stu-id="dc185-116">Block inventory during inspection to prevent non-approved inventory from being used (full blocking of purchase order quantities).</span></span>
-   <span data-ttu-id="dc185-117">Use a amostragem do item como parte de uma associação de qualidade para definir o valor de estoque físico atual que deve ser inspecionado.</span><span class="sxs-lookup"><span data-stu-id="dc185-117">Use item sampling as part of a quality association to define the amount of current physical inventory that must be inspected.</span></span> <span data-ttu-id="dc185-118">A amostragem pode se basear em quantidades fixas, em uma porcentagem ou na placa de licença completa.</span><span class="sxs-lookup"><span data-stu-id="dc185-118">Sampling can be based on fixed quantities, a percentage, or full license plate.</span></span>

> [!NOTE]
> <span data-ttu-id="dc185-119">O recurso _Gerenciamento de qualidade para processos de depósito_ estende as possibilidades de gerenciamento de qualidade.</span><span class="sxs-lookup"><span data-stu-id="dc185-119">The _Quality management for warehouse processes_ feature extends the capabilities of quality management.</span></span> <span data-ttu-id="dc185-120">Se você estiver usando esse recurso, consulte [_Gerenciamento de qualidade para processos de depósito](quality-management-for-warehouses-processes.md) para obter exemplos de como o gerenciamento de qualidade funciona quando habilitado.</span><span class="sxs-lookup"><span data-stu-id="dc185-120">If you are using this feature, then see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md) for examples of how quality management works when it's enabled.</span></span>

-   <span data-ttu-id="dc185-121">Crie ordens de qualidade para recebimentos parciais.</span><span class="sxs-lookup"><span data-stu-id="dc185-121">Create quality orders for partial receipts.</span></span> <span data-ttu-id="dc185-122">Para criar uma ordem de qualidade baseada na quantidade fisicamente recebida com uma ordem, marque a caixa de seleção **Por quantidade atualizada** no formulário **Amostragem de itens**.</span><span class="sxs-lookup"><span data-stu-id="dc185-122">To create a quality order that is based on the quantity that is physically received with an order, you must select the **Per updated quantity** check box on the **Item sampling** form.</span></span>
-   <span data-ttu-id="dc185-123">Crie tipos de teste que incluem valores de teste mínimos, máximos, e de destino, e realizar testes qualitativos versos quantitativos que possuem resultados de validação pré-definidos.</span><span class="sxs-lookup"><span data-stu-id="dc185-123">Create test types that include minimum, maximum, and target test values, and perform qualitative-versus-quantitative testing that has predefined validation results.</span></span>
-   <span data-ttu-id="dc185-124">Especifique um nível de qualidade aceitável (AQL) para controlar as tolerâncias da medição de qualidade.</span><span class="sxs-lookup"><span data-stu-id="dc185-124">Specify an acceptable quality level (AQL) to control quality measure tolerances.</span></span>
-   <span data-ttu-id="dc185-125">Especifique os recursos que uma operação de inspeção requer, como uma área de teste e instrumentos de teste.</span><span class="sxs-lookup"><span data-stu-id="dc185-125">Specify the resources that an inspection operation requires, such as a test area and test instruments.</span></span>

## <a name="working-with-quality-associations"></a><span data-ttu-id="dc185-126">Trabalhando com associações de qualidade</span><span class="sxs-lookup"><span data-stu-id="dc185-126">Working with quality associations</span></span>
<span data-ttu-id="dc185-127">O processo comercial que utiliza uma associação de qualidade pode estar relacionado a diversos documentos de origem, como ordens de compra, ordens de venda, ou ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="dc185-127">The business process that uses a quality association can be related to various source documents, such as purchase orders, sales orders, or production orders.</span></span>

<span data-ttu-id="dc185-128">Cada registro de associação de qualidade também define o conjunto de testes, o nível de qualidade aceitável (AQL) e o plano de amostragem que se aplicam às ordens de qualidade geradas.</span><span class="sxs-lookup"><span data-stu-id="dc185-128">Each quality association record defines the set of tests, the AQL, and the sampling plan that applies to the quality orders that are generated.</span></span> <span data-ttu-id="dc185-129">Um registro de associação de qualidade deve ser definido para cada variação em um processo de negócios.</span><span class="sxs-lookup"><span data-stu-id="dc185-129">You must define a quality association record for each variation in a business process.</span></span> <span data-ttu-id="dc185-130">Por exemplo, você pode configurar uma associação de qualidade que gera uma ordem de qualidade quando um recebimento de produto da ordem de produção é atualizado.</span><span class="sxs-lookup"><span data-stu-id="dc185-130">For example, you can set up a quality association that generates a quality order when a purchase order product receipt is updated.</span></span> <span data-ttu-id="dc185-131">Dependendo da configuração do plano de execução, o próprio processo de disparo pode ser bloqueado quando houver uma ordem de qualidade aberta, ou os processos seguintes, como o faturamento de ordem de compra, puderem ser bloqueados.</span><span class="sxs-lookup"><span data-stu-id="dc185-131">Depending on the setup of the execution plan, the triggering process itself can be blocked while there is an open quality order, or the next processes, such as purchase order invoicing, can be blocked.</span></span>

<span data-ttu-id="dc185-132">**Observação:** Enquanto houver ordens de qualidade abertas, as quantidades de destoque serão automaticamente impedidas de serem usadas.</span><span class="sxs-lookup"><span data-stu-id="dc185-132">**Note:** While there are open quality orders, inventory quantities are automatically blocked from being issued.</span></span> <span data-ttu-id="dc185-133">Dependendo da configuração de **Bloqueio total** na página **Amostragens de item**, a quantidade será a quantidade na ordem de qualidade ou a quantidade na linha do documento de origem.</span><span class="sxs-lookup"><span data-stu-id="dc185-133">Depending on the **Full blocking** setting on the **Item samplings** page, the quantity is either the quantity on the quality order or the quantity on the source document line.</span></span>

<span data-ttu-id="dc185-134">Para um dado processo comercial, o registro de associação de qualidade identifica o evento e as condições para as quais uma ordem de qualidade é gerada.</span><span class="sxs-lookup"><span data-stu-id="dc185-134">For a given business process, the quality association record identifies the event and the conditions that a quality order is generated for.</span></span> <span data-ttu-id="dc185-135">As condições podem ser específicas para um site ou uma entidade legal.</span><span class="sxs-lookup"><span data-stu-id="dc185-135">The conditions can be specific to either a site or a legal entity.</span></span> <span data-ttu-id="dc185-136">Uma ordem de qualidade que envolve testes destrutivos podem ser geradas somente quando existir um estoque para o evento.</span><span class="sxs-lookup"><span data-stu-id="dc185-136">A quality order that involves destructive tests can be generated only when on-hand inventory exists for the event.</span></span>

<span data-ttu-id="dc185-137">Os exemplos a seguir ilustram como um registro de associação de qualidade é definido para as variações em cada processo comercial.</span><span class="sxs-lookup"><span data-stu-id="dc185-137">The following examples illustrate how a quality association record is defined for the variations in each business process.</span></span> <span data-ttu-id="dc185-138">Para cada exemplo, a tabela a seguir resume os eventos e as condições que são definidas por um registro de associação de qualidade.</span><span class="sxs-lookup"><span data-stu-id="dc185-138">For each example, the following table summarizes the events and conditions that are defined by a quality association record.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="dc185-139">Tipo de referência</span><span class="sxs-lookup"><span data-stu-id="dc185-139">Reference type</span></span></th>
<th><span data-ttu-id="dc185-140">Tipo de evento</span><span class="sxs-lookup"><span data-stu-id="dc185-140">Event type</span></span></th>
<th><span data-ttu-id="dc185-141">Execução</span><span class="sxs-lookup"><span data-stu-id="dc185-141">Execution</span></span></th>
<th><span data-ttu-id="dc185-142">Bloqueio do evento</span><span class="sxs-lookup"><span data-stu-id="dc185-142">Event blocking</span></span></th>
<th><span data-ttu-id="dc185-143">Referência de documento</span><span class="sxs-lookup"><span data-stu-id="dc185-143">Document reference</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="dc185-144">Estoque</span><span class="sxs-lookup"><span data-stu-id="dc185-144">Inventory</span></span></td>
<td><span data-ttu-id="dc185-145">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="dc185-145">Not applicable</span></span></td>
<td><span data-ttu-id="dc185-146">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="dc185-146">Not applicable</span></span></td>
<td><span data-ttu-id="dc185-147">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dc185-147">None</span></span></td>
<td><span data-ttu-id="dc185-148">Tudo</span><span class="sxs-lookup"><span data-stu-id="dc185-148">All</span></span></td>
</tr>
<tr>
<td rowspan="7"><span data-ttu-id="dc185-149">Venda</span><span class="sxs-lookup"><span data-stu-id="dc185-149">Sales</span></span></td>
<td rowspan="4"><span data-ttu-id="dc185-150">O processo de separação está agendado</span><span class="sxs-lookup"><span data-stu-id="dc185-150">Picking process is scheduled</span></span></td>
<td rowspan="4"><span data-ttu-id="dc185-151">Antes</span><span class="sxs-lookup"><span data-stu-id="dc185-151">Before</span></span></td>
<td><span data-ttu-id="dc185-152">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dc185-152">None</span></span></td>
<td rowspan="22"><span data-ttu-id="dc185-153">ID específica, Grupo, ou Todos apenas</span><span class="sxs-lookup"><span data-stu-id="dc185-153">Specific ID, Group, or All only</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-154">Processo de separação</span><span class="sxs-lookup"><span data-stu-id="dc185-154">Picking process</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-155">Guia de remessa</span><span class="sxs-lookup"><span data-stu-id="dc185-155">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-156">Fatura</span><span class="sxs-lookup"><span data-stu-id="dc185-156">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="dc185-157">Guia de remessa</span><span class="sxs-lookup"><span data-stu-id="dc185-157">Packing slip</span></span></td>
<td rowspan="3"><span data-ttu-id="dc185-158">Antes</span><span class="sxs-lookup"><span data-stu-id="dc185-158">Before</span></span></td>
<td><span data-ttu-id="dc185-159">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dc185-159">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-160">Guia de remessa</span><span class="sxs-lookup"><span data-stu-id="dc185-160">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-161">Fatura</span><span class="sxs-lookup"><span data-stu-id="dc185-161">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="15"><span data-ttu-id="dc185-162">Compra</span><span class="sxs-lookup"><span data-stu-id="dc185-162">Purchase</span></span></td>
<td rowspan="7"><span data-ttu-id="dc185-163">Lista de recebimentos</span><span class="sxs-lookup"><span data-stu-id="dc185-163">Receipt list</span></span></td>
<td rowspan="4"><span data-ttu-id="dc185-164">Antes</span><span class="sxs-lookup"><span data-stu-id="dc185-164">Before</span></span></td>
<td><span data-ttu-id="dc185-165">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dc185-165">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-166">Lista de recebimentos</span><span class="sxs-lookup"><span data-stu-id="dc185-166">Receipt list</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-167">Recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="dc185-167">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-168">Fatura</span><span class="sxs-lookup"><span data-stu-id="dc185-168">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="dc185-169">Depois</span><span class="sxs-lookup"><span data-stu-id="dc185-169">After</span></span></td>
<td><span data-ttu-id="dc185-170">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dc185-170">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-171">Recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="dc185-171">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-172">Fatura</span><span class="sxs-lookup"><span data-stu-id="dc185-172">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="dc185-173">Registro</span><span class="sxs-lookup"><span data-stu-id="dc185-173">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="dc185-174">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="dc185-174">Not applicable</span></span></td>
<td><span data-ttu-id="dc185-175">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dc185-175">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-176">Recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="dc185-176">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-177">Fatura</span><span class="sxs-lookup"><span data-stu-id="dc185-177">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="dc185-178">Recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="dc185-178">Product receipt</span></span></td>
<td rowspan="3"><span data-ttu-id="dc185-179">Antes</span><span class="sxs-lookup"><span data-stu-id="dc185-179">Before</span></span></td>
<td><span data-ttu-id="dc185-180">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dc185-180">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-181">Recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="dc185-181">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-182">Fatura</span><span class="sxs-lookup"><span data-stu-id="dc185-182">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="dc185-183">Depois</span><span class="sxs-lookup"><span data-stu-id="dc185-183">After</span></span></td>
<td><span data-ttu-id="dc185-184">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dc185-184">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-185">Fatura</span><span class="sxs-lookup"><span data-stu-id="dc185-185">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="8"><span data-ttu-id="dc185-186">Produção</span><span class="sxs-lookup"><span data-stu-id="dc185-186">Production</span></span></td>
<td rowspan="3"><span data-ttu-id="dc185-187">Registro</span><span class="sxs-lookup"><span data-stu-id="dc185-187">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="dc185-188">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="dc185-188">Not applicable</span></span></td>
<td><span data-ttu-id="dc185-189">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dc185-189">None</span></span></td>
<td rowspan="12"><span data-ttu-id="dc185-190">Tudo</span><span class="sxs-lookup"><span data-stu-id="dc185-190">All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-191">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="dc185-191">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-192">Encerrar</span><span class="sxs-lookup"><span data-stu-id="dc185-192">End</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="dc185-193">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="dc185-193">Report as finished</span></span></td>
<td rowspan="3"><span data-ttu-id="dc185-194">Antes</span><span class="sxs-lookup"><span data-stu-id="dc185-194">Before</span></span></td>
<td><span data-ttu-id="dc185-195">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dc185-195">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-196">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="dc185-196">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-197">Encerrar</span><span class="sxs-lookup"><span data-stu-id="dc185-197">End</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="dc185-198">Depois</span><span class="sxs-lookup"><span data-stu-id="dc185-198">After</span></span></td>
<td><span data-ttu-id="dc185-199">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dc185-199">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-200">Encerrar</span><span class="sxs-lookup"><span data-stu-id="dc185-200">End</span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="dc185-201">Quarentena</span><span class="sxs-lookup"><span data-stu-id="dc185-201">Quarantine</span></span></td>
<td rowspan="3"><span data-ttu-id="dc185-202">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="dc185-202">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="dc185-203">Antes</span><span class="sxs-lookup"><span data-stu-id="dc185-203">Before</span></span></td>
<td><span data-ttu-id="dc185-204">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="dc185-204">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-205">Encerrar</span><span class="sxs-lookup"><span data-stu-id="dc185-205">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-206">Depois</span><span class="sxs-lookup"><span data-stu-id="dc185-206">After</span></span></td>
<td><span data-ttu-id="dc185-207">Encerrar</span><span class="sxs-lookup"><span data-stu-id="dc185-207">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-208">Encerrar</span><span class="sxs-lookup"><span data-stu-id="dc185-208">End</span></span></td>
<td><span data-ttu-id="dc185-209">Antes</span><span class="sxs-lookup"><span data-stu-id="dc185-209">Before</span></span></td>
<td><span data-ttu-id="dc185-210">Encerrar</span><span class="sxs-lookup"><span data-stu-id="dc185-210">End</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="dc185-211">Operação do roteiro</span><span class="sxs-lookup"><span data-stu-id="dc185-211">Route operation</span></span></td>
<td rowspan="3"><span data-ttu-id="dc185-212">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="dc185-212">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="dc185-213">Antes</span><span class="sxs-lookup"><span data-stu-id="dc185-213">Before</span></span></td>
<td><span data-ttu-id="dc185-214">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dc185-214">None</span></span></td>
<td rowspan="3"><span data-ttu-id="dc185-215">ID específica, Grupo, ou Todos, e Específico de recurso, Grupo, ou Todos</span><span class="sxs-lookup"><span data-stu-id="dc185-215">Specific ID, Group, or All, and Resource specific, Group, or All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-216">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="dc185-216">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-217">Depois</span><span class="sxs-lookup"><span data-stu-id="dc185-217">After</span></span></td>
<td><span data-ttu-id="dc185-218">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dc185-218">None</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="dc185-219">Produção de coprodutos</span><span class="sxs-lookup"><span data-stu-id="dc185-219">Co-product production</span></span></td>
<td><span data-ttu-id="dc185-220">Registro</span><span class="sxs-lookup"><span data-stu-id="dc185-220">Registration</span></span></td>
<td><span data-ttu-id="dc185-221">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="dc185-221">Not applicable</span></span></td>
<td rowspan="3"><span data-ttu-id="dc185-222">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dc185-222">None</span></span></td>
<td rowspan="3"><span data-ttu-id="dc185-223">Tudo</span><span class="sxs-lookup"><span data-stu-id="dc185-223">All</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="dc185-224">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="dc185-224">Report as finished</span></span></td>
<td><span data-ttu-id="dc185-225">Antes</span><span class="sxs-lookup"><span data-stu-id="dc185-225">Before</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-226">Depois</span><span class="sxs-lookup"><span data-stu-id="dc185-226">After</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="dc185-227">A tabela a seguir fornece mais informações sobre como as ordens de qualidade podem ser geradas para tipos específicos de processos.</span><span class="sxs-lookup"><span data-stu-id="dc185-227">The following table provides more information about how quality orders can be generated for specific types of processes.</span></span>
<div class="tableSection">

<table>
<tbody>
<tr>
<th><span data-ttu-id="dc185-228">Tipo de processo</span><span class="sxs-lookup"><span data-stu-id="dc185-228">Type of process</span></span></th>
<th><span data-ttu-id="dc185-229">Quando as ordens de qualidade podem ser geradas automaticamente</span><span class="sxs-lookup"><span data-stu-id="dc185-229">When quality orders can be automatically generated</span></span></th>
<th><span data-ttu-id="dc185-230">Quando as ordens de qualidade podem ser geradas se o teste destrutivo for exigido</span><span class="sxs-lookup"><span data-stu-id="dc185-230">When quality orders can be generated if destructive testing is required</span></span></th>
<th><span data-ttu-id="dc185-231">Informações de condição</span><span class="sxs-lookup"><span data-stu-id="dc185-231">Condition information</span></span></th>
<th><span data-ttu-id="dc185-232">Informações de geração manual</span><span class="sxs-lookup"><span data-stu-id="dc185-232">Manual generation information</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="dc185-233">Ordem de compra</span><span class="sxs-lookup"><span data-stu-id="dc185-233">Purchase order</span></span></td>
<td><span data-ttu-id="dc185-234">Antes ou depois de uma lista de recebimentos ou de um recebimento de produtos para o material recebido é lançado</span><span class="sxs-lookup"><span data-stu-id="dc185-234">Before or after a receipts list or product receipt for the material that is received is posted</span></span></td>
<td><span data-ttu-id="dc185-235">Após o recebimento de produtos para o material recebido é lançado, porque o material deve estar disponível para testes destrutivos</span><span class="sxs-lookup"><span data-stu-id="dc185-235">After the product receipt for the material that is received is posted, because the material must be available for destructive testing</span></span></td>
<td><span data-ttu-id="dc185-236">O requisito para uma ordem de qualidade pode refletir um site, item ou fornecedores específicos ou uma combinação destas condições.</span><span class="sxs-lookup"><span data-stu-id="dc185-236">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="dc185-237">Uma ordem de qualidade gerada manualmente que se refere a uma ordem de compra pode usar as informações em um registro de associação, como o planejamento de amostragem de teste.</span><span class="sxs-lookup"><span data-stu-id="dc185-237">A manually generated quality order that refers to a purchase order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-238">Ordem de quarentena</span><span class="sxs-lookup"><span data-stu-id="dc185-238">Quarantine order</span></span></td>
<td><span data-ttu-id="dc185-239">Antes ou depois, a ordem de quarentena é relatada como concluída ou terminada</span><span class="sxs-lookup"><span data-stu-id="dc185-239">Before or after the quarantine order is reported as finished or ended</span></span></td>
<td><span data-ttu-id="dc185-240">Ordens de qualidade que exigem testes destrutivos não podem ser geradas.</span><span class="sxs-lookup"><span data-stu-id="dc185-240">Quality orders that require destructive tests can&#39;t be generated.</span></span> <span data-ttu-id="dc185-241">Presume-se que a funcionalidade de ordem de quarentena controla o descarte do material destruído.</span><span class="sxs-lookup"><span data-stu-id="dc185-241">It&#39;s assumed that the quarantine order functionality handles the disposition of the material that is destroyed.</span></span></td>
<td><span data-ttu-id="dc185-242">O requisito para uma ordem de qualidade pode refletir um site, item ou fornecedores específicos ou uma combinação destas condições.</span><span class="sxs-lookup"><span data-stu-id="dc185-242">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="dc185-243">Uma ordem de qualidade gerada manualmente que se refere a uma ordem de quarentena pode usar as informações em um registro de associação, como o planejamento de amostragem de teste.</span><span class="sxs-lookup"><span data-stu-id="dc185-243">A manually generated quality order that refers to a quarantine order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-244">Ordem de venda</span><span class="sxs-lookup"><span data-stu-id="dc185-244">Sales order</span></span></td>
<td><span data-ttu-id="dc185-245">Antes de uma atualização programada do processo de separação ou da guia de remessa dos itens que estão sendo enviados</span><span class="sxs-lookup"><span data-stu-id="dc185-245">Before a scheduled picking process or packing slip update for the items that are being shipped</span></span></td>
<td><span data-ttu-id="dc185-246">Em qualquer etapa</span><span class="sxs-lookup"><span data-stu-id="dc185-246">At any step</span></span></td>
<td><span data-ttu-id="dc185-247">O requisito para uma ordem de qualidade pode refletir um determinado site, ou cliente ou uma combinação dessas condições.</span><span class="sxs-lookup"><span data-stu-id="dc185-247">The requirement for a quality order can reflect a particular site, item, or customer, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="dc185-248">Uma ordem de qualidade gerada manualmente que se refere à ordem de compra pode usar informações em um registro de associação de qualidade, como o planejamento de amostragem de teste.</span><span class="sxs-lookup"><span data-stu-id="dc185-248">A manually generated quality order that refers to a sales order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-249">Ordem de produção</span><span class="sxs-lookup"><span data-stu-id="dc185-249">Production order</span></span></td>
<td><span data-ttu-id="dc185-250">Antes ou depois, a quantidade concluída para a ordem de produção é relatada</span><span class="sxs-lookup"><span data-stu-id="dc185-250">Before or after the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="dc185-251">Depois que a quantidade concluída para a ordem de produção é relatada</span><span class="sxs-lookup"><span data-stu-id="dc185-251">After the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="dc185-252">O requisito para uma ordem de qualidade pode refletir um site ou item particulares ou uma combinação dessas condições.</span><span class="sxs-lookup"><span data-stu-id="dc185-252">The requirement for a quality order can reflect a particular site or item, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="dc185-253">Uma ordem de qualidade gerada manualmente que se refere a uma ordem de produção em um registro de associação de qualidade, como o plano de amostragem de teste.</span><span class="sxs-lookup"><span data-stu-id="dc185-253">A manually generated quality order that refers to a production order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-254">Ordem de produção que tem uma operação de rota</span><span class="sxs-lookup"><span data-stu-id="dc185-254">Production order that has a route operation</span></span></td>
<td><span data-ttu-id="dc185-255">Antes ou depois da conclusão do relatório para uma operação</span><span class="sxs-lookup"><span data-stu-id="dc185-255">Before or after the report is finished for an operation</span></span></td>
<td><span data-ttu-id="dc185-256">Depois da conclusão de produção de relatório para a última operação</span><span class="sxs-lookup"><span data-stu-id="dc185-256">After the reporting production is finished for the last operation</span></span></td>
<td><span data-ttu-id="dc185-257">O requisito para uma ordem de qualidade pode refletir em um site, item ou recursos de operações ou a combinação dessas condições.</span><span class="sxs-lookup"><span data-stu-id="dc185-257">The requirement for a quality order can reflect a particular, site, item, or operations resource, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="dc185-258">Uma ordem de qualidade gerada manualmente que se refere a uma operação de rota em um registro de associação de qualidade, como o plano de amostragem de teste.</span><span class="sxs-lookup"><span data-stu-id="dc185-258">A manually generated quality order that refers to a route operation can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="dc185-259">Estoque</span><span class="sxs-lookup"><span data-stu-id="dc185-259">Inventory</span></span></td>
<td><span data-ttu-id="dc185-260">Uma ordem de qualidade não pode ser gerada automaticamente para uma transação em um diário de estoque ou para a transação de ordem de transferências.</span><span class="sxs-lookup"><span data-stu-id="dc185-260">A quality order cannot be automatically generated for a transaction in an inventory journal or for transfer order transactions.</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="dc185-261">Uma ordem de qualidade deve ser criada manualmente para a quantidade em estoque de um item.</span><span class="sxs-lookup"><span data-stu-id="dc185-261">A quality order must be created manually for an item&#39;s inventory quantity.</span></span> <span data-ttu-id="dc185-262">O estoque físico disponível do item é necessário.</span><span class="sxs-lookup"><span data-stu-id="dc185-262">Physical on-hand inventory is required.</span></span></td>
</tr>
</tbody>
</table>

## <a name="quality-order-auto-generation-examples"></a><span data-ttu-id="dc185-263">Exemplos de geração automática de ordens de qualidade</span><span class="sxs-lookup"><span data-stu-id="dc185-263">Quality order auto-generation examples</span></span>

### <a name="purchasing"></a><span data-ttu-id="dc185-264">Comprando</span><span class="sxs-lookup"><span data-stu-id="dc185-264">Purchasing</span></span>

<span data-ttu-id="dc185-265">Na compra, se você definir o campo **Tipo de evento** como **Recebimento de produtos** e o campo **Execução** como **Após** na página **Associações de qualidade**, você obterá os seguintes resultados:</span><span class="sxs-lookup"><span data-stu-id="dc185-265">In purchasing, if you set the **Event type** field to **Product receipt** and the **Execution** field to **After** on the **Quality associations** page, you get the following results:</span></span> 

- <span data-ttu-id="dc185-266">Se a opção **Quantidade por atualização** for definida como **Yes**, uma ordem de qualidade é gerada para cada recebimento em relação à ordem de qualidade, com base na quantidade e nas configurações recebidas na amostra do item.</span><span class="sxs-lookup"><span data-stu-id="dc185-266">If the **Per updated quantity** option is set to **Yes**, a quality order is generated for every receipt against the purchase order, based on the received quantity and settings in the item sampling.</span></span> <span data-ttu-id="dc185-267">Sempre que uma quantidade é recebida em relação à ordem de compra, novos pedidos de qualidade são gerados com base na quantidade recém-recebida.</span><span class="sxs-lookup"><span data-stu-id="dc185-267">Every time that a quantity is received against the purchase order, new quality orders are generated based on the newly received quantity.</span></span>
- <span data-ttu-id="dc185-268">Se a opção **Quantidade por atualização** for definida como **Não**, uma ordem de qualidade será gerada para o primeiro recebimento em relação à ordem de qualidade, com base na quantidade recebida.</span><span class="sxs-lookup"><span data-stu-id="dc185-268">If the **Per updated quantity** option is set to **No**, a quality order is generated for the first receipt against the purchase order, based on the received quantity.</span></span> <span data-ttu-id="dc185-269">Além disso, uma ou mais ordens de qualidade são criadas com base na quantidade restante, dependendo das dimensões de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="dc185-269">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions.</span></span> <span data-ttu-id="dc185-270">Os pedidos de qualidade não são gerados para recebimentos subsequentes em relação à ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="dc185-270">Quality orders aren't generated for subsequent receipts against the purchase order.</span></span>

### <a name="production"></a><span data-ttu-id="dc185-271">Produção</span><span class="sxs-lookup"><span data-stu-id="dc185-271">Production</span></span>

<span data-ttu-id="dc185-272">Na produção, se você definir o campo **Tipo de evento** como **Relatar como concluído** e o campo **Execução** como **Após** na página **Associações de qualidade**, você obterá os seguintes resultados:</span><span class="sxs-lookup"><span data-stu-id="dc185-272">In production, if you set the **Event type** field to **Report as finished** and the **Execution** field to **After** on the **Quality associations** page, you get the following results:</span></span>

- <span data-ttu-id="dc185-273">Se a opção **Quantidade por atualização** for definida como **Yes**, uma ordem de qualidade é gerada com base em todas as quantidades e configurações finalizadas na amostra do item.</span><span class="sxs-lookup"><span data-stu-id="dc185-273">If the **Per updated quantity** option is set to **Yes**, a quality order is generated based on every finished quantity and settings in the item sampling.</span></span> <span data-ttu-id="dc185-274">Sempre que uma quantidade é relatada como concluída em relação à ordem de produção, novas ordens de qualidade são geradas com base na quantidade recém-concluída.</span><span class="sxs-lookup"><span data-stu-id="dc185-274">Every time that a quantity is reported as finished against the production order, new quality orders are generated based on newly finished quantity.</span></span> <span data-ttu-id="dc185-275">Essa lógica de geração é consistente com a compra.</span><span class="sxs-lookup"><span data-stu-id="dc185-275">This generation logic is consistent with purchasing.</span></span>
- <span data-ttu-id="dc185-276">Se a opção **Quantidade por atualização** for definida como **Não**, uma ordem de qualidade é gerada na primeira vez que uma quantidade é relatada como concluída, com base na quantidade concluída.</span><span class="sxs-lookup"><span data-stu-id="dc185-276">If the **Per updated quantity** option is set to **No**, a quality order is generated the first time that a quantity is reported as finished, based on the finished quantity.</span></span> <span data-ttu-id="dc185-277">Além disso, uma ou mais ordens de qualidade são criadas com base na quantidade restante, dependendo das dimensões de rastreamento da amostra do item.</span><span class="sxs-lookup"><span data-stu-id="dc185-277">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions of the item sampling.</span></span> <span data-ttu-id="dc185-278">As ordens de qualidade não são geradas para quantidades concluídas subsequentes.</span><span class="sxs-lookup"><span data-stu-id="dc185-278">Quality orders aren't generated for subsequent finished quantities.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="dc185-279">Especificação de qualidade</span><span class="sxs-lookup"><span data-stu-id="dc185-279">Quality specification</span></span></th>
<th><span data-ttu-id="dc185-280">Quantidade por atualização</span><span class="sxs-lookup"><span data-stu-id="dc185-280">Per updated quantity</span></span></th>
<th><span data-ttu-id="dc185-281">Por dimensão de rastreamento</span><span class="sxs-lookup"><span data-stu-id="dc185-281">Per tracking dimension</span></span></th>
<th><span data-ttu-id="dc185-282">Resultado</span><span class="sxs-lookup"><span data-stu-id="dc185-282">Result</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="dc185-283">Porcentagem: 10%</span><span class="sxs-lookup"><span data-stu-id="dc185-283">Percentage: 10%</span></span></td>
<td><span data-ttu-id="dc185-284">Sim</span><span class="sxs-lookup"><span data-stu-id="dc185-284">Yes</span></span></td>
<td>
<p><span data-ttu-id="dc185-285">Nº do lote: não</span><span class="sxs-lookup"><span data-stu-id="dc185-285">Batch number: No</span></span></p>
<p><span data-ttu-id="dc185-286">Número de série: não</span><span class="sxs-lookup"><span data-stu-id="dc185-286">Serial number: No</span></span></p>
</td>
<td>
<p><span data-ttu-id="dc185-287">Quantidade da ordem: 100</span><span class="sxs-lookup"><span data-stu-id="dc185-287">Order quantity: 100</span></span></p>
<ol>
<li><span data-ttu-id="dc185-288">Relatar como concluído para 30</span><span class="sxs-lookup"><span data-stu-id="dc185-288">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="dc185-289">Ordem de qualidade nº 1 para 3 (10% de 30)</span><span class="sxs-lookup"><span data-stu-id="dc185-289">Quality order #1 for 3 (10% of 30)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="dc185-290">Relatar como concluído para 70</span><span class="sxs-lookup"><span data-stu-id="dc185-290">Report as finished for 70</span></span>
<ul>
<li><span data-ttu-id="dc185-291">Ordem de qualidade nº 2 para 7 (10% da quantidade restante da ordem, que é igual a 70 neste caso)</span><span class="sxs-lookup"><span data-stu-id="dc185-291">Quality order #2 for 7 (10% of the remaining order quantity, which equals 70 in this case)</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="dc185-292">Quantidade fixa: 1</span><span class="sxs-lookup"><span data-stu-id="dc185-292">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="dc185-293">Não</span><span class="sxs-lookup"><span data-stu-id="dc185-293">No</span></span></td>
<td>
<p><span data-ttu-id="dc185-294">Nº do lote: não</span><span class="sxs-lookup"><span data-stu-id="dc185-294">Batch number: No</span></span></p>
<p><span data-ttu-id="dc185-295">Número de série: não</span><span class="sxs-lookup"><span data-stu-id="dc185-295">Serial number: No</span></span></p>
</td>
<td><span data-ttu-id="dc185-296">Quantidade da ordem: 100</span><span class="sxs-lookup"><span data-stu-id="dc185-296">Order quantity: 100</span></span>
<ol>
<li><span data-ttu-id="dc185-297">Relatar como concluído para 30</span><span class="sxs-lookup"><span data-stu-id="dc185-297">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="dc185-298">Ordem de qualidade nº 1 para 1 (para a primeira quantidade relatada como concluída, que tem um valor fixo de 1)</span><span class="sxs-lookup"><span data-stu-id="dc185-298">Quality order #1 for 1 (for the first reported-as-finished quantity, which has a fixed value of 1)</span></span></li>
<li><span data-ttu-id="dc185-299">Ordem de qualidade nº 2 para 1 (para a quantidade restante, que ainda possui um valor fixo de 1)</span><span class="sxs-lookup"><span data-stu-id="dc185-299">Quality order #2 for 1 (for the remaining quantity, which still has a fixed value of 1)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="dc185-300">Relatar como concluído para 10</span><span class="sxs-lookup"><span data-stu-id="dc185-300">Report as finished for 10</span></span>
<ul>
<li><span data-ttu-id="dc185-301">Nenhuma ordem de qualidade é criada.</span><span class="sxs-lookup"><span data-stu-id="dc185-301">No quality orders are created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="dc185-302">Relatar como concluído para 60</span><span class="sxs-lookup"><span data-stu-id="dc185-302">Report as finished for 60</span></span>
<ul>
<li><span data-ttu-id="dc185-303">Nenhuma ordem de qualidade é criada.</span><span class="sxs-lookup"><span data-stu-id="dc185-303">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="dc185-304">Quantidade fixa: 1</span><span class="sxs-lookup"><span data-stu-id="dc185-304">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="dc185-305">Sim</span><span class="sxs-lookup"><span data-stu-id="dc185-305">Yes</span></span></td>
<td>
<p><span data-ttu-id="dc185-306">Nº do lote: sim</span><span class="sxs-lookup"><span data-stu-id="dc185-306">Batch number: Yes</span></span></p>
<p><span data-ttu-id="dc185-307">Número de série: sim</span><span class="sxs-lookup"><span data-stu-id="dc185-307">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="dc185-308">Quantidade da ordem: 10</span><span class="sxs-lookup"><span data-stu-id="dc185-308">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="dc185-309">Relatar como concluído para 3: 1 para nº b1, nº s1; 1 para nº b2, nº s2; e 1 para nº b3, nº s3</span><span class="sxs-lookup"><span data-stu-id="dc185-309">Report as finished for 3: 1 for #b1, #s1; 1 for #b2, #s2; and 1 for #b3, #s3</span></span>
<ul>
<li><span data-ttu-id="dc185-310">Ordem de qualidade nº 1 para 1 do lote nº b1, série nº s1</span><span class="sxs-lookup"><span data-stu-id="dc185-310">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="dc185-311">Ordem de qualidade nº 2 para 1 do lote nº b2, série nº s2</span><span class="sxs-lookup"><span data-stu-id="dc185-311">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="dc185-312">Ordem de qualidade nº 3 para 1 do lote nº b3, série nº s3</span><span class="sxs-lookup"><span data-stu-id="dc185-312">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
</ul>
</li>
<li><span data-ttu-id="dc185-313">Relatar como concluído para 2: 1 para nº b4, nº s4; e 1 para nº b5, nº s5</span><span class="sxs-lookup"><span data-stu-id="dc185-313">Report as finished for 2: 1 for #b4, #s4; and 1 for #b5, #s5</span></span>
<ul>
<li><span data-ttu-id="dc185-314">Ordem de qualidade nº 4 para 1 do lote nº b4, série nº s4</span><span class="sxs-lookup"><span data-stu-id="dc185-314">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
<li><span data-ttu-id="dc185-315">Ordem de qualidade nº 5 para 1 do lote nº b5, série nº s5</span><span class="sxs-lookup"><span data-stu-id="dc185-315">Quality order #5 for 1 of batch #b5, serial #s5</span></span></li>
</ul>
</li>
</ol>
<p><span data-ttu-id="dc185-316"><strong>Observação:</strong> o lote pode ser reutilizado.</span><span class="sxs-lookup"><span data-stu-id="dc185-316"><strong>Note:</strong> The batch can be reused.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="dc185-317">Quantidade fixa: 2</span><span class="sxs-lookup"><span data-stu-id="dc185-317">Fixed quantity: 2</span></span></td>
<td><span data-ttu-id="dc185-318">Não</span><span class="sxs-lookup"><span data-stu-id="dc185-318">No</span></span></td>
<td>
<p><span data-ttu-id="dc185-319">Nº do lote: sim</span><span class="sxs-lookup"><span data-stu-id="dc185-319">Batch number: Yes</span></span></p>
<p><span data-ttu-id="dc185-320">Número de série: sim</span><span class="sxs-lookup"><span data-stu-id="dc185-320">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="dc185-321">Quantidade da ordem: 10</span><span class="sxs-lookup"><span data-stu-id="dc185-321">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="dc185-322">Relatar como concluído para 4: 1 para nº b1, nº s1; 1 para nº b2, nº s2; 1 para nº b3, nº s3; e 1 para nº b4, nº s4</span><span class="sxs-lookup"><span data-stu-id="dc185-322">Report as finished for 4: 1 for #b1, #s1; 1 for #b2, #s2; 1 for #b3, #s3; and 1 for #b4, #s4</span></span>
<ul>
<li><span data-ttu-id="dc185-323">Ordem de qualidade nº 1 para 1 do lote nº b1, série nº s1</span><span class="sxs-lookup"><span data-stu-id="dc185-323">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="dc185-324">Ordem de qualidade nº 2 para 1 do lote nº b2, série nº s2</span><span class="sxs-lookup"><span data-stu-id="dc185-324">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="dc185-325">Ordem de qualidade nº 3 para 1 do lote nº b3, série nº s3</span><span class="sxs-lookup"><span data-stu-id="dc185-325">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
<li><span data-ttu-id="dc185-326">Ordem de qualidade nº 4 para 1 do lote nº b4, série nº s4</span><span class="sxs-lookup"><span data-stu-id="dc185-326">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
</ul>
<ul>
<li><span data-ttu-id="dc185-327">Ordem de qualidade nº 5 para 2, sem referência a um lote e um número de série</span><span class="sxs-lookup"><span data-stu-id="dc185-327">Quality order #5 for 2, without a reference to a batch and a serial number</span></span></li>
</ul>
</li>
<li><span data-ttu-id="dc185-328">Relatar como concluído para 6: 1 para nº b5, nº s5; 1 para nº b6, nº s6; 1 para nº b7, nº s7; 1 para nº b8, nº s8; 1 para nº b9, nº s9; e 1 para nº b10, nº s10</span><span class="sxs-lookup"><span data-stu-id="dc185-328">Report as finished for 6: 1 for #b5, #s5; 1 for #b6, #s6; 1 for #b7, #s7; 1 for #b8, #s8; 1 for #b9, #s9; and 1 for #b10, #s10</span></span>
<ul>
<li><span data-ttu-id="dc185-329">Nenhuma ordem de qualidade é criada.</span><span class="sxs-lookup"><span data-stu-id="dc185-329">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="dc185-330">O recurso *Gerenciamento de qualidade para processos de depósito* adiciona recursos para o processamento da ordem de qualidade para produção com o **Tipo de evento** definido como *Relatar como concluído* e **Em execução** definido como *Depois*, e para compras com o **Tipo de evento** definido como *Registro*.</span><span class="sxs-lookup"><span data-stu-id="dc185-330">The *Quality management for warehouse processes* feature adds capabilities for quality order processing for production with **Event type** set to *Report as finished* and **Execution** set to *After*, and for purchases with **Event type** set to *Registration*.</span></span> <span data-ttu-id="dc185-331">Para obter detalhes, consulte [Gerenciamento de qualidade para processos de depósito](quality-management-for-warehouses-processes.md).</span><span class="sxs-lookup"><span data-stu-id="dc185-331">For details, see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md).</span></span>

## <a name="quality-management-pages"></a><span data-ttu-id="dc185-332">Páginas de gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="dc185-332">Quality management pages</span></span>
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc185-333">Página</span><span class="sxs-lookup"><span data-stu-id="dc185-333">Page</span></span></th>
<th><span data-ttu-id="dc185-334">descrição</span><span class="sxs-lookup"><span data-stu-id="dc185-334">Description</span></span></th>
<th><span data-ttu-id="dc185-335">Exemplo</span><span class="sxs-lookup"><span data-stu-id="dc185-335">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="dc185-336">Associações de qualidade</span><span class="sxs-lookup"><span data-stu-id="dc185-336">Quality associations</span></span></td>
<td><span data-ttu-id="dc185-337">Consulte as seções anteriores deste artigo.</span><span class="sxs-lookup"><span data-stu-id="dc185-337">See the previous sections of this article.</span></span></td>
<td><span data-ttu-id="dc185-338">Uma associação de qualidade define todas as informações a seguir para uma ordem de qualidade que é gerada:</span><span class="sxs-lookup"><span data-stu-id="dc185-338">A quality association defines all the following information for a quality order that is generated:</span></span>
<ul>
<li><span data-ttu-id="dc185-339">O evento da transação</span><span class="sxs-lookup"><span data-stu-id="dc185-339">The transaction event</span></span></li>
<li><span data-ttu-id="dc185-340">O conjunto de testes que devem ser executados nos itens</span><span class="sxs-lookup"><span data-stu-id="dc185-340">The set of tests that must be performed on the items</span></span></li>
<li><span data-ttu-id="dc185-341">O AQL</span><span class="sxs-lookup"><span data-stu-id="dc185-341">The AQL</span></span></li>
<li><span data-ttu-id="dc185-342">O plano de amostragem</span><span class="sxs-lookup"><span data-stu-id="dc185-342">The sampling plan</span></span></li>
</ul>
<span data-ttu-id="dc185-343">É necessário definir uma associação de qualidade para cada variação em um processo comercial que requer a geração automática de ordens de qualidade.</span><span class="sxs-lookup"><span data-stu-id="dc185-343">You must define a quality association for each variation in a business process that requires automatic generation of quality orders.</span></span> <span data-ttu-id="dc185-344">Por exemplo, uma ordem de qualidade pode ser gerada nos processos comerciais para ordens de compra, ordens de quarentena, ordens de venda, e ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="dc185-344">For example, a quality order can be generated in the business processes for purchase orders, quarantine orders, sales orders, and production orders.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="dc185-345">Testes</span><span class="sxs-lookup"><span data-stu-id="dc185-345">Tests</span></span></td>
<td><span data-ttu-id="dc185-346">Use esta página para definir e exibir os testes individuais que determinam se seus produtos atendem às especificações de qualidade.</span><span class="sxs-lookup"><span data-stu-id="dc185-346">Use this page to define and view the individual tests that determine whether your products meet quality specifications.</span></span> <span data-ttu-id="dc185-347">Você pode atribuir um ou mais testes individuais a um grupo de teste.</span><span class="sxs-lookup"><span data-stu-id="dc185-347">You can assign one or more individual tests to a test group.</span></span> <span data-ttu-id="dc185-348">Nesse caso, você também pode especificar informações específicas, como os valores de medida aceitáveis.</span><span class="sxs-lookup"><span data-stu-id="dc185-348">In this case, you also specify test-specific information, such as the acceptable measurement values.</span></span> <span data-ttu-id="dc185-349">Os valores de medição são usados para testes quantitativos, e as variáveis de teste são usadas para testes qualitativos.</span><span class="sxs-lookup"><span data-stu-id="dc185-349">Measurement values are used for quantitative tests, and test variables are used for qualitative tests.</span></span>
<ul>
<li><span data-ttu-id="dc185-350">Um teste quantitativo tem um tipo de teste <strong>Inteiro</strong> ou <strong>Fração</strong>, e também tem uma unidade de medida designada.</span><span class="sxs-lookup"><span data-stu-id="dc185-350">A quantitative test has a test type of <strong>Integer</strong> or <strong>Fraction</strong>, and also has a designated unit of measure.</span></span> <span data-ttu-id="dc185-351">As especificações de qualidade e os resultados de teste são expressos em números.</span><span class="sxs-lookup"><span data-stu-id="dc185-351">Quality specifications and test results are expressed as numbers.</span></span></li>
<li><span data-ttu-id="dc185-352">Um teste qualitativo tem o tipo de teste <strong>Opção</strong>.</span><span class="sxs-lookup"><span data-stu-id="dc185-352">A qualitative test has a test type of <strong>Option</strong>.</span></span> <span data-ttu-id="dc185-353">Os testes qualitativos requerem informações adicionais sobre a variável de teste que está sendo medida e suas opções enumeradas.</span><span class="sxs-lookup"><span data-stu-id="dc185-353">Qualitative tests require additional information about the test variable that is being measured and its enumerated options.</span></span> <span data-ttu-id="dc185-354">As especificações de qualidade e os resultados de teste são expressos de acordo com um resultado.</span><span class="sxs-lookup"><span data-stu-id="dc185-354">Quality specifications and test results are expressed according to an outcome.</span></span></li>
</ul></td>
<td><span data-ttu-id="dc185-355">Uma fábrica realiza dois testes em material adquirido: um teste quantitativo sobre a qualidade do material e um teste qualitativo sobre danos de embalagem.</span><span class="sxs-lookup"><span data-stu-id="dc185-355">A manufacturing company performs two tests on purchased material: a quantitative test about material quality and a qualitative test about packaging damage.</span></span> <span data-ttu-id="dc185-356">A empresa define informações adicionais sobre o teste qualitativo para identificar a variável de teste (embalagem danificada) e seus resultados.</span><span class="sxs-lookup"><span data-stu-id="dc185-356">The company defines additional information about the qualitative test to identify the test variable (damaged packaging) and its outcomes.</span></span> <span data-ttu-id="dc185-357">A empresa usa a página <strong>Grupos de teste</strong> para atribuir os dois testes a um grupo de testes e especificar informações específicas do teste.</span><span class="sxs-lookup"><span data-stu-id="dc185-357">The company uses the <strong>Test groups</strong> page to assign the two tests to a test group and to specify the test-specific information.</span></span> <span data-ttu-id="dc185-358">O grupo de testes é atribuído a uma ordem de qualidade, de tal modo que a empresa possa informar resultados de teste para os dois testes.</span><span class="sxs-lookup"><span data-stu-id="dc185-358">The test group is assigned to a quality order, so that the company can report test results for the two tests.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="dc185-359">Grupos de teste</span><span class="sxs-lookup"><span data-stu-id="dc185-359">Test groups</span></span></td>
<td><span data-ttu-id="dc185-360">Use esta página para configurar, editar e exibir grupos de testes e testes individuais atribuídos a um grupo de testes.</span><span class="sxs-lookup"><span data-stu-id="dc185-360">Use this page to set up, edit, and view test groups and the individual tests that are assigned to a test group.</span></span> <span data-ttu-id="dc185-361">O painel superior exibe grupos de testes e o painel inferior exibe os testes atribuídos a um grupo de testes selecionado.</span><span class="sxs-lookup"><span data-stu-id="dc185-361">The upper pane displays test groups, and the lower pane displays the tests that are assigned to a selected test group.</span></span> <span data-ttu-id="dc185-362">Você atribui várias políticas a um grupo de testes, como um plano de amostragem, um AQL, e o requisito para testes destrutivos.</span><span class="sxs-lookup"><span data-stu-id="dc185-362">You assign several policies to a test group, such as a sampling plan, an AQL, and the requirement for destructive testing.</span></span> <span data-ttu-id="dc185-363">Quando você atribui um teste individual a um grupo de testes, você define informações adicionais, como a sequência, os documentos, e as datas de validade.</span><span class="sxs-lookup"><span data-stu-id="dc185-363">When you assign an individual test to a test group, you define additional information, such as the sequence, documents, and validity dates.</span></span> <span data-ttu-id="dc185-364">Para um teste quantitativo, as informações que você define também incluem os valores de medida aceitáveis.</span><span class="sxs-lookup"><span data-stu-id="dc185-364">For a quantitative test, the information that you define also includes the acceptable measurement values.</span></span> <span data-ttu-id="dc185-365">Para um teste qualitativo, as informações incluem a variável de teste e o resultado padrão.</span><span class="sxs-lookup"><span data-stu-id="dc185-365">For a qualitative test, the information includes the test variable and default outcome.</span></span> <span data-ttu-id="dc185-366">O grupo de testes atribuído a uma ordem de qualidade define o conjunto padrão de testes que devem ser realizados no item específico.</span><span class="sxs-lookup"><span data-stu-id="dc185-366">The test group that is assigned to a quality order defines the default set of tests that must be performed on the specified item.</span></span> <span data-ttu-id="dc185-367">No entanto, você pode adicionar, excluir, ou alterar os testes na ordem de qualidade.</span><span class="sxs-lookup"><span data-stu-id="dc185-367">However, you can add, delete, or change tests on the quality order.</span></span> <span data-ttu-id="dc185-368">Os resultados do teste são relatados para cada teste em uma ordem de qualidade.</span><span class="sxs-lookup"><span data-stu-id="dc185-368">Test results are reported for each test on a quality order.</span></span></td>
<td><span data-ttu-id="dc185-369">Uma fábrica define um grupo de testes para cada variação de suas diretrizes de qualidade.</span><span class="sxs-lookup"><span data-stu-id="dc185-369">A manufacturing company defines a test group for each variation of its quality guidelines.</span></span> <span data-ttu-id="dc185-370">Os vários grupos de testes refletem diferenças nos planos de amostragem, nos conjuntos de testes que precisam ser executados juntos, na AQL, e em outros fatores.</span><span class="sxs-lookup"><span data-stu-id="dc185-370">The various test groups reflect differences in the sampling plans, the sets of tests that must be performed together, the AQL, and other factors.</span></span> <span data-ttu-id="dc185-371">Para testes quantitativos, também existem diferenças nos valores de medida aceitáveis.</span><span class="sxs-lookup"><span data-stu-id="dc185-371">For quantitative tests, there are also differences in the acceptable measurement values.</span></span> <span data-ttu-id="dc185-372">Para impor suas diretrizes de qualidade, a empresa atribui um grupo de testes a cada regra para gerar automaticamente ordens de qualidade na página <strong>Associações de qualidade</strong>, e também atribui um grupo de testes às ordens de qualidade criadas manualmente.</span><span class="sxs-lookup"><span data-stu-id="dc185-372">To enforce its quality guidelines, the company assigns a test group to each rule for automatically generating quality orders on the <strong>Quality associations</strong> page, and also assigns a test group to quality orders that are manually created.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="dc185-373">Grupos de qualidade de item</span><span class="sxs-lookup"><span data-stu-id="dc185-373">Item quality groups</span></span></td>
<td><span data-ttu-id="dc185-374">Use esta página para configurar, editar e exibir os itens atribuídos a um grupo de qualidade ou os grupos de qualidade atribuídos a um item.</span><span class="sxs-lookup"><span data-stu-id="dc185-374">Use this page to set up, edit, and view the items that are assigned to a quality group or the quality groups that are assigned to an item.</span></span> <span data-ttu-id="dc185-375">Um grupo de qualidade representa requisitos de teste comuns para itens.</span><span class="sxs-lookup"><span data-stu-id="dc185-375">A quality group represents common testing requirements for items.</span></span> <span data-ttu-id="dc185-376">Após definir os requisitos de teste da página <strong>Grupos de teste</strong>, você pode definir as regras para gerar automaticamente as ordens de qualidade.</span><span class="sxs-lookup"><span data-stu-id="dc185-376">After you define the test requirements on the <strong>Test groups</strong> page, you can define the rules for automatically generating quality orders.</span></span> <span data-ttu-id="dc185-377">Para simplificar o processo, você não define regras para itens individuais.</span><span class="sxs-lookup"><span data-stu-id="dc185-377">To simplify the process, you don&#39;t define rules for individual items.</span></span> <span data-ttu-id="dc185-378">Em vez disso, defina regras para um grupo de qualidade, usando a página <strong>Associações de qualidade</strong>.</span><span class="sxs-lookup"><span data-stu-id="dc185-378">Instead, you define rules for a quality group, by using the <strong>Quality associations</strong> page.</span></span> <span data-ttu-id="dc185-379">Você também pode usar a página <strong>Grupos de qualidade de item</strong> para que um grupo de qualidade selecionado atribua itens relevantes ao grupo.</span><span class="sxs-lookup"><span data-stu-id="dc185-379">You can also use the <strong>Item quality groups</strong> page for a selected quality group to assign relevant items to that group.</span></span> <span data-ttu-id="dc185-380">Você também pode usar a página <strong>Grupos de qualidade de item</strong> para que um item selecionado atribua grupos de qualidade relevantes ao item.</span><span class="sxs-lookup"><span data-stu-id="dc185-380">You can also use the <strong>Item quality groups</strong> page for a selected item to assign relevant quality groups to that item.</span></span></td>
<td><span data-ttu-id="dc185-381">Uma fábrica compra diversas matérias-primas que têm os mesmos requisitos de teste para inspeção de entrada.</span><span class="sxs-lookup"><span data-stu-id="dc185-381">A manufacturing company purchases various raw materials that have the same testing requirements for incoming inspection.</span></span> <span data-ttu-id="dc185-382">A empresa define um grupo de qualidade e então atribui os números de item associados com as matérias-primas ao grupo.</span><span class="sxs-lookup"><span data-stu-id="dc185-382">The company defines a quality group and then assigns the item numbers that are associated with the raw materials to that group.</span></span> <span data-ttu-id="dc185-383">Posteriormente, a empresa compra um novo tipo de matéria-prima que têm os mesmos requisitos de teste.</span><span class="sxs-lookup"><span data-stu-id="dc185-383">Later, the company purchases a new type of raw material that has the same testing requirements.</span></span> <span data-ttu-id="dc185-384">Em vez de configurar novos requisitos de teste para o novo material, a empresa adiciona o número do item para o novo material no grupo de qualidade existente.</span><span class="sxs-lookup"><span data-stu-id="dc185-384">Instead of setting up new testing requirements for the new material, the company adds the item number for the new material to the existing quality group.</span></span> <span data-ttu-id="dc185-385">A mesma fábrica também produz itens com os mesmos requisitos de teste de produção e remete os itens com o mesmo requisito para a execução de testes antes da remessa.</span><span class="sxs-lookup"><span data-stu-id="dc185-385">The same manufacturing company also produces items that have the same production testing requirements and ships items that have the same requirement for pre-shipment testing.</span></span> <span data-ttu-id="dc185-386">A fábrica define dois grupos de qualidade adicionais e então atribui os números de item relevantes a cada grupo.</span><span class="sxs-lookup"><span data-stu-id="dc185-386">The company defines two additional quality groups and then assigns the relevant item numbers to each group.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="dc185-387">Teste de variáveis</span><span class="sxs-lookup"><span data-stu-id="dc185-387">Test variables</span></span></td>
<td><span data-ttu-id="dc185-388">Use esta página para definir e exibir as variáveis associadas a um teste qualitativo.</span><span class="sxs-lookup"><span data-stu-id="dc185-388">Use this page to define and view the variables that are associated with a qualitative test.</span></span> <span data-ttu-id="dc185-389">Para cada variável, você define os resultados enumerados que representam as opções possíveis.</span><span class="sxs-lookup"><span data-stu-id="dc185-389">For each variable, you define enumerated outcomes that represent the possible options.</span></span> <span data-ttu-id="dc185-390">Você define os testes na página <strong>Testes</strong>.</span><span class="sxs-lookup"><span data-stu-id="dc185-390">You define tests on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="dc185-391">Para testes qualitativos, você deve definir o tipo de teste como <strong>Opção</strong>.</span><span class="sxs-lookup"><span data-stu-id="dc185-391">For qualitative tests, you must set the test type to <strong>Option</strong>.</span></span> <span data-ttu-id="dc185-392">Use a página <strong>Grupos de teste</strong> para atribuir uma variável de teste a um teste individual.</span><span class="sxs-lookup"><span data-stu-id="dc185-392">Use the <strong>Test groups</strong> page to assign a test variable to an individual test.</span></span></td>
<td><span data-ttu-id="dc185-393">Uma fábrica que produz biscoitos usa um teste de inspeção para o produto acabado.</span><span class="sxs-lookup"><span data-stu-id="dc185-393">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="dc185-394">Esse teste de inspeção tem várias variáveis.</span><span class="sxs-lookup"><span data-stu-id="dc185-394">This inspection test has several variables.</span></span> <span data-ttu-id="dc185-395">Uma variável é sabor, e os possíveis resultados para essa variável são: bom e ruim.</span><span class="sxs-lookup"><span data-stu-id="dc185-395">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="dc185-396">Uma segunda variável é cor, e os possíveis resultados são: muito escuro, muito claro e correto.</span><span class="sxs-lookup"><span data-stu-id="dc185-396">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="dc185-397">Resultados do teste de variável</span><span class="sxs-lookup"><span data-stu-id="dc185-397">Test variable outcomes</span></span></td>
<td><span data-ttu-id="dc185-398">Use esta página para configurar, editar e exibir os possíveis resultados de teste de uma variável de teste associada a um teste qualitativo.</span><span class="sxs-lookup"><span data-stu-id="dc185-398">Use this page to set up, edit, and to view the possible test results for a test variable that is associated with a qualitative test.</span></span> <span data-ttu-id="dc185-399">Para cada resultado, você atribui um status de <strong>aprovado</strong> ou <strong>reprovado</strong>.</span><span class="sxs-lookup"><span data-stu-id="dc185-399">For each outcome, you assign a <strong>pass</strong> or <strong>fail</strong> status.</span></span> <span data-ttu-id="dc185-400">Você deve definir uma variável e seus resultados para cada teste qualitativo definido na página <strong>Testes</strong>.</span><span class="sxs-lookup"><span data-stu-id="dc185-400">You must define a variable and its outcomes for each qualitative test that is defined on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="dc185-401">(Para testes qualitativos, o tipo de teste é definido como <strong>Opção</strong> na página <strong>Testes</strong>.) Use os <strong>Grupos de testes</strong> para atribuir uma variável de teste e o resultado padrão a um teste qualitativo individual.</span><span class="sxs-lookup"><span data-stu-id="dc185-401">(For qualitative tests, the test type is set to <strong>Option</strong> on the <strong>Tests</strong> page.) Use the <strong>Test groups</strong> page to assign a test variable and the default outcome to an individual qualitative test.</span></span></td>
<td><span data-ttu-id="dc185-402">Uma fábrica que produz biscoitos usa um teste de inspeção para o produto acabado.</span><span class="sxs-lookup"><span data-stu-id="dc185-402">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="dc185-403">Esse teste de inspeção tem várias variáveis.</span><span class="sxs-lookup"><span data-stu-id="dc185-403">This inspection test has of several variables.</span></span> <span data-ttu-id="dc185-404">Uma variável é sabor, e os possíveis resultados para essa variável são: bom e ruim.</span><span class="sxs-lookup"><span data-stu-id="dc185-404">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="dc185-405">Uma segunda variável é cor, e os possíveis resultados são: muito escuro, muito claro e correto.</span><span class="sxs-lookup"><span data-stu-id="dc185-405">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span> <span data-ttu-id="dc185-406">Um status de <strong>aprovado</strong> ou <strong>reprovado</strong> é atribuído a cada resultado.</span><span class="sxs-lookup"><span data-stu-id="dc185-406">A status of <strong>pass</strong> or <strong>fail</strong> is assigned to each outcome.</span></span> <span data-ttu-id="dc185-407">Durante o teste de inspeção de cada variável, o inspetor informa o resultado do teste selecionando um dos resultados.</span><span class="sxs-lookup"><span data-stu-id="dc185-407">During the inspection test for each variable, the inspector reports the test result by selecting one of the outcomes.</span></span></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a><span data-ttu-id="dc185-408">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="dc185-408">Additional resources</span></span>
--------

[<span data-ttu-id="dc185-409">Processos de gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="dc185-409">Quality management processes</span></span>](quality-management-processes.md)

[<span data-ttu-id="dc185-410">​Gerenciamento de não conformidade​</span><span class="sxs-lookup"><span data-stu-id="dc185-410">Nonconformance management</span></span>](enable-nonconformance-management.md)

[<span data-ttu-id="dc185-411">Gestão de qualidade para processos de depósito</span><span class="sxs-lookup"><span data-stu-id="dc185-411">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)
