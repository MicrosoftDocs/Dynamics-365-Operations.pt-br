---
title: Imposto integrado
description: Este tópico descreve a integração de dados do imposto entre o Finance and Operations e o Dataverse.
author: robinarh
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: rhaertle
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: c7e76294944196670ed4b02ebf785c1bed7b5106f73d4b66a15a19c9a4235cbf
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738543"
---
# <a name="integrated-tax"></a>Imposto integrado

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Os dados de configuração de imposto definem a configuração para os impostos indiretos (IVA, GST, imposto) e imposto retido na fonte. Eles descrevem as regras de cálculo de impostos, taxa de imposto, contabilidade de imposto, liquidação e outros conceitos.

## <a name="templates"></a>Modelos

Os dados de imposto incluem um conjunto de mapas de tabelas que funcionam juntos durante a interação de dados, conforme mostrado na tabela a seguir.

| Aplicativos Finance and Operations | Aplicativos do Customer Engagement | descrição |
|-----------------------------|-----------------------------------|-------------|
[Grupo de impostos do item](mapping-reference.md#196) | msdyn_taxitemgroups | |
[Autoridades do imposto](mapping-reference.md#193) | msdyn_taxauthorities | |
[CDS de entidade de código de isenção de imposto](mapping-reference.md#194) | msdyn_taxexemptcodes | |
[Grupos de impostos](mapping-reference.md#195) | msdyn_taxgroups | |
[Grupos de lançamentos contábeis de imposto V2](mapping-reference.md#197) | msdyn_taxpostinggroups | |
[Códigos de impostos retidos na fonte](mapping-reference.md#210) | msdyn_withholdingtaxcodes | |
[Grupos de impostos retidos na fonte](mapping-reference.md#211) | msdyn_withholdingtaxgroups | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
