---
title: Configurar definição de preços com base no atributo para os produtos configuráveis
description: Este procedimento mostra como configurar preços baseados em atributos.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba84fa4de660d16b266763fff5b0b794ed327c81
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844192"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a><span data-ttu-id="9c059-103">Configurar definição de preços com base no atributo para os produtos configuráveis</span><span class="sxs-lookup"><span data-stu-id="9c059-103">Set up attribute-based pricing for configurable products</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9c059-104">Este procedimento mostra como configurar preços baseados em atributos.</span><span class="sxs-lookup"><span data-stu-id="9c059-104">This procedure shows how to set up attribute-based pricing.</span></span> <span data-ttu-id="9c059-105">Como pré-requisito, você deve ter um modelo de configuração de produto com um ou vários componentes e atributos.</span><span class="sxs-lookup"><span data-stu-id="9c059-105">As a prerequisite, you must have a product configuration model that has one or more components and attributes.</span></span> <span data-ttu-id="9c059-106">Este exemplo usa o modelo de produto do Palestrante de avançado na empresa de dados demo USMF.</span><span class="sxs-lookup"><span data-stu-id="9c059-106">This example uses the High End Speaker product model in the USMF demo data company.</span></span> <span data-ttu-id="9c059-107">Normalmente, um gerente de produto usa este procedimento.</span><span class="sxs-lookup"><span data-stu-id="9c059-107">Typically, a product manager uses this procedure.</span></span>


## <a name="create-a-new-price-model"></a><span data-ttu-id="9c059-108">Criar um novo modelo de preço</span><span class="sxs-lookup"><span data-stu-id="9c059-108">Create a new price model</span></span>
1. <span data-ttu-id="9c059-109">Clique em Definição de modelo de variante de produto.</span><span class="sxs-lookup"><span data-stu-id="9c059-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="9c059-110">Clique em Modelos de configuração do produto.</span><span class="sxs-lookup"><span data-stu-id="9c059-110">Click Product configuration models.</span></span>
3. <span data-ttu-id="9c059-111">Na lista, selecione a linha do Palestrante avançado, mas não clique no link do nome.</span><span class="sxs-lookup"><span data-stu-id="9c059-111">In the list, select the High End Speaker line, but don’t click the link for the name.</span></span>
4. <span data-ttu-id="9c059-112">No Painel de Ação, clique em Modelo.</span><span class="sxs-lookup"><span data-stu-id="9c059-112">On the Action Pane, click Model.</span></span>
5. <span data-ttu-id="9c059-113">Clique em Modelos de preço.</span><span class="sxs-lookup"><span data-stu-id="9c059-113">Click Price models.</span></span>
6. <span data-ttu-id="9c059-114">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="9c059-114">Click New.</span></span>
7. <span data-ttu-id="9c059-115">No campo Nome do modelo de preço, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9c059-115">In the Price model name field, type a value.</span></span>
    * <span data-ttu-id="9c059-116">Use um nome que torne o modelo de fácil identificação.</span><span class="sxs-lookup"><span data-stu-id="9c059-116">Use a name that makes the model easy to identify.</span></span>  
8. <span data-ttu-id="9c059-117">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9c059-117">In the Description field, type a value.</span></span>
9. <span data-ttu-id="9c059-118">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="9c059-118">Click Save.</span></span>

## <a name="add-price-elements"></a><span data-ttu-id="9c059-119">Adicionar Elementos de preço</span><span class="sxs-lookup"><span data-stu-id="9c059-119">Add price elements</span></span>
1. <span data-ttu-id="9c059-120">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="9c059-120">Click Edit.</span></span>
    * <span data-ttu-id="9c059-121">Cada componente em um modelo de produto pode ter um elemento de preço base e qualquer quantidade de regras de expressão de preço.</span><span class="sxs-lookup"><span data-stu-id="9c059-121">Each component in a product model can have a base price element and any number of price expression rules.</span></span> <span data-ttu-id="9c059-122">Você também pode adicionar os preços em moedas diferentes.</span><span class="sxs-lookup"><span data-stu-id="9c059-122">You can also add prices in different currencies.</span></span>  
2. <span data-ttu-id="9c059-123">No campo Expressão de preço base, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9c059-123">In the Base price expression field, type a value.</span></span>
    * <span data-ttu-id="9c059-124">Por exemplo, digite 100.</span><span class="sxs-lookup"><span data-stu-id="9c059-124">For example, type 100.</span></span>   <span data-ttu-id="9c059-125">Uma expressão do preço base pode ser um valor numérico, ou pode consistir em um cálculo aritmético que envolve um ou mais atributos.</span><span class="sxs-lookup"><span data-stu-id="9c059-125">A base price expression can be a numerical value, or it can consist of an arithmetic calculation that involves one or more attributes.</span></span>  
3. <span data-ttu-id="9c059-126">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="9c059-126">Click Add.</span></span>
4. <span data-ttu-id="9c059-127">No campo Nome, digite ‘Rosewood’.</span><span class="sxs-lookup"><span data-stu-id="9c059-127">In the Name field, type ‘Rosewood’.</span></span>
    * <span data-ttu-id="9c059-128">O nome de expressão de preço ajuda a identificar qual elemento de preço representa.</span><span class="sxs-lookup"><span data-stu-id="9c059-128">The price expression name helps identify what the price element represents.</span></span> <span data-ttu-id="9c059-129">Neste exemplo, estamos criando um elemento de preço para a opção de término do gabinete do Palestrante Rosewood.</span><span class="sxs-lookup"><span data-stu-id="9c059-129">In this example, we are creating a price element for the Rosewood speaker cabinet finish option.</span></span>  
5. <span data-ttu-id="9c059-130">Clique em Editar condição.</span><span class="sxs-lookup"><span data-stu-id="9c059-130">Click Edit condition.</span></span>
    * <span data-ttu-id="9c059-131">Uma condição de preço ajuda a garantir que um elemento de expressão de preço seja incluído no preço de vendas apenas se uma combinação específica de atributos estiver presente.</span><span class="sxs-lookup"><span data-stu-id="9c059-131">A price condition helps guarantee that a price expression element is included in the sales price only if a specific combination of attributes is present.</span></span>  
6. <span data-ttu-id="9c059-132">No campo de ConstraintBody, insira 'CabinetFinish=="Rosewood"'.</span><span class="sxs-lookup"><span data-stu-id="9c059-132">In the ConstraintBody field, enter 'CabinetFinish=="Rosewood"'.</span></span>
7. <span data-ttu-id="9c059-133">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="9c059-133">Click OK.</span></span>
8. <span data-ttu-id="9c059-134">No campo Expressão, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9c059-134">In the Expression field, type a value.</span></span>
    * <span data-ttu-id="9c059-135">Por exemplo, digite 50.</span><span class="sxs-lookup"><span data-stu-id="9c059-135">For example, type 50.</span></span>  
9. <span data-ttu-id="9c059-136">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9c059-136">Close the page.</span></span>
10. <span data-ttu-id="9c059-137">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9c059-137">Close the page.</span></span>

