---
title: Preparar um trabalho kanban de processo quando materiais não estão disponíveis para a célula de trabalho
description: Esse procedimento se concentra em preparar uns trabalhos kanban de processo embora alguns materiais não estejam disponíveis para a célula de trabalho, consequentemente é necessário escolher materiais de depósito.
author: ChristianRytt
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
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f7e7eb46bda13ef7e72189f921686a9889a8773c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559062"
---
# <a name="prepare-a-process-kanban-job-when-materials-are-not-available-for-the-work-cell"></a><span data-ttu-id="7c5e0-103">Preparar um trabalho kanban de processo quando materiais não estão disponíveis para a célula de trabalho</span><span class="sxs-lookup"><span data-stu-id="7c5e0-103">Prepare a process kanban job when materials are not available for the work cell</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7c5e0-104">Esse procedimento se concentra em preparar uns trabalhos kanban de processo embora alguns materiais não estejam disponíveis para a célula de trabalho, consequentemente é necessário escolher materiais de depósito.</span><span class="sxs-lookup"><span data-stu-id="7c5e0-104">This procedure focuses on preparing a process kanban job when some materials are not available for the work cell, therefore it's necessary to pick materials from the warehouse.</span></span> <span data-ttu-id="7c5e0-105">O procedimento “Preparar uns trabalhos kanban de processo quando os materiais estiverem disponíveis” é um pré-requisito para a criação deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="7c5e0-105">The procedure "Prepare a process kanban job when materials are available" is a prerequisite for creating this procedure.</span></span> <span data-ttu-id="7c5e0-106">Esse procedimento é destinado ao operador da máquina.</span><span class="sxs-lookup"><span data-stu-id="7c5e0-106">This procedure is intended for the machine operator.</span></span> <span data-ttu-id="7c5e0-107">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="7c5e0-107">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="7c5e0-108">Vá para Controle de produção > Kanban > Quadro Kanban para trabalhos de processo.</span><span class="sxs-lookup"><span data-stu-id="7c5e0-108">Go to Production control > Kanban > Kanban board for process jobs.</span></span>
2. <span data-ttu-id="7c5e0-109">No campo Célula de trabalho, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7c5e0-109">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="7c5e0-110">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7c5e0-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="7c5e0-111">Selecione a célula de trabalho 1250.</span><span class="sxs-lookup"><span data-stu-id="7c5e0-111">Select work cell 1250.</span></span>  
4. <span data-ttu-id="7c5e0-112">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="7c5e0-112">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7c5e0-113">Selecionar Kanban 000356.</span><span class="sxs-lookup"><span data-stu-id="7c5e0-113">Select Kanban 000356.</span></span>  
5. <span data-ttu-id="7c5e0-114">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="7c5e0-114">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7c5e0-115">Na lista, desmarque a linha 4</span><span class="sxs-lookup"><span data-stu-id="7c5e0-115">In the list, deselect row 4.</span></span> <span data-ttu-id="7c5e0-116">ou selecione a linha 4 se você não concluiu a tarefa "Preparar um trabalho kanban de processo quando os materiais estiverem disponíveis".</span><span class="sxs-lookup"><span data-stu-id="7c5e0-116">or Select row 4 if you haven't completed the task "Prepare a process kanban job when materials are available."</span></span>  
6. <span data-ttu-id="7c5e0-117">Alternar a expansão da seção Lista de separação.</span><span class="sxs-lookup"><span data-stu-id="7c5e0-117">Toggle the expansion of the Picking list section.</span></span>
    * <span data-ttu-id="7c5e0-118">Nenhum ícone de entrada no status da fonte indica que 48 ea do item P0002 não foram feitas para a célula de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7c5e0-118">The No entry icon in the supply status indicates that 48 ea of item P0002 are missing for the work cell.</span></span>  

## <a name="transfer-materials-to-work-cell"></a><span data-ttu-id="7c5e0-119">Materiais de transferência para célula de trabalho</span><span class="sxs-lookup"><span data-stu-id="7c5e0-119">Transfer materials to work cell</span></span>
1. <span data-ttu-id="7c5e0-120">Alternar a expansão da seção Trabalhos de transferência.</span><span class="sxs-lookup"><span data-stu-id="7c5e0-120">Toggle the expansion of the Transfer jobs section.</span></span>
2. <span data-ttu-id="7c5e0-121">Use o Filtro Rápido para filtrar o campo Número do item com o valor 'P0002'.</span><span class="sxs-lookup"><span data-stu-id="7c5e0-121">Use the Quick Filter to filter on the Item number field with a value of 'P0002'.</span></span>
3. <span data-ttu-id="7c5e0-122">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="7c5e0-122">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="7c5e0-123">Clique em Iniciar.</span><span class="sxs-lookup"><span data-stu-id="7c5e0-123">Click Start.</span></span>
    * <span data-ttu-id="7c5e0-124">Transferência em andamento</span><span class="sxs-lookup"><span data-stu-id="7c5e0-124">Transfer is in progress.</span></span>  
5. <span data-ttu-id="7c5e0-125">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="7c5e0-125">Click Complete.</span></span>
    * <span data-ttu-id="7c5e0-126">O item P0002 está disponível na lista de separação para os trabalhos kanban.</span><span class="sxs-lookup"><span data-stu-id="7c5e0-126">Item P0002 is now available in the picking list for the kanban job.</span></span> <span data-ttu-id="7c5e0-127">Isso significa que podemos preparar o kanban com todos os materiais necessários.</span><span class="sxs-lookup"><span data-stu-id="7c5e0-127">This means that we can prepare the kanban with all the needed materials.</span></span>  
6. <span data-ttu-id="7c5e0-128">Clique em Preparar.</span><span class="sxs-lookup"><span data-stu-id="7c5e0-128">Click Prepare.</span></span>
    * <span data-ttu-id="7c5e0-129">Observe que um ícone no status do trabalho indica que o trabalho agora está pronto.</span><span class="sxs-lookup"><span data-stu-id="7c5e0-129">Notice that an icon in the Job status indicates that the job is now ready.</span></span>  

