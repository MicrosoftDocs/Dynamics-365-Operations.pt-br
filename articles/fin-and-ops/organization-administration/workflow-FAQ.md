---
title: Perguntas frequentes sobre fluxo de trabalho
description: Esse tópico responde perguntas frequentes sobre o sistema de fluxo de trabalho no Microsoft Dynamics 365 for Finance and Operations.
author: ChrisGarty
manager: AnnBe
ms.date: 05/07/2019
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
ms.openlocfilehash: f6240b1b5136937aa47f455547fed6f0c7c08e2c
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509282"
---
# <a name="workflow-system"></a><span data-ttu-id="8d3d9-103">Sistema do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="8d3d9-103">Workflow system</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8d3d9-104">Esse tópico responde perguntas frequentes sobre o sistema de fluxo de trabalho no Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8d3d9-104">This topic answers frequently asked questions about the workflow system in Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="notifications"></a><span data-ttu-id="8d3d9-105">Notificações</span><span class="sxs-lookup"><span data-stu-id="8d3d9-105">Notifications</span></span>

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a><span data-ttu-id="8d3d9-106">Por que várias notificações são recebidas quando um item de trabalho é rejeitado?</span><span class="sxs-lookup"><span data-stu-id="8d3d9-106">Why are multiple notifications received when a work item is rejected?</span></span>
<span data-ttu-id="8d3d9-107">Quando um item de trabalho é rejeitado, esse item de trabalho é concluído como anulado.</span><span class="sxs-lookup"><span data-stu-id="8d3d9-107">When a work item is rejected, that work item is completed as rejected.</span></span> <span data-ttu-id="8d3d9-108">Outro item de trabalho é criado e atribuído ao originador.</span><span class="sxs-lookup"><span data-stu-id="8d3d9-108">Another work item is created and assigned to the originator.</span></span> <span data-ttu-id="8d3d9-109">Isso significa que há uma notificação para o originador do item de trabalho rejeitado, e uma notificação separada para o usuário atribuído ao novo item de trabalho com "alteração solicitada".</span><span class="sxs-lookup"><span data-stu-id="8d3d9-109">This means that there is a notification to the originator for the rejected work item, and a separate notification to the user assigned to the new "change requested" work item.</span></span> 

<span data-ttu-id="8d3d9-110">Cada notificação é para um item de trabalho diferente, mas a similaridade pode causar confusão.</span><span class="sxs-lookup"><span data-stu-id="8d3d9-110">Each notification is for a different work item, but the similarity can cause confusion.</span></span> <span data-ttu-id="8d3d9-111">Sempre estamos de olho em formas para aprimorar isso em uma versão futura.</span><span class="sxs-lookup"><span data-stu-id="8d3d9-111">We are looking at ways to improve this in a future release.</span></span>

### <a name="why-are-my-workflow-exports-failing"></a><span data-ttu-id="8d3d9-112">Por que minhas exportações de fluxo de trabalho estão falhando?</span><span class="sxs-lookup"><span data-stu-id="8d3d9-112">Why are my workflow exports failing?</span></span>
<span data-ttu-id="8d3d9-113">Atualmente, existe uma limitação no recurso de exportação de fluxo de trabalho para prevenir que nomes de fluxo de trabalho excedam 48 caracteres.</span><span class="sxs-lookup"><span data-stu-id="8d3d9-113">There is currently a limitation in the workflow export feature that prevents workflow names from exceeding 48 characters.</span></span> <span data-ttu-id="8d3d9-114">Usar um nome maior que 48 caracteres pode resultar em um erro de "Falha do servidor ao autenticar a solicitação" e/ou prevenir que um arquivo seja exportado sem um tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="8d3d9-114">Using a name that is longer than 48 characters can result in a "Server failed to authenticate the request" error and/or prevent a file to be exported  without a file type.</span></span> <span data-ttu-id="8d3d9-115">A postagem de blog a seguir fornece mais detalhes [Solução de problemas na exportação do fluxo de trabalho](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="8d3d9-115">The following blog post provides more details [Workflow Export Troubleshooting](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).</span></span>
