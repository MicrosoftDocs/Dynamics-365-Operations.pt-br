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
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 766c857cca603f84bb7fcef2c7eea3bc76620c19
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422422"
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