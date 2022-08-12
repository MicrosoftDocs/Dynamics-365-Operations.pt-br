---
title: Imposto integrado
description: Este artigo descreve a integração de dados de impostos entre os aplicativos de finanças e operações e o Dataverse.
author: tonyafehr
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: tfehr
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 29d8b2079b5d1cd70f14e096780f83a4a38d4b63
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111526"
---
# <a name="integrated-tax"></a>Imposto integrado

[!include [banner](../../includes/banner.md)]



Os dados de configuração de imposto definem a configuração para os impostos indiretos (IVA, GST, imposto) e imposto retido na fonte. Eles descrevem as regras de cálculo de impostos, taxa de imposto, contabilidade de imposto, liquidação e outros conceitos.

## <a name="templates"></a>Modelos

Os dados de imposto incluem um conjunto de mapas de tabelas que funcionam juntos durante a interação de dados, conforme mostrado na tabela a seguir.

| Aplicativos do Finance and Operations | Aplicativos do Customer Engagement | Descrição |
|-----------------------------|-----------------------------------|-------------|
[Grupo de impostos do item](mapping-reference.md#196) | msdyn_taxitemgroups | |
[Autoridades do imposto](mapping-reference.md#193) | msdyn_taxauthorities | |
[CDS de entidade de código de isenção de imposto](mapping-reference.md#194) | msdyn_taxexemptcodes | |
[Grupos de impostos](mapping-reference.md#195) | msdyn_taxgroups | |
[Grupos de lançamentos contábeis de imposto V2](mapping-reference.md#197) | msdyn_taxpostinggroups | |
[Códigos de impostos retidos na fonte](mapping-reference.md#210) | msdyn_withholdingtaxcodes | |
[Grupos de impostos retidos na fonte](mapping-reference.md#211) | msdyn_withholdingtaxgroups | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

