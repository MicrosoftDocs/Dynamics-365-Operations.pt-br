---
title: Delegar itens de trabalho em um fluxo de trabalho
description: Se você planeja se ausentar do escritório ou ficar indisponível para executar ações em itens de trabalho, poderá delegar ou reatribuir seus itens de trabalho a outros usuários.
author: ChrisGarty
ms.date: 07/07/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ed21f6d32cdcf74eb153daba32c20b7cef94d4e4
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747360"
---
# <a name="delegate-work-items-in-a-workflow"></a><span data-ttu-id="151a5-103">​Delegar itens de trabalho em um fluxo de trabalho​</span><span class="sxs-lookup"><span data-stu-id="151a5-103">Delegate work items in a workflow</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="manually-delegate-a-work-item"></a><span data-ttu-id="151a5-104">Delegar um item de trabalho manualmente</span><span class="sxs-lookup"><span data-stu-id="151a5-104">Manually delegate a work item</span></span>

<span data-ttu-id="151a5-105">Para delegar um item de trabalho específico, selecione a opção **Delegar** no menu **Fluxo de Trabalho** e insira o usuário a ser delegado junto com um comentário.</span><span class="sxs-lookup"><span data-stu-id="151a5-105">To delegate an individual work item, select the **Delegate** option in the **Workflow** menu and then enter the user to be delegated to along with a comment.</span></span> <span data-ttu-id="151a5-106">Isso atribuirá novamente o item de trabalho para que esse usuário possa concluí-lo.</span><span class="sxs-lookup"><span data-stu-id="151a5-106">This will reassign the work item to that user so they can complete it.</span></span>

## <a name="manually-delegate-multiple-work-items"></a><span data-ttu-id="151a5-107">Delegar manualmente vários itens de trabalho</span><span class="sxs-lookup"><span data-stu-id="151a5-107">Manually delegate multiple work items</span></span>

<span data-ttu-id="151a5-108">Vários itens de trabalho podem ser delegados em conjunto na página **Itens de trabalho atribuídos a mim**.</span><span class="sxs-lookup"><span data-stu-id="151a5-108">Multiple work items can be delegated together from the **Work items assigned to me** page.</span></span> <span data-ttu-id="151a5-109">Os seguintes tipos de fluxo de trabalho estão qualificados para delegação em massa: Fluxo de trabalho de aprovação do contrato de compra, Fluxo de trabalho da ordem de compra, Revisão da requisição de compra e Fluxo de trabalho da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="151a5-109">The following workflow types are eligible for mass delegation: Purchase agreement approval workflow, Purchase order workflow, Purchase requisition review, and Vendor invoice workflow.</span></span> <span data-ttu-id="151a5-110">O recurso **Delegar vários itens de trabalho** é desabilitado por padrão e pode ser habilitado em **Espaços de trabalho > Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="151a5-110">The **Delegate multiple work items** feature is disabled by default and can be enabled in **Workspaces > Feature management**.</span></span> <span data-ttu-id="151a5-111">Entre em contato com o administrador do sistema para obter ajuda para habilitar este recurso.</span><span class="sxs-lookup"><span data-stu-id="151a5-111">Contact your system administrator for help with enabling this feature.</span></span>
1.  <span data-ttu-id="151a5-112">Vá para **Comum > Comum > Itens de trabalho > Itens de trabalho atribuídos a mim**.</span><span class="sxs-lookup"><span data-stu-id="151a5-112">Go to **Common > Common > Work items > Work items assigned to me**.</span></span>
2.  <span data-ttu-id="151a5-113">Selecione os itens de trabalho que serão delegados.</span><span class="sxs-lookup"><span data-stu-id="151a5-113">Select the work items that will be delegated.</span></span>
3.  <span data-ttu-id="151a5-114">Clique no menu **Delegar itens de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="151a5-114">Click the **Delegate work items** menu.</span></span>
4.  <span data-ttu-id="151a5-115">No campo **Usuário**, selecione o usuário ao qual delegar os itens de trabalho.</span><span class="sxs-lookup"><span data-stu-id="151a5-115">In the **User** field, select the user to delegate the work items to.</span></span>
5.  <span data-ttu-id="151a5-116">No campo **Comentário**, insira um comentário que explique o motivo de você estar delegando os itens de trabalho.</span><span class="sxs-lookup"><span data-stu-id="151a5-116">In the **Comment** field, enter a comment that explains why you're delegating the work items.</span></span>
6.  <span data-ttu-id="151a5-117">Clique no botão **Delegar itens de trabalho** para concluir a delegação.</span><span class="sxs-lookup"><span data-stu-id="151a5-117">Click the **Delegate work items** button to complete the work item delegation.</span></span>

## <a name="automatically-delegate-work-items"></a><span data-ttu-id="151a5-118">Delegar itens de trabalho automaticamente</span><span class="sxs-lookup"><span data-stu-id="151a5-118">Automatically delegate work items</span></span>

<span data-ttu-id="151a5-119">Se pretende se ausentar do escritório ou ficar indisponível para executar ações em itens de trabalho por um período, você poderá delegar novos itens de trabalho automaticamente para outros usuários na página **Opções de usuário**.</span><span class="sxs-lookup"><span data-stu-id="151a5-119">If you plan to be out of the office or otherwise unavailable to act on work items for a period of time, you can automatically delegate new work items to other users using the **User options** page.</span></span>

### <a name="set-up-automatic-delegation"></a><span data-ttu-id="151a5-120">Configurar delegação automática</span><span class="sxs-lookup"><span data-stu-id="151a5-120">Set up automatic delegation</span></span>
1. <span data-ttu-id="151a5-121">Vá para **Comum > Configuração > Opções do usuário**.</span><span class="sxs-lookup"><span data-stu-id="151a5-121">Go to **Common > Setup > User options**.</span></span>
2. <span data-ttu-id="151a5-122">Clique na guia **Fluxo de trabalho**. Verifique se a seção Delegação está expandida.</span><span class="sxs-lookup"><span data-stu-id="151a5-122">Click the **Workflow** tab. Make sure the Delegation section is expanded.</span></span> <span data-ttu-id="151a5-123">Para configurar o sistema para delegar automaticamente seus itens de trabalho a outros usuários, você deve criar a regra de delegação, que especifique quando determinados tipos de itens de trabalho serão delegados.</span><span class="sxs-lookup"><span data-stu-id="151a5-123">To configure the system to automatically delegate your work items to other users, you must create delegation rules, which specify when certain types of work items are delegated.</span></span> <span data-ttu-id="151a5-124">Siga estas etapas para criar uma regra de delegação.</span><span class="sxs-lookup"><span data-stu-id="151a5-124">Follow these steps to create a delegation rule.</span></span>  
3. <span data-ttu-id="151a5-125">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="151a5-125">Click **Add**.</span></span>
4. <span data-ttu-id="151a5-126">No campo **Escopo**, selecione uma opção:</span><span class="sxs-lookup"><span data-stu-id="151a5-126">In the **Scope** field, select an option:</span></span>
    - <span data-ttu-id="151a5-127">Tudo - delega todos os itens de trabalho atribuídos a você.</span><span class="sxs-lookup"><span data-stu-id="151a5-127">All – Delegate all work items that are assigned to you.</span></span>
    - <span data-ttu-id="151a5-128">Módulo – Delega apenas os itens de trabalho relacionados a um tipo específico de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="151a5-128">Module – Delegate only the work items that are related to a specific type of workflow.</span></span> <span data-ttu-id="151a5-129">Se você selecionar essa opção, deverá selecionar o tipo de fluxo de trabalho no campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="151a5-129">If you select this option, you must select the type of workflow in the **Name** field.</span></span>
    - <span data-ttu-id="151a5-130">Fluxo de Trabalho – Delega apenas os itens de trabalho relacionados a um fluxo de trabalho específico.</span><span class="sxs-lookup"><span data-stu-id="151a5-130">Workflow – Delegate only the work items that are related to a specific workflow.</span></span> <span data-ttu-id="151a5-131">Se você selecionar essa opção, deverá selecionar o fluxo de trabalho no campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="151a5-131">If you select this option, you must select the workflow in the **Name** field.</span></span>  
5. <span data-ttu-id="151a5-132">No campo **Nome**:</span><span class="sxs-lookup"><span data-stu-id="151a5-132">In the **Name** field:</span></span>
    - <span data-ttu-id="151a5-133">Para o escopo **Módulo**, selecione o módulo de destino.</span><span class="sxs-lookup"><span data-stu-id="151a5-133">For **Module** scope, select the target module.</span></span>
    - <span data-ttu-id="151a5-134">Para o escopo **Fluxo de trabalho**, selecione o fluxo de trabalho de destino.</span><span class="sxs-lookup"><span data-stu-id="151a5-134">For **Workflow** scope, select the target workflow.</span></span>
6. <span data-ttu-id="151a5-135">No campo **Delegar**, selecione o usuário para delegar os itens de trabalho.</span><span class="sxs-lookup"><span data-stu-id="151a5-135">In the **Delegate** field, select the user to delegate the work items to.</span></span> <span data-ttu-id="151a5-136">Use os campos **Data/hora inicial** e **Data/hora final** para especificar quando você quer que os itens de trabalho sejam delegados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="151a5-136">Use the **Start date/time** and **End date/time** fields to specify when you want the work items to be automatically delegated.</span></span>  
7. <span data-ttu-id="151a5-137">No campo **Data/hora inicial**, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="151a5-137">In the **Start date/time** field, enter a date and time.</span></span>
8. <span data-ttu-id="151a5-138">No campo **Data/hora final**, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="151a5-138">In the **End date/time** field, enter a date and time.</span></span>
9. <span data-ttu-id="151a5-139">Marque a caixa de seleção **Habilitado** para ativar a regra de delegação.</span><span class="sxs-lookup"><span data-stu-id="151a5-139">Select the **Enabled** check box to activate the delegation rule.</span></span> 
10. <span data-ttu-id="151a5-140">No campo **Comentário**, insira um comentário que explique o motivo de você estar delegando os itens de trabalho.</span><span class="sxs-lookup"><span data-stu-id="151a5-140">In the **Comment** field, enter a comment that explains why you're delegating the work items.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]