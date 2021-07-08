---
title: Grupos de gerenciamento de reembolso
description: Este tópico descreve como configurar Grupos de gerenciamento de reembolso. Os grupos de gerenciamento de reembolso podem ser usados durante cálculos de reembolso e podem ser anexados a um registro mestre.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: ee5a195b3d2881ff70fb1f0d4063ed681e874648
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271068"
---
# <a name="rebate-management-groups"></a><span data-ttu-id="82c45-104">Grupos de gerenciamento de reembolsos</span><span class="sxs-lookup"><span data-stu-id="82c45-104">Rebate management groups</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="82c45-105">Os cálculos de gerenciamento de reembolso e deduções podem ser orientados por grupos.</span><span class="sxs-lookup"><span data-stu-id="82c45-105">Rebate management calculations can be driven by groups.</span></span> <span data-ttu-id="82c45-106">Os grupos de gerenciamento de reembolso podem ser criados para clientes, fornecedores e itens.</span><span class="sxs-lookup"><span data-stu-id="82c45-106">Rebate management groups can be created for customers, vendors, and items.</span></span> <span data-ttu-id="82c45-107">Eles podem ser anexados a um registro mestre.</span><span class="sxs-lookup"><span data-stu-id="82c45-107">They can be attached to a master record.</span></span>

## <a name="rebate-management-customer-groups"></a><span data-ttu-id="82c45-108">Grupos de clientes de gerenciamento de reembolso</span><span class="sxs-lookup"><span data-stu-id="82c45-108">Rebate management customer groups</span></span>

<span data-ttu-id="82c45-109">O cálculo de um grupo de clientes em geral é criado para uma cadeia de empresas, como uma rede de supermercados ou uma empresa de franquia.</span><span class="sxs-lookup"><span data-stu-id="82c45-109">The calculation for a group of customers is often created for a chain of companies, such as a supermarket chain or a franchise company.</span></span> <span data-ttu-id="82c45-110">Esse tipo de cálculo costuma estar relacionado a um reembolso.</span><span class="sxs-lookup"><span data-stu-id="82c45-110">This type of calculation is usually related to a rebate.</span></span>

<span data-ttu-id="82c45-111">Uma dedução é frequentemente calculada sem considerar a quem a ordem de qualificação foi vendida.</span><span class="sxs-lookup"><span data-stu-id="82c45-111">A deduction is often calculated without considering who the qualifying order was sold to.</span></span> <span data-ttu-id="82c45-112">Mas existem exceções.</span><span class="sxs-lookup"><span data-stu-id="82c45-112">However, there are exceptions.</span></span> <span data-ttu-id="82c45-113">Por exemplo, um licenciado pode criar um esquema de dedução em que o grupo de clientes A receberá 4%, mas o grupo de clientes B só receberá 3%.</span><span class="sxs-lookup"><span data-stu-id="82c45-113">For example, a licensee might create a deduction scheme where customer group A will receive 4 percent, but customer group B will receive only 3 percent.</span></span>

### <a name="set-up-customer-groups"></a><span data-ttu-id="82c45-114">Configurar grupos de clientes</span><span class="sxs-lookup"><span data-stu-id="82c45-114">Set up customer groups</span></span>

<span data-ttu-id="82c45-115">Para trabalhar com grupos de clientes de Gerenciamento de reembolso, acesse **Gerenciamento de reembolso \> Configuração de grupos de gerenciamento de reembolso \> Grupos de clientes**.</span><span class="sxs-lookup"><span data-stu-id="82c45-115">To work with Rebate management customer groups, go to **Rebate management \> Rebate management groups setup \> Customer groups**.</span></span> <span data-ttu-id="82c45-116">Você pode usar os botões no Painel de Ações para adicionar e remover grupos, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="82c45-116">You can use the buttons on the Action Pane to add and remove groups as required.</span></span> <span data-ttu-id="82c45-117">Em cada grupo, defina os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="82c45-117">For each group, set the following fields:</span></span>

- <span data-ttu-id="82c45-118">**Grupo de gerenciamento de reembolso** – insira um nome exclusivo para o grupo.</span><span class="sxs-lookup"><span data-stu-id="82c45-118">**Rebate management group** – Enter a unique name for the group.</span></span>
- <span data-ttu-id="82c45-119">**Descrição** – Insira uma descrição do grupo para fornecer mais informações sobre como ela deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="82c45-119">**Description** – Enter a description of the group to provide more information about how it should be used.</span></span>

### <a name="manage-customer-group-assignments"></a><span data-ttu-id="82c45-120">Gerenciar atribuições de grupos de clientes</span><span class="sxs-lookup"><span data-stu-id="82c45-120">Manage customer group assignments</span></span>

<span data-ttu-id="82c45-121">Cada cliente pode pertencer a qualquer número de Grupos de gerenciamento de reembolso.</span><span class="sxs-lookup"><span data-stu-id="82c45-121">Each customer can belong to any number of Rebate management groups.</span></span> <span data-ttu-id="82c45-122">Para exibir e atribuir membros do grupo, você pode iniciar na lista de grupos ou na lista de clientes.</span><span class="sxs-lookup"><span data-stu-id="82c45-122">To view and assign group members, you can start from either the group list or the customer list.</span></span>

<span data-ttu-id="82c45-123">Para exibir, adicionar ou remover clientes de um grupo selecionado, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="82c45-123">To view, add, or remove customers for a selected group, follow these steps.</span></span>

1. <span data-ttu-id="82c45-124">Acesse **Gerenciamento de reembolso \> Configuração de grupos de gerenciamento de reembolso \> Grupos de clientes**.</span><span class="sxs-lookup"><span data-stu-id="82c45-124">Go to **Rebate management \> Rebate management groups setup \> Customer groups**.</span></span>
1. <span data-ttu-id="82c45-125">Selecione o grupo a ser gerenciado.</span><span class="sxs-lookup"><span data-stu-id="82c45-125">Select the group to manage.</span></span>
1. <span data-ttu-id="82c45-126">No Painel de Ações, selecione **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="82c45-126">On the Action Pane, select **Customers**.</span></span> <span data-ttu-id="82c45-127">A página **Grupos de gerenciamento de reembolso** aparece e mostra uma lista de clientes que já são membros do grupo selecionado.</span><span class="sxs-lookup"><span data-stu-id="82c45-127">The **Rebate management groups** page appears and shows a list of customers that are already members of the selected group.</span></span>
1. <span data-ttu-id="82c45-128">Para adicionar um novo cliente ao grupo, selecione **Novo** no Painel de Ações para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="82c45-128">To add a new customer to the group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="82c45-129">Defina o seguinte campo para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="82c45-129">Then set the following field for the new row:</span></span>

    - <span data-ttu-id="82c45-130">**Conta de cliente** – Selecione a ID de conta do cliente.</span><span class="sxs-lookup"><span data-stu-id="82c45-130">**Customer account** – Select the customer account ID.</span></span>

1. <span data-ttu-id="82c45-131">Para remover um cliente do grupo, selecione o cliente e, depois, selecione **Excluir** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="82c45-131">To remove a customer from the group, select the customer, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="82c45-132">Para exibir, adicionar ou remover atribuições de grupo para um cliente selecionado, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="82c45-132">To view, add, or remove group assignments for a selected customer, follow these steps.</span></span>

1. <span data-ttu-id="82c45-133">Ir para **Contas recebíveis \> Clientes \> Todos os clientes**.</span><span class="sxs-lookup"><span data-stu-id="82c45-133">Go to **Accounts receivable \> Customers \> All customers**.</span></span>
1. <span data-ttu-id="82c45-134">Selecione o cliente com o qual deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="82c45-134">Select the customer to work with.</span></span>
1. <span data-ttu-id="82c45-135">No Painel de Ações, na guia **Cliente**, no grupo **Gerenciamento de reembolso**, selecione **Grupos de gerenciamento de reembolso**.</span><span class="sxs-lookup"><span data-stu-id="82c45-135">On the Action Pane, on the **Customer** tab, in the **Rebate management** group, select **Rebate management groups**.</span></span> <span data-ttu-id="82c45-136">A página **Grupos de gerenciamento de reembolso** aparece e mostra uma lista de grupos aos quais o cliente selecionado já pertence.</span><span class="sxs-lookup"><span data-stu-id="82c45-136">The **Rebate management groups** page appears and shows a list of groups that the selected customer already belongs to.</span></span>
1. <span data-ttu-id="82c45-137">Para adicionar o cliente a um novo grupo, selecione **Novo** no Painel de Ações para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="82c45-137">To add the customer to a new group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="82c45-138">Defina o seguinte campo para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="82c45-138">Then set the following field for the new row:</span></span>

    - <span data-ttu-id="82c45-139">**Grupo de gerenciamento de reembolso** – Selecione o grupo ao qual o cliente será adicionado.</span><span class="sxs-lookup"><span data-stu-id="82c45-139">**Rebate management group** – Select the group to add the customer to.</span></span>

1. <span data-ttu-id="82c45-140">Para remover um cliente de um grupo, selecione o grupo e, depois, selecione **Excluir** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="82c45-140">To remove a customer from a group, select the group, and then select **Delete** on the Action Pane.</span></span>

## <a name="rebate-management-vendor-groups"></a><span data-ttu-id="82c45-141">Grupos de fornecedores de gerenciamento de reembolso</span><span class="sxs-lookup"><span data-stu-id="82c45-141">Rebate management vendor groups</span></span>

<span data-ttu-id="82c45-142">O cálculo de um grupo de fornecedores em geral é criado para um grupo de pontos de entrega.</span><span class="sxs-lookup"><span data-stu-id="82c45-142">The calculation for a group of vendors is often created for a group of delivery points.</span></span> <span data-ttu-id="82c45-143">Esse tipo de cálculo costuma estar relacionado a um reembolso.</span><span class="sxs-lookup"><span data-stu-id="82c45-143">This type of calculation is usually related to a rebate.</span></span>

### <a name="set-up-vendor-groups"></a><span data-ttu-id="82c45-144">Configurar grupos de fornecedor​es</span><span class="sxs-lookup"><span data-stu-id="82c45-144">Set up vendor groups</span></span>

<span data-ttu-id="82c45-145">Para trabalhar com grupos de fornecedores de Gerenciamento de reembolso, acesse **Gerenciamento de reembolso \> Configuração de grupos de gerenciamento de reembolso \> Grupos de fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="82c45-145">To work with Rebate management vendor groups, go to **Rebate management \> Rebate management groups setup \> Vendor groups**.</span></span> <span data-ttu-id="82c45-146">Você pode usar os botões no Painel de Ações para adicionar e remover grupos, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="82c45-146">You can use the buttons on the Action Pane to add and remove groups as required.</span></span> <span data-ttu-id="82c45-147">Em cada grupo, defina os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="82c45-147">For each group, set the following fields:</span></span>

- <span data-ttu-id="82c45-148">**Grupo de gerenciamento de reembolso** – insira um nome exclusivo para o grupo.</span><span class="sxs-lookup"><span data-stu-id="82c45-148">**Rebate management group** – Enter a unique name for the group.</span></span>
- <span data-ttu-id="82c45-149">**Descrição** – Insira uma descrição do grupo para fornecer mais informações sobre como ela deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="82c45-149">**Description** – Enter a description of the group to provide more information about how it should be used.</span></span>

### <a name="manage-vendor-group-assignments"></a><span data-ttu-id="82c45-150">Gerenciar atribuições de grupos de fornecedores</span><span class="sxs-lookup"><span data-stu-id="82c45-150">Manage vendor group assignments</span></span>

<span data-ttu-id="82c45-151">Cada fornecedor pode pertencer a qualquer número de Grupos de gerenciamento de reembolso.</span><span class="sxs-lookup"><span data-stu-id="82c45-151">Each vendor can belong to any number of Rebate management groups.</span></span> <span data-ttu-id="82c45-152">Para exibir e atribuir membros do grupo, você pode iniciar na lista de grupos ou na lista de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="82c45-152">To view and assign group members, you can start from either the group list or the vendor list.</span></span>

<span data-ttu-id="82c45-153">Para exibir, adicionar ou remover fornecedores de um grupo selecionado, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="82c45-153">To view, add, or remove vendors for a selected group, follow these steps.</span></span>

1. <span data-ttu-id="82c45-154">Acesse **Gerenciamento de reembolso \> Configuração de grupos de gerenciamento de reembolso \> Grupos de fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="82c45-154">Go to **Rebate management \> Rebate management groups setup \> Vendor groups**.</span></span>
1. <span data-ttu-id="82c45-155">Selecione o grupo a ser gerenciado.</span><span class="sxs-lookup"><span data-stu-id="82c45-155">Select the group to manage.</span></span>
1. <span data-ttu-id="82c45-156">No Painel de Ações, selecione **Fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="82c45-156">On the Action Pane, select **Vendors**.</span></span> <span data-ttu-id="82c45-157">A página **Grupos de gerenciamento de reembolso** aparece e mostra uma lista de fornecedores que já são membros do grupo selecionado.</span><span class="sxs-lookup"><span data-stu-id="82c45-157">The **Rebate management groups** page appears and shows a list of vendors that are already members of the selected group.</span></span>
1. <span data-ttu-id="82c45-158">Para adicionar um novo fornecedor ao grupo, selecione **Novo** no Painel de Ações para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="82c45-158">To add a new vendor to the group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="82c45-159">Defina o seguinte campo para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="82c45-159">Then set the following field for the new row:</span></span>

    - <span data-ttu-id="82c45-160">**Conta de fornecedor** – Selecione a ID de conta do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="82c45-160">**Vendor account** – Select the vendor account ID.</span></span>

1. <span data-ttu-id="82c45-161">Para remover um fornecedor do grupo, selecione o fornecedor e, depois, selecione **Excluir** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="82c45-161">To remove a vendor from the group, select the vendor, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="82c45-162">Para exibir, adicionar ou remover atribuições de grupo para um fornecedor selecionado, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="82c45-162">To view, add, or remove group assignments for a selected vendor, follow these steps.</span></span>

1. <span data-ttu-id="82c45-163">Acesse **Contas a pagar \> Fornecedores \> Todos os fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="82c45-163">Go to **Accounts payable \> Vendors \> All vendors**.</span></span>
1. <span data-ttu-id="82c45-164">Selecione o fornecedor com o qual deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="82c45-164">Select the vendor to work with.</span></span>
1. <span data-ttu-id="82c45-165">No Painel de Ações, na guia **Fornecedor**, no grupo **Gerenciamento de reembolso**, selecione **Grupos de gerenciamento de reembolso**.</span><span class="sxs-lookup"><span data-stu-id="82c45-165">On the Action Pane, on the **Vendor** tab, in the **Rebate management** group, select **Rebate management groups**.</span></span> <span data-ttu-id="82c45-166">A página **Grupos de gerenciamento de reembolso** aparece e mostra uma lista de grupos aos quais o fornecedor selecionado já pertence.</span><span class="sxs-lookup"><span data-stu-id="82c45-166">The **Rebate management groups** page appears and shows a list of groups that the selected vendor already belongs to.</span></span>
1. <span data-ttu-id="82c45-167">Para adicionar o fornecedor a um novo grupo, selecione **Novo** no Painel de Ações para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="82c45-167">To add the vendor to a new group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="82c45-168">Defina o seguinte campo para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="82c45-168">Then set the following field for the new row:</span></span>

    - <span data-ttu-id="82c45-169">**Grupo de gerenciamento de reembolso** – Selecione o grupo ao qual o fornecedor será adicionado.</span><span class="sxs-lookup"><span data-stu-id="82c45-169">**Rebate management group** – Select the group to add the vendor to.</span></span>

1. <span data-ttu-id="82c45-170">Para remover um fornecedor de um grupo, selecione o grupo e, depois, selecione **Excluir** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="82c45-170">To remove a vendor from a group, select the group, and then select **Delete** on the Action Pane.</span></span>

## <a name="item-rebate-groups"></a><span data-ttu-id="82c45-171">Grupos de reembolsos de itens</span><span class="sxs-lookup"><span data-stu-id="82c45-171">Item rebate groups</span></span>

<span data-ttu-id="82c45-172">Ao agrupar itens, você tem mais flexibilidade quando reembolsos e deduções são calculadas.</span><span class="sxs-lookup"><span data-stu-id="82c45-172">By grouping items, you have more flexibility when rebates and deductions are calculated.</span></span> <span data-ttu-id="82c45-173">Essa abordagem frequentemente é uma maneira mais eficiente de configurar reembolsos e deduções para clientes e fornecedores.</span><span class="sxs-lookup"><span data-stu-id="82c45-173">This approach is often a more efficient way to set up rebates and deductions for customers and vendors.</span></span>

### <a name="set-up-item-groups"></a><span data-ttu-id="82c45-174">Configurar grupos de itens</span><span class="sxs-lookup"><span data-stu-id="82c45-174">Set up item groups</span></span>

<span data-ttu-id="82c45-175">Para trabalhar com grupos de itens de Gerenciamento de reembolso, acesse **Gerenciamento de reembolso \> Configuração de grupos de gerenciamento de reembolso \> Grupos de itens**.</span><span class="sxs-lookup"><span data-stu-id="82c45-175">To work with Rebate management item groups, go to **Rebate management \> Rebate management groups setup \> Item groups**.</span></span> <span data-ttu-id="82c45-176">Você pode usar os botões no Painel de Ações para adicionar e remover grupos, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="82c45-176">You can use the buttons on the Action Pane to add and remove groups as required.</span></span> <span data-ttu-id="82c45-177">Em cada grupo, defina os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="82c45-177">For each group, set the following fields:</span></span>

- <span data-ttu-id="82c45-178">**Grupo de gerenciamento de reembolso** – insira um nome exclusivo para o grupo.</span><span class="sxs-lookup"><span data-stu-id="82c45-178">**Rebate management group** – Enter a unique name for the group.</span></span>
- <span data-ttu-id="82c45-179">**Descrição** – Insira uma descrição do grupo para fornecer mais informações sobre como ela deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="82c45-179">**Description** – Enter a description of the group to provide more information about how it should be used.</span></span>

### <a name="manage-item-group-assignments"></a><span data-ttu-id="82c45-180">Gerenciar atribuições de grupos de itens</span><span class="sxs-lookup"><span data-stu-id="82c45-180">Manage item group assignments</span></span>

<span data-ttu-id="82c45-181">Cada item pode pertencer a qualquer número de Grupos de gerenciamento de reembolso.</span><span class="sxs-lookup"><span data-stu-id="82c45-181">Each item can belong to any number of Rebate management groups.</span></span> <span data-ttu-id="82c45-182">Para exibir e atribuir membros do grupo, você pode iniciar na lista de grupos ou na lista de itens.</span><span class="sxs-lookup"><span data-stu-id="82c45-182">To view and assign group members, you can start from either the group list or the item list.</span></span> <span data-ttu-id="82c45-183">Você também pode adicionar itens com base na sua hierarquia de categoria.</span><span class="sxs-lookup"><span data-stu-id="82c45-183">You can also add items based on your category hierarchy.</span></span>

<span data-ttu-id="82c45-184">Para exibir, adicionar ou remover itens de um grupo selecionado, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="82c45-184">To view, add, or remove items for a selected group, follow these steps.</span></span>

1. <span data-ttu-id="82c45-185">Acesse **Gerenciamento de reembolso \> Configuração de grupos de gerenciamento de reembolso \> Grupos de itens**.</span><span class="sxs-lookup"><span data-stu-id="82c45-185">Go to **Rebate management \> Rebate management groups setup \> Item groups**.</span></span>
1. <span data-ttu-id="82c45-186">Selecione o grupo a ser gerenciado.</span><span class="sxs-lookup"><span data-stu-id="82c45-186">Select the group to manage.</span></span>
1. <span data-ttu-id="82c45-187">No Painel de Ações, selecione **Itens**.</span><span class="sxs-lookup"><span data-stu-id="82c45-187">On the Action Pane, select **Items**.</span></span> <span data-ttu-id="82c45-188">A página **Grupos de gerenciamento de reembolso** aparece e mostra uma lista de itens que já são membros do grupo selecionado.</span><span class="sxs-lookup"><span data-stu-id="82c45-188">The **Rebate management groups** page appears and shows a list of items that are already members of the selected group.</span></span>
1. <span data-ttu-id="82c45-189">Para adicionar um novo item ao grupo, selecione **Novo** no Painel de Ações para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="82c45-189">To add a new item to the group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="82c45-190">Defina o seguinte campo para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="82c45-190">Then set the following field for the new row:</span></span>

    - <span data-ttu-id="82c45-191">**Conta de item** – Selecione a ID de conta do item.</span><span class="sxs-lookup"><span data-stu-id="82c45-191">**Item account** – Select the item account ID.</span></span>

1. <span data-ttu-id="82c45-192">Para remover um item do grupo, selecione o item e, depois, selecione **Excluir** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="82c45-192">To remove an item from the group, select the item, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="82c45-193">Para exibir, adicionar ou remover atribuições de grupo para um item selecionado, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="82c45-193">To view, add, or remove group assignments for a selected item, follow these steps.</span></span>

1. <span data-ttu-id="82c45-194">Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="82c45-194">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="82c45-195">Selecione o item com o qual deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="82c45-195">Select the item to work with.</span></span>
1. <span data-ttu-id="82c45-196">No Painel de Ações, na guia **Produto**, no grupo **Gerenciamento de reembolso**, selecione **Grupos de gerenciamento de reembolso**.</span><span class="sxs-lookup"><span data-stu-id="82c45-196">On the Action Pane, on the **Product** tab, in the **Rebate management** group, select **Rebate management groups**.</span></span> <span data-ttu-id="82c45-197">A página **Grupos de gerenciamento de reembolso** aparece e mostra uma lista de grupos aos quais o item selecionado já pertence.</span><span class="sxs-lookup"><span data-stu-id="82c45-197">The **Rebate management groups** page appears and shows a list of groups that the selected item already belongs to.</span></span>
1. <span data-ttu-id="82c45-198">Para adicionar o item a um novo grupo, selecione **Novo** no Painel de Ações para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="82c45-198">To add the item to a new group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="82c45-199">Defina o seguinte campo para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="82c45-199">Then set the following field for the new row:</span></span>

    - <span data-ttu-id="82c45-200">**Grupo de gerenciamento de reembolso** – Selecione o grupo ao qual o item será adicionado.</span><span class="sxs-lookup"><span data-stu-id="82c45-200">**Rebate management group** – Select the group to add the item to.</span></span>

1. <span data-ttu-id="82c45-201">Para remover um item de um grupo, selecione o grupo e, depois, selecione **Excluir** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="82c45-201">To remove an item from a group, select the group, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="82c45-202">Para adicionar itens a um grupo com base na sua hierarquia de categoria, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="82c45-202">To add items to a group based on your category hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="82c45-203">Acesse **Gerenciamento de reembolso \> Configuração de grupos de gerenciamento de reembolso \> Grupos de itens**.</span><span class="sxs-lookup"><span data-stu-id="82c45-203">Go to **Rebate management \> Rebate management groups setup \> Item groups**.</span></span>
1. <span data-ttu-id="82c45-204">Selecione o grupo a ser gerenciado.</span><span class="sxs-lookup"><span data-stu-id="82c45-204">Select the group to manage.</span></span>
1. <span data-ttu-id="82c45-205">No Painel de Ações, selecione **Adicionar itens**.</span><span class="sxs-lookup"><span data-stu-id="82c45-205">On the Action Pane, select **Add items**.</span></span>
1. <span data-ttu-id="82c45-206">Na caixa de diálogo **Adicionar itens**, no campo **Hierarquia de categoria**, selecione uma categoria de nível superior.</span><span class="sxs-lookup"><span data-stu-id="82c45-206">In the **Add items** dialog box, in the **Category hierarchy** field, select a top-level category.</span></span>
1. <span data-ttu-id="82c45-207">A hierarquia de itens é aberta no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="82c45-207">The item hierarchy is opened in the left pane.</span></span> <span data-ttu-id="82c45-208">Selecione o nível de hierarquia que você procura.</span><span class="sxs-lookup"><span data-stu-id="82c45-208">Select the hierarchy level that you're looking for.</span></span> 
1. <span data-ttu-id="82c45-209">Os itens da hierarquia e do nível de hierarquia selecionados agora são listados no painel à direita.</span><span class="sxs-lookup"><span data-stu-id="82c45-209">Items from the selected hierarchy and hierarchy level are now listed in the right pane.</span></span> <span data-ttu-id="82c45-210">Siga estas etapas para trabalhar com o painel:</span><span class="sxs-lookup"><span data-stu-id="82c45-210">Follow these steps to work with the pane:</span></span>

    - <span data-ttu-id="82c45-211">Marque a caixa de seleção de cada item a ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="82c45-211">Select the check box for each item that you want to add.</span></span>
    - <span data-ttu-id="82c45-212">Marque a caixa de seleção no cabeçalho da grade para selecionar todos os itens listados.</span><span class="sxs-lookup"><span data-stu-id="82c45-212">Select the check box on the grid header to select all the items that are listed.</span></span>
    - <span data-ttu-id="82c45-213">Selecione o botão **Mostrar selecionado** para filtrar a grade de forma que ela mostre apenas os itens selecionados até o momento.</span><span class="sxs-lookup"><span data-stu-id="82c45-213">Select the **Show selected** button to filter the grid so that it shows only the items that you've selected so far.</span></span> <span data-ttu-id="82c45-214">Selecione novamente o botão para retornar à lista completa.</span><span class="sxs-lookup"><span data-stu-id="82c45-214">Select the button again to return to the full list.</span></span>

1. <span data-ttu-id="82c45-215">Selecione **OK** para aplicar a seleção de itens ao grupo selecionado.</span><span class="sxs-lookup"><span data-stu-id="82c45-215">Select **OK** to apply your item selection to the selected group.</span></span>
