---
title: Criar um item de menu de dispositivo móvel para consolidação de placa de licença
description: Este procedimento mostra como criar um item de menu de dispositivo móvel para trabalhos de consolidação de matrícula.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13d08de62129698f85e0a30f870ba680e3bb0532
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148391"
---
# <a name="create-a-mobile-device-menu-item-for-license-plate-consolidation"></a><span data-ttu-id="278e0-103">Criar um item de menu de dispositivo móvel para consolidação de placa de licença</span><span class="sxs-lookup"><span data-stu-id="278e0-103">Create a mobile device menu item for license plate consolidation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="278e0-104">Este procedimento mostra como criar um item de menu de dispositivo móvel para trabalhos de consolidação de matrícula.</span><span class="sxs-lookup"><span data-stu-id="278e0-104">This procedure shows you how to create a mobile device menu item for license plate consolidation work.</span></span> <span data-ttu-id="278e0-105">Isso permite funcionários do depósito para consolidar itens em uma matrícula com itens em outro local de licença no mesmo local.</span><span class="sxs-lookup"><span data-stu-id="278e0-105">This enables warehouse workers to consolidate items on one license plate with items on another license place within the same location.</span></span> <span data-ttu-id="278e0-106">Por exemplo, podem usar este se as etapas subsequentes de preparo estavam as mesmas em ambas as ordens de trabalho, para que somente os trabalhos precisassem de ser executados uma vez para itens mesclados.</span><span class="sxs-lookup"><span data-stu-id="278e0-106">For example, they might use this if subsequent staging steps were the same on both work orders, so that the work only needs to be performed once for the merged items.</span></span> <span data-ttu-id="278e0-107">Você pode usar este procedimento na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="278e0-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="278e0-108">A tarefa normalmente seria realizada por um gerente do depósito.</span><span class="sxs-lookup"><span data-stu-id="278e0-108">The task would typically be carried out by a warehouse manager.</span></span> <span data-ttu-id="278e0-109">Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="278e0-109">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>

1. <span data-ttu-id="278e0-110">Vá para Gerenciamento de depósito > Configuração > Dispositivo móvel > Itens de menu de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="278e0-110">Go to Warehouse management > Setup > Mobile device > Mobile device menu items.</span></span>
2. <span data-ttu-id="278e0-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="278e0-111">Click New.</span></span>
3. <span data-ttu-id="278e0-112">No campo Item de menu, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="278e0-112">In the Menu item name field, type a value.</span></span>
4. <span data-ttu-id="278e0-113">No campo Título, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="278e0-113">In the Title field, type a value.</span></span>
5. <span data-ttu-id="278e0-114">No campo Modo, selecione 'Indireto'.</span><span class="sxs-lookup"><span data-stu-id="278e0-114">In the Mode field, select 'Indirect'.</span></span>
6. <span data-ttu-id="278e0-115">No campo Código da atividade, selecione "Consolidar placas de licença".</span><span class="sxs-lookup"><span data-stu-id="278e0-115">In the Activity code field, select 'Consolidate license plates'.</span></span>

