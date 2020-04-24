---
title: Visão geral de planejamento mestre e funcionalidade multissite
description: O planejamento mestre leva em consideração as configurações de dimensões de estoque de local e de depósito.
author: roxanadiaconu
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2434
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b26ff5c2f580c30113b82302bbad744bbf285ff
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213713"
---
# <a name="master-planning-and-multisite-functionality-overview"></a><span data-ttu-id="b6a4d-103">Visão geral de planejamento mestre e funcionalidade multissite</span><span class="sxs-lookup"><span data-stu-id="b6a4d-103">Master planning and multisite functionality overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b6a4d-104">O planejamento mestre leva em consideração as configurações de dimensões de estoque de local e de depósito.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-104">Master planning takes the settings of the site and warehouse inventory dimensions into account.</span></span> 

<span data-ttu-id="b6a4d-105">A dimensão do site é obrigatória, e você pode definir a dimensão do depósito como obrigatória.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-105">The site dimension is mandatory, and you can set the warehouse dimension to be mandatory.</span></span>

<span data-ttu-id="b6a4d-106">Quando uma dimensão é obrigatória, deve-se inserir um valor de dimensão em todas as transações de estoque.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-106">When a dimension is mandatory, a dimension value must be entered on all inventory transactions.</span></span> <span data-ttu-id="b6a4d-107">Assim, durante o planejamento mestre, o site e o depósito da demanda inicial são conhecidos.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-107">Therefore, during master planning, the site and the warehouse for the initial demand are known.</span></span> <span data-ttu-id="b6a4d-108">A dimensão do site também é consistente para que durante o detalhamento da demanda de nível inferior, o valor do site não seja alterado.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-108">The site dimension is also consistent so that during the explosion of lower-level demand, the site value does not change.</span></span>

<span data-ttu-id="b6a4d-109">Quando o depósito não está definido como obrigatório, ele pode não ser conhecido na demanda inicial.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-109">When the warehouse is not set to mandatory, it may not be known from the initial demand.</span></span> <span data-ttu-id="b6a4d-110">O mecanismo de planejamento deve determinar qual depósito usar com base nas configurações definidas para o item, os depósitos individuais e os detalhes da linha de ordem.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-110">The planning engine must determine which warehouse to use based on the settings that are defined for the item, individual warehouses, and the details of the order line.</span></span>

<span data-ttu-id="b6a4d-111">Os tópicos a seguir descrevem como o mecanismo de planejamento funciona, quando configurações diferentes são feitas, para determinar o depósito a ser usado.</span><span class="sxs-lookup"><span data-stu-id="b6a4d-111">The following topics describe how the planning engine works, when different settings are defined, to determine the warehouse to use.</span></span>

[<span data-ttu-id="b6a4d-112">Planejamento mestre para de site e cobertura de depósito, depósito obrigatório</span><span class="sxs-lookup"><span data-stu-id="b6a4d-112">Master planning for site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="b6a4d-113">Planejamento mestre para cobertura de site, depósito obrigatório</span><span class="sxs-lookup"><span data-stu-id="b6a4d-113">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="b6a4d-114">Planejamento mestre para de site e cobertura de depósito, depósito não obrigatório</span><span class="sxs-lookup"><span data-stu-id="b6a4d-114">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="b6a4d-115">Planejamento mestre para cobertura de site, depósito não obrigatório</span><span class="sxs-lookup"><span data-stu-id="b6a4d-115">Master planning for site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="b6a4d-116">Determinar a versão da BOM</span><span class="sxs-lookup"><span data-stu-id="b6a4d-116">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)



