---
title: Configurar direitos de acesso para um controlador de objeto de custo
description: Use este procedimento para configurar direitos de acesso para um controlador de objeto de custo.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b7356706ea80c97fdf5b73faf32134a4aebacbb
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176420"
---
# <a name="configure-access-rights-for-a-cost-object-controller"></a><span data-ttu-id="44355-103">Configurar direitos de acesso para um controlador de objeto de custo</span><span class="sxs-lookup"><span data-stu-id="44355-103">Configure access rights for a cost object controller</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="44355-104">Use este procedimento para configurar direitos de acesso para um controlador de objeto de custo.</span><span class="sxs-lookup"><span data-stu-id="44355-104">Use this procedure to configure access rights for a cost object controller.</span></span> <span data-ttu-id="44355-105">Esta gravação usa os dados da empresa de demonstração USP2.</span><span class="sxs-lookup"><span data-stu-id="44355-105">This recording uses the USP2 demo data company.</span></span>


## <a name="assign-the-cost-object-controller-role"></a><span data-ttu-id="44355-106">Atribuir a função de controlador de objeto de custo</span><span class="sxs-lookup"><span data-stu-id="44355-106">Assign the cost object controller role</span></span>
1. <span data-ttu-id="44355-107">Vá para Administração do sistema > Usuários > Usuários.</span><span class="sxs-lookup"><span data-stu-id="44355-107">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="44355-108">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="44355-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="44355-109">Por exemplo, filtre no campo Nome de usuário um valor de "alicia".</span><span class="sxs-lookup"><span data-stu-id="44355-109">For example, filter on the User name field with a value of 'alicia'.</span></span>
3. <span data-ttu-id="44355-110">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="44355-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="44355-111">Clique em Atribuir funções.</span><span class="sxs-lookup"><span data-stu-id="44355-111">Click Assign roles.</span></span>
5. <span data-ttu-id="44355-112">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="44355-112">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="44355-113">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="44355-113">Click OK.</span></span>

## <a name="enable-access-list-security"></a><span data-ttu-id="44355-114">Habilitar segurança da lista de acesso</span><span class="sxs-lookup"><span data-stu-id="44355-114">Enable access list security</span></span>
1. <span data-ttu-id="44355-115">Vá para Contabilização de custos > Dimensões > Hierarquias de dimensões.</span><span class="sxs-lookup"><span data-stu-id="44355-115">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="44355-116">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="44355-116">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="44355-117">Selecione Organização.</span><span class="sxs-lookup"><span data-stu-id="44355-117">Select Organization.</span></span>  
3. <span data-ttu-id="44355-118">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="44355-118">Click Edit.</span></span>
4. <span data-ttu-id="44355-119">Selecione Sim no campo Acessar hierarquia de lista.</span><span class="sxs-lookup"><span data-stu-id="44355-119">Select Yes in the Access list hierarchy field.</span></span>
5. <span data-ttu-id="44355-120">Clique em Exibir hierarquia.</span><span class="sxs-lookup"><span data-stu-id="44355-120">Click View hierarchy.</span></span>

## <a name="assign-access-rights-to-user"></a><span data-ttu-id="44355-121">Atribuir direitos de acesso ao usuário</span><span class="sxs-lookup"><span data-stu-id="44355-121">Assign access rights to user</span></span>
1. <span data-ttu-id="44355-122">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="44355-122">Click New.</span></span>
2. <span data-ttu-id="44355-123">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="44355-123">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="44355-124">No campo ID do usuário, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="44355-124">In the User ID field, enter or select a value.</span></span>
    * <span data-ttu-id="44355-125">Selecione Administrador.</span><span class="sxs-lookup"><span data-stu-id="44355-125">Select Admin.</span></span>  
4. <span data-ttu-id="44355-126">Na árvore, selecione 'Organização\CEO\CFO\FIM'.</span><span class="sxs-lookup"><span data-stu-id="44355-126">In the tree, select 'Organization\CEO\CFO\FIM'.</span></span>
5. <span data-ttu-id="44355-127">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="44355-127">Click New.</span></span>
6. <span data-ttu-id="44355-128">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="44355-128">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="44355-129">No campo ID do usuário, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="44355-129">In the User ID field, enter or select a value.</span></span>
    * <span data-ttu-id="44355-130">Selecione Alicia.</span><span class="sxs-lookup"><span data-stu-id="44355-130">Select Alicia.</span></span>  
8. <span data-ttu-id="44355-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="44355-131">Click Save.</span></span>

## <a name="enable-access-rights-in-cost-accounting"></a><span data-ttu-id="44355-132">Habilitar direitos de acesso na Contabilização de custos</span><span class="sxs-lookup"><span data-stu-id="44355-132">Enable access rights in Cost accounting</span></span>
1. <span data-ttu-id="44355-133">Vá para Contabilização de custos > Configuração > Parâmetros.</span><span class="sxs-lookup"><span data-stu-id="44355-133">Go to Cost accounting > Setup > Parameters.</span></span>
2. <span data-ttu-id="44355-134">Clique na guia Geral.</span><span class="sxs-lookup"><span data-stu-id="44355-134">Click the General tab.</span></span>
3. <span data-ttu-id="44355-135">Selecione Sim no campo Habilitar acesso de visualização para membros de dimensão de objeto de custo.</span><span class="sxs-lookup"><span data-stu-id="44355-135">Select Yes in the Enable view access for cost object dimension members field.</span></span>
4. <span data-ttu-id="44355-136">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="44355-136">Click Save.</span></span>
5. <span data-ttu-id="44355-137">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="44355-137">Close the page.</span></span>
6. <span data-ttu-id="44355-138">Vá para Contabilização de custos > Configuração > Configuração de espaço de trabalho de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="44355-138">Go to Cost accounting > Setup > Cost control workspace configuration.</span></span>
7. <span data-ttu-id="44355-139">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="44355-139">Click Edit.</span></span>
8. <span data-ttu-id="44355-140">Selecione Sim no campo Publicado.</span><span class="sxs-lookup"><span data-stu-id="44355-140">Select Yes in the Published field.</span></span>
    * <span data-ttu-id="44355-141">Se selecionar Sim, um usuário atribuído a uma das quatro funções poderá consultar os relatórios no espaço de trabalho de controle de custo: gerente de contabilidade de custo, contador de custos, funcionário de contador de custo e controlador de objeto de custo.</span><span class="sxs-lookup"><span data-stu-id="44355-141">If you select Yes, a user who is assigned one of the following four roles can see the reports in the Cost control workspace: cost accounting manager, cost accountant, cost accountant clerk, and cost object controller.</span></span> <span data-ttu-id="44355-142">Se selecionar Não, somente um usuário atribuído a uma das quatro funções poderá consultar os relatórios: gerente de contabilidade de custo, contador de custos e funcionário do contador de custos.</span><span class="sxs-lookup"><span data-stu-id="44355-142">If you select No, only a user who is assigned one of the following roles can see the reports: cost accounting manager, cost accountant, and cost accountant clerk.</span></span>    
9. <span data-ttu-id="44355-143">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="44355-143">Click Save.</span></span>

