---
title: Criar e processar não conformidades
description: Este tópico descreve como executar o gerenciamento de não conformidades, com base em uma ordem de qualidade existente.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 06a56a694f7a80d65cb46d08744e78d8361cee3b
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956197"
---
# <a name="create-and-process-nonconformances"></a><span data-ttu-id="0db63-103">Criar e processar não conformidades</span><span class="sxs-lookup"><span data-stu-id="0db63-103">Create and process nonconformances</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0db63-104">Este tópico descreve como executar o gerenciamento de não conformidades, com base em uma ordem de qualidade existente.</span><span class="sxs-lookup"><span data-stu-id="0db63-104">This topic describes how to perform nonconformance management based on an existing quality order.</span></span> <span data-ttu-id="0db63-105">Normalmente, o gerenciamento de não conformidade é feito por um auxiliar de qualidade.</span><span class="sxs-lookup"><span data-stu-id="0db63-105">Typically, nonconformance management is done by a quality clerk.</span></span> <span data-ttu-id="0db63-106">Como pré-requisito, você deve ter uma ordem de qualidade disponível.</span><span class="sxs-lookup"><span data-stu-id="0db63-106">As a prerequisite, you must have a quality order available.</span></span> <span data-ttu-id="0db63-107">(Para obter mais informações sobre como criar uma ordem de qualidade, consulte [Verificar a qualidade de mercadorias](inspect-quality-goods.md)).</span><span class="sxs-lookup"><span data-stu-id="0db63-107">(For information about how to create a quality order, see [Inspect the quality of goods](inspect-quality-goods.md).)</span></span>

<span data-ttu-id="0db63-108">Antes que um usuário possa processar a aprovação de uma não conformidade, um trabalhador deve ser atribuído a ela no campo **Pessoa** na página **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="0db63-108">Before a user can process the approval of a nonconformance, a worker must be assigned to them in the **Person** field on the **Users** page.</span></span> <span data-ttu-id="0db63-109">Além disso, antes que o usuário possa usar as notas do documento, a opção **Habilitar manuseio de documentos** deve ser definida como *Sim* nas opções do usuário.</span><span class="sxs-lookup"><span data-stu-id="0db63-109">Additionally, before the user can use the document notes, the **Enable document handling** option must be set to *Yes* in their user options.</span></span>

## <a name="create-a-nonconformance"></a><span data-ttu-id="0db63-110">Criar uma não conformidade</span><span class="sxs-lookup"><span data-stu-id="0db63-110">Create a nonconformance</span></span>

<span data-ttu-id="0db63-111">Para criar uma não conformidade, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="0db63-111">To create a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="0db63-112">Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Não conformidades**.</span><span class="sxs-lookup"><span data-stu-id="0db63-112">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="0db63-113">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="0db63-113">On the Action pane, select **New**.</span></span>
1. <span data-ttu-id="0db63-114">Na caixa de diálogo **Criar não conformidade**, no campo **Tipo de problema**, selecione o tipo de problema encontrado durante o processo de inspeção.</span><span class="sxs-lookup"><span data-stu-id="0db63-114">In the **Create non conformance** dialog box, in **Problem type** field, select the type of problem that was found during the inspection process.</span></span>
1. <span data-ttu-id="0db63-115">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="0db63-115">Select **OK**.</span></span>

## <a name="approve-or-reject-a-nonconformance"></a><span data-ttu-id="0db63-116">Aprovar ou rejeitar uma não conformidade</span><span class="sxs-lookup"><span data-stu-id="0db63-116">Approve or reject a nonconformance</span></span>

<span data-ttu-id="0db63-117">Para aprovar ou rejeitar uma não conformidade, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="0db63-117">To approve or reject a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="0db63-118">Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Não conformidades**.</span><span class="sxs-lookup"><span data-stu-id="0db63-118">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="0db63-119">Na lista, selecione a não conformidade que deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="0db63-119">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0db63-120">Você pode adicionar uma correção somente a não conformidades que foram aprovadas.</span><span class="sxs-lookup"><span data-stu-id="0db63-120">You can add a correction only to nonconformances that are approved.</span></span>

1. <span data-ttu-id="0db63-121">No Painel de Ações, selecione **Funções \> Aprovar não conformidade** para aprovar a não conformidade ou **Funções \> Recusar não conformidade** para rejeitá-la.</span><span class="sxs-lookup"><span data-stu-id="0db63-121">On the Action Pane, select **Functions \> Approve non conformance** to approve the nonconformance or **Functions \> Refuse non conformance** to reject it.</span></span> <span data-ttu-id="0db63-122">Você pode associar não conformidades aprovadas a [operações relacionadas](../quality-operations.md).</span><span class="sxs-lookup"><span data-stu-id="0db63-122">You can associate approved nonconformances with [related operations](../quality-operations.md).</span></span> <span data-ttu-id="0db63-123">Dessa forma, você pode registrar o trabalho feito como parte do tratamento de não conformidade e do processamento do tratamento de correção.</span><span class="sxs-lookup"><span data-stu-id="0db63-123">In this way, you can record work that is done as part of the nonconformance handling and the processing of correction handling.</span></span>
1. <span data-ttu-id="0db63-124">Será solicitado que você confirme sua seleção.</span><span class="sxs-lookup"><span data-stu-id="0db63-124">You're prompted to confirm your selection.</span></span> <span data-ttu-id="0db63-125">Selecione **Sim** para continuar.</span><span class="sxs-lookup"><span data-stu-id="0db63-125">Select **Yes** to continue.</span></span>

## <a name="add-operations-and-other-details-to-nonconformances"></a><span data-ttu-id="0db63-126">Adicionar operações e outros detalhes a não conformidades</span><span class="sxs-lookup"><span data-stu-id="0db63-126">Add operations and other details to nonconformances</span></span>

<span data-ttu-id="0db63-127">Depois de criar uma não conformidade, você pode começar a adicionar operações relacionadas e especificar informações adicionais sobre essas operações.</span><span class="sxs-lookup"><span data-stu-id="0db63-127">After you've created a nonconformance, you can start to add related operations and specify additional information about those operations.</span></span> <span data-ttu-id="0db63-128">Você pode adicionar operações relacionadas somente a não conformidades que foram aprovadas.</span><span class="sxs-lookup"><span data-stu-id="0db63-128">You can add related operations only to nonconformances that are approved.</span></span>

<span data-ttu-id="0db63-129">Além das informações básicas, você pode adicionar os seguintes detalhes a uma operação:</span><span class="sxs-lookup"><span data-stu-id="0db63-129">Besides the basic information, you can add the following details to an operation:</span></span>

- <span data-ttu-id="0db63-130">**Itens** – você pode criar uma lista de itens consumidos para realizar a correção.</span><span class="sxs-lookup"><span data-stu-id="0db63-130">**Items** – You can create a list of items that are consumed to perform the correction.</span></span> <span data-ttu-id="0db63-131">Por exemplo, os itens podem ser produtos necessários para reparar equipamentos ou ingredientes necessários à retrabalho de um produto acabado.</span><span class="sxs-lookup"><span data-stu-id="0db63-131">For example, the items might be products that are required to repair equipment or ingredients that are required to rework a finished product.</span></span>
- <span data-ttu-id="0db63-132">**Encargos de qualidade** – você pode criar uma lista de encargos incorridos ou faturados para fontes externas.</span><span class="sxs-lookup"><span data-stu-id="0db63-132">**Quality charges** – You can create a list of charges that are incurred or billed out to external sources.</span></span>
- <span data-ttu-id="0db63-133">**Folha de ponto** – você pode criar um log do tempo gasto por cada trabalhador na operação.</span><span class="sxs-lookup"><span data-stu-id="0db63-133">**Timesheet** – You can create a log of the time that each worker spends on the operation.</span></span>

<span data-ttu-id="0db63-134">As demais configurações são opcionais.</span><span class="sxs-lookup"><span data-stu-id="0db63-134">The remaining settings are optional.</span></span> <span data-ttu-id="0db63-135">O custo de cada item, encargos de qualidade e folha de ponto são somados e mostrados na operação.</span><span class="sxs-lookup"><span data-stu-id="0db63-135">The cost for each item, quality charges, and the timesheet are summed and shown on the operation.</span></span> <span data-ttu-id="0db63-136">Não é possível editar diretamente o campo **Custo** na operação.</span><span class="sxs-lookup"><span data-stu-id="0db63-136">You can't directly edit the **Cost** field on the operation.</span></span>

### <a name="create-an-operation-for-a-nonconformance"></a><span data-ttu-id="0db63-137">Criar uma operação para uma não conformidade</span><span class="sxs-lookup"><span data-stu-id="0db63-137">Create an operation for a nonconformance</span></span>

<span data-ttu-id="0db63-138">Para criar uma operação para uma não conformidade, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="0db63-138">To create an operation for a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="0db63-139">Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Não conformidades**.</span><span class="sxs-lookup"><span data-stu-id="0db63-139">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="0db63-140">Na lista, selecione a não conformidade que deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="0db63-140">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0db63-141">Você pode adicionar ou atualizar operações somente a não conformidades que foram aprovadas.</span><span class="sxs-lookup"><span data-stu-id="0db63-141">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="0db63-142">No Painel de Ações, selecione **Operações relacionadas**.</span><span class="sxs-lookup"><span data-stu-id="0db63-142">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="0db63-143">Na página **Operações relacionadas**, no painel de Ações, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="0db63-143">On the **Related operations** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="0db63-144">Defina os seguintes campos para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="0db63-144">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="0db63-145">**Operação** – Selecione o código da operação que será executada para a não conformidade.</span><span class="sxs-lookup"><span data-stu-id="0db63-145">**Operation** – Select the code of the operation that will be performed for the nonconformance.</span></span>
    - <span data-ttu-id="0db63-146">**Motivo** – Insira uma descrição detalhada que explique por que a operação é necessária.</span><span class="sxs-lookup"><span data-stu-id="0db63-146">**Reason** – Enter a detailed description that explains why the operation is required.</span></span>
    - <span data-ttu-id="0db63-147">**Ordem de venda** – se o código de operação selecionado estiver relacionado ao tipo de ordem de venda, selecione a ordem de venda à qual a operação está sendo vinculada.</span><span class="sxs-lookup"><span data-stu-id="0db63-147">**Sales order** – If the selected operation code is related to the sales order type, select the sales order that you're linking the operation to.</span></span>
    - <span data-ttu-id="0db63-148">**Ordem de compra** – se o código de operação selecionado estiver relacionado ao tipo de ordem de compra, selecione a ordem de compra à qual a operação está sendo vinculada.</span><span class="sxs-lookup"><span data-stu-id="0db63-148">**Purchase order** – If the selected operation code is related to the purchase order type, select the purchase order that you're linking the operation to.</span></span>

1. <span data-ttu-id="0db63-149">Feche as páginas.</span><span class="sxs-lookup"><span data-stu-id="0db63-149">Close the pages.</span></span>

### <a name="add-items-to-an-operation"></a><span data-ttu-id="0db63-150">Adicionar itens a uma operação</span><span class="sxs-lookup"><span data-stu-id="0db63-150">Add items to an operation</span></span>

<span data-ttu-id="0db63-151">Para adicionar itens a uma operação, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="0db63-151">To add items to an operation, follow these steps.</span></span>

1. <span data-ttu-id="0db63-152">Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Não conformidades**.</span><span class="sxs-lookup"><span data-stu-id="0db63-152">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="0db63-153">Na lista, selecione a não conformidade que deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="0db63-153">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0db63-154">Você pode adicionar ou atualizar operações somente a não conformidades que foram aprovadas.</span><span class="sxs-lookup"><span data-stu-id="0db63-154">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="0db63-155">No Painel de Ações, selecione **Operações relacionadas**.</span><span class="sxs-lookup"><span data-stu-id="0db63-155">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="0db63-156">Na página **Operações relacionadas**, selecione a operação à qual deseja adicionar itens.</span><span class="sxs-lookup"><span data-stu-id="0db63-156">On the **Related operations** page, select the operation that you want to add items to.</span></span>
1. <span data-ttu-id="0db63-157">No Painel de Ações, selecione **Itens**.</span><span class="sxs-lookup"><span data-stu-id="0db63-157">On the Action Pane, select **Items**.</span></span>
1. <span data-ttu-id="0db63-158">Na página **Operações relacionadas**, no painel de Ações, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="0db63-158">On the **Related operations** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="0db63-159">Em seguida, defina os seguintes campos para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="0db63-159">Then set the following fields for new row:</span></span>

    - <span data-ttu-id="0db63-160">**Número do item** – selecione o produto que será consumido como parte da operação selecionada.</span><span class="sxs-lookup"><span data-stu-id="0db63-160">**Item number** – Select the product that will be consumed as part of the selected operation.</span></span>
    - <span data-ttu-id="0db63-161">**Quantidade** – Insira o número de itens que serão consumidos.</span><span class="sxs-lookup"><span data-stu-id="0db63-161">**Quantity** – Enter the number of items that will be consumed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0db63-162">Você pode exibir o custo do item no campo **Custo** na guia **Geral**. O custo que é mostrado vem do custo configurado na página **Produto liberado**.</span><span class="sxs-lookup"><span data-stu-id="0db63-162">You can view the cost for the item in the **Cost** field on the **General** tab. The cost that is shown there comes from the cost that is set up on the **Released product** page.</span></span> <span data-ttu-id="0db63-163">O custo não pode ser atualizado diretamente na página **Item de operação relacionado**.</span><span class="sxs-lookup"><span data-stu-id="0db63-163">The cost can't be updated directly on the **Related operation item** page.</span></span> <span data-ttu-id="0db63-164">O custo de todos os itens adicionados na página **Itens de operação relacionados** é adicionado automaticamente ao campo **Custo** na página **Operações relacionadas**.</span><span class="sxs-lookup"><span data-stu-id="0db63-164">The cost of all items that are added on the **Related operation items** page is automatically added to the **Cost** field on the **Related operations** page.</span></span>

1. <span data-ttu-id="0db63-165">Repita a etapa anterior para cada item adicional que deve ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="0db63-165">Repeat the previous step for each additional item that you must add.</span></span>
1. <span data-ttu-id="0db63-166">Feche as páginas.</span><span class="sxs-lookup"><span data-stu-id="0db63-166">Close the pages.</span></span>

### <a name="add-quality-charges-to-an-operation"></a><span data-ttu-id="0db63-167">Adicionar encargos de qualidade a uma operação</span><span class="sxs-lookup"><span data-stu-id="0db63-167">Add quality charges to an operation</span></span>

<span data-ttu-id="0db63-168">Para adicionar encargos de qualidade a uma operação, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="0db63-168">To add quality charges to an operation, follow these steps.</span></span>

1. <span data-ttu-id="0db63-169">Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Não conformidades**.</span><span class="sxs-lookup"><span data-stu-id="0db63-169">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="0db63-170">Na lista, selecione a não conformidade que deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="0db63-170">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0db63-171">Você pode adicionar ou atualizar operações somente a não conformidades que foram aprovadas.</span><span class="sxs-lookup"><span data-stu-id="0db63-171">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="0db63-172">No Painel de Ações, selecione **Operações relacionadas**.</span><span class="sxs-lookup"><span data-stu-id="0db63-172">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="0db63-173">Na página **Operações relacionadas**, selecione a operação à qual deseja adicionar encargos de qualidade.</span><span class="sxs-lookup"><span data-stu-id="0db63-173">On the **Related operations** page, select the operation that you want to add quality charges to.</span></span>
1. <span data-ttu-id="0db63-174">No Painel de Ações, selecione **Encargos de qualidade**.</span><span class="sxs-lookup"><span data-stu-id="0db63-174">On the Action Pane, select **Quality charges**.</span></span>
1. <span data-ttu-id="0db63-175">Na página **Encargos de operações relacionadas**, no Painel de Ações, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="0db63-175">On the **Related operation charges** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="0db63-176">Defina os seguintes campos para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="0db63-176">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="0db63-177">**Código de encargos** – Selecione o encargo de qualidade ao qual você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="0db63-177">**Charges code** – Select the quality charge that you want to add.</span></span>
    - <span data-ttu-id="0db63-178">**Descrição** – Insira uma descrição detalhada do encargo.</span><span class="sxs-lookup"><span data-stu-id="0db63-178">**Description** – Enter a detailed description of the charge.</span></span>
    - <span data-ttu-id="0db63-179">**Valor dos encargos** – Insira o valor do encargo.</span><span class="sxs-lookup"><span data-stu-id="0db63-179">**Charges value** – Enter the amount of the charge.</span></span>

1. <span data-ttu-id="0db63-180">Repita a etapa anterior para cada encargo adicional que deve ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="0db63-180">Repeat the previous step for each additional charge that you must add.</span></span>
1. <span data-ttu-id="0db63-181">Feche as páginas.</span><span class="sxs-lookup"><span data-stu-id="0db63-181">Close the pages.</span></span>

> [!NOTE]
> <span data-ttu-id="0db63-182">O valor no campo **Valor de encargos** é somado automaticamente a todos os encargos de qualidade e adicionado a quaisquer valores no campo **Custo** na página **Operações relacionadas**.</span><span class="sxs-lookup"><span data-stu-id="0db63-182">The amount in the **Charges value** field is automatically summed for all quality charges and added to any other amounts in the **Cost** field on the **Related operations** page.</span></span>

### <a name="create-a-timesheet-on-an-operation"></a><span data-ttu-id="0db63-183">Criar uma folha de ponto em uma operação</span><span class="sxs-lookup"><span data-stu-id="0db63-183">Create a timesheet on an operation</span></span>

<span data-ttu-id="0db63-184">Para adicionar uma folha de ponto em uma operação, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="0db63-184">To add a timesheet to an operation, follow these steps.</span></span>

1. <span data-ttu-id="0db63-185">Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Não conformidades**.</span><span class="sxs-lookup"><span data-stu-id="0db63-185">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="0db63-186">Na lista, selecione a não conformidade que deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="0db63-186">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0db63-187">Você pode adicionar ou atualizar operações somente a não conformidades que foram aprovadas.</span><span class="sxs-lookup"><span data-stu-id="0db63-187">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="0db63-188">No Painel de Ações, selecione **Operações relacionadas**.</span><span class="sxs-lookup"><span data-stu-id="0db63-188">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="0db63-189">Na página **Operações relacionadas**, selecione a operação à qual deseja adicionar uma folha de ponto.</span><span class="sxs-lookup"><span data-stu-id="0db63-189">On the **Related operations** page, select the operation that you want to add a timesheet to.</span></span>
1. <span data-ttu-id="0db63-190">No Painel de Ação, selecione **Folha de Ponto**.</span><span class="sxs-lookup"><span data-stu-id="0db63-190">On the Action Pane, select **Timesheet**.</span></span>
1. <span data-ttu-id="0db63-191">Na página **Folhas de ponto da operação relacionada**, no Painel de Ações, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="0db63-191">On the **Related operation time sheets** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="0db63-192">Defina os seguintes campos para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="0db63-192">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="0db63-193">**Data** – especifique a data em que o trabalho foi concluído.</span><span class="sxs-lookup"><span data-stu-id="0db63-193">**Date** – Specify the date when work was done.</span></span> <span data-ttu-id="0db63-194">Por padrão, esse campo é definido como a data atual.</span><span class="sxs-lookup"><span data-stu-id="0db63-194">By default, this field is set to the current date.</span></span>
    - <span data-ttu-id="0db63-195">**Trabalhador** – selecione o trabalhador que fez o trabalho.</span><span class="sxs-lookup"><span data-stu-id="0db63-195">**Worker** – Select the worker who did the work.</span></span> <span data-ttu-id="0db63-196">Por padrão, este campo é definido ao trabalhador atribuído ao usuário atual.</span><span class="sxs-lookup"><span data-stu-id="0db63-196">By default, this field is set to the worker that is assigned to the current user.</span></span>
    - <span data-ttu-id="0db63-197">**Horas de operação** – insira o número de horas que foram trabalhadas na operação selecionada.</span><span class="sxs-lookup"><span data-stu-id="0db63-197">**Operation hours** – Enter the number of hours that were worked on the selected operation.</span></span>
    - <span data-ttu-id="0db63-198">**Faturado** – Marque esta caixa de seleção se o tempo tiver sido cobrado de um cliente ou fornecedor em uma fatura.</span><span class="sxs-lookup"><span data-stu-id="0db63-198">**Invoiced** – Select this check box if the time has been charged to a customer or vendor on an invoice.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0db63-199">Você pode exibir o custo no campo **Custo** na guia **Geral**. O custo é calculado usando a taxa definida na página **Parâmetros de gerenciamento de estoque**.</span><span class="sxs-lookup"><span data-stu-id="0db63-199">You can view the cost in the **Cost** field on the **General** tab. The cost is calculated by using the rate that you define on the **Inventory management parameters** page.</span></span>

1. <span data-ttu-id="0db63-200">Repita a etapa anterior para cada linha da folha de ponto adicional que deve ser adicionada.</span><span class="sxs-lookup"><span data-stu-id="0db63-200">Repeat the previous step for each additional timesheet line that you must add.</span></span>
1. <span data-ttu-id="0db63-201">Feche as páginas.</span><span class="sxs-lookup"><span data-stu-id="0db63-201">Close the pages.</span></span>

> [!NOTE]
> <span data-ttu-id="0db63-202">O valor no campo **Custo** é somado a todas as linhas da planilha de ponto e adicionado a quaisquer outros valores no campo **Custo** na página **Operações relacionadas**.</span><span class="sxs-lookup"><span data-stu-id="0db63-202">The amount in the **Cost** field is summed for all timesheet lines and added to any other amounts in the **Cost** field on the **Related operations** page.</span></span>

## <a name="add-a-correction-to-a-nonconformance"></a><span data-ttu-id="0db63-203">Adicionar uma correção a uma não conformidade</span><span class="sxs-lookup"><span data-stu-id="0db63-203">Add a correction to a nonconformance</span></span>

<span data-ttu-id="0db63-204">Para adicionar uma correção a uma não conformidade, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="0db63-204">To add a correction to a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="0db63-205">Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Não conformidades**.</span><span class="sxs-lookup"><span data-stu-id="0db63-205">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="0db63-206">Na lista, selecione a não conformidade que deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="0db63-206">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0db63-207">Você pode adicionar uma correção somente a não conformidades que foram aprovadas.</span><span class="sxs-lookup"><span data-stu-id="0db63-207">You can add a correction only to nonconformances that are approved.</span></span>

1. <span data-ttu-id="0db63-208">No Painel de Ações, selecione **Correções**.</span><span class="sxs-lookup"><span data-stu-id="0db63-208">On the Action Pane, select **Corrections**.</span></span>
1. <span data-ttu-id="0db63-209">Na página **Correções**, no Painel de Ações, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="0db63-209">On the **Corrections** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="0db63-210">Defina os seguintes campos para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="0db63-210">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="0db63-211">**Diagnóstico** – Selecione o tipo de diagnóstico que identifica o tipo de correção que você está criando.</span><span class="sxs-lookup"><span data-stu-id="0db63-211">**Diagnostic** – Select the diagnostic type that identifies the type of correction that you're creating.</span></span>
    - <span data-ttu-id="0db63-212">**Trabalhador** – Selecione a pessoa responsável pela correção.</span><span class="sxs-lookup"><span data-stu-id="0db63-212">**Worker** – Select the person who is responsible for the correction.</span></span>
    - <span data-ttu-id="0db63-213">**Prioridade de correção** – Selecione uma opção para indicar como a correção deve ser priorizada (*Baixa*, *Normal* ou *Alta*).</span><span class="sxs-lookup"><span data-stu-id="0db63-213">**Correction priority** – Select an option to indicate how the correction should be prioritized (*Low*, *Normal*, or *High*).</span></span>
    - <span data-ttu-id="0db63-214">**Data da solicitação** – Insira a data em que a ação corretiva foi solicitada.</span><span class="sxs-lookup"><span data-stu-id="0db63-214">**Requested date** – Enter the date when the corrective action was requested.</span></span>
    - <span data-ttu-id="0db63-215">**Data planejada** – Insira a data em que a correção deve ser concluída.</span><span class="sxs-lookup"><span data-stu-id="0db63-215">**Planned date** – Enter the date when the correction is expected to be completed.</span></span>
    - <span data-ttu-id="0db63-216">**Solução de curto prazo** – Marque esta caixa de seleção se a ação corretiva corrigir a não conformidade somente por um curto período.</span><span class="sxs-lookup"><span data-stu-id="0db63-216">**Short term solution** – Select this check box if the corrective action corrects the nonconformance only for a short time.</span></span>

1. <span data-ttu-id="0db63-217">Feche as páginas.</span><span class="sxs-lookup"><span data-stu-id="0db63-217">Close the pages.</span></span>

## <a name="mark-a-correction-as-completed"></a><span data-ttu-id="0db63-218">Marcar uma correção como concluída</span><span class="sxs-lookup"><span data-stu-id="0db63-218">Mark a correction as completed</span></span>

<span data-ttu-id="0db63-219">Para marcar uma correção de não conformidade como concluída, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="0db63-219">To mark a nonconformance correction as completed, follow these steps.</span></span>

1. <span data-ttu-id="0db63-220">Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Não conformidades**.</span><span class="sxs-lookup"><span data-stu-id="0db63-220">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="0db63-221">Na lista, selecione a não conformidade que deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="0db63-221">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0db63-222">Você pode adicionar uma correção somente a não conformidades que foram aprovadas.</span><span class="sxs-lookup"><span data-stu-id="0db63-222">You can add a correction only to nonconformances that are approved.</span></span>

1. <span data-ttu-id="0db63-223">No Painel de Ações, selecione **Correções**.</span><span class="sxs-lookup"><span data-stu-id="0db63-223">On the Action Pane, select **Corrections**.</span></span>
1. <span data-ttu-id="0db63-224">Na página **Correções**, na grade, selecione a correção que deseja marcar como concluída.</span><span class="sxs-lookup"><span data-stu-id="0db63-224">On the **Corrections** page, in the grid, select the correction that you want to mark as completed.</span></span>
1. <span data-ttu-id="0db63-225">No Painel de Ações, clique em **Marcar como concluída**.</span><span class="sxs-lookup"><span data-stu-id="0db63-225">On the Action Pane, select **Mark complete**.</span></span>
1. <span data-ttu-id="0db63-226">Será solicitado que você confirme sua seleção.</span><span class="sxs-lookup"><span data-stu-id="0db63-226">You're prompted to confirm your selection.</span></span> <span data-ttu-id="0db63-227">Selecione **OK** para continuar.</span><span class="sxs-lookup"><span data-stu-id="0db63-227">Select **OK** to continue.</span></span> <span data-ttu-id="0db63-228">O campo **Data e hora de conclusão** é definido como a data e a hora atuais, e a caixa de seleção **Concluído** será marcada.</span><span class="sxs-lookup"><span data-stu-id="0db63-228">The **Completion date and time** field is set to the current date and time, and the **Completed** check box is selected.</span></span>
1. <span data-ttu-id="0db63-229">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0db63-229">Close the page.</span></span>

## <a name="reopen-a-completed-correction"></a><span data-ttu-id="0db63-230">Reabrir uma correção como concluída</span><span class="sxs-lookup"><span data-stu-id="0db63-230">Reopen a completed correction</span></span>

<span data-ttu-id="0db63-231">Para reabrir uma correção concluída, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="0db63-231">To reopen a completed correction, follow these steps.</span></span>

1. <span data-ttu-id="0db63-232">Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Não conformidades**.</span><span class="sxs-lookup"><span data-stu-id="0db63-232">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="0db63-233">Na lista, selecione a não conformidade que deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="0db63-233">In the list, select the nonconformance that you want to update.</span></span>
1. <span data-ttu-id="0db63-234">No Painel de Ações, selecione **Correções**.</span><span class="sxs-lookup"><span data-stu-id="0db63-234">On the Action pane, select **Corrections**.</span></span>
1. <span data-ttu-id="0db63-235">Na página **Correções**, na grade, selecione a correção que deseja reabrir.</span><span class="sxs-lookup"><span data-stu-id="0db63-235">On the **Corrections** page, in the grid, select the correction that you want to reopen.</span></span>
1. <span data-ttu-id="0db63-236">No Painel de Ação, selecione **Reabrir**.</span><span class="sxs-lookup"><span data-stu-id="0db63-236">On the Action Pane, select **Reopen**.</span></span>
1. <span data-ttu-id="0db63-237">Será solicitado que você confirme sua seleção.</span><span class="sxs-lookup"><span data-stu-id="0db63-237">You're prompted to confirm your selection.</span></span> <span data-ttu-id="0db63-238">Selecione **OK** para continuar.</span><span class="sxs-lookup"><span data-stu-id="0db63-238">Select **OK** to continue.</span></span> <span data-ttu-id="0db63-239">O valor é desmarcado do campo **Data e hora de conclusão** e a caixa de seleção **Concluída** será desmarcada.</span><span class="sxs-lookup"><span data-stu-id="0db63-239">The value is cleared from the **Completion date and time** field, and the **Completed** check box is cleared.</span></span>
1. <span data-ttu-id="0db63-240">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0db63-240">Close the page.</span></span>

<span data-ttu-id="0db63-241">Agora você pode fazer edições adicionais ou atualizações na correção.</span><span class="sxs-lookup"><span data-stu-id="0db63-241">You can now make additional edits or updates to the correction.</span></span> <span data-ttu-id="0db63-242">Quando terminar, você poderá marcar a correção como concluída novamente.</span><span class="sxs-lookup"><span data-stu-id="0db63-242">When you've finished, you can mark the correction as completed again.</span></span>

## <a name="close-a-nonconformance"></a><span data-ttu-id="0db63-243">Fechar uma não conformidade</span><span class="sxs-lookup"><span data-stu-id="0db63-243">Close a nonconformance</span></span>

<span data-ttu-id="0db63-244">Para fechar uma não conformidade, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="0db63-244">To close a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="0db63-245">Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Ordens de qualidade**.</span><span class="sxs-lookup"><span data-stu-id="0db63-245">Go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>
1. <span data-ttu-id="0db63-246">Selecione uma ordem de qualidade na grade.</span><span class="sxs-lookup"><span data-stu-id="0db63-246">Select a quality order in the grid.</span></span>
1. <span data-ttu-id="0db63-247">No Painel de Ações, selecione **Consultas \> Não conformidades**.</span><span class="sxs-lookup"><span data-stu-id="0db63-247">On the Action Pane, select **Inquiries \> Non conformances**.</span></span>
1. <span data-ttu-id="0db63-248">Na página **Não conformidades**, selecione a não conformidade de destino na grade.</span><span class="sxs-lookup"><span data-stu-id="0db63-248">On the **Non conformances** page, select the target nonconformance in the grid.</span></span>
1. <span data-ttu-id="0db63-249">No Painel de Ações, selecione **Funções \> Fechar não conformidades**.</span><span class="sxs-lookup"><span data-stu-id="0db63-249">On the Action Pane, select **Functions \> Close non conformance**.</span></span>
1. <span data-ttu-id="0db63-250">Será solicitado que você confirme sua seleção.</span><span class="sxs-lookup"><span data-stu-id="0db63-250">You're prompted to confirm your selection.</span></span> <span data-ttu-id="0db63-251">Selecione **Sim** para continuar.</span><span class="sxs-lookup"><span data-stu-id="0db63-251">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="0db63-252">Feche as páginas.</span><span class="sxs-lookup"><span data-stu-id="0db63-252">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0db63-253">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="0db63-253">Additional resources</span></span>

- [<span data-ttu-id="0db63-254">Visão geral do gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="0db63-254">Quality management overview</span></span>](../quality-management-processes.md)
- [<span data-ttu-id="0db63-255">Habilitar gerenciamento de qualidade e não conformidade</span><span class="sxs-lookup"><span data-stu-id="0db63-255">Enable quality and nonconformance management</span></span>](../enable-quality-management.md)
- [<span data-ttu-id="0db63-256">Trabalhadores responsáveis por aprovar não conformidades</span><span class="sxs-lookup"><span data-stu-id="0db63-256">Workers responsible for approving nonconformances</span></span>](../quality-responsible-workers.md)
- [<span data-ttu-id="0db63-257">Zonas de quarentena para não conformidades</span><span class="sxs-lookup"><span data-stu-id="0db63-257">Quarantine zones for nonconformances</span></span>](../quality-quarantine-zones.md)
- [<span data-ttu-id="0db63-258">Tipos de diagnóstico para não conformidades</span><span class="sxs-lookup"><span data-stu-id="0db63-258">Diagnostic types for nonconformances</span></span>](../quality-diagnostic-types.md)
- [<span data-ttu-id="0db63-259">Encargos de qualidade para não conformidades</span><span class="sxs-lookup"><span data-stu-id="0db63-259">Quality charges for nonconformances</span></span>](../quality-charges.md)
- [<span data-ttu-id="0db63-260">Operações para não conformidades</span><span class="sxs-lookup"><span data-stu-id="0db63-260">Operations for nonconformances</span></span>](../quality-operations.md)
- [<span data-ttu-id="0db63-261">Gerenciamento de qualidade para processos de depósito</span><span class="sxs-lookup"><span data-stu-id="0db63-261">Quality management for warehouse processes</span></span>](../quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
