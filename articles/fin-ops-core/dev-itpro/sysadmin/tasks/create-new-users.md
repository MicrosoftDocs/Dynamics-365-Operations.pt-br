---
title: Criar novos usuários
description: Os usuários são funcionários internos da sua organização, ou clientes e fornecedores externos, que precisam de acesso ao sistema para realizar seus trabalhos.
author: maertenm
manager: AnnBe
ms.date: 02/06/2020
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
ms.openlocfilehash: 9db4b6d355d6499bce6c550b2fbe76b82cf69fd4
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143550"
---
# <a name="create-new-users"></a><span data-ttu-id="01c42-103">Criar novos usuários</span><span class="sxs-lookup"><span data-stu-id="01c42-103">Create new users</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="01c42-104">Os usuários são funcionários internos da sua organização ou clientes e fornecedores externos que precisam de acesso ao sistema para realizar seus trabalhos.</span><span class="sxs-lookup"><span data-stu-id="01c42-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to do their jobs.</span></span>

## <a name="associate-a-user-with-a-license-new-license-types-only"></a><span data-ttu-id="01c42-105">Associar um usuário a uma licença (somente novos tipos de licença)</span><span class="sxs-lookup"><span data-stu-id="01c42-105">Associate a user with a license (new license types only)</span></span>
<span data-ttu-id="01c42-106">Para os clientes que têm um dos novos tipos de licença adicionados em outubro de 2019, os usuários devem ser associados a uma licença.</span><span class="sxs-lookup"><span data-stu-id="01c42-106">For customers who are on one of the new license types that were added in October 2019, users must be associated with a license.</span></span> <span data-ttu-id="01c42-107">Os usuários associados a uma licença são adicionados automaticamente como usuários do sistema que não têm funções na primeira vez em que entram.</span><span class="sxs-lookup"><span data-stu-id="01c42-107">Users who are associated with a license are automatically added as system users who have no roles the first time that they sign in.</span></span>

<span data-ttu-id="01c42-108">Os administradores do sistema podem [atribuir licenças a usuários](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) no [Centro de administração do Microsoft 365](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="01c42-108">System admins can [assign licenses to users](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) in the [Microsoft 365 admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).</span></span>

## <a name="associate-an-external-user-with-a-license-new-license-types-only"></a><span data-ttu-id="01c42-109">Associar um usuário externo a uma licença (somente novos tipos de licença)</span><span class="sxs-lookup"><span data-stu-id="01c42-109">Associate an external user with a license (new license types only)</span></span>
<span data-ttu-id="01c42-110">Os usuários externos ao locatário em que o ambiente foi implantado precisam ser representados no diretório de locatários host (Azure Active Directory (Azure AD)) para que possam receber licenças.</span><span class="sxs-lookup"><span data-stu-id="01c42-110">Users external to the tenant that the environment was deployed into need to be represented in the host tenant directory (Azure Active Directory (Azure AD)) so that they can be assigned licenses.</span></span> <span data-ttu-id="01c42-111">Esses usuários externos devem ser adicionados ao locatário no Azure AD como usuários convidados para depois poderem receber as licenças apropriadas.</span><span class="sxs-lookup"><span data-stu-id="01c42-111">Those external users should be added to the tenant in Azure AD as guest users and then assigned the appropriate licenses.</span></span> <span data-ttu-id="01c42-112">Para obter mais informações, consulte [Adicionar usuários de colaboração B2B do Azure Active Directory no portal do Azure](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="01c42-112">For more information, see [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="01c42-113">Adicionar um novo usuário</span><span class="sxs-lookup"><span data-stu-id="01c42-113">Add a new user</span></span>
1. <span data-ttu-id="01c42-114">Vá para **Administração do sistema \> Usuários \> Usuários**.</span><span class="sxs-lookup"><span data-stu-id="01c42-114">Go to **System administration \> Users \> Users**.</span></span>
2. <span data-ttu-id="01c42-115">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="01c42-115">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="01c42-116">No campo **ID do usuário**, insira um identificador exclusivo para o usuário.</span><span class="sxs-lookup"><span data-stu-id="01c42-116">In the **User ID** field, enter a unique identifier for the user.</span></span> <span data-ttu-id="01c42-117">Um ID de usuário é necessário.</span><span class="sxs-lookup"><span data-stu-id="01c42-117">A user ID is required.</span></span>  
4. <span data-ttu-id="01c42-118">No campo **Nome do usuário**, insira o nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="01c42-118">In the **User name** field, enter the user's name.</span></span>  
5. <span data-ttu-id="01c42-119">No campo **Domínio**, insira o domínio do usuário.</span><span class="sxs-lookup"><span data-stu-id="01c42-119">In the **Domain** field, enter the user's domain.</span></span>  
6. <span data-ttu-id="01c42-120">No campo **Alias** , insira o apelido do usuário.</span><span class="sxs-lookup"><span data-stu-id="01c42-120">In the **Alias** field, enter the user's alias.</span></span>  
7. <span data-ttu-id="01c42-121">No campo **Empresa**, selecione a empresa desejada.</span><span class="sxs-lookup"><span data-stu-id="01c42-121">In the **Company** field, select the desired company.</span></span> 
8. <span data-ttu-id="01c42-122">Na FastTab **Funções do usuário**, selecione **Atribuir funções** para atribuir usuários a funções de segurança.</span><span class="sxs-lookup"><span data-stu-id="01c42-122">On the **User's roles** FastTab, select **Assign roles** to assign users to security roles.</span></span> <span data-ttu-id="01c42-123">Para obter mais informações, consulte [Atribuir usuários a funções de segurança](assign-users-security-roles.md).</span><span class="sxs-lookup"><span data-stu-id="01c42-123">For more information, see [Assign users to security roles](assign-users-security-roles.md).</span></span>
9. <span data-ttu-id="01c42-124">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="01c42-124">Select **OK**.</span></span>
10. <span data-ttu-id="01c42-125">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="01c42-125">Select **Save**.</span></span>

## <a name="import-users"></a><span data-ttu-id="01c42-126">Importar usuários</span><span class="sxs-lookup"><span data-stu-id="01c42-126">Import users</span></span>
1. <span data-ttu-id="01c42-127">No Painel de Ação, selecione **Importar usuários**.</span><span class="sxs-lookup"><span data-stu-id="01c42-127">On the Action Pane, select **Import users**.</span></span>
2. <span data-ttu-id="01c42-128">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="01c42-128">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="01c42-129">Selecione **Importar usuários**.</span><span class="sxs-lookup"><span data-stu-id="01c42-129">Select **Import users**.</span></span>
4. <span data-ttu-id="01c42-130">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="01c42-130">Select **Close**.</span></span>

