---
title: Ativos internos para manutenção
description: Este tópico descreve como você pode usar o Microsoft Dynamics 365 Field Service para atender ativos de cliente e ativos internos.
author: RamaKrishnamoorthy
ms.date: 01/27/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: 9ba92b9bf0e35aa812fc7077d998c8779ebe622e
ms.sourcegitcommit: f65bde9ab0bf4c12a3250e7c9b2abb1555cd7931
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6542334"
---
# <a name="in-house-assets-for-servicing"></a>Ativos internos para manutenção

[!include [banner](../../includes/banner.md)]

O Microsoft Dynamics 365 Field Service foi projetado para atender aos ativos dos clientes. O Gerenciamento de ativos de Dynamics 365 Supply Chain Management for desenvolvido para manter ativos internos. A integração desses dois aplicativos permite usar o Field Service para atender tanto ativos do cliente como ativos internos. Também é possível classificar os ativos, com base no local funcional ou na hierarquia, e rastrear o serviço em um nível detalhado.

Para obter mais informações, consulte [Integras Dynamics 365 Field Service e Supply Chain Management](/dynamics365/field-service/supply-chain-field-service-integration).

## <a name="templates"></a>Modelos

Ativos internos incluem um conjunto de mapas de tabelas centrais que funcionam juntos durante a interação de dados, conforme mostrado na tabela a seguir.

| Aplicativos do Finance and Operations | Aplicativos do Customer Engagement | descrição |
|-----------------------------|-----------------------------------|-------------|
[Modelos de ciclo de vida do ativo de gerenciamento de ativos](mapping-reference.md#119) | msdyn_assetlifecyclemodels | |
[Estados de ciclo de vida do ativo de gerenciamento de ativos](mapping-reference.md#120) | msdyn_assetlifecyclestates | |
[Tipos de ativo de gerenciamento de ativo](mapping-reference.md#124) | msdyn_customerassetcategories | |
[Ativos de gerenciamento de ativo](mapping-reference.md#125) | msdyn_customerassets | |
[Modelos de ciclo de vida do local funcional de gerenciamento de ativos](mapping-reference.md#134) | msdyn_functionallocationlifecyclemodels | |
[Estados de ciclo de vida do local funcional de gerenciamento de ativos](mapping-reference.md#135) | msdyn_functionallocationlifecyclestates | |
[Tipos de locais funcionais de gerenciamento de ativos](mapping-reference.md#137) | msdyn_functionallocationtypes | |
[Locais funcionais de gerenciamento de ativos](mapping-reference.md#136) | msdyn_functionallocations | |
[Fabricantes de gerenciamento de ativos](mapping-reference.md#153) | msdyn_manufacturers | |
[Modelos de gerenciamento de ativo](mapping-reference.md#154) | msdyn_models | |
[Garantia de gerenciamento de ativos](mapping-reference.md#209) | msdyn_warranties | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
