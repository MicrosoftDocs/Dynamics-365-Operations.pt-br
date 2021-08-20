---
title: Determinar a versão da BOM
description: Durante um detalhamento da demanda, se um item tiver um tipo de ordem padrão, o mecanismo de planejamento localizará uma versão da BOM válida com base no site.
author: roxanadiaconu
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
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 91a55bfcd10ee0efbbf1170ad29194c17ea72d62cf5516e2661b43bad7446808
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6766065"
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