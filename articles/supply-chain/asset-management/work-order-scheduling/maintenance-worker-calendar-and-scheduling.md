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
ms.openlocfilehash: aa2d50a976af7ee7dde5335f94336b995fdc2d11
ms.sourcegitcommit: fb66731f05207094149a6bc7b8549a4dabbb071a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2019
ms.locfileid: "2652048"
---
# <a name="maintenance-worker-calendar-and-scheduling"></a><span data-ttu-id="eb2ba-103">Calendário e agendamento de funcionários de manutenção</span><span class="sxs-lookup"><span data-stu-id="eb2ba-103">Maintenance worker calendar and scheduling</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="eb2ba-104">Ao agendar ordens de trabalho, você cria um agendamento para funcionários de manutenção, ferramentas e ativos.</span><span class="sxs-lookup"><span data-stu-id="eb2ba-104">When you schedule work orders, you create a schedule for maintenance workers, tools, and assets.</span></span> <span data-ttu-id="eb2ba-105">Para agendar funcionários de manutenção, um calendário deve ser configurado para cada funcionário de manutenção.</span><span class="sxs-lookup"><span data-stu-id="eb2ba-105">In order to schedule maintenance workers, a calendar must be set up for each maintenance worker.</span></span> <span data-ttu-id="eb2ba-106">Os funcionários de manutenção são relacionados a um recurso e os calendários de produção são configurados para os recursos.</span><span class="sxs-lookup"><span data-stu-id="eb2ba-106">Maintenance workers are related to a resource, and working time calendars are set up for resources.</span></span> <span data-ttu-id="eb2ba-107">Você deve configurar o recurso e o calendário em **Gerenciamento de ativos** > **Configurar** > **Trabalhadores** > **Trabalhadores**, que está descrito em [Funcionários de manutenção e grupos de trabalhadores](../setup-for-objects/workers-and-worker-groups.md).</span><span class="sxs-lookup"><span data-stu-id="eb2ba-107">You set up the resource and calendar in **Asset management** > **Setup** > **Workers** > **Workers**, which is described in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).</span></span>

<span data-ttu-id="eb2ba-108">A captura de tela a seguir mostra um exemplo de um funcionário de manutenção que é relacionado a um recurso que usa o calendário de horas úteis "Produção".</span><span class="sxs-lookup"><span data-stu-id="eb2ba-108">The screenshot below shows an example of a maintenance worker who is related to a resource that uses the working time calendar "Production".</span></span>

![Figura 1](media/01-work-order-scheduling.png)

<span data-ttu-id="eb2ba-110">A configuração de calendário para ferramentas e ativos não é necessária em relação ao agendamento de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="eb2ba-110">Calendar setup for tools and assets is not needed in relation to work order scheduling.</span></span> <span data-ttu-id="eb2ba-111">A suposição é que as ferramentas e os ativos estão disponíveis 24 horas por dia para manutenção.</span><span class="sxs-lookup"><span data-stu-id="eb2ba-111">The assumption is that tools and assets are available 24 hours a day for maintenance.</span></span>

