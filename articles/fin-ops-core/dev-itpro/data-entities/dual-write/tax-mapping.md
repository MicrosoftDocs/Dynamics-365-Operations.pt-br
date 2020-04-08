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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ''
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: a4da37d45698290b40f6c72148f1500bef72127a
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173076"
---
# <a name="integrated-tax"></a>Imposto integrado

[!include [banner](../../includes/banner.md)]



Os dados de configuração de imposto definem a configuração para os impostos indiretos (IVA, GST, imposto) e imposto retido na fonte. Eles descrevem as regras de cálculo de impostos, taxa de imposto, contabilidade de imposto, liquidação e outros conceitos.

## <a name="templates"></a>Modelos

Os dados de imposto incluem um conjunto de mapas de entidades que funcionam juntos durante a interação de dados, conforme mostrado na tabela a seguir.

| Aplicativos Finance and Operations | Aplicativos controlados por modelos no Dynamics 365 | descrição |
-------------------------|---------------------------------
Códigos de imposto                   | msdyn\_taxcodes.md | 
Grupos de impostos                 | msdyn\_taxgroups.md | 
Grupos de itens de impostos             | msdyn\_taxitemgroups.md | 
Isenções de impostos             | msdyn\_taxexemptcodes.md | 
Autoridades fiscais             | msdyn\_taxauthorities.md | 
Códigos de impostos retidos na fonte       | msdyn\_withholdingtaxcodes.md | 
Grupos de impostos retidos na fonte     | msdyn\_withholdingtaxgroups.md | 
Grupo de contas contábeis de imposto | msdyn\_taxpostinggroups     | 

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

