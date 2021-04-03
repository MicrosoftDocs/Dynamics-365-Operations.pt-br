---
title: Determinar a versão da BOM
description: Durante um detalhamento da demanda, se um item tiver um tipo de ordem padrão, o mecanismo de planejamento localizará uma versão da BOM válida com base no site.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConsistOf, BOMDesigner, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d6f1f1656f0ef04799b1ce6b397dac0f829e41c9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251928"
---
# <a name="determine-the-bom-version"></a><span data-ttu-id="8d795-103">Determinar a versão da BOM</span><span class="sxs-lookup"><span data-stu-id="8d795-103">Determine the BOM version</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8d795-104">Durante um detalhamento da demanda, se um item tiver um tipo de ordem padrão, o mecanismo de planejamento localizará uma versão da BOM válida com base no site.</span><span class="sxs-lookup"><span data-stu-id="8d795-104">During a demand explosion, if an item has a default order type of Production, the planning engine finds a valid BOM version based on the site.</span></span> 

<span data-ttu-id="8d795-105">A dimensão do site é sempre conhecida e é declarada na transação de demanda.</span><span class="sxs-lookup"><span data-stu-id="8d795-105">The site dimension is always known and is stated on the demand transaction.</span></span> <span data-ttu-id="8d795-106">O processo a seguir é usado para determinar a versão da BOM a ser usada:</span><span class="sxs-lookup"><span data-stu-id="8d795-106">The following process is used to determine the BOM version to use:</span></span>

-   <span data-ttu-id="8d795-107">Se houver uma versão da BOM definida para o item no site de demanda, será usada a BOM específica do site.</span><span class="sxs-lookup"><span data-stu-id="8d795-107">If there is a BOM version defined for the item at the demand site, the site-specific BOM is used.</span></span>
-   <span data-ttu-id="8d795-108">Se não houver uma versão da BOM específica do site definida para um item no site de demanda, será usada a BOM geral.</span><span class="sxs-lookup"><span data-stu-id="8d795-108">If there is no site-specific BOM version defined for an item at the demand site, a general BOM is used.</span></span> <span data-ttu-id="8d795-109">Esse tipo de BOM não informa um site e é válida para vários sites.</span><span class="sxs-lookup"><span data-stu-id="8d795-109">A general BOM does not state a site, and it is valid for multiple sites.</span></span> <span data-ttu-id="8d795-110">Se houver uma BOM geral, ela será usada.</span><span class="sxs-lookup"><span data-stu-id="8d795-110">If there is a general BOM, it is used.</span></span>
-   <span data-ttu-id="8d795-111">Se não houver uma versão da BOM geral para uso, o detalhamento da demanda para nesse ponto.</span><span class="sxs-lookup"><span data-stu-id="8d795-111">If there is no general BOM version to use, the demand explosion stops at this point.</span></span>

<span data-ttu-id="8d795-112">Uma versão da BOM válida, específica a um site ou geral, deve preencher os critérios necessários de data e quantidade.</span><span class="sxs-lookup"><span data-stu-id="8d795-112">A valid BOM version, whether site-specific or general, must meet the required criteria for date and quantity.</span></span>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]