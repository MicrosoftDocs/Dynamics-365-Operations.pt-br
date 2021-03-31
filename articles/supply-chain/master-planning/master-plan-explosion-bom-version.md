---
title: Detalhamento de uma versão da BOM
description: Este artigo explica um cenário de planejamento mestre que envolve detalhamento de uma versão da lista de materiais (BOM).
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 617d9c3f05f2db30ec075a07b54c4827e668c20e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5220839"
---
# <a name="explosion-of-a-bom-version"></a><span data-ttu-id="264db-103">Detalhamento de uma versão da BOM</span><span class="sxs-lookup"><span data-stu-id="264db-103">Explosion of a BOM version</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="264db-104">Este artigo explica um cenário de planejamento mestre que envolve detalhamento de uma versão da lista de materiais (BOM).</span><span class="sxs-lookup"><span data-stu-id="264db-104">This article explains a master planning scenario that involves explosion of a bill of materials (BOM) version.</span></span>

<span data-ttu-id="264db-105">Um detalhamento da demanda de uma versão da lista de materiais (BOM) cria uma demanda para cada item de linha da BOM em um site específico e, possivelmente, em um depósito específico.</span><span class="sxs-lookup"><span data-stu-id="264db-105">A demand explosion of a bill of materials (BOM) version creates a demand for each BOM line item at a specific site and, possibly, at a specific warehouse.</span></span> <span data-ttu-id="264db-106">Em uma BOM específica do site, um determinado depósito pode ser definido para cada linha de BOM.</span><span class="sxs-lookup"><span data-stu-id="264db-106">In a site-specific BOM, a specific warehouse can be defined for each BOM line.</span></span> <span data-ttu-id="264db-107">Além disso, para cada linha de BOM, as configurações de dimensão do item determinam se o depósito é necessário.</span><span class="sxs-lookup"><span data-stu-id="264db-107">Additionally, for each BOM line, the item's dimension settings determine whether the warehouse is required.</span></span> <span data-ttu-id="264db-108">A demanda resultante para cada item de linha de BOM se torna, então, o ponto de partida para detalhamento de demanda adicional.</span><span class="sxs-lookup"><span data-stu-id="264db-108">The resulting demand for each BOM line item then becomes the starting point for additional demand explosion.</span></span> <span data-ttu-id="264db-109">Este cenário de planejamento mestre envolve estas condições:</span><span class="sxs-lookup"><span data-stu-id="264db-109">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="264db-110">A dimensão do site é obrigatória e deve ser inserida na transação de demanda.</span><span class="sxs-lookup"><span data-stu-id="264db-110">The site dimension is mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="264db-111">A dimensão do site é consistente.</span><span class="sxs-lookup"><span data-stu-id="264db-111">The site dimension is consistent.</span></span> <span data-ttu-id="264db-112">Portanto, o site para demanda de nível inferior é o mesmo site na transação de demanda inicial.</span><span class="sxs-lookup"><span data-stu-id="264db-112">Therefore, the site for lower-level demand is the same as the site on the initial demand transaction.</span></span>

<span data-ttu-id="264db-113">A ilustração a seguir mostra como ocorre o processo de detalhamento da demanda do planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="264db-113">The following illustration shows how the process for master planning demand explosion.</span></span> ![Explosão de demanda usando a versão da BOM](./media/multisitedemandexplosionscenariousingbomversion.gif)

<a name="additional-resources"></a><span data-ttu-id="264db-115">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="264db-115">Additional resources</span></span>
--------

[<span data-ttu-id="264db-116">Determinar a versão da BOM</span><span class="sxs-lookup"><span data-stu-id="264db-116">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)

[<span data-ttu-id="264db-117">Visão geral de planejamento mestre e funcionalidade multissite</span><span class="sxs-lookup"><span data-stu-id="264db-117">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]