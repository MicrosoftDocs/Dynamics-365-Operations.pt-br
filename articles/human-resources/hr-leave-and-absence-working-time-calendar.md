---
title: Criar um calendário de horário de trabalho
description: Defina um calendário de horário de trabalho, feriados e horário não comercial no Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 641f66c75875cfba51af3753223a070d7cb7dc50
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008129"
---
# <a name="create-a-working-time-calendar"></a><span data-ttu-id="93a5c-103">Criar um calendário de horário de trabalho</span><span class="sxs-lookup"><span data-stu-id="93a5c-103">Create a working time calendar</span></span>

<span data-ttu-id="93a5c-104">Um calendário de horário de trabalho no Dynamics 365 Human Resources mostra os dias e as horas em que os funcionários trabalham na sua organização.</span><span class="sxs-lookup"><span data-stu-id="93a5c-104">A working time calendar in Dynamics 365 Human Resources shows the days and hours that employees work in your organization.</span></span> <span data-ttu-id="93a5c-105">Quando um funcionário envia uma solicitação de folga, ele não precisa se preocupar com feriados e recessos.</span><span class="sxs-lookup"><span data-stu-id="93a5c-105">When an employee submits a time-off request, they don't have to worry about holidays and closures.</span></span>

<span data-ttu-id="93a5c-106">Para simplificar as solicitações de folga, configure estes itens na organização:</span><span class="sxs-lookup"><span data-stu-id="93a5c-106">To streamline time-off requests, configure these items for your organization:</span></span>

- <span data-ttu-id="93a5c-107">Calendário de horário de trabalho</span><span class="sxs-lookup"><span data-stu-id="93a5c-107">Working time calendar</span></span>
- <span data-ttu-id="93a5c-108">Feriados e recessos</span><span class="sxs-lookup"><span data-stu-id="93a5c-108">Holidays and closures</span></span>
- <span data-ttu-id="93a5c-109">Horário não comercial</span><span class="sxs-lookup"><span data-stu-id="93a5c-109">Non-work time</span></span>

<span data-ttu-id="93a5c-110">Você poderá adicionar os dois últimos itens enquanto estiver configurando um calendário de horário de trabalho.</span><span class="sxs-lookup"><span data-stu-id="93a5c-110">You can add the last two items while you're setting up a working time calendar.</span></span> <span data-ttu-id="93a5c-111">Você também pode configurá-los ou atualizá-los separadamente.</span><span class="sxs-lookup"><span data-stu-id="93a5c-111">You can also configure or update them separately.</span></span>

## <a name="set-up-a-working-time-calendar"></a><span data-ttu-id="93a5c-112">Configure um calendário de horário de trabalho</span><span class="sxs-lookup"><span data-stu-id="93a5c-112">Set up a working time calendar</span></span>

<span data-ttu-id="93a5c-113">Configure pelo menos um calendário de horário de trabalho que mostre os dias e as horas de operação.</span><span class="sxs-lookup"><span data-stu-id="93a5c-113">Set up at least one working time calendar that shows your days and hours of operation.</span></span> <span data-ttu-id="93a5c-114">Se você tiver locais em vários países e regiões, talvez queira configurar um calendário de produção para cada área.</span><span class="sxs-lookup"><span data-stu-id="93a5c-114">If you have locations in multiple countries and regions, you might want to set up a working time calendar for each area.</span></span>

1. <span data-ttu-id="93a5c-115">Na página **Administração da organização**, selecione **Calendários**.</span><span class="sxs-lookup"><span data-stu-id="93a5c-115">On the **Organization administration** page, select **Calendars**.</span></span>

2. <span data-ttu-id="93a5c-116">Selecione **Novo** e digite um nome e uma descrição para seu calendário.</span><span class="sxs-lookup"><span data-stu-id="93a5c-116">Select **New** and enter a name and description for your calendar.</span></span>

3. <span data-ttu-id="93a5c-117">Em **Opções de geração**, selecione os dias de trabalho da sua organização e insira os horários de trabalho.</span><span class="sxs-lookup"><span data-stu-id="93a5c-117">Under **Generation options**, select the work days for your organization and enter work times.</span></span> 
   - <span data-ttu-id="93a5c-118">Para adicionar um feriado ou um recesso, selecione o botão **Adicionar** ao lado de **Feriados e recessos**.</span><span class="sxs-lookup"><span data-stu-id="93a5c-118">To add a holiday or closure, select the **Add** button next to **Holidays and closures**.</span></span>
   - <span data-ttu-id="93a5c-119">Para adicionar um período não útil, como almoços ou pausas, selecione **Adicionar** em **HORÁRIO NÃO COMERCIAL** e insira o nome e o intervalo de tempo.</span><span class="sxs-lookup"><span data-stu-id="93a5c-119">To add non-work time, like lunches or breaks, select **Add** under **NON-WORK TIME** and enter the name and time range.</span></span>

4. <span data-ttu-id="93a5c-120">Em **Dias** , selecione **Gerar** para gerar os dias no calendário.</span><span class="sxs-lookup"><span data-stu-id="93a5c-120">Under **Days**, select **Generate** to generate the days in your calendar.</span></span> <span data-ttu-id="93a5c-121">Insira o intervalo de datas para o calendário e selecione **Gerar dias**.</span><span class="sxs-lookup"><span data-stu-id="93a5c-121">Enter the date range for your calendar and then select **Generate days**.</span></span>

5. <span data-ttu-id="93a5c-122">Para adicionar agendas de trabalho, em **Agenda de trabalho**, selecione **Adicionar** e insira os horários de cada plano de trabalho.</span><span class="sxs-lookup"><span data-stu-id="93a5c-122">To add work schedules, under **Work schedule**, select **Add** and then enter the times for each work schedule.</span></span>

## <a name="configure-holidays-and-closures"></a><span data-ttu-id="93a5c-123">Configurar feriados e recessos</span><span class="sxs-lookup"><span data-stu-id="93a5c-123">Configure holidays and closures</span></span>

<span data-ttu-id="93a5c-124">Você pode adicionar ou alterar feriados e recessos separadamente de um calendário de horário de trabalho.</span><span class="sxs-lookup"><span data-stu-id="93a5c-124">You can add or change holidays and closures separately from a working time calendar.</span></span>

1. <span data-ttu-id="93a5c-125">Na página **Administração da organização**, selecione **Feriados e recessos**.</span><span class="sxs-lookup"><span data-stu-id="93a5c-125">On the **Organization administration** page, select **Holidays and closures**.</span></span>

2. <span data-ttu-id="93a5c-126">Selecione **Novo** e digite um nome e uma data para o feriado ou recesso.</span><span class="sxs-lookup"><span data-stu-id="93a5c-126">Select **New** and enter a name and date for the holiday or closure.</span></span>

## <a name="configure-non-work-time"></a><span data-ttu-id="93a5c-127">Configurar horário não comercial</span><span class="sxs-lookup"><span data-stu-id="93a5c-127">Configure non-work time</span></span>

<span data-ttu-id="93a5c-128">Você pode adicionar ou alterar horários não comerciais separadamente de um calendário de horário de trabalho.</span><span class="sxs-lookup"><span data-stu-id="93a5c-128">You can add or change non-work times separately from a working time calendar.</span></span>

1. <span data-ttu-id="93a5c-129">Na página **Administração da organização**, selecione **Horário não comercial**.</span><span class="sxs-lookup"><span data-stu-id="93a5c-129">On the **Organization administration** page, select **Non-work time**.</span></span>

2. <span data-ttu-id="93a5c-130">Selecione **Novo** e insira um nome e o intervalo de tempo para o horário não comercial.</span><span class="sxs-lookup"><span data-stu-id="93a5c-130">Select **New** and enter a name and time range for the non-work time.</span></span>

## <a name="leave-and-absence-preview-feature"></a><span data-ttu-id="93a5c-131">Recurso de visualização de licenças e ausências</span><span class="sxs-lookup"><span data-stu-id="93a5c-131">Leave and absence preview feature</span></span>

[!include [banner](includes/preview-feature-leave-absence.md)]

<span data-ttu-id="93a5c-132">Se você tiver habilitado o recurso de visualização de correções de feriados no banco de licenças e ausências, o Human Resources usará feriados e recessos para determinar o número de dias a serem ajustados para os funcionários inscritos no calendário.</span><span class="sxs-lookup"><span data-stu-id="93a5c-132">If you've enabled the Leave and absence bank holiday corrections preview feature, Human Resources uses holidays and closure dates to determine the number of days to adjust for employees enrolled in the calendar.</span></span>

## <a name="see-also"></a><span data-ttu-id="93a5c-133">Consulte também</span><span class="sxs-lookup"><span data-stu-id="93a5c-133">See also</span></span>

- [<span data-ttu-id="93a5c-134">Visão geral de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="93a5c-134">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="93a5c-135">Configurar tipos de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="93a5c-135">Configure leave and absence types</span></span>](hr-leave-and-absence-types.md)
