---
title: Preparar um trabalho kanban de processo quando os materiais estão disponíveis para a célula de trabalho
description: Esta tarefa foca na preparação de um processo de trabalho kanban quanto todas materiais estão disponíveis para a célula de trabalho.
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 714196ba92fe3f57c80809930ed54705a4e75078
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "341939"
---
# <a name="prepare-a-process-kanban-job-when-materials-are-available-for-the-work-cell"></a><span data-ttu-id="68fe4-103">Preparar um trabalho kanban de processo quando os materiais estão disponíveis para a célula de trabalho</span><span class="sxs-lookup"><span data-stu-id="68fe4-103">Prepare a process kanban job when materials are available for the work cell</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="68fe4-104">Esta tarefa foca na preparação de um processo de trabalho kanban quanto todas materiais estão disponíveis para a célula de trabalho.</span><span class="sxs-lookup"><span data-stu-id="68fe4-104">This task focuses on preparing a process kanban job when all materials are available for the work cell.</span></span> <span data-ttu-id="68fe4-105">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="68fe4-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="68fe4-106">Essa tarefa é destinado ao operador da máquina.</span><span class="sxs-lookup"><span data-stu-id="68fe4-106">This task is intended for the machine operator.</span></span>

1. <span data-ttu-id="68fe4-107">Vá para o quadro kanban para processar trabalhos.</span><span class="sxs-lookup"><span data-stu-id="68fe4-107">Go to Kanban board for process jobs.</span></span>
2. <span data-ttu-id="68fe4-108">No campo Célula de trabalho, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="68fe4-108">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="68fe4-109">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="68fe4-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="68fe4-110">Selecione célula de trabalho 1250 e clique em OK.</span><span class="sxs-lookup"><span data-stu-id="68fe4-110">Select work cell 1250 and click OK.</span></span>  
4. <span data-ttu-id="68fe4-111">Na lista, selecione a linha 4.</span><span class="sxs-lookup"><span data-stu-id="68fe4-111">In the list, select row 4.</span></span>
    * <span data-ttu-id="68fe4-112">Na empresa que limpa a demonstração, o kanban 000329 na linha 4 é o primeiro trabalho que não está encerrado.</span><span class="sxs-lookup"><span data-stu-id="68fe4-112">In the clean demo company, Kanban 000329 in row 4 is the first job that is not completed yet.</span></span>  
5. <span data-ttu-id="68fe4-113">Alternar a expansão da seção Lista de separação.</span><span class="sxs-lookup"><span data-stu-id="68fe4-113">Toggle the expansion of the Picking list section.</span></span>
    * <span data-ttu-id="68fe4-114">Verifique se o status de fornecimento estão disponíveis para todos os itens da lista de separação.</span><span class="sxs-lookup"><span data-stu-id="68fe4-114">Verify that the supply status is available for all items in the picking list.</span></span>  
    * <span data-ttu-id="68fe4-115">Se vários trabalhos são selecionados, a lista de separação mostrará a soma de todos os itens necessários para o trabalho selecionado.</span><span class="sxs-lookup"><span data-stu-id="68fe4-115">If multiple jobs are selected, the picking list will show the sum of all items needed for the selected jobs.</span></span>  
6. <span data-ttu-id="68fe4-116">Clique em Preparar.</span><span class="sxs-lookup"><span data-stu-id="68fe4-116">Click Prepare.</span></span>
    * <span data-ttu-id="68fe4-117">O processo de preparação é concluído agora.</span><span class="sxs-lookup"><span data-stu-id="68fe4-117">The preparation process is now completed.</span></span> <span data-ttu-id="68fe4-118">A caixa de seleção marcada para todas as linhas da lista de separação indica que o status da fonte será separado.</span><span class="sxs-lookup"><span data-stu-id="68fe4-118">The selected check box for all rows in the picking list indicates that the supply status is picked.</span></span>  

