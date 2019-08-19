---
title: Aprovar fornecedores para categorias específicas da compras
description: Quando uma requisição da compra é criada, pode haver uma exigência para selecionar um vendedor aprovado ou preferido, dependendo de como as políticas de compra são definidas.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, DirPartyEcoResCategory, EcoResCategorySingleLookup, ProcCategoryHierarchyManagement
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: eec50e2e8f08fabb64f89c17159b97ba770026f8
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1836327"
---
# <a name="approve-vendors-for-specific-procurement-categories"></a><span data-ttu-id="ec1b9-103">Aprovar fornecedores para categorias específicas da compras</span><span class="sxs-lookup"><span data-stu-id="ec1b9-103">Approve vendors for specific procurement categories</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ec1b9-104">Quando uma requisição da compra é criada, pode haver uma exigência para selecionar um vendedor aprovado ou preferido, dependendo de como as políticas de compra são definidas.</span><span class="sxs-lookup"><span data-stu-id="ec1b9-104">When a purchase requisition is created, there may be a requirement to select an approved or preferred vendor, depending on how the purchasing policies are set up.</span></span> <span data-ttu-id="ec1b9-105">Este procedimento mostra como especificar se um vendedor é aprovado ou preferido para uma categoria específica da obtenção.</span><span class="sxs-lookup"><span data-stu-id="ec1b9-105">This procedure shows you how to specify that a vendor is approved or preferred for a specific procurement category.</span></span> <span data-ttu-id="ec1b9-106">Essa tarefa é tipicamente realizada por um profissional de aquisição.</span><span class="sxs-lookup"><span data-stu-id="ec1b9-106">This task would usually be carried out by a procurement professional.</span></span> <span data-ttu-id="ec1b9-107">Você pode usar este procedimento na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="ec1b9-107">You can use this procedure in demo data company USMF.</span></span>

1. <span data-ttu-id="ec1b9-108">Vá para Aquisição e fornecimento > Fornecedores > Todos os fornecedores.</span><span class="sxs-lookup"><span data-stu-id="ec1b9-108">Go to Procurement and sourcing > Vendors > All vendors.</span></span>
2. <span data-ttu-id="ec1b9-109">Selecione o vendedor que você quer ajustar como um vendedor aprovado ou preferido para uma categoria.</span><span class="sxs-lookup"><span data-stu-id="ec1b9-109">Select the vendor that you want to set as an approved or preferred vendor for a category.</span></span>
3. <span data-ttu-id="ec1b9-110">No Painel de Ação, clique em Geral.</span><span class="sxs-lookup"><span data-stu-id="ec1b9-110">On the Action Pane, click General.</span></span>
4. <span data-ttu-id="ec1b9-111">Clique em Categorias.</span><span class="sxs-lookup"><span data-stu-id="ec1b9-111">Click Categories.</span></span>
5. <span data-ttu-id="ec1b9-112">Clique em Adicionar categoria.</span><span class="sxs-lookup"><span data-stu-id="ec1b9-112">Click Add category.</span></span>
6. <span data-ttu-id="ec1b9-113">No campo Categoria, selecione ACESSÓRIOS DE ESCRITÓRIO E MESA (ACESSÓRIOS DE ESCRITÓRIO E MESA).</span><span class="sxs-lookup"><span data-stu-id="ec1b9-113">In the Category field, select OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES).</span></span>
7. <span data-ttu-id="ec1b9-114">No campo Status da categoria do vendedor, selecione "Preferido".</span><span class="sxs-lookup"><span data-stu-id="ec1b9-114">In the Vendor category status field, select 'Preferred'.</span></span>
    * <span data-ttu-id="ec1b9-115">É possível especificar mais de um vendedor preferido para uma categoria.</span><span class="sxs-lookup"><span data-stu-id="ec1b9-115">It’s possible to specify more than one preferred vendor for a category.</span></span>  
8. <span data-ttu-id="ec1b9-116">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="ec1b9-116">Click Save.</span></span>
9. <span data-ttu-id="ec1b9-117">Vá para Aquisição e fornecimento > Categorias de aquisição.</span><span class="sxs-lookup"><span data-stu-id="ec1b9-117">Go to Procurement and sourcing > Procurement categories.</span></span>
10. <span data-ttu-id="ec1b9-118">Na árvore, selecione 'CATEGORIAS DE AQUISIÇÃO CORPORATIVA\ESCRITÓRIO E ACESSÓRIOS DE MESA'.</span><span class="sxs-lookup"><span data-stu-id="ec1b9-118">In the tree, select 'CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES'.</span></span>
11. <span data-ttu-id="ec1b9-119">Expanda a seção Fornecedores.</span><span class="sxs-lookup"><span data-stu-id="ec1b9-119">Expand the Vendors section.</span></span>
    * <span data-ttu-id="ec1b9-120">Verifique se o vendedor que você selecionou aparece como um vendedor preferido para a categoria dos acessórios do escritório e de mesa.</span><span class="sxs-lookup"><span data-stu-id="ec1b9-120">Check if the vendor that you selected  appears as a preferred vendor for the Office and desk accessories category.</span></span> <span data-ttu-id="ec1b9-121">Se você está executando este procedimento como um guia da tarefa, você pode ter que clicar no botão para destravar para poder rolar para baixo a lista de vendedores.</span><span class="sxs-lookup"><span data-stu-id="ec1b9-121">If you’re running this procedure as a task guide, you may have to click the Unlock button to be able to scroll down to the list of vendors.</span></span>  <span data-ttu-id="ec1b9-122">É igualmente possível adicionar vendedores preferidos e aprovados nesta página.</span><span class="sxs-lookup"><span data-stu-id="ec1b9-122">It’s also possible to add preferred and approved vendors on this page.</span></span>  
12. <span data-ttu-id="ec1b9-123">Na árvore, expanda 'ACESSÓRIOS DE ESCRITÓRIO E MESA'.</span><span class="sxs-lookup"><span data-stu-id="ec1b9-123">In the tree, expand 'OFFICE AND DESK ACCESSORIES'.</span></span>
13. <span data-ttu-id="ec1b9-124">Na árvore, selecione "Tesouras".</span><span class="sxs-lookup"><span data-stu-id="ec1b9-124">In the tree, select 'Scissors'.</span></span>
14. <span data-ttu-id="ec1b9-125">Selecione Não no campo Fornecedores herdados da categoria principal:.</span><span class="sxs-lookup"><span data-stu-id="ec1b9-125">Select No in the Inherit vendors from parent category: field.</span></span>
15. <span data-ttu-id="ec1b9-126">Selecione Sim no campo Fornecedores herdados da categoria principal:.</span><span class="sxs-lookup"><span data-stu-id="ec1b9-126">Select Yes in the Inherit vendors from parent category: field.</span></span>

