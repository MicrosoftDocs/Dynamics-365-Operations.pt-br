---
title: Ativos internos para manutenção
description: Este tópico descreve como você pode usar o Microsoft Dynamics 365 Field Service para atender ativos de cliente e ativos internos.
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
ms.openlocfilehash: ebda6b5679ec601513fb6d046725b396e69fe0f3
ms.sourcegitcommit: a202bf67c3c2c054e2a47cb7b3145cb7c0ee635e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/25/2021
ms.locfileid: "5941405"
---
# <a name="in-house-assets-for-servicing"></a><span data-ttu-id="80b05-103">Ativos internos para manutenção</span><span class="sxs-lookup"><span data-stu-id="80b05-103">In-house assets for servicing</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="80b05-104">O Microsoft Dynamics 365 Field Service foi projetado para atender aos ativos dos clientes.</span><span class="sxs-lookup"><span data-stu-id="80b05-104">Microsoft Dynamics 365 Field Service is designed to service customer assets.</span></span> <span data-ttu-id="80b05-105">O Gerenciamento de ativos de Dynamics 365 Supply Chain Management for desenvolvido para manter ativos internos.</span><span class="sxs-lookup"><span data-stu-id="80b05-105">Asset management for Dynamics 365 Supply Chain Management is designed to maintain in-house assets.</span></span> <span data-ttu-id="80b05-106">A integração desses dois aplicativos permite usar o Field Service para atender tanto ativos do cliente como ativos internos.</span><span class="sxs-lookup"><span data-stu-id="80b05-106">Integration of these two apps lets you use Field Service to service both customer assets and in-house assets.</span></span> <span data-ttu-id="80b05-107">Também é possível classificar os ativos, com base no local funcional ou na hierarquia, e rastrear o serviço em um nível detalhado.</span><span class="sxs-lookup"><span data-stu-id="80b05-107">You can also classify the assets, based on functional location or hierarchy, and track the servicing at a detailed level.</span></span>

<span data-ttu-id="80b05-108">Para obter mais informações, consulte [Integras Dynamics 365 Field Service e Supply Chain Management](/dynamics365/field-service/supply-chain-field-service-integration).</span><span class="sxs-lookup"><span data-stu-id="80b05-108">For more information, see [Integrate Dynamics 365 Field Service and Supply Chain Management](/dynamics365/field-service/supply-chain-field-service-integration).</span></span>

## <a name="templates"></a><span data-ttu-id="80b05-109">Modelos</span><span class="sxs-lookup"><span data-stu-id="80b05-109">Templates</span></span>

<span data-ttu-id="80b05-110">Ativos internos incluem um conjunto de mapas de tabelas centrais que funcionam juntos durante a interação de dados, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="80b05-110">In-house-assets include a collection of core table maps that work together during data interaction, as shown in the following table.</span></span>

| <span data-ttu-id="80b05-111">Aplicativos Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="80b05-111">Finance and Operations apps</span></span> | <span data-ttu-id="80b05-112">Aplicativos controlados por modelos no Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="80b05-112">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="80b05-113">descrição</span><span class="sxs-lookup"><span data-stu-id="80b05-113">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="80b05-114">Modelos de ciclo de vida do ativo de gerenciamento de ativos</span><span class="sxs-lookup"><span data-stu-id="80b05-114">Asset management asset lifecycle models</span></span> | <span data-ttu-id="80b05-115">msdyn\_assetlifecyclemodels</span><span class="sxs-lookup"><span data-stu-id="80b05-115">msdyn\_assetlifecyclemodels</span></span> | |
| <span data-ttu-id="80b05-116">Estados de ciclo de vida do ativo de gerenciamento de ativos</span><span class="sxs-lookup"><span data-stu-id="80b05-116">Asset management asset lifecycle states</span></span> | <span data-ttu-id="80b05-117">msdyn\_assetlifecyclestates</span><span class="sxs-lookup"><span data-stu-id="80b05-117">msdyn\_assetlifecyclestates</span></span> | |
| <span data-ttu-id="80b05-118">Ativos de gerenciamento de ativo</span><span class="sxs-lookup"><span data-stu-id="80b05-118">Asset management assets</span></span> | <span data-ttu-id="80b05-119">msdyn\_customerassets</span><span class="sxs-lookup"><span data-stu-id="80b05-119">msdyn\_customerassets</span></span> | |
| <span data-ttu-id="80b05-120">Tipos de ativo de gerenciamento de ativo</span><span class="sxs-lookup"><span data-stu-id="80b05-120">Asset management asset types</span></span> | <span data-ttu-id="80b05-121">msdyn\_customerassetcategories</span><span class="sxs-lookup"><span data-stu-id="80b05-121">msdyn\_customerassetcategories</span></span> | |
| <span data-ttu-id="80b05-122">Modelos de ciclo de vida do local funcional de gerenciamento de ativos</span><span class="sxs-lookup"><span data-stu-id="80b05-122">Asset management functional location lifecycle models</span></span> | <span data-ttu-id="80b05-123">msdyn\_functionallocationlifecyclemodels</span><span class="sxs-lookup"><span data-stu-id="80b05-123">msdyn\_functionallocationlifecyclemodels</span></span> | |
| <span data-ttu-id="80b05-124">Estados de ciclo de vida do local funcional de gerenciamento de ativos</span><span class="sxs-lookup"><span data-stu-id="80b05-124">Asset management functional location lifecycle states</span></span> | <span data-ttu-id="80b05-125">msdyn\_functionallocationlifecyclestates</span><span class="sxs-lookup"><span data-stu-id="80b05-125">msdyn\_functionallocationlifecyclestates</span></span> | |
| <span data-ttu-id="80b05-126">Locais funcionais de gerenciamento de ativos</span><span class="sxs-lookup"><span data-stu-id="80b05-126">Asset management functional locations</span></span> | <span data-ttu-id="80b05-127">msdyn\_functionallocations</span><span class="sxs-lookup"><span data-stu-id="80b05-127">msdyn\_functionallocations</span></span> | |
| <span data-ttu-id="80b05-128">Tipos de locais funcionais de gerenciamento de ativos</span><span class="sxs-lookup"><span data-stu-id="80b05-128">Asset management functional location types</span></span> | <span data-ttu-id="80b05-129">msdyn\_functionallocationtypes</span><span class="sxs-lookup"><span data-stu-id="80b05-129">msdyn\_functionallocationtypes</span></span> | |
| <span data-ttu-id="80b05-130">Fabricantes de gerenciamento de ativos</span><span class="sxs-lookup"><span data-stu-id="80b05-130">Asset management manufacturers</span></span> | <span data-ttu-id="80b05-131">msdyn\_manufacturers</span><span class="sxs-lookup"><span data-stu-id="80b05-131">msdyn\_manufacturers</span></span> | |
| <span data-ttu-id="80b05-132">Modelos de gerenciamento de ativo</span><span class="sxs-lookup"><span data-stu-id="80b05-132">Asset management models</span></span> | <span data-ttu-id="80b05-133">msdyn\_models</span><span class="sxs-lookup"><span data-stu-id="80b05-133">msdyn\_models</span></span> | |
| <span data-ttu-id="80b05-134">Garantia de gerenciamento de ativos</span><span class="sxs-lookup"><span data-stu-id="80b05-134">Asset management warranty</span></span> | <span data-ttu-id="80b05-135">msdyn\_warranties</span><span class="sxs-lookup"><span data-stu-id="80b05-135">msdyn\_warranties</span></span> | |

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