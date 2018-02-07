--- 
title: " Mover produtos do centro de distribuição para a loja usando a compra centralizada"
description: "Este procedimento orienta nas etapas para criar e processar uma compra centralizada para distribuir produtos de um localização para uma ou várias lojas."
author: rubencdelgado
manager: AnnBe
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 9d9a5d4fdece1cfb573224bd54d96ccd281c0f09
ms.contentlocale: pt-br
ms.lasthandoff: 02/07/2018

---
# <a name="push-products-from-distribution-center-to-store-using-buyers-push"></a><span data-ttu-id="dd406-103"> Mover produtos do centro de distribuição para a loja usando a compra centralizada</span><span class="sxs-lookup"><span data-stu-id="dd406-103">Push products from distribution center to store using buyer's push</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="dd406-104">Este procedimento orienta nas etapas para criar e processar uma compra centralizada para distribuir produtos de um localização para uma ou várias lojas.</span><span class="sxs-lookup"><span data-stu-id="dd406-104">This procedure walks through the steps to create and process a Buyer´s push to distribute products from one location to one or many stores.</span></span> <span data-ttu-id="dd406-105">O usuário pode definir várias configurações e fazer com que o sistema sugira como distribuir os produtos ou inserir manualmente onde os produtos serão distribuídos e a quantidade distribuída em cada loja.</span><span class="sxs-lookup"><span data-stu-id="dd406-105">The user can define multiple configurations and have the system suggest how to distribute the products, or manually enter where the products are distributed to and how much gets distributed to each store.</span></span> <span data-ttu-id="dd406-106">Este procedimento não inclui a instalação de dados que possam ser usados na compra centralizada, como regras de reabastecimento, hierarquias das organizações e pesos das lojas.</span><span class="sxs-lookup"><span data-stu-id="dd406-106">This procedure doesn't include setup of data that can be used in the Buyer´s push, such as replenishment rules, organizational hierarchies, and store weights.</span></span> <span data-ttu-id="dd406-107">Este procedimento usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="dd406-107">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="dd406-108">Vá para Compra centralizada.</span><span class="sxs-lookup"><span data-stu-id="dd406-108">Go to Buyer's push.</span></span>
2. <span data-ttu-id="dd406-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="dd406-109">Click New.</span></span>
3. <span data-ttu-id="dd406-110">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="dd406-110">In the Description field, type a value.</span></span>
4. <span data-ttu-id="dd406-111">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="dd406-111">In the Site field, enter or select a value.</span></span>
5. <span data-ttu-id="dd406-112">No campo Depósito, insira ou selecione um depósito que tenha produtos com quantidades disponíveis.</span><span class="sxs-lookup"><span data-stu-id="dd406-112">In the Warehouse field, enter or select a warehouse that has products with on-hand quantities.</span></span>
6. <span data-ttu-id="dd406-113">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="dd406-113">Click Add.</span></span>
7. <span data-ttu-id="dd406-114">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="dd406-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="dd406-115">No campo Número do item, insira ou selecione um produto.</span><span class="sxs-lookup"><span data-stu-id="dd406-115">In the Item number field, enter or select a product.</span></span>
9. <span data-ttu-id="dd406-116">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="dd406-116">Click Add.</span></span>
10. <span data-ttu-id="dd406-117">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="dd406-117">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="dd406-118">No campo Número do item, insira ou selecione uma grade de produto.</span><span class="sxs-lookup"><span data-stu-id="dd406-118">In the Item number field, enter or select a variant product.</span></span>
    * <span data-ttu-id="dd406-119">Ao inserir uma grade de produto, serão criadas linhas para cada grade.</span><span class="sxs-lookup"><span data-stu-id="dd406-119">When entering a variant product, lines will be created for each variant.</span></span>  
12. <span data-ttu-id="dd406-120">Na lista, marque uma linha.</span><span class="sxs-lookup"><span data-stu-id="dd406-120">In the list, mark a row.</span></span>
13. <span data-ttu-id="dd406-121">No campo Quantidade de compra centralizada, digite a quantidade do produto selecionado que você deseja distribuir.</span><span class="sxs-lookup"><span data-stu-id="dd406-121">In the Pushed quantity field, type how many of the selected product you want to distribute.</span></span>
14. <span data-ttu-id="dd406-122">No campo Quantidade de compra centralizada adicional, insira a quantidade de produtos com quantidade disponível para serem distribuídos.</span><span class="sxs-lookup"><span data-stu-id="dd406-122">In the Additional quantity to push field, enter the quantity of the products that have available quantity to distribute.</span></span>
15. <span data-ttu-id="dd406-123">No campo Distribuição, insira 'Peso da localização'.</span><span class="sxs-lookup"><span data-stu-id="dd406-123">In the Distribution field, enter 'Location weight'.</span></span>
    * <span data-ttu-id="dd406-124">Você pode selecionar outros tipos para usar outras regras para a distribuição.</span><span class="sxs-lookup"><span data-stu-id="dd406-124">You can select the other types to use other rules for the distribution.</span></span>  
16. <span data-ttu-id="dd406-125">No campo Hierarquia de reabastecimento, selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="dd406-125">In the Replenishment hierarchy field, select a value.</span></span>
17. <span data-ttu-id="dd406-126">Selecione Sim no campo Respeitar classificações.</span><span class="sxs-lookup"><span data-stu-id="dd406-126">Select Yes in the Respect assortments field.</span></span>
18. <span data-ttu-id="dd406-127">Clique em Calcular quantidades e examine as quantidades que são adicionadas às linhas na seção Depósito.</span><span class="sxs-lookup"><span data-stu-id="dd406-127">Click Calculate quantities and review the quantities that are added to the rows in the Warehouse section.</span></span>
19. <span data-ttu-id="dd406-128">Clique em Criar ordem.</span><span class="sxs-lookup"><span data-stu-id="dd406-128">Click Create order.</span></span>
20. <span data-ttu-id="dd406-129">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="dd406-129">Click Yes.</span></span>


