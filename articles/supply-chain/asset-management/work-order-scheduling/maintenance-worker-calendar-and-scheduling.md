---
title: Calendário e agendamento de funcionários de manutenção
description: Este tópico explica o calendário do funcionário de manutenção em relação ao agendamento no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorker
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4c1e068d273374c6c8ac162a92be6130d85cbe40
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "3888680"
---
# <a name="maintenance-worker-calendar-and-scheduling"></a><span data-ttu-id="b8f2e-103">Calendário e agendamento de funcionários de manutenção</span><span class="sxs-lookup"><span data-stu-id="b8f2e-103">Maintenance worker calendar and scheduling</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="b8f2e-104">Ao agendar ordens de trabalho, você cria um agendamento para funcionários de manutenção, ferramentas e ativos.</span><span class="sxs-lookup"><span data-stu-id="b8f2e-104">When you schedule work orders, you create a schedule for maintenance workers, tools, and assets.</span></span> <span data-ttu-id="b8f2e-105">Para agendar funcionários de manutenção, um calendário deve ser configurado para cada funcionário de manutenção.</span><span class="sxs-lookup"><span data-stu-id="b8f2e-105">In order to schedule maintenance workers, a calendar must be set up for each maintenance worker.</span></span> <span data-ttu-id="b8f2e-106">Os funcionários de manutenção são relacionados a um recurso e os calendários de produção são configurados para os recursos.</span><span class="sxs-lookup"><span data-stu-id="b8f2e-106">Maintenance workers are related to a resource, and working time calendars are set up for resources.</span></span> <span data-ttu-id="b8f2e-107">Você deve configurar o recurso e o calendário em **Gerenciamento de ativos** > **Configurar** > **Trabalhadores** > **Trabalhadores**, que está descrito em [Funcionários de manutenção e grupos de trabalhadores](../setup-for-objects/workers-and-worker-groups.md).</span><span class="sxs-lookup"><span data-stu-id="b8f2e-107">You set up the resource and calendar in **Asset management** > **Setup** > **Workers** > **Workers**, which is described in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).</span></span>

<span data-ttu-id="b8f2e-108">A captura de tela a seguir mostra um exemplo de um funcionário de manutenção que é relacionado a um recurso que usa o calendário de horas úteis "Produção".</span><span class="sxs-lookup"><span data-stu-id="b8f2e-108">The screenshot below shows an example of a maintenance worker who is related to a resource that uses the working time calendar "Production".</span></span>

![Figura 1](media/01-work-order-scheduling.png)

<span data-ttu-id="b8f2e-110">A configuração de calendário para ferramentas e ativos não é necessária em relação ao agendamento de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="b8f2e-110">Calendar setup for tools and assets is not needed in relation to work order scheduling.</span></span> <span data-ttu-id="b8f2e-111">A suposição é que as ferramentas e os ativos estão disponíveis 24 horas por dia para manutenção.</span><span class="sxs-lookup"><span data-stu-id="b8f2e-111">The assumption is that tools and assets are available 24 hours a day for maintenance.</span></span>

