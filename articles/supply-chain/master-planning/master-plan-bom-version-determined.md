---
title: Determinar a versão da BOM
description: Durante um detalhamento da demanda, se um item tiver um tipo de ordem padrão, o mecanismo de planejamento localizará uma versão da BOM válida com base no site.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMConsistOf, BOMDesigner, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 511d69dd1c02771840ef45e9a74aa3444b099dd2
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2022
ms.locfileid: "8470348"
---
# <a name="determine-the-bom-version"></a>Determinar a versão da BOM

[!include [banner](../includes/banner.md)]

Durante um detalhamento da demanda, se um item tiver um tipo de ordem padrão, o mecanismo de planejamento localizará uma versão da BOM válida com base no site. 

A dimensão do site é sempre conhecida e é declarada na transação de demanda. O processo a seguir é usado para determinar a versão da BOM a ser usada:

-   Se houver uma versão da BOM definida para o item no site de demanda, será usada a BOM específica do site.
-   Se não houver uma versão da BOM específica do site definida para um item no site de demanda, será usada a BOM geral. Esse tipo de BOM não informa um site e é válida para vários sites. Se houver uma BOM geral, ela será usada.
-   Se não houver uma versão da BOM geral para uso, o detalhamento da demanda para nesse ponto.

Uma versão da BOM válida, específica a um site ou geral, deve preencher os critérios necessários de data e quantidade.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]