---
title: Ativos internos para manutenção
description: Este tópico descreve como você pode usar o Microsoft Dtnamics 365 Field Service para atender tanto ativos de cliente como ativos internos.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/27/2020
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
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: d4d681b2362c90b69007ea44c01c886f96cc1db1
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568069"
---
# <a name="in-house-assets-for-servicing"></a>Ativos internos para manutenção

[!include [banner](../../includes/banner.md)]



O Microsoft Dynamics 365 Field Service foi projetado para atender aos ativos dos clientes. O Gerenciamento de ativos de Dynamics 365 Supply Chain Management for desenvolvido para manter ativos internos. A integração desses dois aplicativos permite usar o Field Service para atender tanto ativos do cliente como ativos internos. Também é possível classificar os ativos, com base no local funcional ou na hierarquia, e rastrear o serviço em um nível detalhado.

Para obter mais informações, consulte [Integras Dynamics 365 Field Service e Supply Chain Management](https://docs.microsoft.com/dynamics365/field-service/supply-chain-field-service-integration).

## <a name="templates"></a>Modelos

Ativos internos incluem um conjunto de mapas de tabelas centrais que funcionam juntos durante a interação de dados, conforme mostrado na tabela a seguir.

| Aplicativos Finance and Operations | Aplicativos controlados por modelos no Dynamics 365 | descrição |
|-----------------------------|-----------------------------------|-------------|
| Modelos de ciclo de vida do ativo de gerenciamento de ativos | msdyn\_assetlifecyclemodels | |
| Estados de ciclo de vida do ativo de gerenciamento de ativos | msdyn\_assetlifecyclestates | |
| Ativos de gerenciamento de ativo | msdyn\_customerassets | |
| Tipos de ativo de gerenciamento de ativo | msdyn\_customerassetcategories | |
| Modelos de ciclo de vida do local funcional de gerenciamento de ativos | msdyn\_functionallocationlifecyclemodels | |
| Estados de ciclo de vida do local funcional de gerenciamento de ativos | msdyn\_functionallocationlifecyclestates | |
| Locais funcionais de gerenciamento de ativos | msdyn\_functionallocations | |
| Tipos de locais funcionais de gerenciamento de ativos | msdyn\_functionallocationtypes | |
| Fabricantes de gerenciamento de ativos | msdyn\_manufacturers | |
| Modelos de gerenciamento de ativo | msdyn\_models | |
| Garantia de gerenciamento de ativos | msdyn\_warranties | |

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [lifecycle models](includes/AssetManagementAssetLifecycleModels-msdyn-assetlifecyclemodels.md)]

[!include [lifecycle states](includes/AssetManagementAssetLifecycleStates-msdyn-assetlifecyclestates.md)]

[!include [assets](includes/AssetManagementAssets-msdyn-customerassets.md)]

[!include [asset types](includes/AssetManagementAssetTypes-msdyn-customerassetcategories.md)]

[!include [functional location lifecycle models](includes/AssetManagementFunctionalLocationLifecycleModels-msdyn-functionallocationlifecyclemodels.md)]

[!include [functional location lifecycle states](includes/AssetManagementFunctionalLocationLifecycleStates-msdyn-functionallocationlifecyclestates.md)]

[!include [functional locations](includes/AssetManagementFunctionalLocations-msdyn-functionallocations.md)]

[!include [functional location types](includes/AssetManagementFunctionalLocationTypes-msdyn-functionallocationtypes.md)]

[!include [manufacturers](includes/AssetManagementManufacturers-msdyn-manufacturers.md)]

[!include [models](includes/AssetManagementModels-msdyn-models.md)]

[!include [warranty](includes/AssetManagementWarranty-msdyn-warranties.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]