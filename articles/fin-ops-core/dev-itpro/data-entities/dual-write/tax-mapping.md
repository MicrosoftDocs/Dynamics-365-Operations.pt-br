---
title: Imposto integrado
description: Este tópico descreve a integração de dados do imposto entre o Finance and Operations e o Common Data Service.
author: robinarh
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: rhaertle
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 26818ceace7d2b7e7c3ed4d0bb0bd9ab2e884aba
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997591"
---
# <a name="integrated-tax"></a>Imposto integrado

[!include [banner](../../includes/banner.md)]



Os dados de configuração de imposto definem a configuração para os impostos indiretos (IVA, GST, imposto) e imposto retido na fonte. Eles descrevem as regras de cálculo de impostos, taxa de imposto, contabilidade de imposto, liquidação e outros conceitos.

## <a name="templates"></a>Modelos

Os dados de imposto incluem um conjunto de mapas de entidades que funcionam juntos durante a interação de dados, conforme mostrado na tabela a seguir.

Aplicativos Finance and Operations | Aplicativos controlados por modelos no Dynamics 365 | descrição |
-------------------------|---------------------------------|----|
Grupo de impostos do item | msdyn_taxitemgroups |
Autoridades do imposto | msdyn_taxauthorities |
CDS de entidade de código de isenção de imposto | msdyn_taxexemptcodes |
Grupos de impostos | msdyn_taxgroups |
Grupos de lançamentos contábeis de imposto V2 | msdyn_taxpostinggroups |
Códigos de impostos retidos na fonte | msdyn_withholdingtaxcodes |
Grupos de impostos retidos na fonte | msdyn_withholdingtaxgroups | 


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

