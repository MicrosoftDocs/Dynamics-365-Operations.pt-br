--- 
title: "Criar calendário e gerar horários de trabalho"
description: "Os calendários descrevem a capacidade e os horários de trabalho dos recursos de operações."
author: kherr75
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: OpResLifeCycleManagementWorkspace, WorkCalendarTable, WorkCalendarDate
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 8a556367857890acdb926ed29518cf2f2f2b92ea
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="create-calendar-and-generate-working-times"></a><span data-ttu-id="4c51d-103">Criar calendário e gerar horários de trabalho</span><span class="sxs-lookup"><span data-stu-id="4c51d-103">Create calendar and generate working times</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4c51d-104">Os calendários descrevem a capacidade e os horários de trabalho dos recursos de operações.</span><span class="sxs-lookup"><span data-stu-id="4c51d-104">Calendars describe the capacity and working times of operations resources.</span></span> <span data-ttu-id="4c51d-105">Este procedimento ajudará a definir um calendário de trabalho com base no modelo de horário de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4c51d-105">This procedure will help you define a work calendar based on a working time template.</span></span> <span data-ttu-id="4c51d-106">Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="4c51d-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="4c51d-107">Vá para Todas áreas de trabalho > Gerenciamento de ciclo de vida de recurso.</span><span class="sxs-lookup"><span data-stu-id="4c51d-107">Go to All workspaces > Resource lifecycle management.</span></span>
2. <span data-ttu-id="4c51d-108">Clique em Calendários.</span><span class="sxs-lookup"><span data-stu-id="4c51d-108">Click Calendars.</span></span>
3. <span data-ttu-id="4c51d-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="4c51d-109">Click New.</span></span>
4. <span data-ttu-id="4c51d-110">No campo Calendário, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="4c51d-110">In the Calendar field, type a value.</span></span>
    * <span data-ttu-id="4c51d-111">Este é o ID do calendário, que é usado como uma referência ao atribuir calendários, como um recurso de operações ou um grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="4c51d-111">This is the ID of the calendar, which is used as a reference when assigning calendars, such as to an operations resource or a resource group.</span></span>  
5. <span data-ttu-id="4c51d-112">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="4c51d-112">In the Name field, type a value.</span></span>
6. <span data-ttu-id="4c51d-113">No campo Dia de trabalho padrão em horas, insira um número.</span><span class="sxs-lookup"><span data-stu-id="4c51d-113">In the Standard work day in hours field, enter a number.</span></span>
7. <span data-ttu-id="4c51d-114">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="4c51d-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="4c51d-115">Clique em Horários de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4c51d-115">Click Working times.</span></span>
9. <span data-ttu-id="4c51d-116">Clique em Compor horários de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4c51d-116">Click Compose working times.</span></span>
    * <span data-ttu-id="4c51d-117">Gera horas de trabalho para cada dia no período que você quer agendar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="4c51d-117">Generate working hours for each day in the period where you want to be able to schedule work.</span></span> <span data-ttu-id="4c51d-118">Conforme o tempo passa, você pode gerar horários de trabalho para períodos adicionais.</span><span class="sxs-lookup"><span data-stu-id="4c51d-118">As time goes by, you can generate working times for additional periods.</span></span>  
10. <span data-ttu-id="4c51d-119">No campo De data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="4c51d-119">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="4c51d-120">Esse é o primeiro dia que este calendário deve ficar aberto.</span><span class="sxs-lookup"><span data-stu-id="4c51d-120">This is the first day that this calendar must be open.</span></span>  
11. <span data-ttu-id="4c51d-121">No campo Para data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="4c51d-121">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="4c51d-122">Esse é o último dia que este calendário deve está aberto.</span><span class="sxs-lookup"><span data-stu-id="4c51d-122">This is the last day that this calendar is open.</span></span>  
12. <span data-ttu-id="4c51d-123">No campo Modelo de horário de trabalho, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="4c51d-123">In the Working time template field, enter or select a value.</span></span>
    * <span data-ttu-id="4c51d-124">O modelo de horário de trabalho define as horas de trabalho para cada dia da semana.</span><span class="sxs-lookup"><span data-stu-id="4c51d-124">The working time template defines the working hours for each day of the week.</span></span>  
13. <span data-ttu-id="4c51d-125">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4c51d-125">Click OK.</span></span>
14. <span data-ttu-id="4c51d-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4c51d-126">Close the page.</span></span>


