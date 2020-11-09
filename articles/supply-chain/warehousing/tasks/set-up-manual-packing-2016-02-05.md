---
title: Configurar embalagem manual (fevereiro de 2016 e maio de 2016)
description: O processo de embalagem permite que você valide e empacote produtos em contêineres.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile, WHSParameters, WHSContainerType, WHSPackProfile, WHSCloseContainerProfile, InventLocationIdLookup, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 67e1e99b479752a027c60a878c57bd35d4219981
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017544"
---
# <a name="set-up-manual-packing-february-2016--may-2016"></a><span data-ttu-id="83cee-103">Configurar embalagem manual (fevereiro de 2016 e maio de 2016)</span><span class="sxs-lookup"><span data-stu-id="83cee-103">Set up manual packing (February 2016 & May 2016)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="83cee-104">O processo de embalagem permite que você valide e empacote produtos em contêineres.</span><span class="sxs-lookup"><span data-stu-id="83cee-104">The packing process allows you to validate and pack products into containers.</span></span> <span data-ttu-id="83cee-105">Nesse processo, os trabalhadores do depósito escolhem produtos dos locais de depósito e os movem para uma estação de embalagem onde eles podem verificar as quantidades e tipos, e atribuí-los aos contêineres apropriados.</span><span class="sxs-lookup"><span data-stu-id="83cee-105">In this process, warehouse workers pick products from the storage locations and move them to a packing station where they check the item quantities and types, and assign them to appropriate containers.</span></span> <span data-ttu-id="83cee-106">Quando um contêiner é embalado totalmente, poderá fechá-lo e movê-lo para as docas de saída, e o produto está pronto para ser enviado.</span><span class="sxs-lookup"><span data-stu-id="83cee-106">When a container is fully packed, they can close it and move it to the outbound docks, and the products are ready to ship.</span></span> <span data-ttu-id="83cee-107">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="83cee-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="83cee-108">Este procedimento é válido apenas para as versões de fevereiro de 2016 e maio de 2016 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="83cee-108">This procedure is for the February 2016 & May 2016 versions of Dynamics 365 for Operations only.</span></span>


## <a name="set-up-location-profiles"></a><span data-ttu-id="83cee-109">Configurar perfis de localização</span><span class="sxs-lookup"><span data-stu-id="83cee-109">Set up location profiles</span></span>
1. <span data-ttu-id="83cee-110">Vá para Gerenciamento de depósito > Configuração > Depósito > Perfis de localização.</span><span class="sxs-lookup"><span data-stu-id="83cee-110">Go to Warehouse management > Setup > Warehouse > Location profiles.</span></span>
2. <span data-ttu-id="83cee-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="83cee-111">Click New.</span></span>
    * <span data-ttu-id="83cee-112">O perfil de local é usado para estações de embalagem e contém informações e as regras para um local.</span><span class="sxs-lookup"><span data-stu-id="83cee-112">The location profile is used for packing stations and contains information and rules for a location.</span></span>  
3. <span data-ttu-id="83cee-113">No campo ID do perfil de localização, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="83cee-113">In the Location profile ID field, type a value.</span></span>
4. <span data-ttu-id="83cee-114">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="83cee-114">In the Name field, type a value.</span></span>
5. <span data-ttu-id="83cee-115">No campo Formato de local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="83cee-115">In the Location format field, enter or select a value.</span></span>
6. <span data-ttu-id="83cee-116">No campo Tipo de local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="83cee-116">In the Location type field, enter or select a value.</span></span>
7. <span data-ttu-id="83cee-117">Selecione Sim no campo Permitir itens misturados.</span><span class="sxs-lookup"><span data-stu-id="83cee-117">Select Yes in the Allow mixed items field.</span></span>
8. <span data-ttu-id="83cee-118">Selecione Sim no campo Permitir status de estoque misturados.</span><span class="sxs-lookup"><span data-stu-id="83cee-118">Select Yes in the Allow mixed  inventory statuses field.</span></span>
9. <span data-ttu-id="83cee-119">Selecione Sim nas Regras de substituição para o campo de dias do lote.</span><span class="sxs-lookup"><span data-stu-id="83cee-119">Select Yes in the Override rules for batch days field.</span></span>
10. <span data-ttu-id="83cee-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="83cee-120">Close the page.</span></span>

## <a name="set-up-warehouse-management-parameters"></a><span data-ttu-id="83cee-121">Configurar parâmetros para gerenciamento de depósito</span><span class="sxs-lookup"><span data-stu-id="83cee-121">Set up warehouse management parameters</span></span> 
1. <span data-ttu-id="83cee-122">Vá para Gerenciamento de depósito > Configuração > Parâmetros de gerenciamento de depósito.</span><span class="sxs-lookup"><span data-stu-id="83cee-122">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="83cee-123">Clique na guia Pacote.</span><span class="sxs-lookup"><span data-stu-id="83cee-123">Click the Packing tab.</span></span>
3. <span data-ttu-id="83cee-124">No campo ID de perfil para local de pacote, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="83cee-124">In the Profile ID for packing location field, enter or select a value.</span></span>
    * <span data-ttu-id="83cee-125">Selecione o perfil de local que deseja usar para separação.</span><span class="sxs-lookup"><span data-stu-id="83cee-125">Select the location profile that you want to use for packing.</span></span>  
4. <span data-ttu-id="83cee-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="83cee-126">Close the page.</span></span>

## <a name="set-up-container-types"></a><span data-ttu-id="83cee-127">Configure tipos de contêiner</span><span class="sxs-lookup"><span data-stu-id="83cee-127">Set up container types</span></span>
1. <span data-ttu-id="83cee-128">Vá para Gerenciamento de depósito > Configuração > Recipientes > Tipos de recipiente.</span><span class="sxs-lookup"><span data-stu-id="83cee-128">Go to Warehouse management > Setup > Containers > Container types.</span></span>
2. <span data-ttu-id="83cee-129">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="83cee-129">Click New.</span></span>
    * <span data-ttu-id="83cee-130">É possível definir os tipos de contêineres a serem usados.</span><span class="sxs-lookup"><span data-stu-id="83cee-130">You can define the types of containers to use.</span></span> <span data-ttu-id="83cee-131">Você pode especificar as dimensões físicas do contêiner, incluindo o peso de tara, o peso máximo, o volume máximo, o tamanho, a largura, e o peso.</span><span class="sxs-lookup"><span data-stu-id="83cee-131">You can specify the physical dimensions of the container, including tare weight, maximum weight, maximum volume, length, width, and weight.</span></span>  <span data-ttu-id="83cee-132">Os Atributos são campos personalizáveis que permitem adicionar dimensões extra no tipo de contêiner.</span><span class="sxs-lookup"><span data-stu-id="83cee-132">The Attributes are customized fields that allow you to add extra dimensions on the container type.</span></span>     
3. <span data-ttu-id="83cee-133">No campo Código de tipo de contêiner, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="83cee-133">In the Container type code field, type a value.</span></span>
4. <span data-ttu-id="83cee-134">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="83cee-134">In the Description field, type a value.</span></span>
5. <span data-ttu-id="83cee-135">No campo Tara, insira um número.</span><span class="sxs-lookup"><span data-stu-id="83cee-135">In the Tare weight field, enter a number.</span></span>
6. <span data-ttu-id="83cee-136">No campo Peso máximo, insira um número.</span><span class="sxs-lookup"><span data-stu-id="83cee-136">In the Maximum weight field, enter a number.</span></span>
7. <span data-ttu-id="83cee-137">No campo Volume, insira um número.</span><span class="sxs-lookup"><span data-stu-id="83cee-137">In the Volume field, enter a number.</span></span>
8. <span data-ttu-id="83cee-138">No campo Comprimento, insira um número.</span><span class="sxs-lookup"><span data-stu-id="83cee-138">In the Length field, enter a number.</span></span>
9. <span data-ttu-id="83cee-139">No campo Largura, insira um número.</span><span class="sxs-lookup"><span data-stu-id="83cee-139">In the Width field, enter a number.</span></span>
10. <span data-ttu-id="83cee-140">No campo Altura, insira um número.</span><span class="sxs-lookup"><span data-stu-id="83cee-140">In the Height field, enter a number.</span></span>
11. <span data-ttu-id="83cee-141">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="83cee-141">Click Save.</span></span>
12. <span data-ttu-id="83cee-142">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="83cee-142">Close the page.</span></span>

## <a name="set-up-packing-profiles"></a><span data-ttu-id="83cee-143">Configurar perfis de embalagem</span><span class="sxs-lookup"><span data-stu-id="83cee-143">Set up packing profiles</span></span>
1. <span data-ttu-id="83cee-144">Vá para Gerenciamento de depósito > Configuração > Empacotamento > Perfis de empacotamento.</span><span class="sxs-lookup"><span data-stu-id="83cee-144">Go to Warehouse management > Setup > Packing > Packing profiles.</span></span>
2. <span data-ttu-id="83cee-145">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="83cee-145">Click New.</span></span>
3. <span data-ttu-id="83cee-146">No campo ID de perfil de pacote, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="83cee-146">In the Packing profile ID field, type a value.</span></span>
4. <span data-ttu-id="83cee-147">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="83cee-147">In the Description field, type a value.</span></span>
5. <span data-ttu-id="83cee-148">No campo ID de perfil de fechamento de Contêiner, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="83cee-148">In the Container closing profile ID field, enter or select a value.</span></span>
    * <span data-ttu-id="83cee-149">A identificação do perfil do fechamento do contêiner é opcional e é o novo perfil padrão do contêiner para o perfil de embalagem.</span><span class="sxs-lookup"><span data-stu-id="83cee-149">A container closing profile ID is optional and is the default close container profile for this packing profile.</span></span>  
6. <span data-ttu-id="83cee-150">No campo Modo de ID de contêiner, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="83cee-150">In the Container ID mode field, select an option.</span></span>
    * <span data-ttu-id="83cee-151">Esta opção determina se uma ID de contêiner será gerada automaticamente quando um contêiner é criado ou se uma ID de contêiner será criado manualmente.</span><span class="sxs-lookup"><span data-stu-id="83cee-151">This option determines whether a container ID will be automatically generated when a container is created or if a container ID will be created manually.</span></span>  
7. <span data-ttu-id="83cee-152">No campo Tipo de contêiner, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="83cee-152">In the Container type field, enter or select a value.</span></span>
    * <span data-ttu-id="83cee-153">O tipo de contêiner será usado por padrão quando um novo contêiner é criado.</span><span class="sxs-lookup"><span data-stu-id="83cee-153">The container type will be used by default when a new container is created.</span></span>  
8. <span data-ttu-id="83cee-154">Selecione a caixa de seleção Criar automaticamente contêiner no fechamento do contêiner.</span><span class="sxs-lookup"><span data-stu-id="83cee-154">Select the Autocreate container at container close check box.</span></span>
9. <span data-ttu-id="83cee-155">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="83cee-155">Click Save.</span></span>
10. <span data-ttu-id="83cee-156">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="83cee-156">Close the page.</span></span>

## <a name="set-up-container-closing-profiles"></a><span data-ttu-id="83cee-157">Configurar perfis de fechamento de contêiner</span><span class="sxs-lookup"><span data-stu-id="83cee-157">Set up container closing profiles</span></span>
1. <span data-ttu-id="83cee-158">Vá para Gerenciamento de depósito > Configuração > Recipientes > Perfis de fechamento de recipientes.</span><span class="sxs-lookup"><span data-stu-id="83cee-158">Go to Warehouse management > Setup > Containers > Container closing profiles.</span></span>
    * <span data-ttu-id="83cee-159">Os perfis de fechamento de contêiner definem o que acontece quando um contêiner é fechado.</span><span class="sxs-lookup"><span data-stu-id="83cee-159">Container closing profiles define what happens when a container is closed.</span></span> <span data-ttu-id="83cee-160">Você pode configurar perfis de contêiner múltiplos próximos.</span><span class="sxs-lookup"><span data-stu-id="83cee-160">You can set up multiple close container profiles.</span></span>       
2. <span data-ttu-id="83cee-161">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="83cee-161">Click New.</span></span>
3. <span data-ttu-id="83cee-162">No campo ID de perfil de fechamento de Contêiner, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="83cee-162">In the Container closing profile ID field, type a value.</span></span>
4. <span data-ttu-id="83cee-163">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="83cee-163">In the Description field, type a value.</span></span>
5. <span data-ttu-id="83cee-164">No campo Manifestar em, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="83cee-164">In the Manifest at field, select an option.</span></span>
    * <span data-ttu-id="83cee-165">Especifique se a manifestação ocorrerá ao fechar os contêineres ou ao confirmar a remessa.</span><span class="sxs-lookup"><span data-stu-id="83cee-165">Specify whether manifesting will occur when closing containers or when confirming the shipment.</span></span> <span data-ttu-id="83cee-166">Observe que a manifestação requer o gerenciamento de transporte.</span><span class="sxs-lookup"><span data-stu-id="83cee-166">Note that manifesting requires Transportation management.</span></span> <span data-ttu-id="83cee-167">A manifestação deve ser implementada nos mecanismos de transporte para que ela funcione.</span><span class="sxs-lookup"><span data-stu-id="83cee-167">Manifesting must be implemented in the transportation engines in order for it work.</span></span>  
6. <span data-ttu-id="83cee-168">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="83cee-168">In the Warehouse field, enter or select a value.</span></span>
7. <span data-ttu-id="83cee-169">No campo Local padrão para envio final, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="83cee-169">In the Default location for final shipment field, enter or select a value.</span></span>
    * <span data-ttu-id="83cee-170">Esse será o local para o qual os produtos serão movidos depois que os contêineres são fechados.</span><span class="sxs-lookup"><span data-stu-id="83cee-170">This will be location to which products will be moved after the containers are closed.</span></span> <span data-ttu-id="83cee-171">Esta localização deve ter um perfil de local definido nos Parâmetros de depósito.</span><span class="sxs-lookup"><span data-stu-id="83cee-171">This location must have a location profile defined on Warehouse parameters.</span></span>  
8. <span data-ttu-id="83cee-172">No campo Unidade de peso, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="83cee-172">In the Weight unit field, enter or select a value.</span></span>
9. <span data-ttu-id="83cee-173">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="83cee-173">Click Save.</span></span>

