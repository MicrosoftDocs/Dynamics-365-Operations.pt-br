---
title: Criar um plano para um site
description: O planejador de produção calcula os requisitos de capacidade e de material para a produção de um item específico.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqTransPOUrgentFormPart, SysQueryForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13238818de10596de34eaf9d8cd7d55562a307eb
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3150300"
---
# <a name="create-a-plan-for-a-site"></a><span data-ttu-id="202e7-103">Criar um plano para um site</span><span class="sxs-lookup"><span data-stu-id="202e7-103">Create a plan for a site</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="202e7-104">O planejador de produção calcula os requisitos de capacidade e de material para a produção de um item específico.</span><span class="sxs-lookup"><span data-stu-id="202e7-104">The production planner calculates the material and capacity requirements for the production of a specific item.</span></span> <span data-ttu-id="202e7-105">Depois que as indicações de fornecimento são criadas, ele encontra as ordens no site para o qual ele está planejando e confirma ordens a partir de ordens urgentes.</span><span class="sxs-lookup"><span data-stu-id="202e7-105">After the sourcing suggestions are created, he finds the orders at the site for which he is planning and firms the orders, starting from the urgent ones.</span></span> <span data-ttu-id="202e7-106">As ordens mais urgentes são aquelas que precisam ser confirmadas na data atual.</span><span class="sxs-lookup"><span data-stu-id="202e7-106">The most urgent orders are the ones that need to be firmed on the current date.</span></span> <span data-ttu-id="202e7-107">Use a empresa USMF de dados de demonstração para executar essas tarefas.</span><span class="sxs-lookup"><span data-stu-id="202e7-107">Use the demo data company USMF to perform these tasks.</span></span>


## <a name="create-a-materials-and-capacity-plan-for-an-item"></a><span data-ttu-id="202e7-108">Criar materiais e planejamento de capacidade para um item</span><span class="sxs-lookup"><span data-stu-id="202e7-108">Create a materials and capacity plan for an item</span></span>
1. <span data-ttu-id="202e7-109">Clique em Planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="202e7-109">Click Master planning.</span></span>
    * <span data-ttu-id="202e7-110">Você precisa navegar para o Painel padrão.</span><span class="sxs-lookup"><span data-stu-id="202e7-110">You need to navigate to the default Dashboard.</span></span>  
2. <span data-ttu-id="202e7-111">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="202e7-111">Click Run.</span></span>
3. <span data-ttu-id="202e7-112">Expanda os Registros para incluir a seção.</span><span class="sxs-lookup"><span data-stu-id="202e7-112">Expand the Records to include section.</span></span>
4. <span data-ttu-id="202e7-113">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="202e7-113">Click Filter.</span></span>
5. <span data-ttu-id="202e7-114">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="202e7-114">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="202e7-115">No campo Critérios, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="202e7-115">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="202e7-116">Exemplo: D0001</span><span class="sxs-lookup"><span data-stu-id="202e7-116">Example: D0001</span></span>  
7. <span data-ttu-id="202e7-117">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="202e7-117">Click OK.</span></span>
8. <span data-ttu-id="202e7-118">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="202e7-118">Click OK.</span></span>
    * <span data-ttu-id="202e7-119">Isso pode levar alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="202e7-119">This may take a few minutes.</span></span>  
9. <span data-ttu-id="202e7-120">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="202e7-120">Refresh the page.</span></span>

## <a name="identify-the-urgent-planned-orders-for-the-item"></a><span data-ttu-id="202e7-121">Identificar as ordens urgentes planejadas para o item</span><span class="sxs-lookup"><span data-stu-id="202e7-121">Identify the urgent planned orders for the item</span></span>
1. <span data-ttu-id="202e7-122">Abra o filtro na coluna do número do item.</span><span class="sxs-lookup"><span data-stu-id="202e7-122">Open Item number column filter.</span></span>
2. <span data-ttu-id="202e7-123">Aplicar um filtro no campo "Número de item", com um valor de "D0001", usando o operador de filtro "começa com".</span><span class="sxs-lookup"><span data-stu-id="202e7-123">Apply a filter on the "Item number" field, with a value of "D0001", using the "begins with" filter operator.</span></span>
3. <span data-ttu-id="202e7-124">Filtro de coluna de data Abrir ordem.</span><span class="sxs-lookup"><span data-stu-id="202e7-124">Open Order date column filter.</span></span>
4. <span data-ttu-id="202e7-125">Aplicar um filtro no campo "Data da ordem", com um valor de data atual, usando o operador de filtro "é exatamente".</span><span class="sxs-lookup"><span data-stu-id="202e7-125">Apply a filter on the "Order date" field, with a value of current date, using the "is exactly" filter operator.</span></span>

## <a name="firm-all-the-urgent-orders-for-the-item"></a><span data-ttu-id="202e7-126">Confirmar as ordens urgentes para o item</span><span class="sxs-lookup"><span data-stu-id="202e7-126">Firm all the urgent orders for the item</span></span>
1. <span data-ttu-id="202e7-127">Na lista, marque ou desmarque todas as linhas.</span><span class="sxs-lookup"><span data-stu-id="202e7-127">In the list, mark or unmark all rows.</span></span>
2. <span data-ttu-id="202e7-128">Clique em Confirmar.</span><span class="sxs-lookup"><span data-stu-id="202e7-128">Click Firm.</span></span>
3. <span data-ttu-id="202e7-129">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="202e7-129">Click OK.</span></span>

