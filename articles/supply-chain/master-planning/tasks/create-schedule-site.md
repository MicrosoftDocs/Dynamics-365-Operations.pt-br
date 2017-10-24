--- 
title: Criar uma agenda para um site
description: "Este procedimento mostra como planejar ordens de produção que ainda não foram iniciadas para um site."
author: YuyuScheller
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 775428bf84a752c03c492e764fa9ed576ab64fb8
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-schedule-for-a-site"></a><span data-ttu-id="dd842-103">Criar uma agenda para um site</span><span class="sxs-lookup"><span data-stu-id="dd842-103">Create a schedule for a site</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dd842-104">Este procedimento mostra como planejar ordens de produção que ainda não foram iniciadas para um site.</span><span class="sxs-lookup"><span data-stu-id="dd842-104">This procedure shows how to schedule production orders that are not yet started for a site.</span></span>  <span data-ttu-id="dd842-105">A empresa de dados demo USMF é usada para completar este procedimento.</span><span class="sxs-lookup"><span data-stu-id="dd842-105">The demo data company USMF is used to complete this procedure.</span></span>


## <a name="identify-production-orders-that-are-not-started"></a><span data-ttu-id="dd842-106">Identificar ordem de produção que não foram iniciadas</span><span class="sxs-lookup"><span data-stu-id="dd842-106">Identify production orders that are not started</span></span>
1. <span data-ttu-id="dd842-107">Vá para Controle de produção > Ordens de produção > Todas as ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="dd842-107">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="dd842-108">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="dd842-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="dd842-109">Por exemplo, filtre o campo Site com um valor de '1'.</span><span class="sxs-lookup"><span data-stu-id="dd842-109">For example, filter on the Site field with a value of '1'.</span></span>
    * <span data-ttu-id="dd842-110">1 representa um site em USMF.</span><span class="sxs-lookup"><span data-stu-id="dd842-110">1 represents a site in USMF.</span></span> <span data-ttu-id="dd842-111">Se você não estiver usando USMF, selecione um site em sua própria empresa.</span><span class="sxs-lookup"><span data-stu-id="dd842-111">If you are not using USMF, select a site from your own company.</span></span>  
3. <span data-ttu-id="dd842-112">Abra o filtro da coluna Status.</span><span class="sxs-lookup"><span data-stu-id="dd842-112">Open the Status column filter.</span></span>
4. <span data-ttu-id="dd842-113">Aplicar um filtro no campo "Status", com um valor de "Agendado", usando o operador de filtro "é exatamente".</span><span class="sxs-lookup"><span data-stu-id="dd842-113">Apply a filter on the "Status" field, with a value of "Scheduled", using the "is exactly" filter operator.</span></span>

## <a name="create-a-schedule"></a><span data-ttu-id="dd842-114">Criar uma agenda</span><span class="sxs-lookup"><span data-stu-id="dd842-114">Create a schedule</span></span>
1. <span data-ttu-id="dd842-115">Na lista, marque ou desmarque todas as linhas.</span><span class="sxs-lookup"><span data-stu-id="dd842-115">In the list, mark or unmark all rows.</span></span>
2. <span data-ttu-id="dd842-116">No Painel de Ação, clique em Agenda.</span><span class="sxs-lookup"><span data-stu-id="dd842-116">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="dd842-117">Clique em Agendar trabalhos.</span><span class="sxs-lookup"><span data-stu-id="dd842-117">Click Schedule jobs.</span></span>
4. <span data-ttu-id="dd842-118">No campo Direção do plano, selecione 'Voltar a partir da data de entrega'.</span><span class="sxs-lookup"><span data-stu-id="dd842-118">In the Scheduling direction field, select 'Backward from delivery date'.</span></span>
5. <span data-ttu-id="dd842-119">Selecione Não no campo Capacidade finita.</span><span class="sxs-lookup"><span data-stu-id="dd842-119">Select No in the Finite capacity field.</span></span>
6. <span data-ttu-id="dd842-120">Selecione Não no campo Material finito.</span><span class="sxs-lookup"><span data-stu-id="dd842-120">Select No in the Finite material field.</span></span>
7. <span data-ttu-id="dd842-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="dd842-121">Click OK.</span></span>
    * <span data-ttu-id="dd842-122">Isso pode levar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="dd842-122">This may take a while.</span></span>  

## <a name="view-the-result-of-scheduled-production-orders"></a><span data-ttu-id="dd842-123">Exibe o resultado das ordens de produção programadas</span><span class="sxs-lookup"><span data-stu-id="dd842-123">View the result of scheduled production orders</span></span>
1. <span data-ttu-id="dd842-124">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="dd842-124">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="dd842-125">Você pode marcar todas as linhas.</span><span class="sxs-lookup"><span data-stu-id="dd842-125">You can mark any row.</span></span>  
2. <span data-ttu-id="dd842-126">No Painel de Ação, clique em Ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="dd842-126">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="dd842-127">Clique em Todos os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="dd842-127">Click All jobs.</span></span>
    * <span data-ttu-id="dd842-128">Nessa página, você pode ver a lista de trabalho.</span><span class="sxs-lookup"><span data-stu-id="dd842-128">On this page, you can see the list of jobs.</span></span> <span data-ttu-id="dd842-129">Na guia de programação, você pode ver as datas de início e fim de um trabalho.</span><span class="sxs-lookup"><span data-stu-id="dd842-129">On the Scheduling tab, you can see the Start date and End date for a job.</span></span>  
4. <span data-ttu-id="dd842-130">Clique em Materiais.</span><span class="sxs-lookup"><span data-stu-id="dd842-130">Click Materials.</span></span>
    * <span data-ttu-id="dd842-131">Nessa página, você pode ver o consumo de material previsto para as operações na ordem de produção e de estoque disponível atualmente.</span><span class="sxs-lookup"><span data-stu-id="dd842-131">On this page, you can see the estimated material consumption for the operations on the production order and the current available inventory.</span></span>  


