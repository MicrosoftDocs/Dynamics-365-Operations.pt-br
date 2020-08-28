---
title: Perguntas frequentes sobre recomendações de produtos
description: Este tópico fornece informações sobre processos e ferramentas que você pode usar para solucionar problemas relacionados a recomendações de produtos ou resultados.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, Core, Operations
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cf3df2267671b50c20b28dbdb1c6a21696bf2515
ms.sourcegitcommit: 8905d7a7a010e451c5435086480f66650ec54926
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "3664969"
---
# <a name="product-recommendations-faq"></a><span data-ttu-id="a60e2-103">Perguntas frequentes sobre recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="a60e2-103">Product recommendations FAQ</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="a60e2-104">Este tópico fornece informações sobre processos e ferramentas que você pode usar para solucionar problemas relacionados a [recomendações de produtos](product-recommendations.md) ou resultados.</span><span class="sxs-lookup"><span data-stu-id="a60e2-104">This topic provides information about processes and tools that you can use to troubleshoot issues that are related to [product recommendations](product-recommendations.md) or their results.</span></span>

## <a name="best-practices"></a><span data-ttu-id="a60e2-105">Práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="a60e2-105">Best practices</span></span>
<span data-ttu-id="a60e2-106">É muito importante usar o conceito produtos mestre e as variantes.</span><span class="sxs-lookup"><span data-stu-id="a60e2-106">It's very important to utilize the concept of product masters and variants.</span></span> <span data-ttu-id="a60e2-107">O agrupamento correto de variantes de um produto mestre ajuda os algoritmos da lista e serviço a criar melhores modelos.</span><span class="sxs-lookup"><span data-stu-id="a60e2-107">The sensible grouping of variants to a parent product master helps the list algorithms and service create better models.</span></span> <span data-ttu-id="a60e2-108">Além disso, o serviço pode servir apenas uma instância de um produto em vez de colocar todas as variantes relacionadas próximas em uma lista.</span><span class="sxs-lookup"><span data-stu-id="a60e2-108">Additionally, the service can serve just one instance of a product instead of putting all closely related variants in a list.</span></span> <span data-ttu-id="a60e2-109">Quando todas as variantes relacionadas próximas são colocadas em uma lista, resultados errados ou duplicados podem ocorrer.</span><span class="sxs-lookup"><span data-stu-id="a60e2-109">When all closely related variants are put in a list, erroneous or duplicate results can occur.</span></span>

## <a name="why-are-products-missing-from-my-recommendation-lists"></a><span data-ttu-id="a60e2-110">Por que tenho produtos faltando nas minhas listas de recomendação?</span><span class="sxs-lookup"><span data-stu-id="a60e2-110">Why are products missing from my recommendation lists?</span></span>

<span data-ttu-id="a60e2-111">Normalmente, se um item está ausente em uma lista de recomendação de produto, pode haver um problema de configuração de produto.</span><span class="sxs-lookup"><span data-stu-id="a60e2-111">Typically, if an item is missing from a product recommendation list, there might be a product configuration issue.</span></span> <span data-ttu-id="a60e2-112">Por exemplo, pode haver uma data inicial e uma data final incorreta de produto, uma dimensão pode ser configurada errado ou produtos podem não estar na classificação de canal correta, etc.</span><span class="sxs-lookup"><span data-stu-id="a60e2-112">For example, there might be an incorrect product start date or end date, a dimension might be misconfigured, or the product might not be in the correct channel assortment, etc.</span></span>

<span data-ttu-id="a60e2-113">Se um item está ausente de uma lista de recomendação baseada em aprendizado de máquina de inteligência artificial (AI-ML), o item não pode modificar os critérios da recomendação ou pode não ter transações de compra suficientes para a lista de recomendação exibi-lo.</span><span class="sxs-lookup"><span data-stu-id="a60e2-113">If an item is missing from a recommendation list that is based on artificial intelligence-machine learning (AI-ML), the item might not fit the criteria of the recommendation list, or it might not have enough purchase transactions for the recommendation list to show it.</span></span>

<span data-ttu-id="a60e2-114">Recomendamos que você verifique estas etapas:</span><span class="sxs-lookup"><span data-stu-id="a60e2-114">We recommend that you check these steps:</span></span>
1. <span data-ttu-id="a60e2-115">**Verifique se as recomendações de produtos foram habilitadas na matriz.**</span><span class="sxs-lookup"><span data-stu-id="a60e2-115">**Make sure that product recommendations have been enabled in HQ.**</span></span> <span data-ttu-id="a60e2-116">Para obter mais informações sobre como habilitar este serviço, consulte [Habilitar recomendações de produto](enable-product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="a60e2-116">For more information about how to enable this service, see [Enable product recommendations](enable-product-recommendations.md).</span></span>
1. <span data-ttu-id="a60e2-117">**Verifique se as propriedades básicas de produto básico estão definidas.**</span><span class="sxs-lookup"><span data-stu-id="a60e2-117">**Make sure that key product properties are set.**</span></span> <span data-ttu-id="a60e2-118">Por exemplo, as classificações do produto devem ser definidas como **Incluir**.</span><span class="sxs-lookup"><span data-stu-id="a60e2-118">For example, product assortments must be set to **Include**.</span></span>
1. <span data-ttu-id="a60e2-119">**Para produtos classificados recentemente, pode levar até 3 horas antes do produto começar a aparecer na nova lista.**</span><span class="sxs-lookup"><span data-stu-id="a60e2-119">**For newly assorted products, it might take up to 3 hours before the product will start appearing in the new list.**</span></span>
1. <span data-ttu-id="a60e2-120">**Se um produto ainda não estão aparecendo em Tendência, as Pessoas também gostaram de ou Comprados juntos com frequência, então esse produto pode não ter transações suficientes.**</span><span class="sxs-lookup"><span data-stu-id="a60e2-120">**If a product is still not appearing in Trending, Best selling, People also like, or Frequently bought together, then that product might not have enough transactions.**</span></span> <span data-ttu-id="a60e2-121">Nesse caso, você pode esperar que mais transações ocorram, atualizar parâmetros padrão de listas de recomendação, ou usar a intervenção manual para alterar os resultados da lista de produtos de recomendação.</span><span class="sxs-lookup"><span data-stu-id="a60e2-121">In this case, you can either wait for more transactions to occur, update the default recommendation list parameters, or use manual intervention to modify the recommendation product list results.</span></span> <span data-ttu-id="a60e2-122">Para obter mais informações sobre os parâmetros de recomendação, consulte [Gerenciar resultados de recomendação de produto baseado em AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="a60e2-122">For more information about recommendation parameters, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>
1. <span data-ttu-id="a60e2-123">**Verifique se o produto atende aos critérios da recomendação para a lista.**</span><span class="sxs-lookup"><span data-stu-id="a60e2-123">**Make sure that the product meets the recommendation criteria for the list.**</span></span> <span data-ttu-id="a60e2-124">Para obter mais informações sobre os parâmetros de recomendação de produto, consulte [Gerenciar resultados de recomendação de produto baseado em AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="a60e2-124">For more information about product recommendation parameters, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="how-can-i-prevent-poor-recommendation-results-from-being-returned"></a><span data-ttu-id="a60e2-125">Como posso prevenir que resultados incorretos de recomendação sejam retornados?</span><span class="sxs-lookup"><span data-stu-id="a60e2-125">How can I prevent poor recommendation results from being returned?</span></span>

<span data-ttu-id="a60e2-126">As listas de recomendação exigem um grande volume de transações para produzir resultados.</span><span class="sxs-lookup"><span data-stu-id="a60e2-126">Recommendation lists require a large volume of transactions to produce results.</span></span> <span data-ttu-id="a60e2-127">Portanto, é importante que os usuários fornecem dados de transações de histórico completos.</span><span class="sxs-lookup"><span data-stu-id="a60e2-127">Therefore, it's important that users provide full historical transaction data.</span></span>

<span data-ttu-id="a60e2-128">Adicionalmente, os produtos que não têm nenhuma transação ou poucas transações geralmente não têm resultados **As pessoas também gostam de** ou **Comprado junto com frequência**, e eles não aparecerão em listas de recomendação em **Tendência** ou **Mais vendidos** .</span><span class="sxs-lookup"><span data-stu-id="a60e2-128">Additionally, products that have no transactions or few transactions typically don't have **People also like** or **Frequently bought together** results, and don't appear in **Trending** or **Best selling** recommendation lists.</span></span> <span data-ttu-id="a60e2-129">Essa situação pode ocorrer para cada produto novo ou para produto antigos que possuem um pequeno número de compras.</span><span class="sxs-lookup"><span data-stu-id="a60e2-129">This situation can often occur for very new products, or for old products that have a small number of purchases.</span></span> <span data-ttu-id="a60e2-130">Novos itens populares superarão esse problema com facilidade.</span><span class="sxs-lookup"><span data-stu-id="a60e2-130">Popular new items will easily overcome this issue.</span></span>

<span data-ttu-id="a60e2-131">Recomendamos que você siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="a60e2-131">We recommend that you follow these steps:</span></span>
1. <span data-ttu-id="a60e2-132">**Verifique se o produto atende aos critérios da recomendação para essa lista.**</span><span class="sxs-lookup"><span data-stu-id="a60e2-132">**Make sure that the product meets the recommendation criteria for that list.**</span></span> <span data-ttu-id="a60e2-133">Para obter mais informações sobre os parâmetros de recomendação de produto, consulte Modificar resultados de recomendação de produto baseado em AI-ML.</span><span class="sxs-lookup"><span data-stu-id="a60e2-133">For more information about product recommendation parameters, see Modify AI-ML-based product recommendation results.</span></span>
1. <span data-ttu-id="a60e2-134">**Se o produto for novo, considere modificar uma lista de recomendação até que o produto tenha mais transações.**</span><span class="sxs-lookup"><span data-stu-id="a60e2-134">**If the product is new, consider modifying a recommendation list until the product has more transactions.**</span></span> <span data-ttu-id="a60e2-135">Para obter mais informações sobre como modificar os resultados da lista de recomendação, consulte [Gerenciar resultados de recomendação de produto baseado em AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="a60e2-135">For more information about how to modify recommendation list results, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>


- <span data-ttu-id="a60e2-136">**Verifique se o produto atende aos critérios da recomendação para essa lista.**</span><span class="sxs-lookup"><span data-stu-id="a60e2-136">**Make sure that the product meets the recommendation criteria for that list.**</span></span> <span data-ttu-id="a60e2-137">Para obter mais informações sobre os parâmetros de recomendação de produto, consulte [Gerenciar resultados de recomendação de produto baseado em AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="a60e2-137">For more information about product recommendation parameters, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>
- <span data-ttu-id="a60e2-138">**Se o produto for novo, considere modificar uma lista de recomendação até que o produto tenha mais transações**.</span><span class="sxs-lookup"><span data-stu-id="a60e2-138">**If the product is new, consider modifying a recommendation list until the product has more transactions**.</span></span> <span data-ttu-id="a60e2-139">Para obter mais informações sobre como modificar os resultados da lista de recomendação, consulte [Gerenciar resultados de recomendação de produto baseado em AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="a60e2-139">For more information about how to modify recommendation list results, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="can-i-remove-a-product-but-still-see-it-in-the-store"></a><span data-ttu-id="a60e2-140">Posso remover um produto mas ainda vê-lo na loja?</span><span class="sxs-lookup"><span data-stu-id="a60e2-140">Can I remove a product but still see it in the store?</span></span>

<span data-ttu-id="a60e2-141">Você pode ajustar as listas geradas algoritmicamente se uma necessidade comercial acontecer.</span><span class="sxs-lookup"><span data-stu-id="a60e2-141">You can adjust lists that are algorithmically generated if a business need arises.</span></span> <span data-ttu-id="a60e2-142">No entanto, se um produto é removido de uma lista de recomendação, o produto ainda poderá ser descoberto na loja.</span><span class="sxs-lookup"><span data-stu-id="a60e2-142">However, if a product is removed from a recommendation list, the product will remain discoverable in the store.</span></span> <span data-ttu-id="a60e2-143">Para obter mais informações sobre como modificar os resultados da recomendação de produto, consulte [Gerenciar resultados de recomendação de produto baseado em AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="a60e2-143">For more information about how to modify product recommendation results, see [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

<span data-ttu-id="a60e2-144">Se precisar bloquear um item de ser descoberto na loja, você deve alterar o valor **Classificações de item** para **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="a60e2-144">If you must block an item from being discovered in the store, you must change the **Item assortments** value to **Exclude**.</span></span>

## <a name="how-do-i-add-a-list-to-an-e-commerce-page"></a><span data-ttu-id="a60e2-145">Como adiciono uma lista à uma página de comércio online?</span><span class="sxs-lookup"><span data-stu-id="a60e2-145">How do I add a list to an e-Commerce page?</span></span>

<span data-ttu-id="a60e2-146">Para obter informações sobre como adicionar páginas de recomendação de produto ao site de comércio online, consulte [Adicionar listas de recomendação de produto às páginas](add-reco-list-to-page.md).</span><span class="sxs-lookup"><span data-stu-id="a60e2-146">For information about how to add product recommendation pages to your e-Commerce website, see [Add product recommendation lists to pages](add-reco-list-to-page.md).</span></span>

## <a name="how-do-i-enable-recommendations-on-pos"></a><span data-ttu-id="a60e2-147">Como habilito recomendações em PDV?</span><span class="sxs-lookup"><span data-stu-id="a60e2-147">How do I enable recommendations on POS?</span></span>

<span data-ttu-id="a60e2-148">Após habilitar recomendações de produto, é preciso adicionar o painel de recomendações à tela PDV de controle.</span><span class="sxs-lookup"><span data-stu-id="a60e2-148">After enabling product recommendations, you will need to add the recommendations panel to the control POS screen.</span></span> <span data-ttu-id="a60e2-149">Para obter mais informações, consulte [Adicionar um controle de recomendação à tela de transação em dispositivos do PDV](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="a60e2-149">For more information, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a60e2-150">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="a60e2-150">Additional resources</span></span>

[<span data-ttu-id="a60e2-151">Visão geral das recomendações dos produtos</span><span class="sxs-lookup"><span data-stu-id="a60e2-151">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="a60e2-152">Habilitar Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="a60e2-152">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="a60e2-153">Habilitar recomendações dos produtos</span><span class="sxs-lookup"><span data-stu-id="a60e2-153">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="a60e2-154">Habilitar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="a60e2-154">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="a60e2-155">Cancelar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="a60e2-155">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="a60e2-156">Habilitar recomendações de "comprar looks semelhantes"</span><span class="sxs-lookup"><span data-stu-id="a60e2-156">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="a60e2-157">Adicionar recomendações dos produtos no PDV</span><span class="sxs-lookup"><span data-stu-id="a60e2-157">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="a60e2-158">Adicionar recomendações à tela de transações</span><span class="sxs-lookup"><span data-stu-id="a60e2-158">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="a60e2-159">Ajustar os resultados das recomendações de AI-ML</span><span class="sxs-lookup"><span data-stu-id="a60e2-159">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="a60e2-160">Criar manualmente recomendações selecionadas</span><span class="sxs-lookup"><span data-stu-id="a60e2-160">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="a60e2-161">Criar recomendações com dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="a60e2-161">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)
