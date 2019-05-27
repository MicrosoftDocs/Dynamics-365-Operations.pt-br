---
title: Delegar itens de trabalho em um fluxo de trabalho
description: Se você planeja se ausentar do escritório ou ficar indisponível para executar ações em itens de trabalho, poderá delegar ou reatribuir seus itens de trabalho a outros usuários.
author: jasongre
manager: AnnBe
ms.date: 04/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: feace647d7acef6abf86b13fcb8019c622c55ff6
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509443"
---
# <a name="delegate-work-items-in-a-workflow"></a><span data-ttu-id="2f23b-103">​Delegar itens de trabalho em um fluxo de trabalho​</span><span class="sxs-lookup"><span data-stu-id="2f23b-103">Delegate work items in a workflow</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

## <a name="manually-delegate-a-work-item"></a><span data-ttu-id="2f23b-104">Delegar um item de trabalho manualmente</span><span class="sxs-lookup"><span data-stu-id="2f23b-104">Manually delegate a work item</span></span>

<span data-ttu-id="2f23b-105">Para delegar um item de trabalho específico, selecione a opção **Delegar** no menu **Fluxo de Trabalho** e insira o usuário a ser delegado junto com um comentário.</span><span class="sxs-lookup"><span data-stu-id="2f23b-105">To delegate an individual work item, select the **Delegate** option in the **Workflow** menu and then enter the user to be delegated to along with a comment.</span></span> <span data-ttu-id="2f23b-106">Isso atribuirá novamente o item de trabalho para que esse usuário possa concluí-lo.</span><span class="sxs-lookup"><span data-stu-id="2f23b-106">This will reassign the work item to that user so they can complete it.</span></span>

## <a name="automatically-delegate-work-items"></a><span data-ttu-id="2f23b-107">Delegar itens de trabalho automaticamente</span><span class="sxs-lookup"><span data-stu-id="2f23b-107">Automatically delegate work items</span></span>

<span data-ttu-id="2f23b-108">Se pretende se ausentar do escritório ou ficar indisponível para executar ações em itens de trabalho por um período, você poderá delegar novos itens de trabalho automaticamente para outros usuários na página **Opções de usuário**.</span><span class="sxs-lookup"><span data-stu-id="2f23b-108">If you plan to be out of the office or otherwise unavailable to act on work items for a period of time, you can automatically delegate new work items to other users using the **User options** page.</span></span>

### <a name="set-up-automatic-delegation"></a><span data-ttu-id="2f23b-109">Configurar delegação automática</span><span class="sxs-lookup"><span data-stu-id="2f23b-109">Set up automatic delegation</span></span>
1. <span data-ttu-id="2f23b-110">Vá para Comum > Configuração > Opções do usuário.</span><span class="sxs-lookup"><span data-stu-id="2f23b-110">Go to Common > Setup > User options.</span></span>
2. <span data-ttu-id="2f23b-111">Clique na guia Fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2f23b-111">Click the Workflow tab.</span></span>
    * <span data-ttu-id="2f23b-112">Certifique-se de que a seção Delegação está expandida.</span><span class="sxs-lookup"><span data-stu-id="2f23b-112">Make sure the Delegation section is expanded.</span></span>    <span data-ttu-id="2f23b-113">Para configurar o sistema para delegar automaticamente seus itens de trabalho a outros usuários, você deve criar a regra de delegação, que especifique quando determinados tipos de itens de trabalho serão delegados.</span><span class="sxs-lookup"><span data-stu-id="2f23b-113">To configure the system to automatically delegate your work items to other users, you must create delegation rules, which specify when certain types of work items are delegated.</span></span> <span data-ttu-id="2f23b-114">Siga estas etapas para criar uma regra de delegação.</span><span class="sxs-lookup"><span data-stu-id="2f23b-114">Follow these steps to create a delegation rule.</span></span>  
3. <span data-ttu-id="2f23b-115">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="2f23b-115">Click Add.</span></span>
4. <span data-ttu-id="2f23b-116">No campo Escopo, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="2f23b-116">In the Scope field, select an option.</span></span>
    * <span data-ttu-id="2f23b-117">Tudo - delega todos os itens de trabalho atribuídos a você.</span><span class="sxs-lookup"><span data-stu-id="2f23b-117">All – Delegate all work items that are assigned to you.</span></span>    <span data-ttu-id="2f23b-118">Módulo – Delega apenas os itens de trabalho relacionados a um tipo específico de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2f23b-118">Module – Delegate only the work items that are related to a specific type of workflow.</span></span> <span data-ttu-id="2f23b-119">Se você selecionar essa opção, selecione o tipo de fluxo de trabalho no campo Nome.</span><span class="sxs-lookup"><span data-stu-id="2f23b-119">If you select this option, you must select the type of workflow in the Name field.</span></span>    <span data-ttu-id="2f23b-120">Fluxo de Trabalho – Delega apenas os itens de trabalho relacionados a um fluxo de trabalho específico.</span><span class="sxs-lookup"><span data-stu-id="2f23b-120">Workflow – Delegate only the work items that are related to a specific workflow.</span></span> <span data-ttu-id="2f23b-121">Se você selecionar essa opção, selecione o fluxo de trabalho no campo Nome.</span><span class="sxs-lookup"><span data-stu-id="2f23b-121">If you select this option, you must select the workflow in the Name field.</span></span>  
5. <span data-ttu-id="2f23b-122">No campo Delegar, selecione o usuário para delegar os itens de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2f23b-122">In the Delegate field, select the user to delegate the work items to.</span></span>
    * <span data-ttu-id="2f23b-123">Use os campos Data/hora inicial e Data/hora final para especificar quando você quer que os itens de trabalho sejam delegados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2f23b-123">Use the Start date/time and End date/time fields to specify when you want the work items to be automatically delegated.</span></span>  
6. <span data-ttu-id="2f23b-124">No campo Data/hora inicial, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="2f23b-124">In the Start date/time field, enter a date and time.</span></span>
7. <span data-ttu-id="2f23b-125">No campo Data/hora final, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="2f23b-125">In the End date/time field, enter a date and time.</span></span>
8. <span data-ttu-id="2f23b-126">Marque a caixa de seleção Habilitado para ativar a regra de delegação.</span><span class="sxs-lookup"><span data-stu-id="2f23b-126">Select the Enabled check box to activate the delegation rule.</span></span>
    * <span data-ttu-id="2f23b-127">Se você selecionou Módulo o como o Escopo, em seguida, você deve selecionar o módulo no campo Nome.</span><span class="sxs-lookup"><span data-stu-id="2f23b-127">If you selected Module as the Scope, then you must select the module in the Name field.</span></span>    <span data-ttu-id="2f23b-128">Se você selecionou Fluxo de Trabalho como o Escopo, em seguida, você deve selecionar fluxo de trabalho específico para delegar no campo Nome.</span><span class="sxs-lookup"><span data-stu-id="2f23b-128">If you selected Workflow as the Scope, then you must select the specific workflow to delegate in the Name field.</span></span>  
9. <span data-ttu-id="2f23b-129">No campo Comentário, insira um comentário que explique o motivo pelo qual você está delegando os itens de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2f23b-129">In the Comment field, enter a comment that explains why you are delegating the work items.</span></span>

