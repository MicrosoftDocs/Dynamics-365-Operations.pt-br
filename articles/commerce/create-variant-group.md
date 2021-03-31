---
title: Criar um grupo de grades
description: Este tópico descreve como criar um grupo de grades de tamanho, estilo ou cor para um produto do Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: RetailSizeGroupTable, ConfigGroupIdLookup, RetailStyleGroupTable
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 4c34aca043f10fef38f186800c429cac36c41ce7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207838"
---
# <a name="create-a-variant-group"></a><span data-ttu-id="8d1e3-103">Criar um grupo de grades</span><span class="sxs-lookup"><span data-stu-id="8d1e3-103">Create a variant group</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="8d1e3-104">Este tópico descreve como criar um grupo de grades de tamanho, estilo ou cor para um produto do Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8d1e3-104">This topic describes how to create a size, style, or color variant group for a product in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="8d1e3-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="8d1e3-105">Overview</span></span>

<span data-ttu-id="8d1e3-106">O Dynamics 365 Commerce oferece suporte a várias grades para produtos.</span><span class="sxs-lookup"><span data-stu-id="8d1e3-106">Dynamics 365 Commerce supports multiple variants for products.</span></span> <span data-ttu-id="8d1e3-107">O ideal é configurar grupos de grades para as diferentes categorias de produtos.</span><span class="sxs-lookup"><span data-stu-id="8d1e3-107">It is ideal to set up variant groups for different product categories.</span></span> <span data-ttu-id="8d1e3-108">Por exemplo, é possível criar um grupo de tamanhos para camisetas com tamanhos extra pequeno, pequeno, médio, grande e extra grande, ou criar um grupo de cores para incluir todas as cores disponíveis de um produto.</span><span class="sxs-lookup"><span data-stu-id="8d1e3-108">For example, a size group can be created for t-shirts with sizes extra small, small, medium, large, and extra large, or a color group could be created to include all available colors of a product.</span></span> <span data-ttu-id="8d1e3-109">Os grupos de grades devem ser adicionados antes de os produtos serem adicionados.</span><span class="sxs-lookup"><span data-stu-id="8d1e3-109">Variant groups should be added before products are added.</span></span>

<span data-ttu-id="8d1e3-110">Neste tópico, será criado e configurado um grupo de tamanhos.</span><span class="sxs-lookup"><span data-stu-id="8d1e3-110">In this topic, a size group will be created and configured.</span></span> <span data-ttu-id="8d1e3-111">Procedimentos semelhantes podem ser usados para adicionar e configurar grupos de estilos e de cores.</span><span class="sxs-lookup"><span data-stu-id="8d1e3-111">Similar procedures can be used for adding and configuring style groups and color groups.</span></span>

## <a name="create-a-size-group"></a><span data-ttu-id="8d1e3-112">Criar um grupo de tamanhos</span><span class="sxs-lookup"><span data-stu-id="8d1e3-112">Create a size group</span></span>

<span data-ttu-id="8d1e3-113">Para criar um grupo de tamanhos, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="8d1e3-113">To create a size group, follow these steps.</span></span>
 
1. <span data-ttu-id="8d1e3-114">No painel de navegação, vá para **Módulos \> Varejo e comércio \> Produtos e categorias \> Grupos de grades \> Grupos de tamanho**.</span><span class="sxs-lookup"><span data-stu-id="8d1e3-114">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Variant groups \> Size groups**.</span></span>
1. <span data-ttu-id="8d1e3-115">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8d1e3-115">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="8d1e3-116">Na caixa **Grupo de tamanhos**, digite um nome para o grupo de tamanhos.</span><span class="sxs-lookup"><span data-stu-id="8d1e3-116">In the **Size group** box, enter a name for the size group.</span></span>
1. <span data-ttu-id="8d1e3-117">Na caixa **Descrição**, insira uma descrição apropriada.</span><span class="sxs-lookup"><span data-stu-id="8d1e3-117">In the **Description** box, enter an appropriate description.</span></span>
1. <span data-ttu-id="8d1e3-118">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8d1e3-118">On the action pane, select **Save**.</span></span>

## <a name="add-attributes-to-the-size-group"></a><span data-ttu-id="8d1e3-119">Adicionar atributos ao grupo de tamanhos</span><span class="sxs-lookup"><span data-stu-id="8d1e3-119">Add attributes to the size group</span></span>

<span data-ttu-id="8d1e3-120">Para adicionar atributos a um grupo de tamanhos, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="8d1e3-120">To add attributes to a size group, follow these steps.</span></span>

1. <span data-ttu-id="8d1e3-121">No painel de navegação, vá para **Módulos \> Varejo e comércio \> Produtos e categorias \> Grupos de grades \> Grupos de tamanho**</span><span class="sxs-lookup"><span data-stu-id="8d1e3-121">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Variant groups \> Size groups**</span></span>
1. <span data-ttu-id="8d1e3-122">No painel de navegação, selecione um grupo de tamanhos.</span><span class="sxs-lookup"><span data-stu-id="8d1e3-122">In the navigation pane, select a size group.</span></span>
1. <span data-ttu-id="8d1e3-123">Em **Linhas de grupo de tamanhos**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8d1e3-123">Under **Size group lines**, select **Add**.</span></span>
1. <span data-ttu-id="8d1e3-124">Na caixa **Tamanho**, insira uma sequência de caracteres que represente o tamanho (por exemplo, "GG").</span><span class="sxs-lookup"><span data-stu-id="8d1e3-124">In the **Size** box, enter a string representing the size (for example, "XL").</span></span>
1. <span data-ttu-id="8d1e3-125">Na caixa **Nome do tamanho**, digite um nome para o tamanho (por exemplo, "Extra Grande").</span><span class="sxs-lookup"><span data-stu-id="8d1e3-125">In the **Size name** box, enter a name for the size (for example, "Extra Large").</span></span>
1. <span data-ttu-id="8d1e3-126">Na caixa **Peso de reabastecimento**, insira um número que represente o peso de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="8d1e3-126">In the **Replenishment weight** box, enter a number representing the replenishment weight.</span></span>
1. <span data-ttu-id="8d1e3-127">Na caixa **Número no código de barras**, insira um número que represente o código de barras.</span><span class="sxs-lookup"><span data-stu-id="8d1e3-127">In the **Number in bar code** box, enter a number representing the bar code.</span></span>
1. <span data-ttu-id="8d1e3-128">Na caixa **Ordem de exibição**, insira um número que represente a ordem de exibição.</span><span class="sxs-lookup"><span data-stu-id="8d1e3-128">In the **Display order** box, enter a number representing the display order.</span></span>
1. <span data-ttu-id="8d1e3-129">Quando terminar de adicionar os tamanhos, selecione **Salvar** no painel de ação.</span><span class="sxs-lookup"><span data-stu-id="8d1e3-129">When finished adding sizes, select **Save** on the action pane.</span></span>

<span data-ttu-id="8d1e3-130">A imagem a seguir mostra um exemplo de grupo de tamanhos para "tamanhos de camisas casuais".</span><span class="sxs-lookup"><span data-stu-id="8d1e3-130">The following image shows an example of a size group for "casual shirt sizes".</span></span>

![Criar grupo de tamanhos](media/create-variant-group.png)

## <a name="additional-resources"></a><span data-ttu-id="8d1e3-132">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="8d1e3-132">Additional resources</span></span>

[<span data-ttu-id="8d1e3-133">Visão geral das informações do produto</span><span class="sxs-lookup"><span data-stu-id="8d1e3-133">Product information overview</span></span>](../supply-chain/pim/product-information.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="8d1e3-134">Configurar produtos de varejo</span><span class="sxs-lookup"><span data-stu-id="8d1e3-134">Set up retail products</span></span>](set-up-retail-products.md)

[<span data-ttu-id="8d1e3-135">Dimensões do produto</span><span class="sxs-lookup"><span data-stu-id="8d1e3-135">Product dimensions</span></span>](../supply-chain/pim/product-dimensions.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]