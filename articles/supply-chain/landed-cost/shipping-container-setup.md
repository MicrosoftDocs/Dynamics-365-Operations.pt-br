---
title: Contêineres de remessa
description: Este tópico descreve como configurar contêineres de remessa para o módulo Custo de entrega.
author: sherry-zheng
manager: tfehr
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMContainerTypeTable, ITMContainerTable, ITMContainerUnitTypeTable, ITMRefrigerationTypeTable, ITMContainersListPage, ITMContainers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: ca712aa7f07792861d5ba36afd8d7b63cc9ce8fb
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500949"
---
# <a name="shipping-container-setup"></a><span data-ttu-id="184f0-103">Configuração de contêineres de remessa</span><span class="sxs-lookup"><span data-stu-id="184f0-103">Shipping container setup</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="184f0-104">Este tópico descreve como configurar contêineres de remessa para o módulo **Custo de entrega**.</span><span class="sxs-lookup"><span data-stu-id="184f0-104">This topic describes how to set up shipping containers for the **Landed cost** module.</span></span>

## <a name="set-up-shipping-container-types"></a><a id="shipping-container-types"></a><span data-ttu-id="184f0-105">Configurar tipos de contêineres de remessa</span><span class="sxs-lookup"><span data-stu-id="184f0-105">Set up shipping container types</span></span>

<span data-ttu-id="184f0-106">Os tipos de contêineres de remessa definem os tipos de contêineres de remessa disponíveis para uso durante remessas e viagens.</span><span class="sxs-lookup"><span data-stu-id="184f0-106">Shipping container types define the types of shipping containers that are available for use during shipping and voyages.</span></span>

<span data-ttu-id="184f0-107">Para trabalhar com os tipos de contêineres de remessa, vá para **Custo de entrega \> Configuração de contêineres \> Tipos de contêineres de remessa**.</span><span class="sxs-lookup"><span data-stu-id="184f0-107">To work with the shipping container types, go to **Landed cost \> Containers setup \> Shipping container types**.</span></span> <span data-ttu-id="184f0-108">Lá, você pode exibir, adicionar e remover registros para os seus tipos de contêineres.</span><span class="sxs-lookup"><span data-stu-id="184f0-108">There, you can view, add, and remove records for your container types.</span></span> <span data-ttu-id="184f0-109">A tabela a seguir descreve os campos disponíveis para cada registro.</span><span class="sxs-lookup"><span data-stu-id="184f0-109">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="184f0-110">Campo</span><span class="sxs-lookup"><span data-stu-id="184f0-110">Field</span></span> | <span data-ttu-id="184f0-111">descrição</span><span class="sxs-lookup"><span data-stu-id="184f0-111">Description</span></span> |
|---|---|
| <span data-ttu-id="184f0-112">Tipo de contêiner de remessa</span><span class="sxs-lookup"><span data-stu-id="184f0-112">Shipping container type</span></span> | <span data-ttu-id="184f0-113">Insira um nome/número de identificação exclusivo para o tipo de contêiner de remessa.</span><span class="sxs-lookup"><span data-stu-id="184f0-113">Enter a unique identification name/number for the shipping container type.</span></span> |
| <span data-ttu-id="184f0-114">descrição</span><span class="sxs-lookup"><span data-stu-id="184f0-114">Description</span></span> | <span data-ttu-id="184f0-115">Insira uma descrição do tipo de contêiner de remessa.</span><span class="sxs-lookup"><span data-stu-id="184f0-115">Enter a description of the shipping container type.</span></span> |
| <span data-ttu-id="184f0-116">Volume</span><span class="sxs-lookup"><span data-stu-id="184f0-116">Volume</span></span> | <span data-ttu-id="184f0-117">Insira o volume máximo permitido em contêineres de remessa deste tipo.</span><span class="sxs-lookup"><span data-stu-id="184f0-117">Enter the maximum volume that is allowed in shipping containers of this type.</span></span> |
| <span data-ttu-id="184f0-118">Peso</span><span class="sxs-lookup"><span data-stu-id="184f0-118">Weight</span></span> | <span data-ttu-id="184f0-119">Insira o peso máximo permitido em contêineres de remessa deste tipo.</span><span class="sxs-lookup"><span data-stu-id="184f0-119">Enter the maximum weight that is allowed in shipping containers of this type.</span></span> |
| <span data-ttu-id="184f0-120">Retornável</span><span class="sxs-lookup"><span data-stu-id="184f0-120">Returnable</span></span> | <span data-ttu-id="184f0-121">Especifique se os contêineres de remessa deste tipo podem ser devolvidos ao fornecedor depois de serem usados durante uma viagem.</span><span class="sxs-lookup"><span data-stu-id="184f0-121">Specify whether shipping containers of this type can be returned to the vendor after they are used during a voyage.</span></span> <span data-ttu-id="184f0-122">Se essa opção for definida como *Sim*, custos adicionais poderão ser aplicados para a devolução de contêineres de remessa deste tipo ao porto de origem.</span><span class="sxs-lookup"><span data-stu-id="184f0-122">If this option is set to *Yes*, additional costs might apply for the return of shipping containers of this type to the port of origin.</span></span> |

## <a name="set-up-shipping-containers"></a><span data-ttu-id="184f0-123">Configurar contêineres de remessa</span><span class="sxs-lookup"><span data-stu-id="184f0-123">Set up shipping containers</span></span>

<span data-ttu-id="184f0-124">Você usa registros de contêineres de remessa para identificar cada contêiner usado durante as viagens.</span><span class="sxs-lookup"><span data-stu-id="184f0-124">You use shipping container records to identify each container that you use during voyages.</span></span> <span data-ttu-id="184f0-125">Ao criar uma viagem, é possível selecionar um contêiner específico para ela na lista de todos os registros de contêineres de remessa que você definiu aqui.</span><span class="sxs-lookup"><span data-stu-id="184f0-125">When you create a voyage, you can select a specific container for it in the list of all the shipping container records that you've defined here.</span></span> <span data-ttu-id="184f0-126">Esse recurso é especialmente útil se a empresa tiver seus próprios contêineres de remessa.</span><span class="sxs-lookup"><span data-stu-id="184f0-126">This feature is especially useful if your company owns its own shipping containers.</span></span>

<span data-ttu-id="184f0-127">Não é necessário inserir números de contêineres de remessa para contêineres de remessa que serão usados apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="184f0-127">You don't have to enter shipping container numbers for shipping containers that will be used only one time.</span></span> <span data-ttu-id="184f0-128">Em vez disso, você pode adicionar o número do contêiner de remessa quando criar uma viagem.</span><span class="sxs-lookup"><span data-stu-id="184f0-128">Instead, you can add the shipping container number when you create a voyage.</span></span>

<span data-ttu-id="184f0-129">Os registros dos contêineres de remessa são usados somente no Custo de entrega.</span><span class="sxs-lookup"><span data-stu-id="184f0-129">Shipping container records are used only in Landed cost.</span></span> <span data-ttu-id="184f0-130">Eles não estão disponíveis no módulo **Gerenciamento de transporte** (TMS) padrão.</span><span class="sxs-lookup"><span data-stu-id="184f0-130">They aren't available in the standard **Transportation management** module (TMS).</span></span>

<span data-ttu-id="184f0-131">Para trabalhar com contêineres de remessa, vá para **Custo de entrega \> Configuração de contêineres \> Contêineres de remessa**.</span><span class="sxs-lookup"><span data-stu-id="184f0-131">To work with shipping containers, go to **Landed cost \> Containers setup \> Shipping containers**.</span></span> <span data-ttu-id="184f0-132">Lá, você pode exibir, adicionar e remover registros para os seus contêineres de remessa.</span><span class="sxs-lookup"><span data-stu-id="184f0-132">There, you can view, add, and remove records your shipping containers.</span></span> <span data-ttu-id="184f0-133">A tabela a seguir descreve os campos disponíveis para cada registro.</span><span class="sxs-lookup"><span data-stu-id="184f0-133">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="184f0-134">Campo</span><span class="sxs-lookup"><span data-stu-id="184f0-134">Field</span></span> | <span data-ttu-id="184f0-135">descrição</span><span class="sxs-lookup"><span data-stu-id="184f0-135">Description</span></span> |
|---|---|
| <span data-ttu-id="184f0-136">Contêiner de remessa</span><span class="sxs-lookup"><span data-stu-id="184f0-136">Shipping container</span></span> | <span data-ttu-id="184f0-137">Insira um nome/número de identificação exclusivo para o contêiner de remessa.</span><span class="sxs-lookup"><span data-stu-id="184f0-137">Enter a unique identification name/number for the shipping container.</span></span> |
| <span data-ttu-id="184f0-138">Tipo de contêiner de remessa</span><span class="sxs-lookup"><span data-stu-id="184f0-138">Shipping container type</span></span> | <span data-ttu-id="184f0-139">Selecione o tipo de contêiner de remessa.</span><span class="sxs-lookup"><span data-stu-id="184f0-139">Select the type of shipping container.</span></span> <span data-ttu-id="184f0-140">Para obter mais informações, consulte a seção [Configurar tipos de contêineres de remessa](#shipping-container-types) anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="184f0-140">For more information, see the [Set up shipping container types](#shipping-container-types) section earlier in this topic.</span></span> |

> [!NOTE]
> - <span data-ttu-id="184f0-141">A configuração de contêineres de remessa é opcional.</span><span class="sxs-lookup"><span data-stu-id="184f0-141">The shipping container setup is optional.</span></span> <span data-ttu-id="184f0-142">Normalmente, ela será usada somente se a empresa tiver seus próprios contêineres de remessa ou reutilizar os mesmos contêineres de remessa com frequência.</span><span class="sxs-lookup"><span data-stu-id="184f0-142">Typically, you will use it only if your company owns its own shipping containers or often reuses the same shipping containers.</span></span>
> - <span data-ttu-id="184f0-143">Nenhum dígito de verificação é calculado para números de contêineres de remessa.</span><span class="sxs-lookup"><span data-stu-id="184f0-143">No check digits are calculated for shipping container numbers.</span></span>

## <a name="set-up-unit-types"></a><a name="unit-types"></a><span data-ttu-id="184f0-144">Configurar tipos de unidades</span><span class="sxs-lookup"><span data-stu-id="184f0-144">Set up unit types</span></span>

<span data-ttu-id="184f0-145">Os tipos de unidades estabelecem agrupamentos e métodos de identificação adicionais para contêineres de remessa.</span><span class="sxs-lookup"><span data-stu-id="184f0-145">Unit types establish additional groupings and identification methods for shipping containers.</span></span> <span data-ttu-id="184f0-146">Normalmente, o tipo de unidade é usado para identificar o tipo de contêiner em que as mercadorias são embaladas, como paletes ou tambores.</span><span class="sxs-lookup"><span data-stu-id="184f0-146">The unit type is typically used to identify the type of container that goods are packaged in, such as pallets or drums.</span></span> <span data-ttu-id="184f0-147">Você pode selecionar um tipo de unidade ao configurar um contêiner na página **Todos os contêineres de remessa**.</span><span class="sxs-lookup"><span data-stu-id="184f0-147">You can select a unit type when you set up a container on the **All shipping containers** page.</span></span>

<span data-ttu-id="184f0-148">Os tipos de unidades são usados somente no Custo de entrega.</span><span class="sxs-lookup"><span data-stu-id="184f0-148">Unit types are used only in Landed cost.</span></span> <span data-ttu-id="184f0-149">Eles não estão disponíveis no TMS.</span><span class="sxs-lookup"><span data-stu-id="184f0-149">They aren't available in TMS.</span></span>

<span data-ttu-id="184f0-150">Para trabalhar com tipos de unidades, vá para **Custo de entrega \> Configuração de contêineres \> Tipos de unidades**.</span><span class="sxs-lookup"><span data-stu-id="184f0-150">To work with unit types, go to **Landed cost \> Containers setup \> Unit types**.</span></span> <span data-ttu-id="184f0-151">Lá, você pode exibir, adicionar e remover registros para os seus tipos de unidades.</span><span class="sxs-lookup"><span data-stu-id="184f0-151">There, you can view, add, and remove records for your unit types.</span></span> <span data-ttu-id="184f0-152">A tabela a seguir descreve os campos disponíveis para cada registro.</span><span class="sxs-lookup"><span data-stu-id="184f0-152">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="184f0-153">Campo</span><span class="sxs-lookup"><span data-stu-id="184f0-153">Field</span></span> | <span data-ttu-id="184f0-154">descrição</span><span class="sxs-lookup"><span data-stu-id="184f0-154">Description</span></span> |
|---|---|
| <span data-ttu-id="184f0-155">Tipo de Unidade</span><span class="sxs-lookup"><span data-stu-id="184f0-155">Unit type</span></span> | <span data-ttu-id="184f0-156">Insira um nome/número de identificação exclusivo para o tipo de unidade.</span><span class="sxs-lookup"><span data-stu-id="184f0-156">Enter a unique identification name/number for the unit type.</span></span> |
| <span data-ttu-id="184f0-157">descrição</span><span class="sxs-lookup"><span data-stu-id="184f0-157">Description</span></span> | <span data-ttu-id="184f0-158">Insira uma descrição do tipo de unidade.</span><span class="sxs-lookup"><span data-stu-id="184f0-158">Enter a description of the unit type.</span></span> |

## <a name="set-up-refrigeration-types"></a><a name="refrigeration-types"></a><span data-ttu-id="184f0-159">Configurar tipos de refrigeração</span><span class="sxs-lookup"><span data-stu-id="184f0-159">Set up refrigeration types</span></span>

<span data-ttu-id="184f0-160">Os tipos de refrigeração estabelecem agrupamentos e métodos de identificação adicionais para contêineres de remessa (normalmente contêineres refrigerados).</span><span class="sxs-lookup"><span data-stu-id="184f0-160">Refrigeration types establish additional groupings and identification methods for shipping containers (usually refrigerated containers).</span></span> <span data-ttu-id="184f0-161">Você pode selecionar um tipo de refrigeração ao configurar um contêiner na página **Todos os contêineres de remessa**.</span><span class="sxs-lookup"><span data-stu-id="184f0-161">You can select a refrigeration type when you set up a container on the **All shipping containers** page.</span></span>

<span data-ttu-id="184f0-162">Para trabalhar com tipos de refrigeração, vá para **Custo de entrega \> Configuração de contêineres \> Tipos de refrigeração**.</span><span class="sxs-lookup"><span data-stu-id="184f0-162">To work with refrigeration types, go to **Landed cost \> Containers setup \> Refrigeration types**.</span></span> <span data-ttu-id="184f0-163">Lá, você pode exibir, adicionar e remover registros para os seus tipos de refrigeração.</span><span class="sxs-lookup"><span data-stu-id="184f0-163">There, you can view, add, and remove records for your refrigeration types.</span></span> <span data-ttu-id="184f0-164">A tabela a seguir descreve os campos disponíveis para cada registro.</span><span class="sxs-lookup"><span data-stu-id="184f0-164">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="184f0-165">Campo</span><span class="sxs-lookup"><span data-stu-id="184f0-165">Field</span></span> | <span data-ttu-id="184f0-166">descrição</span><span class="sxs-lookup"><span data-stu-id="184f0-166">Description</span></span> |
|---|---|
| <span data-ttu-id="184f0-167">Tipo de refrigeração</span><span class="sxs-lookup"><span data-stu-id="184f0-167">Refrigeration type</span></span> | <span data-ttu-id="184f0-168">Insira um nome/número de identificação exclusivo para o tipo de refrigeração.</span><span class="sxs-lookup"><span data-stu-id="184f0-168">Enter a unique identification name/number for the refrigeration type.</span></span> |
| <span data-ttu-id="184f0-169">descrição</span><span class="sxs-lookup"><span data-stu-id="184f0-169">Description</span></span> | <span data-ttu-id="184f0-170">Insira uma descrição do tipo de refrigeração.</span><span class="sxs-lookup"><span data-stu-id="184f0-170">Enter a description of the refrigeration type.</span></span> |
