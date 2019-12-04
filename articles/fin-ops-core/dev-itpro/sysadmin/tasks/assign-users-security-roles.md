---
title: Atribuir usuários a funções de segurança
description: Para acessar os aplicativos Finance and Operations, os usuários devem ser atribuídos a funções de segurança.
author: ChrisGarty
manager: AnnBe
ms.date: 11/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e4f4ef4535de9e371829c2d86d4fdc1400510c7b
ms.sourcegitcommit: 6aa74f66f1abd3a7977050a5339b0b17e62ff053
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "2807987"
---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="85fb7-103">Atribuir usuários a funções de segurança</span><span class="sxs-lookup"><span data-stu-id="85fb7-103">Assign users to security roles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="85fb7-104">Para usar qualquer coisa além das funcionalidades comuns, os usuários devem ser atribuídos a funções de segurança.</span><span class="sxs-lookup"><span data-stu-id="85fb7-104">To use anything other than common capabilities, users must be assigned to security roles.</span></span> <span data-ttu-id="85fb7-105">Este procedimento explica como os administradores do sistema podem atribuir usuários a funções automaticamente com base em dados corporativos.</span><span class="sxs-lookup"><span data-stu-id="85fb7-105">This procedure explains how system administrators can automatically assign users to roles, based on business data.</span></span> 

## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="85fb7-106">Atribuir automaticamente usuários às funções</span><span class="sxs-lookup"><span data-stu-id="85fb7-106">Automatically assign users to roles</span></span>
1. <span data-ttu-id="85fb7-107">Vá para **Painel de navegação > Módulos > Administração do sistema > Segurança > Atribuir usuários a funções**.</span><span class="sxs-lookup"><span data-stu-id="85fb7-107">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
2. <span data-ttu-id="85fb7-108">Na árvore, selecione "Supervisor de contabilidade".</span><span class="sxs-lookup"><span data-stu-id="85fb7-108">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="85fb7-109">Selecione a função para a qual deseja configurar a regra.</span><span class="sxs-lookup"><span data-stu-id="85fb7-109">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="85fb7-110">Neste exemplo, selecione Supervisor de contabilidade.</span><span class="sxs-lookup"><span data-stu-id="85fb7-110">In this example, select Accounting supervisor.</span></span> 
3. <span data-ttu-id="85fb7-111">Clique em **Adicionar regra** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="85fb7-111">Click **Add rule** to open the drop dialog.</span></span>
4. <span data-ttu-id="85fb7-112">Na lista **Selecionar uma consulta**, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="85fb7-112">In the **Select a query**list, find and select the desired record.</span></span> <span data-ttu-id="85fb7-113">Selecione a consulta a ser usada para esta regra.</span><span class="sxs-lookup"><span data-stu-id="85fb7-113">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="85fb7-114">Na lista **Nome da regra de associação**, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="85fb7-114">In the **Membership rule name** list, click the link in the selected row.</span></span>
6. <span data-ttu-id="85fb7-115">Clique em **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="85fb7-115">Click **Edit query**.</span></span> <span data-ttu-id="85fb7-116">Edite a consulta, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="85fb7-116">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="85fb7-117">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="85fb7-117">Click **OK**.</span></span>
8. <span data-ttu-id="85fb7-118">Clique em **Executar atribuição de função automática**.</span><span class="sxs-lookup"><span data-stu-id="85fb7-118">Click **Run automatic role assignment**.</span></span>
9. <span data-ttu-id="85fb7-119">Vá para **Painel de navegação > Módulos > Administração do sistema > Usuários > Usuários** (de preferência em outra guia do navegador).</span><span class="sxs-lookup"><span data-stu-id="85fb7-119">Go to **Navigation pane > Modules > System administration > Users > Users** (ideally in a separate browser tab).</span></span>
10. <span data-ttu-id="85fb7-120">Examine as funções atribuídas para vários usuários para confirmar que a consulta de atribuição de função está correta.</span><span class="sxs-lookup"><span data-stu-id="85fb7-120">Review the roles assigned to various users to confirm that the role assignment query was correct.</span></span> <span data-ttu-id="85fb7-121">Faça os ajustes e execute novamente, se necessário.</span><span class="sxs-lookup"><span data-stu-id="85fb7-121">Adjust and re-run if needed.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="85fb7-122">Excluir usuários de atribuição de função automática</span><span class="sxs-lookup"><span data-stu-id="85fb7-122">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="85fb7-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="85fb7-123">Close the page.</span></span>
2. <span data-ttu-id="85fb7-124">Vá para **Painel de navegação > Módulos > Administração do sistema > Segurança > Atribuir usuários a funções**.</span><span class="sxs-lookup"><span data-stu-id="85fb7-124">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
3. <span data-ttu-id="85fb7-125">Na árvore, selecione "Supervisor de contabilidade".</span><span class="sxs-lookup"><span data-stu-id="85fb7-125">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="85fb7-126">Selecione uma função.</span><span class="sxs-lookup"><span data-stu-id="85fb7-126">Select a role.</span></span> <span data-ttu-id="85fb7-127">Para este exemplo, selecione Supervisor de contabilidade.</span><span class="sxs-lookup"><span data-stu-id="85fb7-127">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="85fb7-128">No menu **Usuários atribuídos à função**, selecione **Atribuir/excluir usuários manualmente**.</span><span class="sxs-lookup"><span data-stu-id="85fb7-128">In the **Users assigned to role** menu, select **Manually assign / exclude users**.</span></span>
5. <span data-ttu-id="85fb7-129">Na lista **Atribuir usuários ou excluir usuários da função**, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="85fb7-129">In the **Assign users to or exclude users from role** list, mark the selected row.</span></span> <span data-ttu-id="85fb7-130">Selecione um usuário.</span><span class="sxs-lookup"><span data-stu-id="85fb7-130">Select a user.</span></span>  
6. <span data-ttu-id="85fb7-131">No **Painel de ação**, selecione **Excluir da função**.</span><span class="sxs-lookup"><span data-stu-id="85fb7-131">On the **Action pane**, select **Exclude from role**.</span></span>
    
    <span data-ttu-id="85fb7-132">Clique em **Excluir da função** para excluir os usuários selecionados da função.</span><span class="sxs-lookup"><span data-stu-id="85fb7-132">Click **Exclude from role** to exclude the selected users from the role.</span></span> <span data-ttu-id="85fb7-133">Para remover as exclusões, selecione os usuários que você deseja remover e clique em **Redefinir status**.</span><span class="sxs-lookup"><span data-stu-id="85fb7-133">To remove exclusions, select the users that you want to remove exclusions for, and then click **Reset status**.</span></span> <span data-ttu-id="85fb7-134">Quando você remover uma exclusão redefinindo o status do usuário, a função do usuário será atribuída automaticamente novamente.</span><span class="sxs-lookup"><span data-stu-id="85fb7-134">When you remove an exclusion by resetting the user’s status, the user’s role is again assigned automatically.</span></span> <span data-ttu-id="85fb7-135">No entanto, o usuário não está atribuído à função imediatamente ou não será excluído da função quando você redefinir o status.</span><span class="sxs-lookup"><span data-stu-id="85fb7-135">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="85fb7-136">Em vez disso, o usuário é atribuído à função ou removido da função da próxima vez que as regras para a atribuição de função automática são executadas.</span><span class="sxs-lookup"><span data-stu-id="85fb7-136">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  
