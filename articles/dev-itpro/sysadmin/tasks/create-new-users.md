---
title: Criar novos usuários
description: Os usuários são funcionários internos da sua organização, ou clientes e fornecedores externos, que precisam de acesso ao sistema para realizar seus trabalhos.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: 89e492ef5030dd28020094152259b615010aa676
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1851302"
---
# <a name="create-new-users"></a><span data-ttu-id="942f3-103">Criar novos usuários</span><span class="sxs-lookup"><span data-stu-id="942f3-103">Create new users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="942f3-104">Os usuários são funcionários internos da sua organização, ou clientes e fornecedores externos, que precisam de acesso ao sistema para realizar seus trabalhos.</span><span class="sxs-lookup"><span data-stu-id="942f3-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to perform their jobs.</span></span> <span data-ttu-id="942f3-105">Os administradores do sistema podem realizar esse procedimento para adicionar usuários ao sistema.</span><span class="sxs-lookup"><span data-stu-id="942f3-105">System administrators can complete this procedure to add users to the system.</span></span> <span data-ttu-id="942f3-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="942f3-106">The demo data company used to create this procedure is USMF.</span></span> 


## <a name="add-a-new-user"></a><span data-ttu-id="942f3-107">Adicionar um novo usuário</span><span class="sxs-lookup"><span data-stu-id="942f3-107">Add a new user</span></span>
1. <span data-ttu-id="942f3-108">Vá para Administração do sistema > Usuários > Usuários.</span><span class="sxs-lookup"><span data-stu-id="942f3-108">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="942f3-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="942f3-109">Click New.</span></span>
3. <span data-ttu-id="942f3-110">No campo ID de usuário, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="942f3-110">In the User ID field, type a value.</span></span>
    * <span data-ttu-id="942f3-111">Insira um identificador exclusivo para o usuário.</span><span class="sxs-lookup"><span data-stu-id="942f3-111">Enter a unique identifier for the user.</span></span> <span data-ttu-id="942f3-112">Um ID de usuário é necessário.</span><span class="sxs-lookup"><span data-stu-id="942f3-112">A user ID is required.</span></span>  
4. <span data-ttu-id="942f3-113">No campo Nome de usuário, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="942f3-113">In the User name field, type a value.</span></span>
    * <span data-ttu-id="942f3-114">Insira o nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="942f3-114">Enter the user's name.</span></span>  
5. <span data-ttu-id="942f3-115">No campo Domínio, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="942f3-115">In the Domain field, type a value.</span></span>
    * <span data-ttu-id="942f3-116">Insira o domínio do usuário.</span><span class="sxs-lookup"><span data-stu-id="942f3-116">Enter the user's domain.</span></span>  
6. <span data-ttu-id="942f3-117">No campo Alias, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="942f3-117">In the Alias field, type a value.</span></span>
    * <span data-ttu-id="942f3-118">Insira o alias do usuário.</span><span class="sxs-lookup"><span data-stu-id="942f3-118">Enter the user's alias.</span></span>  
7. <span data-ttu-id="942f3-119">No campo Empresa, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="942f3-119">In the Company field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="942f3-120">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="942f3-120">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="942f3-121">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="942f3-121">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="942f3-122">Selecione a empresa do usuário</span><span class="sxs-lookup"><span data-stu-id="942f3-122">Select the user's company</span></span>  
10. <span data-ttu-id="942f3-123">Clique em Atribuir funções.</span><span class="sxs-lookup"><span data-stu-id="942f3-123">Click Assign roles.</span></span>
11. <span data-ttu-id="942f3-124">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="942f3-124">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="942f3-125">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="942f3-125">Click OK.</span></span>
13. <span data-ttu-id="942f3-126">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="942f3-126">Click Save.</span></span>

## <a name="import-users"></a><span data-ttu-id="942f3-127">Importar usuários</span><span class="sxs-lookup"><span data-stu-id="942f3-127">Import users</span></span>
1. <span data-ttu-id="942f3-128">Clique em Importar usuários.</span><span class="sxs-lookup"><span data-stu-id="942f3-128">Click Import users.</span></span>
2. <span data-ttu-id="942f3-129">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="942f3-129">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="942f3-130">Clique em Importar usuários.</span><span class="sxs-lookup"><span data-stu-id="942f3-130">Click Import users.</span></span>
4. <span data-ttu-id="942f3-131">Clique em Fechar.</span><span class="sxs-lookup"><span data-stu-id="942f3-131">Click Close.</span></span>

