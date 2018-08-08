--- 
title: "Criar um estado do ciclo de vida do produto padrão"
description: "Este procedimento mostra como criar um estado do ciclo de vida do produto padrão, bem como associar o estado padrão com os produtos liberados."
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 6e7e637157ee06a3d07a1a9c5da71295eb75b424
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---
# <a name="create-a-default-product-lifecycle-state"></a><span data-ttu-id="03658-103">Criar um estado do ciclo de vida do produto padrão</span><span class="sxs-lookup"><span data-stu-id="03658-103">Create a default product lifecycle state</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="03658-104">Este procedimento mostra como criar um estado do ciclo de vida do produto padrão, bem como associar o estado padrão com os produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="03658-104">This procedure shows how to create a default product lifecycle state as well as how to associate the default state with released products.</span></span>


## <a name="create-a-default-lifecycle-state"></a><span data-ttu-id="03658-105">Crie um estado do ciclo de vida padrão</span><span class="sxs-lookup"><span data-stu-id="03658-105">Create a default lifecycle state</span></span>
1. <span data-ttu-id="03658-106">Vá para Gerenciamento de informações de produto > Configuração > Estado do ciclo de vida do produto.</span><span class="sxs-lookup"><span data-stu-id="03658-106">Go to Product information management > Setup > Product lifecycle state.</span></span>
2. <span data-ttu-id="03658-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="03658-107">Click New.</span></span>
3. <span data-ttu-id="03658-108">No campo Estado, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="03658-108">In the State field, type a value.</span></span>
4. <span data-ttu-id="03658-109">Selecione Sim no campo Padrão quando liberado para entidade legal.</span><span class="sxs-lookup"><span data-stu-id="03658-109">Select Yes in the Default when released to legal entity field.</span></span>
5. <span data-ttu-id="03658-110">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="03658-110">In the Description field, type a value.</span></span>
6. <span data-ttu-id="03658-111">Selecione Não no campo Está ativo para planejar.</span><span class="sxs-lookup"><span data-stu-id="03658-111">Select No in the Is active for planning field.</span></span>

> [!NOTE]
> <span data-ttu-id="03658-112">Caso um novo produto liberado não deva ser incluído no Planejamento mestre, selecione Não.</span><span class="sxs-lookup"><span data-stu-id="03658-112">If a new released product should not be included in Master planning, select No.</span></span> <span data-ttu-id="03658-113">Caso deva ser incluído no Planejamento mestre, deixe o controle em seu valor padrão Sim.</span><span class="sxs-lookup"><span data-stu-id="03658-113">If it should be included in Master planning, leave the control at its default value Yes.</span></span>  

## <a name="create-a-new-released-product"></a><span data-ttu-id="03658-114">Crie um novo produto liberado</span><span class="sxs-lookup"><span data-stu-id="03658-114">Create a new released product</span></span>
1. <span data-ttu-id="03658-115">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="03658-115">Close the page.</span></span>
2. <span data-ttu-id="03658-116">Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="03658-116">Go to Product information management > Products > Released products.</span></span>
3. <span data-ttu-id="03658-117">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="03658-117">Click New.</span></span>
4. <span data-ttu-id="03658-118">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="03658-118">In the Product number field, type a value.</span></span>
5. <span data-ttu-id="03658-119">No campo Nome do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="03658-119">In the Product name field, type a value.</span></span>
6. <span data-ttu-id="03658-120">No campo Nome da pesquisa, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="03658-120">In the Search name field, type a value.</span></span>
7. <span data-ttu-id="03658-121">No campo Grupo de modelos do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="03658-121">In the Item model group field, enter or select a value.</span></span>
8. <span data-ttu-id="03658-122">No campo Grupo de itens, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="03658-122">In the Item group field, enter or select a value.</span></span>
9. <span data-ttu-id="03658-123">No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="03658-123">In the Storage dimension group field, enter or select a value.</span></span>
10. <span data-ttu-id="03658-124">No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="03658-124">In the Tracking dimension group field, enter or select a value.</span></span>
11. <span data-ttu-id="03658-125">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="03658-125">Click OK.</span></span>

> [!NOTE]
> <span data-ttu-id="03658-126">O estado do ciclo de vida do produto padrão é uma definição global.</span><span class="sxs-lookup"><span data-stu-id="03658-126">The default product lifecycle state is a global definition.</span></span>  

## <a name="change-the-product-to-an-active-state"></a><span data-ttu-id="03658-127">Altere o produto para um estado ativo</span><span class="sxs-lookup"><span data-stu-id="03658-127">Change the product to an active state</span></span>
1. <span data-ttu-id="03658-128">No campo Estado do ciclo de vida do produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="03658-128">In the Product lifecycle state field, enter or select a value.</span></span>

> [!NOTE]
> <span data-ttu-id="03658-129">Suponha que você tenha configurado um estado ativo, agora você pode selecioná-lo para permitir que o produto seja usado no Planejamento mestre e no cálculo do nível da BOM.</span><span class="sxs-lookup"><span data-stu-id="03658-129">Assume that you have set up an active state, you can now select the active state to allow the product to be used in Master planning and BOM-level calculation.</span></span> <span data-ttu-id="03658-130">Obviamente, isso só faz sentido se todos os detalhes do produto que são necessários para o planejamento consistente forem especificados.</span><span class="sxs-lookup"><span data-stu-id="03658-130">Obviously, this only makes sense if all the product details that are required for consistent planning are specified.</span></span>  


