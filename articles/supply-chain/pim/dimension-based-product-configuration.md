---
title: Configuração de produto baseada em dimensão
description: A configuração do produto com base na dimensão representa uma solução simples para criação de diversas variantes de produtos de um único produto mestre e sua lista de materiais.
author: cvocph
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConfigRule, BOMTable, ConfigChooseFromRoute, ConfigGroup, ConfigHierarchy, EcoResDimensionBasedConfiguration
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19821
ms.assetid: 4db9890b-306b-4be7-ba98-3be2094d561f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eb2690ec5296f65430268a211108551348a4a060
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1555945"
---
# <a name="dimension-based-product-configuration"></a><span data-ttu-id="addb9-103">Configuração de produto baseada em dimensão</span><span class="sxs-lookup"><span data-stu-id="addb9-103">Dimension-based product configuration</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="addb9-104">A configuração do produto com base na dimensão representa uma solução simples para criação de diversas variantes de produtos de um único produto mestre e sua lista de materiais.</span><span class="sxs-lookup"><span data-stu-id="addb9-104">Dimension-based product configuration represents a simple solution for creating many product variants from a single product master and its bill of materials.</span></span>

<span data-ttu-id="addb9-105">A configuração de produto baseada em dimensão é uma das três tecnologias de configuração de produto internas.</span><span class="sxs-lookup"><span data-stu-id="addb9-105">Dimension-based product configuration is one of the three built-in product configuration technologies.</span></span> <span data-ttu-id="addb9-106">As duas outras tecnologias são variações pré-definidas e configuração baseada em restrições.</span><span class="sxs-lookup"><span data-stu-id="addb9-106">The two other technologies are predefined variants and constraint-based configuration.</span></span> <span data-ttu-id="addb9-107">As três tecnologias usam um produto mestre como ponto de partida e permitem que o usuário crie várias variantes de produto para um produto mestre.</span><span class="sxs-lookup"><span data-stu-id="addb9-107">All three technologies use a product master as the starting point and allow the user to create many product variants for one product master.</span></span>

## <a name="key-concepts"></a><span data-ttu-id="addb9-108">Conceitos principais</span><span class="sxs-lookup"><span data-stu-id="addb9-108">Key concepts</span></span>
<span data-ttu-id="addb9-109">A configuração de produto baseada em dimensão baseia-se nos seguintes conceitos principais:</span><span class="sxs-lookup"><span data-stu-id="addb9-109">Dimension-based product configuration is based on the following key concepts:</span></span>

-   <span data-ttu-id="addb9-110">Produtos mestres</span><span class="sxs-lookup"><span data-stu-id="addb9-110">Product masters</span></span>
-   <span data-ttu-id="addb9-111">Dimensão de configuração do produto</span><span class="sxs-lookup"><span data-stu-id="addb9-111">Configuration product dimension</span></span>
-   <span data-ttu-id="addb9-112">Grupos de configuração</span><span class="sxs-lookup"><span data-stu-id="addb9-112">Configuration groups</span></span>
-   <span data-ttu-id="addb9-113">Lista de materiais (BOM)</span><span class="sxs-lookup"><span data-stu-id="addb9-113">Bill of materials (BOM)</span></span>
-   <span data-ttu-id="addb9-114">Roteiro de configuração</span><span class="sxs-lookup"><span data-stu-id="addb9-114">Configuration route</span></span>
-   <span data-ttu-id="addb9-115">Regras de configuração</span><span class="sxs-lookup"><span data-stu-id="addb9-115">Configuration rules</span></span>

### <a name="product-masters"></a><span data-ttu-id="addb9-116">Produtos mestres</span><span class="sxs-lookup"><span data-stu-id="addb9-116">Product masters</span></span>

<span data-ttu-id="addb9-117">Um produto mestre é o ponto de partida para qualquer processo de configuração de produto.</span><span class="sxs-lookup"><span data-stu-id="addb9-117">A product master is the starting point for any product configuration process.</span></span> <span data-ttu-id="addb9-118">Para a configuração de produto baseada em dimensão, você precisa de um produto mestre com essa tecnologia de configuração específica e um grupo de dimensões de produto que inclui a dimensão de configuração de produto.</span><span class="sxs-lookup"><span data-stu-id="addb9-118">For the dimension-based product configuration, you need a product master with this particular configuration technology and a product dimension group that includes the configuration product dimension.</span></span>

### <a name="configuration-product-dimension"></a><span data-ttu-id="addb9-119">Dimensão de configuração do produto</span><span class="sxs-lookup"><span data-stu-id="addb9-119">Configuration product dimension</span></span>

<span data-ttu-id="addb9-120">A dimensão de produto de configuração é usada para identificar variantes de produtos para um produto mestre com a tecnologia de configuração baseada em dimensão.</span><span class="sxs-lookup"><span data-stu-id="addb9-120">The configuration product dimension is used to identify the product variants for a product master with the dimension-based configuration technology.</span></span> <span data-ttu-id="addb9-121">O valor de dimensão de configuração é inserido pelo usuário e deve ajudar a identificar as variantes de produto individuais.</span><span class="sxs-lookup"><span data-stu-id="addb9-121">The configuration dimension value is entered by the user and should help to identify the individual product variants.</span></span>

### <a name="configuration-groups"></a><span data-ttu-id="addb9-122">Grupos de configuração</span><span class="sxs-lookup"><span data-stu-id="addb9-122">Configuration groups</span></span>

<span data-ttu-id="addb9-123">Os grupos de configuração são definidos em um repositório central e podem ser usados para todos os modelos de configuração de produto baseados em dimensão.</span><span class="sxs-lookup"><span data-stu-id="addb9-123">Configuration groups are defined in a central repository and can be used for all dimension-based product configuration models.</span></span> <span data-ttu-id="addb9-124">Os grupos de configuração são associados às linhas individuais de BOM e compõem um grupo de linhas que são mutuamente exclusivas.</span><span class="sxs-lookup"><span data-stu-id="addb9-124">Configuration groups are associated to the individual BOM lines and hold together a group of lines that are mutually exclusive.</span></span> <span data-ttu-id="addb9-125">Isso significa que apenas uma linha em um grupo pode ser selecionada para uma única variante de produto.</span><span class="sxs-lookup"><span data-stu-id="addb9-125">This means that only one line in a group can be selected for a single product variant.</span></span>

### <a name="bill-of-materials-bom"></a><span data-ttu-id="addb9-126">Lista de materiais (BOM)</span><span class="sxs-lookup"><span data-stu-id="addb9-126">Bill of materials (BOM)</span></span>

<span data-ttu-id="addb9-127">A BOM representa os blocos de construção para uma configuração de produto baseada em dimensão.</span><span class="sxs-lookup"><span data-stu-id="addb9-127">The BOM represent the building blocks for a dimension-based product configuration.</span></span> <span data-ttu-id="addb9-128">Ela deve incluir todos os produtos diferentes que podem ser usados em qualquer variante de produto.</span><span class="sxs-lookup"><span data-stu-id="addb9-128">It must include all the different products that can be used in any product variant.</span></span> <span data-ttu-id="addb9-129">Cada linha na BOM pode fazer referência a um grupo de configuração.</span><span class="sxs-lookup"><span data-stu-id="addb9-129">Each line in the BOM can reference a configuration group.</span></span> <span data-ttu-id="addb9-130">Se uma linha não fizer referência a um grupo de configuração, ela será incluída em todas as variantes de produto.</span><span class="sxs-lookup"><span data-stu-id="addb9-130">If a line doesn’t reference a configuration group, it will be included in all product variants.</span></span>

### <a name="configuration-route"></a><span data-ttu-id="addb9-131">Roteiro de configuração</span><span class="sxs-lookup"><span data-stu-id="addb9-131">Configuration route</span></span>

<span data-ttu-id="addb9-132">O roteiro de configuração determina a sequência dos grupos de configurações, pois serão exibidos ao usuário durante o processo de configuração de produto.</span><span class="sxs-lookup"><span data-stu-id="addb9-132">The configuration route determines the sequence of the configuration groups, as they will be displayed to the user during the product configuration process.</span></span>

### <a name="configuration-rules"></a><span data-ttu-id="addb9-133">Regras de configuração</span><span class="sxs-lookup"><span data-stu-id="addb9-133">Configuration rules</span></span>

<span data-ttu-id="addb9-134">As regras de configuração representam um mecanismo para assegurar que um produto incluído em um grupo de configuração em uma BOM garanta uma inclusão ou uma exclusão de um produto em um grupo de configurações diferentes na mesma BOM.</span><span class="sxs-lookup"><span data-stu-id="addb9-134">The configuration rules represent a mechanism for ensuring that a product included in one configuration group in a BOM enforces either an inclusion or an exclusion of a product in a different configuration group in the same BOM.</span></span>

## <a name="product-modeling-process"></a><span data-ttu-id="addb9-135">Processo de modelagem do produto</span><span class="sxs-lookup"><span data-stu-id="addb9-135">Product modeling process</span></span>
<span data-ttu-id="addb9-136">A sequência natural para compilar um modelo de produto para um produto baseado em dimensão começa com a definição dos grupos de configuração relevantes.</span><span class="sxs-lookup"><span data-stu-id="addb9-136">The natural sequence for building a product model for a dimension-based product starts with defining the relevant configuration groups.</span></span> <span data-ttu-id="addb9-137">É importante garantir que todos os produtos que serão usados na BOM tenham sido liberados para a empresa para a qual o modelo de produto foi criado.</span><span class="sxs-lookup"><span data-stu-id="addb9-137">It is important to ensure that all products which will be used in the BOM have been released to the company that the product model is built for.</span></span> <span data-ttu-id="addb9-138">Com esses blocos de construção em vigor, o usuário poderá criar a BOM e atribuir grupos de configuração a todas as linhas relevantes da BOM.</span><span class="sxs-lookup"><span data-stu-id="addb9-138">With these building blocks in place, the user can create the BOM and assign configuration groups to all relevant BOM lines.</span></span> <span data-ttu-id="addb9-139">Quando a BOM estiver concluída, um roteiro de configuração poderá ser definido para o pedido de grupos de configuração na sequência apropriada.</span><span class="sxs-lookup"><span data-stu-id="addb9-139">When the BOM is complete, a configuration route can be defined for ordering the configuration groups in the proper sequence.</span></span> <span data-ttu-id="addb9-140">[![Processo de modelagem de produto baseado em dimensão](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) Se houver alguns produtos de grupos de configuração diferentes que devem ou não ser usados junto, você poderá criar regras de configuração que aplicam esses relacionamentos de produto.</span><span class="sxs-lookup"><span data-stu-id="addb9-140">[![Dimension-based product modeling process](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) If there are certain products from different configuration groups that either must or must not be used together, you can create configuration rules that will enforce these product relationships.</span></span> <span data-ttu-id="addb9-141">Após a BOM ser vinculada a um produto mestre baseado em dimensão por meio de uma versão da BOM e ambos serem aprovados e ativados, será possível criar configurações de produto e inserir um nome para cada configuração.</span><span class="sxs-lookup"><span data-stu-id="addb9-141">After the BOM has been tied together with a dimension-based product master through a BOM version and both have been approved and activated, you can create product configurations and enter a name for each configuration.</span></span> <span data-ttu-id="addb9-142">As configurações podem ser definidas antes que qualquer transação seja gerada ou possa ser feita quando houver necessidade de uma determinada configuração.</span><span class="sxs-lookup"><span data-stu-id="addb9-142">The configurations can be defined before any transactions are generated or it can be done when the need for a certain configuration occurs.</span></span>

### <a name="suggested-use"></a><span data-ttu-id="addb9-143">Uso sugerido</span><span class="sxs-lookup"><span data-stu-id="addb9-143">Suggested use</span></span>

<span data-ttu-id="addb9-144">A tecnologia de configuração baseada em dimensão é melhor usada para produtos com variabilidade limitada e a combinação de estilo, cor, tamanho e configuração das dimensões do produto não for adequada para identificar uma variante de produto específica.</span><span class="sxs-lookup"><span data-stu-id="addb9-144">The dimension-based configuration technology is best used for products with limited variability and the combination of the standard product dimensions size, color, style, and configuration is unsuitable for identifying a specific product variant.</span></span> <span data-ttu-id="addb9-145">Um exemplo poderia ser uma bicicleta com altura de quadro, tamanho de roda, tipos de freio, e embreagem diferente.</span><span class="sxs-lookup"><span data-stu-id="addb9-145">An example could be bicycle with frame height, wheel size, brake types, and different gears.</span></span>

### <a name="next-step"></a><span data-ttu-id="addb9-146">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="addb9-146">Next step</span></span> 

<span data-ttu-id="addb9-147">As seguintes oito guias de tarefa são listadas na ordem em que devem ser concluídas.</span><span class="sxs-lookup"><span data-stu-id="addb9-147">The following eight task guides are listed in the order in which you should complete them.</span></span> 

1.  [<span data-ttu-id="addb9-148">Criar um produto mestre baseado em dimensão (Guia de tarefas)</span><span class="sxs-lookup"><span data-stu-id="addb9-148">Create a dimension-based product master (Task guide)</span></span>](tasks/create-dimension-based-product-master.md)
2.  [<span data-ttu-id="addb9-149">Lançar um produto mestre baseado em dimensão (Guia de tarefas)</span><span class="sxs-lookup"><span data-stu-id="addb9-149">Release a dimension-based product master (Task guide)</span></span>](tasks/release-dimension-based-product-master.md)
3.  [<span data-ttu-id="addb9-150">Concluir a configuração básica de um produto mestre lançado (Guia de tarefas)</span><span class="sxs-lookup"><span data-stu-id="addb9-150">Complete basic setup of a released product master (Task guide)</span></span>](tasks/complete-basic-setup-released-product-master.md)
4.  [<span data-ttu-id="addb9-151">Definir grupos de configuração (Guia de tarefas)</span><span class="sxs-lookup"><span data-stu-id="addb9-151">Define configuration groups (Task guide)</span></span>](tasks/define-configuration-groups.md)
5.  [<span data-ttu-id="addb9-152">Criar uma lista de materiais para um produto mestre baseado em dimensão (Guia de tarefas)</span><span class="sxs-lookup"><span data-stu-id="addb9-152">Create a bill of materials for a dimension-based product master (Task guide)</span></span>](tasks/create-bill-materials-dimension-based-product-master.md)
6.  [<span data-ttu-id="addb9-153">Definir roteiros de configuração (Guia de tarefas)</span><span class="sxs-lookup"><span data-stu-id="addb9-153">Define configuration routes (Task guide)</span></span>](tasks/define-configuration-route.md)
7.  [<span data-ttu-id="addb9-154">Criar regras de configuração (Guia de tarefas)</span><span class="sxs-lookup"><span data-stu-id="addb9-154">Create configuration rules (Task guide)</span></span>](tasks/create-configuration-rules.md)
8.  [<span data-ttu-id="addb9-155">Criar configurações baseadas em dimensão (Guia de tarefas)</span><span class="sxs-lookup"><span data-stu-id="addb9-155">Create dimension-based configurations (Task guide)</span></span>](tasks/create-dimension-based-configurations.md)

