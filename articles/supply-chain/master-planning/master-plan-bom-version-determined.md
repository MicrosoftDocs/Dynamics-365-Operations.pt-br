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
ms.search.scope: Core, Operations
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: efc980e3a3dfff6d163812396613a1493f4428a4
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213782"
---
# <a name="determine-the-bom-version"></a><span data-ttu-id="646fc-103">Determinar a versão da BOM</span><span class="sxs-lookup"><span data-stu-id="646fc-103">Determine the BOM version</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="646fc-104">Durante um detalhamento da demanda, se um item tiver um tipo de ordem padrão, o mecanismo de planejamento localizará uma versão da BOM válida com base no site.</span><span class="sxs-lookup"><span data-stu-id="646fc-104">During a demand explosion, if an item has a default order type of Production, the planning engine finds a valid BOM version based on the site.</span></span> 

<span data-ttu-id="646fc-105">A dimensão do site é sempre conhecida e é declarada na transação de demanda.</span><span class="sxs-lookup"><span data-stu-id="646fc-105">The site dimension is always known and is stated on the demand transaction.</span></span> <span data-ttu-id="646fc-106">O processo a seguir é usado para determinar a versão da BOM a ser usada:</span><span class="sxs-lookup"><span data-stu-id="646fc-106">The following process is used to determine the BOM version to use:</span></span>

-   <span data-ttu-id="646fc-107">Se houver uma versão da BOM definida para o item no site de demanda, será usada a BOM específica do site.</span><span class="sxs-lookup"><span data-stu-id="646fc-107">If there is a BOM version defined for the item at the demand site, the site-specific BOM is used.</span></span>
-   <span data-ttu-id="646fc-108">Se não houver uma versão da BOM específica do site definida para um item no site de demanda, será usada a BOM geral.</span><span class="sxs-lookup"><span data-stu-id="646fc-108">If there is no site-specific BOM version defined for an item at the demand site, a general BOM is used.</span></span> <span data-ttu-id="646fc-109">Esse tipo de BOM não informa um site e é válida para vários sites.</span><span class="sxs-lookup"><span data-stu-id="646fc-109">A general BOM does not state a site, and it is valid for multiple sites.</span></span> <span data-ttu-id="646fc-110">Se houver uma BOM geral, ela será usada.</span><span class="sxs-lookup"><span data-stu-id="646fc-110">If there is a general BOM, it is used.</span></span>
-   <span data-ttu-id="646fc-111">Se não houver uma versão da BOM geral para uso, o detalhamento da demanda para nesse ponto.</span><span class="sxs-lookup"><span data-stu-id="646fc-111">If there is no general BOM version to use, the demand explosion stops at this point.</span></span>

<span data-ttu-id="646fc-112">Uma versão da BOM válida, específica a um site ou geral, deve preencher os critérios necessários de data e quantidade.</span><span class="sxs-lookup"><span data-stu-id="646fc-112">A valid BOM version, whether site-specific or general, must meet the required criteria for date and quantity.</span></span>





