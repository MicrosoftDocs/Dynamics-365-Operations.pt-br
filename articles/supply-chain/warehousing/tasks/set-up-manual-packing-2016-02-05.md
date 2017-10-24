--- 
title: Configurar a embalagem manual (somente fevereiro e maio de 2016)
description: "O processo de embalagem permite que você valide e empacote produtos em contêineres."
author: BibiSp
manager: AnnBe
ms.date: 11/04/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7f992a6a1655cd868d79228c490d59b46bfae715
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-manual-packing-february--may-2016-only"></a><span data-ttu-id="66e72-103">Configurar a embalagem manual (somente fevereiro e maio de 2016)</span><span class="sxs-lookup"><span data-stu-id="66e72-103">Set up manual packing (February & May 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="66e72-104">O processo de embalagem permite que você valide e empacote produtos em contêineres.</span><span class="sxs-lookup"><span data-stu-id="66e72-104">The packing process allows you to validate and pack products into containers.</span></span> <span data-ttu-id="66e72-105">Nesse processo, os trabalhadores do depósito escolhem produtos dos locais de depósito e os movem para uma estação de embalagem onde eles podem verificar as quantidades e tipos, e atribuí-los aos contêineres apropriados.</span><span class="sxs-lookup"><span data-stu-id="66e72-105">In this process, warehouse workers pick products from the storage locations and move them to a packing station where they check the item quantities and types, and assign them to appropriate containers.</span></span> <span data-ttu-id="66e72-106">Quando um contêiner é embalado totalmente, poderá fechá-lo e movê-lo para as docas de saída, e o produto está pronto para ser enviado.</span><span class="sxs-lookup"><span data-stu-id="66e72-106">When a container is fully packed, they can close it and move it to the outbound docks, and the products are ready to ship.</span></span> <span data-ttu-id="66e72-107">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="66e72-107">This procedure uses the USMF demo company.</span></span>


## <a name="set-up-location-profiles"></a><span data-ttu-id="66e72-108">Configurar perfis de localização</span><span class="sxs-lookup"><span data-stu-id="66e72-108">Set up location profiles</span></span>
1. <span data-ttu-id="66e72-109">Vá para Gerenciamento de depósito > Configuração > Depósito > Perfis de localização.</span><span class="sxs-lookup"><span data-stu-id="66e72-109">Go to Warehouse management > Setup > Warehouse > Location profiles.</span></span>
2. <span data-ttu-id="66e72-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="66e72-110">Click New.</span></span>
    * <span data-ttu-id="66e72-111">O perfil de local é usado para estações de embalagem e contém informações e as regras para um local.</span><span class="sxs-lookup"><span data-stu-id="66e72-111">The location profile is used for packing stations and contains information and rules for a location.</span></span>  
3. <span data-ttu-id="66e72-112">No campo ID do perfil de localização, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="66e72-112">In the Location profile ID field, type a value.</span></span>
4. <span data-ttu-id="66e72-113">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="66e72-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="66e72-114">No campo Formato de local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="66e72-114">In the Location format field, enter or select a value.</span></span>
6. <span data-ttu-id="66e72-115">No campo Tipo de local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="66e72-115">In the Location type field, enter or select a value.</span></span>
7. <span data-ttu-id="66e72-116">Selecione Sim no campo Permitir itens misturados.</span><span class="sxs-lookup"><span data-stu-id="66e72-116">Select Yes in the Allow mixed items field.</span></span>
8. <span data-ttu-id="66e72-117">Selecione Sim no campo Permitir status de estoque misturados.</span><span class="sxs-lookup"><span data-stu-id="66e72-117">Select Yes in the Allow mixed  inventory statuses field.</span></span>
9. <span data-ttu-id="66e72-118">Selecione Sim nas Regras de substituição para o campo de dias do lote.</span><span class="sxs-lookup"><span data-stu-id="66e72-118">Select Yes in the Override rules for batch days field.</span></span>
10. <span data-ttu-id="66e72-119">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="66e72-119">Close the page.</span></span>

## <a name="set-up-warehouse-management-parameters"></a><span data-ttu-id="66e72-120">Configurar parâmetros para gerenciamento de depósito</span><span class="sxs-lookup"><span data-stu-id="66e72-120">Set up warehouse management parameters</span></span> 
1. <span data-ttu-id="66e72-121">Vá para Gerenciamento de depósito > Configuração > Parâmetros de gerenciamento de depósito.</span><span class="sxs-lookup"><span data-stu-id="66e72-121">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="66e72-122">Clique na guia Pacote.</span><span class="sxs-lookup"><span data-stu-id="66e72-122">Click the Packing tab.</span></span>
3. <span data-ttu-id="66e72-123">No campo ID de perfil para local de pacote, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="66e72-123">In the Profile ID for packing location field, enter or select a value.</span></span>
    * <span data-ttu-id="66e72-124">Selecione o perfil de local que deseja usar para separação.</span><span class="sxs-lookup"><span data-stu-id="66e72-124">Select the location profile that you want to use for packing.</span></span>  
4. <span data-ttu-id="66e72-125">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="66e72-125">Close the page.</span></span>

## <a name="set-up-container-types"></a><span data-ttu-id="66e72-126">Configure tipos de contêiner</span><span class="sxs-lookup"><span data-stu-id="66e72-126">Set up container types</span></span>
1. <span data-ttu-id="66e72-127">Vá para Gerenciamento de depósito > Configuração > Recipientes > Tipos de recipiente.</span><span class="sxs-lookup"><span data-stu-id="66e72-127">Go to Warehouse management > Setup > Containers > Container types.</span></span>
2. <span data-ttu-id="66e72-128">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="66e72-128">Click New.</span></span>
    * <span data-ttu-id="66e72-129">É possível definir os tipos de contêineres a serem usados.</span><span class="sxs-lookup"><span data-stu-id="66e72-129">You can define the types of containers to use.</span></span> <span data-ttu-id="66e72-130">Você pode especificar as dimensões físicas do contêiner, incluindo o peso de tara, o peso máximo, o volume máximo, o tamanho, a largura, e o peso.</span><span class="sxs-lookup"><span data-stu-id="66e72-130">You can specify the physical dimensions of the container, including tare weight, maximum weight, maximum volume, length, width, and weight.</span></span>  <span data-ttu-id="66e72-131">Os Atributos são campos personalizáveis que permitem adicionar dimensões extra no tipo de contêiner.</span><span class="sxs-lookup"><span data-stu-id="66e72-131">The Attributes are customized fields that allow you to add extra dimensions on the container type.</span></span>     
3. <span data-ttu-id="66e72-132">No campo Código de tipo de contêiner, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="66e72-132">In the Container type code field, type a value.</span></span>
4. <span data-ttu-id="66e72-133">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="66e72-133">In the Description field, type a value.</span></span>
5. <span data-ttu-id="66e72-134">No campo Tara, insira um número.</span><span class="sxs-lookup"><span data-stu-id="66e72-134">In the Tare weight field, enter a number.</span></span>
6. <span data-ttu-id="66e72-135">No campo Peso máximo, insira um número.</span><span class="sxs-lookup"><span data-stu-id="66e72-135">In the Maximum weight field, enter a number.</span></span>
7. <span data-ttu-id="66e72-136">No campo Volume, insira um número.</span><span class="sxs-lookup"><span data-stu-id="66e72-136">In the Volume field, enter a number.</span></span>
8. <span data-ttu-id="66e72-137">No campo Comprimento, insira um número.</span><span class="sxs-lookup"><span data-stu-id="66e72-137">In the Length field, enter a number.</span></span>
9. <span data-ttu-id="66e72-138">No campo Largura, insira um número.</span><span class="sxs-lookup"><span data-stu-id="66e72-138">In the Width field, enter a number.</span></span>
10. <span data-ttu-id="66e72-139">No campo Altura, insira um número.</span><span class="sxs-lookup"><span data-stu-id="66e72-139">In the Height field, enter a number.</span></span>
11. <span data-ttu-id="66e72-140">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="66e72-140">Click Save.</span></span>
12. <span data-ttu-id="66e72-141">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="66e72-141">Close the page.</span></span>

## <a name="set-up-packing-profiles"></a><span data-ttu-id="66e72-142">Configurar perfis de embalagem</span><span class="sxs-lookup"><span data-stu-id="66e72-142">Set up packing profiles</span></span>
1. <span data-ttu-id="66e72-143">Vá para Gerenciamento de depósito > Configuração > Empacotamento > Perfis de empacotamento.</span><span class="sxs-lookup"><span data-stu-id="66e72-143">Go to Warehouse management > Setup > Packing > Packing profiles.</span></span>
2. <span data-ttu-id="66e72-144">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="66e72-144">Click New.</span></span>
3. <span data-ttu-id="66e72-145">No campo ID de perfil de pacote, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="66e72-145">In the Packing profile ID field, type a value.</span></span>
4. <span data-ttu-id="66e72-146">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="66e72-146">In the Description field, type a value.</span></span>
5. <span data-ttu-id="66e72-147">No campo ID de perfil de fechamento de Contêiner, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="66e72-147">In the Container closing profile ID field, enter or select a value.</span></span>
    * <span data-ttu-id="66e72-148">A identificação do perfil do fechamento do contêiner é opcional e é o novo perfil padrão do contêiner para o perfil de embalagem.</span><span class="sxs-lookup"><span data-stu-id="66e72-148">A container closing profile ID is optional and is the default close container profile for this packing profile.</span></span>  
6. <span data-ttu-id="66e72-149">No campo Modo de ID de contêiner, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="66e72-149">In the Container ID mode field, select an option.</span></span>
    * <span data-ttu-id="66e72-150">Esta opção determina se uma ID de contêiner será gerada automaticamente quando um contêiner é criado ou se uma ID de contêiner será criado manualmente.</span><span class="sxs-lookup"><span data-stu-id="66e72-150">This option determines whether a container ID will be automatically generated when a container is created or if a container ID will be created manually.</span></span>  
7. <span data-ttu-id="66e72-151">No campo Tipo de contêiner, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="66e72-151">In the Container type field, enter or select a value.</span></span>
    * <span data-ttu-id="66e72-152">O tipo de contêiner será usado por padrão quando um novo contêiner é criado.</span><span class="sxs-lookup"><span data-stu-id="66e72-152">The container type will be used by default when a new container is created.</span></span>  
8. <span data-ttu-id="66e72-153">Selecione a caixa de seleção Criar automaticamente contêiner no fechamento do contêiner.</span><span class="sxs-lookup"><span data-stu-id="66e72-153">Select the Autocreate container at container close check box.</span></span>
9. <span data-ttu-id="66e72-154">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="66e72-154">Click Save.</span></span>
10. <span data-ttu-id="66e72-155">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="66e72-155">Close the page.</span></span>

## <a name="set-up-container-closing-profiles"></a><span data-ttu-id="66e72-156">Configurar perfis de fechamento de contêiner</span><span class="sxs-lookup"><span data-stu-id="66e72-156">Set up container closing profiles</span></span>
1. <span data-ttu-id="66e72-157">Vá para Gerenciamento de depósito > Configuração > Recipientes > Perfis de fechamento de recipientes.</span><span class="sxs-lookup"><span data-stu-id="66e72-157">Go to Warehouse management > Setup > Containers > Container closing profiles.</span></span>
    * <span data-ttu-id="66e72-158">Os perfis de fechamento de contêiner definem o que acontece quando um contêiner é fechado.</span><span class="sxs-lookup"><span data-stu-id="66e72-158">Container closing profiles define what happens when a container is closed.</span></span> <span data-ttu-id="66e72-159">Você pode configurar perfis de contêiner múltiplos próximos.</span><span class="sxs-lookup"><span data-stu-id="66e72-159">You can set up multiple close container profiles.</span></span>       
2. <span data-ttu-id="66e72-160">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="66e72-160">Click New.</span></span>
3. <span data-ttu-id="66e72-161">No campo ID de perfil de fechamento de Contêiner, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="66e72-161">In the Container closing profile ID field, type a value.</span></span>
4. <span data-ttu-id="66e72-162">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="66e72-162">In the Description field, type a value.</span></span>
5. <span data-ttu-id="66e72-163">No campo Manifestar em, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="66e72-163">In the Manifest at field, select an option.</span></span>
    * <span data-ttu-id="66e72-164">Especifique se a manifestação ocorrerá ao fechar os contêineres ou ao confirmar a remessa.</span><span class="sxs-lookup"><span data-stu-id="66e72-164">Specify whether manifesting will occur when closing containers or when confirming the shipment.</span></span> <span data-ttu-id="66e72-165">Observe que a manifestação requer o gerenciamento de transporte.</span><span class="sxs-lookup"><span data-stu-id="66e72-165">Note that manifesting requires Transportation management.</span></span> <span data-ttu-id="66e72-166">A manifestação deve ser implementada nos mecanismos de transporte para que ela funcione.</span><span class="sxs-lookup"><span data-stu-id="66e72-166">Manifesting must be implemented in the transportation engines in order for it work.</span></span>  
6. <span data-ttu-id="66e72-167">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="66e72-167">In the Warehouse field, enter or select a value.</span></span>
7. <span data-ttu-id="66e72-168">No campo Local padrão para envio final, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="66e72-168">In the Default location for final shipment field, enter or select a value.</span></span>
    * <span data-ttu-id="66e72-169">Esse será o local para o qual os produtos serão movidos depois que os contêineres são fechados.</span><span class="sxs-lookup"><span data-stu-id="66e72-169">This will be location to which products will be moved after the containers are closed.</span></span> <span data-ttu-id="66e72-170">Esta localização deve ter um perfil de local definido nos Parâmetros de depósito.</span><span class="sxs-lookup"><span data-stu-id="66e72-170">This location must have a location profile defined on Warehouse parameters.</span></span>  
8. <span data-ttu-id="66e72-171">No campo Unidade de peso, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="66e72-171">In the Weight unit field, enter or select a value.</span></span>
9. <span data-ttu-id="66e72-172">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="66e72-172">Click Save.</span></span>


