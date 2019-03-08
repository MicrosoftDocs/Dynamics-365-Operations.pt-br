---
title: Atribuir usuários a funções de segurança
description: Para acessar o Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, os usuários devem ser atribuídos às funções de segurança.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 55cb085bb5170aa4894a2240a12f6ca451b922fb
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "349943"
---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="31e57-103">Atribuir usuários a funções de segurança</span><span class="sxs-lookup"><span data-stu-id="31e57-103">Assign users to security roles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="31e57-104">Para acessar o Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, os usuários devem ser atribuídos às funções de segurança.</span><span class="sxs-lookup"><span data-stu-id="31e57-104">To access Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, users must be assigned to security roles.</span></span> <span data-ttu-id="31e57-105">Este processo explica como os administradores de sistemas podem atribuir usuários às funções automaticamente, com base nos dados comerciais.</span><span class="sxs-lookup"><span data-stu-id="31e57-105">This procedure explains how system administrators can assign users to roles automatically, based on business data.</span></span> <span data-ttu-id="31e57-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="31e57-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="31e57-107">Atribuir automaticamente usuários às funções</span><span class="sxs-lookup"><span data-stu-id="31e57-107">Automatically assign users to roles</span></span>
1. <span data-ttu-id="31e57-108">Vá para Administração do sistema > Segurança > Atribuir usuários a funções.</span><span class="sxs-lookup"><span data-stu-id="31e57-108">Go to System administration > Security > Assign users to roles.</span></span>
2. <span data-ttu-id="31e57-109">Na árvore, selecione "Supervisor de contabilidade".</span><span class="sxs-lookup"><span data-stu-id="31e57-109">In the tree, select 'Accounting supervisor'.</span></span>
    * <span data-ttu-id="31e57-110">Selecione a função para a qual deseja configurar a regra.</span><span class="sxs-lookup"><span data-stu-id="31e57-110">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="31e57-111">Neste exemplo, selecione Supervisor de contabilidade.</span><span class="sxs-lookup"><span data-stu-id="31e57-111">In this example, select Accounting supervisor.</span></span>  
3. <span data-ttu-id="31e57-112">Clique em Adicionar regras para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="31e57-112">Click Add rule to open the drop dialog.</span></span>
4. <span data-ttu-id="31e57-113">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="31e57-113">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="31e57-114">Selecione a consulta a ser usada para esta regra.</span><span class="sxs-lookup"><span data-stu-id="31e57-114">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="31e57-115">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="31e57-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="31e57-116">Clique em Editar consulta.</span><span class="sxs-lookup"><span data-stu-id="31e57-116">Click Edit query.</span></span>
    * <span data-ttu-id="31e57-117">Edite a consulta, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="31e57-117">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="31e57-118">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="31e57-118">Click OK.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="31e57-119">Excluir usuários de atribuição de função automática</span><span class="sxs-lookup"><span data-stu-id="31e57-119">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="31e57-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="31e57-120">Close the page.</span></span>
2. <span data-ttu-id="31e57-121">Vá para Administração do sistema > Segurança > Atribuir usuários a funções.</span><span class="sxs-lookup"><span data-stu-id="31e57-121">Go to System administration > Security > Assign users to roles.</span></span>
3. <span data-ttu-id="31e57-122">Na árvore, selecione "Supervisor de contabilidade".</span><span class="sxs-lookup"><span data-stu-id="31e57-122">In the tree, select 'Accounting supervisor'.</span></span>
    * <span data-ttu-id="31e57-123">Selecione uma função.</span><span class="sxs-lookup"><span data-stu-id="31e57-123">Select a role.</span></span> <span data-ttu-id="31e57-124">Para este exemplo, selecione Supervisor de contabilidade.</span><span class="sxs-lookup"><span data-stu-id="31e57-124">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="31e57-125">Clique em Atribuir/excluir usuários manualmente.</span><span class="sxs-lookup"><span data-stu-id="31e57-125">Click Manually assign / exclude users.</span></span>
5. <span data-ttu-id="31e57-126">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="31e57-126">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="31e57-127">Selecione um usuário.</span><span class="sxs-lookup"><span data-stu-id="31e57-127">Select a user.</span></span>  
6. <span data-ttu-id="31e57-128">Clique em Excluir da função.</span><span class="sxs-lookup"><span data-stu-id="31e57-128">Click Exclude from role.</span></span>
    * <span data-ttu-id="31e57-129">Clique em Excluir da função para excluir os usuários selecionados da função.</span><span class="sxs-lookup"><span data-stu-id="31e57-129">Click Exclude from role to exclude the selected users from the role.</span></span> <span data-ttu-id="31e57-130">Para remover as exclusões, selecione os usuários que você deseja remover, e clique em Redefinir status.</span><span class="sxs-lookup"><span data-stu-id="31e57-130">To remove exclusions, select the users that you want to remove exclusions for, and then click Reset status.</span></span> <span data-ttu-id="31e57-131">Quando você remover uma exclusão redefinindo o status do usuário, a função do usuário será atribuída automaticamente novamente.</span><span class="sxs-lookup"><span data-stu-id="31e57-131">When you remove an exclusion by resetting the user’s status, the user’s role is again assigned automatically.</span></span> <span data-ttu-id="31e57-132">No entanto, o usuário não está atribuído à função imediatamente ou não será excluído da função quando você redefinir o status.</span><span class="sxs-lookup"><span data-stu-id="31e57-132">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="31e57-133">Em vez disso, o usuário é atribuído à função ou removido da função da próxima vez que as regras para a atribuição de função automática são executadas.</span><span class="sxs-lookup"><span data-stu-id="31e57-133">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  

