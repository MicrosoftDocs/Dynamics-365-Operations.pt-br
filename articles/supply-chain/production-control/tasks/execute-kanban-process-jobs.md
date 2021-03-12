---
title: Executar trabalhos do processo kanban
description: Esse procedimento se concentra em executar trabalhos de processo do kanban.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9da49ae17d6c25166f6b0e05e3c45fc991c9a54d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994145"
---
# <a name="execute-kanban-process-jobs"></a><span data-ttu-id="8d859-103">Executar trabalhos do processo kanban</span><span class="sxs-lookup"><span data-stu-id="8d859-103">Execute kanban process jobs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8d859-104">Esse procedimento se concentra em executar trabalhos de processo do kanban.</span><span class="sxs-lookup"><span data-stu-id="8d859-104">This procedure focuses on executing kanban process jobs.</span></span> <span data-ttu-id="8d859-105">O primeiro trabalho é preenchido com a quantidade prevista e não têm erros.</span><span class="sxs-lookup"><span data-stu-id="8d859-105">The first job is completed with the expected quantity and has no errors.</span></span> <span data-ttu-id="8d859-106">O segundo trabalho é preenchido com erros.</span><span class="sxs-lookup"><span data-stu-id="8d859-106">The second job is completed with errors.</span></span> <span data-ttu-id="8d859-107">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="8d859-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="8d859-108">Esse procedimento é destinado ao operador da máquina.</span><span class="sxs-lookup"><span data-stu-id="8d859-108">This procedure is intended for the machine operator.</span></span>


## <a name="select-a-kanban-job"></a><span data-ttu-id="8d859-109">Selecionar trabalho kanban</span><span class="sxs-lookup"><span data-stu-id="8d859-109">Select a kanban job</span></span>
1. <span data-ttu-id="8d859-110">Vá para Controle de produção > Kanban > Quadro Kanban para trabalhos de processo.</span><span class="sxs-lookup"><span data-stu-id="8d859-110">Go to Production control > Kanban > Kanban board for process jobs.</span></span>
2. <span data-ttu-id="8d859-111">No campo Célula de trabalho, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8d859-111">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="8d859-112">Clique na linha com grupo de recursos 1250.</span><span class="sxs-lookup"><span data-stu-id="8d859-112">Click the row with resource group 1250.</span></span> <span data-ttu-id="8d859-113">Isso filtra a Lista de trabalhos para exibir somente os trabalhos para a célula de trabalho 1250.</span><span class="sxs-lookup"><span data-stu-id="8d859-113">This filters the Jobs list to display only the jobs for work cell 1250.</span></span>
    * <span data-ttu-id="8d859-114">Marque a linha que tem o status do trabalho planejado.</span><span class="sxs-lookup"><span data-stu-id="8d859-114">Mark the row that has the Planned job status.</span></span>  

## <a name="complete-a-job-with-expected-quantity"></a><span data-ttu-id="8d859-115">Execute um trabalho com quantidade prevista</span><span class="sxs-lookup"><span data-stu-id="8d859-115">Complete a job with expected quantity</span></span>
1. <span data-ttu-id="8d859-116">Expandir ou recolher a seção Detalhes.</span><span class="sxs-lookup"><span data-stu-id="8d859-116">Expand or collapse the Details section.</span></span>
    * <span data-ttu-id="8d859-117">Esta seção exibe informações importantes sobre o número do cartão, o número do item, a quantidade encomendada, e o nome da atividade.</span><span class="sxs-lookup"><span data-stu-id="8d859-117">This section displays important information about card number, item number, quantity ordered, and activity name.</span></span>  
2. <span data-ttu-id="8d859-118">Expanda ou recolha a seção Instruções de produção.</span><span class="sxs-lookup"><span data-stu-id="8d859-118">Expand or collapse the Production instructions section.</span></span>
    * <span data-ttu-id="8d859-119">Esta seção exibe instruções de produção da atividade.</span><span class="sxs-lookup"><span data-stu-id="8d859-119">This section displays production instructions for the activity.</span></span> <span data-ttu-id="8d859-120">As instruções podem ser texto, imagens, desenhos e outros documentos.</span><span class="sxs-lookup"><span data-stu-id="8d859-120">The instructions can be text, pictures, drawings, and other documents.</span></span>  
3. <span data-ttu-id="8d859-121">Clique em Iniciar.</span><span class="sxs-lookup"><span data-stu-id="8d859-121">Click Start.</span></span>
    * <span data-ttu-id="8d859-122">Selecione um trabalho que não esteja concluído.</span><span class="sxs-lookup"><span data-stu-id="8d859-122">Select a job that is not completed.</span></span> <span data-ttu-id="8d859-123">Use os ícones de status no campo status do trabalho para exibir o status do trabalho.</span><span class="sxs-lookup"><span data-stu-id="8d859-123">Use status icons in the Job status field to view job status.</span></span>      
4. <span data-ttu-id="8d859-124">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="8d859-124">Click Complete.</span></span>
    * <span data-ttu-id="8d859-125">Os trabalhos são preenchidos com a qualidade esperada.</span><span class="sxs-lookup"><span data-stu-id="8d859-125">The job is completed with the expected quality.</span></span>  

## <a name="complete-a-job-with-errors"></a><span data-ttu-id="8d859-126">Execute um trabalho com erros</span><span class="sxs-lookup"><span data-stu-id="8d859-126">Complete a job with errors</span></span>
1. <span data-ttu-id="8d859-127">Clique em Iniciar.</span><span class="sxs-lookup"><span data-stu-id="8d859-127">Click Start.</span></span>
    * <span data-ttu-id="8d859-128">Quando um trabalho é concluído, o próximo trabalho na lista é automaticamente selecionado.</span><span class="sxs-lookup"><span data-stu-id="8d859-128">When a job is completed, the next job on the list is selected automatically.</span></span> <span data-ttu-id="8d859-129">Por esse motivo você não precisará selecionar um trabalho antes de clicar em Início.</span><span class="sxs-lookup"><span data-stu-id="8d859-129">This is why you don't need to select a job before you click Start.</span></span>  
2. <span data-ttu-id="8d859-130">No painel de Ação, clique em Fabricar.</span><span class="sxs-lookup"><span data-stu-id="8d859-130">On the Action Pane, click Manufacture.</span></span>
3. <span data-ttu-id="8d859-131">Clique em Concluir (detalhes).</span><span class="sxs-lookup"><span data-stu-id="8d859-131">Click Complete (details).</span></span>
4. <span data-ttu-id="8d859-132">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="8d859-132">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="8d859-133">No campo Quantidade de erro, insira um número.</span><span class="sxs-lookup"><span data-stu-id="8d859-133">In the Error quantity field, enter a number.</span></span>
6. <span data-ttu-id="8d859-134">No campo Quantidade de mercadoria, insira um número.</span><span class="sxs-lookup"><span data-stu-id="8d859-134">In the Good quantity field, enter a number.</span></span>
7. <span data-ttu-id="8d859-135">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="8d859-135">Click OK.</span></span>

