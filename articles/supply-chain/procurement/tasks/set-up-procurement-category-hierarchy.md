--- 
title: Configurar uma hierarquia de categorias de compras
description: "Este procedimento mostra como criar novos nós em uma hierarquia de categorias de aquisição e como configurar uma categoria de aquisição para ser usada em um processo de aquisição."
author: mkirknel
manager: AnnBe
ms.date: 11/06/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 6ad5c8552a6989e9093d0b1325754bc0f6d19372
ms.openlocfilehash: 4541d029c9c3be3ee42332e5d8ff183dd503f13e
ms.contentlocale: pt-br
ms.lasthandoff: 11/06/2017

---
# <a name="set-up-a-procurement-category-hierarchy"></a><span data-ttu-id="1274f-103">Configurar uma hierarquia de categorias de compras</span><span class="sxs-lookup"><span data-stu-id="1274f-103">Set up a procurement category hierarchy</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1274f-104">Este procedimento mostra como criar novos nós em uma hierarquia de categorias de aquisição e como configurar uma categoria de aquisição para ser usada em um processo de aquisição.</span><span class="sxs-lookup"><span data-stu-id="1274f-104">This procedure shows you how to create new nodes in a procurement category hierarchy and how to configure a procurement category to be used in a procurement process.</span></span> <span data-ttu-id="1274f-105">Essas tarefas são normalmente realizadas por um Gerente de compras.</span><span class="sxs-lookup"><span data-stu-id="1274f-105">These tasks would typically be carried out by a Purchasing manager.</span></span> <span data-ttu-id="1274f-106">Antes que você possa começar esse procedimento, é necessário que exista uma hierarquia de categoria do tipo Aquisição.</span><span class="sxs-lookup"><span data-stu-id="1274f-106">Before you can start this procedure, there must be a category hierarchy of type Procurement.</span></span> <span data-ttu-id="1274f-107">Se você for utilizar uma empresa de dados demonstrativos, é possível executar esse procedimento na empresa USMF.</span><span class="sxs-lookup"><span data-stu-id="1274f-107">If you're using a demo data company, you can run this procedure in the USMF company.</span></span>


## <a name="add-a-new-procurement-category"></a><span data-ttu-id="1274f-108">Adicione uma nova categoria de aquisição.</span><span class="sxs-lookup"><span data-stu-id="1274f-108">Add a new procurement category</span></span>
1. <span data-ttu-id="1274f-109">Vá para Aquisição e fornecimento > Categorias de aquisição.</span><span class="sxs-lookup"><span data-stu-id="1274f-109">Go to Procurement and sourcing > Procurement categories.</span></span>
2. <span data-ttu-id="1274f-110">Clique em Editar hierarquia de categoria.</span><span class="sxs-lookup"><span data-stu-id="1274f-110">Click Edit category hierarchy.</span></span>
    * <span data-ttu-id="1274f-111">A hierarquia de categorias de aquisição atual é exibida no lado esquerdo da página.</span><span class="sxs-lookup"><span data-stu-id="1274f-111">The current procurement category hierarchy is displayed in the left side of the page.</span></span> <span data-ttu-id="1274f-112">Você está prestes a modificar a hierarquia.</span><span class="sxs-lookup"><span data-stu-id="1274f-112">You  are about to modify the hierarchy.</span></span>  
3. <span data-ttu-id="1274f-113">Clique em Novo nó de categoria.</span><span class="sxs-lookup"><span data-stu-id="1274f-113">Click New category node.</span></span>
    * <span data-ttu-id="1274f-114">O sistema seleciona o nó superior por padrão.</span><span class="sxs-lookup"><span data-stu-id="1274f-114">The system selects the top node by default.</span></span> <span data-ttu-id="1274f-115">Se você estiver executando esse procedimento como um guia de tarefa, é possível clicar no botão Desbloquear e selecionar outro nó superior onde irá inserir o novo nó.</span><span class="sxs-lookup"><span data-stu-id="1274f-115">If you are running this procedure as a task guide, you can click the Unlock button and select another parent node to insert your new node into.</span></span> <span data-ttu-id="1274f-116">Assim que isso for feito, bloqueie o guia de tarefa novamente e clique em Novo nó de categoria.</span><span class="sxs-lookup"><span data-stu-id="1274f-116">Once that is done, lock the task guide again and then click New category node.</span></span>  
4. <span data-ttu-id="1274f-117">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1274f-117">In the Name field, type a value.</span></span>
5. <span data-ttu-id="1274f-118">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1274f-118">In the Description field, type a value.</span></span>
6. <span data-ttu-id="1274f-119">No campo Nome amigável, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1274f-119">In the Friendly name field, type a value.</span></span>
    * <span data-ttu-id="1274f-120">O nome amigável é opcional.</span><span class="sxs-lookup"><span data-stu-id="1274f-120">The friendly name is optional.</span></span> <span data-ttu-id="1274f-121">Ele será exibido nas pesquisas de categoria junto com o nome da categoria.</span><span class="sxs-lookup"><span data-stu-id="1274f-121">It will be displayed in category lookups together with the category name.</span></span>  
7. <span data-ttu-id="1274f-122">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1274f-122">Click Save.</span></span>

## <a name="add-products-to-your-new-procurement-category"></a><span data-ttu-id="1274f-123">Adicionar produtos a sua nova categoria de aquisição</span><span class="sxs-lookup"><span data-stu-id="1274f-123">Add products to your new procurement category</span></span>
1. <span data-ttu-id="1274f-124">Vá para Aquisição e fornecimento > Categorias de aquisição.</span><span class="sxs-lookup"><span data-stu-id="1274f-124">Go to Procurement and sourcing > Procurement categories.</span></span>
    * <span data-ttu-id="1274f-125">Selecione o nó que você acabou de adicionar.</span><span class="sxs-lookup"><span data-stu-id="1274f-125">Select the node you just added.</span></span> <span data-ttu-id="1274f-126">Se você estiver executando este procedimento como um guia de tarefa você talvez precise desbloquear o guia de tarefa para selecionar o nó.</span><span class="sxs-lookup"><span data-stu-id="1274f-126">If you’re running this procedure as a task guide you might need to unlock the task guide to select the node.</span></span>  
2. <span data-ttu-id="1274f-127">Ative a expansão da seção Produtos.</span><span class="sxs-lookup"><span data-stu-id="1274f-127">Toggle the expansion of the Products section.</span></span>
3. <span data-ttu-id="1274f-128">Clique em Adicionar para associar produtos à categoria de aquisição.</span><span class="sxs-lookup"><span data-stu-id="1274f-128">Click Add to associate products with the procurement category.</span></span>
4. <span data-ttu-id="1274f-129">Selecione o produto que você deseja adicionar à categoria de aquisição.</span><span class="sxs-lookup"><span data-stu-id="1274f-129">Select the product you want to add to the procurement category.</span></span>
5. <span data-ttu-id="1274f-130">Clique na seta para selecionar o produto.</span><span class="sxs-lookup"><span data-stu-id="1274f-130">Click the arrow to select the product.</span></span>
6. <span data-ttu-id="1274f-131">Selecione outro produto para adicionar à categoria de aquisição.</span><span class="sxs-lookup"><span data-stu-id="1274f-131">Select another product to add to the procurement category.</span></span>
7. <span data-ttu-id="1274f-132">Clique na seta para selecionar o produto.</span><span class="sxs-lookup"><span data-stu-id="1274f-132">Click the arrow to select the product.</span></span>
8. <span data-ttu-id="1274f-133">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1274f-133">Click OK.</span></span>

## <a name="add-approved-and-preferred-vendors"></a><span data-ttu-id="1274f-134">Adicionar fornecedores aprovados e preferenciais</span><span class="sxs-lookup"><span data-stu-id="1274f-134">Add approved and preferred vendors</span></span>
1. <span data-ttu-id="1274f-135">Alternar a expansão da seção Fornecedores.</span><span class="sxs-lookup"><span data-stu-id="1274f-135">Toggle the expansion of the Vendors section.</span></span>
2. <span data-ttu-id="1274f-136">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="1274f-136">Click Add.</span></span>
    * <span data-ttu-id="1274f-137">Você pode adicionar um fornecedor à uma categoria de aquisição e especificar se um fornecedor é o preferencial ou apenas aprovado na categoria.</span><span class="sxs-lookup"><span data-stu-id="1274f-137">You can add a vendor to a procurement category and specify whether a vendor is preferred or just approved for the category.</span></span> <span data-ttu-id="1274f-138">Quando você exclui um fornecedor de uma categoria, as transações do histórico com o fornecedor na categoria não serão excluídas.</span><span class="sxs-lookup"><span data-stu-id="1274f-138">When you delete a vendor from a category, the historical transactions with the vendor in the category are not deleted.</span></span>   
3. <span data-ttu-id="1274f-139">Encontre o fornecedor que você deseja adicionar à categoria.</span><span class="sxs-lookup"><span data-stu-id="1274f-139">Find the vendor you want to add to the category.</span></span>
4. <span data-ttu-id="1274f-140">Clique na seta para selecionar o fornecedor.</span><span class="sxs-lookup"><span data-stu-id="1274f-140">Click the arrow to select the vendor.</span></span>
5. <span data-ttu-id="1274f-141">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1274f-141">Click OK.</span></span>
6. <span data-ttu-id="1274f-142">Selecione a linha de fornecedor que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="1274f-142">Select the vendor row that you want to modify.</span></span>
7. <span data-ttu-id="1274f-143">No campo Status do fornecedor, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="1274f-143">In the Vendor status field, select an option.</span></span>
    * <span data-ttu-id="1274f-144">A configuração de seleção do fornecedor na regra Política de categoria controla se os preferenciais, aprovados, ou todos os fornecedores estão disponíveis para requisições de compra.</span><span class="sxs-lookup"><span data-stu-id="1274f-144">The vendor selection setting in the Category policy rule governs whether preferred, approved, or all vendors are available on purchase requisitions.</span></span>   

## <a name="add-additional-information-to-the-category"></a><span data-ttu-id="1274f-145">Adicionar informações adicionais à categoria</span><span class="sxs-lookup"><span data-stu-id="1274f-145">Add additional information to the category</span></span>
1. <span data-ttu-id="1274f-146">Ative a expansão da seção Grupos de critério de avaliação do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="1274f-146">Toggle the expansion of the Vendor evaluation criterion groups section.</span></span>
    * <span data-ttu-id="1274f-147">Esta aba permite que você defina os critérios sobre os quais os fornecedores na categoria de aquisição devem ser avaliados.</span><span class="sxs-lookup"><span data-stu-id="1274f-147">This tab allows you to define which criteria the vendors in the procurement category should be rated against.</span></span> <span data-ttu-id="1274f-148">Para fazer isso você deve clicar em Adicionar e então selecionar um grupo de avaliação de fornecedores que contêm os critérios desejados.</span><span class="sxs-lookup"><span data-stu-id="1274f-148">To do this you would click Add and then select a vendor evaluation group that contains the criteria you want.</span></span>  
2. <span data-ttu-id="1274f-149">Ative a expansão da seção Questionários.</span><span class="sxs-lookup"><span data-stu-id="1274f-149">Toggle the expansion of the Questionnaires section.</span></span>
    * <span data-ttu-id="1274f-150">Esta aba permite que você adicione questionários que irão aparecer na requisição, desde que você defina o Tipo de atividade como "Requisição".</span><span class="sxs-lookup"><span data-stu-id="1274f-150">This tab allows you to add questionnaires that will appear on the requisition, as long as you set the Activity type to "Requisition".</span></span> <span data-ttu-id="1274f-151">O solicitante precisa então preencher um questionário antes de enviar uma requisição para os produtos ou produto específico na categoria de aquisição.</span><span class="sxs-lookup"><span data-stu-id="1274f-151">The requester then has to fill out a questionnaire before they submit a requisition for the specific product or products in the procurement category.</span></span>  
3. <span data-ttu-id="1274f-152">Ative a expansão da seção Grupos de imposto sobre vendas do item.</span><span class="sxs-lookup"><span data-stu-id="1274f-152">Toggle the expansion of the Item sales tax groups section.</span></span>
4. <span data-ttu-id="1274f-153">No campo Grupo de imposto sobre vendas do item:, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="1274f-153">In the Item sales tax group: field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="1274f-154">Selecione um grupo de impostos sobre vendas.</span><span class="sxs-lookup"><span data-stu-id="1274f-154">Select a sales tax group.</span></span>
6. <span data-ttu-id="1274f-155">Ative a expansão da seção Página de categoria.</span><span class="sxs-lookup"><span data-stu-id="1274f-155">Toggle the expansion of the Category page section.</span></span>
    * <span data-ttu-id="1274f-156">Páginas de categoria são criadas na página Hierarquia de categoria.</span><span class="sxs-lookup"><span data-stu-id="1274f-156">Category pages are created in the Category hierarchy page.</span></span> <span data-ttu-id="1274f-157">Elas contêm informação sobre a categoria de aquisição como por exemplo informações sobre o tipo de produtos em uma categoria, imagens de produtos em uma categoria, ou anúncios como os descontos disponíveis em uma categoria.</span><span class="sxs-lookup"><span data-stu-id="1274f-157">They contain information about the procurement category such as information about the type of products in a category, images of products in a category, or announcements such as the discounts that are available in a category.</span></span> <span data-ttu-id="1274f-158">As informações em uma página de categoria são exibidas em requisições de compra.</span><span class="sxs-lookup"><span data-stu-id="1274f-158">The information in a category page is displayed on purchase requisitions.</span></span>  
7. <span data-ttu-id="1274f-159">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1274f-159">Close the page.</span></span>


