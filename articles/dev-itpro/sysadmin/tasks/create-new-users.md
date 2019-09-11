---
title: Criar novos usuários
description: Os usuários são funcionários internos da sua organização, ou clientes e fornecedores externos, que precisam de acesso ao sistema para realizar seus trabalhos.
author: maertenm
manager: AnnBe
ms.date: 07/01/2019
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
ms.openlocfilehash: a542ece226750330262e0c44427e5654fa4f6369
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916475"
---
# <a name="create-new-users"></a><span data-ttu-id="04b02-103">Criar novos usuários</span><span class="sxs-lookup"><span data-stu-id="04b02-103">Create new users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="04b02-104">Os usuários são funcionários internos da sua organização, ou clientes e fornecedores externos, que precisam de acesso ao sistema para realizar seus trabalhos.</span><span class="sxs-lookup"><span data-stu-id="04b02-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to perform their jobs.</span></span> <span data-ttu-id="04b02-105">Os administradores do sistema podem realizar esse procedimento para adicionar usuários ao sistema.</span><span class="sxs-lookup"><span data-stu-id="04b02-105">System administrators can complete this procedure to add users to the system.</span></span> <span data-ttu-id="04b02-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="04b02-106">The demo data company used to create this procedure is USMF.</span></span> 


## <a name="add-a-new-user"></a><span data-ttu-id="04b02-107">Adicionar um novo usuário</span><span class="sxs-lookup"><span data-stu-id="04b02-107">Add a new user</span></span>
1. <span data-ttu-id="04b02-108">Vá para **Painel de navegação > Módulos > Administração do sistema > Usuários > Usuários**.</span><span class="sxs-lookup"><span data-stu-id="04b02-108">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="04b02-109">No **Painel de Ações**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="04b02-109">On the **Action pane**, click **New**.</span></span>
3. <span data-ttu-id="04b02-110">No campo **ID de usuário**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="04b02-110">In the **User ID** field, type a value.</span></span> <span data-ttu-id="04b02-111">Insira um identificador exclusivo para o usuário.</span><span class="sxs-lookup"><span data-stu-id="04b02-111">Enter a unique identifier for the user.</span></span> <span data-ttu-id="04b02-112">Um ID de usuário é necessário.</span><span class="sxs-lookup"><span data-stu-id="04b02-112">A user ID is required.</span></span>  
4. <span data-ttu-id="04b02-113">No campo **Nome de usuário**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="04b02-113">In the **User name** field, type a value.</span></span> <span data-ttu-id="04b02-114">Insira o nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="04b02-114">Enter the user's name.</span></span>  
5. <span data-ttu-id="04b02-115">No campo **Domínio**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="04b02-115">In the **Domain** field, type a value.</span></span> <span data-ttu-id="04b02-116">Insira o domínio do usuário.</span><span class="sxs-lookup"><span data-stu-id="04b02-116">Enter the user's domain.</span></span>  
6. <span data-ttu-id="04b02-117">No campo **Alias**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="04b02-117">In the **Alias** field, type a value.</span></span> <span data-ttu-id="04b02-118">Insira o alias do usuário.</span><span class="sxs-lookup"><span data-stu-id="04b02-118">Enter the user's alias.</span></span>  
7. <span data-ttu-id="04b02-119">No campo **Empresa**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="04b02-119">In the **Company** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="04b02-120">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="04b02-120">In the list, find and select the desired record.</span></span> 
9. <span data-ttu-id="04b02-121">Na seção **Funções do usuário**, clique em **Atribuir funções**.</span><span class="sxs-lookup"><span data-stu-id="04b02-121">In the **User's roles** section, click **Assign roles**.</span></span>
10. <span data-ttu-id="04b02-122">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="04b02-122">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="04b02-123">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="04b02-123">Click **OK**.</span></span>
12. <span data-ttu-id="04b02-124">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="04b02-124">Click **Save**.</span></span>

## <a name="import-users"></a><span data-ttu-id="04b02-125">Importar usuários</span><span class="sxs-lookup"><span data-stu-id="04b02-125">Import users</span></span>
1. <span data-ttu-id="04b02-126">No **Painel de Ações**, clique em **Importar usuários**.</span><span class="sxs-lookup"><span data-stu-id="04b02-126">On the **Action pane**, click **Import users**.</span></span>
2. <span data-ttu-id="04b02-127">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="04b02-127">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="04b02-128">Clique em **Importar usuários**.</span><span class="sxs-lookup"><span data-stu-id="04b02-128">Click **Import users**.</span></span>
4. <span data-ttu-id="04b02-129">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="04b02-129">Click **Close**.</span></span>

