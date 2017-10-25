---
title: "Incluir o peso e o volume do contêiner na carga"
description: "Este tópico descreve como configurar e aplicar a funcionalidade para incluir o peso e volume de contêineres em cargas."
author: pjacobse
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: b137db6f67da30d6ac3a973940c1df1fd7268a1a
ms.openlocfilehash: ac1df9b430feb025e4a544a7ecd7baa0c919cbe4
ms.contentlocale: pt-br
ms.lasthandoff: 10/02/2017

---

# <a name="include-container-weight-and-volume-on-load"></a><span data-ttu-id="dc867-103">Incluir o peso e o volume do contêiner na carga</span><span class="sxs-lookup"><span data-stu-id="dc867-103">Include container weight and volume on load</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="dc867-104">A funcionalidade para incluir o peso e volume de contêiner em uma carga fornece uma representação perfeita do peso e volume totais de contêineres e de itens que estejam prestes a serem carregados.</span><span class="sxs-lookup"><span data-stu-id="dc867-104">The functionality for including the container weight and volume on a load gives a clear representation of the total weight and volume of containers and items that are going on a load.</span></span>

<span data-ttu-id="dc867-105">Uma carga contém uma ou várias remessas remessa de varejo, e essas remessas contêm itens distintos pertencentes a uma única ordem de venda a várias ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="dc867-105">A load contains a single shipment or multiple shipments, and these shipments contain distinct items that belong to a single sales order or multiple sales orders.</span></span> <span data-ttu-id="dc867-106">Os itens são armazenados em um contêiner, e os contêineres são carregados uma carga.</span><span class="sxs-lookup"><span data-stu-id="dc867-106">The items are stored inside a container, and containers are loaded on a load.</span></span> <span data-ttu-id="dc867-107">Os itens fora de um contêiner também podem fazer parte de uma carga.</span><span class="sxs-lookup"><span data-stu-id="dc867-107">Items that are outside a container can also be part of a load.</span></span> <span data-ttu-id="dc867-108">Com base nessas condições, o sistema calculará valores para peso e volume da carga, considerando o peso e volume de contêineres e de itens.</span><span class="sxs-lookup"><span data-stu-id="dc867-108">Based on these conditions, the system calculates values for the weight and volume on the load by considering the weight and volume of both containers and items.</span></span>

<span data-ttu-id="dc867-109">Se os valores calculados não são precisos, você pode ajustá-los inserindo valores reais do peso e volume na carga.</span><span class="sxs-lookup"><span data-stu-id="dc867-109">If the calculated values aren’t precise, you can adjust them by entering the actual values for the weight and volume on the load.</span></span> <span data-ttu-id="dc867-110">Os valores do peso e volume são usados juntamente processos de gerenciamento de transporte.</span><span class="sxs-lookup"><span data-stu-id="dc867-110">The values for the weight and volume are used in transportation management processes.</span></span> <span data-ttu-id="dc867-111">Por exemplo, os valores são usados na bancada do roteiro de taxa, que ajuda a definir e a taxa a roteiro de cargas, e também são usados para propostas de transporte e check-in do motorista.</span><span class="sxs-lookup"><span data-stu-id="dc867-111">For example, the values are used in the rate route workbench, where they help define the rate and route for loads, and they are also used for transportation tenders and driver check-in.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="dc867-112">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="dc867-112">Where it applies</span></span>

<span data-ttu-id="dc867-113">A funcionalidade para incluir o peso e volume de contêiner em uma carga aplica-se em processos gerenciamento de transporte, como bancada de roteiro de taxa, as propostas de transporte e check-in do motorista.</span><span class="sxs-lookup"><span data-stu-id="dc867-113">The functionality for including the container weight and volume on a load applies in transportation management processes, such as the rate route workbench, transportation tenders, and driver check-in.</span></span>

## <a name="how-it-is-set-up"></a><span data-ttu-id="dc867-114">Como é configurada</span><span class="sxs-lookup"><span data-stu-id="dc867-114">How it is set up</span></span>

<span data-ttu-id="dc867-115">O número de contêineres que devem ser considerados para uma carga ser calculada com base no peso e volume do contêiner e, em porcentagem de contêiner é usado.</span><span class="sxs-lookup"><span data-stu-id="dc867-115">The number of containers that should be considered for a load is calculated based on the weight and volume of the container, and on the percentage of the container is used.</span></span>

-   <span data-ttu-id="dc867-116">Para definir o peso e volume de um contêiner, clique em **Gerenciamento de depósito** \> **Configuração** \> **Contêineres** \> **Tipos de contêiner**.</span><span class="sxs-lookup"><span data-stu-id="dc867-116">To set the weight and volume for a container, click **Warehouse management** \> **Setup** \> **Containers** \> **Container types**.</span></span>

-   <span data-ttu-id="dc867-117">Para definir a porcentagem de utilização de contêiner, clique em **Gerenciamento de depósito** \> **Configuração** \> **Contêineres** \> **Grupos de contêiner**, e insira o valor no campo **Porcentagem de utilização do contêiner**.</span><span class="sxs-lookup"><span data-stu-id="dc867-117">To set the container utilization percentage, click **Warehouse management** \> **Setup** \> **Containers** \> **Container groups**, and then enter a value in the **Container utilization percentage** field.</span></span>
