---
title: Atribuir usuários a funções de segurança
description: Para acessar os aplicativos Finance and Operations, os usuários devem ser atribuídos a funções de segurança.
author: ChrisGarty
manager: AnnBe
ms.date: 09/16/2019
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
ms.openlocfilehash: a4daecc1acd589cd1656402244e5325382a407e7
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180958"
---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="bec01-103">Atribuir usuários a funções de segurança</span><span class="sxs-lookup"><span data-stu-id="bec01-103">Assign users to security roles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bec01-104">Para usar qualquer coisa além das funcionalidades comuns, os usuários devem ser atribuídos a funções de segurança.</span><span class="sxs-lookup"><span data-stu-id="bec01-104">To use anything other than common capabilities, users must be assigned to security roles.</span></span> <span data-ttu-id="bec01-105">Este procedimento explica como os administradores do sistema podem atribuir usuários a funções automaticamente com base em dados corporativos.</span><span class="sxs-lookup"><span data-stu-id="bec01-105">This procedure explains how system administrators can automatically assign users to roles, based on business data.</span></span> 

## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="bec01-106">Atribuir automaticamente usuários às funções</span><span class="sxs-lookup"><span data-stu-id="bec01-106">Automatically assign users to roles</span></span>
1. <span data-ttu-id="bec01-107">Vá para **Painel de navegação > Módulos > Administração do sistema > Segurança > Atribuir usuários a funções**.</span><span class="sxs-lookup"><span data-stu-id="bec01-107">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
2. <span data-ttu-id="bec01-108">Na árvore, selecione "Supervisor de contabilidade".</span><span class="sxs-lookup"><span data-stu-id="bec01-108">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="bec01-109">Selecione a função para a qual deseja configurar a regra.</span><span class="sxs-lookup"><span data-stu-id="bec01-109">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="bec01-110">Neste exemplo, selecione Supervisor de contabilidade.</span><span class="sxs-lookup"><span data-stu-id="bec01-110">In this example, select Accounting supervisor.</span></span> 
3. <span data-ttu-id="bec01-111">Clique em **Adicionar regra** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="bec01-111">Click **Add rule** to open the drop dialog.</span></span>
4. <span data-ttu-id="bec01-112">Na lista **Selecionar uma consulta**, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="bec01-112">In the **Select a query**list, find and select the desired record.</span></span> <span data-ttu-id="bec01-113">Selecione a consulta a ser usada para esta regra.</span><span class="sxs-lookup"><span data-stu-id="bec01-113">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="bec01-114">Na lista **Nome da regra de associação**, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="bec01-114">In the **Membership rule name** list, click the link in the selected row.</span></span>
6. <span data-ttu-id="bec01-115">Clique em **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="bec01-115">Click **Edit query**.</span></span> <span data-ttu-id="bec01-116">Edite a consulta, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="bec01-116">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="bec01-117">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bec01-117">Click **OK**.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="bec01-118">Excluir usuários de atribuição de função automática</span><span class="sxs-lookup"><span data-stu-id="bec01-118">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="bec01-119">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="bec01-119">Close the page.</span></span>
2. <span data-ttu-id="bec01-120">Vá para **Painel de navegação > Módulos > Administração do sistema > Segurança > Atribuir usuários a funções**.</span><span class="sxs-lookup"><span data-stu-id="bec01-120">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
3. <span data-ttu-id="bec01-121">Na árvore, selecione "Supervisor de contabilidade".</span><span class="sxs-lookup"><span data-stu-id="bec01-121">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="bec01-122">Selecione uma função.</span><span class="sxs-lookup"><span data-stu-id="bec01-122">Select a role.</span></span> <span data-ttu-id="bec01-123">Para este exemplo, selecione Supervisor de contabilidade.</span><span class="sxs-lookup"><span data-stu-id="bec01-123">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="bec01-124">No menu **Usuários atribuídos à função**, selecione **Atribuir/excluir usuários manualmente**.</span><span class="sxs-lookup"><span data-stu-id="bec01-124">In the **Users assigned to role** menu, select **Manually assign / exclude users**.</span></span>
5. <span data-ttu-id="bec01-125">Na lista **Atribuir usuários ou excluir usuários da função**, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="bec01-125">In the **Assign users to or exclude users from role** list, mark the selected row.</span></span> <span data-ttu-id="bec01-126">Selecione um usuário.</span><span class="sxs-lookup"><span data-stu-id="bec01-126">Select a user.</span></span>  
6. <span data-ttu-id="bec01-127">No **Painel de ação**, selecione **Excluir da função**.</span><span class="sxs-lookup"><span data-stu-id="bec01-127">On the **Action pane**, select **Exclude from role**.</span></span>
    
    <span data-ttu-id="bec01-128">Clique em **Excluir da função** para excluir os usuários selecionados da função.</span><span class="sxs-lookup"><span data-stu-id="bec01-128">Click **Exclude from role** to exclude the selected users from the role.</span></span> <span data-ttu-id="bec01-129">Para remover as exclusões, selecione os usuários que você deseja remover e clique em **Redefinir status**.</span><span class="sxs-lookup"><span data-stu-id="bec01-129">To remove exclusions, select the users that you want to remove exclusions for, and then click **Reset status**.</span></span> <span data-ttu-id="bec01-130">Quando você remover uma exclusão redefinindo o status do usuário, a função do usuário será atribuída automaticamente novamente.</span><span class="sxs-lookup"><span data-stu-id="bec01-130">When you remove an exclusion by resetting the user’s status, the user’s role is again assigned automatically.</span></span> <span data-ttu-id="bec01-131">No entanto, o usuário não está atribuído à função imediatamente ou não será excluído da função quando você redefinir o status.</span><span class="sxs-lookup"><span data-stu-id="bec01-131">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="bec01-132">Em vez disso, o usuário é atribuído à função ou removido da função da próxima vez que as regras para a atribuição de função automática são executadas.</span><span class="sxs-lookup"><span data-stu-id="bec01-132">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  
