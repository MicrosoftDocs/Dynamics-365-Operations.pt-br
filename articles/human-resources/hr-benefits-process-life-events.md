---
title: Processar eventos de vida
description: Durante o ciclo de vida do funcionário no Microsoft Dynamics 365 Human Resources, cada funcionário pode encontrar várias alterações de eventos de vida.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 461f90c3da8fa5b2db14b6dd67a0c19f7eabe867
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5793792"
---
# <a name="process-life-events"></a><span data-ttu-id="8e496-103">Processar eventos de vida</span><span class="sxs-lookup"><span data-stu-id="8e496-103">Process life events</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="8e496-104">Durante o ciclo de vida do funcionário no Microsoft Dynamics 365 Human Resources, cada funcionário pode encontrar várias alterações de eventos de vida.</span><span class="sxs-lookup"><span data-stu-id="8e496-104">During the employee lifecycle in Microsoft Dynamics 365 Human Resources, each employee may encounter various life event changes.</span></span> <span data-ttu-id="8e496-105">Por exemplo, casamento, mudança de emprego ou alteração de dependente/beneficiário.</span><span class="sxs-lookup"><span data-stu-id="8e496-105">For example, marriage, change in employment, or dependent/beneficiary change.</span></span> <span data-ttu-id="8e496-106">Para usar eventos de vida, você deve habilitar eventos de vida no formulário de parâmetros de benefícios, configurar tipos de eventos de vida e configurar opções de eventos de vida para tipos de plano.</span><span class="sxs-lookup"><span data-stu-id="8e496-106">To use life events, you must enable life events in the benefits parameters form, set up life event types, and set up life event options for plan types.</span></span>

<span data-ttu-id="8e496-107">Antes de poder processar eventos de vida, você já deve ter executado a inscrição aberta pelo menos uma vez durante um período de contratação.</span><span class="sxs-lookup"><span data-stu-id="8e496-107">Before you can process life events, you must have already run open enrollment at least once during a hiring time frame.</span></span> <span data-ttu-id="8e496-108">Nos Estados Unidos, a inscrição aberta costuma ocorrer uma vez por ano.</span><span class="sxs-lookup"><span data-stu-id="8e496-108">In the United States, open enrollment is typically once per year.</span></span> <span data-ttu-id="8e496-109">Fora dos Estados Unidos, a inscrição aberta pode ser realizada no momento da contratação.</span><span class="sxs-lookup"><span data-stu-id="8e496-109">Outside the United States, open enrollment may be run at the time of hire.</span></span> <span data-ttu-id="8e496-110">Um trabalhador não precisa selecionar um plano de benefícios para que os eventos de vida sejam processados, mas eles precisam ter sido incluídos no processamento de inscrição aberta.</span><span class="sxs-lookup"><span data-stu-id="8e496-110">A worker does not need to select a benefit plan in order for life events to be processed, but they need to have been included in open enrollment processing.</span></span> 

<span data-ttu-id="8e496-111">Use o processamento de eventos de vida quando tiver trabalhadores com eventos de vida que ocorrerão em uma data futura.</span><span class="sxs-lookup"><span data-stu-id="8e496-111">Use life event processing when you have workers who have life events that take place on a future date.</span></span> <span data-ttu-id="8e496-112">Este evento processará todos os eventos de vida que não foram processados (como eventos de vida futuros ou eventos de vida adicionados que não são específicos para nenhum trabalhador; por exemplo, um novo benefício).</span><span class="sxs-lookup"><span data-stu-id="8e496-112">This event will process all life events that have not been processed (like future life events, or life events that have been added that are not specific to any one worker – one example is a new benefit).</span></span> <span data-ttu-id="8e496-113">Os eventos de vida em tempo real estão ocultos.</span><span class="sxs-lookup"><span data-stu-id="8e496-113">Real-time life events are hidden.</span></span>

<span data-ttu-id="8e496-114">Por exemplo, se hoje for 1º de fevereiro, houver um agendamento para que trabalhador José da Silva altere entidades legais em 14 de fevereiro e você executar o processamento de eventos de vida em 15 de fevereiro, o sistema processará todos os eventos até 15 de fevereiro.</span><span class="sxs-lookup"><span data-stu-id="8e496-114">For example, if today is February 1, and on February 14 worker Joe Smith is scheduled to change legal entities, if you run life event processing for February 15, the system processes all events up until February 15.</span></span> 

1. <span data-ttu-id="8e496-115">No espaço de trabalho **Gerenciamento de benefícios**, em **Processando**, selecione **Processamento de eventos de vida**.</span><span class="sxs-lookup"><span data-stu-id="8e496-115">In the **Benefits management** workspace, under **Processing**, select **Life event processing**.</span></span>

2. <span data-ttu-id="8e496-116">No caixa de diálogo **Executar o processamento de eventos de vida**, especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="8e496-116">In the **Run life event process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="8e496-117">Campo</span><span class="sxs-lookup"><span data-stu-id="8e496-117">Field</span></span> | <span data-ttu-id="8e496-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="8e496-118">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="8e496-119">**Período de inscrição**</span><span class="sxs-lookup"><span data-stu-id="8e496-119">**Enrollment period**</span></span> | <span data-ttu-id="8e496-120">O período de inscrição para processar eventos de vida.</span><span class="sxs-lookup"><span data-stu-id="8e496-120">The enrollment period to process life events for.</span></span> |
   | <span data-ttu-id="8e496-121">**Pessoa jurídica em geral**</span><span class="sxs-lookup"><span data-stu-id="8e496-121">**Legal entity**</span></span> | <span data-ttu-id="8e496-122">A entidade legal para processar eventos de vida.</span><span class="sxs-lookup"><span data-stu-id="8e496-122">The legal entity to process life events for.</span></span> |
   | <span data-ttu-id="8e496-123">**Data do evento de vida**</span><span class="sxs-lookup"><span data-stu-id="8e496-123">**Life event date**</span></span> | <span data-ttu-id="8e496-124">O sistema processa todos os eventos durante o período de inscrição que ocorrem até a data atual.</span><span class="sxs-lookup"><span data-stu-id="8e496-124">The system processes all events during the enrollment period that occur up until this date.</span></span> |
   | <span data-ttu-id="8e496-125">**Trabalhador**</span><span class="sxs-lookup"><span data-stu-id="8e496-125">**Worker**</span></span> | <span data-ttu-id="8e496-126">O trabalhador para processar eventos de vida.</span><span class="sxs-lookup"><span data-stu-id="8e496-126">The worker to process life events for.</span></span> <span data-ttu-id="8e496-127">Se você deixar esse campo em branco, os eventos de vida serão processados para todos os trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="8e496-127">If you leave this field blank, life events will be processed for all workers.</span></span> |

3. <span data-ttu-id="8e496-128">Se você deseja executar o processo em segundo plano, selecione **Executar em segundo plano** e execute as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="8e496-128">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="8e496-129">Insira informações para o processo.</span><span class="sxs-lookup"><span data-stu-id="8e496-129">Enter information for the process.</span></span>

   2. <span data-ttu-id="8e496-130">Para configurar um trabalho recorrente, selecione **Recorrência**, insira as informações de recorrência e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e496-130">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="8e496-131">Para configurar um alerta de trabalho, selecione **Alertas**, selecione os alertas a receber e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e496-131">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="8e496-132">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e496-132">Select **OK**.</span></span> <span data-ttu-id="8e496-133">O processo será executado com os parâmetros definidos por você.</span><span class="sxs-lookup"><span data-stu-id="8e496-133">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="8e496-134">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e496-134">Select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]