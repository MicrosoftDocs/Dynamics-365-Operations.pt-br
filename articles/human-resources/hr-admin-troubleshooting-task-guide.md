---
title: Salvar guias de tarefa no LCS e repeti-las
description: Este artigo explica como salvar as guias de tarefa para o Microsoft Dynamics Lifecycle Services (LCS) e depois reproduzi-las.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b55937c0867117809471f50f1987f7bf12a4b25d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4417291"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a><span data-ttu-id="c9dff-103">Salvar guias de tarefa no LCS e repeti-las</span><span class="sxs-lookup"><span data-stu-id="c9dff-103">Save task guides to LCS and replay them</span></span>

<span data-ttu-id="c9dff-104">**Detalhes do ambiente**</span><span class="sxs-lookup"><span data-stu-id="c9dff-104">**Environment details**</span></span> 

<span data-ttu-id="c9dff-105">Microsoft Dynamics 365 Human Resources, que foi implantado por meio do Microsoft Dynamics Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="c9dff-105">Microsoft Dynamics 365 Human Resources, which was deployed via Microsoft Dynamics Lifecycle Services (LCS)</span></span>

<span data-ttu-id="c9dff-106">**Saída**</span><span class="sxs-lookup"><span data-stu-id="c9dff-106">**Issue**</span></span>

<span data-ttu-id="c9dff-107">O cliente deseja salvar novas gravações de tarefa para seu projeto LCS, e depois repeti-las às guias de tarefa salvas.</span><span class="sxs-lookup"><span data-stu-id="c9dff-107">The customer wants to save new task recordings to his or her LCS project, and then replay the saved task guides.</span></span>

<span data-ttu-id="c9dff-108">**Resolução**</span><span class="sxs-lookup"><span data-stu-id="c9dff-108">**Resolution**</span></span>

<span data-ttu-id="c9dff-109">Siga estas etapas para salvar uma gravação de tarefas ao LCS.</span><span class="sxs-lookup"><span data-stu-id="c9dff-109">Follow these steps to save a task recording to LCS.</span></span>

1. <span data-ttu-id="c9dff-110">Conecte-se ao LCS e selecione o projeto.</span><span class="sxs-lookup"><span data-stu-id="c9dff-110">Sign in to LCS, and select the project.</span></span>
2. <span data-ttu-id="c9dff-111">Selecione o quadro **Modelador de processo de negócios**.</span><span class="sxs-lookup"><span data-stu-id="c9dff-111">Select the **Business process modeler** tile.</span></span>
3. <span data-ttu-id="c9dff-112">Exibir a página na "Experiência de BPM atualizado".</span><span class="sxs-lookup"><span data-stu-id="c9dff-112">View the page in the "Updated BPM experience."</span></span>
4. <span data-ttu-id="c9dff-113">Selecione uma biblioteca e selecione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="c9dff-113">Select a library, and then select **Copy**.</span></span>
5. <span data-ttu-id="c9dff-114">Insira um nome para o modelo do Modelador de processo de negócios (BPM).</span><span class="sxs-lookup"><span data-stu-id="c9dff-114">Enter a name for the Business process modeler (BPM) model.</span></span>
6. <span data-ttu-id="c9dff-115">Faça logon no Human Resources do LCS.</span><span class="sxs-lookup"><span data-stu-id="c9dff-115">Sign in to Human Resources from LCS.</span></span>
7. <span data-ttu-id="c9dff-116">No campo **Pesquisar**, insira **ajuda**.</span><span class="sxs-lookup"><span data-stu-id="c9dff-116">In the **Search** field, enter **help**.</span></span> <span data-ttu-id="c9dff-117">Ajuda do Lifecycle Services é aberta.</span><span class="sxs-lookup"><span data-stu-id="c9dff-117">Lifecycle Services Help is opened.</span></span>
8. <span data-ttu-id="c9dff-118">Selecione o botão **Atualizar** para configuração da ajuda do Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="c9dff-118">Select the **Refresh** button for Lifecycle Services Help configuration.</span></span>

    <span data-ttu-id="c9dff-119">A nova biblioteca de BPM deve aparecer e deve ficar ativa.</span><span class="sxs-lookup"><span data-stu-id="c9dff-119">Your new BPM library should appear, and it should be active.</span></span>

9. <span data-ttu-id="c9dff-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c9dff-120">Close the page.</span></span>
10. <span data-ttu-id="c9dff-121">Criar uma gravação de tarefas.</span><span class="sxs-lookup"><span data-stu-id="c9dff-121">Create a task recording.</span></span>
11. <span data-ttu-id="c9dff-122">Quando terminar, selecione **Salvar para Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="c9dff-122">When you've finished, select **Save to Lifecycle Services**.</span></span>

    ![Salvar no Lifecycle Services](media/task-guides.png)

12. <span data-ttu-id="c9dff-124">Selecione a biblioteca e nó de BPM onde deseja salvar a gravação de tarefa.</span><span class="sxs-lookup"><span data-stu-id="c9dff-124">Select the BPM library and node to save the task recording to.</span></span>

<span data-ttu-id="c9dff-125">Rastrear essas etapas para repetir uma guia de tarefas do LCS.</span><span class="sxs-lookup"><span data-stu-id="c9dff-125">Follow these steps to replay a task guide from LCS.</span></span>

1. <span data-ttu-id="c9dff-126">Iniciar Gravador de tarefas.</span><span class="sxs-lookup"><span data-stu-id="c9dff-126">Start Task recorder.</span></span>
2. <span data-ttu-id="c9dff-127">Selecione **Abrir a partir do LCS**.</span><span class="sxs-lookup"><span data-stu-id="c9dff-127">Select **Open from LCS**.</span></span>
3. <span data-ttu-id="c9dff-128">Selecione a biblioteca e o nó de BPM que têm a guia da tarefa salva.</span><span class="sxs-lookup"><span data-stu-id="c9dff-128">Select the library and the BPM node that have the saved task guide.</span></span>
4. <span data-ttu-id="c9dff-129">Abrir a guia de tarefas.</span><span class="sxs-lookup"><span data-stu-id="c9dff-129">Open the task guide.</span></span>
