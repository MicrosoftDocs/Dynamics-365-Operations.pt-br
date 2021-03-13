---
title: Nível e descrição de serviço
description: Este tópico explica nível de serviço e descrição no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectServiceLevel, EntAssetWorkOrderStandardDescription, EntAssetWorkOrderServiceLevel, EntAssetServiceLevelLookup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8bb56e5103bd9e18e88c164cd308e55d48e64823
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019370"
---
# <a name="service-level-and-description"></a><span data-ttu-id="a89c1-103">Nível e descrição de serviço</span><span class="sxs-lookup"><span data-stu-id="a89c1-103">Service level and description</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="a89c1-104">Quando você cria uma ordem de serviço, você pode desejar definir os níveis de serviço para ela e adicionar uma descrição geral a ela.</span><span class="sxs-lookup"><span data-stu-id="a89c1-104">When you create a work order, you might want to define the service levels for it and add a general description to it.</span></span> <span data-ttu-id="a89c1-105">Você pode criar níveis de serviço da ordem de serviço na página **Níveis de serviço da ordem de serviço** e descrições na página **Descrição da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="a89c1-105">You can create work order service levels on the **Work order service levels** page and descriptions on the **Work order description** page.</span></span>

## <a name="create-a-service-level"></a><span data-ttu-id="a89c1-106">Criar um nível de serviço</span><span class="sxs-lookup"><span data-stu-id="a89c1-106">Create a service level</span></span>

1. <span data-ttu-id="a89c1-107">Selecione **Gerenciamento de Ativos** \> **Configuração** \> **Ordens de serviço** \> **Nível de serviço**.</span><span class="sxs-lookup"><span data-stu-id="a89c1-107">Select **Asset management** \> **Setup** \> **Work orders** \> **Service level**.</span></span>
2. <span data-ttu-id="a89c1-108">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="a89c1-108">Select **New**.</span></span>
3. <span data-ttu-id="a89c1-109">No campo **Nível de serviço**, insira o nível de serviço (por exemplo, um número).</span><span class="sxs-lookup"><span data-stu-id="a89c1-109">In the **Service level** field, enter the service level (for example, a number).</span></span>
4. <span data-ttu-id="a89c1-110">No campo **Nome**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="a89c1-110">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="a89c1-111">Na Guia Rápida **Ordens de serviço**, você pode definir as datas e horas de início e término.</span><span class="sxs-lookup"><span data-stu-id="a89c1-111">On the **Work orders** FastTab, you can define expected start and end dates and times.</span></span> <span data-ttu-id="a89c1-112">Os campos nessa Guia Rápida definem o período que as ordens de serviço devem ser iniciados e terminados.</span><span class="sxs-lookup"><span data-stu-id="a89c1-112">The fields on this FastTab define the period that work orders should be started and ended during.</span></span> <span data-ttu-id="a89c1-113">Eles são usados para ordens de serviço que são criadas manualmente e ordens de serviço que são criadas com base em solicitações de manutenção.</span><span class="sxs-lookup"><span data-stu-id="a89c1-113">They are used for work orders that are manually created and work orders that are created based on maintenance requests.</span></span> 

5. <span data-ttu-id="a89c1-114">No campo **Dia Inicial**, insira um número de dias para definir o período em que a ordem de serviço deve iniciar.</span><span class="sxs-lookup"><span data-stu-id="a89c1-114">In the **Start day** field, enter a number of days to define the period that the work order should start during.</span></span> <span data-ttu-id="a89c1-115">O número de dias é calculado a partir da data de criação da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="a89c1-115">The number of days is calculated from the creation date of the work order.</span></span> <span data-ttu-id="a89c1-116">Por exemplo, se a ordem de serviço começa quando é criada, insira **0**.</span><span class="sxs-lookup"><span data-stu-id="a89c1-116">For example, if the work order should start when it's created, enter **0**.</span></span> <span data-ttu-id="a89c1-117">Se a ordem de serviço começa uma semana depois de ser criada, insira **7**.</span><span class="sxs-lookup"><span data-stu-id="a89c1-117">If the work order should start within one week after it's created, enter **7**.</span></span>
6. <span data-ttu-id="a89c1-118">Para definir uma hora inicial para a ordem de serviço, além de uma data de início, defina **Definir hora inicial** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="a89c1-118">To set a start time for the work order, in addition to a start date, set the **Set start time** option to **Yes**.</span></span> <span data-ttu-id="a89c1-119">Insira a hora inicial no campo **Hora inicial**.</span><span class="sxs-lookup"><span data-stu-id="a89c1-119">Then enter the start time in the **Start time** field.</span></span> <span data-ttu-id="a89c1-120">Se você definir a opção como **Não**, a hora atual será usada.</span><span class="sxs-lookup"><span data-stu-id="a89c1-120">If you set the option to **No**, the current time of day is used.</span></span>
7. <span data-ttu-id="a89c1-121">No campo **Dia final**, insira um número de dias para definir o período em que a ordem de serviço deve terminar.</span><span class="sxs-lookup"><span data-stu-id="a89c1-121">In the **End day** field, enter a number of days to define the period that the work order should end during.</span></span> <span data-ttu-id="a89c1-122">O número de dias é calculado a partir da data de início da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="a89c1-122">The number of days is calculated from the start date of the work order.</span></span> <span data-ttu-id="a89c1-123">Por exemplo, se a ordem de serviço finalizar dentro de uma semana da data de início, insira **7**.</span><span class="sxs-lookup"><span data-stu-id="a89c1-123">For example, if the work order should end within one week of its start date, enter **7**.</span></span>
8. <span data-ttu-id="a89c1-124">Para definir uma hora final para a ordem de serviço, além de uma data de término, defina **Definir hora final** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="a89c1-124">To set an end time for the work order, in addition to an end date, set the **Set end time** option to **Yes**.</span></span> <span data-ttu-id="a89c1-125">Insira a hora final no campo **Hora final**.</span><span class="sxs-lookup"><span data-stu-id="a89c1-125">Then enter the end time in the **End time** field.</span></span> <span data-ttu-id="a89c1-126">Se você definir a opção como **Não**, a hora atual será usada.</span><span class="sxs-lookup"><span data-stu-id="a89c1-126">If you set the option to **No**, the current time of day is used.</span></span>
9. <span data-ttu-id="a89c1-127">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a89c1-127">Select **Save**.</span></span>

![Página do nível de serviço das ordens de serviço](media/19-setup-for-work-orders.png)

## <a name="create-a-description"></a><span data-ttu-id="a89c1-129">Criar uma descrição</span><span class="sxs-lookup"><span data-stu-id="a89c1-129">Create a description</span></span>

1. <span data-ttu-id="a89c1-130">Selecione **Gerenciamento de Ativos** \> **Configuração** \> **Ordens de serviço** \> **Descrições**.</span><span class="sxs-lookup"><span data-stu-id="a89c1-130">Select **Asset management** \> **Setup** \> **Work orders** \> **Descriptions**.</span></span>
2. <span data-ttu-id="a89c1-131">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="a89c1-131">Select **New**.</span></span>
3. <span data-ttu-id="a89c1-132">No campo **Descrição**, insira a descrição.</span><span class="sxs-lookup"><span data-stu-id="a89c1-132">In the **Description** field, enter the description.</span></span>
4. <span data-ttu-id="a89c1-133">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a89c1-133">Select **Save**.</span></span>
