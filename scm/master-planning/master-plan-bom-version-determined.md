---
title: "Determinar a versão da BOM"
description: "Durante um detalhamento da demanda, se um item tiver um tipo de ordem padrão, o mecanismo de planejamento localizará uma versão da BOM válida com base no site."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConsistOf, BOMDesigner, BOMTable, InventItemOrderSetup
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ee265d0ab7807cd92c70096111ffb3dbec11ad62
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="determine-the-bom-version"></a>Determinar a versão da BOM

[!include[banner](../includes/banner.md)]


Durante um detalhamento da demanda, se um item tiver um tipo de ordem padrão, o mecanismo de planejamento localizará uma versão da BOM válida com base no site. 

A dimensão do site é sempre conhecida e é declarada na transação de demanda. O processo a seguir é usado para determinar a versão da BOM a ser usada:

-   Se houver uma versão da BOM definida para o item no site de demanda, será usada a BOM específica do site.
-   Se não houver uma versão da BOM específica do site definida para um item no site de demanda, será usada a BOM geral. Esse tipo de BOM não informa um site e é válida para vários sites. Se houver uma BOM geral, ela será usada.
-   Se não houver uma versão da BOM geral para uso, o detalhamento da demanda para nesse ponto.

Uma versão da BOM válida, específica a um site ou geral, deve preencher os critérios necessários de data e quantidade.






