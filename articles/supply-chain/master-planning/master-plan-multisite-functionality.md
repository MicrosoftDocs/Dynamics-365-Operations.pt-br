---
title: Visão geral de planejamento mestre e funcionalidade multissite
description: O planejamento mestre leva em consideração as configurações de dimensões de estoque de local e de depósito.
author: roxanadiaconu
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2434
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f05e3efd1716a27a659ae40145f37bb0b3d977f
ms.sourcegitcommit: e286572ce94a9442a5b3076c3ff5b429be0ed512
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2019
ms.locfileid: "1865391"
---
# <a name="master-planning-and-multisite-functionality-overview"></a><span data-ttu-id="adef8-103">Visão geral de planejamento mestre e funcionalidade multissite</span><span class="sxs-lookup"><span data-stu-id="adef8-103">Master planning and multisite functionality overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="adef8-104">O planejamento mestre leva em consideração as configurações de dimensões de estoque de local e de depósito.</span><span class="sxs-lookup"><span data-stu-id="adef8-104">Master planning takes the settings of the site and warehouse inventory dimensions into account.</span></span> 

<span data-ttu-id="adef8-105">A dimensão do site é obrigatória, e você pode definir a dimensão do depósito como obrigatória.</span><span class="sxs-lookup"><span data-stu-id="adef8-105">The site dimension is mandatory, and you can set the warehouse dimension to be mandatory.</span></span>

<span data-ttu-id="adef8-106">Quando uma dimensão é obrigatória, deve-se inserir um valor de dimensão em todas as transações de estoque.</span><span class="sxs-lookup"><span data-stu-id="adef8-106">When a dimension is mandatory, a dimension value must be entered on all inventory transactions.</span></span> <span data-ttu-id="adef8-107">Assim, durante o planejamento mestre, o site e o depósito da demanda inicial são conhecidos.</span><span class="sxs-lookup"><span data-stu-id="adef8-107">Therefore, during master planning, the site and the warehouse for the initial demand are known.</span></span> <span data-ttu-id="adef8-108">A dimensão do site também é consistente para que durante o detalhamento da demanda de nível inferior, o valor do site não seja alterado.</span><span class="sxs-lookup"><span data-stu-id="adef8-108">The site dimension is also consistent so that during the explosion of lower-level demand, the site value does not change.</span></span>

<span data-ttu-id="adef8-109">Quando o depósito não está definido como obrigatório, ele pode não ser conhecido na demanda inicial.</span><span class="sxs-lookup"><span data-stu-id="adef8-109">When the warehouse is not set to mandatory, it may not be known from the initial demand.</span></span> <span data-ttu-id="adef8-110">O mecanismo de planejamento deve determinar qual depósito usar com base nas configurações definidas para o item, os depósitos individuais e os detalhes da linha de ordem.</span><span class="sxs-lookup"><span data-stu-id="adef8-110">The planning engine must determine which warehouse to use based on the settings that are defined for the item, individual warehouses, and the details of the order line.</span></span>

<span data-ttu-id="adef8-111">Os tópicos a seguir descrevem como o mecanismo de planejamento funciona, quando configurações diferentes são feitas, para determinar o depósito a ser usado.</span><span class="sxs-lookup"><span data-stu-id="adef8-111">The following topics describe how the planning engine works, when different settings are defined, to determine the warehouse to use.</span></span>

[<span data-ttu-id="adef8-112">Planejamento mestre - cobertura de site e depósito, depósito obrigatório</span><span class="sxs-lookup"><span data-stu-id="adef8-112">Master planning - site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="adef8-113">Planejamento mestre - cobertura de site, depósito obrigatório</span><span class="sxs-lookup"><span data-stu-id="adef8-113">Master planning - site coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="adef8-114">Planejamento mestre - cobertura de site e depósito, depósito não obrigatório</span><span class="sxs-lookup"><span data-stu-id="adef8-114">Master planning - site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="adef8-115">Planejamento mestre - cobertura de site, depósito não obrigatório</span><span class="sxs-lookup"><span data-stu-id="adef8-115">Master planning - site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="adef8-116">Planejamento mestre – como a versão da BOM é determinada</span><span class="sxs-lookup"><span data-stu-id="adef8-116">Master planning - How the BOM version is determined</span></span>](master-plan-bom-version-determined.md)



