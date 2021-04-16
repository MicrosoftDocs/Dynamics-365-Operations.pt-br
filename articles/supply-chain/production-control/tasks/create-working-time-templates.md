---
title: Criar modelos de produção
description: Os modelos de horário de trabalho definem as horas de trabalho ao longo de uma semana e são usados para gerar horários de trabalho para um período.
author: sorenva
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkTimeTable, WorkTimeCopyDayDialog, WorkPeriodTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1885aba11b5c6878cc9dca615cea98b77b4df63f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811573"
---
# <a name="create-working-time-templates"></a><span data-ttu-id="86549-103">Criar modelos de produção</span><span class="sxs-lookup"><span data-stu-id="86549-103">Create working time templates</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="86549-104">Os modelos de horário de trabalho definem as horas de trabalho ao longo de uma semana e são usados para gerar horários de trabalho para um período.</span><span class="sxs-lookup"><span data-stu-id="86549-104">Working time templates define the working hours throughout a week and are used to generate working times for a period of time.</span></span> <span data-ttu-id="86549-105">Este procedimento mostra como definir um modelo de horário de trabalho usando propriedades de programação de horário de trabalho para categorizar intervalos de horário de trabalho.</span><span class="sxs-lookup"><span data-stu-id="86549-105">This procedure shows you how to define a working time template using working time scheduling properties for categorizing working time intervals.</span></span> <span data-ttu-id="86549-106">Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="86549-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="86549-107">Vá para Todas áreas de trabalho > Gerenciamento de ciclo de vida de recurso.</span><span class="sxs-lookup"><span data-stu-id="86549-107">Go to All workspaces > Resource lifecycle management.</span></span>
2. <span data-ttu-id="86549-108">Clique em Modelos de horário de trabalho.</span><span class="sxs-lookup"><span data-stu-id="86549-108">Click Working time templates.</span></span>

## <a name="create-working-time-template"></a><span data-ttu-id="86549-109">Criar modelo de horário de trabalho</span><span class="sxs-lookup"><span data-stu-id="86549-109">Create working time template</span></span>
1. <span data-ttu-id="86549-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="86549-110">Click New.</span></span>
2. <span data-ttu-id="86549-111">No campo Modelo de horário de trabalho, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="86549-111">In the Working time template field, type a value.</span></span>
3. <span data-ttu-id="86549-112">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="86549-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="86549-113">Expandir a seção Segunda-feira.</span><span class="sxs-lookup"><span data-stu-id="86549-113">Expand the Monday section.</span></span>
5. <span data-ttu-id="86549-114">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="86549-114">Click Add.</span></span>
6. <span data-ttu-id="86549-115">No campo De, insira uma hora.</span><span class="sxs-lookup"><span data-stu-id="86549-115">In the From field, enter a time.</span></span>
    * <span data-ttu-id="86549-116">Especifique a hora em que o trabalho é iniciado na manhã.</span><span class="sxs-lookup"><span data-stu-id="86549-116">Specify the time when work begins in the morning.</span></span>  
7. <span data-ttu-id="86549-117">No campo Até, insira uma hora.</span><span class="sxs-lookup"><span data-stu-id="86549-117">In the To field, enter a time.</span></span>
    * <span data-ttu-id="86549-118">Especifique a hora em que trabalhadores param para o almoço.</span><span class="sxs-lookup"><span data-stu-id="86549-118">Specify the time when workers break for lunch.</span></span>  
8. <span data-ttu-id="86549-119">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="86549-119">Click Add.</span></span>
9. <span data-ttu-id="86549-120">No campo De, insira uma hora.</span><span class="sxs-lookup"><span data-stu-id="86549-120">In the From field, enter a time.</span></span>
    * <span data-ttu-id="86549-121">Especifique a hora em que o trabalho é retomado após o almoço.</span><span class="sxs-lookup"><span data-stu-id="86549-121">Specify the time when work resumes after lunch.</span></span>  
10. <span data-ttu-id="86549-122">No campo Até, insira uma hora.</span><span class="sxs-lookup"><span data-stu-id="86549-122">In the To field, enter a time.</span></span>
    * <span data-ttu-id="86549-123">Especifique o fim do dia de trabalho.</span><span class="sxs-lookup"><span data-stu-id="86549-123">Specify the end of the work day.</span></span>  

## <a name="replicate-working-times-to-all-week-days"></a><span data-ttu-id="86549-124">Replicar horários de trabalho para todos os dias da semana</span><span class="sxs-lookup"><span data-stu-id="86549-124">Replicate working times to all week days</span></span>
1. <span data-ttu-id="86549-125">Clique em Copiar dia.</span><span class="sxs-lookup"><span data-stu-id="86549-125">Click Copy day.</span></span>
    * <span data-ttu-id="86549-126">Copie as definições de horários de trabalho de segunda-feira a terça-feira.</span><span class="sxs-lookup"><span data-stu-id="86549-126">Copy the working times definitions from Monday to Tuesday.</span></span>  
2. <span data-ttu-id="86549-127">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="86549-127">Click OK.</span></span>
3. <span data-ttu-id="86549-128">Clique em Copiar dia.</span><span class="sxs-lookup"><span data-stu-id="86549-128">Click Copy day.</span></span>
    * <span data-ttu-id="86549-129">Copie as definições de horários de trabalho de segunda-feira a quarta-feira.</span><span class="sxs-lookup"><span data-stu-id="86549-129">Copy the working times definitions from Monday to Wednesday.</span></span>  
4. <span data-ttu-id="86549-130">No campo Ao dia útil, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="86549-130">In the To weekday field, select an option.</span></span>
5. <span data-ttu-id="86549-131">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="86549-131">Click OK.</span></span>
6. <span data-ttu-id="86549-132">Clique em Copiar dia.</span><span class="sxs-lookup"><span data-stu-id="86549-132">Click Copy day.</span></span>
    * <span data-ttu-id="86549-133">Copie as definições de horários de trabalho de segunda-feira a quinta-feira.</span><span class="sxs-lookup"><span data-stu-id="86549-133">Copy the working times definitions from Monday to Thursday.</span></span>  
7. <span data-ttu-id="86549-134">No campo Ao dia útil, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="86549-134">In the To weekday field, select an option.</span></span>
8. <span data-ttu-id="86549-135">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="86549-135">Click OK.</span></span>
9. <span data-ttu-id="86549-136">Clique em Copiar dia.</span><span class="sxs-lookup"><span data-stu-id="86549-136">Click Copy day.</span></span>
    * <span data-ttu-id="86549-137">Copie as definições de horários de trabalho de segunda-feira a sexta-feira.</span><span class="sxs-lookup"><span data-stu-id="86549-137">Copy the working times definitions from Monday to Friday.</span></span>  
10. <span data-ttu-id="86549-138">No campo Ao dia útil, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="86549-138">In the To weekday field, select an option.</span></span>
11. <span data-ttu-id="86549-139">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="86549-139">Click OK.</span></span>

## <a name="define-time-slots-for-special-operations"></a><span data-ttu-id="86549-140">Definir alocações de tempo para operações especiais</span><span class="sxs-lookup"><span data-stu-id="86549-140">Define time slots for special operations</span></span>
1. <span data-ttu-id="86549-141">Expanda a seção Sexta-feira.</span><span class="sxs-lookup"><span data-stu-id="86549-141">Expand the Friday section.</span></span>
2. <span data-ttu-id="86549-142">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="86549-142">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="86549-143">No campo Propriedade, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="86549-143">In the Property field, enter or select a value.</span></span>
4. <span data-ttu-id="86549-144">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="86549-144">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="86549-145">No campo Propriedade, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="86549-145">In the Property field, enter or select a value.</span></span>

## <a name="mark-weekend-days-as-closed-for-pickup"></a><span data-ttu-id="86549-146">Marcar dias do final de semana como fechados para a retirada</span><span class="sxs-lookup"><span data-stu-id="86549-146">Mark weekend days as closed for pickup</span></span>
1. <span data-ttu-id="86549-147">Expanda a seção Sábado.</span><span class="sxs-lookup"><span data-stu-id="86549-147">Expand the Saturday section.</span></span>
2. <span data-ttu-id="86549-148">Selecione Sim no campo Fechado para retirada.</span><span class="sxs-lookup"><span data-stu-id="86549-148">Select Yes in the Closed for pickup field.</span></span>
3. <span data-ttu-id="86549-149">Expanda a seção Domingo.</span><span class="sxs-lookup"><span data-stu-id="86549-149">Expand the Sunday section.</span></span>
4. <span data-ttu-id="86549-150">Selecione Sim no campo Fechado para retirada.</span><span class="sxs-lookup"><span data-stu-id="86549-150">Select Yes in the Closed for pickup field.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]