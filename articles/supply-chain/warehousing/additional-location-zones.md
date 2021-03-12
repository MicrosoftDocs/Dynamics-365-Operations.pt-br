---
title: Zonas de localização adicionais
description: Este tópico mostra uma visão geral das novas zonas de localização que foram adicionadas ao Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationBuild, WHSZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 662725edf5bf8d95be038f7c989b73d8d05fa0df
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996417"
---
# <a name="additional-location-zones"></a><span data-ttu-id="034f9-103">Zonas de localização adicionais</span><span class="sxs-lookup"><span data-stu-id="034f9-103">Additional location zones</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="034f9-104">Três novos campos de zona estão disponíveis no Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="034f9-104">Three new zone fields are available in Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="034f9-105">Os gerentes de depósito podem usá-los para definir organizações ou layouts de depósito adicionais.</span><span class="sxs-lookup"><span data-stu-id="034f9-105">Warehouse managers can use them to define additional warehouse organizations or layouts.</span></span> <span data-ttu-id="034f9-106">Os novos campos de zona podem ser definidos manualmente ou usando o assistente **Configuração de localização**.</span><span class="sxs-lookup"><span data-stu-id="034f9-106">The new zone fields can be set either manually or by using the **Location setup** wizard.</span></span> <span data-ttu-id="034f9-107">Eles podem ser usados em qualquer consulta ou filtragem que utiliza a tabela Localizações.</span><span class="sxs-lookup"><span data-stu-id="034f9-107">They can be used in any query or filtering that uses the Locations table.</span></span>

<span data-ttu-id="034f9-108">Nenhuma configuração adicional é necessária para usar os campos de zona.</span><span class="sxs-lookup"><span data-stu-id="034f9-108">No additional setup is required to use the zone fields.</span></span>

## <a name="turn-on-the-additional-location-zone-feature"></a><span data-ttu-id="034f9-109">Ativar o recurso Zona de localização adicional</span><span class="sxs-lookup"><span data-stu-id="034f9-109">Turn on the Additional location zone feature</span></span>

<span data-ttu-id="034f9-110">Para que você possa usar o recurso *Zona de localização adicional*, ele deve estar ativado no sistema.</span><span class="sxs-lookup"><span data-stu-id="034f9-110">Before you can use the *Additional location zone* feature, it must be turned on in your system.</span></span> <span data-ttu-id="034f9-111">Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo se necessário.</span><span class="sxs-lookup"><span data-stu-id="034f9-111">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="034f9-112">No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="034f9-112">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="034f9-113">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="034f9-113">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="034f9-114">**Nome do recurso:** *Zona de localização adicional*</span><span class="sxs-lookup"><span data-stu-id="034f9-114">**Feature name:** *Additional location zone*</span></span>

## <a name="use-location-zones"></a><span data-ttu-id="034f9-115">Usar zonas de localização</span><span class="sxs-lookup"><span data-stu-id="034f9-115">Use location zones</span></span>

1. <span data-ttu-id="034f9-116">Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Assistente de configuração de localização**.</span><span class="sxs-lookup"><span data-stu-id="034f9-116">Go to **Warehouse management \> Setup \> Warehouse \> Location setup wizard**.</span></span>
2. <span data-ttu-id="034f9-117">Defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="034f9-117">Set the following values:</span></span>

    - <span data-ttu-id="034f9-118">No campo **Depósito**, selecione _62_.</span><span class="sxs-lookup"><span data-stu-id="034f9-118">In the **Warehouse** field, select _62_.</span></span>
    - <span data-ttu-id="034f9-119">No campo **ID da zona**, selecione _CHÃO_.</span><span class="sxs-lookup"><span data-stu-id="034f9-119">In the **Zone ID** field, select _FLOOR_.</span></span>
    - <span data-ttu-id="034f9-120">No campo **Zona Adicional 1**, selecione _PICKZONE1_.</span><span class="sxs-lookup"><span data-stu-id="034f9-120">In the **Additional Zone 1** field, select _PICKZONE1_.</span></span>
    - <span data-ttu-id="034f9-121">No campo **Zona Adicional 2**, selecione _WEBSHOP1_.</span><span class="sxs-lookup"><span data-stu-id="034f9-121">In the **Additional Zone 2** field, select _WEBSHOP1_.</span></span>
    - <span data-ttu-id="034f9-122">No campo **ID do perfil de localização**, selecione _FLOOR_.</span><span class="sxs-lookup"><span data-stu-id="034f9-122">In the **Location profile ID** field, select _FLOOR_.</span></span>

3. <span data-ttu-id="034f9-123">Selecione a linha **Chão**.</span><span class="sxs-lookup"><span data-stu-id="034f9-123">Select the **Floor** line.</span></span>
4. <span data-ttu-id="034f9-124">No campo **Número inicial**, insira _1_.</span><span class="sxs-lookup"><span data-stu-id="034f9-124">In the **From number** field, enter _1_.</span></span> <span data-ttu-id="034f9-125">No campo **Número final**, insira _3_.</span><span class="sxs-lookup"><span data-stu-id="034f9-125">In the **To number** field, enter _3_.</span></span>
5. <span data-ttu-id="034f9-126">Selecione a linha **Corredor**.</span><span class="sxs-lookup"><span data-stu-id="034f9-126">Select the **Aisle** line.</span></span>
6. <span data-ttu-id="034f9-127">No campo **Número inicial**, insira _1_.</span><span class="sxs-lookup"><span data-stu-id="034f9-127">In the **From number** field, enter _1_.</span></span> <span data-ttu-id="034f9-128">No campo **Número final**, insira _5_.</span><span class="sxs-lookup"><span data-stu-id="034f9-128">In the **To number** field, enter _5_.</span></span>
7. <span data-ttu-id="034f9-129">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="034f9-129">Select **Create**.</span></span>
8. <span data-ttu-id="034f9-130">Você recebe mensagens indicando que novas localizações foram adicionadas.</span><span class="sxs-lookup"><span data-stu-id="034f9-130">You receive messages that state that new locations have been added.</span></span> <span data-ttu-id="034f9-131">Selecione o botão **Mostrar mensagens** para exibir as mensagens.</span><span class="sxs-lookup"><span data-stu-id="034f9-131">Select the **Show messages** button to view the messages.</span></span>
9. <span data-ttu-id="034f9-132">Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Localizações**.</span><span class="sxs-lookup"><span data-stu-id="034f9-132">Go to **Warehouse management \> Setup \> Warehouse \> Locations**.</span></span> <span data-ttu-id="034f9-133">As novas localizações serão exibidas na lista, e todos os campos de zona estarão disponíveis (ou seja, o campo de zona existente e os novos campos de zona adicionais).</span><span class="sxs-lookup"><span data-stu-id="034f9-133">The new locations appear in the list, and all zone fields are available (that is, the existing zone field and the new additional zone fields).</span></span>
