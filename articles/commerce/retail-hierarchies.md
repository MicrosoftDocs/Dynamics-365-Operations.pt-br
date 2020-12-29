---
title: Hierarquias do Commerce
description: Este artigo descreve as hierarquias no Dynamics 365 Commerce.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: OMHierarchyManager, EcoResCategoryHierarchyFactbox
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15851
ms.assetid: dfa11d41-2a0c-4cde-99b6-058c49176c94
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 8f7e4d01970f459f66934fe434ec7307104b39b2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410282"
---
# <a name="commerce-hierarchies"></a><span data-ttu-id="f75e6-103">Hierarquias do Commerce</span><span class="sxs-lookup"><span data-stu-id="f75e6-103">Commerce hierarchies</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f75e6-104">Este artigo descreve as hierarquias no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f75e6-104">This article describes hierarchies in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="f75e6-105">É possível criar uma hierarquia de categoria para organizar os produtos vendidos por meio dos seus canais.</span><span class="sxs-lookup"><span data-stu-id="f75e6-105">You can create a category hierarchy to organize the products that you sell through your channels.</span></span> <span data-ttu-id="f75e6-106">Você pode usar as hierarquias de produtos para categorizar ou agrupar produtos.</span><span class="sxs-lookup"><span data-stu-id="f75e6-106">You can use product hierarchies to categorize or group products.</span></span> <span data-ttu-id="f75e6-107">Esses produtos podem ser usados para criar sortimentos de produtos e programas de fidelidade do cliente.</span><span class="sxs-lookup"><span data-stu-id="f75e6-107">You can then use these products to create product assortments and customer loyalty programs.</span></span> <span data-ttu-id="f75e6-108">Também é possível designar atributos e propriedades de produtos, atribuir uma estrutura de preços, incluir os produtos em promoções de produtos, e usar os produtos em relatórios.</span><span class="sxs-lookup"><span data-stu-id="f75e6-108">You can also assign product attributes and properties, assign a pricing structure, include the products in product promotions, and use the products for reporting.</span></span> <span data-ttu-id="f75e6-109">Você pode criar uma hierarquia de categoria para representar todos os produtos e categorias em sua organização, e depois usar essa hierarquia de categoria para várias finalidades.</span><span class="sxs-lookup"><span data-stu-id="f75e6-109">You can create one category hierarchy to represent all the products and categories in your organization, and then use that category hierarchy for multiple purposes.</span></span> <span data-ttu-id="f75e6-110">Como alternativa, é possível criar várias hierarquias de categoria para finalidades especiais, como promoções de produtos.</span><span class="sxs-lookup"><span data-stu-id="f75e6-110">Alternatively, you can create multiple category hierarchies for special purposes, such as product promotions.</span></span> <span data-ttu-id="f75e6-111">Quando você cria uma hierarquia de produtos, é preciso atribuir um tipo de hierarquia de categoria para identificar a finalidade da hierarquia de categoria.</span><span class="sxs-lookup"><span data-stu-id="f75e6-111">When you create a product hierarchy, you must assign a category hierarchy type to identify the purpose of the category hierarchy.</span></span> <span data-ttu-id="f75e6-112">Por exemplo, somente as hierarquias do produto que são atribuídas ao tipo **Hierarquia de navegação comercial** são mencionadas quando você procura produtos por categoria online ou no ponto de venda (PDV).</span><span class="sxs-lookup"><span data-stu-id="f75e6-112">For example, only product hierarchies that are assigned the **Commerce navigation hierarchy** type are referenced when you browse products by category online or in point of sale (POS).</span></span>

## <a name="hierarchy-types"></a><span data-ttu-id="f75e6-113">Tipos de hierarquia</span><span class="sxs-lookup"><span data-stu-id="f75e6-113">Hierarchy types</span></span>

<span data-ttu-id="f75e6-114">A tabela a seguir lista os tipos de hierarquias de categoria disponíveis e a finalidade geral de cada tipo.</span><span class="sxs-lookup"><span data-stu-id="f75e6-114">The following table lists the types of category hierarchies that are available and the general purpose of each type.</span></span>

| <span data-ttu-id="f75e6-115">Tipo de hierarquia de categoria</span><span class="sxs-lookup"><span data-stu-id="f75e6-115">Category hierarchy type</span></span>       | <span data-ttu-id="f75e6-116">Finalidade</span><span class="sxs-lookup"><span data-stu-id="f75e6-116">Purpose</span></span> |
|-------------------------------|---------|
| <span data-ttu-id="f75e6-117">Hierarquia de produtos</span><span class="sxs-lookup"><span data-stu-id="f75e6-117">Product hierarchy</span></span>      | <span data-ttu-id="f75e6-118">Use esse tipo da hierarquia para definir a hierarquia de produtos geral da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f75e6-118">Use this hierarchy type to define the overall product hierarchy for your organization.</span></span> <span data-ttu-id="f75e6-119">Você pode usar esse tipo da hierarquia para comercialização, preços e promoções, relatórios e planejamento de classificação.</span><span class="sxs-lookup"><span data-stu-id="f75e6-119">You can use this hierarchy type for merchandising, pricing and promotions, reporting, and assortment planning.</span></span> <span data-ttu-id="f75e6-120">Apenas uma hierarquia de produtos pode ser atribuída esse tipo de hierarquia.</span><span class="sxs-lookup"><span data-stu-id="f75e6-120">Only one product hierarchy can be assigned this hierarchy type.</span></span> |
| <span data-ttu-id="f75e6-121">Hierarquia complementar</span><span class="sxs-lookup"><span data-stu-id="f75e6-121">Supplemental hierarchy</span></span> | <span data-ttu-id="f75e6-122">Use esse tipo de hierarquia para qualquer hierarquia de categoria adicional que você deseja criar.</span><span class="sxs-lookup"><span data-stu-id="f75e6-122">Use this hierarchy type for any additional category hierarchies that you want to create.</span></span> <span data-ttu-id="f75e6-123">Por exemplo, na primavera, você tem uma promoção para moda praia.</span><span class="sxs-lookup"><span data-stu-id="f75e6-123">For example, in the spring, you have a promotion for swimwear.</span></span> <span data-ttu-id="f75e6-124">Portanto, você inclui os produtos de moda praia em uma hierarquia de categoria separada e aplica o preço promocional a várias categorias de produto.</span><span class="sxs-lookup"><span data-stu-id="f75e6-124">Therefore, you include your swimwear products in a separate category hierarchy and apply the promotional pricing to the various product categories.</span></span> |
| <span data-ttu-id="f75e6-125">Hierarquia de navegação</span><span class="sxs-lookup"><span data-stu-id="f75e6-125">Navigation hierarchy</span></span>   | <span data-ttu-id="f75e6-126">Use este tipo da hierarquia para agrupar e organizar produtos em categorias, de forma que seja possível procurar os produtos online ou no PDV.</span><span class="sxs-lookup"><span data-stu-id="f75e6-126">Use this hierarchy type to group and organize products into categories so that the products can be browsed online or in POS.</span></span> |

<span data-ttu-id="f75e6-127">Ao usar uma hierarquia de categoria para estruturar seus produtos, você pode configurar e manter atributos e propriedades de produtos no nível de categoria.</span><span class="sxs-lookup"><span data-stu-id="f75e6-127">By using a category hierarchy to structure your products, you can set up and maintain product attributes and properties at the category level.</span></span> <span data-ttu-id="f75e6-128">Esses atributos e propriedades incluem as configurações para dimensões do produto e do PDV.</span><span class="sxs-lookup"><span data-stu-id="f75e6-128">These attributes and properties include settings for product dimensions and POS settings.</span></span> <span data-ttu-id="f75e6-129">Todos os produtos que você atribui às categorias herdam automaticamente os atributos e as propriedades que você define.</span><span class="sxs-lookup"><span data-stu-id="f75e6-129">Any products that you assign to the categories automatically inherit the attributes and properties that you define.</span></span> <span data-ttu-id="f75e6-130">Você também pode copiar as configurações de propriedade de qualquer produto para vários produtos da categoria selecionada ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="f75e6-130">You can also copy the property settings for any product to multiple products in a selected category at the same time.</span></span>
