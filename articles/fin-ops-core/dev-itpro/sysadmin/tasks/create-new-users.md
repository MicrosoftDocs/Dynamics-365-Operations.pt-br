---
title: Criar novos usuários
description: Os usuários são funcionários internos da sua organização, ou clientes e fornecedores externos, que precisam de acesso ao sistema para realizar seus trabalhos.
author: maertenm
manager: AnnBe
ms.date: 10/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3c347a34a389c32d005cc8086c4a1349ecb8a698
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570512"
---
# <a name="create-new-users"></a><span data-ttu-id="dfa48-103">Criar novos usuários</span><span class="sxs-lookup"><span data-stu-id="dfa48-103">Create new users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dfa48-104">Os usuários são funcionários internos da sua organização ou clientes e fornecedores externos que precisam de acesso ao sistema para realizar seus trabalhos.</span><span class="sxs-lookup"><span data-stu-id="dfa48-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to do their jobs.</span></span>

## <a name="associate-a-user-with-a-license-new-license-types-only"></a><span data-ttu-id="dfa48-105">Associar um usuário a uma licença (somente novos tipos de licença)</span><span class="sxs-lookup"><span data-stu-id="dfa48-105">Associate a user with a license (new license types only)</span></span>
<span data-ttu-id="dfa48-106">Para os clientes que têm um dos novos tipos de licença adicionados em outubro de 2019, os usuários devem ser associados a uma licença.</span><span class="sxs-lookup"><span data-stu-id="dfa48-106">For customers who are on one of the new license types that were added in October 2019, users must be associated with a license.</span></span> <span data-ttu-id="dfa48-107">Os usuários associados a uma licença são adicionados automaticamente como usuários do sistema que não têm funções na primeira vez em que entram.</span><span class="sxs-lookup"><span data-stu-id="dfa48-107">Users who are associated with a license are automatically added as system users who have no roles the first time that they sign in.</span></span> <span data-ttu-id="dfa48-108">Os usuários que não estão associados a uma licença recebem uma mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="dfa48-108">Users who aren't associated with a licence receive a warning message.</span></span>

<span data-ttu-id="dfa48-109">Os administradores do sistema podem [atribuir licenças a usuários](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) no [Centro de administração do Microsoft 365](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="dfa48-109">System admins can [assign licenses to users](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) in the [Microsoft 365 admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="dfa48-110">Adicionar um novo usuário</span><span class="sxs-lookup"><span data-stu-id="dfa48-110">Add a new user</span></span>
1. <span data-ttu-id="dfa48-111">Vá para **Administração do sistema \> Usuários \> Usuários**.</span><span class="sxs-lookup"><span data-stu-id="dfa48-111">Go to **System administration \> Users \> Users**.</span></span>
2. <span data-ttu-id="dfa48-112">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="dfa48-112">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="dfa48-113">No campo **ID do usuário**, insira um identificador exclusivo para o usuário.</span><span class="sxs-lookup"><span data-stu-id="dfa48-113">In the **User ID** field, enter a unique identifier for the user.</span></span> <span data-ttu-id="dfa48-114">Um ID de usuário é necessário.</span><span class="sxs-lookup"><span data-stu-id="dfa48-114">A user ID is required.</span></span>  
4. <span data-ttu-id="dfa48-115">No campo **Nome do usuário**, insira o nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="dfa48-115">In the **User name** field, enter the user's name.</span></span>  
5. <span data-ttu-id="dfa48-116">No campo **Domínio**, insira o domínio do usuário.</span><span class="sxs-lookup"><span data-stu-id="dfa48-116">In the **Domain** field, enter the user's domain.</span></span>  
6. <span data-ttu-id="dfa48-117">No campo **Alias** , insira o apelido do usuário.</span><span class="sxs-lookup"><span data-stu-id="dfa48-117">In the **Alias** field, enter the user's alias.</span></span>  
7. <span data-ttu-id="dfa48-118">No campo **Empresa**, selecione a empresa desejada.</span><span class="sxs-lookup"><span data-stu-id="dfa48-118">In the **Company** field, select the desired company.</span></span> 
8. <span data-ttu-id="dfa48-119">Na Guia Rápida **Funções do usuário**, selecione **Atribuir funções** para [atribuir usuários a funções de segurança](assign-users-security-roles.md)</span><span class="sxs-lookup"><span data-stu-id="dfa48-119">On the **User's roles** FastTab, select **Assign roles** to [assign users to security roles](assign-users-security-roles.md)</span></span>
9. <span data-ttu-id="dfa48-120">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="dfa48-120">Select **OK**.</span></span>
10. <span data-ttu-id="dfa48-121">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="dfa48-121">Select **Save**.</span></span>

## <a name="import-users"></a><span data-ttu-id="dfa48-122">Importar usuários</span><span class="sxs-lookup"><span data-stu-id="dfa48-122">Import users</span></span>
1. <span data-ttu-id="dfa48-123">No Painel de Ação, selecione **Importar usuários**.</span><span class="sxs-lookup"><span data-stu-id="dfa48-123">On the Action Pane, select **Import users**.</span></span>
2. <span data-ttu-id="dfa48-124">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="dfa48-124">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="dfa48-125">Selecione **Importar usuários**.</span><span class="sxs-lookup"><span data-stu-id="dfa48-125">Select **Import users**.</span></span>
4. <span data-ttu-id="dfa48-126">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="dfa48-126">Select **Close**.</span></span>

