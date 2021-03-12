---
title: Itens fantasma
description: Este tópico descreve, em detalhes, como o tipo de linha fantasma pode ser usado para as linhas de uma lista de materiais (BOM) e uma fórmula no Dynamics 365 Supply Chain Management.
author: ShylaThompson
manager: tfehr
ms.date: 06/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.search.region: Global
ms.author: kamaybac
ms.search.validfrom: ''
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 02c4994fe6df192937f92f0167a3127ff2a8a588
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966320"
---
# <a name="phantom-items"></a><span data-ttu-id="46911-103">Itens fantasma</span><span class="sxs-lookup"><span data-stu-id="46911-103">Phantom items</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="46911-104">Este tópico descreve, em detalhes, como o tipo de linha fantasma pode ser usado para as linhas de uma lista de materiais (BOM) e uma fórmula.</span><span class="sxs-lookup"><span data-stu-id="46911-104">This topic describes, in detail, how the Phantom line type can be used for the lines of a bill of materials (BOM) and a formula.</span></span> <span data-ttu-id="46911-105">Na ilustração a seguir, (a) é a BOM dos produtos H e peças F e G, e (b) é a planilha de roteiro dos produtos H e peça F.</span><span class="sxs-lookup"><span data-stu-id="46911-105">In the following illustration, (a) is the BOM for product H and parts F and G, and (b) is the route sheet for products H and part F.</span></span>

![Produto H e peça F](media/product-H-part-F.png)


<span data-ttu-id="46911-107">Esta ilustração mostra um exemplo de uma estrutura de BOM em dois níveis.</span><span class="sxs-lookup"><span data-stu-id="46911-107">This illustration shows an example of a BOM structure in two levels.</span></span> <span data-ttu-id="46911-108">O produto finalizado H representa um produto para uma montagem de máquina.</span><span class="sxs-lookup"><span data-stu-id="46911-108">Finished product H represents a product for a machine assembly.</span></span> <span data-ttu-id="46911-109">A montagem da máquina consiste em duas peças, uma unidade elétrica (F) que tem dois materiais (A e B) e um grupo de materiais de embalagem (G) que também tem dois materiais (C e D).</span><span class="sxs-lookup"><span data-stu-id="46911-109">The machine assembly consists of two parts, an electrical unit (F) that has two materials (A and B) and a group of packaging materials (G) that also has two materials (C and D).</span></span> <span data-ttu-id="46911-110">Outro material (E) é usado durante a montagem geral da máquina.</span><span class="sxs-lookup"><span data-stu-id="46911-110">Another material (E) is used during the general assembly of the machine.</span></span>

![Produto H e peça F](media/product-H-part-B.png)

<span data-ttu-id="46911-112">A ilustração anterior representa a BOM de engenharia para o produto. H. Esta estrutura para fornece uma visão geral das peças e componentes da montagem geral da máquina.</span><span class="sxs-lookup"><span data-stu-id="46911-112">The preceding illustration represents the Engineering BOM for product H. This structure provides a good overview of the parts and components of the overall machine assembly.</span></span> <span data-ttu-id="46911-113">Entretanto, embora talvez os designers de produtos prefiram ver a BOM representada dessa maneira, é possível que essa estrutura não represente corretamente a maneira que máquina é criada no chão de fábrica.</span><span class="sxs-lookup"><span data-stu-id="46911-113">However, although product designers might prefer to see the BOM represented in this way, this structure might not correctly represent the way that the machine is built on the shop floor.</span></span> 

<span data-ttu-id="46911-114">Por exemplo, a BOM de engenharia na ilustração anterior indica que a unidade elétrica F é montada como uma parte separada em uma ordem de trabalho separada.</span><span class="sxs-lookup"><span data-stu-id="46911-114">For example, the Engineering BOM in the preceding illustration indicates that electrical unit F is assembled as a separate part on a separate work order.</span></span> <span data-ttu-id="46911-115">Entretanto, no chão de fábrica, pode ser considerado melhor montar a unidade elétrica como parte da montagem geral da máquina, não como uma ordem de trabalho separada.</span><span class="sxs-lookup"><span data-stu-id="46911-115">However, on the shop floor, it might be judged more optimal to assemble the electrical unit as part of the overall machine assembly, not as a separate work order.</span></span>

<span data-ttu-id="46911-116">Essa BOM de engenharia também indica que a peça G é uma peça separada.</span><span class="sxs-lookup"><span data-stu-id="46911-116">This Engineering BOM also indicates that part G is a separate part.</span></span> <span data-ttu-id="46911-117">Entretanto, nessa estrutura, a peça G não representa uma peça física, mas sim uma coleção de materiais de embalagem.</span><span class="sxs-lookup"><span data-stu-id="46911-117">However, in this structure, part G doesn’t represent a physical part but a collection of packaging materials.</span></span> 

<span data-ttu-id="46911-118">Portanto, apesar de uma BOM de engenharia agregar muito valor para a criação de um produto e a manutenção desse design, essa talvez não seja a maneira mais lógica de oferecer suporte ao processo de execução da fabricação do produto.</span><span class="sxs-lookup"><span data-stu-id="46911-118">Therefore, although an Engineering BOM provides great value for the design of a product and maintenance of that design, it might not be the most logical way to support the manufacturing execution process of the product.</span></span> <span data-ttu-id="46911-119">Em contraste, uma BOM de fabricação representa a melhor maneira de criar um produto.</span><span class="sxs-lookup"><span data-stu-id="46911-119">By contrast, a Manufacturing BOM represents the best way to build a product.</span></span>

<span data-ttu-id="46911-120">A ilustração a seguir mostra como a é feita a transição da BOM de engenharia anterior para uma BOM de fabricação.</span><span class="sxs-lookup"><span data-stu-id="46911-120">The following illustration shows how the preceding Engineering BOM is transitioned into a Manufacturing BOM.</span></span> <span data-ttu-id="46911-121">Nesta ilustração, (a) é a BOM do produto H, e (b) é a planilha de roteiro do produto H.</span><span class="sxs-lookup"><span data-stu-id="46911-121">In this illustration, (a) is the BOM for product H, and b is the route sheet for product H.</span></span>

<span data-ttu-id="46911-122">Nesta estrutura, você verá que não há uma noção de peças F e G, e os materiais em que essas peças consistem foram elevados para o próximo nível de BOM.</span><span class="sxs-lookup"><span data-stu-id="46911-122">In this structure, you can see that there is no notion of parts F and G, and the materials that these parts consist of have been elevated to the next BOM level.</span></span> 

<span data-ttu-id="46911-123">Diferentemente da BOM de engenharia, que tinha duas planilhas de operações, a BOM de fabricação tem apenas uma planilha de operações.</span><span class="sxs-lookup"><span data-stu-id="46911-123">Unlike the Engineering BOM, which had two operations sheets, the Manufacturing BOM has only one operations sheet.</span></span> <span data-ttu-id="46911-124">A operação de embalagem que foi vinculada à peça G também foi elevada e agora faz parte da planilha de operações do produto. H. A montagem da unidade elétrica é a primeira operação.</span><span class="sxs-lookup"><span data-stu-id="46911-124">The packaging operation that was linked to part G has also been elevated and is now part of the operations sheet for product H. The assembly of the electrical unit is the first operation.</span></span> <span data-ttu-id="46911-125">Essa ordem faz sentido, porque essa unidade é usada na operação seguinte, a montagem da máquina.</span><span class="sxs-lookup"><span data-stu-id="46911-125">This order makes good sense, because this unit is used in the next operation, which is the machine assembly.</span></span> <span data-ttu-id="46911-126">A última operação é a operação de embalagem, que consume dois materiais de embalagem (C e D).</span><span class="sxs-lookup"><span data-stu-id="46911-126">The last operation is the packaging operation, which consumes two packing materials (C and D).</span></span>

<span data-ttu-id="46911-127">A transição entre a BOM de engenharia e a BOM de fabricação é habilitada por meio do tipo de linha fantasma da BOM.</span><span class="sxs-lookup"><span data-stu-id="46911-127">The transition between the Engineering BOM and the Manufacturing BOM is enabled through the Phantom BOM line type.</span></span> <span data-ttu-id="46911-128">Como o termo “fantasma” já indica, as peças F e G desapareceram durante a transição entre os dois tipos de BOM.</span><span class="sxs-lookup"><span data-stu-id="46911-128">As the term “phantom” indicates, parts F and G have disappeared during the transition between the two BOM types.</span></span> <span data-ttu-id="46911-129">Neste exemplo, o tipo de linha fantasma será aplicado às linhas de BOM das peças F e G na BOM de engenharia.</span><span class="sxs-lookup"><span data-stu-id="46911-129">In this example, the Phantom line type is applied to the BOM lines for parts F and G in the Engineering BOM.</span></span> <span data-ttu-id="46911-130">Quando uma ordem de produção ou de lote é criada, a BOM de engenharia é copiada na ordem de produção ou de lote.</span><span class="sxs-lookup"><span data-stu-id="46911-130">When a production or batch order is created, the Engineering BOM is copied to the production or batch order.</span></span> <span data-ttu-id="46911-131">Em seguida, quando a ordem é estimada, ocorre a transição da BOM de engenharia para a BOM de fabricação, conforme mostrado nas ilustrações anteriores.</span><span class="sxs-lookup"><span data-stu-id="46911-131">Then, when the order is estimated, the transition from the Engineering BOM to the Manufacturing BOM occurs, as shown in the preceding illustrations.</span></span> <span data-ttu-id="46911-132">Na planilha de operações da segunda ilustração, os materiais de embalagem C e D são inseridos para a operação.</span><span class="sxs-lookup"><span data-stu-id="46911-132">From the operations sheet in the second illustration, packaging materials C and D are input for the operation.</span></span> 

## <a name="multilevel-phantom-bom-structures"></a><span data-ttu-id="46911-133">Estruturas fantasma de BOM de vários níveis</span><span class="sxs-lookup"><span data-stu-id="46911-133">Multilevel phantom BOM structures</span></span>
<span data-ttu-id="46911-134">O tipo de linha fantasma pode ser usado em estruturas de BOM de vários níveis, conforme mostrado na ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="46911-134">The Phantom line type can be used in multilevel BOM structures, as shown in the following illustration.</span></span> <span data-ttu-id="46911-135">Nesta ilustração, (a) é a BOM do produto G, e (b) é a planilha de roteiro das peças E e F e do produto G.</span><span class="sxs-lookup"><span data-stu-id="46911-135">In this illustration, (a) is the BOM for product G, and (b) is the route sheet for parts E and F and product G.</span></span> 

![Produto G e peça F com planilhas de roteiro](media/product-G-route-sheet-G.png)


<span data-ttu-id="46911-137">A ilustração a seguir mostra a BOM de fabricação e a planilha de roteiro resultantes se as linhas da BOM das peças E e F são configuradas para que o tipo de linha seja fantasma.</span><span class="sxs-lookup"><span data-stu-id="46911-137">The following illustration shows the resulting Manufacturing BOM and route sheet if the BOM lines for parts E and F are configured so that the line type is Phantom.</span></span> <span data-ttu-id="46911-138">Nesta ilustração, (a) é a BOM do produto G, e (b) é a planilha de roteiro do produto G.</span><span class="sxs-lookup"><span data-stu-id="46911-138">In this illustration, (a) is the BOM for product G, and (b) is the route sheet for product G.</span></span>

![Produto G](media/product-G.png)


## <a name="phantom-and-route-network"></a><span data-ttu-id="46911-140">Rede de roteiro e fantasma</span><span class="sxs-lookup"><span data-stu-id="46911-140">Phantom and route network</span></span>
<span data-ttu-id="46911-141">As BOMs fantasma também podem ser usadas para uma BOM com uma rede de roteiro.</span><span class="sxs-lookup"><span data-stu-id="46911-141">Phantom BOMs can also be used for a BOM that has a route network.</span></span> <span data-ttu-id="46911-142">Em uma rede de roteiro, uma ou várias operações são executadas em paralelo.</span><span class="sxs-lookup"><span data-stu-id="46911-142">In a route network, one or more operations run in parallel.</span></span> <span data-ttu-id="46911-143">A ilustração a seguir mostra um exemplo de uma rede de roteiro usada em uma BOM de vários níveis.</span><span class="sxs-lookup"><span data-stu-id="46911-143">The following illustration shows an example of a route network that is used in a multilevel BOM.</span></span> <span data-ttu-id="46911-144">Nesta ilustração, (a) é a BOM do produto G e peça F, e (b) é a planilha de roteiro do produto G e peça F, que tem uma rede de roteiro.</span><span class="sxs-lookup"><span data-stu-id="46911-144">In this illustration, (a) is the BOM for product G and part F, and (b) is the route sheet for product G and part F, which has a route network.</span></span>

![Produto G e peça F](media/product-G-part-F.png)


<span data-ttu-id="46911-146">Na ilustração a seguir, (a) é a BOM do produto G e peça F, e (b) é a planilha de roteiro do produto G e peça F.</span><span class="sxs-lookup"><span data-stu-id="46911-146">In the following illustration, (a) is the BOM for product G and part F, and (b) is the route sheet for product G and part F.</span></span>

![Produto G e peça F com planilhas de roteiro](media/product-G-part-F-with-route-sheet.png)
