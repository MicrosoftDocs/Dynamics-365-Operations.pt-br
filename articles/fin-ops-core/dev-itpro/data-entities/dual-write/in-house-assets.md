---
title: Ativos internos para manutenção
description: Este tópico descreve como você pode usar o Microsoft Dtnamics 365 Field Service para atender tanto ativos de cliente como ativos internos.
author: RamaKrishnamoorthy
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
ms.openlocfilehash: 040f9d26a137ebce1edc6adf28ff226b3a81e1ae
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748584"
---
# <a name="in-house-assets-for-servicing"></a><span data-ttu-id="ed45c-103">Ativos internos para manutenção</span><span class="sxs-lookup"><span data-stu-id="ed45c-103">In-house assets for servicing</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="ed45c-104">O Microsoft Dynamics 365 Field Service foi projetado para atender aos ativos dos clientes.</span><span class="sxs-lookup"><span data-stu-id="ed45c-104">Microsoft Dynamics 365 Field Service is designed to service customer assets.</span></span> <span data-ttu-id="ed45c-105">O Gerenciamento de ativos de Dynamics 365 Supply Chain Management for desenvolvido para manter ativos internos.</span><span class="sxs-lookup"><span data-stu-id="ed45c-105">Asset management for Dynamics 365 Supply Chain Management is designed to maintain in-house assets.</span></span> <span data-ttu-id="ed45c-106">A integração desses dois aplicativos permite usar o Field Service para atender tanto ativos do cliente como ativos internos.</span><span class="sxs-lookup"><span data-stu-id="ed45c-106">Integration of these two apps lets you use Field Service to service both customer assets and in-house assets.</span></span> <span data-ttu-id="ed45c-107">Também é possível classificar os ativos, com base no local funcional ou na hierarquia, e rastrear o serviço em um nível detalhado.</span><span class="sxs-lookup"><span data-stu-id="ed45c-107">You can also classify the assets, based on functional location or hierarchy, and track the servicing at a detailed level.</span></span>

<span data-ttu-id="ed45c-108">Para obter mais informações, consulte [Integras Dynamics 365 Field Service e Supply Chain Management](https://docs.microsoft.com/dynamics365/field-service/supply-chain-field-service-integration).</span><span class="sxs-lookup"><span data-stu-id="ed45c-108">For more information, see [Integrate Dynamics 365 Field Service and Supply Chain Management](https://docs.microsoft.com/dynamics365/field-service/supply-chain-field-service-integration).</span></span>

## <a name="templates"></a><span data-ttu-id="ed45c-109">Modelos</span><span class="sxs-lookup"><span data-stu-id="ed45c-109">Templates</span></span>

<span data-ttu-id="ed45c-110">Ativos internos incluem um conjunto de mapas de tabelas centrais que funcionam juntos durante a interação de dados, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="ed45c-110">In-house-assets include a collection of core table maps that work together during data interaction, as shown in the following table.</span></span>

| <span data-ttu-id="ed45c-111">Aplicativos Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ed45c-111">Finance and Operations apps</span></span> | <span data-ttu-id="ed45c-112">Aplicativos controlados por modelos no Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="ed45c-112">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="ed45c-113">descrição</span><span class="sxs-lookup"><span data-stu-id="ed45c-113">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="ed45c-114">Modelos de ciclo de vida do ativo de gerenciamento de ativos</span><span class="sxs-lookup"><span data-stu-id="ed45c-114">Asset management asset lifecycle models</span></span> | <span data-ttu-id="ed45c-115">msdyn\_assetlifecyclemodels</span><span class="sxs-lookup"><span data-stu-id="ed45c-115">msdyn\_assetlifecyclemodels</span></span> | |
| <span data-ttu-id="ed45c-116">Estados de ciclo de vida do ativo de gerenciamento de ativos</span><span class="sxs-lookup"><span data-stu-id="ed45c-116">Asset management asset lifecycle states</span></span> | <span data-ttu-id="ed45c-117">msdyn\_assetlifecyclestates</span><span class="sxs-lookup"><span data-stu-id="ed45c-117">msdyn\_assetlifecyclestates</span></span> | |
| <span data-ttu-id="ed45c-118">Ativos de gerenciamento de ativo</span><span class="sxs-lookup"><span data-stu-id="ed45c-118">Asset management assets</span></span> | <span data-ttu-id="ed45c-119">msdyn\_customerassets</span><span class="sxs-lookup"><span data-stu-id="ed45c-119">msdyn\_customerassets</span></span> | |
| <span data-ttu-id="ed45c-120">Tipos de ativo de gerenciamento de ativo</span><span class="sxs-lookup"><span data-stu-id="ed45c-120">Asset management asset types</span></span> | <span data-ttu-id="ed45c-121">msdyn\_customerassetcategories</span><span class="sxs-lookup"><span data-stu-id="ed45c-121">msdyn\_customerassetcategories</span></span> | |
| <span data-ttu-id="ed45c-122">Modelos de ciclo de vida do local funcional de gerenciamento de ativos</span><span class="sxs-lookup"><span data-stu-id="ed45c-122">Asset management functional location lifecycle models</span></span> | <span data-ttu-id="ed45c-123">msdyn\_functionallocationlifecyclemodels</span><span class="sxs-lookup"><span data-stu-id="ed45c-123">msdyn\_functionallocationlifecyclemodels</span></span> | |
| <span data-ttu-id="ed45c-124">Estados de ciclo de vida do local funcional de gerenciamento de ativos</span><span class="sxs-lookup"><span data-stu-id="ed45c-124">Asset management functional location lifecycle states</span></span> | <span data-ttu-id="ed45c-125">msdyn\_functionallocationlifecyclestates</span><span class="sxs-lookup"><span data-stu-id="ed45c-125">msdyn\_functionallocationlifecyclestates</span></span> | |
| <span data-ttu-id="ed45c-126">Locais funcionais de gerenciamento de ativos</span><span class="sxs-lookup"><span data-stu-id="ed45c-126">Asset management functional locations</span></span> | <span data-ttu-id="ed45c-127">msdyn\_functionallocations</span><span class="sxs-lookup"><span data-stu-id="ed45c-127">msdyn\_functionallocations</span></span> | |
| <span data-ttu-id="ed45c-128">Tipos de locais funcionais de gerenciamento de ativos</span><span class="sxs-lookup"><span data-stu-id="ed45c-128">Asset management functional location types</span></span> | <span data-ttu-id="ed45c-129">msdyn\_functionallocationtypes</span><span class="sxs-lookup"><span data-stu-id="ed45c-129">msdyn\_functionallocationtypes</span></span> | |
| <span data-ttu-id="ed45c-130">Fabricantes de gerenciamento de ativos</span><span class="sxs-lookup"><span data-stu-id="ed45c-130">Asset management manufacturers</span></span> | <span data-ttu-id="ed45c-131">msdyn\_manufacturers</span><span class="sxs-lookup"><span data-stu-id="ed45c-131">msdyn\_manufacturers</span></span> | |
| <span data-ttu-id="ed45c-132">Modelos de gerenciamento de ativo</span><span class="sxs-lookup"><span data-stu-id="ed45c-132">Asset management models</span></span> | <span data-ttu-id="ed45c-133">msdyn\_models</span><span class="sxs-lookup"><span data-stu-id="ed45c-133">msdyn\_models</span></span> | |
| <span data-ttu-id="ed45c-134">Garantia de gerenciamento de ativos</span><span class="sxs-lookup"><span data-stu-id="ed45c-134">Asset management warranty</span></span> | <span data-ttu-id="ed45c-135">msdyn\_warranties</span><span class="sxs-lookup"><span data-stu-id="ed45c-135">msdyn\_warranties</span></span> | |

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