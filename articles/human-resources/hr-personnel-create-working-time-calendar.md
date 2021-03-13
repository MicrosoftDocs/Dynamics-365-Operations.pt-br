---
title: Criar calendários e gerar horários de trabalho
description: Os calendários descrevem a capacidade e os horários de trabalho dos recursos de operações. Este artigo explica como definir um calendário de trabalho com base no modelo de horário de trabalho.
author: andreabichsel
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkCalendarTable, WorkCalendarDate, HcmPersonnelManagementWorkspace, WrkCtrGroupDateCalendar, WrkCtrDateCalendar
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2fd297d9368472138fbe2db5a2133719cb1a9f18
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "5130292"
---
# <a name="create-calendars-and-generate-working-times"></a><span data-ttu-id="bb2e2-104">Criar calendários e gerar horários de trabalho</span><span class="sxs-lookup"><span data-stu-id="bb2e2-104">Create calendars and generate working times</span></span>



<span data-ttu-id="bb2e2-105">Os calendários descrevem a capacidade e os horários de trabalho dos recursos de operações.</span><span class="sxs-lookup"><span data-stu-id="bb2e2-105">Calendars describe the capacity and working times of operations resources.</span></span> <span data-ttu-id="bb2e2-106">Este artigo explica como definir um calendário de trabalho com base no modelo de horário de trabalho.</span><span class="sxs-lookup"><span data-stu-id="bb2e2-106">This article explains how to define a work calendar based on a working time template.</span></span> <span data-ttu-id="bb2e2-107">Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="bb2e2-107">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="bb2e2-108">Na home page, selecione **Gerenciamento do ciclo de vida de recurso**.</span><span class="sxs-lookup"><span data-stu-id="bb2e2-108">On the home page, select **Resource lifecycle management**.</span></span>
2. <span data-ttu-id="bb2e2-109">Selecione **Calendários**.</span><span class="sxs-lookup"><span data-stu-id="bb2e2-109">Select **Calendars**.</span></span>
3. <span data-ttu-id="bb2e2-110">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="bb2e2-110">Select **New**.</span></span>
4. <span data-ttu-id="bb2e2-111">No campo **Calendário**, classifique o seu calendário.</span><span class="sxs-lookup"><span data-stu-id="bb2e2-111">In the **Calendar** field, classify your calendar.</span></span> <span data-ttu-id="bb2e2-112">Este é o ID do calendário, que é usado como uma referência ao atribuir calendários, como um recurso de operações ou um grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="bb2e2-112">This is the ID of the calendar, which is used as a reference when assigning calendars, such as to an operations resource or a resource group.</span></span>  
5. <span data-ttu-id="bb2e2-113">No campo **Nome**, nomeie seu calendário.</span><span class="sxs-lookup"><span data-stu-id="bb2e2-113">In the **Name** field, name your calendar.</span></span>
6. <span data-ttu-id="bb2e2-114">No campo **Dia de trabalho padrão em horas**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="bb2e2-114">In the **Standard work day in hours** field, enter a number.</span></span>
7. <span data-ttu-id="bb2e2-115">Verifique se a linha está selecionada e marque **Horários de trabalho** no painel de Ação.</span><span class="sxs-lookup"><span data-stu-id="bb2e2-115">Make sure the row is selected, then select **Working times** from the Action Pane.</span></span>
8. <span data-ttu-id="bb2e2-116">Selecione **Compor horários de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="bb2e2-116">Select **Compose working times**.</span></span> <span data-ttu-id="bb2e2-117">Gera horas de trabalho para cada dia no período que você quer agendar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="bb2e2-117">Generate working hours for each day in the period where you want to be able to schedule work.</span></span> <span data-ttu-id="bb2e2-118">Conforme o tempo passa, você pode gerar horários de trabalho para períodos adicionais.</span><span class="sxs-lookup"><span data-stu-id="bb2e2-118">As time goes by, you can generate working times for additional periods.</span></span>  
9. <span data-ttu-id="bb2e2-119">No campo **Data inicial**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="bb2e2-119">In the **From date** field, enter a date.</span></span> <span data-ttu-id="bb2e2-120">Esse é o primeiro dia que este calendário deve ficar aberto.</span><span class="sxs-lookup"><span data-stu-id="bb2e2-120">This is the first day that this calendar must be open.</span></span>  
10. <span data-ttu-id="bb2e2-121">No campo **Data final**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="bb2e2-121">In the **To date field**, enter a date.</span></span> <span data-ttu-id="bb2e2-122">Esse é o último dia que este calendário deve está aberto.</span><span class="sxs-lookup"><span data-stu-id="bb2e2-122">This is the last day that this calendar is open.</span></span>  
11. <span data-ttu-id="bb2e2-123">No campo **Modelo de horário de trabalho**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="bb2e2-123">In the **Working time template** field, enter or select a value.</span></span> <span data-ttu-id="bb2e2-124">O modelo de horário de trabalho define as horas de trabalho para cada dia da semana.</span><span class="sxs-lookup"><span data-stu-id="bb2e2-124">The working time template defines the working hours for each day of the week.</span></span>  
12. <span data-ttu-id="bb2e2-125">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb2e2-125">Select **OK**.</span></span>
13. <span data-ttu-id="bb2e2-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="bb2e2-126">Close the page.</span></span>

