---
title: Visão geral de recomendações de produtos
description: Este tópico fornece informações gerais sobre as recomendações do produto. As recomendações de produtos permitem que os clientes encontrem com facilidade e rapidez os produtos que desejam e até produtos que não pretendiam comprar originalmente.
author: Moonma
manager: AnnBe
ms.date: 05/26/2020
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
ms.author: moonma
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5aa7db8e53906f9e1416b912fe2c3b70d5430258
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410062"
---
# <a name="product-recommendations-overview"></a><span data-ttu-id="19783-104">Visão geral de recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="19783-104">Product recommendations overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="19783-105">O Microsoft Dynamics 365 Commerce pode ser usado para mostrar recomendações de produtos no site de comércio eletrônico e no dispositivo de ponto de venda (PDV).</span><span class="sxs-lookup"><span data-stu-id="19783-105">Microsoft Dynamics 365 Commerce can be used to show product recommendations on the e-Commerce website and point of sale (POS) device.</span></span> <span data-ttu-id="19783-106">As recomendações de produtos são itens nos quais um cliente pode estar interessado.</span><span class="sxs-lookup"><span data-stu-id="19783-106">Product recommendations are items that a customer might be interested in.</span></span> <span data-ttu-id="19783-107">As recomendações baseiam-se em tendências de compra dos outros clientes em lojas online e físicas.</span><span class="sxs-lookup"><span data-stu-id="19783-107">The recommendations are based on the purchase trends of other customers in online and brick-and-mortar stores.</span></span>

<span data-ttu-id="19783-108">As recomendações de produtos permitem que os clientes encontrem com facilidade e rapidez os produtos que desejam, enquanto têm uma experiência que os atende bem.</span><span class="sxs-lookup"><span data-stu-id="19783-108">Product recommendations allow customers to easily and quickly find products that they want while they have an experience that serves them well.</span></span> <span data-ttu-id="19783-109">A venda cruzada e a adicional podem até ser usadas para ajudar os clientes a encontrar produtos adicionais que eles não pretendiam comprar originalmente.</span><span class="sxs-lookup"><span data-stu-id="19783-109">Cross-selling and upselling can even be used to assist customers find additional products that they didn't originally intend to buy.</span></span> <span data-ttu-id="19783-110">Quando as recomendações são usadas para aprimorar a descoberta do produto, elas criam mais oportunidades de conversão, ajudam a aumentar a receita de vendas e até a aumentar a satisfação e retenção de clientes.</span><span class="sxs-lookup"><span data-stu-id="19783-110">When recommendations are used to enhance product discovery, they create more conversion opportunities, help increase sales revenue, and even amplify customer satisfaction and retention.</span></span>

<span data-ttu-id="19783-111">No comércio eletrônico, as recomendações de produtos são baseadas nas tecnologias de aprendizado de máquina do Microsoft Recommendations em larga escala.</span><span class="sxs-lookup"><span data-stu-id="19783-111">In e-Commerce, product recommendations are powered by Microsoft Recommendations machine learning technologies on a large scale.</span></span>

## <a name="recommendation-service"></a><span data-ttu-id="19783-112">Serviço de recomendação</span><span class="sxs-lookup"><span data-stu-id="19783-112">Recommendation service</span></span>

<span data-ttu-id="19783-113">O serviço de recomendações de produtos utiliza as tecnologias de inteligência artificial e de vida de máquina (AI-ML) da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="19783-113">The product recommendations service utilizes artificial intelligence and machine learning (AI-ML) technologies in the following way:</span></span>

- <span data-ttu-id="19783-114">Os dados no formato que o serviço de Recomendação exige é extraído do banco de dados operacional do Commerce e enviado ao Azure Data Lake Storage ou à loja da Entidade.</span><span class="sxs-lookup"><span data-stu-id="19783-114">Data in the format that the Recommendation service requires is extracted from the Commerce operational database and sent to Azure Data Lake Storage or Entity store.</span></span>
- <span data-ttu-id="19783-115">O serviço da recomendações usa os dados armazenados para treinar modelos da recomendação para as listas **As pessoas também gostam de**, **Frequentemente comprado junto**, **Novo**, **Mais vendidos** e **Mais populares** .</span><span class="sxs-lookup"><span data-stu-id="19783-115">The recommendations service uses the stored data to train recommendation models for the **People also like**, **Frequently bought together**, **New**, **Best selling**, and **Trending** lists.</span></span>

## <a name="scenarios"></a><span data-ttu-id="19783-116">Cenários</span><span class="sxs-lookup"><span data-stu-id="19783-116">Scenarios</span></span>

<span data-ttu-id="19783-117">As recomendações de produtos estão disponíveis para os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="19783-117">Product recommendations are available for the following scenarios:</span></span>

- <span data-ttu-id="19783-118">**Em qualquer página da loja para navegação ou página inicial no comércio eletrônico:** Se os clientes ou associados da loja visitam uma página da loja, o mecanismo de recomendação pode sugerir produtos nas listas **Novo**, **Mais Vendidos** e **Mais Populares**.</span><span class="sxs-lookup"><span data-stu-id="19783-118">**On any store page for browsing or landing page in e-Commerce:** If customers or store associates visit a store page, the recommendation engine can suggest products in the **New**, **Best Selling**, and **Trending** lists.</span></span>
- <span data-ttu-id="19783-119">**Na página de detalhes do Produto:** Se os clientes ou associados da loja visitam uma página de **Detalhes do produto**, o mecanismo de recomendação sugere itens adicionais que provavelmente também serão comprados.</span><span class="sxs-lookup"><span data-stu-id="19783-119">**On the Product details page:** If customers or store associates visit a **Product details** page, the recommendation engine suggests additional items that are also likely to be purchased.</span></span> <span data-ttu-id="19783-120">Esses itens são exibidos na lista **As pessoas também gostam de** .</span><span class="sxs-lookup"><span data-stu-id="19783-120">These items appear in the **People also like** list.</span></span>
- <span data-ttu-id="19783-121">**Na página da Transação ou na página de check-out:** O mecanismo de recomendação sugere itens, com base na lista completa de itens na cesta.</span><span class="sxs-lookup"><span data-stu-id="19783-121">**On the Transaction page or the checkout page:** The recommendation engine suggests items, based on the whole list of items in the basket.</span></span> <span data-ttu-id="19783-122">Esses itens são exibidos na lista **Compra junto com frequência** .</span><span class="sxs-lookup"><span data-stu-id="19783-122">These items appear in the **Frequently bought together** list.</span></span>
- <span data-ttu-id="19783-123">**Recomendações personalizadas:** os vendedores podem fornecer aos clientes conectados uma lista de **seleções para você** personalizada, além da nova funcionalidade que permite a personalização de cenários de lista existentes com base nesse cliente.</span><span class="sxs-lookup"><span data-stu-id="19783-123">**Personalized recommendations:** Merchandizers can provide signed-in customers a personalized **picks for you** list, in addition to new functionality that allows for existing list scenarios to be personalized based on that customer.</span></span> <span data-ttu-id="19783-124">Para saber mais, consulte [Habilitar recomendações personalizadas](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="19783-124">To learn more, see [Enable personalized recommendations.](personalized-recommendations.md).</span></span>

### <a name="types-of-product-recommendations"></a><span data-ttu-id="19783-125">Tipos de recomendações de produto</span><span class="sxs-lookup"><span data-stu-id="19783-125">Types of product recommendations</span></span>

<span data-ttu-id="19783-126">A tabela a seguir descreve vários tipos de recomendações de produto automatizadas disponíveis para varejistas a fim de implementar em sua solução Dynamics 365 Commerce por meio do [módulo de coleção de produtos](product-collection-module-overview.md).</span><span class="sxs-lookup"><span data-stu-id="19783-126">The following table describes various types of automated product recommendations available for retailers to implement in their Dynamics 365 Commerce solution via the [product collection module](product-collection-module-overview.md).</span></span> <span data-ttu-id="19783-127">Os varejistas também podem mostrar resultados personalizados para um usuário conectado, caso o autor do site escolha essa opção.</span><span class="sxs-lookup"><span data-stu-id="19783-127">Retailers can also show personalized results for a signed-in user if the site author chooses that option.</span></span>

| <span data-ttu-id="19783-128">Módulos de coleta de produtos</span><span class="sxs-lookup"><span data-stu-id="19783-128">Product collection module</span></span>  | <span data-ttu-id="19783-129">Tipo</span><span class="sxs-lookup"><span data-stu-id="19783-129">Type</span></span> | <span data-ttu-id="19783-130">descrição</span><span class="sxs-lookup"><span data-stu-id="19783-130">Description</span></span> |
|----------------------------|------|-------------|
| <span data-ttu-id="19783-131">Nova</span><span class="sxs-lookup"><span data-stu-id="19783-131">New</span></span>                        | <span data-ttu-id="19783-132">Algorítmico</span><span class="sxs-lookup"><span data-stu-id="19783-132">Algorithmic</span></span> | <span data-ttu-id="19783-133">Este módulo mostra uma lista de produtos mais novos que foram classificadas recentemente para canais e os catálogos.</span><span class="sxs-lookup"><span data-stu-id="19783-133">This module shows a list of the newest products that have been recently assorted to channels and catalogs.</span></span> |
| <span data-ttu-id="19783-134">Mais vendidos</span><span class="sxs-lookup"><span data-stu-id="19783-134">Best selling</span></span>               | <span data-ttu-id="19783-135">Algorítmico</span><span class="sxs-lookup"><span data-stu-id="19783-135">Algorithmic</span></span> | <span data-ttu-id="19783-136">Este módulo mostra uma lista de produtos que estão classificados por número mais alto de venda.</span><span class="sxs-lookup"><span data-stu-id="19783-136">This module shows a list of products that are ranked by the highest number of sales.</span></span> |
| <span data-ttu-id="19783-137">Mais populares</span><span class="sxs-lookup"><span data-stu-id="19783-137">Trending</span></span>                   | <span data-ttu-id="19783-138">Algorítmico</span><span class="sxs-lookup"><span data-stu-id="19783-138">Algorithmic</span></span> | <span data-ttu-id="19783-139">Esse módulo mostra uma lista dos produtos com melhor desempenho por um determinado período, classificado pelo maior número de vendas.</span><span class="sxs-lookup"><span data-stu-id="19783-139">This module shows a list of the highest-performing products for a given period, ranked by highest number of sales.</span></span>  |
| <span data-ttu-id="19783-140">Frequentemente comprado junto</span><span class="sxs-lookup"><span data-stu-id="19783-140">Frequently bought together</span></span> | <span data-ttu-id="19783-141">AI-ML</span><span class="sxs-lookup"><span data-stu-id="19783-141">AI-ML</span></span> | <span data-ttu-id="19783-142">Este módulo recomenda uma lista de produtos que normalmente são comprados juntamente com o conteúdo do carrinho de clientes atual.</span><span class="sxs-lookup"><span data-stu-id="19783-142">This module recommends a list of products that are commonly purchased together with the contents of the consumers current cart.</span></span> |
| <span data-ttu-id="19783-143">As pessoas também gostam</span><span class="sxs-lookup"><span data-stu-id="19783-143">People also like</span></span>           | <span data-ttu-id="19783-144">AI-ML</span><span class="sxs-lookup"><span data-stu-id="19783-144">AI-ML</span></span> | <span data-ttu-id="19783-145">Este módulo recomenda produtos para um determinado produto de semente com base nos padrões de compra do consumidor.</span><span class="sxs-lookup"><span data-stu-id="19783-145">This module recommends products for a given seed product based on consumer purchase patterns.</span></span> |
| <span data-ttu-id="19783-146">Seleções para Você</span><span class="sxs-lookup"><span data-stu-id="19783-146">Picks for you</span></span>              | <span data-ttu-id="19783-147">AI-ML</span><span class="sxs-lookup"><span data-stu-id="19783-147">AI-ML</span></span> | <span data-ttu-id="19783-148">Este módulo recomenda uma lista individualizada de produtos com base em padrões de compra do usuário conectado.</span><span class="sxs-lookup"><span data-stu-id="19783-148">This module recommends a personalized list of products based on purchase patterns of the signed-in user.</span></span> <span data-ttu-id="19783-149">Para um usuário convidado, esta lista será recolhida.</span><span class="sxs-lookup"><span data-stu-id="19783-149">For a guest user, this list will be collapsed.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="19783-150">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="19783-150">Additional resources</span></span>

[<span data-ttu-id="19783-151">Habilitar Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="19783-151">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="19783-152">Habilitar recomendações dos produtos</span><span class="sxs-lookup"><span data-stu-id="19783-152">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="19783-153">Habilitar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="19783-153">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="19783-154">Cancelar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="19783-154">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="19783-155">Habilitar recomendações de "comprar looks semelhantes"</span><span class="sxs-lookup"><span data-stu-id="19783-155">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="19783-156">Adicionar recomendações dos produtos no PDV</span><span class="sxs-lookup"><span data-stu-id="19783-156">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="19783-157">Adicionar recomendações à tela de transações</span><span class="sxs-lookup"><span data-stu-id="19783-157">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="19783-158">Ajustar os resultados das recomendações de AI-ML</span><span class="sxs-lookup"><span data-stu-id="19783-158">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="19783-159">Criar manualmente recomendações selecionadas</span><span class="sxs-lookup"><span data-stu-id="19783-159">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="19783-160">Criar recomendações com dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="19783-160">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="19783-161">Perguntas frequentes sobre recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="19783-161">Product recommendations FAQ</span></span>](faq-recommendations.md)
