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
ms.openlocfilehash: ed1981b7c1427c902f237f0aa95f63e89bc345ab
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920919"
---
# <a name="create-working-time-templates"></a><span data-ttu-id="ea4cd-103">Criar modelos de produção</span><span class="sxs-lookup"><span data-stu-id="ea4cd-103">Create working time templates</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ea4cd-104">Os modelos de horário de trabalho definem as horas de trabalho ao longo de uma semana e são usados para gerar horários de trabalho para um período.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-104">Working time templates define the working hours throughout a week and are used to generate working times for a period of time.</span></span> <span data-ttu-id="ea4cd-105">Este procedimento mostra como definir um modelo de horário de trabalho usando propriedades de programação de horário de trabalho para categorizar intervalos de horário de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-105">This procedure shows you how to define a working time template using working time scheduling properties for categorizing working time intervals.</span></span> <span data-ttu-id="ea4cd-106">Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="ea4cd-107">Vá para **Espaços de trabalho > Gerenciamento de ciclo de vida de recurso**.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-107">Go to **Workspaces > Resource lifecycle management**.</span></span>
1. <span data-ttu-id="ea4cd-108">Selecione **Modelos de horário de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-108">Select **Working time templates**.</span></span>

## <a name="create-working-time-template"></a><span data-ttu-id="ea4cd-109">Criar modelo de horário de trabalho</span><span class="sxs-lookup"><span data-stu-id="ea4cd-109">Create working time template</span></span>

1. <span data-ttu-id="ea4cd-110">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-110">Select **New**.</span></span>
1. <span data-ttu-id="ea4cd-111">No campo **Modelo de horário de trabalho**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-111">In the **Working time template** field, type a value.</span></span>
1. <span data-ttu-id="ea4cd-112">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-112">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="ea4cd-113">Expanda a seção **Segunda-feira**.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-113">Expand the **Monday** section.</span></span>
1. <span data-ttu-id="ea4cd-114">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-114">Select **Add**.</span></span>
1. <span data-ttu-id="ea4cd-115">No campo **De**, digite um horário.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-115">In the **From** field, enter a time.</span></span>
    * <span data-ttu-id="ea4cd-116">Especifique a hora em que o trabalho é iniciado na manhã.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-116">Specify the time when work begins in the morning.</span></span>  
1. <span data-ttu-id="ea4cd-117">No campo **Até**, digite um horário.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-117">In the **To** field, enter a time.</span></span>
    * <span data-ttu-id="ea4cd-118">Especifique a hora em que trabalhadores param para o almoço.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-118">Specify the time when workers break for lunch.</span></span>  
1. <span data-ttu-id="ea4cd-119">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-119">Select **Add**.</span></span>
1. <span data-ttu-id="ea4cd-120">No campo **De**, digite um horário.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-120">In the **From** field, enter a time.</span></span>
    * <span data-ttu-id="ea4cd-121">Especifique a hora em que o trabalho é retomado após o almoço.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-121">Specify the time when work resumes after lunch.</span></span>  
1. <span data-ttu-id="ea4cd-122">No campo **Até**, digite um horário.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-122">In the **To** field, enter a time.</span></span>
    * <span data-ttu-id="ea4cd-123">Especifique o fim do dia de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-123">Specify the end of the work day.</span></span>  

## <a name="replicate-working-times-to-all-week-days"></a><span data-ttu-id="ea4cd-124">Replicar horários de trabalho para todos os dias da semana</span><span class="sxs-lookup"><span data-stu-id="ea4cd-124">Replicate working times to all week days</span></span>

1. <span data-ttu-id="ea4cd-125">Selecione **Copiar dia**.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-125">Select **Copy day**.</span></span>
    * <span data-ttu-id="ea4cd-126">Copie as definições de horários de trabalho de segunda-feira a terça-feira.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-126">Copy the working times definitions from Monday to Tuesday.</span></span>  
1. <span data-ttu-id="ea4cd-127">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-127">Select **OK**.</span></span>
1. <span data-ttu-id="ea4cd-128">Selecione **Copiar dia**.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-128">Select **Copy day**.</span></span>
    * <span data-ttu-id="ea4cd-129">Copie as definições de horários de trabalho de segunda-feira a quarta-feira.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-129">Copy the working times definitions from Monday to Wednesday.</span></span>  
1. <span data-ttu-id="ea4cd-130">No campo **Ao dia útil**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-130">In the **To weekday** field, select an option.</span></span>
1. <span data-ttu-id="ea4cd-131">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-131">Select **OK**.</span></span>
1. <span data-ttu-id="ea4cd-132">Selecione **Copiar dia**.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-132">Select **Copy day**.</span></span>
    * <span data-ttu-id="ea4cd-133">Copie as definições de horários de trabalho de segunda-feira a quinta-feira.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-133">Copy the working times definitions from Monday to Thursday.</span></span>  
1. <span data-ttu-id="ea4cd-134">No campo **Ao dia útil**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-134">In the **To weekday** field, select an option.</span></span>
1. <span data-ttu-id="ea4cd-135">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-135">Select **OK**.</span></span>
1. <span data-ttu-id="ea4cd-136">Selecione **Copiar dia**.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-136">Select **Copy day**.</span></span>
    * <span data-ttu-id="ea4cd-137">Copie as definições de horários de trabalho de segunda-feira a sexta-feira.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-137">Copy the working times definitions from Monday to Friday.</span></span>  
1. <span data-ttu-id="ea4cd-138">No campo **Ao dia útil**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-138">In the **To weekday** field, select an option.</span></span>
1. <span data-ttu-id="ea4cd-139">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-139">Select **OK**.</span></span>

## <a name="define-time-slots-for-special-operations"></a><span data-ttu-id="ea4cd-140">Definir alocações de tempo para operações especiais</span><span class="sxs-lookup"><span data-stu-id="ea4cd-140">Define time slots for special operations</span></span>

1. <span data-ttu-id="ea4cd-141">Expanda a seção **Sexta-feira**.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-141">Expand the **Friday** section.</span></span>
1. <span data-ttu-id="ea4cd-142">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-142">In the list, find and select the desired record.</span></span>
1. <span data-ttu-id="ea4cd-143">No campo **Propriedade** insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-143">In the **Property** field, enter or select a value.</span></span>
1. <span data-ttu-id="ea4cd-144">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-144">In the list, find and select the desired record.</span></span>
1. <span data-ttu-id="ea4cd-145">No campo **Propriedade** insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-145">In the **Property** field, enter or select a value.</span></span>

## <a name="mark-weekend-days-as-closed-for-pickup"></a><span data-ttu-id="ea4cd-146">Marcar dias do final de semana como fechados para a retirada</span><span class="sxs-lookup"><span data-stu-id="ea4cd-146">Mark weekend days as closed for pickup</span></span>

1. <span data-ttu-id="ea4cd-147">Expanda a seção **Sábado**.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-147">Expand the **Saturday** section.</span></span>
1. <span data-ttu-id="ea4cd-148">Selecione *Sim* no campo **Fechado para retirada**.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-148">Select *Yes* in the **Closed for pickup** field.</span></span>
1. <span data-ttu-id="ea4cd-149">Expanda a seção **Domingo**.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-149">Expand the **Sunday** section.</span></span>
1. <span data-ttu-id="ea4cd-150">Selecione *Sim* no campo **Fechado para retirada**.</span><span class="sxs-lookup"><span data-stu-id="ea4cd-150">Select *Yes* in the **Closed for pickup** field.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]