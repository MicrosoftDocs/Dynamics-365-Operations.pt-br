--- 
title: "Relatar como concluído para um local controlado por placa "
description: "Esta guia mostra um exemplo de tarefas do relatório de conclusão para um local que não seja controlado por placa de licença."
author: ChristianRytt
manager: AnnBe
ms.date: 06/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: dcf78f54422f8c17e4965cc5d664cd9bdbc3f440
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---
# <a name="report-as-finished-to-a-plate-controlled-location"></a><span data-ttu-id="2e05b-103">Relatar como concluído para um local controlado por placa </span><span class="sxs-lookup"><span data-stu-id="2e05b-103">Report as finished to a plate-controlled location</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2e05b-104">Esta guia mostra um exemplo de tarefas do relatório de conclusão para um local que não seja controlado por placa de licença.</span><span class="sxs-lookup"><span data-stu-id="2e05b-104">This task guide shows an example of reporting as finished to a location that isn't license plate–controlled.</span></span> <span data-ttu-id="2e05b-105">Uma diretiva de trabalho aplicável é o pré-requisito para esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="2e05b-105">An applicable work policy is the prerequisite for this task.</span></span> <span data-ttu-id="2e05b-106">Uma guia anterior da tarefa mostrou da instalação da diretiva de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2e05b-106">A previous task guide showed the setup of the work policy.</span></span> <span data-ttu-id="2e05b-107">Essa guia da tarefa requer a aplicação 7.0.1 do Dynamics AX ou posterior.</span><span class="sxs-lookup"><span data-stu-id="2e05b-107">This task guide requires Dynamics AX application 7.0.1 or later.</span></span>




## <a name="set-up-an-output-location"></a><span data-ttu-id="2e05b-108">Configurar uma localização de saída</span><span class="sxs-lookup"><span data-stu-id="2e05b-108">Set up an output location</span></span>
1. <span data-ttu-id="2e05b-109">Vá para Administração da organização > Recursos > Grupos de recursos.</span><span class="sxs-lookup"><span data-stu-id="2e05b-109">Go to Organization administration > Resources > Resource groups.</span></span>
2. <span data-ttu-id="2e05b-110">Na lista, selecione grupo de recurso "5102".</span><span class="sxs-lookup"><span data-stu-id="2e05b-110">In the list, select resource group '5102'.</span></span>
3. <span data-ttu-id="2e05b-111">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="2e05b-111">Click Edit.</span></span>
4. <span data-ttu-id="2e05b-112">No campo Depósito de saída, insira "51".</span><span class="sxs-lookup"><span data-stu-id="2e05b-112">In the Output warehouse field, enter '51'.</span></span>
5. <span data-ttu-id="2e05b-113">No campo Local de saída, insira "001".</span><span class="sxs-lookup"><span data-stu-id="2e05b-113">In the Output location field, enter '001'.</span></span>
    * <span data-ttu-id="2e05b-114">O local 001 não é um local controlado por placa de licença.</span><span class="sxs-lookup"><span data-stu-id="2e05b-114">Location 001 isn't a license plate–controlled location.</span></span> <span data-ttu-id="2e05b-115">Você pode configurar um local de saída em branco da licença não aplicável somente se uma diretiva de trabalho existir para o local.</span><span class="sxs-lookup"><span data-stu-id="2e05b-115">You can set up a non–license plate output location only if an applicable work policy exists for the location.</span></span>  

## <a name="create-a-production-order-and-report-it-as-finished"></a><span data-ttu-id="2e05b-116">Criar uma ordem de produção e relatar quando estiver concluída</span><span class="sxs-lookup"><span data-stu-id="2e05b-116">Create a production order and report it as finished</span></span>
1. <span data-ttu-id="2e05b-117">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2e05b-117">Close the page.</span></span>
2. <span data-ttu-id="2e05b-118">Vá para Controle de produção > Ordens de produção > Todas as ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="2e05b-118">Go to Production control > Production orders > All production orders.</span></span>
3. <span data-ttu-id="2e05b-119">Clique em Nova ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="2e05b-119">Click New production order.</span></span>
4. <span data-ttu-id="2e05b-120">No campo Número do item, insira "L0101".</span><span class="sxs-lookup"><span data-stu-id="2e05b-120">In the Item number field, enter 'L0101'.</span></span>
5. <span data-ttu-id="2e05b-121">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="2e05b-121">Click Create.</span></span>
6. <span data-ttu-id="2e05b-122">No Painel de Ação, clique em Ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="2e05b-122">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="2e05b-123">Clique em Estimar.</span><span class="sxs-lookup"><span data-stu-id="2e05b-123">Click Estimate.</span></span>
8. <span data-ttu-id="2e05b-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="2e05b-124">Click OK.</span></span>
9. <span data-ttu-id="2e05b-125">Clique em Iniciar.</span><span class="sxs-lookup"><span data-stu-id="2e05b-125">Click Start.</span></span>
10. <span data-ttu-id="2e05b-126">Clique na guia Geral.</span><span class="sxs-lookup"><span data-stu-id="2e05b-126">Click the General tab.</span></span>
11. <span data-ttu-id="2e05b-127">No campo Consumo automático de BOM, selecione 'Nunca'.</span><span class="sxs-lookup"><span data-stu-id="2e05b-127">In the Automatic BOM consumption field, select 'Never'.</span></span>
12. <span data-ttu-id="2e05b-128">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="2e05b-128">Click OK.</span></span>
13. <span data-ttu-id="2e05b-129">Clique em Relatório de conclusão.</span><span class="sxs-lookup"><span data-stu-id="2e05b-129">Click Report as finished.</span></span>
14. <span data-ttu-id="2e05b-130">Clique na guia Geral.</span><span class="sxs-lookup"><span data-stu-id="2e05b-130">Click the General tab.</span></span>
15. <span data-ttu-id="2e05b-131">Selecione Sim no campo Aceitar erro.</span><span class="sxs-lookup"><span data-stu-id="2e05b-131">Select Yes in the Accept error field.</span></span>
16. <span data-ttu-id="2e05b-132">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="2e05b-132">Click OK.</span></span>
17. <span data-ttu-id="2e05b-133">No Painel de Ação, clique em Depósito.</span><span class="sxs-lookup"><span data-stu-id="2e05b-133">On the Action Pane, click Warehouse.</span></span>
18. <span data-ttu-id="2e05b-134">Clique em Detalhes do trabalho.</span><span class="sxs-lookup"><span data-stu-id="2e05b-134">Click Work details.</span></span>
    * <span data-ttu-id="2e05b-135">Quando a ordem de produção foi informada como concluída, nenhum trabalho foi gerado para ser colocado de lado.</span><span class="sxs-lookup"><span data-stu-id="2e05b-135">When the production order was reported as finished, no work was generated for put-away.</span></span> <span data-ttu-id="2e05b-136">Isso ocorre porque uma diretiva de trabalho que é definida impede que o trabalho seja gerado quando o produto L0101 é relatado como concluídos no local 001.</span><span class="sxs-lookup"><span data-stu-id="2e05b-136">This occurs because a work policy is defined that prevents work from being generated when product L0101 is reported as finished to location 001.</span></span>  


