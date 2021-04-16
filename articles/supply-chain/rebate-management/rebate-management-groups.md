---
title: Grupos de gerenciamento de reembolso
description: Este tópico descreve como configurar Grupos de gerenciamento de reembolso. Os grupos de gerenciamento de reembolso podem ser usados durante cálculos de reembolso e podem ser anexados a um registro mestre.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TAMRebateGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 2d1f8ed9def03afc97c0b4c5ea86430ff089aac6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819223"
---
# <a name="rebate-management-groups"></a><span data-ttu-id="8a7cc-104">Grupos de gerenciamento de reembolso</span><span class="sxs-lookup"><span data-stu-id="8a7cc-104">Rebate management groups</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="8a7cc-105">Os cálculos de reembolsos e deduções podem ser orientados por grupos.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-105">Rebate and deduction calculations can be driven by groups.</span></span> <span data-ttu-id="8a7cc-106">Os grupos de gerenciamento de reembolso podem ser criados para clientes, fornecedores e itens.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-106">Rebate management groups can be created for customers, vendors, and items.</span></span> <span data-ttu-id="8a7cc-107">Eles podem ser anexados a um registro mestre.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-107">They can be attached to a master record.</span></span>

## <a name="rebate-management-customer-groups"></a><span data-ttu-id="8a7cc-108">Grupos de clientes de gerenciamento de reembolso</span><span class="sxs-lookup"><span data-stu-id="8a7cc-108">Rebate management customer groups</span></span>

<span data-ttu-id="8a7cc-109">O cálculo de um grupo de clientes em geral é criado para uma cadeia de empresas, como uma rede de supermercados ou uma empresa de franquia.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-109">The calculation for a group of customers is often created for a chain of companies, such as a supermarket chain or a franchise company.</span></span> <span data-ttu-id="8a7cc-110">Esse tipo de cálculo costuma estar relacionado a um reembolso.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-110">This type of calculation is usually related to a rebate.</span></span>

<span data-ttu-id="8a7cc-111">Uma dedução é frequentemente calculada sem considerar a quem a ordem de qualificação foi vendida.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-111">A deduction is often calculated without considering who the qualifying order was sold to.</span></span> <span data-ttu-id="8a7cc-112">Mas existem exceções.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-112">However, there are exceptions.</span></span> <span data-ttu-id="8a7cc-113">Por exemplo, um licenciado pode criar um esquema de dedução em que o grupo de clientes A receberá 4%, mas o grupo de clientes B só receberá 3%.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-113">For example, a licensee might create a deduction scheme where customer group A will receive 4 percent, but customer group B will receive only 3 percent.</span></span>

### <a name="set-up-customer-groups"></a><span data-ttu-id="8a7cc-114">Configurar grupos de clientes</span><span class="sxs-lookup"><span data-stu-id="8a7cc-114">Set up customer groups</span></span>

<span data-ttu-id="8a7cc-115">Para trabalhar com grupos de clientes de Gerenciamento de reembolso, acesse **Gerenciamento de reembolso \> Configuração de grupos de gerenciamento de reembolso \> Grupos de clientes**.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-115">To work with Rebate management customer groups, go to **Rebate management \> Rebate management groups setup \> Customer groups**.</span></span> <span data-ttu-id="8a7cc-116">Você pode usar os botões no Painel de Ações para adicionar e remover grupos, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-116">You can use the buttons on the Action Pane to add and remove groups as required.</span></span> <span data-ttu-id="8a7cc-117">Em cada grupo, defina os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="8a7cc-117">For each group, set the following fields:</span></span>

- <span data-ttu-id="8a7cc-118">**Grupo de gerenciamento de reembolso** – insira um nome exclusivo para o grupo.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-118">**Rebate management group** – Enter a unique name for the group.</span></span>
- <span data-ttu-id="8a7cc-119">**Descrição** – Insira uma descrição do grupo para fornecer mais informações sobre como ela deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-119">**Description** – Enter a description of the group to provide more information about how it should be used.</span></span>

### <a name="manage-customer-group-assignments"></a><span data-ttu-id="8a7cc-120">Gerenciar atribuições de grupos de clientes</span><span class="sxs-lookup"><span data-stu-id="8a7cc-120">Manage customer group assignments</span></span>

<span data-ttu-id="8a7cc-121">Cada cliente pode pertencer a qualquer número de Grupos de gerenciamento de reembolso.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-121">Each customer can belong to any number of Rebate management groups.</span></span> <span data-ttu-id="8a7cc-122">Para exibir e atribuir membros do grupo, você pode iniciar na lista de grupos ou na lista de clientes.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-122">To view and assign group members, you can start from either the group list or the customer list.</span></span>

<span data-ttu-id="8a7cc-123">Para exibir, adicionar ou remover clientes de um grupo selecionado, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-123">To view, add, or remove customers for a selected group, follow these steps.</span></span>

1. <span data-ttu-id="8a7cc-124">Acesse **Gerenciamento de reembolso \> Configuração de grupos de gerenciamento de reembolso \> Grupos de clientes**.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-124">Go to **Rebate management \> Rebate management groups setup \> Customer groups**.</span></span>
1. <span data-ttu-id="8a7cc-125">Selecione o grupo a ser gerenciado.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-125">Select the group to manage.</span></span>
1. <span data-ttu-id="8a7cc-126">No Painel de Ações, selecione **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-126">On the Action Pane, select **Customers**.</span></span> <span data-ttu-id="8a7cc-127">A página **Grupos de gerenciamento de reembolso** aparece e mostra uma lista de clientes que já são membros do grupo selecionado.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-127">The **Rebate management groups** page appears and shows a list of customers that are already members of the selected group.</span></span>
1. <span data-ttu-id="8a7cc-128">Para adicionar um novo cliente ao grupo, selecione **Novo** no Painel de Ações para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-128">To add a new customer to the group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="8a7cc-129">Defina os seguintes campos para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="8a7cc-129">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="8a7cc-130">**Conta de cliente** – Selecione a ID de conta do cliente.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-130">**Customer account** – Select the customer account ID.</span></span>
    - <span data-ttu-id="8a7cc-131">**Nome** – Insira um nome e/ou descrição do cliente.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-131">**Name** – Enter a name and/or description of the customer.</span></span>

1. <span data-ttu-id="8a7cc-132">Para remover um cliente do grupo, selecione o cliente e, depois, selecione **Excluir** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-132">To remove a customer from the group, select the customer, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="8a7cc-133">Para exibir, adicionar ou remover atribuições de grupo para um cliente selecionado, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-133">To view, add, or remove group assignments for a selected customer, follow these steps.</span></span>

1. <span data-ttu-id="8a7cc-134">Ir para **Contas recebíveis \> Clientes \> Todos os clientes**.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-134">Go to **Accounts receivable \> Customers \> All customers**.</span></span>
1. <span data-ttu-id="8a7cc-135">Selecione o cliente com o qual deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-135">Select the customer to work with.</span></span>
1. <span data-ttu-id="8a7cc-136">No Painel de Ações, na guia **Cliente**, no grupo **Gerenciamento de reembolso**, selecione **Grupos de gerenciamento de reembolso**.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-136">On the Action Pane, on the **Customer** tab, in the **Rebate management** group, select **Rebate management groups**.</span></span> <span data-ttu-id="8a7cc-137">A página **Grupos de gerenciamento de reembolso** aparece e mostra uma lista de grupos aos quais o cliente selecionado já pertence.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-137">The **Rebate management groups** page appears and shows a list of groups that the selected customer already belongs to.</span></span>
1. <span data-ttu-id="8a7cc-138">Para adicionar o cliente a um novo grupo, selecione **Novo** no Painel de Ações para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-138">To add the customer to a new group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="8a7cc-139">Defina os seguintes campos para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="8a7cc-139">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="8a7cc-140">**Grupo de gerenciamento de reembolso** – Selecione o grupo ao qual o cliente será adicionado.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-140">**Rebate management group** – Select the group to add the customer to.</span></span>
    - <span data-ttu-id="8a7cc-141">**Descrição** – Insira uma descrição do grupo (por exemplo, para explicar por que o cliente é membro dele).</span><span class="sxs-lookup"><span data-stu-id="8a7cc-141">**Description** – Enter a description of the group (for example, to explain why the customer is a member of it).</span></span>

1. <span data-ttu-id="8a7cc-142">Para remover um cliente de um grupo, selecione o grupo e, depois, selecione **Excluir** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-142">To remove a customer from a group, select the group, and then select **Delete** on the Action Pane.</span></span>

## <a name="rebate-management-vendor-groups"></a><span data-ttu-id="8a7cc-143">Grupos de fornecedores de gerenciamento de reembolso</span><span class="sxs-lookup"><span data-stu-id="8a7cc-143">Rebate management vendor groups</span></span>

<span data-ttu-id="8a7cc-144">O cálculo de um grupo de fornecedores em geral é criado para um grupo de pontos de entrega.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-144">The calculation for a group of vendors is often created for a group of delivery points.</span></span> <span data-ttu-id="8a7cc-145">Esse tipo de cálculo costuma estar relacionado a um reembolso.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-145">This type of calculation is usually related to a rebate.</span></span>

### <a name="set-up-vendor-groups"></a><span data-ttu-id="8a7cc-146">Configurar grupos de fornecedor​es</span><span class="sxs-lookup"><span data-stu-id="8a7cc-146">Set up vendor groups</span></span>

<span data-ttu-id="8a7cc-147">Para trabalhar com grupos de fornecedores de Gerenciamento de reembolso, acesse **Gerenciamento de reembolso \> Configuração de grupos de gerenciamento de reembolso \> Grupos de fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-147">To work with Rebate management vendor groups, go to **Rebate management \> Rebate management groups setup \> Vendor groups**.</span></span> <span data-ttu-id="8a7cc-148">Você pode usar os botões no Painel de Ações para adicionar e remover grupos, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-148">You can use the buttons on the Action Pane to add and remove groups as required.</span></span> <span data-ttu-id="8a7cc-149">Em cada grupo, defina os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="8a7cc-149">For each group, set the following fields:</span></span>

- <span data-ttu-id="8a7cc-150">**Grupo de gerenciamento de reembolso** – insira um nome exclusivo para o grupo.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-150">**Rebate management group** – Enter a unique name for the group.</span></span>
- <span data-ttu-id="8a7cc-151">**Descrição** – Insira uma descrição do grupo para fornecer mais informações sobre como ela deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-151">**Description** – Enter a description of the group to provide more information about how it should be used.</span></span>

### <a name="manage-vendor-group-assignments"></a><span data-ttu-id="8a7cc-152">Gerenciar atribuições de grupos de fornecedores</span><span class="sxs-lookup"><span data-stu-id="8a7cc-152">Manage vendor group assignments</span></span>

<span data-ttu-id="8a7cc-153">Cada fornecedor pode pertencer a qualquer número de Grupos de gerenciamento de reembolso.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-153">Each vendor can belong to any number of Rebate management groups.</span></span> <span data-ttu-id="8a7cc-154">Para exibir e atribuir membros do grupo, você pode iniciar na lista de grupos ou na lista de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-154">To view and assign group members, you can start from either the group list or the vendor list.</span></span>

<span data-ttu-id="8a7cc-155">Para exibir, adicionar ou remover fornecedores de um grupo selecionado, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-155">To view, add, or remove vendors for a selected group, follow these steps.</span></span>

1. <span data-ttu-id="8a7cc-156">Acesse **Gerenciamento de reembolso \> Configuração de grupos de gerenciamento de reembolso \> Grupos de fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-156">Go to **Rebate management \> Rebate management groups setup \> Vendor groups**.</span></span>
1. <span data-ttu-id="8a7cc-157">Selecione o grupo a ser gerenciado.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-157">Select the group to manage.</span></span>
1. <span data-ttu-id="8a7cc-158">No Painel de Ações, selecione **Fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-158">On the Action Pane, select **Vendors**.</span></span> <span data-ttu-id="8a7cc-159">A página **Grupos de gerenciamento de reembolso** aparece e mostra uma lista de fornecedores que já são membros do grupo selecionado.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-159">The **Rebate management groups** page appears and shows a list of vendors that are already members of the selected group.</span></span>
1. <span data-ttu-id="8a7cc-160">Para adicionar um novo fornecedor ao grupo, selecione **Novo** no Painel de Ações para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-160">To add a new vendor to the group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="8a7cc-161">Defina os seguintes campos para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="8a7cc-161">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="8a7cc-162">**Conta de fornecedor** – Selecione a ID de conta do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-162">**Vendor account** – Select the vendor account ID.</span></span>
    - <span data-ttu-id="8a7cc-163">**Nome** – Insira um nome e/ou descrição do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-163">**Name** – Enter a name and/or description of the vendor.</span></span>

1. <span data-ttu-id="8a7cc-164">Para remover um fornecedor do grupo, selecione o fornecedor e, depois, selecione **Excluir** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-164">To remove a vendor from the group, select the vendor, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="8a7cc-165">Para exibir, adicionar ou remover atribuições de grupo para um fornecedor selecionado, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-165">To view, add, or remove group assignments for a selected vendor, follow these steps.</span></span>

1. <span data-ttu-id="8a7cc-166">Acesse **Contas a pagar \> Fornecedores \> Todos os fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-166">Go to **Accounts payable \> Vendors \> All vendors**.</span></span>
1. <span data-ttu-id="8a7cc-167">Selecione o fornecedor com o qual deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-167">Select the vendor to work with.</span></span>
1. <span data-ttu-id="8a7cc-168">No Painel de Ações, na guia **Fornecedor**, no grupo **Gerenciamento de reembolso**, selecione **Grupos de gerenciamento de reembolso**.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-168">On the Action Pane, on the **Vendor** tab, in the **Rebate management** group, select **Rebate management groups**.</span></span> <span data-ttu-id="8a7cc-169">A página **Grupos de gerenciamento de reembolso** aparece e mostra uma lista de grupos aos quais o fornecedor selecionado já pertence.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-169">The **Rebate management groups** page appears and shows a list of groups that the selected vendor already belongs to.</span></span>
1. <span data-ttu-id="8a7cc-170">Para adicionar o fornecedor a um novo grupo, selecione **Novo** no Painel de Ações para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-170">To add the vendor to a new group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="8a7cc-171">Defina os seguintes campos para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="8a7cc-171">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="8a7cc-172">**Grupo de gerenciamento de reembolso** – Selecione o grupo ao qual o fornecedor será adicionado.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-172">**Rebate management group** – Select the group to add the vendor to.</span></span>
    - <span data-ttu-id="8a7cc-173">**Descrição** – Insira uma descrição do grupo (por exemplo, para explicar por que o fornecedor é membro dele).</span><span class="sxs-lookup"><span data-stu-id="8a7cc-173">**Description** – Enter a description of the group (for example, to explain why the vendor is a member of it).</span></span>

1. <span data-ttu-id="8a7cc-174">Para remover um fornecedor de um grupo, selecione o grupo e, depois, selecione **Excluir** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-174">To remove a vendor from a group, select the group, and then select **Delete** on the Action Pane.</span></span>

## <a name="item-rebate-groups"></a><span data-ttu-id="8a7cc-175">Grupos de reembolsos de itens</span><span class="sxs-lookup"><span data-stu-id="8a7cc-175">Item rebate groups</span></span>

<span data-ttu-id="8a7cc-176">Ao agrupar itens, você tem mais flexibilidade quando reembolsos e deduções são calculadas.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-176">By grouping items, you have more flexibility when rebates and deductions are calculated.</span></span> <span data-ttu-id="8a7cc-177">Essa abordagem frequentemente é uma maneira mais eficiente de configurar reembolsos e deduções para clientes e fornecedores.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-177">This approach is often a more efficient way to set up rebates and deductions for customers and vendors.</span></span>

### <a name="set-up-item-groups"></a><span data-ttu-id="8a7cc-178">Configurar grupos de itens</span><span class="sxs-lookup"><span data-stu-id="8a7cc-178">Set up item groups</span></span>

<span data-ttu-id="8a7cc-179">Para trabalhar com grupos de itens de Gerenciamento de reembolso, acesse **Gerenciamento de reembolso \> Configuração de grupos de gerenciamento de reembolso \> Grupos de itens**.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-179">To work with Rebate management item groups, go to **Rebate management \> Rebate management groups setup \> Item groups**.</span></span> <span data-ttu-id="8a7cc-180">Você pode usar os botões no Painel de Ações para adicionar e remover grupos, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-180">You can use the buttons on the Action Pane to add and remove groups as required.</span></span> <span data-ttu-id="8a7cc-181">Em cada grupo, defina os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="8a7cc-181">For each group, set the following fields:</span></span>

- <span data-ttu-id="8a7cc-182">**Grupo de gerenciamento de reembolso** – insira um nome exclusivo para o grupo.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-182">**Rebate management group** – Enter a unique name for the group.</span></span>
- <span data-ttu-id="8a7cc-183">**Descrição** – Insira uma descrição do grupo para fornecer mais informações sobre como ela deve ser usada.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-183">**Description** – Enter a description of the group to provide more information about how it should be used.</span></span>

### <a name="manage-item-group-assignments"></a><span data-ttu-id="8a7cc-184">Gerenciar atribuições de grupos de itens</span><span class="sxs-lookup"><span data-stu-id="8a7cc-184">Manage item group assignments</span></span>

<span data-ttu-id="8a7cc-185">Cada item pode pertencer a qualquer número de Grupos de gerenciamento de reembolso.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-185">Each item can belong to any number of Rebate management groups.</span></span> <span data-ttu-id="8a7cc-186">Para exibir e atribuir membros do grupo, você pode iniciar na lista de grupos ou na lista de itens.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-186">To view and assign group members, you can start from either the group list or the item list.</span></span> <span data-ttu-id="8a7cc-187">Você também pode adicionar itens com base na sua hierarquia de categoria.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-187">You can also add items based on your category hierarchy.</span></span>

<span data-ttu-id="8a7cc-188">Para exibir, adicionar ou remover itens de um grupo selecionado, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-188">To view, add, or remove items for a selected group, follow these steps.</span></span>

1. <span data-ttu-id="8a7cc-189">Acesse **Gerenciamento de reembolso \> Configuração de grupos de gerenciamento de reembolso \> Grupos de itens**.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-189">Go to **Rebate management \> Rebate management groups setup \> Item groups**.</span></span>
1. <span data-ttu-id="8a7cc-190">Selecione o grupo a ser gerenciado.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-190">Select the group to manage.</span></span>
1. <span data-ttu-id="8a7cc-191">No Painel de Ações, selecione **Itens**.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-191">On the Action Pane, select **Items**.</span></span> <span data-ttu-id="8a7cc-192">A página **Grupos de gerenciamento de reembolso** aparece e mostra uma lista de itens que já são membros do grupo selecionado.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-192">The **Rebate management groups** page appears and shows a list of items that are already members of the selected group.</span></span>
1. <span data-ttu-id="8a7cc-193">Para adicionar um novo item ao grupo, selecione **Novo** no Painel de Ações para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-193">To add a new item to the group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="8a7cc-194">Defina os seguintes campos para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="8a7cc-194">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="8a7cc-195">**Conta de item** – Selecione a ID de conta do item.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-195">**Item account** – Select the item account ID.</span></span>
    - <span data-ttu-id="8a7cc-196">**Nome do produto** – Insira um nome e/ou descrição do item.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-196">**Product name** – Enter a name and/or description of the item.</span></span>

1. <span data-ttu-id="8a7cc-197">Para remover um item do grupo, selecione o item e, depois, selecione **Excluir** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-197">To remove an item from the group, select the item, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="8a7cc-198">Para exibir, adicionar ou remover atribuições de grupo para um item selecionado, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-198">To view, add, or remove group assignments for a selected item, follow these steps.</span></span>

1. <span data-ttu-id="8a7cc-199">Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-199">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="8a7cc-200">Selecione o item com o qual deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-200">Select the item to work with.</span></span>
1. <span data-ttu-id="8a7cc-201">No Painel de Ações, na guia **Produto**, no grupo **Gerenciamento de reembolso**, selecione **Grupos de gerenciamento de reembolso**.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-201">On the Action Pane, on the **Product** tab, in the **Rebate management** group, select **Rebate management groups**.</span></span> <span data-ttu-id="8a7cc-202">A página **Grupos de gerenciamento de reembolso** aparece e mostra uma lista de grupos aos quais o item selecionado já pertence.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-202">The **Rebate management groups** page appears and shows a list of groups that the selected item already belongs to.</span></span>
1. <span data-ttu-id="8a7cc-203">Para adicionar o item a um novo grupo, selecione **Novo** no Painel de Ações para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-203">To add the item to a new group, select **New** on the Action Pane to add a row to the grid.</span></span> <span data-ttu-id="8a7cc-204">Defina os seguintes campos para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="8a7cc-204">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="8a7cc-205">**Grupo de gerenciamento de reembolso** – Selecione o grupo ao qual o item será adicionado.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-205">**Rebate management group** – Select the group to add the item to.</span></span>
    - <span data-ttu-id="8a7cc-206">**Descrição** – Insira uma descrição do grupo (por exemplo, para explicar por que o item é membro dele).</span><span class="sxs-lookup"><span data-stu-id="8a7cc-206">**Description** – Enter a description of the group (for example, to explain why the item is a member of it).</span></span>

1. <span data-ttu-id="8a7cc-207">Para remover um item de um grupo, selecione o grupo e, depois, selecione **Excluir** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-207">To remove an item from a group, select the group, and then select **Delete** on the Action Pane.</span></span>

<span data-ttu-id="8a7cc-208">Para adicionar itens a um grupo com base na sua hierarquia de categoria, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-208">To add items to a group based on your category hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="8a7cc-209">Acesse **Gerenciamento de reembolso \> Configuração de grupos de gerenciamento de reembolso \> Grupos de itens**.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-209">Go to **Rebate management \> Rebate management groups setup \> Item groups**.</span></span>
1. <span data-ttu-id="8a7cc-210">Selecione o grupo a ser gerenciado.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-210">Select the group to manage.</span></span>
1. <span data-ttu-id="8a7cc-211">No Painel de Ações, selecione **Adicionar itens**.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-211">On the Action Pane, select **Add items**.</span></span>
1. <span data-ttu-id="8a7cc-212">Na caixa de diálogo **Adicionar itens**, no campo **Hierarquia de categoria**, selecione uma categoria de nível superior.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-212">In the **Add items** dialog box, in the **Category hierarchy** field, select a top-level category.</span></span>
1. <span data-ttu-id="8a7cc-213">A hierarquia de itens é aberta no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-213">The item hierarchy is opened in the left pane.</span></span> <span data-ttu-id="8a7cc-214">Selecione o nível de hierarquia que você procura.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-214">Select the hierarchy level that you're looking for.</span></span> 
1. <span data-ttu-id="8a7cc-215">Os itens da hierarquia e do nível de hierarquia selecionados agora são listados no painel à direita.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-215">Items from the selected hierarchy and hierarchy level are now listed in the right pane.</span></span> <span data-ttu-id="8a7cc-216">Siga estas etapas para trabalhar com o painel:</span><span class="sxs-lookup"><span data-stu-id="8a7cc-216">Follow these steps to work with the pane:</span></span>

    - <span data-ttu-id="8a7cc-217">Marque a caixa de seleção de cada item a ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-217">Select the check box for each item that you want to add.</span></span>
    - <span data-ttu-id="8a7cc-218">Marque a caixa de seleção no cabeçalho da grade para selecionar todos os itens listados.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-218">Select the check box on the grid header to select all the items that are listed.</span></span>
    - <span data-ttu-id="8a7cc-219">Selecione o botão **Mostrar selecionado** para filtrar a grade de forma que ela mostre apenas os itens selecionados até o momento.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-219">Select the **Show selected** button to filter the grid so that it shows only the items that you've selected so far.</span></span> <span data-ttu-id="8a7cc-220">Selecione novamente o botão para retornar à lista completa.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-220">Select the button again to return to the full list.</span></span>

1. <span data-ttu-id="8a7cc-221">Selecione **OK** para aplicar a seleção de itens ao grupo selecionado.</span><span class="sxs-lookup"><span data-stu-id="8a7cc-221">Select **OK** to apply your item selection to the selected group.</span></span>