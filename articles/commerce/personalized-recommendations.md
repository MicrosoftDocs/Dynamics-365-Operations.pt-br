---
title: Habilitar recomendações de produtos personalizados
description: Este tópico descreve como disponibilizar recomendações de produtos personalizados para clientes no Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4103096f23e5568cc2bf64f21720c7c16d3e0cd1
ms.sourcegitcommit: 8905d7a7a010e451c5435086480f66650ec54926
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "3664849"
---
# <a name="enable-personalized-recommendations"></a><span data-ttu-id="c5d0c-103">Habilitar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="c5d0c-103">Enable personalized recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c5d0c-104">Este tópico descreve como disponibilizar recomendações de produtos personalizados para clientes no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-104">This topic describes how to make personalized product recommendations available for customers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c5d0c-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="c5d0c-105">Overview</span></span>

<span data-ttu-id="c5d0c-106">No Dynamics 365 Commerce, os varejistas podem disponibilizar recomendações de produtos personalizados (também conhecidos como personalização).</span><span class="sxs-lookup"><span data-stu-id="c5d0c-106">In Dynamics 365 Commerce, retailers can make personalized product recommendations (also known as personalization) available.</span></span> <span data-ttu-id="c5d0c-107">Dessa forma, as recomendações personalizadas podem ser incorporadas na experiência do cliente online e no PDV (ponto de venda).</span><span class="sxs-lookup"><span data-stu-id="c5d0c-107">In this way, personalized recommendations can be incorporated into the customer experience online and at the point of sale (POS).</span></span> <span data-ttu-id="c5d0c-108">Quando a funcionalidade de personalização é ativada, o sistema pode associar as informações de compra e de produto de um usuário para gerar recomendações de produtos individualizadas.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-108">When the personalization functionality is turned on, the system can associate a user's purchase and product information to generate individualized product recommendations.</span></span>

## <a name="personalization-prerequisites"></a><span data-ttu-id="c5d0c-109">Pré-requisitos de personalização</span><span class="sxs-lookup"><span data-stu-id="c5d0c-109">Personalization prerequisites</span></span>

<span data-ttu-id="c5d0c-110">Antes de disponibilizar as recomendações de produto personalizadas para clientes, observe que há suporte apenas para os usuários comerciais que migraram o armazenamento para o Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-110">Before you make personalized product recommendations available for customers, note that product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Store.</span></span> <span data-ttu-id="c5d0c-111">Antes que os clientes possam receber recomendações personalizadas sobre o produto, os varejistas devem [ativar as recomendações do produto](enable-product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="c5d0c-111">Before customers can receive personalized product recommendations, retailers must [turn on product recommendations](enable-product-recommendations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c5d0c-112">Ativando as recomendações do produto, você também ativa a personalização.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-112">By turning on product recommendations, you also turn on personalization.</span></span> <span data-ttu-id="c5d0c-113">No entanto, se você desativar a personalização, não desativará os outros tipos de recomendações de produto.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-113">However, if you turn off personalization, you don't turn off the other types of product recommendations.</span></span>

<span data-ttu-id="c5d0c-114">Para obter mais informações sobre recomendações de produtos, consulte a [Visão geral das recomendações de produtos](product-recommendations.md)</span><span class="sxs-lookup"><span data-stu-id="c5d0c-114">For more information about product recommendations, see the [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="turn-on-personalization"></a><span data-ttu-id="c5d0c-115">Ativar personalização</span><span class="sxs-lookup"><span data-stu-id="c5d0c-115">Turn on personalization</span></span>

<span data-ttu-id="c5d0c-116">Para ativar a personalização, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-116">To turn on personalization, follow these steps.</span></span>

1. <span data-ttu-id="c5d0c-117">Acesse **Varejo e comércio \> Recomendações de produto \> Parâmetros de recomendação**.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-117">Go to **Retail and commerce \> Product recommendations \> Recommendation parameters**.</span></span>
1. <span data-ttu-id="c5d0c-118">Na lista de parâmetros compartilhados de varejo, selecione **Listas de recomendação**.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-118">In the list of Retail shared parameters, select **Recommendation lists**.</span></span>
1. <span data-ttu-id="c5d0c-119">Defina a opção **Habilitar personalização** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-119">Set the **Enable personalization** option to **Yes**.</span></span>

![Ativar personalização](./media/enablepersonalization.png)

> [!NOTE]
> <span data-ttu-id="c5d0c-121">Quando você ativa a personalização, o processo de geração de listas personalizadas de recomendação de produtos é iniciado.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-121">When you turn on personalization, the process of generating personalized product recommendation lists is started.</span></span> <span data-ttu-id="c5d0c-122">Talvez seja necessário até um dia para que essas listas estejam disponíveis e visíveis online e no PDV.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-122">Up to one day might be required before these lists are available and visible online and at the POS.</span></span>

## <a name="personalized-lists"></a><span data-ttu-id="c5d0c-123">Listas personalizadas</span><span class="sxs-lookup"><span data-stu-id="c5d0c-123">Personalized lists</span></span>

<span data-ttu-id="c5d0c-124">Além de permitir a personalização de listas existentes geradas por máquina, o serviço de recomendações permite a personalização da experiência de descoberta de produtos online e no PDV.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-124">In addition to allowing for personalization of existing machine-generated lists, the recommendations service allows for personalization of the product discovery experience both online and at the POS.</span></span>

<span data-ttu-id="c5d0c-125">Depois que a personalização é ativada, os varejistas podem mostrar as listas de clientes personalizados do comprador para as listas "online" ou "recomendável para o cliente" nos terminais de PDV.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-125">After personalization is turned on, retailers can show shoppers personalized "Picks for you" lists online or "Recommended for customer" lists on POS terminals.</span></span> <span data-ttu-id="c5d0c-126">Além disso, os varejistas podem aplicar a personalização a listas de recomendações de produtos existentes e fornecer experiências de recusa GDPR (regulamentação geral de proteção de dados) para usuários autenticados.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-126">Additionally, retailers can apply personalization to existing product recommendation lists and provide General Data Protection Regulation (GDPR) opt-out experiences for authenticated users.</span></span> <span data-ttu-id="c5d0c-127">Se você desativar a personalização, também desative esses recursos.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-127">If you turn off personalization, you also turn off these features.</span></span>

### <a name="online-picks-for-you-lists"></a><span data-ttu-id="c5d0c-128">Listas de "Seleções para você" online</span><span class="sxs-lookup"><span data-stu-id="c5d0c-128">Online "Picks for you" lists</span></span>

<span data-ttu-id="c5d0c-129">Uma lista de "Seleções para você" é uma lista de aprendizado de máquina de inteligência artificial (AI-ML) que mostra a um usuário autenticado uma lista individualizada de produtos sugeridos.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-129">A "Picks for you" list is an artificial intelligence-machine learning (AI-ML) list that shows an authenticated user a personalized list of suggested products.</span></span> <span data-ttu-id="c5d0c-130">Essa lista se baseia no histórico de compras de omnicanal do usuário.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-130">This list is based on the user's omnichannel purchase history.</span></span> <span data-ttu-id="c5d0c-131">As recomendações personalizadas são atualizadas dinamicamente à medida que o usuário faz mais compras.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-131">Personalized recommendations are dynamically updated as the user makes more purchases.</span></span> <span data-ttu-id="c5d0c-132">Esse tipo de lista também oferece suporte à filtragem de categorias, de forma que os varejistas possam mostrar as primeiras seleções, com base nas hierarquias de navegação.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-132">This type of list also supports category filtering, so that retailers can show top picks, based on navigational hierarchies.</span></span>

<span data-ttu-id="c5d0c-133">Antes da lista "Seleções para você" aparecer em qualquer página de comércio eletrônico, os seguintes requisitos de usuário devem ser atendidos:</span><span class="sxs-lookup"><span data-stu-id="c5d0c-133">Before the "Picks for you" list can appear on any e-Commerce page, the following user requirements must be met:</span></span>

- <span data-ttu-id="c5d0c-134">Os usuários devem estar logados.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-134">Users must be signed in.</span></span> <span data-ttu-id="c5d0c-135">Os usuários anônimos não verão recomendações personalizadas.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-135">Anonymous users won't see personalized recommendations.</span></span>
- <span data-ttu-id="c5d0c-136">Os usuários devem ter pelo menos uma compra na conta deles.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-136">Users must have at least one purchase on their account.</span></span>
- <span data-ttu-id="c5d0c-137">Os usuários devem optar por receber recomendações personalizadas.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-137">Users must opt in to receive personalized recommendations.</span></span>

<span data-ttu-id="c5d0c-138">A ilustração a seguir mostra um exemplo de uma lista de "Seleções para você" em uma página de armazenamento online.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-138">The following illustration shows an example of a "Picks for you" list on an online store page.</span></span>

![Lista Seleções para você online](./media/picksforyou.png)

### <a name="recommended-for-customer-lists-at-the-pos"></a><span data-ttu-id="c5d0c-140">Listas "recomendadas para clientes" no PDV</span><span class="sxs-lookup"><span data-stu-id="c5d0c-140">"Recommended for customer" lists at the POS</span></span>

<span data-ttu-id="c5d0c-141">Para aprimorar a experiência dos clientes, os varejistas podem personalizar páginas de detalhes de clientes existentes, adicionando uma lista contextual "Recomendado para o cliente".</span><span class="sxs-lookup"><span data-stu-id="c5d0c-141">To enhance their clienteling experience, retailers can personalize existing customer details pages by adding a contextual "Recommended for customer" list.</span></span>

<span data-ttu-id="c5d0c-142">A ilustração a seguir mostra um exemplo de uma lista de "Recomendado para o cliente" em um Terminal de PDV.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-142">The following illustration shows an example of a "Recommended for customer" list on a POS terminal.</span></span>

![Lista Recomendado para o cliente no PDV](./media/picksonpos.png)

## <a name="apply-personalization-to-existing-recommendation-lists"></a><span data-ttu-id="c5d0c-144">Aplicar personalização a listas de recomendação existentes</span><span class="sxs-lookup"><span data-stu-id="c5d0c-144">Apply personalization to existing recommendation lists</span></span>

<span data-ttu-id="c5d0c-145">Os varejistas podem aplicar a personalização a listas de recomendação existentes, como "Novo", "Tendência", "Mais vendidos", "As pessoas também gostam de" e "Frequentemente comprado junto".</span><span class="sxs-lookup"><span data-stu-id="c5d0c-145">Retailers can apply personalization to existing recommendation lists, such as "New," "Trending," "Best selling," "People also like," and "Frequently bought together."</span></span> <span data-ttu-id="c5d0c-146">Quando a personalização é aplicada a listas existentes, os itens que um usuário conectado comprou anteriormente são removidos dessas listas.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-146">When personalization is applied to existing lists, items that a signed-in user previously bought are removed from those lists.</span></span> <span data-ttu-id="c5d0c-147">Para usuários anônimos e usuários que optaram por receber recomendações personalizadas, as versões padrão das listas existentes são mostradas.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-147">For both anonymous users and users who opted out of receiving personalized recommendations, default versions of the existing lists are shown.</span></span> <span data-ttu-id="c5d0c-148">Portanto, os varejistas não precisam manter manualmente experiências de página separadas.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-148">Therefore, retailers don't have to manually maintain separate page experiences.</span></span>

<span data-ttu-id="c5d0c-149">Por exemplo, um usuário conectado já comprou o relógio preto e as botas de trabalho marrom que aparecem na lista "Mais populares - padrão" da ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-149">For example, a signed-in user has already bought the black watch and the brown work boots that appear in the "Trending - default" list in the following illustration.</span></span> <span data-ttu-id="c5d0c-150">Portanto, o usuário verá novos produtos em vez desses produtos, conforme mostrado na lista "Mais populares - personalizado".</span><span class="sxs-lookup"><span data-stu-id="c5d0c-150">Therefore, the user will see new products instead of those products, as shown in the "Trending - personalized" list.</span></span>

![Aplicando personalização](./media/applypersonalization.png)

<span data-ttu-id="c5d0c-152">Para aplicar a personalização a uma lista de recomendação existente no Commerce site builder, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-152">To apply personalization to an existing recommendation list in the Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="c5d0c-153">Abra uma página existente do assistente para criação de sites que contenha um módulo de coleção de produtos.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-153">Open an existing site builder page that contains a product collection module.</span></span>
1. <span data-ttu-id="c5d0c-154">No painel de navegação esquerdo, selecione o módulo de coleta de produtos.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-154">In the left navigation pane, select the product collection module.</span></span>
1. <span data-ttu-id="c5d0c-155">No painel de navegação direito, em **Produtos**, selecione a lista.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-155">In the right navigation pane, under **Products**, select the list.</span></span>
1. <span data-ttu-id="c5d0c-156">Na caixa de diálogo **Selecionar configuração da lista de produtos**, em **Tipo**, selecione o tipo de lista.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-156">In the **Select product list configuration** dialog box, under **Type**, select the list type.</span></span>
1. <span data-ttu-id="c5d0c-157">Marque caixa de seleção **Aplicar Personalização** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-157">Select the **Apply Personalization** check box, and then select **OK**.</span></span>

    ![Aplicando personalização a uma lista de tendências](./media/ApplyPersonalizationToTrending.PNG)

1. <span data-ttu-id="c5d0c-159">Salve a página, termine de editá-la e publique-a.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-159">Save the page, finish editing it, and then publish it.</span></span> <span data-ttu-id="c5d0c-160">Depois que a página for publicada, os usuários conectados verão listas de tendências personalizadas.</span><span class="sxs-lookup"><span data-stu-id="c5d0c-160">After the page is published, signed-in users will see personalized trending lists.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c5d0c-161">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="c5d0c-161">Additional resources</span></span>

[<span data-ttu-id="c5d0c-162">Visão geral das recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="c5d0c-162">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="c5d0c-163">Habilitar Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="c5d0c-163">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="c5d0c-164">Habilitar recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="c5d0c-164">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="c5d0c-165">Habilitar recomendações de "comprar looks semelhantes"</span><span class="sxs-lookup"><span data-stu-id="c5d0c-165">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="c5d0c-166">Cancelar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="c5d0c-166">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="c5d0c-167">Adicionar recomendações de produtos no PDV</span><span class="sxs-lookup"><span data-stu-id="c5d0c-167">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="c5d0c-168">Adicionar recomendações à tela de transação</span><span class="sxs-lookup"><span data-stu-id="c5d0c-168">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="c5d0c-169">Ajustar os resultados das recomendações de AI-ML</span><span class="sxs-lookup"><span data-stu-id="c5d0c-169">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="c5d0c-170">Criar manualmente recomendações selecionadas</span><span class="sxs-lookup"><span data-stu-id="c5d0c-170">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="c5d0c-171">Criar recomendações com dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="c5d0c-171">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="c5d0c-172">Perguntas frequentes sobre recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="c5d0c-172">Product recommendations FAQ</span></span>](faq-recommendations.md)
