---
title: "Localizações de estoque"
description: "As localizações de estoque são usadas com o depósito básico (WMS I) para determinar onde os itens serão armazenados e onde os itens serão separados em um depósito WMS I."
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSLocation
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2134
ms.assetid: 69bf6922-4151-447f-b678-4ba95637f54c
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 2a0af10d1d94f9ead2b024e1afd009d60ee13590
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="inventory-locations"></a><span data-ttu-id="a6d53-103">Localizações de estoque</span><span class="sxs-lookup"><span data-stu-id="a6d53-103">Inventory locations</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="a6d53-104">As localizações de estoque são usadas com o depósito básico (WMS I) para determinar onde os itens serão armazenados e onde os itens serão separados em um depósito WMS I.</span><span class="sxs-lookup"><span data-stu-id="a6d53-104">Inventory locations are used with basic warehousing (WMS I) to determine where items are stored and where items are picked from in a WMS I warehouse.</span></span>

<span data-ttu-id="a6d53-105">Este tópico se aplica aos recursos do módulo Gerenciamento de estoque.</span><span class="sxs-lookup"><span data-stu-id="a6d53-105">This topic applies to features in the Inventory management module.</span></span> <span data-ttu-id="a6d53-106">Não se aplica aos recursos do módulo de Gerenciamento de depósito.</span><span class="sxs-lookup"><span data-stu-id="a6d53-106">It does not apply to features in the Warehouse management module.</span></span>

<span data-ttu-id="a6d53-107">O termo localização se refere ao lugar de onde os itens são extraídos.</span><span class="sxs-lookup"><span data-stu-id="a6d53-107">The term location refers to the place that items are stored and drawn from.</span></span>

<span data-ttu-id="a6d53-108">Para cada localização, o lugar em que o item é inserido também deve ser especificado.</span><span class="sxs-lookup"><span data-stu-id="a6d53-108">For each location, the place where the item is inserted can also be specified.</span></span> <span data-ttu-id="a6d53-109">Por padrão, eles são iguais.</span><span class="sxs-lookup"><span data-stu-id="a6d53-109">By default, they are the same.</span></span> <span data-ttu-id="a6d53-110">Geralmente, os itens são inseridos e extraídos do mesmo lado da localização, mas nem sempre.</span><span class="sxs-lookup"><span data-stu-id="a6d53-110">Items are usually inserted and drawn from the same side of a location, but not always.</span></span> <span data-ttu-id="a6d53-111">Por exemplo, os itens armazenados em racks de armazenamento dinâmicos são inseridos de um corredor e extraídos de outro.</span><span class="sxs-lookup"><span data-stu-id="a6d53-111">For example, items that are stored in live storage racks are inserted from one aisle and drawn from another.</span></span> <span data-ttu-id="a6d53-112">A entrada principal é fornecida pelo nome da localização, que geralmente é definida pelas suas coordenadas: depósito, corredor, rack, prateleira e compartimento.</span><span class="sxs-lookup"><span data-stu-id="a6d53-112">The main input is given by a location name, which is usually determined by its coordinates: warehouse, aisle, rack, shelf, and bin.</span></span> <span data-ttu-id="a6d53-113">Esse nome ou essa ID é inserida manualmente ou gerada a partir das coordenadas da localização, por exemplo, 01-02-03-4 para o corredor 1, rack 2, prateleira 3, compartimento 4 na página Localizações de estoque.</span><span class="sxs-lookup"><span data-stu-id="a6d53-113">This name or ID can be entered manually or generated from the location coordinates—for example, 01-02-03-4 for aisle 1, rack 2, shelf 3, bin 4 in the Inventory locations page.</span></span>
<span data-ttu-id="a6d53-114">Propriedades da localização</span><span class="sxs-lookup"><span data-stu-id="a6d53-114">Location properties</span></span>

<span data-ttu-id="a6d53-115">Uma localização possui as seguintes características:</span><span class="sxs-lookup"><span data-stu-id="a6d53-115">A location has the following characteristics:</span></span>
-   <span data-ttu-id="a6d53-116">Tamanho (altura, largura e profundidade e, portanto, volume)</span><span class="sxs-lookup"><span data-stu-id="a6d53-116">Size (height, width, depth, and thereby volume)</span></span>
-   <span data-ttu-id="a6d53-117">Depósito, corredor, rack, prateleira e posição do compartimento.</span><span class="sxs-lookup"><span data-stu-id="a6d53-117">Warehouse, aisle, rack, shelf, and bin position</span></span>
-   <span data-ttu-id="a6d53-118">Tipo de localização (localização em massa, local de separação, doca de entrada, doca de saída, localização de entrada de produção, local de inspeção ou supermercado de kanban)</span><span class="sxs-lookup"><span data-stu-id="a6d53-118">Location type (bulk location, picking location, inbound dock, outbound dock, production input location, inspection location, or kanban supermarket)</span></span>

<span data-ttu-id="a6d53-119">O texto de verificação pode ser utilizado nos sistemas online para verificar se o operador selecionou a localização correta para um item específico.</span><span class="sxs-lookup"><span data-stu-id="a6d53-119">Check text can be used in online systems to verify that the operator has selected the correct location for a specific item.</span></span> <span data-ttu-id="a6d53-120">Este texto de verificação pode ser criado manualmente ou por padrão.</span><span class="sxs-lookup"><span data-stu-id="a6d53-120">This check text can be created manually or by default.</span></span>

## <a name="sort-codes"></a><span data-ttu-id="a6d53-121">Códigos de classificação</span><span class="sxs-lookup"><span data-stu-id="a6d53-121">Sort codes</span></span>
<span data-ttu-id="a6d53-122">Use os códigos de classificação para otimizar o manuseio das linhas de separação, que descrevem as informações necessárias para a separação de itens de estoque, incluindo a ordem de separação.</span><span class="sxs-lookup"><span data-stu-id="a6d53-122">Use sort codes to optimize the handling of picking lines, which describe the information that is required for picking items from inventory, including the picking order.</span></span> <span data-ttu-id="a6d53-123">Os códigos de classificação podem ser especificados pelo corredor e demais coordenadas ou atribuídos manualmente à localização.</span><span class="sxs-lookup"><span data-stu-id="a6d53-123">Sort codes can be specified by the aisle and other coordinates, or assigned manually for the location.</span></span>

## <a name="blocked-locations"></a><span data-ttu-id="a6d53-124">Localizações bloqueadas</span><span class="sxs-lookup"><span data-stu-id="a6d53-124">Blocked locations</span></span>
<span data-ttu-id="a6d53-125">Ocasionalmente, talvez você queira indicar que uma localização está bloqueada por um período, por exemplo, para permitir reparos.</span><span class="sxs-lookup"><span data-stu-id="a6d53-125">Occasionally, you might want to indicate that a location is blocked for a period of time, for example, to allow for repairs.</span></span> <span data-ttu-id="a6d53-126">Outras vezes, talvez você queira indicar o bloqueio somente da entrada ou da saída.</span><span class="sxs-lookup"><span data-stu-id="a6d53-126">At other times, you may want to indicate blocking of only the input or only output.</span></span>

## <a name="tree-structure"></a><span data-ttu-id="a6d53-127">Estrutura de árvore</span><span class="sxs-lookup"><span data-stu-id="a6d53-127">Tree structure</span></span>

<span data-ttu-id="a6d53-128">Na página Localizações de estoque, você pode exibir o layout do depósito em uma estrutura de árvore com base nas coordenadas das localizações de estoque, em um formato de exibição definido.</span><span class="sxs-lookup"><span data-stu-id="a6d53-128">In the Inventory locations page, you can view the warehouse layout in a tree structure based on the coordinates of inventory locations, in a defined display format.</span></span>

## <a name="maintain-inventory-locations-via-the-warehouse-form"></a><span data-ttu-id="a6d53-129">Manter localizações de estoque por meio do formulário do depósito</span><span class="sxs-lookup"><span data-stu-id="a6d53-129">Maintain inventory locations via the warehouse form</span></span>

<span data-ttu-id="a6d53-130">É possível copiar localizações de um depósito para outro e criar localizações por meio de um assistente.</span><span class="sxs-lookup"><span data-stu-id="a6d53-130">It is possible to copy locations from one warehouse to another and to create locations via a wizard.</span></span> <span data-ttu-id="a6d53-131">Antes de executar o assistente você deve garantir que você definiu os nomes da localização padrão na página Depósito.</span><span class="sxs-lookup"><span data-stu-id="a6d53-131">Before you run the wizard you should make sure that you have defined the default location names on the Warehouse page.</span></span>



<a name="see-also"></a><span data-ttu-id="a6d53-132">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a6d53-132">See also</span></span>
--------

[<span data-ttu-id="a6d53-133">Criar um layout de depósito (Guia de tarefas)</span><span class="sxs-lookup"><span data-stu-id="a6d53-133">Create a new warehouse layout (Task guide)</span></span>](tasks/create-new-warehouse-layout.md)

