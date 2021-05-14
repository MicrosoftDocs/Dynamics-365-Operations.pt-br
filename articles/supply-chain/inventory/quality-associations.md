---
title: Associações de qualidade
description: Este tópico descreve como você pode usar associações de qualidade no Microsoft Dynamics 365 Supply Chain Management para gerar automaticamente ordens de qualidade relacionadas a seus processos de venda, compra e produção.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestAssociationTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2020-06-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0f46f09dc9b67cfb04d0320a071c2c739266af58
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956546"
---
# <a name="quality-associations"></a><span data-ttu-id="e32e7-103">Associações de qualidade</span><span class="sxs-lookup"><span data-stu-id="e32e7-103">Quality associations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e32e7-104">Este tópico descreve como você pode usar associações de qualidade no Microsoft Dynamics 365 Supply Chain Management para gerar automaticamente ordens de qualidade relacionadas a seus processos de venda, compra e produção.</span><span class="sxs-lookup"><span data-stu-id="e32e7-104">This topic describes how you can use quality associations in Microsoft Dynamics 365 Supply Chain Management to automatically generate quality orders that are related to your sales, purchase, and production processes.</span></span>

<span data-ttu-id="e32e7-105">Uma associação de qualidade define todas as informações a seguir para uma ordem de qualidade que é gerada:</span><span class="sxs-lookup"><span data-stu-id="e32e7-105">A quality association defines all the following information for a quality order that is generated:</span></span>

- <span data-ttu-id="e32e7-106">O evento da transação</span><span class="sxs-lookup"><span data-stu-id="e32e7-106">The transaction event</span></span>
- <span data-ttu-id="e32e7-107">O conjunto de testes que devem ser executados nos itens</span><span class="sxs-lookup"><span data-stu-id="e32e7-107">The set of tests that must be performed on the items</span></span>
- <span data-ttu-id="e32e7-108">O nível de qualidade aceitável (AQL)</span><span class="sxs-lookup"><span data-stu-id="e32e7-108">The acceptable quality level (AQL)</span></span>
- <span data-ttu-id="e32e7-109">O plano de amostragem</span><span class="sxs-lookup"><span data-stu-id="e32e7-109">The sampling plan</span></span>

<span data-ttu-id="e32e7-110">É necessário definir uma associação de qualidade para cada variação em um processo comercial que requer a geração automática de ordens de qualidade.</span><span class="sxs-lookup"><span data-stu-id="e32e7-110">You must define a quality association for each variation in a business process that requires automatic generation of quality orders.</span></span> <span data-ttu-id="e32e7-111">Por exemplo, uma ordem de qualidade pode ser gerada nos processos comerciais para ordens de compra, ordens de quarentena, ordens de venda, e ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="e32e7-111">For example, a quality order can be generated in the business processes for purchase orders, quarantine orders, sales orders, and production orders.</span></span>

## <a name="working-with-quality-associations"></a><span data-ttu-id="e32e7-112">Trabalhando com associações de qualidade</span><span class="sxs-lookup"><span data-stu-id="e32e7-112">Working with quality associations</span></span>

<span data-ttu-id="e32e7-113">O processo comercial que utiliza uma associação de qualidade pode estar relacionado a diversos documentos de origem, como ordens de compra, ordens de venda, ou ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="e32e7-113">The business process that uses a quality association can be related to various source documents, such as purchase orders, sales orders, or production orders.</span></span>

<span data-ttu-id="e32e7-114">Cada registro de associação de qualidade também define o conjunto de testes, o nível de qualidade aceitável (AQL) e o plano de amostragem que se aplicam às ordens de qualidade geradas.</span><span class="sxs-lookup"><span data-stu-id="e32e7-114">Each quality association record defines the set of tests, the AQL, and the sampling plan that applies to the quality orders that are generated.</span></span> <span data-ttu-id="e32e7-115">Um registro de associação de qualidade deve ser definido para cada variação em um processo de negócios.</span><span class="sxs-lookup"><span data-stu-id="e32e7-115">You must define a quality association record for each variation in a business process.</span></span> <span data-ttu-id="e32e7-116">Por exemplo, você pode configurar uma associação de qualidade que gera uma ordem de qualidade quando um recebimento de produto da ordem de produção é atualizado.</span><span class="sxs-lookup"><span data-stu-id="e32e7-116">For example, you can set up a quality association that generates a quality order when a purchase order product receipt is updated.</span></span> <span data-ttu-id="e32e7-117">Dependendo da configuração do plano de execução, o próprio processo de disparo pode ser bloqueado enquanto houver uma ordem de qualidade aberta.</span><span class="sxs-lookup"><span data-stu-id="e32e7-117">Depending on the setup of the execution plan, the triggering process itself can be blocked while there is an open quality order.</span></span> <span data-ttu-id="e32e7-118">Como alternativa, processos subsequentes, como o faturamento de ordens de compra, podem ser bloqueados.</span><span class="sxs-lookup"><span data-stu-id="e32e7-118">Alternatively, subsequent processes, such as purchase order invoicing, can be blocked.</span></span>

> [!NOTE]
> <span data-ttu-id="e32e7-119">Enquanto houver ordens de qualidade abertas, as quantidades de estoque serão automaticamente impedidas de serem fornecidas.</span><span class="sxs-lookup"><span data-stu-id="e32e7-119">While there are open quality orders, inventory quantities are automatically blocked from being issued.</span></span> <span data-ttu-id="e32e7-120">Dependendo da configuração do campo **Bloqueio total** na página **Amostragens de item**, a quantidade será a quantidade na ordem de qualidade ou a quantidade na linha do documento de origem.</span><span class="sxs-lookup"><span data-stu-id="e32e7-120">Depending on the setting of the **Full blocking** field on the **Item samplings** page, the quantity is either the quantity on the quality order or the quantity on the source document line.</span></span> <span data-ttu-id="e32e7-121">Para obter mais informações, consulte [Amostragem de item de gerenciamento de qualidade](quality-item-sampling.md).</span><span class="sxs-lookup"><span data-stu-id="e32e7-121">For more information, see [Quality management item sampling](quality-item-sampling.md).</span></span>

<span data-ttu-id="e32e7-122">Para um determinado processo empresarial, o registro de associação de qualidade identifica o evento e as condições para os quais uma ordem de qualidade é gerada.</span><span class="sxs-lookup"><span data-stu-id="e32e7-122">For a given business process, the quality association record identifies the event and conditions that a quality order is generated for.</span></span> <span data-ttu-id="e32e7-123">As condições podem ser específicas para um site ou uma entidade legal.</span><span class="sxs-lookup"><span data-stu-id="e32e7-123">The conditions can be specific to either a site or a legal entity.</span></span> <span data-ttu-id="e32e7-124">Uma ordem de qualidade que envolve testes destrutivos podem ser geradas somente quando existir um estoque para o evento.</span><span class="sxs-lookup"><span data-stu-id="e32e7-124">A quality order that involves destructive tests can be generated only when on-hand inventory exists for the event.</span></span>

<span data-ttu-id="e32e7-125">Para trabalhar com associações de qualidade, vá para **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Associações de qualidade**.</span><span class="sxs-lookup"><span data-stu-id="e32e7-125">To work with quality associations, go to **Inventory management \> Setup \> Quality control \> Quality associations**.</span></span> <span data-ttu-id="e32e7-126">Os exemplos a seguir mostram como um registro de associação de qualidade é definido para as variações em cada processo empresarial.</span><span class="sxs-lookup"><span data-stu-id="e32e7-126">The following examples show how a quality association record is defined for the variations in each business process.</span></span> <span data-ttu-id="e32e7-127">Para cada exemplo, a tabela a seguir resume os eventos e as condições que são definidas por um registro de associação de qualidade.</span><span class="sxs-lookup"><span data-stu-id="e32e7-127">For each example, the following table summarizes the events and conditions that are defined by a quality association record.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e32e7-128">Tipo de referência</span><span class="sxs-lookup"><span data-stu-id="e32e7-128">Reference type</span></span></th>
<th><span data-ttu-id="e32e7-129">Tipo de evento</span><span class="sxs-lookup"><span data-stu-id="e32e7-129">Event type</span></span></th>
<th><span data-ttu-id="e32e7-130">Execução</span><span class="sxs-lookup"><span data-stu-id="e32e7-130">Execution</span></span></th>
<th><span data-ttu-id="e32e7-131">Bloqueio do evento</span><span class="sxs-lookup"><span data-stu-id="e32e7-131">Event blocking</span></span></th>
<th><span data-ttu-id="e32e7-132">Referência de documento</span><span class="sxs-lookup"><span data-stu-id="e32e7-132">Document reference</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e32e7-133">Estoque</span><span class="sxs-lookup"><span data-stu-id="e32e7-133">Inventory</span></span></td>
<td><span data-ttu-id="e32e7-134">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="e32e7-134">Not applicable</span></span></td>
<td><span data-ttu-id="e32e7-135">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="e32e7-135">Not applicable</span></span></td>
<td><span data-ttu-id="e32e7-136">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e32e7-136">None</span></span></td>
<td><span data-ttu-id="e32e7-137">Tudo</span><span class="sxs-lookup"><span data-stu-id="e32e7-137">All</span></span></td>
</tr>
<tr>
<td rowspan="7"><span data-ttu-id="e32e7-138">Venda</span><span class="sxs-lookup"><span data-stu-id="e32e7-138">Sales</span></span></td>
<td rowspan="4"><span data-ttu-id="e32e7-139">O processo de separação está agendado</span><span class="sxs-lookup"><span data-stu-id="e32e7-139">Picking process is scheduled</span></span></td>
<td rowspan="4"><span data-ttu-id="e32e7-140">Antes</span><span class="sxs-lookup"><span data-stu-id="e32e7-140">Before</span></span></td>
<td><span data-ttu-id="e32e7-141">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e32e7-141">None</span></span></td>
<td rowspan="22"><span data-ttu-id="e32e7-142">ID específica, Grupo, ou Todos apenas</span><span class="sxs-lookup"><span data-stu-id="e32e7-142">Specific ID, Group, or All only</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-143">Processo de separação</span><span class="sxs-lookup"><span data-stu-id="e32e7-143">Picking process</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-144">Guia de remessa</span><span class="sxs-lookup"><span data-stu-id="e32e7-144">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-145">Fatura</span><span class="sxs-lookup"><span data-stu-id="e32e7-145">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="e32e7-146">Guia de remessa</span><span class="sxs-lookup"><span data-stu-id="e32e7-146">Packing slip</span></span></td>
<td rowspan="3"><span data-ttu-id="e32e7-147">Antes</span><span class="sxs-lookup"><span data-stu-id="e32e7-147">Before</span></span></td>
<td><span data-ttu-id="e32e7-148">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e32e7-148">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-149">Guia de remessa</span><span class="sxs-lookup"><span data-stu-id="e32e7-149">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-150">Fatura</span><span class="sxs-lookup"><span data-stu-id="e32e7-150">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="15"><span data-ttu-id="e32e7-151">Compra</span><span class="sxs-lookup"><span data-stu-id="e32e7-151">Purchase</span></span></td>
<td rowspan="7"><span data-ttu-id="e32e7-152">Lista de recebimentos</span><span class="sxs-lookup"><span data-stu-id="e32e7-152">Receipt list</span></span></td>
<td rowspan="4"><span data-ttu-id="e32e7-153">Antes</span><span class="sxs-lookup"><span data-stu-id="e32e7-153">Before</span></span></td>
<td><span data-ttu-id="e32e7-154">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e32e7-154">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-155">Lista de recebimentos</span><span class="sxs-lookup"><span data-stu-id="e32e7-155">Receipt list</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-156">Recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="e32e7-156">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-157">Fatura</span><span class="sxs-lookup"><span data-stu-id="e32e7-157">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="e32e7-158">Depois</span><span class="sxs-lookup"><span data-stu-id="e32e7-158">After</span></span></td>
<td><span data-ttu-id="e32e7-159">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e32e7-159">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-160">Recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="e32e7-160">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-161">Fatura</span><span class="sxs-lookup"><span data-stu-id="e32e7-161">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="e32e7-162">Registro</span><span class="sxs-lookup"><span data-stu-id="e32e7-162">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="e32e7-163">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="e32e7-163">Not applicable</span></span></td>
<td><span data-ttu-id="e32e7-164">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e32e7-164">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-165">Recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="e32e7-165">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-166">Fatura</span><span class="sxs-lookup"><span data-stu-id="e32e7-166">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="e32e7-167">Recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="e32e7-167">Product receipt</span></span></td>
<td rowspan="3"><span data-ttu-id="e32e7-168">Antes</span><span class="sxs-lookup"><span data-stu-id="e32e7-168">Before</span></span></td>
<td><span data-ttu-id="e32e7-169">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e32e7-169">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-170">Recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="e32e7-170">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-171">Fatura</span><span class="sxs-lookup"><span data-stu-id="e32e7-171">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="e32e7-172">Depois</span><span class="sxs-lookup"><span data-stu-id="e32e7-172">After</span></span></td>
<td><span data-ttu-id="e32e7-173">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e32e7-173">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-174">Fatura</span><span class="sxs-lookup"><span data-stu-id="e32e7-174">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="8"><span data-ttu-id="e32e7-175">Produção</span><span class="sxs-lookup"><span data-stu-id="e32e7-175">Production</span></span></td>
<td rowspan="3"><span data-ttu-id="e32e7-176">Registro</span><span class="sxs-lookup"><span data-stu-id="e32e7-176">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="e32e7-177">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="e32e7-177">Not applicable</span></span></td>
<td><span data-ttu-id="e32e7-178">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e32e7-178">None</span></span></td>
<td rowspan="12"><span data-ttu-id="e32e7-179">Tudo</span><span class="sxs-lookup"><span data-stu-id="e32e7-179">All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-180">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="e32e7-180">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-181">Encerrar</span><span class="sxs-lookup"><span data-stu-id="e32e7-181">End</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="e32e7-182">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="e32e7-182">Report as finished</span></span></td>
<td rowspan="3"><span data-ttu-id="e32e7-183">Antes</span><span class="sxs-lookup"><span data-stu-id="e32e7-183">Before</span></span></td>
<td><span data-ttu-id="e32e7-184">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e32e7-184">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-185">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="e32e7-185">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-186">Encerrar</span><span class="sxs-lookup"><span data-stu-id="e32e7-186">End</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="e32e7-187">Depois</span><span class="sxs-lookup"><span data-stu-id="e32e7-187">After</span></span></td>
<td><span data-ttu-id="e32e7-188">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e32e7-188">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-189">Encerrar</span><span class="sxs-lookup"><span data-stu-id="e32e7-189">End</span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="e32e7-190">Quarentena</span><span class="sxs-lookup"><span data-stu-id="e32e7-190">Quarantine</span></span></td>
<td rowspan="3"><span data-ttu-id="e32e7-191">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="e32e7-191">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="e32e7-192">Antes</span><span class="sxs-lookup"><span data-stu-id="e32e7-192">Before</span></span></td>
<td><span data-ttu-id="e32e7-193">Relatar como concluído</span><span class="sxs-lookup"><span data-stu-id="e32e7-193">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-194">Encerrar</span><span class="sxs-lookup"><span data-stu-id="e32e7-194">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-195">Depois</span><span class="sxs-lookup"><span data-stu-id="e32e7-195">After</span></span></td>
<td><span data-ttu-id="e32e7-196">Encerrar</span><span class="sxs-lookup"><span data-stu-id="e32e7-196">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-197">Encerrar</span><span class="sxs-lookup"><span data-stu-id="e32e7-197">End</span></span></td>
<td><span data-ttu-id="e32e7-198">Antes</span><span class="sxs-lookup"><span data-stu-id="e32e7-198">Before</span></span></td>
<td><span data-ttu-id="e32e7-199">Encerrar</span><span class="sxs-lookup"><span data-stu-id="e32e7-199">End</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="e32e7-200">Operação do roteiro</span><span class="sxs-lookup"><span data-stu-id="e32e7-200">Route operation</span></span></td>
<td rowspan="3"><span data-ttu-id="e32e7-201">Relatório de Conclusão</span><span class="sxs-lookup"><span data-stu-id="e32e7-201">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="e32e7-202">Antes</span><span class="sxs-lookup"><span data-stu-id="e32e7-202">Before</span></span></td>
<td><span data-ttu-id="e32e7-203">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="e32e7-203">None</span></span></td>
<td rowspan="3"><span data-ttu-id="e32e7-204">ID específica, Grupo ou Todos, e Recurso específico, Grupo ou Todos</span><span class="sxs-lookup"><span data-stu-id="e32e7-204">Specific ID, Group, or All, and specific Resource, Group, or All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-205">Relatório de Conclusão</span><span class="sxs-lookup"><span data-stu-id="e32e7-205">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-206">Após</span><span class="sxs-lookup"><span data-stu-id="e32e7-206">After</span></span></td>
<td><span data-ttu-id="e32e7-207">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="e32e7-207">None</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="e32e7-208">Produção de coprodutos</span><span class="sxs-lookup"><span data-stu-id="e32e7-208">Co-product production</span></span></td>
<td><span data-ttu-id="e32e7-209">Registro</span><span class="sxs-lookup"><span data-stu-id="e32e7-209">Registration</span></span></td>
<td><span data-ttu-id="e32e7-210">Não Aplicável</span><span class="sxs-lookup"><span data-stu-id="e32e7-210">Not applicable</span></span></td>
<td rowspan="3"><span data-ttu-id="e32e7-211">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="e32e7-211">None</span></span></td>
<td rowspan="3"><span data-ttu-id="e32e7-212">Todas</span><span class="sxs-lookup"><span data-stu-id="e32e7-212">All</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="e32e7-213">Relatório de Conclusão</span><span class="sxs-lookup"><span data-stu-id="e32e7-213">Report as finished</span></span></td>
<td><span data-ttu-id="e32e7-214">Antes</span><span class="sxs-lookup"><span data-stu-id="e32e7-214">Before</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-215">Após</span><span class="sxs-lookup"><span data-stu-id="e32e7-215">After</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="e32e7-216">O recurso *Gerenciamento de qualidade para processos de depósito* adiciona funcionalidades para o processamento de ordens de qualidade para produção em que o campo **Tipo de evento** é definido como *Relatar como concluído* e o campo **Execução** é definido como *Depois*, e para compras em que o campo **Tipo de evento** é definido como *Registro*.</span><span class="sxs-lookup"><span data-stu-id="e32e7-216">The *Quality management for warehouse processes* feature adds capabilities for quality order processing for production where the **Event type** field is set to *Report as finished* and the **Execution** field is set to *After*, and for purchases where the **Event type** field is set to *Registration*.</span></span> <span data-ttu-id="e32e7-217">Para obter mais informações, consulte [Gerenciamento de qualidade para processos de depósito](quality-management-for-warehouses-processes.md).</span><span class="sxs-lookup"><span data-stu-id="e32e7-217">For more information, see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md).</span></span>

<span data-ttu-id="e32e7-218">A tabela a seguir fornece mais informações sobre como as ordens de qualidade podem ser geradas para tipos específicos de processos.</span><span class="sxs-lookup"><span data-stu-id="e32e7-218">The following table provides more information about how quality orders can be generated for specific types of processes.</span></span>

<div class="tableSection">
<table>
<thead>
<tr>
<th><span data-ttu-id="e32e7-219">Tipo de processo</span><span class="sxs-lookup"><span data-stu-id="e32e7-219">Type of process</span></span></th>
<th><span data-ttu-id="e32e7-220">Quando as ordens de qualidade podem ser geradas automaticamente</span><span class="sxs-lookup"><span data-stu-id="e32e7-220">When quality orders can be automatically generated</span></span></th>
<th><span data-ttu-id="e32e7-221">Quando as ordens de qualidade podem ser geradas se o teste destrutivo for exigido</span><span class="sxs-lookup"><span data-stu-id="e32e7-221">When quality orders can be generated if destructive testing is required</span></span></th>
<th><span data-ttu-id="e32e7-222">Informações de condição</span><span class="sxs-lookup"><span data-stu-id="e32e7-222">Condition information</span></span></th>
<th><span data-ttu-id="e32e7-223">Informações de geração manual</span><span class="sxs-lookup"><span data-stu-id="e32e7-223">Manual generation information</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e32e7-224">Ordem de compra</span><span class="sxs-lookup"><span data-stu-id="e32e7-224">Purchase order</span></span></td>
<td><span data-ttu-id="e32e7-225">Antes ou depois de uma lista de recebimentos ou de um recebimento de produtos para o material recebido é lançado</span><span class="sxs-lookup"><span data-stu-id="e32e7-225">Before or after a receipts list or product receipt for the material that is received is posted</span></span></td>
<td><span data-ttu-id="e32e7-226">Após o recebimento de produtos para o material recebido é lançado, porque o material deve estar disponível para testes destrutivos</span><span class="sxs-lookup"><span data-stu-id="e32e7-226">After the product receipt for the material that is received is posted, because the material must be available for destructive testing</span></span></td>
<td><span data-ttu-id="e32e7-227">O requisito para uma ordem de qualidade pode refletir um site, item ou fornecedor específico ou uma combinação dessas condições.</span><span class="sxs-lookup"><span data-stu-id="e32e7-227">The requirement for a quality order can reflect a specific site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="e32e7-228">Uma ordem de qualidade gerada manualmente que se refere a uma ordem de compra pode usar as informações em um registro de associação, como o planejamento de amostragem de teste.</span><span class="sxs-lookup"><span data-stu-id="e32e7-228">A manually generated quality order that refers to a purchase order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-229">Ordem de quarentena</span><span class="sxs-lookup"><span data-stu-id="e32e7-229">Quarantine order</span></span></td>
<td><span data-ttu-id="e32e7-230">Antes ou depois, a ordem de quarentena é relatada como concluída ou terminada</span><span class="sxs-lookup"><span data-stu-id="e32e7-230">Before or after the quarantine order is reported as finished or ended</span></span></td>
<td><span data-ttu-id="e32e7-231">Ordens de qualidade que exigem testes destrutivos não podem ser geradas.</span><span class="sxs-lookup"><span data-stu-id="e32e7-231">Quality orders that require destructive tests can't be generated.</span></span> <span data-ttu-id="e32e7-232">Presume-se que a funcionalidade da ordem de quarentena controla a disposição do material destruído.</span><span class="sxs-lookup"><span data-stu-id="e32e7-232">It's assumed that the quarantine order functionality handles the disposition of the material that is destroyed.</span></span></td>
<td><span data-ttu-id="e32e7-233">O requisito para uma ordem de qualidade pode refletir um site, item ou fornecedor específico ou uma combinação dessas condições.</span><span class="sxs-lookup"><span data-stu-id="e32e7-233">The requirement for a quality order can reflect a specific site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="e32e7-234">Uma ordem de qualidade gerada manualmente que se refere a uma ordem de quarentena pode usar as informações em um registro de associação, como o planejamento de amostragem de teste.</span><span class="sxs-lookup"><span data-stu-id="e32e7-234">A manually generated quality order that refers to a quarantine order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-235">Ordem de venda</span><span class="sxs-lookup"><span data-stu-id="e32e7-235">Sales order</span></span></td>
<td><span data-ttu-id="e32e7-236">Antes de uma atualização programada do processo de separação ou da guia de remessa dos itens que estão sendo enviados</span><span class="sxs-lookup"><span data-stu-id="e32e7-236">Before a scheduled picking process or packing slip update for the items that are being shipped</span></span></td>
<td><span data-ttu-id="e32e7-237">Em qualquer etapa</span><span class="sxs-lookup"><span data-stu-id="e32e7-237">At any step</span></span></td>
<td><span data-ttu-id="e32e7-238">O requisito para uma ordem de qualidade pode refletir um site, item ou cliente específico ou uma combinação dessas condições.</span><span class="sxs-lookup"><span data-stu-id="e32e7-238">The requirement for a quality order can reflect a specific site, item, or customer, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="e32e7-239">Uma ordem de qualidade gerada manualmente que se refere à ordem de compra pode usar informações em um registro de associação de qualidade, como o planejamento de amostragem de teste.</span><span class="sxs-lookup"><span data-stu-id="e32e7-239">A manually generated quality order that refers to a sales order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-240">Ordem de produção</span><span class="sxs-lookup"><span data-stu-id="e32e7-240">Production order</span></span></td>
<td><span data-ttu-id="e32e7-241">Antes ou depois, a quantidade concluída para a ordem de produção é relatada</span><span class="sxs-lookup"><span data-stu-id="e32e7-241">Before or after the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="e32e7-242">Depois que a quantidade concluída para a ordem de produção é relatada</span><span class="sxs-lookup"><span data-stu-id="e32e7-242">After the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="e32e7-243">O requisito para uma ordem de qualidade pode refletir um site ou item específico ou uma combinação dessas condições.</span><span class="sxs-lookup"><span data-stu-id="e32e7-243">The requirement for a quality order can reflect a specific site or item, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="e32e7-244">Uma ordem de qualidade gerada manualmente que se refere a uma ordem de produção em um registro de associação de qualidade, como o plano de amostragem de teste.</span><span class="sxs-lookup"><span data-stu-id="e32e7-244">A manually generated quality order that refers to a production order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-245">Ordem de produção que tem uma operação de rota</span><span class="sxs-lookup"><span data-stu-id="e32e7-245">Production order that has a route operation</span></span></td>
<td><span data-ttu-id="e32e7-246">Antes ou depois da conclusão do relatório para uma operação</span><span class="sxs-lookup"><span data-stu-id="e32e7-246">Before or after the report is finished for an operation</span></span></td>
<td><span data-ttu-id="e32e7-247">Depois da conclusão de produção de relatório para a última operação</span><span class="sxs-lookup"><span data-stu-id="e32e7-247">After the reporting production is finished for the last operation</span></span></td>
<td><span data-ttu-id="e32e7-248">O requisito para uma ordem de qualidade pode refletir um site, item ou recurso de operações específico ou uma combinação dessas condições.</span><span class="sxs-lookup"><span data-stu-id="e32e7-248">The requirement for a quality order can reflect a specific site, item, or operations resource, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="e32e7-249">Uma ordem de qualidade gerada manualmente que se refere a uma operação de rota em um registro de associação de qualidade, como o plano de amostragem de teste.</span><span class="sxs-lookup"><span data-stu-id="e32e7-249">A manually generated quality order that refers to a route operation can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-250">Inventário</span><span class="sxs-lookup"><span data-stu-id="e32e7-250">Inventory</span></span></td>
<td><span data-ttu-id="e32e7-251">Uma ordem de qualidade não pode ser gerada automaticamente para uma transação em um diário de estoque ou para transações de ordem de transferência.</span><span class="sxs-lookup"><span data-stu-id="e32e7-251">A quality order can't be automatically generated for a transaction in an inventory journal or for transfer order transactions.</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="e32e7-252">Uma ordem de qualidade deve ser criada manualmente para a quantidade em estoque de um item.</span><span class="sxs-lookup"><span data-stu-id="e32e7-252">A quality order must be manually created for an item's inventory quantity.</span></span> <span data-ttu-id="e32e7-253">O estoque físico disponível do item é necessário.</span><span class="sxs-lookup"><span data-stu-id="e32e7-253">Physical on-hand inventory is required.</span></span></td>
</tr>
</tbody>
</table>
</div>

## <a name="examples-of-automatic-generation-of-quality-orders"></a><span data-ttu-id="e32e7-254">Exemplos de geração automática de ordens de qualidade</span><span class="sxs-lookup"><span data-stu-id="e32e7-254">Examples of automatic generation of quality orders</span></span>

### <a name="purchasing"></a><span data-ttu-id="e32e7-255">Comprando</span><span class="sxs-lookup"><span data-stu-id="e32e7-255">Purchasing</span></span>

<span data-ttu-id="e32e7-256">Na compra, se você definir o campo **Tipo de evento** como *Recebimento de produtos* e o campo **Execução** como *Após* na página **Associações de qualidade**, você obterá os seguintes resultados:</span><span class="sxs-lookup"><span data-stu-id="e32e7-256">In purchasing, if you set the **Event type** field to *Product receipt* and the **Execution** field to *After* on the **Quality associations** page, you get the following results:</span></span>

- <span data-ttu-id="e32e7-257">Se a opção **Quantidade por atualização** for definida como *Yes*, uma ordem de qualidade é gerada para cada recebimento em relação à ordem de qualidade, com base na quantidade e nas configurações recebidas na amostra do item.</span><span class="sxs-lookup"><span data-stu-id="e32e7-257">If the **Per updated quantity** option is set to *Yes*, a quality order is generated for every receipt against the purchase order, based on the received quantity and settings in the item sampling.</span></span> <span data-ttu-id="e32e7-258">Sempre que uma quantidade é recebida em relação à ordem de compra, novos pedidos de qualidade são gerados com base na quantidade recém-recebida.</span><span class="sxs-lookup"><span data-stu-id="e32e7-258">Every time that a quantity is received against the purchase order, new quality orders are generated based on the newly received quantity.</span></span>
- <span data-ttu-id="e32e7-259">Se a opção **Quantidade por atualização** for definida como *Não*, uma ordem de qualidade será gerada para o primeiro recebimento em relação à ordem de qualidade, com base na quantidade recebida.</span><span class="sxs-lookup"><span data-stu-id="e32e7-259">If the **Per updated quantity** option is set to *No*, a quality order is generated for the first receipt against the purchase order, based on the received quantity.</span></span> <span data-ttu-id="e32e7-260">Além disso, uma ou mais ordens de qualidade são criadas com base na quantidade restante, dependendo das dimensões de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="e32e7-260">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions.</span></span> <span data-ttu-id="e32e7-261">Os pedidos de qualidade não são gerados para recebimentos subsequentes em relação à ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="e32e7-261">Quality orders aren't generated for subsequent receipts against the purchase order.</span></span>

### <a name="production"></a><span data-ttu-id="e32e7-262">Produção</span><span class="sxs-lookup"><span data-stu-id="e32e7-262">Production</span></span>

<span data-ttu-id="e32e7-263">Na produção, se você definir o campo **Tipo de evento** como *Relatar como concluído* e o campo **Execução** como *Após* na página **Associações de qualidade**, você obterá os seguintes resultados:</span><span class="sxs-lookup"><span data-stu-id="e32e7-263">In production, if you set the **Event type** field to *Report as finished* and the **Execution** field to *After* on the **Quality associations** page, you get the following results:</span></span>

- <span data-ttu-id="e32e7-264">Se a opção **Quantidade por atualização** for definida como *Yes*, uma ordem de qualidade é gerada com base em todas as quantidades e configurações finalizadas na amostra do item.</span><span class="sxs-lookup"><span data-stu-id="e32e7-264">If the **Per updated quantity** option is set to *Yes*, a quality order is generated based on every finished quantity and settings in the item sampling.</span></span> <span data-ttu-id="e32e7-265">Sempre que uma quantidade é relatada como concluída em relação à ordem de produção, novas ordens de qualidade são geradas com base na quantidade recém-concluída.</span><span class="sxs-lookup"><span data-stu-id="e32e7-265">Every time that a quantity is reported as finished against the production order, new quality orders are generated based on the newly finished quantity.</span></span> <span data-ttu-id="e32e7-266">Essa lógica de geração é consistente com a compra.</span><span class="sxs-lookup"><span data-stu-id="e32e7-266">This generation logic is consistent with purchasing.</span></span>
- <span data-ttu-id="e32e7-267">Se a opção **Quantidade por atualização** for definida como *Não*, uma ordem de qualidade é gerada na primeira vez que uma quantidade é relatada como concluída, com base na quantidade concluída.</span><span class="sxs-lookup"><span data-stu-id="e32e7-267">If the **Per updated quantity** option is set to *No*, a quality order is generated the first time that a quantity is reported as finished, based on the finished quantity.</span></span> <span data-ttu-id="e32e7-268">Além disso, uma ou mais ordens de qualidade são criadas com base na quantidade restante, dependendo das dimensões de rastreamento da amostra do item.</span><span class="sxs-lookup"><span data-stu-id="e32e7-268">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions of the item sampling.</span></span> <span data-ttu-id="e32e7-269">As ordens de qualidade não são geradas para quantidades concluídas subsequentes.</span><span class="sxs-lookup"><span data-stu-id="e32e7-269">Quality orders aren't generated for subsequent finished quantities.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="e32e7-270">Especificação de qualidade</span><span class="sxs-lookup"><span data-stu-id="e32e7-270">Quality specification</span></span></th>
<th><span data-ttu-id="e32e7-271">Quantidade por atualização</span><span class="sxs-lookup"><span data-stu-id="e32e7-271">Per updated quantity</span></span></th>
<th><span data-ttu-id="e32e7-272">Por dimensão de rastreamento</span><span class="sxs-lookup"><span data-stu-id="e32e7-272">Per tracking dimension</span></span></th>
<th><span data-ttu-id="e32e7-273">Resultado</span><span class="sxs-lookup"><span data-stu-id="e32e7-273">Result</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="e32e7-274">Porcentagem: 10%</span><span class="sxs-lookup"><span data-stu-id="e32e7-274">Percentage: 10%</span></span></td>
<td><span data-ttu-id="e32e7-275">Sim</span><span class="sxs-lookup"><span data-stu-id="e32e7-275">Yes</span></span></td>
<td>
<p><span data-ttu-id="e32e7-276">Nº do lote: não</span><span class="sxs-lookup"><span data-stu-id="e32e7-276">Batch number: No</span></span></p>
<p><span data-ttu-id="e32e7-277">Número de série: não</span><span class="sxs-lookup"><span data-stu-id="e32e7-277">Serial number: No</span></span></p>
</td>
<td>
<p><span data-ttu-id="e32e7-278">Quantidade da ordem: 100</span><span class="sxs-lookup"><span data-stu-id="e32e7-278">Order quantity: 100</span></span></p>
<ol>
<li><span data-ttu-id="e32e7-279">Relatar como concluído para 30</span><span class="sxs-lookup"><span data-stu-id="e32e7-279">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="e32e7-280">Ordem de qualidade 1 para 3 (10% de 30)</span><span class="sxs-lookup"><span data-stu-id="e32e7-280">Quality order 1 for 3 (10% of 30)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="e32e7-281">Relatar como concluído para 70</span><span class="sxs-lookup"><span data-stu-id="e32e7-281">Report as finished for 70</span></span>
<ul>
<li><span data-ttu-id="e32e7-282">Ordem de qualidade 2 para 7 (10% da quantidade restante da ordem, que é 70 neste caso)</span><span class="sxs-lookup"><span data-stu-id="e32e7-282">Quality order 2 for 7 (10% of the remaining order quantity, which is 70 in this case)</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-283">Quantidade fixa: 1</span><span class="sxs-lookup"><span data-stu-id="e32e7-283">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="e32e7-284">Não</span><span class="sxs-lookup"><span data-stu-id="e32e7-284">No</span></span></td>
<td>
<p><span data-ttu-id="e32e7-285">Nº do lote: não</span><span class="sxs-lookup"><span data-stu-id="e32e7-285">Batch number: No</span></span></p>
<p><span data-ttu-id="e32e7-286">Número de série: não</span><span class="sxs-lookup"><span data-stu-id="e32e7-286">Serial number: No</span></span></p>
</td>
<td><span data-ttu-id="e32e7-287">Quantidade da ordem: 100</span><span class="sxs-lookup"><span data-stu-id="e32e7-287">Order quantity: 100</span></span>
<ol>
<li><span data-ttu-id="e32e7-288">Relatar como concluído para 30</span><span class="sxs-lookup"><span data-stu-id="e32e7-288">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="e32e7-289">Ordem de qualidade 1 para 1 (para a primeira quantidade relatada como concluída, que tem um valor fixo de 1)</span><span class="sxs-lookup"><span data-stu-id="e32e7-289">Quality order 1 for 1 (for the first reported-as-finished quantity, which has a fixed value of 1)</span></span></li>
<li><span data-ttu-id="e32e7-290">Ordem de qualidade 2 para 1 (para a quantidade restante, que ainda possui um valor fixo de 1)</span><span class="sxs-lookup"><span data-stu-id="e32e7-290">Quality order 2 for 1 (for the remaining quantity, which still has a fixed value of 1)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="e32e7-291">Relatar como concluído para 10</span><span class="sxs-lookup"><span data-stu-id="e32e7-291">Report as finished for 10</span></span>
<ul>
<li><span data-ttu-id="e32e7-292">Nenhuma ordem de qualidade é criada.</span><span class="sxs-lookup"><span data-stu-id="e32e7-292">No quality orders are created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="e32e7-293">Relatar como concluído para 60</span><span class="sxs-lookup"><span data-stu-id="e32e7-293">Report as finished for 60</span></span>
<ul>
<li><span data-ttu-id="e32e7-294">Nenhuma ordem de qualidade é criada.</span><span class="sxs-lookup"><span data-stu-id="e32e7-294">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-295">Quantidade fixa: 1</span><span class="sxs-lookup"><span data-stu-id="e32e7-295">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="e32e7-296">Sim</span><span class="sxs-lookup"><span data-stu-id="e32e7-296">Yes</span></span></td>
<td>
<p><span data-ttu-id="e32e7-297">Nº do lote: sim</span><span class="sxs-lookup"><span data-stu-id="e32e7-297">Batch number: Yes</span></span></p>
<p><span data-ttu-id="e32e7-298">Número de série: sim</span><span class="sxs-lookup"><span data-stu-id="e32e7-298">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="e32e7-299">Quantidade da ordem: 10</span><span class="sxs-lookup"><span data-stu-id="e32e7-299">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="e32e7-300">Relatar como concluído para 3: 1 para número de lote b1, número de série s1; 1 para número de lote b2, número de série s2; e 1 para número de lote b3, número de série s3</span><span class="sxs-lookup"><span data-stu-id="e32e7-300">Report as finished for 3: 1 for batch number b1, serial number s1; 1 for batch number b2, serial number s2; and 1 for batch number b3, serial number s3</span></span>
<ul>
<li><span data-ttu-id="e32e7-301">Ordem de qualidade 1 para 1 do número de lote b1, número de série s1</span><span class="sxs-lookup"><span data-stu-id="e32e7-301">Quality order 1 for 1 of batch number b1, serial number s1</span></span></li>
<li><span data-ttu-id="e32e7-302">Ordem de qualidade 2 para 1 do número de lote b2, número de série s2</span><span class="sxs-lookup"><span data-stu-id="e32e7-302">Quality order 2 for 1 of batch number b2, serial number s2</span></span></li>
<li><span data-ttu-id="e32e7-303">Ordem de qualidade 3 para 1 do número de lote b3, número de série s3</span><span class="sxs-lookup"><span data-stu-id="e32e7-303">Quality order 3 for 1 of batch number b3, serial number s3</span></span></li>
</ul>
</li>
<li><span data-ttu-id="e32e7-304">Relatar como concluído para 2: 1 para número de lote b4, número de série s4; e 1 para número de lote b5, número de série s5</span><span class="sxs-lookup"><span data-stu-id="e32e7-304">Report as finished for 2: 1 for batch number b4, serial number s4; and 1 for batch number b5, serial number s5</span></span>
<ul>
<li><span data-ttu-id="e32e7-305">Ordem de qualidade 4 para 1 do número de lote b4, número de série s4</span><span class="sxs-lookup"><span data-stu-id="e32e7-305">Quality order 4 for 1 of batch number b4, serial number s4</span></span></li>
<li><span data-ttu-id="e32e7-306">Ordem de qualidade 5 para 1 do número de lote b5, número de série s5</span><span class="sxs-lookup"><span data-stu-id="e32e7-306">Quality order 5 for 1 of batch number b5, serial number s5</span></span></li>
</ul>
</li>
</ol>
<p><span data-ttu-id="e32e7-307"><strong>Observação:</strong> o lote pode ser reutilizado.</span><span class="sxs-lookup"><span data-stu-id="e32e7-307"><strong>Note:</strong> The batch can be reused.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="e32e7-308">Quantidade fixa: 2</span><span class="sxs-lookup"><span data-stu-id="e32e7-308">Fixed quantity: 2</span></span></td>
<td><span data-ttu-id="e32e7-309">Não</span><span class="sxs-lookup"><span data-stu-id="e32e7-309">No</span></span></td>
<td>
<p><span data-ttu-id="e32e7-310">Nº do lote: sim</span><span class="sxs-lookup"><span data-stu-id="e32e7-310">Batch number: Yes</span></span></p>
<p><span data-ttu-id="e32e7-311">Número de série: sim</span><span class="sxs-lookup"><span data-stu-id="e32e7-311">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="e32e7-312">Quantidade da ordem: 10</span><span class="sxs-lookup"><span data-stu-id="e32e7-312">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="e32e7-313">Relatar como concluído para 4: 1 para número de lote b1, número de série s1; 1 para número de lote b2, número de série s2; 1 para número de lote b3, número de série s3; e 1 para número de lote b4, número de série s4</span><span class="sxs-lookup"><span data-stu-id="e32e7-313">Report as finished for 4: 1 for batch number b1, serial number s1; 1 for batch number b2, serial number s2; 1 for batch number b3, serial number s3; and 1 for batch number b4, serial number s4</span></span>
<ul>
<li><span data-ttu-id="e32e7-314">Ordem de qualidade 1 para 1 do número de lote b1, número de série s1</span><span class="sxs-lookup"><span data-stu-id="e32e7-314">Quality order 1 for 1 of batch number b1, serial number s1</span></span></li>
<li><span data-ttu-id="e32e7-315">Ordem de qualidade 2 para 1 do número de lote b2, número de série s2</span><span class="sxs-lookup"><span data-stu-id="e32e7-315">Quality order 2 for 1 of batch number b2, serial number s2</span></span></li>
<li><span data-ttu-id="e32e7-316">Ordem de qualidade 3 para 1 do número de lote b3, número de série s3</span><span class="sxs-lookup"><span data-stu-id="e32e7-316">Quality order 3 for 1 of batch number b3, serial number s3</span></span></li>
<li><span data-ttu-id="e32e7-317">Ordem de qualidade 4 para 1 do número de lote b4, número de série s4</span><span class="sxs-lookup"><span data-stu-id="e32e7-317">Quality order 4 for 1 of batch number b4, serial number s4</span></span></li>
</ul>
<ul>
<li><span data-ttu-id="e32e7-318">Ordem de qualidade 5 para 2, sem referência a um número de lote e um número de série</span><span class="sxs-lookup"><span data-stu-id="e32e7-318">Quality order 5 for 2, without a reference to a batch number and a serial number</span></span></li>
</ul>
</li>
<li><span data-ttu-id="e32e7-319">Relatar como concluído para 6: 1 para número de lote b5, número de série s5; 1 para número de lote b6, número de série s6; 1 para número de lote b7, número de série s7; 1 para número de lote b8, número de série s8; 1 para número de lote b9, número de série s9; e 1 para número de lote b10, número de série s10</span><span class="sxs-lookup"><span data-stu-id="e32e7-319">Report as finished for 6: 1 for batch number b5, serial number s5; 1 for batch number b6, serial number s6; 1 for batch number b7, serial number s7; 1 for batch number b8, serial number s8; 1 for batch number b9, serial number s9; and 1 for batch number b10, serial number s10</span></span>
<ul>
<li><span data-ttu-id="e32e7-320">Nenhuma ordem de qualidade é criada.</span><span class="sxs-lookup"><span data-stu-id="e32e7-320">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="e32e7-321">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="e32e7-321">Additional resources</span></span>

- [<span data-ttu-id="e32e7-322">Processos de gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="e32e7-322">Quality management processes</span></span>](quality-management-processes.md)
- [<span data-ttu-id="e32e7-323">Habilitar gerenciamento de qualidade e não conformidade</span><span class="sxs-lookup"><span data-stu-id="e32e7-323">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="e32e7-324">Gerenciamento de qualidade para processos de depósito</span><span class="sxs-lookup"><span data-stu-id="e32e7-324">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
