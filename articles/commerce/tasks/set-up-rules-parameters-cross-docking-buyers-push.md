---
title: Configurar regras e parâmetros para a distribuição integrada e a compra centralizada
description: Este procedimento demonstra as etapas para criar regras de reabastecimento.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailReplenishmentRuleTable, RetailReplenishmentTreeLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9bccd92946783628dce37c3fd018e4dd927efd49
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141122"
---
# <a name="set-up-rules-and-parameters-for-cross-docking-and-buyers-push"></a><span data-ttu-id="ea2a5-103">Configurar regras e parâmetros para a distribuição integrada e a compra centralizada</span><span class="sxs-lookup"><span data-stu-id="ea2a5-103">Set up rules and parameters for cross docking and buyer's push</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ea2a5-104">Este procedimento demonstra as etapas para criar regras de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-104">This procedure demonstrates the steps to create Replenishment rules.</span></span> <span data-ttu-id="ea2a5-105">As regras de reabastecimento podem ser usadas para controlar como os produtos são distribuídos para as lojas ao usar a distribuição integrada e a compra centralizada.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-105">Replenishment rules can be used to control how products are distributed to stores when using Cross-docking and Buyer´s push.</span></span> <span data-ttu-id="ea2a5-106">As regras de reabastecimento podem ser configuradas para lojas ou grupos de lojas.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-106">Replenishment rules can be set up for stores or store groups.</span></span> <span data-ttu-id="ea2a5-107">O peso definido para cada linha em uma regra controlará como as quantidades de produtos serão distribuídas entre as lojas ao usar regras de reabastecimento como o método de distribuição em distribuições integradas ou compras centralizadas.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-107">The weight defined for each line in a rule will control how the quantities of products will get distributed between the stores when using Replenishment rules as the distribution method in Cross-docking or Buyer´s push.</span></span> <span data-ttu-id="ea2a5-108">Este procedimento usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-108">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="ea2a5-109">Vá para Regras de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-109">Go to Replenishment rules.</span></span>
2. <span data-ttu-id="ea2a5-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-110">Click New.</span></span>
3. <span data-ttu-id="ea2a5-111">No campo Regra de reabastecimento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-111">In the Replenishment rule field, type a value.</span></span>
4. <span data-ttu-id="ea2a5-112">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="ea2a5-113">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-113">Click Save.</span></span>
6. <span data-ttu-id="ea2a5-114">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-114">Click Add.</span></span>
7. <span data-ttu-id="ea2a5-115">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="ea2a5-116">Você pode escolher Hierarquia de reabastecimento ou Canal para o tipo.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-116">You can choose Replenishment hierarchy or Channel for the type.</span></span> <span data-ttu-id="ea2a5-117">O valor controla se a seleção em Nome será uma hierarquia de canais ou um canal específico.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-117">The value controls whether the selection in Name will be a hierarchy of channels or a specific channel.</span></span>  <span data-ttu-id="ea2a5-118">Neste exemplo, deixe-o definido como uma hierarquia de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-118">For this example, leave it set as Replenishment hierarchy.</span></span>  
8. <span data-ttu-id="ea2a5-119">No campo Nome, selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-119">In the Name field, select a value.</span></span>
    * <span data-ttu-id="ea2a5-120">O valor padrão do peso é preenchido a partir do peso definido no depósito.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-120">The default weight value is populated from the weight defined on the warehouse.</span></span>  <span data-ttu-id="ea2a5-121">Esse peso pode ser usado para a regra de reabastecimento ou você pode inserir um novo peso no campo Peso.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-121">This weight can be used for the Replenishment rule or you can enter a new weight in the Weight field.</span></span>  
9. <span data-ttu-id="ea2a5-122">No campo Peso, insira um número.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-122">In the Weight field, enter a number.</span></span>
10. <span data-ttu-id="ea2a5-123">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-123">Click Add.</span></span>
11. <span data-ttu-id="ea2a5-124">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-124">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="ea2a5-125">No campo Tipo, selecione 'Canal'.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-125">In the Type field, select 'Channel'.</span></span>
13. <span data-ttu-id="ea2a5-126">No campo Nome, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-126">In the Name field, enter or select a value.</span></span>
14. <span data-ttu-id="ea2a5-127">No campo Peso, insira um número.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-127">In the Weight field, enter a number.</span></span>
15. <span data-ttu-id="ea2a5-128">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="ea2a5-128">Click Save.</span></span>

