---
title: Personalizar a navegação do site
description: Este tópico descreve como criar uma hierarquia online personalizada de navegação para organizar seus produtos para procurar no site do Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c2b6a7a3b35873e80be391c627d0397fd6398a99
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410174"
---
# <a name="customize-site-navigation"></a><span data-ttu-id="23b20-103">Personalizar a navegação do site</span><span class="sxs-lookup"><span data-stu-id="23b20-103">Customize site navigation</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="23b20-104">Este tópico descreve como criar uma hierarquia online personalizada de navegação para organizar seus produtos para procurar no site do Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="23b20-104">This topic describes how to create a customized online navigation hierarchy to organize your products for browsing on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="23b20-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="23b20-105">Overview</span></span>

<span data-ttu-id="23b20-106">As lojas online normalmente permitem que os clientes descubram e naveguem entre produtos por meio de categorias de produto.</span><span class="sxs-lookup"><span data-stu-id="23b20-106">Online storefronts typically let customers discover and browse products by navigating through product categories.</span></span> <span data-ttu-id="23b20-107">Este recurso é normalmente fornecido por guias na parte superior da página ou na barra de navegação à esquerda.</span><span class="sxs-lookup"><span data-stu-id="23b20-107">This capability is usually provided by tabs at the top of the page or by a navigation bar on the left.</span></span> <span data-ttu-id="23b20-108">No Dynamics 365 Commerce, você pode criar e gerenciar uma estrutura hierárquica de navegação da categoria e os produtos que estão incluídos nas várias categorias.</span><span class="sxs-lookup"><span data-stu-id="23b20-108">In Dynamics 365 Commerce, you can create and manage the hierarchal structure of your category navigation and the products that are included in the various categories.</span></span>

## <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="23b20-109">Criar uma hierarquia de navegação de canal</span><span class="sxs-lookup"><span data-stu-id="23b20-109">Create a channel navigation hierarchy</span></span>

<span data-ttu-id="23b20-110">Para criar uma hierarquia de navegação de canal, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="23b20-110">To create a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="23b20-111">Vá para **Varejo e Comércio \> Produtos e categorias \> Gerenciamento de categorias e produtos**.</span><span class="sxs-lookup"><span data-stu-id="23b20-111">Go to **Retail and Commerce \> Products and categories \> Category and product management**.</span></span>
1. <span data-ttu-id="23b20-112">Selecione **Hierarquias de categoria** e depois **Novo**.</span><span class="sxs-lookup"><span data-stu-id="23b20-112">Select **Category hierarchies**, and then select **New**.</span></span>
1. <span data-ttu-id="23b20-113">Nomeie a hierarquia.</span><span class="sxs-lookup"><span data-stu-id="23b20-113">Name the hierarchy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="23b20-114">A categoria mais alta que você cria é o nó de categoria raiz.</span><span class="sxs-lookup"><span data-stu-id="23b20-114">The topmost category that you create is the root category node.</span></span> <span data-ttu-id="23b20-115">Não será exibido no site.</span><span class="sxs-lookup"><span data-stu-id="23b20-115">It won't be shown on your site.</span></span> <span data-ttu-id="23b20-116">Para criar uma hierarquia de categoria onde um único nó superior é mostrada no site, crie e nomeie a categoria como filho da categoria raiz.</span><span class="sxs-lookup"><span data-stu-id="23b20-116">To create a category hierarchy where a single top-level node is shown on your site, create and name the category as a child of the root category.</span></span>

1. <span data-ttu-id="23b20-117">Selecione **Novo nó da categoria**, e o nome da categoria.</span><span class="sxs-lookup"><span data-stu-id="23b20-117">Select **New category node**, and name the category.</span></span>
1. <span data-ttu-id="23b20-118">Continue ao criar categorias irmão e filho como necessário.</span><span class="sxs-lookup"><span data-stu-id="23b20-118">Continue to create sibling and child categories as you require.</span></span>

<span data-ttu-id="23b20-119">Agora você pode atribuir produtos a cada categoria criada na categoria de nível superior.</span><span class="sxs-lookup"><span data-stu-id="23b20-119">You can now assign products to each category that you created under the top-level category.</span></span>

## <a name="customize-the-order-of-categories"></a><span data-ttu-id="23b20-120">Personalizar a ordem de categorias</span><span class="sxs-lookup"><span data-stu-id="23b20-120">Customize the order of categories</span></span>

<span data-ttu-id="23b20-121">Por padrão, as categorias que você define em ordem alfabética aparecerão no site.</span><span class="sxs-lookup"><span data-stu-id="23b20-121">By default, the categories that you define will appear in alphabetical order on your site.</span></span> <span data-ttu-id="23b20-122">Entretanto, é possível personalizar a ordem de exibição de categorias.</span><span class="sxs-lookup"><span data-stu-id="23b20-122">However, you can also customize the display order of categories.</span></span>

## <a name="assign-a-category-hierarchy-type"></a><span data-ttu-id="23b20-123">Atribuir um tipo de hierarquia de categoria</span><span class="sxs-lookup"><span data-stu-id="23b20-123">Assign a category hierarchy type</span></span>

1. <span data-ttu-id="23b20-124">Vá para **Varejo e Comércio \> Produtos e categorias \> Gerenciamento de categorias e produtos**.</span><span class="sxs-lookup"><span data-stu-id="23b20-124">Go to **Retail and Commerce \> Products and categories \> Category and product management**.</span></span>
1. <span data-ttu-id="23b20-125">Selecione **Hierarquias de categoria**.</span><span class="sxs-lookup"><span data-stu-id="23b20-125">Select **Category hierarchies**.</span></span>
1. <span data-ttu-id="23b20-126">No Painel de Ação, na guia **Hierarquias de categoria**, no grupo **Configurar**, selecione **Associar tipo de hierarquia**.</span><span class="sxs-lookup"><span data-stu-id="23b20-126">On the Action Pane, on the **Category hierarchy** tab, in the **Set up** group, select **Associate hierarchy type**.</span></span>
1. <span data-ttu-id="23b20-127">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="23b20-127">Select **New**.</span></span>
1. <span data-ttu-id="23b20-128">No campo **Tipo de hierarquia de categoria**, selecione **Hierarquia de navegação de canal**.</span><span class="sxs-lookup"><span data-stu-id="23b20-128">In the **Category hierarchy type** field, select **Channel navigation hierarchy**.</span></span>
1. <span data-ttu-id="23b20-129">No campo **Hierarquia de categoria**, selecione a hierarquia de navegação de canal criadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="23b20-129">In the **Category hierarchy** field, select the channel navigation hierarchy that you created earlier.</span></span>

## <a name="publish-new-or-updated-navigation-hierarchies"></a><span data-ttu-id="23b20-130">Publicar hierarquias de navegação novas ou atualizadas</span><span class="sxs-lookup"><span data-stu-id="23b20-130">Publish new or updated navigation hierarchies</span></span>

<span data-ttu-id="23b20-131">Para tornar sua hierarquia de navegação disponível na loja online, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="23b20-131">To make your navigation hierarchy available to your online storefront, follow these steps.</span></span>

1. <span data-ttu-id="23b20-132">Vá para **Varejo e Comércio \> Configuração de canal \> Categorias do canal e atributos de produto**.</span><span class="sxs-lookup"><span data-stu-id="23b20-132">Go to **Retail and Commerce \> Channel setup \> Channel categories and product attributes**.</span></span>
1. <span data-ttu-id="23b20-133">Na árvore a esquerda, selecione seu armazenamento online.</span><span class="sxs-lookup"><span data-stu-id="23b20-133">In the tree on the left, select your online store.</span></span>
1. <span data-ttu-id="23b20-134">Selecione **Publicar atualizações de canal**.</span><span class="sxs-lookup"><span data-stu-id="23b20-134">Select **Publish channel updates**.</span></span>
1. <span data-ttu-id="23b20-135">Vá para **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**.</span><span class="sxs-lookup"><span data-stu-id="23b20-135">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="23b20-136">Na lista, localize e selecione **Trabalho 1040**.</span><span class="sxs-lookup"><span data-stu-id="23b20-136">In the list, find and select **Job 1040**.</span></span>
1. <span data-ttu-id="23b20-137">Selecione **Executar agora**.</span><span class="sxs-lookup"><span data-stu-id="23b20-137">Select **Run now**.</span></span>
1. <span data-ttu-id="23b20-138">Repita as etapas 5 e 6 para a trabalhos 1070 e 1150.</span><span class="sxs-lookup"><span data-stu-id="23b20-138">Repeat steps 5 and 6 for jobs 1070 and 1150.</span></span>

## <a name="show-categories-on-your-site"></a><span data-ttu-id="23b20-139">Exibir categorias no site</span><span class="sxs-lookup"><span data-stu-id="23b20-139">Show categories on your site</span></span>

<span data-ttu-id="23b20-140">Para exibir sua hierarquia de categoria na loja online, você deve adicionar o módulo do menu de navegação no local apropriado em um modelo ou fragmento.</span><span class="sxs-lookup"><span data-stu-id="23b20-140">To show your category hierarchy on your online storefront, you must add the navigation menu module in the appropriate location in a template or fragment.</span></span> <span data-ttu-id="23b20-141">O módulo de menu de navegação mostrará a hierarquia de navegação, desde que você a tenha publicado no canal ao qual o site está associado.</span><span class="sxs-lookup"><span data-stu-id="23b20-141">The navigation menu module will then show your navigation hierarchy, provided that you've published your navigation hierarchy to the channel that your site is bound to.</span></span>

> [!NOTE]
> <span data-ttu-id="23b20-142">O módulo de menu de navegação incluído na biblioteca de módulos permite que os usuários naveguem somente até categorias que não tenham subcategorias.</span><span class="sxs-lookup"><span data-stu-id="23b20-142">The navigation menu module that is included in the module library lets users navigate only to categories that don't have subcategories.</span></span> <span data-ttu-id="23b20-143">Se seus clientes podem navegar em categorias que têm subcategorias, você deve personalizar o módulo de menu de navegação.</span><span class="sxs-lookup"><span data-stu-id="23b20-143">If your customers should be able to navigate to categories that have subcategories, you must customize the navigation menu module.</span></span>

## <a name="add-custom-navigation-options"></a><span data-ttu-id="23b20-144">Adicionar opções de navegação personalizadas</span><span class="sxs-lookup"><span data-stu-id="23b20-144">Add custom navigation options</span></span>

<span data-ttu-id="23b20-145">No menu de navegação, você pode adicionar opções de navegação que não fazem parte da hierarquia da categoria de produto.</span><span class="sxs-lookup"><span data-stu-id="23b20-145">On your navigation menu, you can add navigation options that aren't part of your product category hierarchy.</span></span> <span data-ttu-id="23b20-146">Por exemplo, no final da lista de categorias de produtos, você pode adicionar um item **Fale conosco** que aponta para uma página de contato criada para o site.</span><span class="sxs-lookup"><span data-stu-id="23b20-146">For example, at the end of the list of product categories, you can add a **Contact Us** item that points to a contact page that you've built for your site.</span></span>

<span data-ttu-id="23b20-147">Para adicionar opções personalizados de navegação no menu de navegação, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="23b20-147">To add custom navigation options to your navigation menu, follow these steps.</span></span>

1. <span data-ttu-id="23b20-148">No modelo ou fragmento que deseja personalizar, selecione o módulo de menu de navegação.</span><span class="sxs-lookup"><span data-stu-id="23b20-148">In the template or fragment that you want to customize, select the navigation menu module.</span></span>
1. <span data-ttu-id="23b20-149">No painel de propriedade, na guia **Dados**, selecione **Adicionar item** para criar um novo item de conteúdo de navegação (CMS) do sistema de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="23b20-149">In the property pane, on the **Data** tab, select **Add item** to create a new content management system (CMS) navigation item.</span></span>
1. <span data-ttu-id="23b20-150">Insira o texto do link e uma URL.</span><span class="sxs-lookup"><span data-stu-id="23b20-150">Enter link text and a URL.</span></span>
1. <span data-ttu-id="23b20-151">Repita as etapas 2 e 3 para adicionar mais uma opções personalizadas de navegação.</span><span class="sxs-lookup"><span data-stu-id="23b20-151">Repeat steps 2 and 3 to add more custom navigation options.</span></span>
1. <span data-ttu-id="23b20-152">Quando terminar, selecione **Salvar** para salvar o modelo ou o fragmento e, em seguida, selecione **Concluir a edição** para fazer o respectivo check-in.</span><span class="sxs-lookup"><span data-stu-id="23b20-152">When you've finished, select **Save** to save the template or fragment, and then select **Finish editing** to check it in.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="23b20-153">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="23b20-153">Additional resources</span></span>

[<span data-ttu-id="23b20-154">Visão geral de modelos e layouts</span><span class="sxs-lookup"><span data-stu-id="23b20-154">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="23b20-155">Trabalhar com modelos</span><span class="sxs-lookup"><span data-stu-id="23b20-155">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="23b20-156">Trabalhar com layouts predefinidos</span><span class="sxs-lookup"><span data-stu-id="23b20-156">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="23b20-157">Trabalhar com fragmentos</span><span class="sxs-lookup"><span data-stu-id="23b20-157">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="23b20-158">Trabalhar com módulos</span><span class="sxs-lookup"><span data-stu-id="23b20-158">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="23b20-159">Criar uma URL da página</span><span class="sxs-lookup"><span data-stu-id="23b20-159">Create a page URL</span></span>](create-page-url.md)

[<span data-ttu-id="23b20-160">Trabalhar com grupos de publicações</span><span class="sxs-lookup"><span data-stu-id="23b20-160">Work with publish groups</span></span>](publish-groups.md)
