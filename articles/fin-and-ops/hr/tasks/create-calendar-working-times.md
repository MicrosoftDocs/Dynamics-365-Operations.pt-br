---
title: Criar calendários e gerar horários de trabalho
description: Os calendários descrevem a capacidade e os horários de trabalho dos recursos de operações. Este tópico explica como definir um calendário de trabalho com base no modelo de horário de trabalho.
author: andreabichsel
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkCalendarTable, WorkCalendarDate
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 50b81ae228d9aee4111ce8d161508d5ed1af4f27
ms.sourcegitcommit: 81e6eaa2178fda7f7d086ad978f4c891bc4ec10a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2019
ms.locfileid: "1738987"
---
# <a name="create-calendar-and-generate-working-times"></a><span data-ttu-id="38865-104">Criar calendário e gerar horários de trabalho</span><span class="sxs-lookup"><span data-stu-id="38865-104">Create calendar and generate working times</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="38865-105">Os calendários descrevem a capacidade e os horários de trabalho dos recursos de operações.</span><span class="sxs-lookup"><span data-stu-id="38865-105">Calendars describe the capacity and working times of operations resources.</span></span> <span data-ttu-id="38865-106">Este tópico explica como definir um calendário de trabalho com base no modelo de horário de trabalho.</span><span class="sxs-lookup"><span data-stu-id="38865-106">This topic explains how to define a work calendar based on a working time template.</span></span> <span data-ttu-id="38865-107">Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="38865-107">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="38865-108">Na home page, selecione **Gerenciamento do ciclo de vida de recurso**.</span><span class="sxs-lookup"><span data-stu-id="38865-108">On the home page, select **Resource lifecycle management**.</span></span>
2. <span data-ttu-id="38865-109">Selecione **Calendários**.</span><span class="sxs-lookup"><span data-stu-id="38865-109">Select **Calendars**.</span></span>
3. <span data-ttu-id="38865-110">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="38865-110">Select **New**.</span></span>
4. <span data-ttu-id="38865-111">No campo **Calendário**, classifique o seu calendário.</span><span class="sxs-lookup"><span data-stu-id="38865-111">In the **Calendar** field, classify your calendar.</span></span> <span data-ttu-id="38865-112">Este é o ID do calendário, que é usado como uma referência ao atribuir calendários, como um recurso de operações ou um grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="38865-112">This is the ID of the calendar, which is used as a reference when assigning calendars, such as to an operations resource or a resource group.</span></span>  
5. <span data-ttu-id="38865-113">No campo **Nome**, nomeie seu calendário.</span><span class="sxs-lookup"><span data-stu-id="38865-113">In the **Name** field, name your calendar.</span></span>
6. <span data-ttu-id="38865-114">No campo **Dia de trabalho padrão em horas**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="38865-114">In the **Standard work day in hours** field, enter a number.</span></span>
7. <span data-ttu-id="38865-115">Verifique se a linha está selecionada e marque **Horários de trabalho** no painel de Ação.</span><span class="sxs-lookup"><span data-stu-id="38865-115">Make sure the row is selected, then select **Working times** from the Action Pane.</span></span>
8. <span data-ttu-id="38865-116">Selecione **Compor horários de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="38865-116">Select **Compose working times**.</span></span> <span data-ttu-id="38865-117">Gera horas de trabalho para cada dia no período que você quer agendar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="38865-117">Generate working hours for each day in the period where you want to be able to schedule work.</span></span> <span data-ttu-id="38865-118">Conforme o tempo passa, você pode gerar horários de trabalho para períodos adicionais.</span><span class="sxs-lookup"><span data-stu-id="38865-118">As time goes by, you can generate working times for additional periods.</span></span>  
9. <span data-ttu-id="38865-119">No campo **Data inicial**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="38865-119">In the **From date** field, enter a date.</span></span> <span data-ttu-id="38865-120">Esse é o primeiro dia que este calendário deve ficar aberto.</span><span class="sxs-lookup"><span data-stu-id="38865-120">This is the first day that this calendar must be open.</span></span>  
10. <span data-ttu-id="38865-121">No campo **Data final**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="38865-121">In the **To date field**, enter a date.</span></span> <span data-ttu-id="38865-122">Esse é o último dia que este calendário deve está aberto.</span><span class="sxs-lookup"><span data-stu-id="38865-122">This is the last day that this calendar is open.</span></span>  
11. <span data-ttu-id="38865-123">No campo **Modelo de horário de trabalho**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="38865-123">In the **Working time template** field, enter or select a value.</span></span> <span data-ttu-id="38865-124">O modelo de horário de trabalho define as horas de trabalho para cada dia da semana.</span><span class="sxs-lookup"><span data-stu-id="38865-124">The working time template defines the working hours for each day of the week.</span></span>  
12. <span data-ttu-id="38865-125">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="38865-125">Select **OK**.</span></span>
13. <span data-ttu-id="38865-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="38865-126">Close the page.</span></span>

