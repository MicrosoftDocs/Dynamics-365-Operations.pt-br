---
title: Sites e depósitos integrados
description: Este tópico descreve a integração de dados do site e do depósito entre o Finance and Operations e o Common Data Service.
author: t-benebo
manager: AnnBe
ms.date: 10/09/2019
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
ms.author: benebotg
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-08-15
ms.openlocfilehash: 0f5ed58ad50df49250aa4c001401ff52d460dfa6
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019635"
---
# <a name="integrated-sites-and-warehouses"></a>Sites e depósitos integrados

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

Este tópico descreve a integração de dados do site e do depósito entre o Finance and Operations e o Common Data Service. Sites e depósitos operacionais são conceitos comuns em um aplicativo do Supply Chain Management. Eles são usados para modelar a cadeia de fornecedores da sua empresa.

## <a name="templates"></a>Modelos

A integração com o Common Data Service disponibiliza esses conceitos e todas as informações relacionadas no Common Data Service por meio das entidades de dados de site e depósito na tabela a seguir.

Aplicativos Finance and Operations | Outros aplicativos do Dynamics 365 | Descrição
--------------------------|---------------------------|---
Sites | msdyn_operationalsites | 
Depósitos | msdyn_warehouses | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]

