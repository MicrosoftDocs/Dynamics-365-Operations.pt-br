---
title: Módulo de carrinho
description: Este tópico abrange os módulos de carrinho e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3ba46fd90507a9cf8da92598c8449a2e553da352
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411264"
---
# <a name="cart-module"></a><span data-ttu-id="3e5de-103">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="3e5de-103">Cart module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="3e5de-104">Este tópico abrange os módulos de carrinho e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3e5de-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="3e5de-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="3e5de-105">Overview</span></span>

<span data-ttu-id="3e5de-106">Um módulo de carrinho mostra os itens que foram adicionados ao carrinho antes de o cliente prosseguir para finalizar a compra.</span><span class="sxs-lookup"><span data-stu-id="3e5de-106">A cart module shows the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="3e5de-107">O módulo também mostra um resumo da ordem e permite que o cliente aplique ou remova códigos promocionais.</span><span class="sxs-lookup"><span data-stu-id="3e5de-107">The module also shows an order summary and lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="3e5de-108">O módulo do carrinho oferece suporte a finalização de compra em conexão e a finalização de compra de convidado.</span><span class="sxs-lookup"><span data-stu-id="3e5de-108">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="3e5de-109">Ele também oferece suporte ao link **Voltar para compra**.</span><span class="sxs-lookup"><span data-stu-id="3e5de-109">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="3e5de-110">Você pode configurar o roteiro desse link em **Configurações de Site \> Extensões \> Roteiros**.</span><span class="sxs-lookup"><span data-stu-id="3e5de-110">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="3e5de-111">O módulo do carrinho processa os dados com base na ID do carrinho, que é um cookie do navegador disponível em todo o site.</span><span class="sxs-lookup"><span data-stu-id="3e5de-111">The cart module renders data based on the cart ID, which is a browser cookie available throughout the site.</span></span> 

<span data-ttu-id="3e5de-112">A imagem a seguir mostra um exemplo de uma página de carrinho no site da Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="3e5de-112">The following image shows an example of a cart page on the Fabrikam site.</span></span>

![Exemplo de um módulo de carrinho](./media/cart2.PNG)

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="3e5de-114">Propriedades e slots do módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="3e5de-114">Cart module properties and slots</span></span>

<span data-ttu-id="3e5de-115">O módulo do carrinho tem uma propriedade **Título** que pode ser definida com valores como **Sacola de compras** e **Itens no seu carrinho**.</span><span class="sxs-lookup"><span data-stu-id="3e5de-115">The cart module has a **Heading** property that can be set to values such as **Shopping bag** and **Items in your cart**.</span></span> 

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="3e5de-116">Módulos que podem ser usados em um módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="3e5de-116">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="3e5de-117">**Bloco de texto** – Este módulo fornece suporte a mensagens personalizadas no módulo de carrinho.</span><span class="sxs-lookup"><span data-stu-id="3e5de-117">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="3e5de-118">As mensagens são direcionadas pelo sistema de gerenciamento de conteúdo (CMS).</span><span class="sxs-lookup"><span data-stu-id="3e5de-118">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="3e5de-119">Qualquer mensagem pode ser adicionada, como "Caso você tenha problemas com o pedido, entre em contato com 1-800-Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="3e5de-119">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="3e5de-120">**Seletor de loja** – Este módulo mostra uma lista de lojas próximas, onde um item está disponível para retirada.</span><span class="sxs-lookup"><span data-stu-id="3e5de-120">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="3e5de-121">Ele permite que os usuários insiram um local para encontrar lojas próximas.</span><span class="sxs-lookup"><span data-stu-id="3e5de-121">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="3e5de-122">Para obter mais informações sobre este módulo, consulte [Módulo do seletor de armazenamento](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="3e5de-122">For more information on this module, see [Store selector module](store-selector.md).</span></span>

## <a name="module-properties"></a><span data-ttu-id="3e5de-123">Propriedades do módulo</span><span class="sxs-lookup"><span data-stu-id="3e5de-123">Module properties</span></span>

<span data-ttu-id="3e5de-124">As seguintes configurações de módulo de carrinho podem ser definidas em **Configurações de Site \> Extensões**:</span><span class="sxs-lookup"><span data-stu-id="3e5de-124">The following cart module settings can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="3e5de-125">**Quantidade máxima** – Esta propriedade é usada para especificar o número máximo de cada item que pode ser adicionado ao carrinho.</span><span class="sxs-lookup"><span data-stu-id="3e5de-125">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="3e5de-126">Por exemplo, um varejista pode decidir que apenas 10 de cada produto podem ser vendidos em uma única transação.</span><span class="sxs-lookup"><span data-stu-id="3e5de-126">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="3e5de-127">**Estoque** – para obter informações sobre como aplicar configurações de estoque, consulte [Aplicar configurações de estoque](inventory-settings.md).</span><span class="sxs-lookup"><span data-stu-id="3e5de-127">**Inventory** – For information about how to apply inventory settings, see [Apply inventory settings](inventory-settings.md).</span></span>
- <span data-ttu-id="3e5de-128">**Voltar para compra** – Esta propriedade é usada para especificar o roteiro do link **Voltar para compra**.</span><span class="sxs-lookup"><span data-stu-id="3e5de-128">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="3e5de-129">O roteiro pode ser configurado no nível do site, permitindo que os varejistas retornem o cliente para a Home Page ou qualquer outra página no site.</span><span class="sxs-lookup"><span data-stu-id="3e5de-129">The route can be configured at the site level, allowing retailers to take the customer back to the home page or any other page on the site.</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="3e5de-130">Interação do Commerce Scale Unit</span><span class="sxs-lookup"><span data-stu-id="3e5de-130">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="3e5de-131">O módulo de carrinho recupera informações do produto usando as APIs de Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="3e5de-131">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="3e5de-132">A ID de carrinho do cookie do navegador é usada para recuperar todas as informações do produto direto do Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="3e5de-132">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="3e5de-133">Adicionar um módulo de carrinho a uma página</span><span class="sxs-lookup"><span data-stu-id="3e5de-133">Add a cart module to a page</span></span>

<span data-ttu-id="3e5de-134">Para adicionar um módulo de carrinho a uma nova página e definir as propriedades necessárias, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="3e5de-134">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="3e5de-135">Vá para **Fragmentos de Página** e selecione **Novo** para criar um novo fragmento.</span><span class="sxs-lookup"><span data-stu-id="3e5de-135">Go to **Page Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="3e5de-136">Na caixa de diálogo **Novo Fragmento de Página**, selecione o módulo **Carrinho**.</span><span class="sxs-lookup"><span data-stu-id="3e5de-136">In the **New Page Fragment** dialog box, select the **Cart** module.</span></span>
1. <span data-ttu-id="3e5de-137">Em **Nome do Fragmento de Página**, digite o nome **Fragmento de carrinho** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e5de-137">Under **Page Fragment Name**, enter the name **Cart fragment**, and then select **OK**.</span></span>
1. <span data-ttu-id="3e5de-138">Selecione o slot **Carrinho**.</span><span class="sxs-lookup"><span data-stu-id="3e5de-138">Select the **Cart** slot.</span></span>
1. <span data-ttu-id="3e5de-139">No painel de propriedades à direita, selecione o símbolo de lápis, digite o texto do título no campo e, em seguida, selecione o símbolo de marca de seleção.</span><span class="sxs-lookup"><span data-stu-id="3e5de-139">In the properties pane on the right, select the pencil symbol, enter heading text in the field, and then select the check mark symbol.</span></span>
1. <span data-ttu-id="3e5de-140">No slot **Carrinho**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="3e5de-140">In the **Cart** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3e5de-141">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Seletor de loja** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e5de-141">In the **Add Module** dialog box, select the **Store selector** module, and then select **OK**.</span></span>
1. <span data-ttu-id="3e5de-142">Selecione **Salvar**, **Concluir edição** para fazer check-in do fragmento e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="3e5de-142">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="3e5de-143">Vá para **Modelos** e selecione **Novo** para criar um novo modelo.</span><span class="sxs-lookup"><span data-stu-id="3e5de-143">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="3e5de-144">Na caixa de diálogo **Novo Modelo**, em **Nome do modelo**, insira um nome para o modelo.</span><span class="sxs-lookup"><span data-stu-id="3e5de-144">In the **New Template** dialog box, under **Template name**, enter a name for the template.</span></span>
1. <span data-ttu-id="3e5de-145">Na árvore de estrutura de tópicos, selecione o slot **Corpo**, as reticências (**...**) e, depois, **Adicionar Fragmento**.</span><span class="sxs-lookup"><span data-stu-id="3e5de-145">In the outline tree, select the **Body** slot, select the ellipsis (**...**), and then select **Add Fragment**.</span></span>
1. <span data-ttu-id="3e5de-146">Na caixa de diálogo **Selecionar Fragmento de Página**, selecione o fragmento **Fragmento de carrinho** e **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e5de-146">In the **Select Page Fragment** dialog box, select the **Cart fragment** fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="3e5de-147">Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="3e5de-147">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="3e5de-148">Vá para **Páginas** e selecione **Novo** para criar uma nova página.</span><span class="sxs-lookup"><span data-stu-id="3e5de-148">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="3e5de-149">Na caixa de diálogo **Escolher um modelo**, selecione o modelo que você criou, insira um nome de página e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e5de-149">In the **Choose a template** dialog box, select the template that you created, enter a page name, and then select **OK**.</span></span>
1. <span data-ttu-id="3e5de-150">Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.</span><span class="sxs-lookup"><span data-stu-id="3e5de-150">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="3e5de-151">Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="3e5de-151">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3e5de-152">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="3e5de-152">Additional resources</span></span>

[<span data-ttu-id="3e5de-153">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="3e5de-153">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="3e5de-154">Módulo de contêiner</span><span class="sxs-lookup"><span data-stu-id="3e5de-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="3e5de-155">Módulo de seletor de loja</span><span class="sxs-lookup"><span data-stu-id="3e5de-155">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="3e5de-156">Módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="3e5de-156">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="3e5de-157">Módulo de ícone de carrinho</span><span class="sxs-lookup"><span data-stu-id="3e5de-157">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="3e5de-158">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="3e5de-158">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="3e5de-159">Módulo de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="3e5de-159">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="3e5de-160">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="3e5de-160">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="3e5de-161">Módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="3e5de-161">Footer module</span></span>](author-footer-module.md)

[<span data-ttu-id="3e5de-162">Calcular disponibilidade de estoque para canais de varejo</span><span class="sxs-lookup"><span data-stu-id="3e5de-162">Calculate inventory availability for retail channels</span></span>](calculated-inventory-retail-channels.md)
