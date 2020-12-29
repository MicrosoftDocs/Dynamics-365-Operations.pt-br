---
title: Grupos de operadoras
description: Este tópico descreve como configurar dados para grupos de operadoras.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSCarrierGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 2570479edac9bc8cc7aa998a8b69f54ffc10cd61
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646362"
---
# <a name="carrier-groups"></a><span data-ttu-id="96b14-103">Grupos de operadoras</span><span class="sxs-lookup"><span data-stu-id="96b14-103">Carrier groups</span></span>

<span data-ttu-id="96b14-104">Um grupo de operadoras é um conjunto de operadoras de remessa e serviços de operadoras.</span><span class="sxs-lookup"><span data-stu-id="96b14-104">A carrier group is a collection of shipping carriers and carrier services.</span></span> <span data-ttu-id="96b14-105">Cada grupo de operadoras especifica a sequência preferencial para as operadoras de remessa e os serviços de operadoras que pertencem a elas.</span><span class="sxs-lookup"><span data-stu-id="96b14-105">Each carrier group specifies the preferred sequence for the shipping carriers and carrier services that belong to it.</span></span>

<span data-ttu-id="96b14-106">Quando existem várias operadoras e serviços de operadoras para o mesmo segmento de roteiro, você pode especificar um grupo de operadoras em vez de uma operadora de remessa e um serviço de operadora específicos no plano de roteiro ou no guia de roteiro.</span><span class="sxs-lookup"><span data-stu-id="96b14-106">When multiple shipping carriers and carrier services exist for the same route segment, you can specify a carrier group instead of a specific shipping carrier and carrier service in the route plan or route guide.</span></span>

## <a name="create-a-carrier-group"></a><span data-ttu-id="96b14-107">Criar um grupo de operadoras</span><span class="sxs-lookup"><span data-stu-id="96b14-107">Create a carrier group</span></span>

1. <span data-ttu-id="96b14-108">Vá para **Gerenciamento de transporte &gt; Configurar &gt; Operadoras &gt; Grupo de operadoras**.</span><span class="sxs-lookup"><span data-stu-id="96b14-108">Go to **Transportation management &gt; Setup &gt; Carriers &gt; Carrier group**.</span></span>
1. <span data-ttu-id="96b14-109">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="96b14-109">Select **New**.</span></span>
1. <span data-ttu-id="96b14-110">No campo **Grupo de operadoras**, insira um identificador exclusivo (ID) para o grupo.</span><span class="sxs-lookup"><span data-stu-id="96b14-110">In the **Carrier group** field, enter a unique identifier (ID) for the group.</span></span>
1. <span data-ttu-id="96b14-111">No campo **Nome**, insira um nome descritivo para o grupo.</span><span class="sxs-lookup"><span data-stu-id="96b14-111">In the **Name** field, enter a descriptive name for the group.</span></span>
1. <span data-ttu-id="96b14-112">Na FastTab **Detalhes**, adicione uma linha e selecione uma operadora de remessa e um serviço de operadora para ela.</span><span class="sxs-lookup"><span data-stu-id="96b14-112">On the **Details** FastTab, add a row, and select a shipping carrier and a carrier service for it.</span></span> <span data-ttu-id="96b14-113">Repita essa etapa até adicionar todas as operadoras necessárias para o grupo.</span><span class="sxs-lookup"><span data-stu-id="96b14-113">Repeat this step until you've added as many carriers as you require for the group.</span></span>
1. <span data-ttu-id="96b14-114">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="96b14-114">Close the page.</span></span>
