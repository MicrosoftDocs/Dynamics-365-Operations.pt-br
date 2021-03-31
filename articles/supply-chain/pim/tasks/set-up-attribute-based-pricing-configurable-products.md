---
title: Configurar definição de preços com base no atributo para os produtos configuráveis
description: Este tópico explica como configurar preços baseados em atributos.
author: ShylaThompson
manager: tfehr
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e540e0f25afa65e84cdb11fb0c56437b72891f9f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5220743"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a><span data-ttu-id="61a60-103">Configurar definição de preços com base no atributo para os produtos configuráveis</span><span class="sxs-lookup"><span data-stu-id="61a60-103">Set up attribute-based pricing for configurable products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="61a60-104">Este tópico explica como configurar preços baseados em atributos.</span><span class="sxs-lookup"><span data-stu-id="61a60-104">This topic explains how to set up attribute-based pricing.</span></span> <span data-ttu-id="61a60-105">Como pré-requisito, você deve ter um modelo de configuração de produto com um ou vários componentes e atributos.</span><span class="sxs-lookup"><span data-stu-id="61a60-105">As a prerequisite, you must have a product configuration model that has one or more components and attributes.</span></span> <span data-ttu-id="61a60-106">Este exemplo usa o modelo de produto do Palestrante de avançado na empresa de dados demo USMF.</span><span class="sxs-lookup"><span data-stu-id="61a60-106">This example uses the High End Speaker product model in the USMF demo data company.</span></span> <span data-ttu-id="61a60-107">Normalmente, um gerente de produto usa este procedimento.</span><span class="sxs-lookup"><span data-stu-id="61a60-107">Typically, a product manager uses this procedure.</span></span>


## <a name="create-a-new-price-model"></a><span data-ttu-id="61a60-108">Criar um novo modelo de preço</span><span class="sxs-lookup"><span data-stu-id="61a60-108">Create a new price model</span></span>
1. <span data-ttu-id="61a60-109">Selecione **Definição de modelo de variante de produto** na página inicial.</span><span class="sxs-lookup"><span data-stu-id="61a60-109">Select **Product variant model definition** on the home page.</span></span>
2. <span data-ttu-id="61a60-110">Selecione **Configurar modelos de produtos** na seção **links**.</span><span class="sxs-lookup"><span data-stu-id="61a60-110">Select **Product configuration models** in the **links** section.</span></span>
3. <span data-ttu-id="61a60-111">Na lista, selecione a linha do **Palestrante avançado**, mas não selecione o link do nome.</span><span class="sxs-lookup"><span data-stu-id="61a60-111">In the list, select the **High End Speaker** line, but don't select the link for the name.</span></span>
4. <span data-ttu-id="61a60-112">No Painel de Ação, selecione **Modelo**.</span><span class="sxs-lookup"><span data-stu-id="61a60-112">On the Action Pane, select **Model**.</span></span>
5. <span data-ttu-id="61a60-113">Selecione **Modelos de preço**.</span><span class="sxs-lookup"><span data-stu-id="61a60-113">Select **Price models**.</span></span>
6. <span data-ttu-id="61a60-114">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="61a60-114">Select **New**.</span></span>
7. <span data-ttu-id="61a60-115">No campo **Nome do modelo de preço**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="61a60-115">In the **Price model name** field, type a value.</span></span> <span data-ttu-id="61a60-116">Use um nome que torne o modelo de fácil identificação.</span><span class="sxs-lookup"><span data-stu-id="61a60-116">Use a name that makes the model easy to identify.</span></span>  
8. <span data-ttu-id="61a60-117">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="61a60-117">In the **Description** field, type a value.</span></span>
9. <span data-ttu-id="61a60-118">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="61a60-118">Select **Save**.</span></span>

## <a name="add-price-elements"></a><span data-ttu-id="61a60-119">Adicionar Elementos de preço</span><span class="sxs-lookup"><span data-stu-id="61a60-119">Add price elements</span></span>
1. <span data-ttu-id="61a60-120">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="61a60-120">Select **Edit**.</span></span> <span data-ttu-id="61a60-121">Cada componente em um modelo de produto pode ter um elemento de preço base e qualquer quantidade de regras de expressão de preço.</span><span class="sxs-lookup"><span data-stu-id="61a60-121">Each component in a product model can have a base price element and any number of price expression rules.</span></span> <span data-ttu-id="61a60-122">Você também pode adicionar os preços em moedas diferentes.</span><span class="sxs-lookup"><span data-stu-id="61a60-122">You can also add prices in different currencies.</span></span>  
2. <span data-ttu-id="61a60-123">No campo **Expressão de preço base**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="61a60-123">In the **Base price expression** field, type a value.</span></span> <span data-ttu-id="61a60-124">Por exemplo, digite 100.</span><span class="sxs-lookup"><span data-stu-id="61a60-124">For example, type 100.</span></span> <span data-ttu-id="61a60-125">Uma expressão do preço base pode ser um valor numérico, ou pode consistir em um cálculo aritmético que envolve um ou mais atributos.</span><span class="sxs-lookup"><span data-stu-id="61a60-125">A base price expression can be a numerical value, or it can consist of an arithmetic calculation that involves one or more attributes.</span></span>  
3. <span data-ttu-id="61a60-126">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="61a60-126">Select **Add**.</span></span>
4. <span data-ttu-id="61a60-127">No campo **Nome**, digite `Rosewood`.</span><span class="sxs-lookup"><span data-stu-id="61a60-127">In the **Name** field, type `Rosewood`.</span></span> <span data-ttu-id="61a60-128">O nome de expressão de preço ajuda a identificar qual elemento de preço representa.</span><span class="sxs-lookup"><span data-stu-id="61a60-128">The price expression name helps identify what the price element represents.</span></span> <span data-ttu-id="61a60-129">Neste exemplo, estamos criando um elemento de preço para a opção de término do gabinete do Palestrante Rosewood.</span><span class="sxs-lookup"><span data-stu-id="61a60-129">In this example, we are creating a price element for the Rosewood speaker cabinet finish option.</span></span>  
5. <span data-ttu-id="61a60-130">Selecione **Editar condição**.</span><span class="sxs-lookup"><span data-stu-id="61a60-130">Select **Edit condition**.</span></span> <span data-ttu-id="61a60-131">Uma condição de preço ajuda a garantir que um elemento de expressão de preço seja incluído no preço de vendas apenas se uma combinação específica de atributos estiver presente.</span><span class="sxs-lookup"><span data-stu-id="61a60-131">A price condition helps guarantee that a price expression element is included in the sales price only if a specific combination of attributes is present.</span></span>  
6. <span data-ttu-id="61a60-132">No campo **ConstraintBody**, insira `CabinetFinish=="Rosewood"`.</span><span class="sxs-lookup"><span data-stu-id="61a60-132">In the **ConstraintBody** field, enter `CabinetFinish=="Rosewood"`.</span></span>
7. <span data-ttu-id="61a60-133">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="61a60-133">Select **OK**.</span></span>
8. <span data-ttu-id="61a60-134">No campo **Expressão**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="61a60-134">In the **Expression** field, type a value.</span></span> <span data-ttu-id="61a60-135">Por exemplo, digite `50`.</span><span class="sxs-lookup"><span data-stu-id="61a60-135">For example, type `50`.</span></span> 
9. <span data-ttu-id="61a60-136">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="61a60-136">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]