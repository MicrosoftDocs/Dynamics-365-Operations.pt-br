---
title: Criar uma nomenclatura de produtos de grades de produto predefinidas
description: Este tópico explica como configurar uma nomenclatura de número de produto para grades de produtos predefinidas e como você pode atribuí-la ao grupo de dimensões do produto apropriado.
author: ShylaThompson
manager: tfehr
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3a15d1f4ecbf85e22bfadc1dd680d24bc56d807f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007532"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a><span data-ttu-id="8589c-103">Criar uma nomenclatura de produtos de grades de produto predefinidas</span><span class="sxs-lookup"><span data-stu-id="8589c-103">Create a product number nomenclature for predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8589c-104">Este tópico explica como configurar uma nomenclatura de número de produto para grades de produtos predefinidas e como você pode atribuí-la ao grupo de dimensões do produto apropriado.</span><span class="sxs-lookup"><span data-stu-id="8589c-104">This topic explains how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="8589c-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="8589c-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="8589c-106">A nova nomenclatura de número de produto é atribuída ao grupo de dimensão de produto Cor e Tamanho.</span><span class="sxs-lookup"><span data-stu-id="8589c-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="8589c-107">A tarefa geralmente seria realizada por um designer de produto.</span><span class="sxs-lookup"><span data-stu-id="8589c-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="8589c-108">Criar uma nomenclatura de número de produto</span><span class="sxs-lookup"><span data-stu-id="8589c-108">Create a product number nomenclature</span></span>
1. <span data-ttu-id="8589c-109">Selecione **Definição de modelo de variante de produto**.</span><span class="sxs-lookup"><span data-stu-id="8589c-109">Select **Product variant model definition**.</span></span>
2. <span data-ttu-id="8589c-110">​Selecione **Nomenclatura de número de produto**.</span><span class="sxs-lookup"><span data-stu-id="8589c-110">Select **Product nomenclature**.</span></span>
3. <span data-ttu-id="8589c-111">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8589c-111">Select **New**.</span></span>
4. <span data-ttu-id="8589c-112">No campo **Nome**, digite um nome de nomenclatura que ajude a identificar o grupo de dimensões do produto de destino, por exemplo, `ColorSize`.</span><span class="sxs-lookup"><span data-stu-id="8589c-112">In the **Name** field, enter a nomenclature name that helps to identify the target product dimension group, for example, `ColorSize`.</span></span>
5. <span data-ttu-id="8589c-113">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8589c-113">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="8589c-114">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8589c-114">Select **Add**.</span></span>
7. <span data-ttu-id="8589c-115">Selecione o número do **Produto mestre**.</span><span class="sxs-lookup"><span data-stu-id="8589c-115">Select **Product master** number.</span></span>
8. <span data-ttu-id="8589c-116">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8589c-116">Select **Add**.</span></span>
9. <span data-ttu-id="8589c-117">Selecione **Constante de texto**.</span><span class="sxs-lookup"><span data-stu-id="8589c-117">Select **Text constant**.</span></span>
10. <span data-ttu-id="8589c-118">No campo **Texto**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8589c-118">In the **Text** field, type a value.</span></span>
11. <span data-ttu-id="8589c-119">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8589c-119">Select **Add**.</span></span>
12. <span data-ttu-id="8589c-120">Selecione **Cor**.</span><span class="sxs-lookup"><span data-stu-id="8589c-120">Select **Color**.</span></span>
13. <span data-ttu-id="8589c-121">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8589c-121">Select **Add**.</span></span>
14. <span data-ttu-id="8589c-122">Selecione **Constante de texto**.</span><span class="sxs-lookup"><span data-stu-id="8589c-122">Select **Text constant**.</span></span>
15. <span data-ttu-id="8589c-123">No campo **Texto**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8589c-123">In the **Text** field, type a value.</span></span>
16. <span data-ttu-id="8589c-124">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8589c-124">Select **Add**.</span></span>
17. <span data-ttu-id="8589c-125">Selecione **Tamanho**.</span><span class="sxs-lookup"><span data-stu-id="8589c-125">Select **Size**.</span></span>
18. <span data-ttu-id="8589c-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8589c-126">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="8589c-127">Atribuir a nomenclatura a um produto mestre</span><span class="sxs-lookup"><span data-stu-id="8589c-127">Assign the nomenclature to a product master</span></span>
1. <span data-ttu-id="8589c-128">Selecione **Grupos de dimensões de produto**.</span><span class="sxs-lookup"><span data-stu-id="8589c-128">Select **Product dimension groups**.</span></span>
2. <span data-ttu-id="8589c-129">Selecione o grupo **Dimensão do produto SizeCol**.</span><span class="sxs-lookup"><span data-stu-id="8589c-129">Select the **SizeCol product dimension** group.</span></span>
3. <span data-ttu-id="8589c-130">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="8589c-130">Select **Edit**.</span></span>
4. <span data-ttu-id="8589c-131">Selecione **Sim** no campo **Usar nomenclatura**.</span><span class="sxs-lookup"><span data-stu-id="8589c-131">Select **Yes** in the **Use nomenclature** field.</span></span>
5. <span data-ttu-id="8589c-132">No campo **Nomenclatura de número de grade de produto**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="8589c-132">In the **Product variant number nomenclature** field, enter or select a value.</span></span>
6. <span data-ttu-id="8589c-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8589c-133">Close the page.</span></span>

