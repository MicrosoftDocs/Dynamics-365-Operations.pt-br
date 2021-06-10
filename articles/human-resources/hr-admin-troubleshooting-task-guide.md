---
title: Salvar guias de tarefa no LCS e repeti-las
description: Este artigo explica como salvar as guias de tarefa para o Microsoft Dynamics Lifecycle Services (LCS) e depois reproduzi-las.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8a18bb14ba8c3c926065c97b0ee26c38ee86ded2
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053266"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a><span data-ttu-id="79c29-103">Salvar guias de tarefa no LCS e repeti-las</span><span class="sxs-lookup"><span data-stu-id="79c29-103">Save task guides to LCS and replay them</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="79c29-104">**Detalhes do ambiente**</span><span class="sxs-lookup"><span data-stu-id="79c29-104">**Environment details**</span></span> 

<span data-ttu-id="79c29-105">Microsoft Dynamics 365 Human Resources, que foi implantado por meio do Microsoft Dynamics Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="79c29-105">Microsoft Dynamics 365 Human Resources, which was deployed via Microsoft Dynamics Lifecycle Services (LCS)</span></span>

<span data-ttu-id="79c29-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="79c29-106">**Issue**</span></span>

<span data-ttu-id="79c29-107">O cliente quer salvar novos registros do trabalho no projeto LCS e, então, reproduzir os guias de tarefa salvos.</span><span class="sxs-lookup"><span data-stu-id="79c29-107">The customer wants to save new task recordings to the LCS project, and then replay the saved task guides.</span></span>

<span data-ttu-id="79c29-108">**Resolução**</span><span class="sxs-lookup"><span data-stu-id="79c29-108">**Resolution**</span></span>

<span data-ttu-id="79c29-109">Siga estas etapas para salvar uma gravação de tarefas ao LCS.</span><span class="sxs-lookup"><span data-stu-id="79c29-109">Follow these steps to save a task recording to LCS.</span></span>

1. <span data-ttu-id="79c29-110">Conecte-se ao LCS e selecione o projeto.</span><span class="sxs-lookup"><span data-stu-id="79c29-110">Sign in to LCS, and select the project.</span></span>
2. <span data-ttu-id="79c29-111">Selecione o quadro **Modelador de processo de negócios**.</span><span class="sxs-lookup"><span data-stu-id="79c29-111">Select the **Business process modeler** tile.</span></span>
3. <span data-ttu-id="79c29-112">Exibir a página na "Experiência de BPM atualizado".</span><span class="sxs-lookup"><span data-stu-id="79c29-112">View the page in the "Updated BPM experience."</span></span>
4. <span data-ttu-id="79c29-113">Selecione uma biblioteca e selecione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="79c29-113">Select a library, and then select **Copy**.</span></span>
5. <span data-ttu-id="79c29-114">Insira um nome para o modelo do Modelador de processo de negócios (BPM).</span><span class="sxs-lookup"><span data-stu-id="79c29-114">Enter a name for the Business process modeler (BPM) model.</span></span>
6. <span data-ttu-id="79c29-115">Faça logon no Human Resources do LCS.</span><span class="sxs-lookup"><span data-stu-id="79c29-115">Sign in to Human Resources from LCS.</span></span>
7. <span data-ttu-id="79c29-116">No campo **Pesquisar**, insira **ajuda**.</span><span class="sxs-lookup"><span data-stu-id="79c29-116">In the **Search** field, enter **help**.</span></span> <span data-ttu-id="79c29-117">Ajuda do Lifecycle Services é aberta.</span><span class="sxs-lookup"><span data-stu-id="79c29-117">Lifecycle Services Help is opened.</span></span>
8. <span data-ttu-id="79c29-118">Selecione o botão **Atualizar** para configuração da ajuda do Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="79c29-118">Select the **Refresh** button for Lifecycle Services Help configuration.</span></span>

    <span data-ttu-id="79c29-119">A nova biblioteca de BPM deve aparecer e deve ficar ativa.</span><span class="sxs-lookup"><span data-stu-id="79c29-119">Your new BPM library should appear, and it should be active.</span></span>

9. <span data-ttu-id="79c29-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="79c29-120">Close the page.</span></span>
10. <span data-ttu-id="79c29-121">Criar uma gravação de tarefas.</span><span class="sxs-lookup"><span data-stu-id="79c29-121">Create a task recording.</span></span>
11. <span data-ttu-id="79c29-122">Quando terminar, selecione **Salvar para Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="79c29-122">When you've finished, select **Save to Lifecycle Services**.</span></span>

    ![Salvar no Lifecycle Services](media/task-guides.png)

12. <span data-ttu-id="79c29-124">Selecione a biblioteca e nó de BPM onde deseja salvar a gravação de tarefa.</span><span class="sxs-lookup"><span data-stu-id="79c29-124">Select the BPM library and node to save the task recording to.</span></span>

<span data-ttu-id="79c29-125">Rastrear essas etapas para repetir uma guia de tarefas do LCS.</span><span class="sxs-lookup"><span data-stu-id="79c29-125">Follow these steps to replay a task guide from LCS.</span></span>

1. <span data-ttu-id="79c29-126">Iniciar Gravador de tarefas.</span><span class="sxs-lookup"><span data-stu-id="79c29-126">Start Task recorder.</span></span>
2. <span data-ttu-id="79c29-127">Selecione **Abrir a partir do LCS**.</span><span class="sxs-lookup"><span data-stu-id="79c29-127">Select **Open from LCS**.</span></span>
3. <span data-ttu-id="79c29-128">Selecione a biblioteca e o nó de BPM que têm a guia da tarefa salva.</span><span class="sxs-lookup"><span data-stu-id="79c29-128">Select the library and the BPM node that have the saved task guide.</span></span>
4. <span data-ttu-id="79c29-129">Abrir a guia de tarefas.</span><span class="sxs-lookup"><span data-stu-id="79c29-129">Open the task guide.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]