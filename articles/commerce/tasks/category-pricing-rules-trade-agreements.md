---
title: Regras de preços de categoria para criar contratos comerciais
description: Este procedimento mostra como criar contratos comerciais de preço de vendas usando uma regra de definição de preços de categoria.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, RetailDiscountPricingWorkspace, RetailPricingDiscountCategoryPriceRule, RetailCategoryPriceRule, EcoResCategorySingleLookup, RetailCategoryPriceWizard, PriceDiscAdm, PriceDiscAdmTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a945a0f49df92731175c1624da98831bbc5bb741
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006076"
---
# <a name="category-pricing-rules-to-create-trade-agreements"></a><span data-ttu-id="81dcc-103">Regras de preços de categoria para criar contratos comerciais</span><span class="sxs-lookup"><span data-stu-id="81dcc-103">Category pricing rules to create trade agreements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="81dcc-104">Este procedimento mostra como criar contratos comerciais de preço de vendas usando uma regra de definição de preços de categoria.</span><span class="sxs-lookup"><span data-stu-id="81dcc-104">This procedure demonstrates how to create sales price trade agreements using a category pricing rule.</span></span> <span data-ttu-id="81dcc-105">A empresa de dados de demonstração usada para criar esta tarefa é USRT.</span><span class="sxs-lookup"><span data-stu-id="81dcc-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="81dcc-106">Esta tarefa é destinada à função de gerente de mercadorias de comércio.</span><span class="sxs-lookup"><span data-stu-id="81dcc-106">This task is intended for the Commerce merchandising manager role.</span></span>

1. <span data-ttu-id="81dcc-107">Clique em Gerenciamento de preços e descontos.</span><span class="sxs-lookup"><span data-stu-id="81dcc-107">Click Pricing and discount management.</span></span>
2. <span data-ttu-id="81dcc-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="81dcc-108">Click New.</span></span>
3. <span data-ttu-id="81dcc-109">Clique em Regra de preço de categoria.</span><span class="sxs-lookup"><span data-stu-id="81dcc-109">Click Category price rule.</span></span>
4. <span data-ttu-id="81dcc-110">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="81dcc-110">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="81dcc-111">No campo Código da conta, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="81dcc-111">In the Account code field, select an option.</span></span>
    * <span data-ttu-id="81dcc-112">Um código de conta do tipo "Grupo" é usado para configurar contratos comerciais de preço de venda específicos para Canais, programas de Fidelidade, Catálogos e Afiliações.</span><span class="sxs-lookup"><span data-stu-id="81dcc-112">A "Group" type account code is used to set up sales price trade agreements that are specific for Channels, Loyalty programs, Catalogs, and Affiliations.</span></span>  
6. <span data-ttu-id="81dcc-113">No campo Seleção de contas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="81dcc-113">In the Account selection field, enter or select a value.</span></span>
7. <span data-ttu-id="81dcc-114">No campo Categoria, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="81dcc-114">In the Category field, enter or select a value.</span></span>
8. <span data-ttu-id="81dcc-115">No campo Valor/Percentual, insira um número.</span><span class="sxs-lookup"><span data-stu-id="81dcc-115">In the Amount/Percent field, enter a number.</span></span>
9. <span data-ttu-id="81dcc-116">No campo Versão de arredondamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="81dcc-116">In the Rounding version field, enter or select a value.</span></span>
10. <span data-ttu-id="81dcc-117">Clique em Gerar contratos comerciais.</span><span class="sxs-lookup"><span data-stu-id="81dcc-117">Click Generate trade agreements.</span></span>
11. <span data-ttu-id="81dcc-118">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="81dcc-118">Click Next.</span></span>
12. <span data-ttu-id="81dcc-119">No campo De data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="81dcc-119">In the From date field, enter a date.</span></span>
13. <span data-ttu-id="81dcc-120">No campo Para data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="81dcc-120">In the To date field, enter a date.</span></span>
14. <span data-ttu-id="81dcc-121">Selecione Sim no campo Localizar próximo.</span><span class="sxs-lookup"><span data-stu-id="81dcc-121">Select Yes in the Find next field.</span></span>
15. <span data-ttu-id="81dcc-122">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="81dcc-122">Click Next.</span></span>
16. <span data-ttu-id="81dcc-123">Clique em Finish (Concluir).</span><span class="sxs-lookup"><span data-stu-id="81dcc-123">Click Finish.</span></span>
    * <span data-ttu-id="81dcc-124">Isso cria e abre um diário de contrato comercial para revisão.</span><span class="sxs-lookup"><span data-stu-id="81dcc-124">This creates a Trade agreement journal and opens it for your review.</span></span>  
17. <span data-ttu-id="81dcc-125">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="81dcc-125">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="81dcc-126">Os diários de contratos comerciais criados das regras de definição de preços de categoria não são lançados.</span><span class="sxs-lookup"><span data-stu-id="81dcc-126">The trade agreement journals created from the Category pricing rules aren't posted.</span></span> <span data-ttu-id="81dcc-127">Você pode revisar e editar os preços produzidos antes de lançá-los.</span><span class="sxs-lookup"><span data-stu-id="81dcc-127">You can  review and edit the prices generated before posting them.</span></span>  
18. <span data-ttu-id="81dcc-128">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="81dcc-128">Click Edit.</span></span>
19. <span data-ttu-id="81dcc-129">No campo Valor em moeda, insira um número.</span><span class="sxs-lookup"><span data-stu-id="81dcc-129">In the Amount in currency field, enter a number.</span></span>
20. <span data-ttu-id="81dcc-130">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="81dcc-130">Click Post.</span></span>
21. <span data-ttu-id="81dcc-131">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="81dcc-131">Click OK.</span></span>
22. <span data-ttu-id="81dcc-132">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="81dcc-132">Close the page.</span></span>
23. <span data-ttu-id="81dcc-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="81dcc-133">Close the page.</span></span>
24. <span data-ttu-id="81dcc-134">Clique na guia Regras de preço de categoria.</span><span class="sxs-lookup"><span data-stu-id="81dcc-134">Click the Category price rules tab.</span></span>
    * <span data-ttu-id="81dcc-135">As regras de definição de preços específicas da categoria do canal serão mostradas nesta lista.</span><span class="sxs-lookup"><span data-stu-id="81dcc-135">Channel specific Category pricing rules will show in this list.</span></span>  

