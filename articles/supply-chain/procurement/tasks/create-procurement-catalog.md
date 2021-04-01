---
title: Criar um catálogo de compras
description: Este tópico explica como criar um catálogo de compras.
author: RichardLuan
manager: tfehr
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProcCategoryHierarchyManagement, CatProcureCatalogListPage, CatProcureCatalogCreate, CatProcureCatalogEdit, SysPolicyListPage, SysPolicy, CatCatalogPolicyRule, PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqAddItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 91c377b2d155fb7b53ef9a15fa9d6e80cd69ed44
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5237242"
---
# <a name="create-a-procurement-catalog"></a><span data-ttu-id="06907-103">Criar um catálogo de compras</span><span class="sxs-lookup"><span data-stu-id="06907-103">Create a procurement catalog</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="06907-104">Este tópico explica como criar um catálogo de compras.</span><span class="sxs-lookup"><span data-stu-id="06907-104">This topic explains how to create a procurement catalog.</span></span> <span data-ttu-id="06907-105">Essa tarefa é tipicamente realizada por um profissional de aquisição.</span><span class="sxs-lookup"><span data-stu-id="06907-105">This task would typically be carried out by a procurement professional.</span></span> <span data-ttu-id="06907-106">Você também aprenderá como os empregados podem usar o catálogo quando criam uma requisição.</span><span class="sxs-lookup"><span data-stu-id="06907-106">You will also learn how employees can use the catalog when they create a requisition.</span></span> <span data-ttu-id="06907-107">Antes de criar um catálogo, deve haver uma hierarquia da categoria da obtenção em seu sistema.</span><span class="sxs-lookup"><span data-stu-id="06907-107">Before you can create a catalog, there must be a procurement category hierarchy in your system.</span></span> <span data-ttu-id="06907-108">A hierarquia é herdada pelo catálogo novo, junto com todos os produtos que estão na hierarquia.</span><span class="sxs-lookup"><span data-stu-id="06907-108">The hierarchy is inherited by the new catalog, along with all the products that are in the hierarchy.</span></span> <span data-ttu-id="06907-109">Você pode usar este guia na empresa USMF dos dados do programa demonstrativo onde a hierarquia da categoria da obtenção está disponível, assim como os exemplos usados nas etapas de procedimento.</span><span class="sxs-lookup"><span data-stu-id="06907-109">You can use this guide in demo data company USMF where the procurement category hierarchy is available, as well as the examples used in the procedure steps.</span></span>


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a><span data-ttu-id="06907-110">Assegure-se de que uma hierarquia da categoria da obtenção exista</span><span class="sxs-lookup"><span data-stu-id="06907-110">Ensure that a procurement category hierarchy exists</span></span>
1. <span data-ttu-id="06907-111">Vá para **Painel de navegação > Módulos > Compras e fornecimento > Categorias de compras**.</span><span class="sxs-lookup"><span data-stu-id="06907-111">Go to **navigation pane > Modules > Procurement and sourcing > Procurement categories**.</span></span> <span data-ttu-id="06907-112">Uma hierarquia de categorias de compras está disponível na empresa de dados de demonstração de USMF e os produtos foram adicionados às **máquinas de escritório/categoria dos computadores**.</span><span class="sxs-lookup"><span data-stu-id="06907-112">A procurement category hierarchy is available in the USMF demo data company and products have been added to the **Office machines/Computers** category.</span></span> <span data-ttu-id="06907-113">Se você estiver executando este procedimento como um guia de tarefa você precisará desbloquear o guia se quiser pesquisar entre a categoria.</span><span class="sxs-lookup"><span data-stu-id="06907-113">If you're running this procedure as a task guide, you'll need to unlock the guide if you want to browse through the category.</span></span> <span data-ttu-id="06907-114">Se uma hierarquia não estava disponível, você a criaria clicando em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="06907-114">If a hierarchy was not available, you'd create it by clicking **New**.</span></span> <span data-ttu-id="06907-115">Isso só pode ser feito uma vez.</span><span class="sxs-lookup"><span data-stu-id="06907-115">This can only be done once.</span></span>  
2. <span data-ttu-id="06907-116">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="06907-116">Close the page.</span></span>

## <a name="create-a-catalog"></a><span data-ttu-id="06907-117">Criar um catálogo</span><span class="sxs-lookup"><span data-stu-id="06907-117">Create a catalog</span></span>
1. <span data-ttu-id="06907-118">Vá para **Painel de navegação > Módulos > Compras e fornecimento > Catálogos > Catálogos de compras**.</span><span class="sxs-lookup"><span data-stu-id="06907-118">Go to **navigation pane > Modules > Procurement and sourcing > Catalogs > Procurement catalogs**.</span></span>
2. <span data-ttu-id="06907-119">Selecione **Novo catálogo de compras** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="06907-119">Select **New procurement catalog** to open the drop dialog.</span></span>
3. <span data-ttu-id="06907-120">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="06907-120">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="06907-121">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="06907-121">Select **OK**.</span></span>
5. <span data-ttu-id="06907-122">Na árvore, expanda **CATEGORIAS DE AQUISIÇÃO CORPORATIVA**.</span><span class="sxs-lookup"><span data-stu-id="06907-122">In the tree, expand **CORP PROCUREMENT CATEGORIES**.</span></span>
6. <span data-ttu-id="06907-123">Na árvore, expanda **MÁQUINAS DE ESCRITÓRIO**.</span><span class="sxs-lookup"><span data-stu-id="06907-123">In the tree, expand **OFFICE MACHINES**.</span></span>
7. <span data-ttu-id="06907-124">Na árvore, selecione **Computadores**.</span><span class="sxs-lookup"><span data-stu-id="06907-124">In the tree, select **Computers**.</span></span>

  - <span data-ttu-id="06907-125">Os produtos da categoria da obtenção são indicados na lista.</span><span class="sxs-lookup"><span data-stu-id="06907-125">The products from the procurement category are displayed in the list.</span></span> <span data-ttu-id="06907-126">Se quiser adicionar um produto à categoria, faça isso na página **Hierarquia de categorias de compras** ou na página **Detalhes do item**.</span><span class="sxs-lookup"><span data-stu-id="06907-126">If you want to add a product to the category you need to do this on the **Procurement category hierarchy** page or on the **Item details** page.</span></span>  
  - <span data-ttu-id="06907-127">O tipo de atualização **Padrão** determina se os produtos novos que foram adicionados à hierarquia de categorias de compras são imediatamente visíveis no catálogo.</span><span class="sxs-lookup"><span data-stu-id="06907-127">The **Default** update type determines whether new products that have been added to the procurement category hierarchy are immediately visible in the catalog.</span></span> <span data-ttu-id="06907-128">Se o tipo de atualização for definido como **Dinâmico**, as mudanças ficarão logo visíveis.</span><span class="sxs-lookup"><span data-stu-id="06907-128">If the update type is set to **Dynamic**, changes are visible immediately.</span></span> <span data-ttu-id="06907-129">Se o tipo de atualização for **Estático**, os produtos novos são somente visíveis às pessoas que usam o catálogo depois que o catálogo foi publicado novamente.</span><span class="sxs-lookup"><span data-stu-id="06907-129">If the update type is **Static**, new products are only visible to people using the catalog after the catalog has been re-published.</span></span> <span data-ttu-id="06907-130">A ação **Publicar** está disponível no Painel de Ação na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="06907-130">The **Publish** action is available on the Action Pane at the top of the page.</span></span> <span data-ttu-id="06907-131">Se os produtos forem removidos da hierarquia de categorias de compras, a mudança ficará logo visível, independentemente do valor no campo de tipo de atualização **Padrão**.</span><span class="sxs-lookup"><span data-stu-id="06907-131">If products are removed from the procurement category hierarchy, the change is immediately visible, regardless of the value in the **Default** update type field.</span></span>  

8. <span data-ttu-id="06907-132">No Painel de Ação, selecione **Navegação de categoria** e certifique-se de que **Habilitar** esteja selecionado.</span><span class="sxs-lookup"><span data-stu-id="06907-132">On the Action Pane, select **Category navigation** and ensure that **Enable** is selected.</span></span>
9. <span data-ttu-id="06907-133">Selecione **Ativar catálogo**.</span><span class="sxs-lookup"><span data-stu-id="06907-133">Select **Activate catalog**.</span></span>
10. <span data-ttu-id="06907-134">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="06907-134">Close the page.</span></span>

## <a name="make-the-catalog-visible"></a><span data-ttu-id="06907-135">Tornar o catálogo visível</span><span class="sxs-lookup"><span data-stu-id="06907-135">Make the catalog visible</span></span>
1. <span data-ttu-id="06907-136">Vá para **Painel de navegação > Módulos > Compras e fornecimento > Configuração > Políticas > Políticas de compras**.</span><span class="sxs-lookup"><span data-stu-id="06907-136">Go to **navigation pane > Modules > Procurement and sourcing > Setup > Policies > Purchasing policies**.</span></span>
2. <span data-ttu-id="06907-137">Selecione **USMF da Política de Aquisição**.</span><span class="sxs-lookup"><span data-stu-id="06907-137">Select **Procurement Policy USMF**.</span></span> <span data-ttu-id="06907-138">Você precisa selecionar a política de compras para a entidade legal em que é permitido ao trabalhador conectado a seu perfil de usuário a pedir produtos.</span><span class="sxs-lookup"><span data-stu-id="06907-138">You need to select the purchasing policy for the legal entity that the worker connected to your user profile is allowed to order products in.</span></span> <span data-ttu-id="06907-139">Nos dados de demonstração USMF, o usuário administrador é conectado ao trabalhador chamado **Julia Funderburk**; ela pede produtos em USMF por padrão.</span><span class="sxs-lookup"><span data-stu-id="06907-139">In the USMF demo data, the Admin user is connected to the worker called **Julia Funderburk**, and she orders products in USMF by default.</span></span>  
3. <span data-ttu-id="06907-140">Selecione o catálogo que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="06907-140">Select the catalog that you've just created.</span></span>
4. <span data-ttu-id="06907-141">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="06907-141">Select **OK**.</span></span>

## <a name="use-the-catalog"></a><span data-ttu-id="06907-142">Usar o catálogo</span><span class="sxs-lookup"><span data-stu-id="06907-142">Use the catalog</span></span>
1. <span data-ttu-id="06907-143">Vá para **Painel de navegação > Módulos > Compras e fornecimento > Requisições de compras > Todas as requisições de compras**.</span><span class="sxs-lookup"><span data-stu-id="06907-143">Go to **navigation pane > Modules > Procurement and sourcing > Purchase requisitions > All purchase requisitions**.</span></span>
2. <span data-ttu-id="06907-144">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="06907-144">Select **New**.</span></span>
3. <span data-ttu-id="06907-145">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="06907-145">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="06907-146">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="06907-146">Select **OK**.</span></span>
5. <span data-ttu-id="06907-147">Selecione **Adicionar produtos**.</span><span class="sxs-lookup"><span data-stu-id="06907-147">Select **Add products**.</span></span>
6. <span data-ttu-id="06907-148">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="06907-148">In the list, find and select the desired record.</span></span> <span data-ttu-id="06907-149">Você pode usar a hierarquia da categoria à esquerda ou o filtro na parte superior da lista para filtrar os produtos.</span><span class="sxs-lookup"><span data-stu-id="06907-149">You can use the category hierarchy on the left or the filter at the top of the list to filter the products.</span></span>  
7. <span data-ttu-id="06907-150">Selecione **Adicionar a linhas**.</span><span class="sxs-lookup"><span data-stu-id="06907-150">Select **Add to lines**.</span></span>
8. <span data-ttu-id="06907-151">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="06907-151">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]