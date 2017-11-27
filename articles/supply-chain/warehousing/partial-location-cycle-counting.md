---
title: "Contagem cíclica parcial do local"
description: "Os planos de contagem cíclica guiam as operações reais de contagem. Você pode solicitar que somente produtos e grades de produtos específicos sejam contados em vez de todo o estoque disponível no local."
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSCycleCountPlan, WHSWorkLineCycleCount, WHSWorkTemplateLineGroup, WHSWorkTemplateTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 0e0f9d81f4d5943a89d8ac87776e05acb32cb8d9
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="partial-location-cycle-counting"></a><span data-ttu-id="b7cb8-104">Contagem cíclica parcial do local</span><span class="sxs-lookup"><span data-stu-id="b7cb8-104">Partial location cycle counting</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="b7cb8-105">Os planos de contagem cíclica guiam as operações reais de contagem.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-105">Cycle count plans guide the actual counting operations.</span></span> <span data-ttu-id="b7cb8-106">Você pode solicitar que somente produtos e grades de produtos específicos sejam contados em vez de todo o estoque disponível no local.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-106">You can request that only specific products and product variants be counted instead of all on-hand inventory in a location.</span></span>

<span data-ttu-id="b7cb8-107">Ao usar os planos de contagem cíclica para criar o trabalho de contagem, você pode guiar as operações reais de contagem.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-107">By using cycle count plans to create counting work, you can guide the actual counting operations.</span></span> <span data-ttu-id="b7cb8-108">Você pode solicitar que somente produtos e grades de produtos específicos sejam contados em vez de todo o estoque disponível no local.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-108">You can request that only specific products and product variants be counted instead of all on-hand inventory in a location.</span></span> <span data-ttu-id="b7cb8-109">Ao filtrar produtos específicos, o gerente do depósito pode reduzir custos indiretos de revisão, evitar erros de consolidação e economizar tempo.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-109">By filtering on specific products, the warehouse manager can reduce review overhead, avoid consolidation mistakes, and save time.</span></span>

## <a name="how-to-configure-partial-location-cycle-counting"></a><span data-ttu-id="b7cb8-110">Como configurar a contagem cíclica parcial do local</span><span class="sxs-lookup"><span data-stu-id="b7cb8-110">How to configure partial location cycle counting</span></span>
<span data-ttu-id="b7cb8-111">Quando você usa o processo de trabalho do depósito para operações de contagem, um cabeçalho de trabalho é criado para cada local.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-111">When you use the warehouse work process for counting operations, a work header is created for each location.</span></span> <span data-ttu-id="b7cb8-112">Quando você define o plano de contagem cíclica, você pode usar a consulta **Selecionar localizações** para limitar o trabalho de contagem cíclica criado.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-112">When you define the cycle count plan, you can use the **Select locations** query to limit the cycle counting work that is created.</span></span> <span data-ttu-id="b7cb8-113">Ao selecionar produtos para o plano de contagem cíclica, você pode selecionar consultas de produto e de grade de produto para refinar o que é contado.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-113">When you select products for the cycle count plan, you can select both product and product variant queries to refine what is counted.</span></span> 

<span data-ttu-id="b7cb8-114">Você pode associar um **modelo de trabalho** a um plano de contagem cíclica para definir como o trabalho de contagem cíclica deve ser criado.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-114">You can associate a **work template** with a cycle count plan to define how the cycle count work should be created.</span></span> <span data-ttu-id="b7cb8-115">O modelo de trabalho para as operações de contagem refere-se diretamente ao plano de contagem cíclica.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-115">The work template for counting operations is directly referenced from the cycle count plan.</span></span> 

<span data-ttu-id="b7cb8-116">Ao definir os detalhes do modelo de trabalho, você pode usar a opção **Divisões de linha de trabalho** para especificar se as linhas de trabalho de contagem devem ser agrupadas por número de item ou por número de grade de produto.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-116">When you define the work template details, you can use the **Work line breaks** option to specify whether the counting work lines must be grouped by item number or product variant number.</span></span> <span data-ttu-id="b7cb8-117">Esta configuração é necessária se você deseja contar o estoque disponível apenas para produtos específicos em um local.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-117">This setup is required if you want to count on-hand inventory only for specific products in a location.</span></span> <span data-ttu-id="b7cb8-118">As linhas de trabalho de contagem cíclica criadas terão o nível de informação que você define aqui, e a operação de contagem guiada será tratada com base nesse nível.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-118">The cycle counting work lines that are created will have the level of information that you define here, and the guided counting operation will be handled based on this level.</span></span> 

<span data-ttu-id="b7cb8-119">Se você associar planos de contagem cíclica a modelos de trabalho usando a opção **Divisões de linha de trabalho**, o campo **Contagem cíclica parcial** é selecionado para o trabalho de contagem cíclica criado, e várias linhas de trabalho de contagem cíclica serão criadas com base na definição do modelo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-119">If you associate cycle count plans with work templates by using the **Work lines breaks** option, the **Partial cycle count** field is selected for the cycle counting work that is created, and multiple cycle counting work lines will be created based on the definition of the work template.</span></span> 

<span data-ttu-id="b7cb8-120">Antes do trabalho de contagem cíclica parcial poder ser processado, você deve, no mínimo, selecionar **Exibir número do item** para o item de menu do dispositivo móvel como parte da configuração de contagem cíclica.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-120">Before partial cycle count work can be processed, you must, at a minimum, select **Display item number** for the mobile device menu item as part of the cycle counting setup.</span></span> <span data-ttu-id="b7cb8-121">Será solicitado ao operador de depósito que registre somente informações de contagem relacionadas às linhas de contagem (números de item e dimensões do produto).</span><span class="sxs-lookup"><span data-stu-id="b7cb8-121">The warehouse operator will be asked to record only counting information that is related to the counting lines (item numbers and product dimensions).</span></span> <span data-ttu-id="b7cb8-122">Qualquer outro estoque disponível será ignorado para esse processo de contagem.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-122">All other on-hand inventory will be ignored for this counting process.</span></span> 

<span data-ttu-id="b7cb8-123">Referente ao processo de contagem cíclica parcial, a data/hora **Última contagem cíclica** não será atualizada para a localização.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-123">For the partial cycle count process, the **Last cycle count** date/time won’t be updated for the location.</span></span>

## <a name="example"></a><span data-ttu-id="b7cb8-124">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b7cb8-124">Example</span></span>
<span data-ttu-id="b7cb8-125">Por exemplo, somente o item número A0001 deve ser contado no depósito 61.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-125">For this example, only item number A0001 must be counted in warehouse 61.</span></span>

1.  <span data-ttu-id="b7cb8-126">Um novo modelo de trabalho para contagem cíclica é criado.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-126">A new work template for cycle counting is created.</span></span> <span data-ttu-id="b7cb8-127">A opção **Divisões de linha de trabalho** é usada para agrupar linhas de trabalho de contagem por número de item.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-127">The **Work line breaks** option is used to group counting work lines by item number.</span></span> <span data-ttu-id="b7cb8-128">Portanto, o trabalho de contagem cíclica criado terá linhas por número de item.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-128">Therefore, the cycle counting work that is created will have lines per item number.</span></span> <span data-ttu-id="b7cb8-129">Você também pode agrupar as linhas por número de grade de produto.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-129">You can also group the lines by product variant number.</span></span>
2.  <span data-ttu-id="b7cb8-130">É criado um novo plano de contagem cíclica que faz referência ao modelo de trabalho recém-criado.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-130">A new cycle counting plan is created that references the newly created work template.</span></span> <span data-ttu-id="b7cb8-131">O plano da contagem cíclica inclui todas as localizações no depósito 61 (consulta **Selecionar localizações**) que mantém o inventário para o item número A0001.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-131">The cycle counting plan includes all locations in warehouse 61 (**Select locations** query) that hold inventory for item number A0001.</span></span> <span data-ttu-id="b7cb8-132">A seleção de produtos específicos é definida na seção **Seleções de produtos de contagem cíclica**.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-132">The selection of specific products is defined in the **Cycle count product selections** section.</span></span>
3.  <span data-ttu-id="b7cb8-133">Você pode selecionar produtos para planos de contagem cíclica definindo o campo **Locais vazios** como **Excluir vazios**.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-133">You can select products for cycle counting plans by setting the **Empty locations** field to **Exclude empty**.</span></span> <span data-ttu-id="b7cb8-134">Quando o plano da contagem cíclica é processado, o trabalho de contagem cíclica parcial para o número de item A0001 é criado.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-134">When the cycle counting plan is processed, partial cycle count work for item number A0001 is created.</span></span> <span data-ttu-id="b7cb8-135">O processo de contagem real pode ser realizado usando um item de menu de dispositivo móvel para a contagem cíclica guiada.</span><span class="sxs-lookup"><span data-stu-id="b7cb8-135">The actual counting process can be performed by using a mobile device menu item for guided cycle counting.</span></span>



<a name="see-also"></a><span data-ttu-id="b7cb8-136">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b7cb8-136">See also</span></span>
--------

[<span data-ttu-id="b7cb8-137">Contagem cíclica</span><span class="sxs-lookup"><span data-stu-id="b7cb8-137">Cycle counting</span></span>](cycle-counting.md)


