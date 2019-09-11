---
title: Calendário e agendamento de funcionários de manutenção
description: Este tópico explica o calendário do funcionário de manutenção em relação ao agendamento no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3f86f6475e5226443f5e4d43fb91acafe2afdbb9
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887379"
---
# <a name="maintenance-worker-calendar-and-scheduling"></a><span data-ttu-id="92301-103">Calendário e agendamento de funcionários de manutenção</span><span class="sxs-lookup"><span data-stu-id="92301-103">Maintenance worker calendar and scheduling</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="92301-104">Ao agendar ordens de trabalho, você cria um agendamento para funcionários de manutenção, ferramentas e ativos.</span><span class="sxs-lookup"><span data-stu-id="92301-104">When you schedule work orders, you create a schedule for maintenance workers, tools, and assets.</span></span> <span data-ttu-id="92301-105">Para executar o agendamento dos funcionários de manutenção, um calendário deve ser configurado para cada funcionário de manutenção.</span><span class="sxs-lookup"><span data-stu-id="92301-105">In order to carry out scheduling on maintenance workers, a calendar must be set up for each maintenance worker.</span></span> <span data-ttu-id="92301-106">Os funcionários de serviço são relacionados a um recurso e os calendários de produção são configurados nos recursos.</span><span class="sxs-lookup"><span data-stu-id="92301-106">Maintenance workers are related to a resource, and working time calendars are set up on resoures.</span></span> <span data-ttu-id="92301-107">Você configura o recurso e o calendário relacionado a um colaborador em **Gerenciamento de ativos** > **Configuração** > **Trabalhadores** > **Trabalhadores**, que é descrito em [Funcionários de manutenção e grupos de trabalhadores](../setup-for-objects/workers-and-worker-groups.md).</span><span class="sxs-lookup"><span data-stu-id="92301-107">You set up the resource and calendar related to a worker in **Asset management** > **Setup** > **Workers** > **Workers**, which is described in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).</span></span>

<span data-ttu-id="92301-108">A captura de tela a seguir mostra um exemplo de um funcionário de manutenção que é relacionado a um recurso que usa o calendário de horas úteis "Produção".</span><span class="sxs-lookup"><span data-stu-id="92301-108">The screenshot below shows an example of a maintenance worker who is related to a resource that uses the working time calendar "Production".</span></span>

![Figura 1](media/01-work-order-scheduling.png)

<span data-ttu-id="92301-110">A configuração de calendário para ferramentas e ativos não é necessária em relação ao agendamento de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="92301-110">Calendar setup for tools and assets is not needed in relation to work order scheduling.</span></span> <span data-ttu-id="92301-111">A suposição é que as ferramentas e os ativos estão disponíveis 24 horas por dia para manutenção.</span><span class="sxs-lookup"><span data-stu-id="92301-111">The assumption is that tools and assets are available 24 hours a day for maintenance.</span></span>

