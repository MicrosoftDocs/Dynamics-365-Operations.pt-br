---
title: Sites e depósitos integrados
description: Este tópico descreve a integração de dados do site e do depósito entre o Finance and Operations e o Dataverse.
author: t-benebo
ms.date: 10/09/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-08-15
ms.openlocfilehash: 533635ece005636dcee4e24d1d132111e1e2b370
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750657"
---
# <a name="integrated-sites-and-warehouses"></a>Sites e depósitos integrados

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Este tópico descreve a integração de dados do site e do depósito entre o Finance and Operations e o Dataverse. Sites e depósitos operacionais são conceitos comuns em um aplicativo do Supply Chain Management. Eles são usados para modelar a cadeia de fornecedores da sua empresa.

## <a name="templates"></a>Modelos

A integração com o Dataverse disponibiliza esses conceitos e todas as informações relacionadas no Dataverse por meio das tabelas de dados de site e depósito na tabela a seguir.

Aplicativos Finance and Operations | Outros aplicativos do Dynamics 365 | descrição
--------------------------|---------------------------|---
Sites | msdyn_operationalsites | 
Depósitos | msdyn_warehouses | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]