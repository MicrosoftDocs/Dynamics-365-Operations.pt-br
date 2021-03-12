---
title: Ajustar resultados da recomendação de produtos com base em IA-ML
description: Este tópico explica como personalizar os resultados da recomendação do produto com base em aprendizado de máquina de inteligência artificial (AI-ML) para sua empresa.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: aab1b22b844ad14a94e1143f49b69f525d93f5b0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985902"
---
# <a name="adjust-ai-ml-based-product-recommendation-results"></a><span data-ttu-id="d8bd9-103">Ajustar resultados da recomendação de produtos com base em IA-ML</span><span class="sxs-lookup"><span data-stu-id="d8bd9-103">Adjust AI-ML-based product recommendation results</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="d8bd9-104">Este tópico explica como ajustar os resultados da recomendação do produto com base em aprendizado de máquina de inteligência artificial (AI-ML) para sua empresa.</span><span class="sxs-lookup"><span data-stu-id="d8bd9-104">This topic explains how to adjust product recommendation results based on artificial intelligence-machine learning (AI-ML) to your business.</span></span> 

<span data-ttu-id="d8bd9-105">Depois de habilitar as recomendações do produto, as configurações padrão entrarão em vigor; esses parâmetros funcionarão, podem funcionar para muitas necessidades.</span><span class="sxs-lookup"><span data-stu-id="d8bd9-105">After enabling product recommendations, the default settings will take effect; these parameters will work for may work for many needs.</span></span> <span data-ttu-id="d8bd9-106">É melhor planejar gastar algum tempo avaliando se os resultados se encaixam no movimento de venda dos produtos.</span><span class="sxs-lookup"><span data-stu-id="d8bd9-106">It is best to plan to spend some time evaluating whether the results fit the selling motion of products.</span></span> <span data-ttu-id="d8bd9-107">Sugerimos avaliar os resultados por alguns dias antes de alterar os parâmetros, conforme necessário, antes de testar novamente.</span><span class="sxs-lookup"><span data-stu-id="d8bd9-107">We suggest evaluating results for a few days before changing parameters as needed before testing again.</span></span> 

## <a name="understanding-recommendation-list-parameters"></a><span data-ttu-id="d8bd9-108">Compreendendo os parâmetros da lista de recomendação</span><span class="sxs-lookup"><span data-stu-id="d8bd9-108">Understanding recommendation list parameters</span></span>

<span data-ttu-id="d8bd9-109">Antes de alterar os parâmetros, saiba como eles afetarão os resultados a seguir.</span><span class="sxs-lookup"><span data-stu-id="d8bd9-109">Before changing the parameters, learn about how they will affect the results below.</span></span>

### <a name="trending-product-list"></a><span data-ttu-id="d8bd9-110">Lista de produtos "mais populares"</span><span class="sxs-lookup"><span data-stu-id="d8bd9-110">"Trending" product list</span></span>

<span data-ttu-id="d8bd9-111">A lista de produtos "mais populares" tem dois parâmetros que podem ser alterados:</span><span class="sxs-lookup"><span data-stu-id="d8bd9-111">The "Trending" product list has two parameters that can be changed:</span></span>

![Exemplo de parâmetros padrão da lista "Mais populares"](./media/exampletrendingparameters.png)

1. <span data-ttu-id="d8bd9-113">**Incluir novos produtos dos últimos X dias** - Os produtos que foram adicionados dentro do número especificado de dias, antes da data atual, podem ser usados para selecionar candidatos ao produto.</span><span class="sxs-lookup"><span data-stu-id="d8bd9-113">**Include new products from last X days** - Products that have been added within the specified number of days before the current date can be used to select product candidates.</span></span> <span data-ttu-id="d8bd9-114">O valor padrão na imagem sugere que produtos antigos com 180 dias podem ser usados na lista de tendências de produtos.</span><span class="sxs-lookup"><span data-stu-id="d8bd9-114">The default value in the picture suggests that products as old has 180 days can be used in the trending product list.</span></span>
1. <span data-ttu-id="d8bd9-115">**Incluir vendas dos últimos X dias** - As transações de vendas que ocorreram dentro do número especificado de dias, antes da data atual, podem ser usadas para solicitar os produtos.</span><span class="sxs-lookup"><span data-stu-id="d8bd9-115">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="d8bd9-116">O valor padrão acima sugere que todas as compras de um produto, feitas nos últimos 30 dias, seriam usadas para determinar a colocação do produto na lista de produtos mais populares.</span><span class="sxs-lookup"><span data-stu-id="d8bd9-116">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the trending product list.</span></span> 

### <a name="best-selling-product-list"></a><span data-ttu-id="d8bd9-117">Lista de produtos "mais vendidos"</span><span class="sxs-lookup"><span data-stu-id="d8bd9-117">"Best selling" product list</span></span>

<span data-ttu-id="d8bd9-118">Dependendo do seu negócio, a lista "Mais vendidos" poderá gerar resultados diferentes do mais popular, mesmo que os dois usem dados de transação para solicitar produtos.</span><span class="sxs-lookup"><span data-stu-id="d8bd9-118">Depending on your business, the "Best selling" list can bring different results than trending, even though they both use transaction data to order products.</span></span> <span data-ttu-id="d8bd9-119">Como a melhor venda não tem suspensão com base na data do sortimento, ela ainda pode destacar produtos muito populares e antigos que podem ter sido retirados da lista de tendências.</span><span class="sxs-lookup"><span data-stu-id="d8bd9-119">Because best selling has no cut off based on assortment date, Best selling can still highlight very popular, older products that might have been dropped from the trending list.</span></span> 

<span data-ttu-id="d8bd9-120">A lista de produtos "Mais vendidos" tem um parâmetro que pode ser alterado:</span><span class="sxs-lookup"><span data-stu-id="d8bd9-120">The "Best selling" product list has one parameter that can be changed:</span></span>

![Exemplo de parâmetro padrão da lista de Melhor venda](./media/examplebestsellingparameters.PNG)

1. <span data-ttu-id="d8bd9-122">**Incluir vendas dos últimos X dias** - As transações de vendas que ocorreram dentro do número especificado de dias, antes da data atual, podem ser usadas para solicitar os produtos.</span><span class="sxs-lookup"><span data-stu-id="d8bd9-122">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="d8bd9-123">O valor padrão acima sugere que todas as compras de um produto, feitas nos últimos 30 dias, seriam usadas para determinar a colocação do produto na lista de produtos Mais vendidos.</span><span class="sxs-lookup"><span data-stu-id="d8bd9-123">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the Best selling product list.</span></span> 

## <a name="manually-add-or-remove-products-from-recommendation-lists"></a><span data-ttu-id="d8bd9-124">Adicionar ou remover manualmente produtos das listas de recomendação</span><span class="sxs-lookup"><span data-stu-id="d8bd9-124">Manually add or remove products from recommendation lists</span></span>

### <a name="for-new-trending-or-best-selling-lists"></a><span data-ttu-id="d8bd9-125">Para as litas "Novo", "Mais Populares" ou "Mais vendidos"</span><span class="sxs-lookup"><span data-stu-id="d8bd9-125">For "New," "Trending," or "Best selling" lists</span></span>

1.  <span data-ttu-id="d8bd9-126">Acesse **Varejo e Comércio** > **Recomendações de produto** > **Parâmetros de recomendação**.</span><span class="sxs-lookup"><span data-stu-id="d8bd9-126">Go to **Retail and Commerce** > **Product recommendations** > **Recommendation parameters**.</span></span>
1.  <span data-ttu-id="d8bd9-127">Na lista de parâmetros compartilhados, selecione **Listas de recomendação**.</span><span class="sxs-lookup"><span data-stu-id="d8bd9-127">In the list of shared parameters, select **Recommendation lists**.</span></span>
1.  <span data-ttu-id="d8bd9-128">Selecione a lista da qual serão adicionados ou removidos os produtos.</span><span class="sxs-lookup"><span data-stu-id="d8bd9-128">Select the list add or remove products from.</span></span>
1.  <span data-ttu-id="d8bd9-129">Para adicionar produtos à tabela, selecione **Adicionar linha**.</span><span class="sxs-lookup"><span data-stu-id="d8bd9-129">To add products to the table, select **Add line.**</span></span> 
1.  <span data-ttu-id="d8bd9-130">Na coluna Produto, procure um produto pelo **Nome** ou **Número do produto.**</span><span class="sxs-lookup"><span data-stu-id="d8bd9-130">Under the Product column, search for a product by **Name** or **Product number.**</span></span>

    ![Exemplo de pesquisa de um produto na Nova lista de produtos](./media/examplenewlistconfiguration1.png)

1.  <span data-ttu-id="d8bd9-132">Na coluna Tipo de linha, selecione uma das duas opções:</span><span class="sxs-lookup"><span data-stu-id="d8bd9-132">Under the Line type column, select one of two options:</span></span>
    -   <span data-ttu-id="d8bd9-133">**Incluir** – coloca um produto à frente da lista</span><span class="sxs-lookup"><span data-stu-id="d8bd9-133">**Include** – forces a product to the front of the list</span></span>
    -   <span data-ttu-id="d8bd9-134">**Excluir** – impede que um produto apareça na lista</span><span class="sxs-lookup"><span data-stu-id="d8bd9-134">**Exclude** – removes a product from appearing in the list</span></span>
    
    ![Exemplo de inclusão ou exclusão de um produto da nova lista de produtos](./media/examplenewlistconfiguration2.png)

1.  <span data-ttu-id="d8bd9-136">Alterar a **Ordem de exibição** alterará a ordem na qual os produtos marcados como **incluir** aparecerão na lista.</span><span class="sxs-lookup"><span data-stu-id="d8bd9-136">Changing the **Display order** will change the order that products marked **include** will appear in the list.</span></span>
    - <span data-ttu-id="d8bd9-137">Se dois produtos tiverem o mesmo valor de **ordem de exibição**, então a ordem final desses dois resultados pode ser diferente do back office.</span><span class="sxs-lookup"><span data-stu-id="d8bd9-137">If two products have the same **display order** value, then the final order of those two results may differ from the back office.</span></span>
1.  <span data-ttu-id="d8bd9-138">Para remover os produtos da tabela: selecione a linha para remover e selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="d8bd9-138">To remove products from the table: select the line to remove and select **Remove**.</span></span>


### <a name="for-people-also-like-or-frequently-bought-together-lists"></a><span data-ttu-id="d8bd9-139">Para as listas de "As pessoas também gostam de" ou "Frequentemente comprado junto"</span><span class="sxs-lookup"><span data-stu-id="d8bd9-139">For "People also like" or "Frequently bought together" lists</span></span>

<span data-ttu-id="d8bd9-140">No contexto das listas "Frequentemente comprado junto" ou "As pessoas também gostam de", o aprendizado de máquina é usado para analisar os padrões de compra do consumidor para recomendar produtos relacionados, geralmente adquiridos juntos, para um produto de origem exclusivo.</span><span class="sxs-lookup"><span data-stu-id="d8bd9-140">In the context of "Frequently bought together" or "People also like" lists, machine learning is used to analyze consumer purchase patterns to recommend related products commonly purchased together for a unique seed product.</span></span> 
 
<span data-ttu-id="d8bd9-141">Um *produto de origem* é o produto para o qual você deseja gerar resultados.</span><span class="sxs-lookup"><span data-stu-id="d8bd9-141">A *seed product* is the product you want to generate results for.</span></span> <span data-ttu-id="d8bd9-142">No contexto de ajuste manual das listas de recomendação, você está adicionando ou removendo resultados desse produto.</span><span class="sxs-lookup"><span data-stu-id="d8bd9-142">In the context of manually adjusting recommendation lists, you are adding or removing results for this product.</span></span> 

<span data-ttu-id="d8bd9-143">Siga estas etapas para adicionar ou remover manualmente os resultados de um produto de origem:</span><span class="sxs-lookup"><span data-stu-id="d8bd9-143">Follow these steps to manually add or remove results for a seed product:</span></span>
1.  <span data-ttu-id="d8bd9-144">Selecione o **Produto de origem**.</span><span class="sxs-lookup"><span data-stu-id="d8bd9-144">Select the **Seed product**.</span></span> 
1.  <span data-ttu-id="d8bd9-145">Na coluna **Produto**, procure um produto por **Nome** ou **Número do produto.**
![Exemplo de como procurar um produto na lista Frequentemente comprado junto](./media/exampleFBTlistconfiguration1.png)</span><span class="sxs-lookup"><span data-stu-id="d8bd9-145">Under the **Product** column, search for a product by **Name** or **Product number.**
![Example of searching for a product on the Frequently bought together list](./media/exampleFBTlistconfiguration1.png)</span></span>
1. <span data-ttu-id="d8bd9-146">Na coluna **Tipo de linha**, selecione uma das duas opções:</span><span class="sxs-lookup"><span data-stu-id="d8bd9-146">Under the **Line type** column, select one of two options:</span></span>
    - <span data-ttu-id="d8bd9-147">**Incluir** – coloca um produto à frente da lista</span><span class="sxs-lookup"><span data-stu-id="d8bd9-147">**Include** – forces a product to the front of the list</span></span>
    - <span data-ttu-id="d8bd9-148">**Excluir** – impede que um produto apareça na lista</span><span class="sxs-lookup"><span data-stu-id="d8bd9-148">**Exclude** – removes a product from appearing in the list</span></span>     
<span data-ttu-id="d8bd9-149">![Exemplo de Como Incluir ou Excluir um produto na lista de Frequentemente comprado junto](./media/exampleFBTlistconfiguration2.png)</span><span class="sxs-lookup"><span data-stu-id="d8bd9-149">![Example of Including or Excluding a product on the Frequently bought together list](./media/exampleFBTlistconfiguration2.png)</span></span>
1.  <span data-ttu-id="d8bd9-150">Para remover os produtos da tabela: selecione a linha para remover e selecione Remover.</span><span class="sxs-lookup"><span data-stu-id="d8bd9-150">To remove products from the table: select the line to remove and select Remove.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="d8bd9-151">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="d8bd9-151">Additional resources</span></span>

[<span data-ttu-id="d8bd9-152">Visão geral das recomendações dos produtos</span><span class="sxs-lookup"><span data-stu-id="d8bd9-152">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="d8bd9-153">Habilitar Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="d8bd9-153">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="d8bd9-154">Habilitar recomendações dos produtos</span><span class="sxs-lookup"><span data-stu-id="d8bd9-154">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="d8bd9-155">Habilitar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="d8bd9-155">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="d8bd9-156">Cancelar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="d8bd9-156">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="d8bd9-157">Habilitar recomendações de "comprar looks semelhantes"</span><span class="sxs-lookup"><span data-stu-id="d8bd9-157">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="d8bd9-158">Adicionar recomendações dos produtos no PDV</span><span class="sxs-lookup"><span data-stu-id="d8bd9-158">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="d8bd9-159">Adicionar recomendações à tela de transações</span><span class="sxs-lookup"><span data-stu-id="d8bd9-159">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="d8bd9-160">Criar manualmente recomendações selecionadas</span><span class="sxs-lookup"><span data-stu-id="d8bd9-160">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="d8bd9-161">Criar recomendações com dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="d8bd9-161">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="d8bd9-162">Perguntas frequentes sobre recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="d8bd9-162">Product recommendations FAQ</span></span>](faq-recommendations.md)
