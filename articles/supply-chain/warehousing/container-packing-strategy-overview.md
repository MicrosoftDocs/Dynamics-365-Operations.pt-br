---
title: Estratégias de embalagem de contêineres
description: Este tópico descreve as diferenças entre as estratégias de embalagem de contêineres e fornece exemplos.
author: GalynaFedorova
ms.date: 06/11/2021
ms.topic: article
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak, WHSContainerStructure, WHSContainerTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: f481f6ca047ee0285fe0e81d8fa96665e9d27cee
ms.sourcegitcommit: 8e846b52763f90d2232ec7d427839f4722570bce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "6292752"
---
# <a name="container-packing-strategies"></a><span data-ttu-id="56cc3-103">Estratégias de embalagem de contêineres</span><span class="sxs-lookup"><span data-stu-id="56cc3-103">Container packing strategies</span></span>

<span data-ttu-id="56cc3-104">Uma *estratégia de embalagem de contêineres* é uma estratégia que você pode usar para definir alocações de itens entre contêineres.</span><span class="sxs-lookup"><span data-stu-id="56cc3-104">A *container packing strategy* is a strategy that you can use to define item allocations across containers.</span></span> <span data-ttu-id="56cc3-105">Este tópico explica as diferenças entre as estratégias *Embalar em todos os contêineres abertos* e *Embalar somente no contêiner atual*.</span><span class="sxs-lookup"><span data-stu-id="56cc3-105">This topic explains the differences between the *Pack into all open containers* and *Pack into current container only* strategies.</span></span>

- <span data-ttu-id="56cc3-106">**Embalar em todos os contêineres abertos** – O sistema deve verificar todos os contêineres abertos que já foram criados durante o ciclo de transporte em contêiner, para garantir que o item caberá em um deles.</span><span class="sxs-lookup"><span data-stu-id="56cc3-106">**Pack into all open containers** – The system must check all open containers that have already been created during the containerization cycle, to make sure that the item will fit into one of them.</span></span> <span data-ttu-id="56cc3-107">Durante a embalagem, o sistema verifica cada item para determinar se ele caberá em algum dos contêineres criados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="56cc3-107">During packing, the system checks each item to determine whether it will fit into any of the previously created containers.</span></span> <span data-ttu-id="56cc3-108">Se o item não couber em um contêiner existente, o sistema cria um novo contêiner e continua até terminar de embalar todo o pedido.</span><span class="sxs-lookup"><span data-stu-id="56cc3-108">If the item won't fit into an existing container, the system creates a new container and continues until it has finished packing the whole order.</span></span>

    <span data-ttu-id="56cc3-109">Por exemplo, *n* itens encomendados requerem conteinerização.</span><span class="sxs-lookup"><span data-stu-id="56cc3-109">For example, *n* ordered items require containerization.</span></span> <span data-ttu-id="56cc3-110">Na pior das hipóteses, toda vez que o sistema processa um item que não cabe em nenhum contêiner existente, ele fará um total de (\[(*n* – 1) × (*n* + 1)\] ÷ 2) verificações para avaliar se o item cabe nos contêineres existentes.</span><span class="sxs-lookup"><span data-stu-id="56cc3-110">In the worst case, every time that the system processes an item that doesn't fit into any existing container, it will do a total of (\[(*n* – 1) × (*n* + 1)\] ÷ 2) checks to evaluate whether the item fits into the existing containers.</span></span>

- <span data-ttu-id="56cc3-111">**Embalar somente no contêiner atual** – O sistema deve verificar somente o contêiner criado por último para garantir que o item não se encaixará nele.</span><span class="sxs-lookup"><span data-stu-id="56cc3-111">**Pack into current container only** – The system must check only the most recently created container to make sure that the item will fit into it.</span></span> <span data-ttu-id="56cc3-112">Durante a embalagem, o sistema verifica cada item para determinar se ele caberá no contêiner criado por último.</span><span class="sxs-lookup"><span data-stu-id="56cc3-112">During packing, the system checks each item to determine whether it will fit into the most recently created container.</span></span> <span data-ttu-id="56cc3-113">Se o item não couber nesse contêiner, o sistema cria um novo contêiner e continua até terminar de embalar todo o pedido.</span><span class="sxs-lookup"><span data-stu-id="56cc3-113">If the item won't fit into that container, the system creates a new container and continues until it has finished packing the whole order.</span></span>

    <span data-ttu-id="56cc3-114">Por exemplo, *n* itens encomendados requerem conteinerização.</span><span class="sxs-lookup"><span data-stu-id="56cc3-114">For example, *n* ordered items require containerization.</span></span> <span data-ttu-id="56cc3-115">Na pior das hipóteses, o sistema fará um total de (*n* – 1) verificações para avaliar se o item cabe nos contêineres.</span><span class="sxs-lookup"><span data-stu-id="56cc3-115">In the worst case, the system will do a total of (*n* – 1) checks to evaluate whether the item fits into the containers.</span></span>

## <a name="example-of-the-flow-for-container-packing-strategies"></a><span data-ttu-id="56cc3-116">Exemplo do fluxo para estratégias de embalagem de contêineres</span><span class="sxs-lookup"><span data-stu-id="56cc3-116">Example of the flow for container packing strategies</span></span>

<span data-ttu-id="56cc3-117">Você deverá configurar os seguintes itens para transporte em contêiner.</span><span class="sxs-lookup"><span data-stu-id="56cc3-117">You set up the following items for containerization.</span></span>

| <span data-ttu-id="56cc3-118">Item </span><span class="sxs-lookup"><span data-stu-id="56cc3-118">Item</span></span> | <span data-ttu-id="56cc3-119">Dimensões físicas (largura × profundidade × altura)</span><span class="sxs-lookup"><span data-stu-id="56cc3-119">Physical dimensions (width × depth × height)</span></span> | <span data-ttu-id="56cc3-120">Peso</span><span class="sxs-lookup"><span data-stu-id="56cc3-120">Weight</span></span> |
|---|---|---|
| <span data-ttu-id="56cc3-121">Cabo HDMI de 6"</span><span class="sxs-lookup"><span data-stu-id="56cc3-121">HDMI Cable 6'</span></span> | <span data-ttu-id="56cc3-122">1 × 1 × 1</span><span class="sxs-lookup"><span data-stu-id="56cc3-122">1 × 1 × 1</span></span> | <span data-ttu-id="56cc3-123">1</span><span class="sxs-lookup"><span data-stu-id="56cc3-123">1</span></span> |
| <span data-ttu-id="56cc3-124">Cabo HDMI de 12"</span><span class="sxs-lookup"><span data-stu-id="56cc3-124">HDMI Cable 12'</span></span> | <span data-ttu-id="56cc3-125">2 × 1 × 1</span><span class="sxs-lookup"><span data-stu-id="56cc3-125">2 × 1 × 1</span></span> | <span data-ttu-id="56cc3-126">1</span><span class="sxs-lookup"><span data-stu-id="56cc3-126">1</span></span> |
| <span data-ttu-id="56cc3-127">Cabo HDMI de 18"</span><span class="sxs-lookup"><span data-stu-id="56cc3-127">HDMI Cable 18'</span></span> | <span data-ttu-id="56cc3-128">3 × 1 × 1</span><span class="sxs-lookup"><span data-stu-id="56cc3-128">3 × 1 × 1</span></span> | <span data-ttu-id="56cc3-129">2</span><span class="sxs-lookup"><span data-stu-id="56cc3-129">2</span></span> |

<span data-ttu-id="56cc3-130">Você também deverá configurar a seguinte caixa que será usada para embalagem.</span><span class="sxs-lookup"><span data-stu-id="56cc3-130">You also set up the following box that will be used for packaging.</span></span>

| <span data-ttu-id="56cc3-131">Contêiner</span><span class="sxs-lookup"><span data-stu-id="56cc3-131">Container</span></span> | <span data-ttu-id="56cc3-132">Dimensões físicas (comprimento x largura × altura)</span><span class="sxs-lookup"><span data-stu-id="56cc3-132">Physical dimensions (length × width × height)</span></span> | <span data-ttu-id="56cc3-133">Peso</span><span class="sxs-lookup"><span data-stu-id="56cc3-133">Weight</span></span> | <span data-ttu-id="56cc3-134">Volume</span><span class="sxs-lookup"><span data-stu-id="56cc3-134">Volume</span></span> |
|---|---|---|---|
| <span data-ttu-id="56cc3-135">Caixa Média</span><span class="sxs-lookup"><span data-stu-id="56cc3-135">Medium Box</span></span> | <span data-ttu-id="56cc3-136">6 × 3 × 2</span><span class="sxs-lookup"><span data-stu-id="56cc3-136">6 × 3 × 2</span></span> | <span data-ttu-id="56cc3-137">10</span><span class="sxs-lookup"><span data-stu-id="56cc3-137">10</span></span> | <span data-ttu-id="56cc3-138">100</span><span class="sxs-lookup"><span data-stu-id="56cc3-138">100</span></span> |

<span data-ttu-id="56cc3-139">Por fim, você deve configurar um pedido que tenha os seguintes produtos e quantidades.</span><span class="sxs-lookup"><span data-stu-id="56cc3-139">Finally, you set up an order that has the following products and quantities.</span></span>

| <span data-ttu-id="56cc3-140">Linha da ordem de venda</span><span class="sxs-lookup"><span data-stu-id="56cc3-140">Sales order line</span></span> | <span data-ttu-id="56cc3-141">Quantidade</span><span class="sxs-lookup"><span data-stu-id="56cc3-141">Quantity</span></span> |
|---|---|
| <span data-ttu-id="56cc3-142">Cabo HDMI de 12"</span><span class="sxs-lookup"><span data-stu-id="56cc3-142">HDMI Cable 12'</span></span> | <span data-ttu-id="56cc3-143">9</span><span class="sxs-lookup"><span data-stu-id="56cc3-143">9</span></span> |
| <span data-ttu-id="56cc3-144">Cabo HDMI de 18"</span><span class="sxs-lookup"><span data-stu-id="56cc3-144">HDMI Cable 18'</span></span> | <span data-ttu-id="56cc3-145">8</span><span class="sxs-lookup"><span data-stu-id="56cc3-145">8</span></span> |
| <span data-ttu-id="56cc3-146">Cabo HDMI de 6"</span><span class="sxs-lookup"><span data-stu-id="56cc3-146">HDMI Cable 6'</span></span> | <span data-ttu-id="56cc3-147">13</span><span class="sxs-lookup"><span data-stu-id="56cc3-147">13</span></span> |

<span data-ttu-id="56cc3-148">A tabela a seguir resume como funciona a conteinerização quando você usa a estratégia *Embalar em todos os contêineres abertos* e quando usa a estratégia *Embalar somente no contêiner atual*.</span><span class="sxs-lookup"><span data-stu-id="56cc3-148">The following table summarizes how containerization works when you use the *Pack into all open containers* strategy and when you use the *Pack into current container only* strategy.</span></span>

| <span data-ttu-id="56cc3-149">Embalar todos os contêineres abertos</span><span class="sxs-lookup"><span data-stu-id="56cc3-149">Pack into all open containers</span></span> | <span data-ttu-id="56cc3-150">Embalar no recipiente atual</span><span class="sxs-lookup"><span data-stu-id="56cc3-150">Pack into current container</span></span> |
|---|---|
| <p><span data-ttu-id="56cc3-151">Cabo HDMI de 12":</span><span class="sxs-lookup"><span data-stu-id="56cc3-151">HDMI Cable 12':</span></span></p><ol><li><span data-ttu-id="56cc3-152">Criar um novo contêiner, CONT0001.</span><span class="sxs-lookup"><span data-stu-id="56cc3-152">Create a new container, CONT0001.</span></span></li><li><span data-ttu-id="56cc3-153">Coloque 9 ea no contêiner CONT0001.</span><span class="sxs-lookup"><span data-stu-id="56cc3-153">Put 9 ea into container CONT0001.</span></span></li></ol> | <p><span data-ttu-id="56cc3-154">Cabo HDMI de 12":</span><span class="sxs-lookup"><span data-stu-id="56cc3-154">HDMI Cable 12':</span></span></p><ol><li><span data-ttu-id="56cc3-155">Criar um novo contêiner, CONT0001.</span><span class="sxs-lookup"><span data-stu-id="56cc3-155">Create a new container, CONT0001.</span></span></li><li><span data-ttu-id="56cc3-156">Coloque 9 ea no contêiner CONT0001.</span><span class="sxs-lookup"><span data-stu-id="56cc3-156">Put 9 ea into container CONT0001.</span></span></li></ol> |
| <p><span data-ttu-id="56cc3-157">Cabo HDMI de 18":</span><span class="sxs-lookup"><span data-stu-id="56cc3-157">HDMI Cable 18':</span></span></p><ol><li><span data-ttu-id="56cc3-158">Verifique se o item cabe no contêiner CONT0001.</span><span class="sxs-lookup"><span data-stu-id="56cc3-158">Check whether the item can fit into container CONT0001.</span></span></li><li><span data-ttu-id="56cc3-159">Criar um novo contêiner, CONT0002.</span><span class="sxs-lookup"><span data-stu-id="56cc3-159">Create a new container, CONT0002.</span></span></li><li><span data-ttu-id="56cc3-160">Coloque 5 ea no contêiner CONT0002.</span><span class="sxs-lookup"><span data-stu-id="56cc3-160">Put 5 ea into container CONT0002.</span></span></li><li><span data-ttu-id="56cc3-161">Criar um novo contêiner, CONT0003.</span><span class="sxs-lookup"><span data-stu-id="56cc3-161">Create a new container, CONT0003.</span></span></li><li><span data-ttu-id="56cc3-162">Coloque 3 ea no contêiner CONT0003.</span><span class="sxs-lookup"><span data-stu-id="56cc3-162">Put 3 ea into container CONT0003.</span></span></li></ol> | <p><span data-ttu-id="56cc3-163">Cabo HDMI de 18":</span><span class="sxs-lookup"><span data-stu-id="56cc3-163">HDMI Cable 18':</span></span></p><ol><li><span data-ttu-id="56cc3-164">Verifique se o item cabe no contêiner CONT0001.</span><span class="sxs-lookup"><span data-stu-id="56cc3-164">Check whether the item can fit into container CONT0001.</span></span></li><li><span data-ttu-id="56cc3-165">Criar um novo contêiner, CONT0002.</span><span class="sxs-lookup"><span data-stu-id="56cc3-165">Create a new container, CONT0002.</span></span></li><li><span data-ttu-id="56cc3-166">Coloque 5 ea no contêiner CONT0002.</span><span class="sxs-lookup"><span data-stu-id="56cc3-166">Put 5 ea into container CONT0002.</span></span></li><li><span data-ttu-id="56cc3-167">Criar um novo contêiner, CONT0003.</span><span class="sxs-lookup"><span data-stu-id="56cc3-167">Create a new container, CONT0003.</span></span></li><li><span data-ttu-id="56cc3-168">Coloque 3 ea no contêiner CONT0003.</span><span class="sxs-lookup"><span data-stu-id="56cc3-168">Put 3 ea into container CONT0003.</span></span></li></ol> |
| <p><span data-ttu-id="56cc3-169">Cabo HDMI de 6":</span><span class="sxs-lookup"><span data-stu-id="56cc3-169">HDMI Cable 6':</span></span></p><ol><li><span data-ttu-id="56cc3-170">Verifique se o item cabe no contêiner CONT0001.</span><span class="sxs-lookup"><span data-stu-id="56cc3-170">Check whether the item can fit into container CONT0001.</span></span></li><li><span data-ttu-id="56cc3-171">Coloque 1 ea no contêiner CONT0001.</span><span class="sxs-lookup"><span data-stu-id="56cc3-171">Put 1 ea into container CONT0001.</span></span></li><li><span data-ttu-id="56cc3-172">Verifique se o item cabe no contêiner CONT0002.</span><span class="sxs-lookup"><span data-stu-id="56cc3-172">Check whether the item can fit into container CONT0002.</span></span></li><li><span data-ttu-id="56cc3-173">Verifique se o item cabe no contêiner CONT0003.</span><span class="sxs-lookup"><span data-stu-id="56cc3-173">Check whether the item can fit into container CONT0003.</span></span></li><li><span data-ttu-id="56cc3-174">Coloque 4 ea no contêiner CONT0003.</span><span class="sxs-lookup"><span data-stu-id="56cc3-174">Put 4 ea into container CONT0003.</span></span></li><li><span data-ttu-id="56cc3-175">Criar um novo contêiner, CONT0004.</span><span class="sxs-lookup"><span data-stu-id="56cc3-175">Create a new container, CONT0004.</span></span></li><li><span data-ttu-id="56cc3-176">Coloque 8 ea no contêiner CONT0004.</span><span class="sxs-lookup"><span data-stu-id="56cc3-176">Put 8 ea into container CONT0004.</span></span></li></ol> | <p><span data-ttu-id="56cc3-177">Cabo HDMI de 6":</span><span class="sxs-lookup"><span data-stu-id="56cc3-177">HDMI Cable 6':</span></span></p><ol><li><span data-ttu-id="56cc3-178">Verifique se o item cabe no contêiner CONT0003.</span><span class="sxs-lookup"><span data-stu-id="56cc3-178">Check whether the item can fit into container CONT0003.</span></span></li><li><span data-ttu-id="56cc3-179">Coloque 4 ea no contêiner CONT0003.</span><span class="sxs-lookup"><span data-stu-id="56cc3-179">Put 4 ea into container CONT0003.</span></span></li><li><span data-ttu-id="56cc3-180">Criar um novo contêiner, CONT0004.</span><span class="sxs-lookup"><span data-stu-id="56cc3-180">Create a new container, CONT0004.</span></span></li><li><span data-ttu-id="56cc3-181">Coloque 9 ea no contêiner CONT0004.</span><span class="sxs-lookup"><span data-stu-id="56cc3-181">Put 9 ea into container CONT0004.</span></span></li></ol> |

## <a name="example-scenario-pack-single-orders-per-container"></a><span data-ttu-id="56cc3-182">Cenário do exemplo: Embalar pedidos únicos por contêiner</span><span class="sxs-lookup"><span data-stu-id="56cc3-182">Example scenario: Pack single orders per container</span></span>

<span data-ttu-id="56cc3-183">Esta seção apresenta um cenário onde o sistema é configurado para consolidar vários pedidos em uma única remessa.</span><span class="sxs-lookup"><span data-stu-id="56cc3-183">This section presents a scenario where the system is set up to consolidate multiple orders into one shipment.</span></span> <span data-ttu-id="56cc3-184">Portanto, a conteinerização será feita com base na ordem de vendas para garantir que cada pedido que contenha vários produtos seja embalado em seu próprio contêiner.</span><span class="sxs-lookup"><span data-stu-id="56cc3-184">Therefore, containerization will be done from the sales order to ensure that every order that contains multiple products is packed into its own container.</span></span>

<span data-ttu-id="56cc3-185">Essa funcionalidade permite lidar com cenários onde você deve embalar apenas um pedido de venda em cada contêiner, para que o centro de distribuição possa realizar distribuição integrada com contêineres cheios entre lojas de varejo.</span><span class="sxs-lookup"><span data-stu-id="56cc3-185">This functionality lets you handle scenarios where you must pack only one sales order into each container, so that the distribution center can cross-dock full containers between retail stores.</span></span> <span data-ttu-id="56cc3-186">Além dos cenários de varejo (pedido por loja de varejo e envio para um centro de distribuição integrada), essa técnica também é comumente usada em cadeias de suprimentos enxutas (ordem de vendas por linha de produção just-in-time).</span><span class="sxs-lookup"><span data-stu-id="56cc3-186">In addition to the retail scenarios (order per retail store and shipping to a distribution center for cross-docking) this technique is also commonly used in lean supply chains (sales order per just-in-time production line).</span></span>

<span data-ttu-id="56cc3-187">Este cenário mostra como você pode diminuir o número de contêineres que são avaliados durante a embalagem usando a estratégia *Embalar somente no contêiner atual*.</span><span class="sxs-lookup"><span data-stu-id="56cc3-187">This scenario shows how you can decrease the number of containers that are evaluated during packing by using the *Pack into current container only* strategy for containerization.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="56cc3-188">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="56cc3-188">Prerequisites</span></span>

#### <a name="turn-on-the-consolidate-shipments-feature-in-your-system"></a><span data-ttu-id="56cc3-189">Ativar o recurso Consolidar remessas no seu sistema</span><span class="sxs-lookup"><span data-stu-id="56cc3-189">Turn on the Consolidate shipments feature in your system</span></span>

<span data-ttu-id="56cc3-190">Este cenário utiliza o recurso *Consolidar remessas*.</span><span class="sxs-lookup"><span data-stu-id="56cc3-190">This scenario uses the *Consolidate shipments* feature.</span></span> <span data-ttu-id="56cc3-191">Se esse recurso ainda não estiver disponível no seu sistema, você deve ativá-lo usando o [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="56cc3-191">If that feature isn't already available in your system, you must turn it on by using [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>

#### <a name="make-demo-data-available"></a><span data-ttu-id="56cc3-192">Disponibilizar dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="56cc3-192">Make demo data available</span></span>

<span data-ttu-id="56cc3-193">O cenário deste tópico faz referência a valores e registros incluídos nos dados de demonstração padrão que são fornecidos para o Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="56cc3-193">This scenario references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="56cc3-194">Se você deseja usar os valores fornecidos aqui ao fazer os exercícios, procure trabalhar em um ambiente no qual os dados de demonstração estejam instalados e defina a entidade legal como **USMF** antes de começar.</span><span class="sxs-lookup"><span data-stu-id="56cc3-194">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

### <a name="inspect-or-create-container-types"></a><span data-ttu-id="56cc3-195">Inspecionar ou criar tipos de contêineres</span><span class="sxs-lookup"><span data-stu-id="56cc3-195">Inspect or create container types</span></span>

<span data-ttu-id="56cc3-196">Para inspecionar seus tipos de contêineres ou criar novos tipos de contêineres, se necessário, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="56cc3-196">To inspect your container types, or to create new container types if they are required, follow these steps.</span></span>

1. <span data-ttu-id="56cc3-197">Vá para **Gerenciamento de depósito** \> **Configuração** \> **Contêineres** \> **Tipos de contêiner**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-197">Go to **Warehouse management** \> **Setup** \> **Containers** \> **Container types**.</span></span>
1. <span data-ttu-id="56cc3-198">Certifique-se de que cada um destes tipos de contêiner esteja disponível em seus dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="56cc3-198">Make sure that each of the following container types is available in your demo data.</span></span> <span data-ttu-id="56cc3-199">Edite ou crie tipos de contêineres conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="56cc3-199">Edit or create container types as required.</span></span>

    - <span data-ttu-id="56cc3-200">Tipo de contêiner 1:</span><span class="sxs-lookup"><span data-stu-id="56cc3-200">Container type 1:</span></span>

        - <span data-ttu-id="56cc3-201">**Código do tipo de contêiner:** *Box-Large*</span><span class="sxs-lookup"><span data-stu-id="56cc3-201">**Container type code:** *Box-Large*</span></span>
        - <span data-ttu-id="56cc3-202">**Descrição:** *Caixa Grande*</span><span class="sxs-lookup"><span data-stu-id="56cc3-202">**Description:** *Large Box*</span></span>
        - <span data-ttu-id="56cc3-203">**Peso líquido máximo:** *100*</span><span class="sxs-lookup"><span data-stu-id="56cc3-203">**Maximum net weight:** *100*</span></span>
        - <span data-ttu-id="56cc3-204">**Volume:** *400*</span><span class="sxs-lookup"><span data-stu-id="56cc3-204">**Volume:** *400*</span></span>
        - <span data-ttu-id="56cc3-205">**Comprimento:** *4*</span><span class="sxs-lookup"><span data-stu-id="56cc3-205">**Length:** *4*</span></span>
        - <span data-ttu-id="56cc3-206">**Largura:** *10*</span><span class="sxs-lookup"><span data-stu-id="56cc3-206">**Width:** *10*</span></span>
        - <span data-ttu-id="56cc3-207">**Altura:** *10*</span><span class="sxs-lookup"><span data-stu-id="56cc3-207">**Height:** *10*</span></span>

    - <span data-ttu-id="56cc3-208">Tipo de contêiner 2:</span><span class="sxs-lookup"><span data-stu-id="56cc3-208">Container type 2:</span></span>

        - <span data-ttu-id="56cc3-209">**Código do tipo de contêiner:** *Box-Medium*</span><span class="sxs-lookup"><span data-stu-id="56cc3-209">**Container type code:** *Box-Medium*</span></span>
        - <span data-ttu-id="56cc3-210">**Descrição:** *Caixa Média*</span><span class="sxs-lookup"><span data-stu-id="56cc3-210">**Description:** *Medium Box*</span></span>
        - <span data-ttu-id="56cc3-211">**Peso líquido máximo:** *50*</span><span class="sxs-lookup"><span data-stu-id="56cc3-211">**Maximum net weight:** *50*</span></span>
        - <span data-ttu-id="56cc3-212">**Volume:** *200*</span><span class="sxs-lookup"><span data-stu-id="56cc3-212">**Volume:** *200*</span></span>
        - <span data-ttu-id="56cc3-213">**Comprimento:** *2*</span><span class="sxs-lookup"><span data-stu-id="56cc3-213">**Length:** *2*</span></span>
        - <span data-ttu-id="56cc3-214">**Largura:** *10*</span><span class="sxs-lookup"><span data-stu-id="56cc3-214">**Width:** *10*</span></span>
        - <span data-ttu-id="56cc3-215">**Altura:** *10*</span><span class="sxs-lookup"><span data-stu-id="56cc3-215">**Height:** *10*</span></span>

    - <span data-ttu-id="56cc3-216">Tipo de contêiner 3:</span><span class="sxs-lookup"><span data-stu-id="56cc3-216">Container type 3:</span></span>

        - <span data-ttu-id="56cc3-217">**Código do tipo de contêiner:** *Box-Small*</span><span class="sxs-lookup"><span data-stu-id="56cc3-217">**Container type code:** *Box-Small*</span></span>
        - <span data-ttu-id="56cc3-218">**Descrição:** *Caixa Pequena*</span><span class="sxs-lookup"><span data-stu-id="56cc3-218">**Description:** *Small Box*</span></span>
        - <span data-ttu-id="56cc3-219">**Peso líquido máximo:** *20*</span><span class="sxs-lookup"><span data-stu-id="56cc3-219">**Maximum net weight:** *20*</span></span>
        - <span data-ttu-id="56cc3-220">**Volume:** *100*</span><span class="sxs-lookup"><span data-stu-id="56cc3-220">**Volume:** *100*</span></span>
        - <span data-ttu-id="56cc3-221">**Comprimento:** *1*</span><span class="sxs-lookup"><span data-stu-id="56cc3-221">**Length:** *1*</span></span>
        - <span data-ttu-id="56cc3-222">**Largura:** *10*</span><span class="sxs-lookup"><span data-stu-id="56cc3-222">**Width:** *10*</span></span>
        - <span data-ttu-id="56cc3-223">**Altura:** *10*</span><span class="sxs-lookup"><span data-stu-id="56cc3-223">**Height:** *10*</span></span>

### <a name="inspect-or-create-container-groups"></a><span data-ttu-id="56cc3-224">Inspecionar ou criar grupos de contêineres</span><span class="sxs-lookup"><span data-stu-id="56cc3-224">Inspect or create container groups</span></span>

<span data-ttu-id="56cc3-225">Para inspecionar seus grupos de contêineres ou criar novos grupos de contêineres, se necessário, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="56cc3-225">To inspect your container groups, or to create new container groups if they are required, follow these steps.</span></span>

1. <span data-ttu-id="56cc3-226">Vá para **Gerenciamento de depósito** \> **Configuração** \> **Contêineres** \> **Grupos de contêineres**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-226">Go to **Warehouse management** \> **Setup** \> **Containers** \> **Container groups**.</span></span>
1. <span data-ttu-id="56cc3-227">Certifique-se de que o seguinte grupo de contêiner esteja disponível em seus dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="56cc3-227">Make sure that the following container group is available in your demo data.</span></span> <span data-ttu-id="56cc3-228">Se ele não estiver disponível, selecione **Novo** para criá-lo.</span><span class="sxs-lookup"><span data-stu-id="56cc3-228">If it isn't available, select **New** to create it.</span></span>

    - <span data-ttu-id="56cc3-229">**ID do grupo de contêineres:** *Caixas*</span><span class="sxs-lookup"><span data-stu-id="56cc3-229">**Container group ID:** *Boxes*</span></span>
    - <span data-ttu-id="56cc3-230">**Descrição:** *Tamanhos de caixa*</span><span class="sxs-lookup"><span data-stu-id="56cc3-230">**Description:** *Box sizes*</span></span>

1. <span data-ttu-id="56cc3-231">Na FastTab **Detalhes** do grupo de contêineres *Caixas*, certifique-se de que as seguintes linhas existam.</span><span class="sxs-lookup"><span data-stu-id="56cc3-231">On the **Details** FastTab for the *Boxes* container group, make sure that the following lines exist.</span></span> <span data-ttu-id="56cc3-232">Se não existirem, selecione **Novo** para adicioná-las.</span><span class="sxs-lookup"><span data-stu-id="56cc3-232">If they don't, select **New** to add them.</span></span>

    - <span data-ttu-id="56cc3-233">Linha 1:</span><span class="sxs-lookup"><span data-stu-id="56cc3-233">Line 1:</span></span>

        - <span data-ttu-id="56cc3-234">**Número de sequência:** *1*</span><span class="sxs-lookup"><span data-stu-id="56cc3-234">**Sequence number:** *1*</span></span>
        - <span data-ttu-id="56cc3-235">**Tipo de contêiner:** *Caixa-Grande*</span><span class="sxs-lookup"><span data-stu-id="56cc3-235">**Container type:** *Box-Large*</span></span>
        - <span data-ttu-id="56cc3-236">**Porcentagem de utilização do contêiner:** *100*</span><span class="sxs-lookup"><span data-stu-id="56cc3-236">**Container utilization percentage:** *100*</span></span>

    - <span data-ttu-id="56cc3-237">Linha 2:</span><span class="sxs-lookup"><span data-stu-id="56cc3-237">Line 2:</span></span>

        - <span data-ttu-id="56cc3-238">**Número de sequência:** *2*</span><span class="sxs-lookup"><span data-stu-id="56cc3-238">**Sequence number:** *2*</span></span>
        - <span data-ttu-id="56cc3-239">**Tipo de contêiner:** *Caixa Média*</span><span class="sxs-lookup"><span data-stu-id="56cc3-239">**Container type:** *Box-Medium*</span></span>
        - <span data-ttu-id="56cc3-240">**Porcentagem de utilização do contêiner:** *100*</span><span class="sxs-lookup"><span data-stu-id="56cc3-240">**Container utilization percentage:** *100*</span></span>

    - <span data-ttu-id="56cc3-241">Linha 3:</span><span class="sxs-lookup"><span data-stu-id="56cc3-241">Line 3:</span></span>

        - <span data-ttu-id="56cc3-242">**Número de sequência:** *3*</span><span class="sxs-lookup"><span data-stu-id="56cc3-242">**Sequence number:** *3*</span></span>
        - <span data-ttu-id="56cc3-243">**Tipo de contêiner:** *Caixa Pequena*</span><span class="sxs-lookup"><span data-stu-id="56cc3-243">**Container type:** *Box-Small*</span></span>
        - <span data-ttu-id="56cc3-244">**Porcentagem de utilização do contêiner:** *100*</span><span class="sxs-lookup"><span data-stu-id="56cc3-244">**Container utilization percentage:** *100*</span></span>

### <a name="create-a-new-container-build-template"></a><span data-ttu-id="56cc3-245">Crie um novo modelo de criação de contêiner</span><span class="sxs-lookup"><span data-stu-id="56cc3-245">Create a new container build template</span></span>

<span data-ttu-id="56cc3-246">Para criar um novo modelo de criação de contêiner, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="56cc3-246">To create a new container build template, follow these steps.</span></span>

1. <span data-ttu-id="56cc3-247">Vá para **Gerenciamento de depósito** \> **Configuração** \> **Contêineres** \> **Modelo de criação de contêiner**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-247">Go to **Warehouse management** \> **Setup** \> **Containers** \> **Container build template**.</span></span>
1. <span data-ttu-id="56cc3-248">Selecione **Novo** para criar um modelo de criação de contêiner que tenha as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="56cc3-248">Select **New** to create a container build template that has the following settings:</span></span>

    - <span data-ttu-id="56cc3-249">**Número de sequência:** *1*</span><span class="sxs-lookup"><span data-stu-id="56cc3-249">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="56cc3-250">**ID do modelo do contêiner:** *Caixa*</span><span class="sxs-lookup"><span data-stu-id="56cc3-250">**Container template ID:** *Box*</span></span>
    - <span data-ttu-id="56cc3-251">**ID do grupo de contêineres:** *Caixas*</span><span class="sxs-lookup"><span data-stu-id="56cc3-251">**Container group ID:** *Boxes*</span></span>
    - <span data-ttu-id="56cc3-252">**Tipos de consulta base:** *Linha de alocação de vendas*</span><span class="sxs-lookup"><span data-stu-id="56cc3-252">**Base query types:** *Sales allocation line*</span></span>
    - <span data-ttu-id="56cc3-253">**Código da etapa do ciclo:** *234*</span><span class="sxs-lookup"><span data-stu-id="56cc3-253">**Wave step code:** *234*</span></span>
    - <span data-ttu-id="56cc3-254">**Permitir separações divididas:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="56cc3-254">**Allow split picks:** *Yes*</span></span>
    - <span data-ttu-id="56cc3-255">**Estratégia de embalagem de contêineres:** *Embalar somente no contêiner atual*</span><span class="sxs-lookup"><span data-stu-id="56cc3-255">**Container packing strategy:** *Pack into current container only*</span></span>
    - <span data-ttu-id="56cc3-256">**Embalar por unidade diretiva:** *Não*</span><span class="sxs-lookup"><span data-stu-id="56cc3-256">**Pack by directive unit:** *No*</span></span>

1. <span data-ttu-id="56cc3-257">Enquanto a linha do novo modelo ainda estiver selecionado, selecione **Editar consulta** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="56cc3-257">While the row for the new template is still selected, select **Edit query** on the Action Pane.</span></span>
1. <span data-ttu-id="56cc3-258">Uma caixa de diálogo do editor de consultas padrão é exibida.</span><span class="sxs-lookup"><span data-stu-id="56cc3-258">A standard query editor dialog box appears.</span></span> <span data-ttu-id="56cc3-259">Na guia **Classificação**, selecionar **Adicionar** para adicionar uma linha com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="56cc3-259">On the **Sorting** tab, select **Add** to add a row that has the following settings:</span></span>

    - <span data-ttu-id="56cc3-260">**Tabela:** *Transações de trabalho temporário*</span><span class="sxs-lookup"><span data-stu-id="56cc3-260">**Table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="56cc3-261">**Tabela derivada:** *Transações de trabalho temporário*</span><span class="sxs-lookup"><span data-stu-id="56cc3-261">**Derived table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="56cc3-262">**Campo:** *Número da ordem*</span><span class="sxs-lookup"><span data-stu-id="56cc3-262">**Field:** *Order number*</span></span>
    - <span data-ttu-id="56cc3-263">**Direção da pesquisa:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="56cc3-263">**Search direction:** *Ascending*</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="56cc3-264">Para evitar percorrer todos os outros contêineres abertos e acelerar o processo verificando um contêiner de cada vez, use a estratégia *Embalar somente no contêiner atual* além de classificar por número de pedido.</span><span class="sxs-lookup"><span data-stu-id="56cc3-264">To avoid cycling over all the other open containers, and to speed up the process by checking one container at a time, use the *Pack into current container only* strategy in addition to sorting by order number.</span></span> <span data-ttu-id="56cc3-265">Essa combinação funcionará como uma pausa de trabalho em um modelo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="56cc3-265">This combination will work like a work break on a work template.</span></span>

1. <span data-ttu-id="56cc3-266">Selecione **OK** para fechar a caixa de diálogo do editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="56cc3-266">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="56cc3-267">Enquanto a linha do novo modelo ainda estiver selecionado, selecione **Restrições de combinação de contêiner** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="56cc3-267">While the row for the new template is still selected, select **Container mixing constraints** on the Action Pane.</span></span>

    <span data-ttu-id="56cc3-268">Agora você adicionará uma restrição que coloca itens de uma única ordem em um único contêiner.</span><span class="sxs-lookup"><span data-stu-id="56cc3-268">You will now add a constraint that puts items from a single order into a single container.</span></span> <span data-ttu-id="56cc3-269">Os itens de qualquer outra ordem serão colocados em um contêiner separado.</span><span class="sxs-lookup"><span data-stu-id="56cc3-269">Items from any other order will be put into a separate container.</span></span>

1. <span data-ttu-id="56cc3-270">Selecione **Novo** para criar uma restrição de combinação que tenha as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="56cc3-270">Select **New** to create a mixing constraint that has the following settings:</span></span>

    - <span data-ttu-id="56cc3-271">**Tabela:** *Ordens de venda*</span><span class="sxs-lookup"><span data-stu-id="56cc3-271">**Table:** *Sales orders*</span></span>
    - <span data-ttu-id="56cc3-272">**Seleção de campo:** *SalesId* (O campo aparecerá como *Ordem de vendas* na grade.)</span><span class="sxs-lookup"><span data-stu-id="56cc3-272">**Field select:** *SalesId* (The field will appear as *Sales order* in the grid.)</span></span>

1. <span data-ttu-id="56cc3-273">Selecione **OK** para adicionar a restrição.</span><span class="sxs-lookup"><span data-stu-id="56cc3-273">Select **OK** to add the constraint.</span></span>
1. <span data-ttu-id="56cc3-274">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="56cc3-274">Close the page.</span></span>

### <a name="set-up-a-wave-template-for-containerization"></a><span data-ttu-id="56cc3-275">Configurar um modelo de ciclo para transporte em contêineres</span><span class="sxs-lookup"><span data-stu-id="56cc3-275">Set up a wave template for containerization</span></span>

<span data-ttu-id="56cc3-276">Para configurar um modelo de ciclo, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="56cc3-276">To set up a wave template, follow these steps.</span></span>

1. <span data-ttu-id="56cc3-277">Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Modelos de onda**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-277">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="56cc3-278">No painel de lista, defina o campo **Tipo de modelo de onda** como *Remessa*.</span><span class="sxs-lookup"><span data-stu-id="56cc3-278">In the list pane, set the **Wave template type** field to *Shipping*.</span></span>
1. <span data-ttu-id="56cc3-279">Selecione o modelo **63 Conteinerização** na lista.</span><span class="sxs-lookup"><span data-stu-id="56cc3-279">Select the **63 Containerization** template in the list.</span></span>
1. <span data-ttu-id="56cc3-280">No Painel de Ações, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-280">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="56cc3-281">Na FastTab **Métodos**, na coluna **Métodos selecionados**, localize a seguinte linha:</span><span class="sxs-lookup"><span data-stu-id="56cc3-281">On the **Methods** FastTab, in the **Selected methods** column, find the following line:</span></span>

    - <span data-ttu-id="56cc3-282">**Nome do método:** *conteinerização*</span><span class="sxs-lookup"><span data-stu-id="56cc3-282">**Method name:** *containerization*</span></span>
    - <span data-ttu-id="56cc3-283">**Nome:** *Conteinerização*</span><span class="sxs-lookup"><span data-stu-id="56cc3-283">**Name:** *Containerization*</span></span>

1. <span data-ttu-id="56cc3-284">Defina o campo **Código da etapa da onda** para a linha como *234*.</span><span class="sxs-lookup"><span data-stu-id="56cc3-284">Set the **Wave step code** field for the line to *234*.</span></span>

### <a name="set-up-a-work-template"></a><span data-ttu-id="56cc3-285">Configurar um modelo de trabalho</span><span class="sxs-lookup"><span data-stu-id="56cc3-285">Set up a work template</span></span>

<span data-ttu-id="56cc3-286">Para configurar um modelo de trabalho, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="56cc3-286">To set up a work template, follow these steps.</span></span>

1. <span data-ttu-id="56cc3-287">Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-287">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="56cc3-288">Defina o campo **Tipo de ordem de serviço** como *Ordens de venda*.</span><span class="sxs-lookup"><span data-stu-id="56cc3-288">Set the **Work order type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="56cc3-289">Na grade **Visão geral**, localize e selecione o modelo de trabalho que deve ser usado para embalar ordens únicas por contêiner.</span><span class="sxs-lookup"><span data-stu-id="56cc3-289">In the **Overview** grid, find and select the work template that should be used for packing single orders per container.</span></span> <span data-ttu-id="56cc3-290">Para esse cenário, selecione o modelo **63 Separar para contêiner**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-290">For this scenario, select the **63 Pick to container** template.</span></span>
1. <span data-ttu-id="56cc3-291">No Painel de Ações, selecione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-291">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="56cc3-292">Uma caixa de diálogo do editor de consultas padrão é exibida.</span><span class="sxs-lookup"><span data-stu-id="56cc3-292">A standard query editor dialog box appears.</span></span> <span data-ttu-id="56cc3-293">Na guia **Classificação**, adicione as seguintes linhas:</span><span class="sxs-lookup"><span data-stu-id="56cc3-293">On the **Sorting** tab, add the following lines:</span></span>

    - <span data-ttu-id="56cc3-294">Linha 1:</span><span class="sxs-lookup"><span data-stu-id="56cc3-294">Line 1:</span></span>

        - <span data-ttu-id="56cc3-295">**Tabela:** *Transações de trabalho temporário*</span><span class="sxs-lookup"><span data-stu-id="56cc3-295">**Table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="56cc3-296">**Tabela derivada:** *Transações de trabalho temporário*</span><span class="sxs-lookup"><span data-stu-id="56cc3-296">**Derived table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="56cc3-297">**Campo:** *ID da Remessa*</span><span class="sxs-lookup"><span data-stu-id="56cc3-297">**Field:** *Shipment ID*</span></span>
        - <span data-ttu-id="56cc3-298">**Direção da pesquisa:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="56cc3-298">**Search direction:** *Ascending*</span></span>

    - <span data-ttu-id="56cc3-299">Linha 2:</span><span class="sxs-lookup"><span data-stu-id="56cc3-299">Line 2:</span></span>

        - <span data-ttu-id="56cc3-300">**Tabela:** *Transações de trabalho temporário*</span><span class="sxs-lookup"><span data-stu-id="56cc3-300">**Table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="56cc3-301">**Tabela derivada:** *Transações de trabalho temporário*</span><span class="sxs-lookup"><span data-stu-id="56cc3-301">**Derived table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="56cc3-302">**Campo:** *Número da ordem*</span><span class="sxs-lookup"><span data-stu-id="56cc3-302">**Field:** *Order number*</span></span>
        - <span data-ttu-id="56cc3-303">**Direção da pesquisa:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="56cc3-303">**Search direction:** *Ascending*</span></span>

    - <span data-ttu-id="56cc3-304">Linha 3:</span><span class="sxs-lookup"><span data-stu-id="56cc3-304">Line 3:</span></span>

        - <span data-ttu-id="56cc3-305">**Tabela:** *Transações de trabalho temporário*</span><span class="sxs-lookup"><span data-stu-id="56cc3-305">**Table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="56cc3-306">**Tabela derivada:** *Transações de trabalho temporário*</span><span class="sxs-lookup"><span data-stu-id="56cc3-306">**Derived table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="56cc3-307">**Campo:** *ID do contêiner*</span><span class="sxs-lookup"><span data-stu-id="56cc3-307">**Field:** *Container ID*</span></span>
        - <span data-ttu-id="56cc3-308">**Direção da pesquisa:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="56cc3-308">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="56cc3-309">Selecione **OK** para fechar a caixa de diálogo do editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="56cc3-309">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="56cc3-310">Você receberá a seguinte mensagem: "O agrupamento será redefinido. Deseja continuar?"</span><span class="sxs-lookup"><span data-stu-id="56cc3-310">You receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="56cc3-311">Selecione **Sim** para continuar.</span><span class="sxs-lookup"><span data-stu-id="56cc3-311">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="56cc3-312">Enquanto o modelo **63 Separar para contêiner** ainda estiver selecionado, selecione **Quebras de cabeçalho de trabalho** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="56cc3-312">While the **63 Pick to container** template is still selected, select **Work header breaks** on the Action Pane.</span></span>

    <span data-ttu-id="56cc3-313">Agora você aplicará configurações para interromper o trabalho para que cada contêiner na ordem esteja vinculado a uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="56cc3-313">You will now apply settings to break the work so that each container in the order is linked to one work order.</span></span>

1. <span data-ttu-id="56cc3-314">Marque a caixa de seleção **Agrupar por este campo** para cada linha na página **Quebras de cabeçalho de trabalho** (**ID da remessa**, **Número do pedido** e **ID do contêiner**).</span><span class="sxs-lookup"><span data-stu-id="56cc3-314">Select the **Group by this field** checkbox for each row on the **Work header breaks** page (**Shipment ID**, **Order number**, and **Container ID**).</span></span>
1. <span data-ttu-id="56cc3-315">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="56cc3-315">Close the page.</span></span>

### <a name="set-up-shipment-consolidation-policies"></a><span data-ttu-id="56cc3-316">Configurar políticas de consolidação da remessa</span><span class="sxs-lookup"><span data-stu-id="56cc3-316">Set up shipment consolidation policies</span></span>

<span data-ttu-id="56cc3-317">Para configurar uma política de consolidação de remessa, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="56cc3-317">To set up a shipment consolidation policy, follow these steps.</span></span>

1. <span data-ttu-id="56cc3-318">Vá para **Gerenciamento de depósito \> Configuração \> Liberar para depósito \> Políticas de consolidação de remessa**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-318">Go to **Warehouse management \> Setup \> Release to warehouse \> Shipment consolidation policies**.</span></span>
1. <span data-ttu-id="56cc3-319">No painel de lista, defina o campo **Tipo de política** como *Ordens de venda*.</span><span class="sxs-lookup"><span data-stu-id="56cc3-319">In the list pane, set the **Policy type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="56cc3-320">Selecione a política **Padrão** na lista.</span><span class="sxs-lookup"><span data-stu-id="56cc3-320">Select the **Default** policy in the list.</span></span>
1. <span data-ttu-id="56cc3-321">No Painel de Ações, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-321">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="56cc3-322">Na Guia Rápida **Campos de consolidação**, na lista **Campos selecionados**, selecione a linha na qual o campo **Nome do campo** está definido como *Número da ordem*.</span><span class="sxs-lookup"><span data-stu-id="56cc3-322">On the **Consolidation fields** FastTab, in the **Selected fields** list, select the row where the **Field name** field is set to *Order number*.</span></span>
1. <span data-ttu-id="56cc3-323">Selecione o botão **Remover** ![Seta para a esquerda](media/backward-button.png) para mover o campo para a lista **Campos restantes**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-323">Select the **Remove** button ![Left arrow](media/backward-button.png) to move the field to the **Remaining fields** list.</span></span>
1. <span data-ttu-id="56cc3-324">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-324">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-physical-dimensions-for-the-product"></a><span data-ttu-id="56cc3-325">Configurar dimensões físicas para o produto</span><span class="sxs-lookup"><span data-stu-id="56cc3-325">Set up physical dimensions for the product</span></span>

<span data-ttu-id="56cc3-326">Para configurar dimensões físicas para os produtos que serão utilizados nesse cenário, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="56cc3-326">To set up physical dimensions for the products that will be used in this scenario, follow these steps.</span></span>

1. <span data-ttu-id="56cc3-327">Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-327">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="56cc3-328">Selecione o produto no qual o campo **Número do item** esteja definido como *A0001*.</span><span class="sxs-lookup"><span data-stu-id="56cc3-328">Select the product where the **Item number** field is set to *A0001*.</span></span>
1. <span data-ttu-id="56cc3-329">No Painel de Ação, na guia **Gerenciar estoque**, no grupo **Depósito**, selecione **Dimensões físicas**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-329">On the Action Pane, on the **Manage inventory** tab, in the **Warehouse** group, select **Physical dimensions**.</span></span>
1. <span data-ttu-id="56cc3-330">Na página **Dimensões físicas**, você deve ver a seguinte linha na grade:</span><span class="sxs-lookup"><span data-stu-id="56cc3-330">On the **Physical dimensions** page, you should see the following line in the grid:</span></span>

    - <span data-ttu-id="56cc3-331">**Unidade:** *pcs*</span><span class="sxs-lookup"><span data-stu-id="56cc3-331">**Unit:** *pcs*</span></span>
    - <span data-ttu-id="56cc3-332">**Peso bruto:** *3,00*</span><span class="sxs-lookup"><span data-stu-id="56cc3-332">**Gross weight:** *3.00*</span></span>
    - <span data-ttu-id="56cc3-333">**Largura:** *2,00*</span><span class="sxs-lookup"><span data-stu-id="56cc3-333">**Width:** *2.00*</span></span>
    - <span data-ttu-id="56cc3-334">**Profundidade:** *2,00*</span><span class="sxs-lookup"><span data-stu-id="56cc3-334">**Depth:** *2.00*</span></span>
    - <span data-ttu-id="56cc3-335">**Altura:** *4,00*</span><span class="sxs-lookup"><span data-stu-id="56cc3-335">**Height:** *4.00*</span></span>
    - <span data-ttu-id="56cc3-336">**Volume:** *16,00*</span><span class="sxs-lookup"><span data-stu-id="56cc3-336">**Volume:** *16.00*</span></span>

1. <span data-ttu-id="56cc3-337">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="56cc3-337">Close the page.</span></span>
1. <span data-ttu-id="56cc3-338">Selecione o produto no qual o campo **Número do item** esteja definido como *A0002*.</span><span class="sxs-lookup"><span data-stu-id="56cc3-338">Select the product where the **Item number** field is set to *A0002*.</span></span>
1. <span data-ttu-id="56cc3-339">No Painel de Ação, na guia **Gerenciar estoque**, no grupo **Depósito**, selecione **Dimensões físicas**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-339">On the Action Pane, on the **Manage inventory** tab, in the **Warehouse** group, select **Physical dimensions**.</span></span>
1. <span data-ttu-id="56cc3-340">Na página **Dimensões físicas**, você deve ver a seguinte linha na grade:</span><span class="sxs-lookup"><span data-stu-id="56cc3-340">On the **Physical dimensions** page, you should see the following line in the grid:</span></span>

    - <span data-ttu-id="56cc3-341">**Unidade:** *pcs*</span><span class="sxs-lookup"><span data-stu-id="56cc3-341">**Unit:** *pcs*</span></span>
    - <span data-ttu-id="56cc3-342">**Peso bruto:** *4,00*</span><span class="sxs-lookup"><span data-stu-id="56cc3-342">**Gross weight:** *4.00*</span></span>
    - <span data-ttu-id="56cc3-343">**Largura:** *3,00*</span><span class="sxs-lookup"><span data-stu-id="56cc3-343">**Width:** *3.00*</span></span>
    - <span data-ttu-id="56cc3-344">**Profundidade:** *1,00*</span><span class="sxs-lookup"><span data-stu-id="56cc3-344">**Depth:** *1.00*</span></span>
    - <span data-ttu-id="56cc3-345">**Altura:** *3,00*</span><span class="sxs-lookup"><span data-stu-id="56cc3-345">**Height:** *3.00*</span></span>
    - <span data-ttu-id="56cc3-346">**Volume:** *9,00*</span><span class="sxs-lookup"><span data-stu-id="56cc3-346">**Volume:** *9.00*</span></span>

### <a name="create-sales-order-1"></a><span data-ttu-id="56cc3-347">Criar ordem de venda 1</span><span class="sxs-lookup"><span data-stu-id="56cc3-347">Create sales order 1</span></span>

<span data-ttu-id="56cc3-348">Para criar uma ordem de venda, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="56cc3-348">To create a sales order, follow these steps.</span></span>

1. <span data-ttu-id="56cc3-349">Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-349">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="56cc3-350">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-350">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="56cc3-351">Uma caixa de diálogo para criar uma nova ordem de venda aparece.</span><span class="sxs-lookup"><span data-stu-id="56cc3-351">A dialog box for creating a new sales order appears.</span></span> <span data-ttu-id="56cc3-352">Defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="56cc3-352">Set the following values:</span></span>

    - <span data-ttu-id="56cc3-353">**Conta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="56cc3-353">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="56cc3-354">**Depósito:** *63*</span><span class="sxs-lookup"><span data-stu-id="56cc3-354">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="56cc3-355">Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="56cc3-355">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="56cc3-356">A nova ordem de venda é aberta.</span><span class="sxs-lookup"><span data-stu-id="56cc3-356">The new sales order is opened.</span></span> <span data-ttu-id="56cc3-357">Na FastTab **Linhas da ordem de venda**, adicione as seguintes linhas de venda:</span><span class="sxs-lookup"><span data-stu-id="56cc3-357">On the **Sales order lines** FastTab, add the following sales lines:</span></span>

    - <span data-ttu-id="56cc3-358">Linha 1:</span><span class="sxs-lookup"><span data-stu-id="56cc3-358">Line 1:</span></span>

        - <span data-ttu-id="56cc3-359">**Número de item:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="56cc3-359">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="56cc3-360">**Quantidade:** *2*</span><span class="sxs-lookup"><span data-stu-id="56cc3-360">**Quantity:** *2*</span></span>

    - <span data-ttu-id="56cc3-361">Linha 2:</span><span class="sxs-lookup"><span data-stu-id="56cc3-361">Line 2:</span></span>

        - <span data-ttu-id="56cc3-362">**Número de item:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="56cc3-362">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="56cc3-363">**Quantidade:** *2*</span><span class="sxs-lookup"><span data-stu-id="56cc3-363">**Quantity:** *2*</span></span>

1. <span data-ttu-id="56cc3-364">Selecione a primeira linha e selecione **Inventário \> Reserva**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-364">Select the first line, and then select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="56cc3-365">Na página **Reserva**, selecione **Reservar lote**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-365">On the **Reservation** page, select **Reserve lot**.</span></span> <span data-ttu-id="56cc3-366">Depois feche a página.</span><span class="sxs-lookup"><span data-stu-id="56cc3-366">Then close the page.</span></span>
1. <span data-ttu-id="56cc3-367">Repita os dois passos anteriores para a segunda linha.</span><span class="sxs-lookup"><span data-stu-id="56cc3-367">Repeat the previous two steps for the second line.</span></span>
1. <span data-ttu-id="56cc3-368">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="56cc3-368">Close the page.</span></span>

### <a name="create-sales-order-2"></a><span data-ttu-id="56cc3-369">Criar ordem de venda 2</span><span class="sxs-lookup"><span data-stu-id="56cc3-369">Create sales order 2</span></span>

<span data-ttu-id="56cc3-370">Siga estas etapas para criar uma segunda ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="56cc3-370">To create a second sales order, follow these steps.</span></span>

1. <span data-ttu-id="56cc3-371">Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-371">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="56cc3-372">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-372">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="56cc3-373">Uma caixa de diálogo para criar uma nova ordem de venda aparece.</span><span class="sxs-lookup"><span data-stu-id="56cc3-373">A dialog box for creating a new sales order appears.</span></span> <span data-ttu-id="56cc3-374">Defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="56cc3-374">Set the following values:</span></span>

    - <span data-ttu-id="56cc3-375">**Conta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="56cc3-375">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="56cc3-376">**Depósito:** *63*</span><span class="sxs-lookup"><span data-stu-id="56cc3-376">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="56cc3-377">Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="56cc3-377">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="56cc3-378">A nova ordem de venda é aberta.</span><span class="sxs-lookup"><span data-stu-id="56cc3-378">The new sales order is opened.</span></span> <span data-ttu-id="56cc3-379">Na FastTab **Linhas da ordem de venda**, adicione as seguintes linhas de venda:</span><span class="sxs-lookup"><span data-stu-id="56cc3-379">On the **Sales order lines** FastTab, add the following sales lines:</span></span>

    - <span data-ttu-id="56cc3-380">Linha 1:</span><span class="sxs-lookup"><span data-stu-id="56cc3-380">Line 1:</span></span>

        - <span data-ttu-id="56cc3-381">**Número de item:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="56cc3-381">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="56cc3-382">**Quantidade:** *4*</span><span class="sxs-lookup"><span data-stu-id="56cc3-382">**Quantity:** *4*</span></span>

    - <span data-ttu-id="56cc3-383">Linha 2:</span><span class="sxs-lookup"><span data-stu-id="56cc3-383">Line 2:</span></span>

        - <span data-ttu-id="56cc3-384">**Número de item:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="56cc3-384">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="56cc3-385">**Quantidade:** *4*</span><span class="sxs-lookup"><span data-stu-id="56cc3-385">**Quantity:** *4*</span></span>

1. <span data-ttu-id="56cc3-386">Selecione a primeira linha e selecione **Inventário \> Reserva**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-386">Select the first line, and then select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="56cc3-387">Na página **Reserva**, selecione **Reservar lote**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-387">On the **Reservation** page, select **Reserve lot**.</span></span> <span data-ttu-id="56cc3-388">Depois feche a página.</span><span class="sxs-lookup"><span data-stu-id="56cc3-388">Then close the page.</span></span>
1. <span data-ttu-id="56cc3-389">Repita os dois passos anteriores para a segunda linha.</span><span class="sxs-lookup"><span data-stu-id="56cc3-389">Repeat the previous two steps for the second line.</span></span>
1. <span data-ttu-id="56cc3-390">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="56cc3-390">Close the page.</span></span>

### <a name="create-the-load"></a><span data-ttu-id="56cc3-391">Criar a carga</span><span class="sxs-lookup"><span data-stu-id="56cc3-391">Create the load</span></span>

<span data-ttu-id="56cc3-392">Para criar uma carga para cada ordem que você criou para esse cenário e, em seguida, liberá-lo para o depósito, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="56cc3-392">To create a load for each order that you created for this scenario and then release it to the warehouse, follow these steps.</span></span>

1. <span data-ttu-id="56cc3-393">Vá para **Gerenciamento de depósito \> Cargas \> Bancada de planejamento de carga**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-393">Go to **Warehouse management \> Loads \> Load planning workbench**.</span></span>
1. <span data-ttu-id="56cc3-394">Na guia **Linhas de venda**, localize e selecione todas as linhas da ordem de venda nas ordens criadas para esse cenário.</span><span class="sxs-lookup"><span data-stu-id="56cc3-394">On the **Sales lines** tab, find and select all the sales order lines from the sales orders that you created for this scenario.</span></span>
1. <span data-ttu-id="56cc3-395">No Painel de Ação, na guia **Oferta e demanda** , no grupo **Adicionar** , selecione **Para nova carga**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-395">On the Action Pane, on the **Supply and demand** tab, in the **Add** group, select **To new load**.</span></span> <span data-ttu-id="56cc3-396">As linhas de ordem selecionadas são adicionadas a uma nova carga.</span><span class="sxs-lookup"><span data-stu-id="56cc3-396">The selected order lines are added to a new load.</span></span>
1. <span data-ttu-id="56cc3-397">Na caixa de diálogo **Atribuição de modelo de carga**, no campo **ID do modelo de carga**, selecione um modelo de carga, como *Contêiner de 40"*.</span><span class="sxs-lookup"><span data-stu-id="56cc3-397">In the **Load template assignment** dialog box, in the **Load template ID** field, select a load template, such as *40' Container*.</span></span>
1. <span data-ttu-id="56cc3-398">Selecione **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="56cc3-398">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="56cc3-399">Na seção **Cargas**, localize e selecione a carga que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="56cc3-399">In the **Loads** section, find and select the load that you just created.</span></span>
1. <span data-ttu-id="56cc3-400">Selecione **Liberação \> Liberação para depósito**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-400">Select **Release \> Release to warehouse**.</span></span>
1. <span data-ttu-id="56cc3-401">Na caixa de diálogo **Liberar para depósito**, selecione **OK** para liberar a carga selecionada para o depósito.</span><span class="sxs-lookup"><span data-stu-id="56cc3-401">In the **Release to warehouse** dialog box, select **OK** to release the selected load to the warehouse.</span></span>

### <a name="verify-the-shipments-and-containers"></a><span data-ttu-id="56cc3-402">Verificar as remessas e os contêineres</span><span class="sxs-lookup"><span data-stu-id="56cc3-402">Verify the shipments and containers</span></span>

<span data-ttu-id="56cc3-403">O procedimento a seguir permite verificar as remessas que foram criadas.</span><span class="sxs-lookup"><span data-stu-id="56cc3-403">The following procedure lets you verify the shipments that have been created.</span></span> <span data-ttu-id="56cc3-404">Use-o para revisar a ordem que você criou para este cenário e ter certeza de que você obteve os resultados esperados.</span><span class="sxs-lookup"><span data-stu-id="56cc3-404">Use it to review the order that you created for this scenario, to make sure that you've obtained the expected results.</span></span>

1. <span data-ttu-id="56cc3-405">Acesse **Gerenciamento de depósito \> Remessas \> Todas as remessas**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-405">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="56cc3-406">Encontre e selecione a remessa que foi criada para a carga que você acabou de liberar.</span><span class="sxs-lookup"><span data-stu-id="56cc3-406">Find and select the shipment that was created for the load that you just released.</span></span>
1. <span data-ttu-id="56cc3-407">No painel de ações, na guia **Transporte**, selecione **Exibir contêineres**.</span><span class="sxs-lookup"><span data-stu-id="56cc3-407">On the Action Pane, on the **Transportation** tab, select **View containers**.</span></span>
1. <span data-ttu-id="56cc3-408">Confirme que os itens das ordens de venda foram conteinerizados em dois contêineres diferentes.</span><span class="sxs-lookup"><span data-stu-id="56cc3-408">Confirm that the items from the sales orders were containerized into two different containers.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="56cc3-409">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="56cc3-409">Additional resources</span></span>

- [<span data-ttu-id="56cc3-410">Transporte em contêineres</span><span class="sxs-lookup"><span data-stu-id="56cc3-410">Containerization</span></span>](wave-containerization.md)
