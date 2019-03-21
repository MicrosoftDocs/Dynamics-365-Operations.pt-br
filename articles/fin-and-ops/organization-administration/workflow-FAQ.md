---
title: Perguntas frequentes sobre fluxo de trabalho
description: Esse tópico responde perguntas frequentes sobre o sistema de fluxo de trabalho no Microsoft Dynamics 365 for Finance and Operations.
author: ChrisGarty
manager: AnnBe
ms.date: 02/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f058a450eb18e688efbc5306a42b4efef6aa91e7
ms.sourcegitcommit: 9a723737565ac78c884e40f7129d0f5aad747524
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/01/2019
ms.locfileid: "773195"
---
# <a name="workflow-system"></a><span data-ttu-id="0bdfb-103">Sistema do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="0bdfb-103">Workflow system</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0bdfb-104">Esse tópico responde perguntas frequentes sobre o sistema de fluxo de trabalho no Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0bdfb-104">This topic answers frequently asked questions about the workflow system in Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="notifications"></a><span data-ttu-id="0bdfb-105">Notificações</span><span class="sxs-lookup"><span data-stu-id="0bdfb-105">Notifications</span></span>

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a><span data-ttu-id="0bdfb-106">Por que várias notificações são recebidas quando um item de trabalho é rejeitado?</span><span class="sxs-lookup"><span data-stu-id="0bdfb-106">Why are multiple notifications received when a work item is rejected?</span></span>
<span data-ttu-id="0bdfb-107">Quando um item de trabalho é rejeitado, esse item de trabalho é concluído como anulado.</span><span class="sxs-lookup"><span data-stu-id="0bdfb-107">When a work item is rejected, that work item is completed as rejected.</span></span> <span data-ttu-id="0bdfb-108">Outro item de trabalho é criado e atribuído ao originador.</span><span class="sxs-lookup"><span data-stu-id="0bdfb-108">Another work item is created and assigned to the originator.</span></span> <span data-ttu-id="0bdfb-109">Isso significa que há uma notificação para o originador do item de trabalho rejeitado, e uma notificação separada para o usuário atribuído ao novo item de trabalho com "alteração solicitada".</span><span class="sxs-lookup"><span data-stu-id="0bdfb-109">This means that there is a notification to the originator for the rejected work item, and a separate notification to the user assigned to the new "change requested" work item.</span></span> 

<span data-ttu-id="0bdfb-110">Cada notificação é para um item de trabalho diferente, mas a similaridade pode causar confusão.</span><span class="sxs-lookup"><span data-stu-id="0bdfb-110">Each notification is for a different work item, but the similarity can cause confusion.</span></span> <span data-ttu-id="0bdfb-111">Sempre estamos de olho em formas para aprimorar isso em uma versão futura.</span><span class="sxs-lookup"><span data-stu-id="0bdfb-111">We are looking at ways to improve this in a future release.</span></span>
