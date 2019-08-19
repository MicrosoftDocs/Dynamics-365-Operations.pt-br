---
title: Criar uma hierarquia de classificação de produto
description: Este procedimento mostra como criar uma nova hierarquia de categoria e atribuir um tipo da hierarquia de código de mercadoria.
author: ShylaThompson
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategoryHierarchyCreate, EcoResCategory, EcoResCategoryHierarchyRole
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: faf43eb15283ffd7e36ad38728f166884dddcd85
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844816"
---
# <a name="create-a-hierarchy-of-product-classification"></a><span data-ttu-id="8c26a-103">Criar uma hierarquia de classificação de produto</span><span class="sxs-lookup"><span data-stu-id="8c26a-103">Create a hierarchy of product classification</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8c26a-104">Este procedimento mostra como criar uma nova hierarquia de categoria e atribuir um tipo da hierarquia de código de mercadoria.</span><span class="sxs-lookup"><span data-stu-id="8c26a-104">This procedure shows how to create a new category hierarchy and assign a commodity code hierarchy type.</span></span> <span data-ttu-id="8c26a-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="8c26a-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="8c26a-106">Esse procedimento é destinado ao gerente de categoria.</span><span class="sxs-lookup"><span data-stu-id="8c26a-106">This procedure is intended for the category manager.</span></span>


## <a name="create-the-new-category-hierarchy"></a><span data-ttu-id="8c26a-107">Criar a nova hierarquia de categoria</span><span class="sxs-lookup"><span data-stu-id="8c26a-107">Create the new category hierarchy</span></span>
1. <span data-ttu-id="8c26a-108">Vá para **Painel de navegação > Módulos > Gerenciamento de informações sobre produtos > Configuração > Categorias e atributos > Hierarquias de categoria**.</span><span class="sxs-lookup"><span data-stu-id="8c26a-108">Go to **Navigation pane > Modules > Product information management > Setup > Categories and attributes > Category hierarchies**.</span></span>
2. <span data-ttu-id="8c26a-109">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8c26a-109">Click **New**.</span></span>
3. <span data-ttu-id="8c26a-110">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8c26a-110">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="8c26a-111">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8c26a-111">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="8c26a-112">Clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="8c26a-112">Click **Create**.</span></span>

## <a name="build-the-hierarchy"></a><span data-ttu-id="8c26a-113">Construir a hierarquia</span><span class="sxs-lookup"><span data-stu-id="8c26a-113">Build the hierarchy</span></span>
1. <span data-ttu-id="8c26a-114">Clique no nó de categoria **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8c26a-114">Click **New** category node.</span></span>
2. <span data-ttu-id="8c26a-115">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8c26a-115">In the **Name** field, type a value.</span></span>
3. <span data-ttu-id="8c26a-116">No campo **Código**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8c26a-116">In the **Code** field, type a value.</span></span>
4. <span data-ttu-id="8c26a-117">No campo **Nome amigável**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8c26a-117">In the **Friendly name** field, type a value.</span></span>
5. <span data-ttu-id="8c26a-118">Clique no nó de categoria **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8c26a-118">Click **New** category node.</span></span>
6. <span data-ttu-id="8c26a-119">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8c26a-119">In the **Name** field, type a value.</span></span>
7. <span data-ttu-id="8c26a-120">No campo **Código**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8c26a-120">In the **Code** field, type a value.</span></span>
8. <span data-ttu-id="8c26a-121">No campo **Nome amigável**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8c26a-121">In the **Friendly name** field, type a value.</span></span>
9. <span data-ttu-id="8c26a-122">Clique no nó de categoria **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8c26a-122">Click **New** category node.</span></span>
10. <span data-ttu-id="8c26a-123">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8c26a-123">In the **Name** field, type a value.</span></span>
11. <span data-ttu-id="8c26a-124">No campo **Código**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8c26a-124">In the **Code** field, type a value.</span></span>
12. <span data-ttu-id="8c26a-125">No campo **Nome amigável**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8c26a-125">In the **Friendly name** field, type a value.</span></span>
13. <span data-ttu-id="8c26a-126">Clique no nó de categoria **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8c26a-126">Click **New** category node.</span></span>
14. <span data-ttu-id="8c26a-127">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8c26a-127">In the **Name** field, type a value.</span></span>
15. <span data-ttu-id="8c26a-128">No campo **Código**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8c26a-128">In the **Code** field, type a value.</span></span>
16. <span data-ttu-id="8c26a-129">No campo **Nome amigável**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8c26a-129">In the **Friendly name** field, type a value.</span></span>
17. <span data-ttu-id="8c26a-130">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8c26a-130">Close the page.</span></span>

## <a name="classify-the-hierarchy"></a><span data-ttu-id="8c26a-131">Classificar a hierarquia</span><span class="sxs-lookup"><span data-stu-id="8c26a-131">Classify the hierarchy</span></span>
1. <span data-ttu-id="8c26a-132">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="8c26a-132">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="8c26a-133">No **Painel de Ação**, clique em **Hierarquia de categoria**.</span><span class="sxs-lookup"><span data-stu-id="8c26a-133">On the **Action Pane**, click **Category hierarchy**.</span></span>
3. <span data-ttu-id="8c26a-134">Clique em **Associar tipo de hierarquia**.</span><span class="sxs-lookup"><span data-stu-id="8c26a-134">Click **Associate hierarchy type**.</span></span>
4. <span data-ttu-id="8c26a-135">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8c26a-135">Click **New**.</span></span>
5. <span data-ttu-id="8c26a-136">No campo **Tipo de hierarquia de categoria**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="8c26a-136">In the **Category hierarchy type** field, select an option.</span></span> <span data-ttu-id="8c26a-137">Selecione o **Tipo de hierarquia de categoria de códigos de mercadoria para a classificação de produtos**.</span><span class="sxs-lookup"><span data-stu-id="8c26a-137">Select the **Commodity code category hierarchy type for product classification**.</span></span>  
6. <span data-ttu-id="8c26a-138">No campo **Hierarquia de categoria**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8c26a-138">In the **Category hierarchy** field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="8c26a-139">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="8c26a-139">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="8c26a-140">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="8c26a-140">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="8c26a-141">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8c26a-141">Close the page.</span></span>

