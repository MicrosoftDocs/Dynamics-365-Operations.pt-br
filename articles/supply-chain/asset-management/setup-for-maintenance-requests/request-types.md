---
title: Tipos de solicitação de manutenção
description: Este tópico explica como configurar uma solicitação de manutenção no Asset Management.
author: josaw1
manager: tfehr
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d353f084e0d3e056f1b5ff5af6437ba211def8ec
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422295"
---
# <a name="maintenance-request-types"></a><span data-ttu-id="e0ccb-103">Tipos de solicitação de manutenção</span><span class="sxs-lookup"><span data-stu-id="e0ccb-103">Maintenance request types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="e0ccb-104">Os tipos de solicitação de manutenção são usados para categorizar solicitações de manutenção.</span><span class="sxs-lookup"><span data-stu-id="e0ccb-104">Maintenance request types are used to categorize maintenance requests.</span></span> <span data-ttu-id="e0ccb-105">Por exemplo, você pode ter os tipos de solicitação de manutenção relacionados à manutenção preventiva e manutenção corretiva.</span><span class="sxs-lookup"><span data-stu-id="e0ccb-105">For example, you might have maintenance request types that are related to preventive maintenance and corrective maintenance.</span></span> <span data-ttu-id="e0ccb-106">Ou pode ter um tipo especial de solicitação de manutenção que é usado para gerenciar o reparo de ativos (reparo de depósito).</span><span class="sxs-lookup"><span data-stu-id="e0ccb-106">Or you might have a special maintenance request type that is used to manage repair of assets (depot repair).</span></span>

<span data-ttu-id="e0ccb-107">Um tipo do solicitação de manutenção define a afiliação ao grupo de estados de ciclo de vida da solicitação de manutenção (modelo do ciclo de vida de manutenção).</span><span class="sxs-lookup"><span data-stu-id="e0ccb-107">A maintenance request type defines the affiliation with a maintenance request lifecycle state group (maintenance lifecycle model).</span></span> <span data-ttu-id="e0ccb-108">Os modelos de ciclo de vida de solicitação de manutenção definem os estados de ciclo de vida que podem ser definidos para uma solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="e0ccb-108">Maintenance request lifecycle models define the lifecycle states that can be set for a maintenance request.</span></span> <span data-ttu-id="e0ccb-109">(Os exemplos dos estados de ciclo de vida de solicitação de manutenção incluem **Criado**, **Ativo** e **Concluído**).</span><span class="sxs-lookup"><span data-stu-id="e0ccb-109">(Examples of maintenance request lifecycle states include **Created**, **Active**, and **Ended**.)</span></span>

1. <span data-ttu-id="e0ccb-110">Selecione **Gerenciamento de ativos** \> **Configuração** \> **Solicitações de manutenção** \> **Tipos de solicitação de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="e0ccb-110">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Maintenance request types**.</span></span>
2. <span data-ttu-id="e0ccb-111">Selecione **Novo** para criar um tipo de solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="e0ccb-111">Select **New** to create a maintenance request type.</span></span>
3. <span data-ttu-id="e0ccb-112">No campo **Tipo de solicitação de manutenção** , insira uma ID para o tipo de solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="e0ccb-112">In the **Maintenance request type** field, enter an ID for the maintenance request type.</span></span>
4. <span data-ttu-id="e0ccb-113">No campo **Nome**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="e0ccb-113">In the **Name** field, enter a name.</span></span>
5. <span data-ttu-id="e0ccb-114">Na Guia Rápida **Geral**, no campo **Modelo de ciclo de vida de solicitação de manutenção** , selecione um modelo de ciclo de vida de solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="e0ccb-114">On the **General** FastTab, in the **Maintenance request lifecycle model** field, select a maintenance request lifecycle model.</span></span>
6. <span data-ttu-id="e0ccb-115">No campo **Tipo de ordem de serviço**, selecione um tipo de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="e0ccb-115">In the **Work order type** field, select a work order type.</span></span> <span data-ttu-id="e0ccb-116">Quando uma solicitação de manutenção é convertida em uma ordem de serviço, a ordem de serviço obtém automaticamente o tipo de ordem de serviço relacionado ao tipo de solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="e0ccb-116">When a maintenance request is converted to a work order, the work order automatically gets the work order type that is related to the maintenance request type.</span></span>

<span data-ttu-id="e0ccb-117">A ilustração a seguir mostra um exemplo da página **Tipos de solicitação de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="e0ccb-117">The following illustration shows an example of the **Maintenance request types** page.</span></span>

![Página de tipos de solicitação de manutenção](media/07-setup-for-requests.png)
