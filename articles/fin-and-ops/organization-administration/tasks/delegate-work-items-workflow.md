--- 
title: Delegar itens de trabalho em um fluxo de trabalho
description: "Se você planeja se ausentar do escritório ou ficar indisponível para executar ações em itens de trabalho, poderá delegar ou reatribuir seus itens de trabalho a outros usuários."
author: jasongre
manager: AnnBe
ms.date: 02/21/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: cd3d09ed12fa4419881910884acefaf1bf5fa0d4
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="delegate-work-items-in-a-workflow"></a><span data-ttu-id="d7b5a-103">Delegar itens de trabalho em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="d7b5a-103">Delegate work items in a workflow</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d7b5a-104">Se você planeja se ausentar do escritório ou ficar indisponível para executar ações em itens de trabalho, poderá delegar ou reatribuir seus itens de trabalho a outros usuários.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-104">If you plan to be out of the office or otherwise unavailable to act on work items, you can delegate, or reassign, your work items to other users.</span></span> <span data-ttu-id="d7b5a-105">Este procedimento ajuda a configurar o sistema para delegar automaticamente seus itens de trabalho a outro usuário.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-105">This procedure helps you configure the system to automatically delegate your work items to another user.</span></span>



<span data-ttu-id="d7b5a-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-automatic-delegation"></a><span data-ttu-id="d7b5a-107">Configurar delegação automática</span><span class="sxs-lookup"><span data-stu-id="d7b5a-107">Set up automatic delegation</span></span>
1. <span data-ttu-id="d7b5a-108">Vá para Comum > Configuração > Opções do usuário.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-108">Go to Common > Setup > User options.</span></span>
2. <span data-ttu-id="d7b5a-109">Clique na guia Fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-109">Click the Workflow tab.</span></span>
    * <span data-ttu-id="d7b5a-110">Certifique-se de que a seção Delegação está expandida.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-110">Make sure the Delegation section is expanded.</span></span>    <span data-ttu-id="d7b5a-111">Para configurar o sistema para delegar automaticamente seus itens de trabalho a outros usuários, você deve criar a regra de delegação, que especifique quando determinados tipos de itens de trabalho serão delegados.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-111">To configure the system to automatically delegate your work items to other users, you must create delegation rules, which specify when certain types of work items are delegated.</span></span> <span data-ttu-id="d7b5a-112">Siga estas etapas para criar uma regra de delegação.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-112">Follow these steps to create a delegation rule.</span></span>  
3. <span data-ttu-id="d7b5a-113">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-113">Click Add.</span></span>
4. <span data-ttu-id="d7b5a-114">No campo Escopo, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-114">In the Scope field, select an option.</span></span>
    * <span data-ttu-id="d7b5a-115">Tudo - delega todos os itens de trabalho atribuídos a você.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-115">All – Delegate all work items that are assigned to you.</span></span>    <span data-ttu-id="d7b5a-116">Módulo – Delega apenas os itens de trabalho relacionados a um tipo específico de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-116">Module – Delegate only the work items that are related to a specific type of workflow.</span></span> <span data-ttu-id="d7b5a-117">Se você selecionar essa opção, selecione o tipo de fluxo de trabalho no campo Nome.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-117">If you select this option, you must select the type of workflow in the Name field.</span></span>    <span data-ttu-id="d7b5a-118">Fluxo de Trabalho – Delega apenas os itens de trabalho relacionados a um fluxo de trabalho específico.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-118">Workflow – Delegate only the work items that are related to a specific workflow.</span></span> <span data-ttu-id="d7b5a-119">Se você selecionar essa opção, selecione o fluxo de trabalho no campo Nome.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-119">If you select this option, you must select the workflow in the Name field.</span></span>  
5. <span data-ttu-id="d7b5a-120">No campo Delegar, selecione o usuário para delegar os itens de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-120">In the Delegate field, select the user to delegate the work items to.</span></span>
    * <span data-ttu-id="d7b5a-121">Use os campos Data/hora inicial e Data/hora final para especificar quando você quer que os itens de trabalho sejam delegados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-121">Use the Start date/time and End date/time fields to specify when you want the work items to be automatically delegated.</span></span>  
6. <span data-ttu-id="d7b5a-122">No campo Data/hora inicial, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-122">In the Start date/time field, enter a date and time.</span></span>
7. <span data-ttu-id="d7b5a-123">No campo Data/hora final, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-123">In the End date/time field, enter a date and time.</span></span>
8. <span data-ttu-id="d7b5a-124">Marque a caixa de seleção Habilitado para ativar a regra de delegação.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-124">Select the Enabled check box to activate the delegation rule.</span></span>
    * <span data-ttu-id="d7b5a-125">Se você selecionou Módulo o como o Escopo, em seguida, você deve selecionar o módulo no campo Nome.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-125">If you selected Module as the Scope, then you must select the module in the Name field.</span></span>    <span data-ttu-id="d7b5a-126">Se você selecionou Fluxo de Trabalho como o Escopo, em seguida, você deve selecionar fluxo de trabalho específico para delegar no campo Nome.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-126">If you selected Workflow as the Scope, then you must select the specific workflow to delegate in the Name field.</span></span>  
9. <span data-ttu-id="d7b5a-127">No campo Comentário, insira um comentário que explique o motivo pelo qual você está delegando os itens de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d7b5a-127">In the Comment field, enter a comment that explains why you are delegating the work items.</span></span>


