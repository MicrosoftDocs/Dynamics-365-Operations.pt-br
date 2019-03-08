---
title: Criar um catálogo de compras
description: Este guia mostra como criar um catálogo de compras.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProcCategoryHierarchyManagement, CatProcureCatalogListPage, CatProcureCatalogCreate, CatProcureCatalogEdit, SysPolicyListPage, SysPolicy, CatCatalogPolicyRule, PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqAddItem
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6f2a010e21f16b3908a6ee5f18d8f144c5130be7
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "314684"
---
# <a name="create-a-procurement-catalog"></a><span data-ttu-id="7382c-103">Criar um catálogo de compras</span><span class="sxs-lookup"><span data-stu-id="7382c-103">Create a procurement catalog</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7382c-104">Este guia mostra como criar um catálogo de compras.</span><span class="sxs-lookup"><span data-stu-id="7382c-104">This guide shows you how to create a procurement catalog.</span></span> <span data-ttu-id="7382c-105">Essa tarefa é tipicamente realizada por um profissional de aquisição.</span><span class="sxs-lookup"><span data-stu-id="7382c-105">This task would typically be carried out by a procurement professional.</span></span> <span data-ttu-id="7382c-106">Você também aprenderá como os empregados podem usar o catálogo quando criam uma requisição.</span><span class="sxs-lookup"><span data-stu-id="7382c-106">You will also learn how employees can use the catalog when they create a requisition.</span></span> <span data-ttu-id="7382c-107">Antes de criar um catálogo, deve haver uma hierarquia da categoria da obtenção em seu sistema.</span><span class="sxs-lookup"><span data-stu-id="7382c-107">Before you can create a catalog, there must be a procurement category hierarchy in your system.</span></span> <span data-ttu-id="7382c-108">A hierarquia é herdada pelo catálogo novo, junto com todos os produtos que estão na hierarquia.</span><span class="sxs-lookup"><span data-stu-id="7382c-108">The hierarchy is inherited by the new catalog, along with all the products that are in the hierarchy.</span></span> <span data-ttu-id="7382c-109">Você pode usar este guia na empresa USMF dos dados do programa demonstrativo onde a hierarquia da categoria da obtenção está disponível, assim como os exemplos usados nas etapas de procedimento.</span><span class="sxs-lookup"><span data-stu-id="7382c-109">You can use this guide in demo data company USMF where the procurement category hierarchy is available, as well as the examples used in the procedure steps.</span></span>


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a><span data-ttu-id="7382c-110">Assegure-se de que uma hierarquia da categoria da obtenção exista</span><span class="sxs-lookup"><span data-stu-id="7382c-110">Ensure that a procurement category hierarchy exists</span></span>
1. <span data-ttu-id="7382c-111">Vá para Aquisição e fornecimento > Categorias de aquisição.</span><span class="sxs-lookup"><span data-stu-id="7382c-111">Go to Procurement and sourcing > Procurement categories.</span></span>
    * <span data-ttu-id="7382c-112">Uma hierarquia da categoria da obtenção está disponível na empresa dos dados do programa demonstrativo de USMF e os produtos foram adicionados às máquinas de escritório/categoria dos computadores.</span><span class="sxs-lookup"><span data-stu-id="7382c-112">A procurement category hierarchy is available in the USMF demo data company and products have been added to the Office machines/Computers category.</span></span> <span data-ttu-id="7382c-113">Se você estiver executando este procedimento como um guia de tarefa você precisará desbloquear o guia se quiser pesquisar entre a categoria.</span><span class="sxs-lookup"><span data-stu-id="7382c-113">If you’re running this procedure as a task guide, you’ll need to unlock the guide if you want to browse through the category.</span></span> <span data-ttu-id="7382c-114">Se uma hierarquia não estava disponível, você a criaria clicando em Novo.</span><span class="sxs-lookup"><span data-stu-id="7382c-114">If a hierarchy was not available, you’d create it by clicking New.</span></span> <span data-ttu-id="7382c-115">Isso só pode ser feito uma vez.</span><span class="sxs-lookup"><span data-stu-id="7382c-115">This can only be done once.</span></span>  
2. <span data-ttu-id="7382c-116">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7382c-116">Close the page.</span></span>

## <a name="create-a-catalog"></a><span data-ttu-id="7382c-117">Criar um catálogo</span><span class="sxs-lookup"><span data-stu-id="7382c-117">Create a catalog</span></span>
1. <span data-ttu-id="7382c-118">Vá para Compras > Catálogos > Catálogos de compras.</span><span class="sxs-lookup"><span data-stu-id="7382c-118">Go to Procurement and sourcing > Catalogs > Procurement catalogs.</span></span>
2. <span data-ttu-id="7382c-119">Clique em Novo catálogo de compras para abrir o formulário suspenso da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7382c-119">Click New procurement catalog to open the drop dialog.</span></span>
3. <span data-ttu-id="7382c-120">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7382c-120">In the Name field, type a value.</span></span>
4. <span data-ttu-id="7382c-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7382c-121">Click OK.</span></span>
5. <span data-ttu-id="7382c-122">Na árvore, expanda 'CATEGORIAS DE AQUISIÇÃO CORPORATIVA\MÁQUINAS DE ESCRITÓRIO'.</span><span class="sxs-lookup"><span data-stu-id="7382c-122">In the tree, expand 'CORP PROCUREMENT CATEGORIES'.</span></span>
6. <span data-ttu-id="7382c-123">Na árvore, expanda 'OFFICE MACHINES'.</span><span class="sxs-lookup"><span data-stu-id="7382c-123">In the tree, expand 'OFFICE MACHINES'.</span></span>
7. <span data-ttu-id="7382c-124">Na árvore, selecione o nó ''Computadores".</span><span class="sxs-lookup"><span data-stu-id="7382c-124">In the tree, select 'Computers'.</span></span>
    * <span data-ttu-id="7382c-125">Os produtos da categoria da obtenção são indicados na lista.</span><span class="sxs-lookup"><span data-stu-id="7382c-125">The products from the procurement category are displayed in the list.</span></span> <span data-ttu-id="7382c-126">Se você quer adicionar um produto à categoria, você precisa fazer isso na página da hierarquia da categoria da obtenção ou na página dos detalhes do artigo.</span><span class="sxs-lookup"><span data-stu-id="7382c-126">If you want to add a product to the category you need to do this on the Procurement category hierarchy page or on the Item details page.</span></span>  
    * <span data-ttu-id="7382c-127">O tipo de atualização padrão determina se os produtos novos que foram adicionados à hierarquia da categoria da obtenção são imediatamente visíveis no catálogo.</span><span class="sxs-lookup"><span data-stu-id="7382c-127">The Default update type determines whether new products that have been added to the procurement category hierarchy are immediately visible in the catalog.</span></span> <span data-ttu-id="7382c-128">Se o tipo de atualização ajustado é dinâmico, as mudanças são visíveis imediatamente.</span><span class="sxs-lookup"><span data-stu-id="7382c-128">If the update type is set to Dynamic, changes are visible immediately.</span></span> <span data-ttu-id="7382c-129">Se o tipo de atualização é estática, os produtos novos são somente visíveis às pessoas que usam o catálogo depois que o catálogo foi publicado novamente.</span><span class="sxs-lookup"><span data-stu-id="7382c-129">If the update type is Static, new products are only visible to people using the catalog after the catalog has been re-published.</span></span> <span data-ttu-id="7382c-130">A ação da publicação está disponível na placa da ação na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="7382c-130">The Publish action is available on the Action Pane at the top of the page.</span></span> <span data-ttu-id="7382c-131">Se os produtos são removidos da hierarquia da categoria da obtenção, a mudança é imediatamente visível, apesar do valor no tipo de atualização campo padrão.</span><span class="sxs-lookup"><span data-stu-id="7382c-131">If products are removed from the procurement category hierarchy, the change is immediately visible, regardless of the value in the Default update type field.</span></span>  
8. <span data-ttu-id="7382c-132">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="7382c-132">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="7382c-133">Clique em Esconder.</span><span class="sxs-lookup"><span data-stu-id="7382c-133">Click Hide.</span></span>
10. <span data-ttu-id="7382c-134">No Painel de Ação, clique em Navegação de categoria.</span><span class="sxs-lookup"><span data-stu-id="7382c-134">On the Action Pane, click Category navigation.</span></span>
11. <span data-ttu-id="7382c-135">Clique em Desabilitar.</span><span class="sxs-lookup"><span data-stu-id="7382c-135">Click Disable.</span></span>
12. <span data-ttu-id="7382c-136">No Painel de Ação, clique em Navegação de categoria.</span><span class="sxs-lookup"><span data-stu-id="7382c-136">On the Action Pane, click Category navigation.</span></span>
13. <span data-ttu-id="7382c-137">Clique em Habilitar.</span><span class="sxs-lookup"><span data-stu-id="7382c-137">Click Enable.</span></span>
14. <span data-ttu-id="7382c-138">Clique em Ativar catálogo.</span><span class="sxs-lookup"><span data-stu-id="7382c-138">Click Activate catalog.</span></span>
15. <span data-ttu-id="7382c-139">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7382c-139">Close the page.</span></span>

## <a name="make-the-catalog-visible"></a><span data-ttu-id="7382c-140">Tornar o catálogo visível</span><span class="sxs-lookup"><span data-stu-id="7382c-140">Make the catalog visible</span></span>
1. <span data-ttu-id="7382c-141">Vá para Compras > Configuração > Políticas > Políticas de compras.</span><span class="sxs-lookup"><span data-stu-id="7382c-141">Go to Procurement and sourcing > Setup > Policies > Purchasing policies.</span></span>
2. <span data-ttu-id="7382c-142">Selecione Política de compras USMF.</span><span class="sxs-lookup"><span data-stu-id="7382c-142">Select Procurement Policy USMF.</span></span>
    * <span data-ttu-id="7382c-143">Você precisa selecionar a política de compras para a entidade legal em que é permitido ao trabalhador conectado a seu perfil de usuário a pedir produtos.</span><span class="sxs-lookup"><span data-stu-id="7382c-143">You need to select the purchasing policy for the legal entity that the worker connected to your user profile is allowed to order products in.</span></span> <span data-ttu-id="7382c-144">Nos dados do programa demonstrativo de USMF, o usuário do Admin é conectado ao trabalhador chamado Julia Funderburk, e pede produtos em USMF por padrão.</span><span class="sxs-lookup"><span data-stu-id="7382c-144">In the USMF demo data, the Admin user is connected to the worker called Julia Funderburk, and she orders products in USMF by default.</span></span>  
3. <span data-ttu-id="7382c-145">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7382c-145">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="7382c-146">Selecione o catálogo que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="7382c-146">Select the catalog that you’ve just created.</span></span>
5. <span data-ttu-id="7382c-147">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7382c-147">Click OK.</span></span>
6. <span data-ttu-id="7382c-148">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7382c-148">Close the page.</span></span>
7. <span data-ttu-id="7382c-149">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7382c-149">Close the page.</span></span>

## <a name="use-the-catalog"></a><span data-ttu-id="7382c-150">Usar o catálogo</span><span class="sxs-lookup"><span data-stu-id="7382c-150">Use the catalog</span></span>
1. <span data-ttu-id="7382c-151">Vá para Compras > Requisições de compra > Todas as requisições de compra.</span><span class="sxs-lookup"><span data-stu-id="7382c-151">Go to Procurement and sourcing > Purchase requisitions > All purchase requisitions.</span></span>
2. <span data-ttu-id="7382c-152">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7382c-152">Click New.</span></span>
3. <span data-ttu-id="7382c-153">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7382c-153">In the Name field, type a value.</span></span>
4. <span data-ttu-id="7382c-154">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7382c-154">Click OK.</span></span>
5. <span data-ttu-id="7382c-155">Clique em Adicionar produtos.</span><span class="sxs-lookup"><span data-stu-id="7382c-155">Click Add products.</span></span>
6. <span data-ttu-id="7382c-156">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="7382c-156">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7382c-157">Você pode usar a hierarquia da categoria à esquerda ou o filtro na parte superior da lista para filtrar os produtos.</span><span class="sxs-lookup"><span data-stu-id="7382c-157">You can use the category hierarchy on the left or the filter at the top of the list to filter the products.</span></span>  
7. <span data-ttu-id="7382c-158">Clique em Adicionar às linhas.</span><span class="sxs-lookup"><span data-stu-id="7382c-158">Click Add to lines.</span></span>
8. <span data-ttu-id="7382c-159">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="7382c-159">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="7382c-160">Clique em Adicionar às linhas.</span><span class="sxs-lookup"><span data-stu-id="7382c-160">Click Add to lines.</span></span>
10. <span data-ttu-id="7382c-161">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7382c-161">Click OK.</span></span>

