--- 
title: "Configurar definição de preços com base no atributo para os produtos configuráveis"
description: "Este procedimento mostra como configurar preços baseados em atributos."
author: YuyuScheller
manager: AnnBe
ms.date: 10/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 6dd2aa1ebc713287120106a9d1ec7dc15c24def9
ms.openlocfilehash: 88402bef6fd5dad38a74795cd31a4046085d6db7
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2017

---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a><span data-ttu-id="3aa89-103">Configurar definição de preços com base no atributo para os produtos configuráveis</span><span class="sxs-lookup"><span data-stu-id="3aa89-103">Set up attribute-based pricing for configurable products</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3aa89-104">Este procedimento mostra como configurar preços baseados em atributos.</span><span class="sxs-lookup"><span data-stu-id="3aa89-104">This procedure shows how to set up attribute-based pricing.</span></span> <span data-ttu-id="3aa89-105">Como pré-requisito, você deve ter um modelo de configuração de produto com um ou vários componentes e atributos.</span><span class="sxs-lookup"><span data-stu-id="3aa89-105">As a prerequisite, you must have a product configuration model that has one or more components and attributes.</span></span> <span data-ttu-id="3aa89-106">Este exemplo usa o modelo de produto do Palestrante de avançado na empresa de dados demo USMF.</span><span class="sxs-lookup"><span data-stu-id="3aa89-106">This example uses the High End Speaker product model in the USMF demo data company.</span></span> <span data-ttu-id="3aa89-107">Normalmente, um gerente de produto usa este procedimento.</span><span class="sxs-lookup"><span data-stu-id="3aa89-107">Typically, a product manager uses this procedure.</span></span>


## <a name="create-a-new-price-model"></a><span data-ttu-id="3aa89-108">Criar um novo modelo de preço</span><span class="sxs-lookup"><span data-stu-id="3aa89-108">Create a new price model</span></span>
1. <span data-ttu-id="3aa89-109">Clique em Definição de modelo de variante de produto.</span><span class="sxs-lookup"><span data-stu-id="3aa89-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="3aa89-110">Clique em Modelos de configuração do produto.</span><span class="sxs-lookup"><span data-stu-id="3aa89-110">Click Product configuration models.</span></span>
3. <span data-ttu-id="3aa89-111">Na lista, selecione a linha do Palestrante avançado, mas não clique no link do nome.</span><span class="sxs-lookup"><span data-stu-id="3aa89-111">In the list, select the High End Speaker line, but don’t click the link for the name.</span></span>
4. <span data-ttu-id="3aa89-112">No Painel de Ação, clique em Modelo.</span><span class="sxs-lookup"><span data-stu-id="3aa89-112">On the Action Pane, click Model.</span></span>
5. <span data-ttu-id="3aa89-113">Clique em Modelos de preço.</span><span class="sxs-lookup"><span data-stu-id="3aa89-113">Click Price models.</span></span>
6. <span data-ttu-id="3aa89-114">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="3aa89-114">Click New.</span></span>
7. <span data-ttu-id="3aa89-115">No campo Nome do modelo de preço, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="3aa89-115">In the Price model name field, type a value.</span></span>
    * <span data-ttu-id="3aa89-116">Use um nome que torne o modelo de fácil identificação.</span><span class="sxs-lookup"><span data-stu-id="3aa89-116">Use a name that makes the model easy to identify.</span></span>  
8. <span data-ttu-id="3aa89-117">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="3aa89-117">In the Description field, type a value.</span></span>
9. <span data-ttu-id="3aa89-118">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="3aa89-118">Click Save.</span></span>

## <a name="add-price-elements"></a><span data-ttu-id="3aa89-119">Adicionar Elementos de preço</span><span class="sxs-lookup"><span data-stu-id="3aa89-119">Add price elements</span></span>
1. <span data-ttu-id="3aa89-120">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="3aa89-120">Click Edit.</span></span>
    * <span data-ttu-id="3aa89-121">Cada componente em um modelo de produto pode ter um elemento de preço base e qualquer quantidade de regras de expressão de preço.</span><span class="sxs-lookup"><span data-stu-id="3aa89-121">Each component in a product model can have a base price element and any number of price expression rules.</span></span> <span data-ttu-id="3aa89-122">Você também pode adicionar os preços em moedas diferentes.</span><span class="sxs-lookup"><span data-stu-id="3aa89-122">You can also add prices in different currencies.</span></span>  
2. <span data-ttu-id="3aa89-123">No campo Expressão de preço base, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="3aa89-123">In the Base price expression field, type a value.</span></span>
    * <span data-ttu-id="3aa89-124">Por exemplo, digite 100.</span><span class="sxs-lookup"><span data-stu-id="3aa89-124">For example, type 100.</span></span>   <span data-ttu-id="3aa89-125">Uma expressão do preço base pode ser um valor numérico, ou pode consistir em um cálculo aritmético que envolve um ou mais atributos.</span><span class="sxs-lookup"><span data-stu-id="3aa89-125">A base price expression can be a numerical value, or it can consist of an arithmetic calculation that involves one or more attributes.</span></span>  
3. <span data-ttu-id="3aa89-126">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="3aa89-126">Click Add.</span></span>
4. <span data-ttu-id="3aa89-127">No campo Nome, digite ‘Rosewood’.</span><span class="sxs-lookup"><span data-stu-id="3aa89-127">In the Name field, type ‘Rosewood’.</span></span>
    * <span data-ttu-id="3aa89-128">O nome de expressão de preço ajuda a identificar qual elemento de preço representa.</span><span class="sxs-lookup"><span data-stu-id="3aa89-128">The price expression name helps identify what the price element represents.</span></span> <span data-ttu-id="3aa89-129">Neste exemplo, estamos criando um elemento de preço para a opção de término do gabinete do Palestrante Rosewood.</span><span class="sxs-lookup"><span data-stu-id="3aa89-129">In this example, we are creating a price element for the Rosewood speaker cabinet finish option.</span></span>  
5. <span data-ttu-id="3aa89-130">Clique em Editar condição.</span><span class="sxs-lookup"><span data-stu-id="3aa89-130">Click Edit condition.</span></span>
    * <span data-ttu-id="3aa89-131">Uma condição de preço ajuda a garantir que um elemento de expressão de preço seja incluído no preço de vendas apenas se uma combinação específica de atributos estiver presente.</span><span class="sxs-lookup"><span data-stu-id="3aa89-131">A price condition helps guarantee that a price expression element is included in the sales price only if a specific combination of attributes is present.</span></span>  
6. <span data-ttu-id="3aa89-132">No campo de ConstraintBody, insira 'CabinetFinish=="Rosewood"'.</span><span class="sxs-lookup"><span data-stu-id="3aa89-132">In the ConstraintBody field, enter 'CabinetFinish=="Rosewood"'.</span></span>
7. <span data-ttu-id="3aa89-133">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="3aa89-133">Click OK.</span></span>
8. <span data-ttu-id="3aa89-134">No campo Expressão, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="3aa89-134">In the Expression field, type a value.</span></span>
    * <span data-ttu-id="3aa89-135">Por exemplo, digite 50.</span><span class="sxs-lookup"><span data-stu-id="3aa89-135">For example, type 50.</span></span>  
9. <span data-ttu-id="3aa89-136">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="3aa89-136">Close the page.</span></span>
10. <span data-ttu-id="3aa89-137">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="3aa89-137">Close the page.</span></span>


