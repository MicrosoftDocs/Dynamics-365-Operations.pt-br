---
title: Configurar eventos de vida futuros
description: Você pode agendar eventos de vida futuros no Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitFutureLifeEvents, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d390bf2e9b25c50e913967ea51fcfadd4a1120b8
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464341"
---
# <a name="configure-future-life-events"></a><span data-ttu-id="e0e17-103">Configurar eventos de vida futuros</span><span class="sxs-lookup"><span data-stu-id="e0e17-103">Configure future life events</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="e0e17-104">Você pode agendar eventos de vida futuros no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e0e17-104">You can schedule future life events in Dynamics 365 Human Resources.</span></span>

1. <span data-ttu-id="e0e17-105">No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Eventos de vida futuros**.</span><span class="sxs-lookup"><span data-stu-id="e0e17-105">In the **Benefits management** workspace, under **Setup**, select **Future life events**.</span></span>

2. <span data-ttu-id="e0e17-106">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="e0e17-106">Select **New**.</span></span>

3. <span data-ttu-id="e0e17-107">Especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="e0e17-107">Specify values for the following fields:</span></span>

   | <span data-ttu-id="e0e17-108">Campo</span><span class="sxs-lookup"><span data-stu-id="e0e17-108">Field</span></span> | <span data-ttu-id="e0e17-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="e0e17-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="e0e17-110">Data do evento de vida</span><span class="sxs-lookup"><span data-stu-id="e0e17-110">Life event date</span></span> | <span data-ttu-id="e0e17-111">O sistema processa todos os eventos durante o período de inscrição que ocorrem até a data atual.</span><span class="sxs-lookup"><span data-stu-id="e0e17-111">The system processes all events during the enrollment period that occur up until this date.</span></span> |
   | <span data-ttu-id="e0e17-112">Evento de vida registrado</span><span class="sxs-lookup"><span data-stu-id="e0e17-112">Life event logged</span></span> | <span data-ttu-id="e0e17-113">Data e hora em que o evento de vida é registrado.</span><span class="sxs-lookup"><span data-stu-id="e0e17-113">Date and time when the life event is logged.</span></span> |
   | <span data-ttu-id="e0e17-114">Tipo de log</span><span class="sxs-lookup"><span data-stu-id="e0e17-114">Log type</span></span> | <span data-ttu-id="e0e17-115">Mostra se a ação é uma das seguintes:</span><span class="sxs-lookup"><span data-stu-id="e0e17-115">Shows whether the action is one of the following:</span></span></br></br><span data-ttu-id="e0e17-116">- **Atualização** – uma alteração em um registro existente que está rastreando eventos de vida</span><span class="sxs-lookup"><span data-stu-id="e0e17-116">- **Update** – a change to an existing record that is tracking life events</span></span></br></br><span data-ttu-id="e0e17-117">- **Inserção** – a criação de um registro de evento de vida</span><span class="sxs-lookup"><span data-stu-id="e0e17-117">- **Insert** – the creation of a new life event record</span></span> |
   | <span data-ttu-id="e0e17-118">ID do tipo de evento de vida</span><span class="sxs-lookup"><span data-stu-id="e0e17-118">Life event type ID</span></span> | <span data-ttu-id="e0e17-119">O identificador exclusivo do tipo de evento de vida.</span><span class="sxs-lookup"><span data-stu-id="e0e17-119">The life event type unique identifier.</span></span> |
   | <span data-ttu-id="e0e17-120">Tipo de evento de vida</span><span class="sxs-lookup"><span data-stu-id="e0e17-120">Life event type</span></span> | <span data-ttu-id="e0e17-121">Um catalisador para atualizar a inscrição em benefícios de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="e0e17-121">A catalyst to updating an employee’s benefits enrollment.</span></span> <span data-ttu-id="e0e17-122">Para obter mais detalhes, consulte a seção Gatilhos de eventos de vida.</span><span class="sxs-lookup"><span data-stu-id="e0e17-122">For more details, see the Life event triggers section.</span></span> |
   | <span data-ttu-id="e0e17-123">Status</span><span class="sxs-lookup"><span data-stu-id="e0e17-123">Status</span></span> | <span data-ttu-id="e0e17-124">Se o evento de vida foi processado ou não.</span><span class="sxs-lookup"><span data-stu-id="e0e17-124">Whether the life event has been processed or not.</span></span> |
   | <span data-ttu-id="e0e17-125">Linha</span><span class="sxs-lookup"><span data-stu-id="e0e17-125">Line</span></span> | <span data-ttu-id="e0e17-126">O número da linha do evento de vida futuro.</span><span class="sxs-lookup"><span data-stu-id="e0e17-126">The line number of the future life event.</span></span> |

4. <span data-ttu-id="e0e17-127">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e0e17-127">Select **Save**.</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]