---
title: Criar um estado do ciclo de vida do produto padrão
description: Este procedimento mostra como criar um estado do ciclo de vida do produto padrão, bem como associar o estado padrão com os produtos liberados.
author: cvocph
manager: tfehr
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b65f34c1d7a0fd22201df5b48f8d42d452d6b8ef
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5216072"
---
# <a name="create-a-default-product-lifecycle-state"></a><span data-ttu-id="b39ad-103">Criar um estado do ciclo de vida do produto padrão</span><span class="sxs-lookup"><span data-stu-id="b39ad-103">Create a default product lifecycle state</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b39ad-104">Este procedimento mostra como criar um estado do ciclo de vida do produto padrão, bem como associar o estado padrão com os produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="b39ad-104">This procedure shows how to create a default product lifecycle state as well as how to associate the default state with released products.</span></span>


## <a name="create-a-default-lifecycle-state"></a><span data-ttu-id="b39ad-105">Crie um estado do ciclo de vida padrão</span><span class="sxs-lookup"><span data-stu-id="b39ad-105">Create a default lifecycle state</span></span>
1. <span data-ttu-id="b39ad-106">Vá para Gerenciamento de informações de produto > Configuração > Estado do ciclo de vida do produto.</span><span class="sxs-lookup"><span data-stu-id="b39ad-106">Go to Product information management > Setup > Product lifecycle state.</span></span>
2. <span data-ttu-id="b39ad-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b39ad-107">Click New.</span></span>
3. <span data-ttu-id="b39ad-108">No campo Estado, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b39ad-108">In the State field, type a value.</span></span>
4. <span data-ttu-id="b39ad-109">Selecione Sim no campo Padrão quando liberado para entidade legal.</span><span class="sxs-lookup"><span data-stu-id="b39ad-109">Select Yes in the Default when released to legal entity field.</span></span>
5. <span data-ttu-id="b39ad-110">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b39ad-110">In the Description field, type a value.</span></span>
6. <span data-ttu-id="b39ad-111">Selecione Não no campo Está ativo para planejar.</span><span class="sxs-lookup"><span data-stu-id="b39ad-111">Select No in the Is active for planning field.</span></span>

> [!NOTE]
> <span data-ttu-id="b39ad-112">Caso um novo produto liberado não deva ser incluído no Planejamento mestre, selecione Não.</span><span class="sxs-lookup"><span data-stu-id="b39ad-112">If a new released product should not be included in Master planning, select No.</span></span> <span data-ttu-id="b39ad-113">Caso deva ser incluído no Planejamento mestre, deixe o controle em seu valor padrão Sim.</span><span class="sxs-lookup"><span data-stu-id="b39ad-113">If it should be included in Master planning, leave the control at its default value Yes.</span></span>  

## <a name="create-a-new-released-product"></a><span data-ttu-id="b39ad-114">Crie um novo produto liberado</span><span class="sxs-lookup"><span data-stu-id="b39ad-114">Create a new released product</span></span>
1. <span data-ttu-id="b39ad-115">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b39ad-115">Close the page.</span></span>
2. <span data-ttu-id="b39ad-116">Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="b39ad-116">Go to Product information management > Products > Released products.</span></span>
3. <span data-ttu-id="b39ad-117">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b39ad-117">Click New.</span></span>
4. <span data-ttu-id="b39ad-118">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b39ad-118">In the Product number field, type a value.</span></span>
5. <span data-ttu-id="b39ad-119">No campo Nome do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b39ad-119">In the Product name field, type a value.</span></span>
6. <span data-ttu-id="b39ad-120">No campo Nome da pesquisa, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b39ad-120">In the Search name field, type a value.</span></span>
7. <span data-ttu-id="b39ad-121">No campo Grupo de modelos do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b39ad-121">In the Item model group field, enter or select a value.</span></span>
8. <span data-ttu-id="b39ad-122">No campo Grupo de itens, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b39ad-122">In the Item group field, enter or select a value.</span></span>
9. <span data-ttu-id="b39ad-123">No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b39ad-123">In the Storage dimension group field, enter or select a value.</span></span>
10. <span data-ttu-id="b39ad-124">No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b39ad-124">In the Tracking dimension group field, enter or select a value.</span></span>
11. <span data-ttu-id="b39ad-125">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b39ad-125">Click OK.</span></span>

> [!NOTE]
> <span data-ttu-id="b39ad-126">O estado do ciclo de vida do produto padrão é uma definição global.</span><span class="sxs-lookup"><span data-stu-id="b39ad-126">The default product lifecycle state is a global definition.</span></span>  

## <a name="change-the-product-to-an-active-state"></a><span data-ttu-id="b39ad-127">Altere o produto para um estado ativo</span><span class="sxs-lookup"><span data-stu-id="b39ad-127">Change the product to an active state</span></span>
1. <span data-ttu-id="b39ad-128">No campo Estado do ciclo de vida do produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b39ad-128">In the Product lifecycle state field, enter or select a value.</span></span>

> [!NOTE]
> <span data-ttu-id="b39ad-129">Suponha que você tenha configurado um estado ativo, agora você pode selecioná-lo para permitir que o produto seja usado no Planejamento mestre e no cálculo do nível da BOM.</span><span class="sxs-lookup"><span data-stu-id="b39ad-129">Assume that you have set up an active state, you can now select the active state to allow the product to be used in Master planning and BOM-level calculation.</span></span> <span data-ttu-id="b39ad-130">Obviamente, isso só faz sentido se todos os detalhes do produto que são necessários para o planejamento consistente forem especificados.</span><span class="sxs-lookup"><span data-stu-id="b39ad-130">Obviously, this only makes sense if all the product details that are required for consistent planning are specified.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]