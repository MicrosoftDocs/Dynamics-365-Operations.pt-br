--- 
title: " Configurar regras e parâmetros para a distribuição integrada e a compra centralizada"
description: Este procedimento demonstra as etapas para criar regras de reabastecimento.
author: josaw1
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 1ff41a18be066b6f32c5172bda38c389e7f34128
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-rules-and-parameters-for-cross-docking-and-buyers-push"></a><span data-ttu-id="650f4-103"> Configurar regras e parâmetros para a distribuição integrada e a compra centralizada</span><span class="sxs-lookup"><span data-stu-id="650f4-103">Set up rules and parameters for cross docking and buyer's push</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="650f4-104">Este procedimento demonstra as etapas para criar regras de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="650f4-104">This procedure demonstrates the steps to create Replenishment rules.</span></span> <span data-ttu-id="650f4-105">As regras de reabastecimento podem ser usadas para controlar como os produtos são distribuídos para as lojas ao usar a distribuição integrada e a compra centralizada.</span><span class="sxs-lookup"><span data-stu-id="650f4-105">Replenishment rules can be used to control how products are distributed to stores when using Cross-docking and Buyer´s push.</span></span> <span data-ttu-id="650f4-106">As regras de reabastecimento podem ser configuradas para lojas ou grupos de lojas.</span><span class="sxs-lookup"><span data-stu-id="650f4-106">Replenishment rules can be set up for stores or store groups.</span></span> <span data-ttu-id="650f4-107">O peso definido para cada linha em uma regra controlará como as quantidades de produtos serão distribuídas entre as lojas ao usar regras de reabastecimento como o método de distribuição em distribuições integradas ou compras centralizadas.</span><span class="sxs-lookup"><span data-stu-id="650f4-107">The weight defined for each line in a rule will control how the quantities of products will get distributed between the stores when using Replenishment rules as the distribution method in Cross-docking or Buyer´s push.</span></span> <span data-ttu-id="650f4-108">Este procedimento usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="650f4-108">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="650f4-109">Vá para Regras de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="650f4-109">Go to Replenishment rules.</span></span>
2. <span data-ttu-id="650f4-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="650f4-110">Click New.</span></span>
3. <span data-ttu-id="650f4-111">No campo Regra de reabastecimento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="650f4-111">In the Replenishment rule field, type a value.</span></span>
4. <span data-ttu-id="650f4-112">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="650f4-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="650f4-113">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="650f4-113">Click Save.</span></span>
6. <span data-ttu-id="650f4-114">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="650f4-114">Click Add.</span></span>
7. <span data-ttu-id="650f4-115">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="650f4-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="650f4-116">Você pode escolher Hierarquia de reabastecimento ou Canal para o tipo.</span><span class="sxs-lookup"><span data-stu-id="650f4-116">You can choose Replenishment hierarchy or Channel for the type.</span></span> <span data-ttu-id="650f4-117">O valor controla se a seleção em Nome será uma hierarquia de canais ou um canal específico.</span><span class="sxs-lookup"><span data-stu-id="650f4-117">The value controls whether the selection in Name will be a hierarchy of channels or a specific channel.</span></span>  <span data-ttu-id="650f4-118">Neste exemplo, deixe-o definido como uma hierarquia de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="650f4-118">For this example, leave it set as Replenishment hierarchy.</span></span>  
8. <span data-ttu-id="650f4-119">No campo Nome, selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="650f4-119">In the Name field, select a value.</span></span>
    * <span data-ttu-id="650f4-120">O valor padrão do peso é preenchido a partir do peso definido no depósito.</span><span class="sxs-lookup"><span data-stu-id="650f4-120">The default weight value is populated from the weight defined on the warehouse.</span></span>  <span data-ttu-id="650f4-121">Esse peso pode ser usado para a regra de reabastecimento ou você pode inserir um novo peso no campo Peso.</span><span class="sxs-lookup"><span data-stu-id="650f4-121">This weight can be used for the Replenishment rule or you can enter a new weight in the Weight field.</span></span>  
9. <span data-ttu-id="650f4-122">No campo Peso, insira um número.</span><span class="sxs-lookup"><span data-stu-id="650f4-122">In the Weight field, enter a number.</span></span>
10. <span data-ttu-id="650f4-123">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="650f4-123">Click Add.</span></span>
11. <span data-ttu-id="650f4-124">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="650f4-124">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="650f4-125">No campo Tipo, selecione 'Canal'.</span><span class="sxs-lookup"><span data-stu-id="650f4-125">In the Type field, select 'Channel'.</span></span>
13. <span data-ttu-id="650f4-126">No campo Nome, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="650f4-126">In the Name field, enter or select a value.</span></span>
14. <span data-ttu-id="650f4-127">No campo Peso, insira um número.</span><span class="sxs-lookup"><span data-stu-id="650f4-127">In the Weight field, enter a number.</span></span>
15. <span data-ttu-id="650f4-128">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="650f4-128">Click Save.</span></span>


