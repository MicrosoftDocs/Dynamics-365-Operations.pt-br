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
ms.openlocfilehash: 4bb73854f52525c0722683086d1b4f1dd7173306
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920648"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a><span data-ttu-id="6f394-103">Criar uma nomenclatura de produtos de grades de produto predefinidas</span><span class="sxs-lookup"><span data-stu-id="6f394-103">Create a product number nomenclature for predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6f394-104">Este tópico explica como configurar uma nomenclatura de número de produto para grades de produtos predefinidas e como você pode atribuí-la ao grupo de dimensões do produto apropriado.</span><span class="sxs-lookup"><span data-stu-id="6f394-104">This topic explains how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="6f394-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="6f394-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="6f394-106">A nova nomenclatura de número de produto é atribuída ao grupo de dimensão de produto Cor e Tamanho.</span><span class="sxs-lookup"><span data-stu-id="6f394-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="6f394-107">A tarefa geralmente seria realizada por um designer de produto.</span><span class="sxs-lookup"><span data-stu-id="6f394-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="6f394-108">Criar uma nomenclatura de número de produto</span><span class="sxs-lookup"><span data-stu-id="6f394-108">Create a product number nomenclature</span></span>

1. <span data-ttu-id="6f394-109">Vá para **Gerenciamento de informações sobre produtos \> Configuração \> Nomenclatura de produto**.</span><span class="sxs-lookup"><span data-stu-id="6f394-109">Go to **Product information management \> Setup \> Product nomenclature**.</span></span>
1. <span data-ttu-id="6f394-110">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="6f394-110">Select **New**.</span></span>
1. <span data-ttu-id="6f394-111">No campo **Nome**, digite um nome de nomenclatura que ajude a identificar o grupo de dimensões do produto de destino, por exemplo, `ColorSize`.</span><span class="sxs-lookup"><span data-stu-id="6f394-111">In the **Name** field, enter a nomenclature name that helps to identify the target product dimension group, for example, `ColorSize`.</span></span>
1. <span data-ttu-id="6f394-112">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6f394-112">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="6f394-113">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="6f394-113">Select **Add**.</span></span>
1. <span data-ttu-id="6f394-114">Selecione o número do **Produto mestre**.</span><span class="sxs-lookup"><span data-stu-id="6f394-114">Select **Product master** number.</span></span>
1. <span data-ttu-id="6f394-115">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="6f394-115">Select **Add**.</span></span>
1. <span data-ttu-id="6f394-116">Selecione **Constante de texto**.</span><span class="sxs-lookup"><span data-stu-id="6f394-116">Select **Text constant**.</span></span>
1. <span data-ttu-id="6f394-117">No campo **Texto**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6f394-117">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="6f394-118">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="6f394-118">Select **Add**.</span></span>
1. <span data-ttu-id="6f394-119">Selecione **Cor**.</span><span class="sxs-lookup"><span data-stu-id="6f394-119">Select **Color**.</span></span>
1. <span data-ttu-id="6f394-120">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="6f394-120">Select **Add**.</span></span>
1. <span data-ttu-id="6f394-121">Selecione **Constante de texto**.</span><span class="sxs-lookup"><span data-stu-id="6f394-121">Select **Text constant**.</span></span>
1. <span data-ttu-id="6f394-122">No campo **Texto**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6f394-122">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="6f394-123">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="6f394-123">Select **Add**.</span></span>
1. <span data-ttu-id="6f394-124">Selecione **Tamanho**.</span><span class="sxs-lookup"><span data-stu-id="6f394-124">Select **Size**.</span></span>
1. <span data-ttu-id="6f394-125">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6f394-125">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="6f394-126">Atribuir a nomenclatura a um produto mestre</span><span class="sxs-lookup"><span data-stu-id="6f394-126">Assign the nomenclature to a product master</span></span>

1. <span data-ttu-id="6f394-127">Selecione **Grupos de dimensões de produto**.</span><span class="sxs-lookup"><span data-stu-id="6f394-127">Select **Product dimension groups**.</span></span>
2. <span data-ttu-id="6f394-128">Selecione o grupo **Dimensão do produto SizeCol**.</span><span class="sxs-lookup"><span data-stu-id="6f394-128">Select the **SizeCol product dimension** group.</span></span>
3. <span data-ttu-id="6f394-129">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6f394-129">Select **Edit**.</span></span>
4. <span data-ttu-id="6f394-130">Selecione **Sim** no campo **Usar nomenclatura**.</span><span class="sxs-lookup"><span data-stu-id="6f394-130">Select **Yes** in the **Use nomenclature** field.</span></span>
5. <span data-ttu-id="6f394-131">No campo **Nomenclatura de número de grade de produto**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="6f394-131">In the **Product variant number nomenclature** field, enter or select a value.</span></span>
6. <span data-ttu-id="6f394-132">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6f394-132">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]