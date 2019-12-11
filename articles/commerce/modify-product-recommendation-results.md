---
title: Gerenciar resultados da recomendação de produtos com base em IA-ML
description: Este tópico explica como personalizar os resultados da recomendação do produto com base em aprendizado de máquina de inteligência artificial (AI-ML) para sua empresa.
author: bebeale
manager: AnnBe
ms.date: 10/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 669b056c38614c8ac9be2d7b244a0ab0c73bc9f8
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770061"
---
# <a name="manage-ai-ml-based-product-recommendation-results"></a><span data-ttu-id="1a856-103">Gerenciar resultados da recomendação de produtos com base em IA-ML</span><span class="sxs-lookup"><span data-stu-id="1a856-103">Manage AI-ML-based product recommendation results</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="1a856-104">Este tópico explica como personalizar os resultados da recomendação do produto com base em aprendizado de máquina de inteligência artificial (AI-ML) para sua empresa.</span><span class="sxs-lookup"><span data-stu-id="1a856-104">This topic explains how to tailor product recommendation results based on artificial intelligence-machine learning (AI-ML) to your business.</span></span> 

<span data-ttu-id="1a856-105">Depois de habilitar as recomendações do produto, as configurações padrão entrarão em vigor; esses parâmetros funcionarão, podem funcionar para muitas necessidades.</span><span class="sxs-lookup"><span data-stu-id="1a856-105">After enabling product recommendations, the default settings will take effect; these parameters will work for may work for many needs.</span></span> <span data-ttu-id="1a856-106">É melhor planejar gastar algum tempo avaliando se os resultados se encaixam no movimento de venda dos produtos.</span><span class="sxs-lookup"><span data-stu-id="1a856-106">It is best to plan to spend some time evaluating whether the results fit the selling motion of products.</span></span> <span data-ttu-id="1a856-107">Sugerimos avaliar os resultados por alguns dias antes de alterar os parâmetros, conforme necessário, antes de testar novamente.</span><span class="sxs-lookup"><span data-stu-id="1a856-107">We suggest evaluating results for a few days before changing parameters as needed before testing again.</span></span> 

## <a name="understanding-recommendation-list-parameters"></a><span data-ttu-id="1a856-108">Compreendendo os parâmetros da lista de recomendação</span><span class="sxs-lookup"><span data-stu-id="1a856-108">Understanding recommendation list parameters</span></span>

<span data-ttu-id="1a856-109">Antes de alterar os parâmetros, saiba como eles afetarão os resultados a seguir.</span><span class="sxs-lookup"><span data-stu-id="1a856-109">Before changing the parameters, learn about how they will affect the results below.</span></span>

### <a name="trending-product-list"></a><span data-ttu-id="1a856-110">Lista de produtos mais populares</span><span class="sxs-lookup"><span data-stu-id="1a856-110">Trending product list</span></span>

<span data-ttu-id="1a856-111">A lista de produtos **Mais populares** tem dois parâmetros que podem ser alterados: ![Exemplo de parâmetros padrão da lista Mais populares](./media/exampletrendingparameters.png)</span><span class="sxs-lookup"><span data-stu-id="1a856-111">The **Trending** product list has two parameters that can be changed: ![Example Trending list default parameters](./media/exampletrendingparameters.png)</span></span>
1. <span data-ttu-id="1a856-112">**Incluir novos produtos dos últimos X dias** - Os produtos que foram adicionados dentro do número especificado de dias, antes da data atual, podem ser usados para selecionar candidatos ao produto.</span><span class="sxs-lookup"><span data-stu-id="1a856-112">**Include new products from last X days** - Products that have been added within the specified number of days before the current date can be used to select product candidates.</span></span> <span data-ttu-id="1a856-113">O valor padrão na imagem sugere que produtos antigos com 180 dias podem ser usados na lista de tendências de produtos.</span><span class="sxs-lookup"><span data-stu-id="1a856-113">The default value in the picture suggests that products as old has 180 days can be used in the trending product list.</span></span>
1. <span data-ttu-id="1a856-114">**Incluir vendas dos últimos X dias** - As transações de vendas que ocorreram dentro do número especificado de dias, antes da data atual, podem ser usadas para solicitar os produtos.</span><span class="sxs-lookup"><span data-stu-id="1a856-114">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="1a856-115">O valor padrão acima sugere que todas as compras de um produto, feitas nos últimos 30 dias, seriam usadas para determinar a colocação do produto na lista de produtos mais populares.</span><span class="sxs-lookup"><span data-stu-id="1a856-115">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the trending product list.</span></span> 

### <a name="best-selling-product-list"></a><span data-ttu-id="1a856-116">Lista de produtos mais vendidos</span><span class="sxs-lookup"><span data-stu-id="1a856-116">Best selling product list</span></span>

<span data-ttu-id="1a856-117">Dependendo do seu negócio, o mais vendido pode trazer resultados diferentes do mais popular, mesmo que os dois usem dados de transação para solicitar produtos.</span><span class="sxs-lookup"><span data-stu-id="1a856-117">Depending on your business, Best selling can bring different results than trending, even though they both use transaction data to order products.</span></span> <span data-ttu-id="1a856-118">Como a melhor venda não tem suspensão com base na data do sortimento, ela ainda pode destacar produtos muito populares e antigos que podem ter sido retirados da lista de tendências.</span><span class="sxs-lookup"><span data-stu-id="1a856-118">Because best selling has no cut off based on assortment date, Best selling can still highlight very popular, older products that might have been dropped from the trending list.</span></span> 

<span data-ttu-id="1a856-119">A lista de produtos de **Melhor venda** tem um parâmetro que pode ser alterado:</span><span class="sxs-lookup"><span data-stu-id="1a856-119">The **Best selling** product list has one parameter that can be changed:</span></span>

![Exemplo de parâmetro padrão da lista de Melhor venda](./media/examplebestsellingparameters.PNG)
1. <span data-ttu-id="1a856-121">**Incluir vendas dos últimos X dias** - As transações de vendas que ocorreram dentro do número especificado de dias, antes da data atual, podem ser usadas para solicitar os produtos.</span><span class="sxs-lookup"><span data-stu-id="1a856-121">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="1a856-122">O valor padrão acima sugere que todas as compras de um produto, feitas nos últimos 30 dias, seriam usadas para determinar a colocação do produto na lista de produtos Mais vendidos.</span><span class="sxs-lookup"><span data-stu-id="1a856-122">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the Best selling product list.</span></span> 

## <a name="manually-add-or-remove-products-from-recommendation-lists"></a><span data-ttu-id="1a856-123">Adicionar ou remover manualmente produtos das listas de recomendação</span><span class="sxs-lookup"><span data-stu-id="1a856-123">Manually add or remove products from recommendation lists</span></span>

### <a name="for-new-trending-or-best-selling"></a><span data-ttu-id="1a856-124">Para Novo, Mais Populares ou Mais vendidos</span><span class="sxs-lookup"><span data-stu-id="1a856-124">For New, Trending, or Best selling</span></span>

1.  <span data-ttu-id="1a856-125">Vá para **Varejo** > **Recomendações do produto** > **Parâmetros de recomendação**.</span><span class="sxs-lookup"><span data-stu-id="1a856-125">Go to **Retail** > **Product recommendations** > **Recommendation parameters**.</span></span>
1.  <span data-ttu-id="1a856-126">Na lista de parâmetros de varejo compartilhados, selecione **Listas de recomendação**.</span><span class="sxs-lookup"><span data-stu-id="1a856-126">In the list of retail shared parameters, select **Recommendation lists**.</span></span>
1.  <span data-ttu-id="1a856-127">Selecione a lista da qual serão adicionados ou removidos os produtos.</span><span class="sxs-lookup"><span data-stu-id="1a856-127">Select the list add or remove products from.</span></span>
1.  <span data-ttu-id="1a856-128">Para adicionar produtos à tabela, selecione **Adicionar linha**.</span><span class="sxs-lookup"><span data-stu-id="1a856-128">To add products to the table, select **Add line.**</span></span> 
1.  <span data-ttu-id="1a856-129">Na coluna Produto, procure um produto por **Nome** ou **Número do produto.**
![Exemplo de como procurar um produto na lista Novo produto](./media/examplenewlistconfiguration1.png)</span><span class="sxs-lookup"><span data-stu-id="1a856-129">Under the Product column, search for a product by **Name** or **Product number.**
![Example of searching for a product on the New product list](./media/examplenewlistconfiguration1.png)</span></span>
1.  <span data-ttu-id="1a856-130">Na coluna Tipo de linha, selecione uma das duas opções:</span><span class="sxs-lookup"><span data-stu-id="1a856-130">Under the Line type column, select one of two options:</span></span>
    -   <span data-ttu-id="1a856-131">**Incluir** – coloca um produto à frente da lista</span><span class="sxs-lookup"><span data-stu-id="1a856-131">**Include** – forces a product to the front of the list</span></span>
    -   <span data-ttu-id="1a856-132">**Excluir** – impede que um produto apareça na lista ![Exemplo de Como Incluir ou Excluir um produto da lista Novo produto](./media/examplenewlistconfiguration2.png)</span><span class="sxs-lookup"><span data-stu-id="1a856-132">**Exclude** – removes a product from appearing in the list ![Example of Including or Excluding a product from the New product list](./media/examplenewlistconfiguration2.png)</span></span>
1.  <span data-ttu-id="1a856-133">Alterar a **Ordem de exibição** alterará a ordem na qual os produtos marcados como **incluir** aparecerão na lista.</span><span class="sxs-lookup"><span data-stu-id="1a856-133">Changing the **Display order** will change the order that products marked **include** will appear in the list.</span></span>
    - <span data-ttu-id="1a856-134">Se dois produtos tiverem o mesmo valor de **ordem de exibição**, então a ordem final desses dois resultados pode ser diferente do back office.</span><span class="sxs-lookup"><span data-stu-id="1a856-134">If two products have the same **display order** value, then the final order of those two results may differ from the back office.</span></span>
1.  <span data-ttu-id="1a856-135">Para remover os produtos da tabela: selecione a linha para remover e selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="1a856-135">To remove products from the table: select the line to remove and select **Remove**.</span></span>


### <a name="for-people-also-like-or-frequently-bought-together-lists"></a><span data-ttu-id="1a856-136">Para as listas de As pessoas também gostam ou Frequentemente comprado junto</span><span class="sxs-lookup"><span data-stu-id="1a856-136">For People also like or Frequently bought together lists</span></span>

<span data-ttu-id="1a856-137">No contexto das listas **Frequentemente comprado junto** ou **As pessoas também gostam**, o aprendizado de máquina é usado para analisar os padrões de compra do consumidor para recomendar produtos relacionados, geralmente adquiridos juntos, para um produto de origem exclusivo.</span><span class="sxs-lookup"><span data-stu-id="1a856-137">In the context of **Frequently bought together** or **People also like** lists, machine learning is used to analyze consumer purchase patterns to recommend related products commonly purchased together for a unique seed product.</span></span> 
 
<span data-ttu-id="1a856-138">Um **produto de origem** é o produto para o qual você deseja gerar resultados.</span><span class="sxs-lookup"><span data-stu-id="1a856-138">A **seed product** is the product you want to generate results for.</span></span> <span data-ttu-id="1a856-139">No contexto de ajuste manual das listas de recomendação, você está adicionando ou removendo resultados desse produto.</span><span class="sxs-lookup"><span data-stu-id="1a856-139">In the context of manually adjusting recommendation lists, you are adding or removing results for this product.</span></span> 

<span data-ttu-id="1a856-140">Siga estas etapas para adicionar ou remover manualmente os resultados de um produto de origem:</span><span class="sxs-lookup"><span data-stu-id="1a856-140">Follow these steps to manually add or remove results for a seed product:</span></span>
1.  <span data-ttu-id="1a856-141">Selecione o **Produto de origem**.</span><span class="sxs-lookup"><span data-stu-id="1a856-141">Select the **Seed product**.</span></span> 
1.  <span data-ttu-id="1a856-142">Na coluna **Produto**, procure um produto por **Nome** ou **Número do produto.**
![Exemplo de como procurar um produto na lista Frequentemente comprado junto](./media/exampleFBTlistconfiguration1.png)</span><span class="sxs-lookup"><span data-stu-id="1a856-142">Under the **Product** column, search for a product by **Name** or **Product number.**
![Example of searching for a product on the Frequently bought together list](./media/exampleFBTlistconfiguration1.png)</span></span>
1. <span data-ttu-id="1a856-143">Na coluna **Tipo de linha**, selecione uma das duas opções:</span><span class="sxs-lookup"><span data-stu-id="1a856-143">Under the **Line type** column, select one of two options:</span></span>
    - <span data-ttu-id="1a856-144">**Incluir** – coloca um produto à frente da lista</span><span class="sxs-lookup"><span data-stu-id="1a856-144">**Include** – forces a product to the front of the list</span></span>
    - <span data-ttu-id="1a856-145">**Excluir** – impede que um produto apareça na lista</span><span class="sxs-lookup"><span data-stu-id="1a856-145">**Exclude** – removes a product from appearing in the list</span></span>     
<span data-ttu-id="1a856-146">![Exemplo de Como Incluir ou Excluir um produto na lista de Frequentemente comprado junto](./media/exampleFBTlistconfiguration2.png)</span><span class="sxs-lookup"><span data-stu-id="1a856-146">![Example of Including or Excluding a product on the Frequently bought together list](./media/exampleFBTlistconfiguration2.png)</span></span>
1.  <span data-ttu-id="1a856-147">Para remover os produtos da tabela: selecione a linha para remover e selecione Remover.</span><span class="sxs-lookup"><span data-stu-id="1a856-147">To remove products from the table: select the line to remove and select Remove.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="1a856-148">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="1a856-148">Additional resources</span></span>

[<span data-ttu-id="1a856-149">Visão geral de recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="1a856-149">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="1a856-150">Habilitar recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="1a856-150">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="1a856-151">Adicionar listas de recomendações de produto às páginas</span><span class="sxs-lookup"><span data-stu-id="1a856-151">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)
