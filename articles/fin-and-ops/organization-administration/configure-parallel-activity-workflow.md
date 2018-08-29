---
title: Configurar atividades paralelas em um fluxo de trabalho
description: Para configurar uma atividade paralela, execute estes procedimentos no editor de fluxo de trabalho.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 64cd387f8a6ab693d159cd659fca51fa6568ee39
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---

# <a name="configure-parallel-activities-in-a-workflow"></a><span data-ttu-id="8294e-103">Configurar atividades paralelas em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="8294e-103">Configure parallel activities in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8294e-104">Para configurar uma atividade paralela, execute estes procedimentos no editor de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="8294e-104">To configure a parallel activity, complete the following procedures in the workflow editor.</span></span>

<span data-ttu-id="8294e-105">Uma atividade paralela consiste em ramificações do fluxo de trabalho que são executadas simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="8294e-105">A parallel activity consists of workflow branches that run at the same time.</span></span>

## <a name="name-a-parallel-activity"></a><span data-ttu-id="8294e-106">Forneça um nome à atividade paralela.</span><span class="sxs-lookup"><span data-stu-id="8294e-106">Name a parallel activity</span></span>
<span data-ttu-id="8294e-107">Siga estas etapas para inserir um nome para a atividade paralela.</span><span class="sxs-lookup"><span data-stu-id="8294e-107">Follow these steps to enter a name for a parallel activity.</span></span>
1.  <span data-ttu-id="8294e-108">Clique com o botão direito do mouse na atividade paralela e clique em **Propriedades** para abrir o formulário **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8294e-108">Right-click the parallel activity, and then click **Properties** to open the **Properties** form.</span></span>
2.  <span data-ttu-id="8294e-109">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="8294e-109">In the left pane, click **Basic Settings**.</span></span>
3.  <span data-ttu-id="8294e-110">No campo **Nome**, insira um nome exclusivo para a atividade paralela.</span><span class="sxs-lookup"><span data-stu-id="8294e-110">In the **Name** field, enter a unique name for the parallel activity.</span></span>
4.  <span data-ttu-id="8294e-111">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="8294e-111">Click **Close**.</span></span>

## <a name="configure-the-branches-of-a-parallel-activity"></a><span data-ttu-id="8294e-112">Configurar as ramificações da atividade paralela</span><span class="sxs-lookup"><span data-stu-id="8294e-112">Configure the branches of a parallel activity</span></span>
<span data-ttu-id="8294e-113">Siga estas etapas para adicionar e configurar as ramificações dessa atividade paralela.</span><span class="sxs-lookup"><span data-stu-id="8294e-113">Follow these steps to add and configure the branches of this parallel activity.</span></span>
1. <span data-ttu-id="8294e-114">Clique duas vezes na atividade paralela para exibir suas ramificações.</span><span class="sxs-lookup"><span data-stu-id="8294e-114">Double-click the parallel activity to display the branches of the parallel activity.</span></span>
2. <span data-ttu-id="8294e-115">Para adicionar uma ramificação, arraste o elemento **Ramificação** da área **Elemento de fluxo de trabalho** para um ponto de inserção na tela.</span><span class="sxs-lookup"><span data-stu-id="8294e-115">To add a branch, drag the **Branch** element from the **Workflow elements** area to an insertion point on the canvas.</span></span> <span data-ttu-id="8294e-116">A figura a seguir mostra um ponto de inserção.![Ponto de inserção](./media/workflow_insertionpoint.gif)</span><span class="sxs-lookup"><span data-stu-id="8294e-116">The following figure shows an insertion point.![Insertion point](./media/workflow_insertionpoint.gif)</span></span>

   |                                              <span data-ttu-id="8294e-117"><strong>Nota</strong></span><span class="sxs-lookup"><span data-stu-id="8294e-117"><strong>Note</strong></span></span>                                               |
   |------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="8294e-118">A ordem das ramificações não é importante porque todas as ramificações de uma atividade paralela são executadas ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="8294e-118">The order of the branches is not important because all the branches of a parallel activity run at the same time.</span></span> |


3. <span data-ttu-id="8294e-119">Cada ramificação para configurar, consulte [Configurar uma filial paralelo](configure-parallel-branch-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="8294e-119">To configure each branch, see [Configure a parallel branch](configure-parallel-branch-workflow.md).</span></span>






