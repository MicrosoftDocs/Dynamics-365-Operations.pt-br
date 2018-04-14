---
title: "Detalhamento de uma versão da BOM"
description: "Este artigo explica um cenário de planejamento mestre que envolve detalhamento de uma versão da lista de materiais (BOM)."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: bce6ffd0ee284f2a5e5b5fef0bdfa92e192b2f42
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="explosion-of-a-bom-version"></a><span data-ttu-id="b9908-103">Detalhamento de uma versão da BOM</span><span class="sxs-lookup"><span data-stu-id="b9908-103">Explosion of a BOM version</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="b9908-104">Este artigo explica um cenário de planejamento mestre que envolve detalhamento de uma versão da lista de materiais (BOM).</span><span class="sxs-lookup"><span data-stu-id="b9908-104">This article explains a master planning scenario that involves explosion of a bill of materials (BOM) version.</span></span>

<span data-ttu-id="b9908-105">Um detalhamento da demanda de uma versão da lista de materiais (BOM) cria uma demanda para cada item de linha da BOM em um site específico e, possivelmente, em um depósito específico.</span><span class="sxs-lookup"><span data-stu-id="b9908-105">A demand explosion of a bill of materials (BOM) version creates a demand for each BOM line item at a specific site and, possibly, at a specific warehouse.</span></span> <span data-ttu-id="b9908-106">Em uma BOM específica do site, um determinado depósito pode ser definido para cada linha de BOM.</span><span class="sxs-lookup"><span data-stu-id="b9908-106">In a site-specific BOM, a specific warehouse can be defined for each BOM line.</span></span> <span data-ttu-id="b9908-107">Além disso, para cada linha de BOM, as configurações de dimensão do item determinam se o depósito é necessário.</span><span class="sxs-lookup"><span data-stu-id="b9908-107">Additionally, for each BOM line, the item's dimension settings determine whether the warehouse is required.</span></span> <span data-ttu-id="b9908-108">A demanda resultante para cada item de linha de BOM se torna, então, o ponto de partida para detalhamento de demanda adicional.</span><span class="sxs-lookup"><span data-stu-id="b9908-108">The resulting demand for each BOM line item then becomes the starting point for additional demand explosion.</span></span> <span data-ttu-id="b9908-109">Este cenário de planejamento mestre envolve estas condições:</span><span class="sxs-lookup"><span data-stu-id="b9908-109">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="b9908-110">A dimensão do site é obrigatória e deve ser inserida na transação de demanda.</span><span class="sxs-lookup"><span data-stu-id="b9908-110">The site dimension is mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="b9908-111">A dimensão do site é consistente.</span><span class="sxs-lookup"><span data-stu-id="b9908-111">The site dimension is consistent.</span></span> <span data-ttu-id="b9908-112">Portanto, o site para demanda de nível inferior é o mesmo site na transação de demanda inicial.</span><span class="sxs-lookup"><span data-stu-id="b9908-112">Therefore, the site for lower-level demand is the same as the site on the initial demand transaction.</span></span>

<span data-ttu-id="b9908-113">A ilustração a seguir mostra como ocorre o processo de detalhamento da demanda do planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="b9908-113">The following illustration shows how the process for master planning demand explosion.</span></span> ![Explosão de demanda usando a versão da BOM](./media/multisitedemandexplosionscenariousingbomversion.gif)

<a name="see-also"></a><span data-ttu-id="b9908-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b9908-115">See also</span></span>
--------

[<span data-ttu-id="b9908-116">Planejamento mestre – como a versão da BOM é determinada</span><span class="sxs-lookup"><span data-stu-id="b9908-116">Master planning - how the BOM version is determined</span></span>](master-plan-bom-version-determined.md)

[<span data-ttu-id="b9908-117">Planejamento mestre e funcionalidade multissite</span><span class="sxs-lookup"><span data-stu-id="b9908-117">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)




