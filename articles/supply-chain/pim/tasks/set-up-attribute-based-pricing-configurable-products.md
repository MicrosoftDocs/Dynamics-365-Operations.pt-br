---
title: Configurar definição de preços com base no atributo para os produtos configuráveis
description: Este tópico explica como configurar preços baseados em atributos.
author: ShylaThompson
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0c30c520e7265c2676937f5191844f6789c364e6
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921232"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a><span data-ttu-id="29464-103">Configurar definição de preços com base no atributo para os produtos configuráveis</span><span class="sxs-lookup"><span data-stu-id="29464-103">Set up attribute-based pricing for configurable products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="29464-104">Este tópico explica como configurar preços baseados em atributos.</span><span class="sxs-lookup"><span data-stu-id="29464-104">This topic explains how to set up attribute-based pricing.</span></span> <span data-ttu-id="29464-105">Como pré-requisito, você deve ter um modelo de configuração de produto com um ou vários componentes e atributos.</span><span class="sxs-lookup"><span data-stu-id="29464-105">As a prerequisite, you must have a product configuration model that has one or more components and attributes.</span></span> <span data-ttu-id="29464-106">Este exemplo usa o modelo de produto do Palestrante de avançado na empresa de dados demo USMF.</span><span class="sxs-lookup"><span data-stu-id="29464-106">This example uses the High End Speaker product model in the USMF demo data company.</span></span> <span data-ttu-id="29464-107">Normalmente, um gerente de produto usa este procedimento.</span><span class="sxs-lookup"><span data-stu-id="29464-107">Typically, a product manager uses this procedure.</span></span>


## <a name="create-a-new-price-model"></a><span data-ttu-id="29464-108">Criar um novo modelo de preço</span><span class="sxs-lookup"><span data-stu-id="29464-108">Create a new price model</span></span>

1. <span data-ttu-id="29464-109">Vá para **Gerenciamento de informações do produto \> Produtos \> Modelos de configuração do produto**.</span><span class="sxs-lookup"><span data-stu-id="29464-109">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="29464-110">Na lista, selecione a linha do **Palestrante avançado**, mas não selecione o link do nome.</span><span class="sxs-lookup"><span data-stu-id="29464-110">In the list, select the **High End Speaker** line, but don't select the link for the name.</span></span>
1. <span data-ttu-id="29464-111">No Painel de Ação, selecione **Modelo**.</span><span class="sxs-lookup"><span data-stu-id="29464-111">On the Action Pane, select **Model**.</span></span>
1. <span data-ttu-id="29464-112">Selecione **Modelos de preço**.</span><span class="sxs-lookup"><span data-stu-id="29464-112">Select **Price models**.</span></span>
1. <span data-ttu-id="29464-113">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="29464-113">Select **New**.</span></span>
1. <span data-ttu-id="29464-114">No campo **Nome do modelo de preço**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="29464-114">In the **Price model name** field, type a value.</span></span> <span data-ttu-id="29464-115">Use um nome que torne o modelo de fácil identificação.</span><span class="sxs-lookup"><span data-stu-id="29464-115">Use a name that makes the model easy to identify.</span></span>  
1. <span data-ttu-id="29464-116">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="29464-116">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="29464-117">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="29464-117">Select **Save**.</span></span>

## <a name="add-price-elements"></a><span data-ttu-id="29464-118">Adicionar Elementos de preço</span><span class="sxs-lookup"><span data-stu-id="29464-118">Add price elements</span></span>

1. <span data-ttu-id="29464-119">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="29464-119">Select **Edit**.</span></span> <span data-ttu-id="29464-120">Cada componente em um modelo de produto pode ter um elemento de preço base e qualquer quantidade de regras de expressão de preço.</span><span class="sxs-lookup"><span data-stu-id="29464-120">Each component in a product model can have a base price element and any number of price expression rules.</span></span> <span data-ttu-id="29464-121">Você também pode adicionar os preços em moedas diferentes.</span><span class="sxs-lookup"><span data-stu-id="29464-121">You can also add prices in different currencies.</span></span>  
2. <span data-ttu-id="29464-122">No campo **Expressão de preço base**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="29464-122">In the **Base price expression** field, type a value.</span></span> <span data-ttu-id="29464-123">Por exemplo, digite 100.</span><span class="sxs-lookup"><span data-stu-id="29464-123">For example, type 100.</span></span> <span data-ttu-id="29464-124">Uma expressão do preço base pode ser um valor numérico, ou pode consistir em um cálculo aritmético que envolve um ou mais atributos.</span><span class="sxs-lookup"><span data-stu-id="29464-124">A base price expression can be a numerical value, or it can consist of an arithmetic calculation that involves one or more attributes.</span></span>  
3. <span data-ttu-id="29464-125">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="29464-125">Select **Add**.</span></span>
4. <span data-ttu-id="29464-126">No campo **Nome**, digite `Rosewood`.</span><span class="sxs-lookup"><span data-stu-id="29464-126">In the **Name** field, type `Rosewood`.</span></span> <span data-ttu-id="29464-127">O nome de expressão de preço ajuda a identificar qual elemento de preço representa.</span><span class="sxs-lookup"><span data-stu-id="29464-127">The price expression name helps identify what the price element represents.</span></span> <span data-ttu-id="29464-128">Neste exemplo, estamos criando um elemento de preço para a opção de término do gabinete do Palestrante Rosewood.</span><span class="sxs-lookup"><span data-stu-id="29464-128">In this example, we are creating a price element for the Rosewood speaker cabinet finish option.</span></span>  
5. <span data-ttu-id="29464-129">Selecione **Editar condição**.</span><span class="sxs-lookup"><span data-stu-id="29464-129">Select **Edit condition**.</span></span> <span data-ttu-id="29464-130">Uma condição de preço ajuda a garantir que um elemento de expressão de preço seja incluído no preço de vendas apenas se uma combinação específica de atributos estiver presente.</span><span class="sxs-lookup"><span data-stu-id="29464-130">A price condition helps guarantee that a price expression element is included in the sales price only if a specific combination of attributes is present.</span></span>  
6. <span data-ttu-id="29464-131">No campo **ConstraintBody**, insira `CabinetFinish=="Rosewood"`.</span><span class="sxs-lookup"><span data-stu-id="29464-131">In the **ConstraintBody** field, enter `CabinetFinish=="Rosewood"`.</span></span>
7. <span data-ttu-id="29464-132">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="29464-132">Select **OK**.</span></span>
8. <span data-ttu-id="29464-133">No campo **Expressão**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="29464-133">In the **Expression** field, type a value.</span></span> <span data-ttu-id="29464-134">Por exemplo, digite `50`.</span><span class="sxs-lookup"><span data-stu-id="29464-134">For example, type `50`.</span></span> 
9. <span data-ttu-id="29464-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="29464-135">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]