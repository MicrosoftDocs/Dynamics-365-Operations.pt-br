---
title: Criar uma nomenclatura de produtos de grades de produto predefinidas
description: Este tópico explica como configurar uma nomenclatura de número de produto para grades de produtos predefinidas e como você pode atribuí-la ao grupo de dimensões do produto apropriado.
author: ShylaThompson
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5cf0efeac2851e6ead6fc5e15a016370dfa620bc
ms.sourcegitcommit: e10491a2ff04f65d9f306ef6e068ee123213b23b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/21/2019
ms.locfileid: "1914898"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a><span data-ttu-id="98cad-103">Criar uma nomenclatura de produtos de grades de produto predefinidas</span><span class="sxs-lookup"><span data-stu-id="98cad-103">Create a product number nomenclature for predefined product variants</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="98cad-104">Este tópico explica como configurar uma nomenclatura de número de produto para grades de produtos predefinidas e como você pode atribuí-la ao grupo de dimensões do produto apropriado.</span><span class="sxs-lookup"><span data-stu-id="98cad-104">This topic explains how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="98cad-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="98cad-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="98cad-106">A nova nomenclatura de número de produto é atribuída ao grupo de dimensão de produto Cor e Tamanho.</span><span class="sxs-lookup"><span data-stu-id="98cad-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="98cad-107">A tarefa geralmente seria realizada por um designer de produto.</span><span class="sxs-lookup"><span data-stu-id="98cad-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="98cad-108">Criar uma nomenclatura de número de produto</span><span class="sxs-lookup"><span data-stu-id="98cad-108">Create a product number nomenclature</span></span>
1. <span data-ttu-id="98cad-109">Selecione **Definição de modelo de variante de produto**.</span><span class="sxs-lookup"><span data-stu-id="98cad-109">Select **Product variant model definition**.</span></span>
2. <span data-ttu-id="98cad-110">​Selecione **Nomenclatura de número de produto**.</span><span class="sxs-lookup"><span data-stu-id="98cad-110">Select **Product nomenclature**.</span></span>
3. <span data-ttu-id="98cad-111">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="98cad-111">Select **New**.</span></span>
4. <span data-ttu-id="98cad-112">No campo **Nome**, digite um nome de nomenclatura que ajude a identificar o grupo de dimensões do produto de destino, por exemplo, `ColorSize`.</span><span class="sxs-lookup"><span data-stu-id="98cad-112">In the **Name** field, enter a nomenclature name that helps to identify the target product dimension group, for example, `ColorSize`.</span></span>
5. <span data-ttu-id="98cad-113">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="98cad-113">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="98cad-114">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="98cad-114">Select **Add**.</span></span>
7. <span data-ttu-id="98cad-115">Selecione o número do **Produto mestre**.</span><span class="sxs-lookup"><span data-stu-id="98cad-115">Select **Product master** number.</span></span>
8. <span data-ttu-id="98cad-116">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="98cad-116">Select **Add**.</span></span>
9. <span data-ttu-id="98cad-117">Selecione **Constante de texto**.</span><span class="sxs-lookup"><span data-stu-id="98cad-117">Select **Text constant**.</span></span>
10. <span data-ttu-id="98cad-118">No campo **Texto**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="98cad-118">In the **Text** field, type a value.</span></span>
11. <span data-ttu-id="98cad-119">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="98cad-119">Select **Add**.</span></span>
12. <span data-ttu-id="98cad-120">Selecione **Cor**.</span><span class="sxs-lookup"><span data-stu-id="98cad-120">Select **Color**.</span></span>
13. <span data-ttu-id="98cad-121">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="98cad-121">Select **Add**.</span></span>
14. <span data-ttu-id="98cad-122">Selecione **Constante de texto**.</span><span class="sxs-lookup"><span data-stu-id="98cad-122">Select **Text constant**.</span></span>
15. <span data-ttu-id="98cad-123">No campo **Texto**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="98cad-123">In the **Text** field, type a value.</span></span>
16. <span data-ttu-id="98cad-124">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="98cad-124">Select **Add**.</span></span>
17. <span data-ttu-id="98cad-125">Selecione **Tamanho**.</span><span class="sxs-lookup"><span data-stu-id="98cad-125">Select **Size**.</span></span>
18. <span data-ttu-id="98cad-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="98cad-126">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="98cad-127">Atribuir a nomenclatura a um produto mestre</span><span class="sxs-lookup"><span data-stu-id="98cad-127">Assign the nomenclature to a product master</span></span>
1. <span data-ttu-id="98cad-128">Selecione **Grupos de dimensões de produto**.</span><span class="sxs-lookup"><span data-stu-id="98cad-128">Select **Product dimension groups**.</span></span>
2. <span data-ttu-id="98cad-129">Selecione o grupo **Dimensão do produto SizeCol**.</span><span class="sxs-lookup"><span data-stu-id="98cad-129">Select the **SizeCol product dimension** group.</span></span>
3. <span data-ttu-id="98cad-130">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="98cad-130">Select **Edit**.</span></span>
4. <span data-ttu-id="98cad-131">Selecione **Sim** no campo **Usar nomenclatura**.</span><span class="sxs-lookup"><span data-stu-id="98cad-131">Select **Yes** in the **Use nomenclature** field.</span></span>
5. <span data-ttu-id="98cad-132">No campo **Nomenclatura de número de grade de produto**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="98cad-132">In the **Product variant number nomenclature** field, enter or select a value.</span></span>
6. <span data-ttu-id="98cad-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="98cad-133">Close the page.</span></span>

