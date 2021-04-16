---
title: Criar uma nomenclatura de produtos de grades de produto predefinidas
description: Este tópico explica como configurar uma nomenclatura de número de produto para grades de produtos predefinidas e como você pode atribuí-la ao grupo de dimensões do produto apropriado.
author: ShylaThompson
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8c69dc3f8e70c3b0a760f54d2251757ac997a432
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841614"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a><span data-ttu-id="79883-103">Criar uma nomenclatura de produtos de grades de produto predefinidas</span><span class="sxs-lookup"><span data-stu-id="79883-103">Create a product number nomenclature for predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="79883-104">Este tópico explica como configurar uma nomenclatura de número de produto para grades de produtos predefinidas e como você pode atribuí-la ao grupo de dimensões do produto apropriado.</span><span class="sxs-lookup"><span data-stu-id="79883-104">This topic explains how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="79883-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="79883-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="79883-106">A nova nomenclatura de número de produto é atribuída ao grupo de dimensão de produto Cor e Tamanho.</span><span class="sxs-lookup"><span data-stu-id="79883-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="79883-107">A tarefa geralmente seria realizada por um designer de produto.</span><span class="sxs-lookup"><span data-stu-id="79883-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="79883-108">Criar uma nomenclatura de número de produto</span><span class="sxs-lookup"><span data-stu-id="79883-108">Create a product number nomenclature</span></span>
1. <span data-ttu-id="79883-109">Selecione **Definição de modelo de variante de produto**.</span><span class="sxs-lookup"><span data-stu-id="79883-109">Select **Product variant model definition**.</span></span>
2. <span data-ttu-id="79883-110">​Selecione **Nomenclatura de número de produto**.</span><span class="sxs-lookup"><span data-stu-id="79883-110">Select **Product nomenclature**.</span></span>
3. <span data-ttu-id="79883-111">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="79883-111">Select **New**.</span></span>
4. <span data-ttu-id="79883-112">No campo **Nome**, digite um nome de nomenclatura que ajude a identificar o grupo de dimensões do produto de destino, por exemplo, `ColorSize`.</span><span class="sxs-lookup"><span data-stu-id="79883-112">In the **Name** field, enter a nomenclature name that helps to identify the target product dimension group, for example, `ColorSize`.</span></span>
5. <span data-ttu-id="79883-113">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="79883-113">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="79883-114">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="79883-114">Select **Add**.</span></span>
7. <span data-ttu-id="79883-115">Selecione o número do **Produto mestre**.</span><span class="sxs-lookup"><span data-stu-id="79883-115">Select **Product master** number.</span></span>
8. <span data-ttu-id="79883-116">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="79883-116">Select **Add**.</span></span>
9. <span data-ttu-id="79883-117">Selecione **Constante de texto**.</span><span class="sxs-lookup"><span data-stu-id="79883-117">Select **Text constant**.</span></span>
10. <span data-ttu-id="79883-118">No campo **Texto**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="79883-118">In the **Text** field, type a value.</span></span>
11. <span data-ttu-id="79883-119">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="79883-119">Select **Add**.</span></span>
12. <span data-ttu-id="79883-120">Selecione **Cor**.</span><span class="sxs-lookup"><span data-stu-id="79883-120">Select **Color**.</span></span>
13. <span data-ttu-id="79883-121">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="79883-121">Select **Add**.</span></span>
14. <span data-ttu-id="79883-122">Selecione **Constante de texto**.</span><span class="sxs-lookup"><span data-stu-id="79883-122">Select **Text constant**.</span></span>
15. <span data-ttu-id="79883-123">No campo **Texto**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="79883-123">In the **Text** field, type a value.</span></span>
16. <span data-ttu-id="79883-124">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="79883-124">Select **Add**.</span></span>
17. <span data-ttu-id="79883-125">Selecione **Tamanho**.</span><span class="sxs-lookup"><span data-stu-id="79883-125">Select **Size**.</span></span>
18. <span data-ttu-id="79883-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="79883-126">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="79883-127">Atribuir a nomenclatura a um produto mestre</span><span class="sxs-lookup"><span data-stu-id="79883-127">Assign the nomenclature to a product master</span></span>
1. <span data-ttu-id="79883-128">Selecione **Grupos de dimensões de produto**.</span><span class="sxs-lookup"><span data-stu-id="79883-128">Select **Product dimension groups**.</span></span>
2. <span data-ttu-id="79883-129">Selecione o grupo **Dimensão do produto SizeCol**.</span><span class="sxs-lookup"><span data-stu-id="79883-129">Select the **SizeCol product dimension** group.</span></span>
3. <span data-ttu-id="79883-130">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="79883-130">Select **Edit**.</span></span>
4. <span data-ttu-id="79883-131">Selecione **Sim** no campo **Usar nomenclatura**.</span><span class="sxs-lookup"><span data-stu-id="79883-131">Select **Yes** in the **Use nomenclature** field.</span></span>
5. <span data-ttu-id="79883-132">No campo **Nomenclatura de número de grade de produto**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="79883-132">In the **Product variant number nomenclature** field, enter or select a value.</span></span>
6. <span data-ttu-id="79883-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="79883-133">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]