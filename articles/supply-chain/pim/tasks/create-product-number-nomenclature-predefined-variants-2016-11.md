---
title: Criar uma nomenclatura de produtos de grades de produto predefinidas
description: Este guia mostra como configurar uma nomenclatura de número de produto para grades de produtos predefinidas e como você pode atribuí-la ao grupo de dimensões do produto apropriado.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4b49e96677b94d5f669ea41861f64e62e118938c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "364870"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a><span data-ttu-id="d8d2e-103">Criar uma nomenclatura de produtos de grades de produto predefinidas</span><span class="sxs-lookup"><span data-stu-id="d8d2e-103">Create a product number nomenclature for predefined product variants</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d8d2e-104">Este guia mostra como configurar uma nomenclatura de número de produto para grades de produtos predefinidas e como você pode atribuí-la ao grupo de dimensões do produto apropriado.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-104">This guide shows you how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="d8d2e-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="d8d2e-106">A nova nomenclatura de número de produto é atribuída ao grupo de dimensão de produto Cor e Tamanho.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="d8d2e-107">A tarefa geralmente seria realizada por um designer de produto.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="d8d2e-108">Criar uma nomenclatura de número de produto</span><span class="sxs-lookup"><span data-stu-id="d8d2e-108">Create a product number nomenclature</span></span>
1. <span data-ttu-id="d8d2e-109">Clique em Definição de modelo de variante de produto.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="d8d2e-110">Clique em Nomenclatura de produto.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-110">Click Product nomenclature.</span></span>
3. <span data-ttu-id="d8d2e-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-111">Click New.</span></span>
4. <span data-ttu-id="d8d2e-112">No campo Nome, digite um nome de nomenclatura que ajude a identificar o grupo de dimensões do produto de destino, por exemplo, ColorSize.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-112">In the Name field, enter a nomenclature name that helps to identify the target product dimension group, for example, ColorSize..</span></span>
5. <span data-ttu-id="d8d2e-113">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-113">In the Description field, type a value.</span></span>
6. <span data-ttu-id="d8d2e-114">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-114">Click Add.</span></span>
7. <span data-ttu-id="d8d2e-115">Clique em Número do produto mestre.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-115">Click Product master number.</span></span>
8. <span data-ttu-id="d8d2e-116">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-116">Click Add.</span></span>
9. <span data-ttu-id="d8d2e-117">Clique em Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-117">Click Text constant.</span></span>
10. <span data-ttu-id="d8d2e-118">No campo Texto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-118">In the Text field, type a value.</span></span>
11. <span data-ttu-id="d8d2e-119">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-119">Click Add.</span></span>
12. <span data-ttu-id="d8d2e-120">Clique em Cor.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-120">Click Color.</span></span>
13. <span data-ttu-id="d8d2e-121">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-121">Click Add.</span></span>
14. <span data-ttu-id="d8d2e-122">Clique em Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-122">Click Text constant.</span></span>
15. <span data-ttu-id="d8d2e-123">No campo Texto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-123">In the Text field, type a value.</span></span>
16. <span data-ttu-id="d8d2e-124">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-124">Click Add.</span></span>
17. <span data-ttu-id="d8d2e-125">Clique em Tamanho.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-125">Click Size.</span></span>
18. <span data-ttu-id="d8d2e-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-126">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="d8d2e-127">Atribuir a nomenclatura a um produto mestre</span><span class="sxs-lookup"><span data-stu-id="d8d2e-127">Assign the nomenclature to a product master</span></span>
1. <span data-ttu-id="d8d2e-128">Clique em Grupos de dimensões do produto.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-128">Click Product dimension groups.</span></span>
2. <span data-ttu-id="d8d2e-129">Selecione o grupo de dimensões do produto SizeCol.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-129">Select the SizeCol product dimension group.</span></span>
3. <span data-ttu-id="d8d2e-130">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-130">Click Edit.</span></span>
4. <span data-ttu-id="d8d2e-131">Selecione Sim no campo Usar nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-131">Select Yes in the Use nomenclature field.</span></span>
5. <span data-ttu-id="d8d2e-132">No campo Nomenclatura de número de grade de produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-132">In the Product variant number nomenclature field, enter or select a value.</span></span>
6. <span data-ttu-id="d8d2e-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d8d2e-133">Close the page.</span></span>

