---
title: Aprovar fornecedores para categorias específicas da compras
description: Este tópico explica como aprovar fornecedores para categorias específicas de compras no Dynamics 365 Supply Chain Management.
author: kamaybac
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable, DirPartyEcoResCategory, EcoResCategorySingleLookup, ProcCategoryHierarchyManagement
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 887905c35c684f2f60c3ce17eb652532831193cc
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812437"
---
# <a name="approve-vendors-for-specific-procurement-categories"></a><span data-ttu-id="5bfe8-103">Aprovar fornecedores para categorias específicas da compras</span><span class="sxs-lookup"><span data-stu-id="5bfe8-103">Approve vendors for specific procurement categories</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5bfe8-104">Este tópico explica como aprovar fornecedores para categorias específicas de compras no Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5bfe8-104">This topic explains how to approve vendors for specific procurement categories in Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="5bfe8-105">Quando uma requisição da compra é criada, pode haver uma exigência para selecionar um vendedor aprovado ou preferido, dependendo de como as políticas de compra são definidas.</span><span class="sxs-lookup"><span data-stu-id="5bfe8-105">When a purchase requisition is created, there may be a requirement to select an approved or preferred vendor, depending on how the purchasing policies are set up.</span></span> <span data-ttu-id="5bfe8-106">Este procedimento mostra como especificar se um vendedor é aprovado ou preferido para uma categoria específica da obtenção.</span><span class="sxs-lookup"><span data-stu-id="5bfe8-106">This procedure shows you how to specify that a vendor is approved or preferred for a specific procurement category.</span></span> <span data-ttu-id="5bfe8-107">Essa tarefa é tipicamente realizada por um profissional de aquisição.</span><span class="sxs-lookup"><span data-stu-id="5bfe8-107">This task would usually be carried out by a procurement professional.</span></span> <span data-ttu-id="5bfe8-108">Você pode usar este procedimento na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="5bfe8-108">You can use this procedure in demo data company USMF.</span></span>

1. <span data-ttu-id="5bfe8-109">No Painel de Navegação, vá para **Módulos > Compras e fornecimento > Fornecedores > Todos os fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="5bfe8-109">In the navigation pane, go to **Modules > Procurement and sourcing > Vendors > All vendors**.</span></span>
2. <span data-ttu-id="5bfe8-110">Selecione o vendedor que você quer ajustar como um vendedor aprovado ou preferido para uma categoria.</span><span class="sxs-lookup"><span data-stu-id="5bfe8-110">Select the vendor that you want to set as an approved or preferred vendor for a category.</span></span>
3. <span data-ttu-id="5bfe8-111">No Painel de Ação, selecione **Geral**.</span><span class="sxs-lookup"><span data-stu-id="5bfe8-111">On the Action Pane, select **General**.</span></span>
4. <span data-ttu-id="5bfe8-112">Selecione **Categorias**.</span><span class="sxs-lookup"><span data-stu-id="5bfe8-112">Select **Categories**.</span></span>
5. <span data-ttu-id="5bfe8-113">Selecione **Adicionar categoria**.</span><span class="sxs-lookup"><span data-stu-id="5bfe8-113">Select **Add category**.</span></span>
6. <span data-ttu-id="5bfe8-114">No campo **Categoria**, selecione **ACESSÓRIOS DE ESCRITÓRIO E MESA (ACESSÓRIOS DE ESCRITÓRIO E MESA)**.</span><span class="sxs-lookup"><span data-stu-id="5bfe8-114">In the **Category** field, select **OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES)**.</span></span>
7. <span data-ttu-id="5bfe8-115">No campo **Status da categoria do fornecedor**, selecione **Preferencial**.</span><span class="sxs-lookup"><span data-stu-id="5bfe8-115">In the **Vendor category status** field, select **Preferred**.</span></span> <span data-ttu-id="5bfe8-116">É possível especificar mais de um vendedor preferido para uma categoria.</span><span class="sxs-lookup"><span data-stu-id="5bfe8-116">It's possible to specify more than one preferred vendor for a category.</span></span>  
8. <span data-ttu-id="5bfe8-117">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5bfe8-117">Select **Save**.</span></span>
9. <span data-ttu-id="5bfe8-118">No Painel de Navegação, vá para **Módulos > Compras e fornecimento > Categorias de compras**.</span><span class="sxs-lookup"><span data-stu-id="5bfe8-118">In the navigation pane, go to **Modules > Procurement and sourcing > Procurement categories**.</span></span>
10. <span data-ttu-id="5bfe8-119">Na árvore, selecione **CATEGORIAS DE AQUISIÇÃO CORPORATIVA\ESCRITÓRIO E ACESSÓRIOS DE MESA**.</span><span class="sxs-lookup"><span data-stu-id="5bfe8-119">In the tree, select **CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES**.</span></span>
11. <span data-ttu-id="5bfe8-120">Expanda a seção **Fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="5bfe8-120">Expand the **Vendors** section.</span></span> <span data-ttu-id="5bfe8-121">Verifique se o fornecedor que você selecionou aparece como vendedor preferencial na categoria Acessórios de escritório e mesa.</span><span class="sxs-lookup"><span data-stu-id="5bfe8-121">Check if the vendor that you selected appears as a preferred vendor for the Office and desk accessories category.</span></span> <span data-ttu-id="5bfe8-122">Se você está executando este procedimento como um guia da tarefa, você pode ter que selecionar o botão **Desbloquear** para destravar para poder rolar para baixo a lista de vendedores.</span><span class="sxs-lookup"><span data-stu-id="5bfe8-122">If you're running this procedure as a task guide, you may have to select the **Unlock** button to be able to scroll down to the list of vendors.</span></span>  <span data-ttu-id="5bfe8-123">É igualmente possível adicionar vendedores preferidos e aprovados nesta página.</span><span class="sxs-lookup"><span data-stu-id="5bfe8-123">It's also possible to add preferred and approved vendors on this page.</span></span>  
12. <span data-ttu-id="5bfe8-124">Na árvore, expanda **ACESSÓRIOS DE ESCRITÓRIO E MESA** e selecione **Tesouras**.</span><span class="sxs-lookup"><span data-stu-id="5bfe8-124">In the tree, expand **OFFICE AND DESK ACCESSORIES** and select **Scissors**.</span></span>
13. <span data-ttu-id="5bfe8-125">Selecione **Não** no campo **Fornecedores herdados da categoria principal:**.</span><span class="sxs-lookup"><span data-stu-id="5bfe8-125">Select **No** in the **Inherit vendors from parent category:** field.</span></span>
14. <span data-ttu-id="5bfe8-126">Selecione **Sim** no campo **Fornecedores herdados da categoria principal:**.</span><span class="sxs-lookup"><span data-stu-id="5bfe8-126">Select **Yes** in the **Inherit vendors from parent category:** field.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]