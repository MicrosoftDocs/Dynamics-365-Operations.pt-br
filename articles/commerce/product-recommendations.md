---
title: Visão geral de recomendações de produtos
description: Este tópico fornece informações gerais sobre as recomendações do produto. As recomendações de produtos permitem que os clientes encontrem com facilidade e rapidez os produtos que desejam e até produtos que não pretendiam comprar originalmente.
author: Moonma
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
ms.author: moonma
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: eb369e6d1356ba13a2310d523b671ac57b9642bf
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770037"
---
# <a name="product-recommendations-overview"></a><span data-ttu-id="a3be9-104">Visão geral de recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="a3be9-104">Product recommendations overview</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="a3be9-105">O Microsoft Dynamics 365 Commerce pode ser usado para mostrar recomendações de produtos no site de comércio eletrônico e no dispositivo de ponto de venda (PDV).</span><span class="sxs-lookup"><span data-stu-id="a3be9-105">Microsoft Dynamics 365 Commerce can be used to show product recommendations on the e-Commerce website and point of sale (POS) device.</span></span> <span data-ttu-id="a3be9-106">As recomendações de produtos são itens nos quais um cliente pode estar interessado.</span><span class="sxs-lookup"><span data-stu-id="a3be9-106">Product recommendations are items that a customer might be interested in.</span></span> <span data-ttu-id="a3be9-107">As recomendações baseiam-se em tendências de compra dos outros clientes em lojas online e físicas.</span><span class="sxs-lookup"><span data-stu-id="a3be9-107">The recommendations are based on the purchase trends of other customers in online and brick-and-mortar stores.</span></span>

<span data-ttu-id="a3be9-108">As recomendações de produtos permitem que os clientes encontrem com facilidade e rapidez os produtos que desejam, enquanto têm uma experiência que os atende bem.</span><span class="sxs-lookup"><span data-stu-id="a3be9-108">Product recommendations let customers easily and quickly find products that they want while they have an experience that serves them well.</span></span> <span data-ttu-id="a3be9-109">A venda cruzada e a adicional podem até ser usadas para ajudar os clientes a encontrar produtos adicionais que eles não pretendiam comprar originalmente.</span><span class="sxs-lookup"><span data-stu-id="a3be9-109">Cross-selling and upselling can even be used to help customers find additional products than they didn't originally intend to buy.</span></span> <span data-ttu-id="a3be9-110">Quando as recomendações são usadas para ajudar na descoberta do produto, elas podem criar mais oportunidades de conversão, ajudar a aumentar a receita de vendas e até ajudar a aumentar a satisfação e retenção de clientes.</span><span class="sxs-lookup"><span data-stu-id="a3be9-110">When recommendations are used to help with product discovery, they can create more conversion opportunities, help increase sales revenue, and even help enhance customer satisfaction and retention.</span></span>

<span data-ttu-id="a3be9-111">No Commerce, as recomendações de produtos são baseadas nas tecnologias de aprendizado de máquina do Microsoft Recommendations em larga escala.</span><span class="sxs-lookup"><span data-stu-id="a3be9-111">In Commerce, product recommendations are powered by Microsoft Recommendations machine learning technologies on a large scale.</span></span>


## <a name="scenarios"></a><span data-ttu-id="a3be9-112">Cenários</span><span class="sxs-lookup"><span data-stu-id="a3be9-112">Scenarios</span></span>

<span data-ttu-id="a3be9-113">As recomendações de produtos estão disponíveis para os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="a3be9-113">Product recommendations are available for the following scenarios:</span></span>

- <span data-ttu-id="a3be9-114">**Em qualquer página da loja para navegação ou página inicial no comércio eletrônico:** Se os clientes ou associados da loja visitam uma página da loja, o mecanismo de recomendação pode sugerir produtos nas listas **Novo**, **Mais Vendidos** e **Mais Populares**.</span><span class="sxs-lookup"><span data-stu-id="a3be9-114">**On any store page for browsing or landing page in e-Commerce:** If customers or store associates visit a store page, the recommendation engine can suggest products in the **New**, **Best Selling**, and **Trending** lists.</span></span>
- <span data-ttu-id="a3be9-115">**Na página de detalhes do Produto:** Se os clientes ou associados da loja visitam uma página de **Detalhes do produto**, o mecanismo de recomendação sugere itens adicionais que provavelmente também serão comprados.</span><span class="sxs-lookup"><span data-stu-id="a3be9-115">**On the Product details page:** If customers or store associates visit a **Product details** page, the recommendation engine suggests additional items that are also likely to be purchased.</span></span> <span data-ttu-id="a3be9-116">Esses itens são exibidos na lista **As pessoas também gostam de** .</span><span class="sxs-lookup"><span data-stu-id="a3be9-116">These items appear in the **People also like** list.</span></span>
- <span data-ttu-id="a3be9-117">**Na página da Transação ou na página de check-out:** O mecanismo de recomendação sugere itens, com base na lista completa de itens na cesta.</span><span class="sxs-lookup"><span data-stu-id="a3be9-117">**On the Transaction page or the checkout page:** The recommendation engine suggests items, based on the whole list of items in the basket.</span></span> <span data-ttu-id="a3be9-118">Esses itens são exibidos na lista **Compra junto com frequência** .</span><span class="sxs-lookup"><span data-stu-id="a3be9-118">These items appear in the **Frequently bought together** list.</span></span>

## <a name="recommendation-service"></a><span data-ttu-id="a3be9-119">Serviço de recomendação</span><span class="sxs-lookup"><span data-stu-id="a3be9-119">Recommendation service</span></span>

<span data-ttu-id="a3be9-120">As recomendações de produtos usam as tecnologias de aprendizado de máquina das Recomendações da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="a3be9-120">Product recommendations use the Recommendations machine learning technologies in the following way:</span></span>

- <span data-ttu-id="a3be9-121">Os dados no formato que o serviço de Recomendação exige é extraído do banco de dados operacional do Commerce e enviado à loja da Entidade.</span><span class="sxs-lookup"><span data-stu-id="a3be9-121">Data in the format that the Recommendation service requires is extracted from the Commerce operational database and sent to the Entity store.</span></span>
- <span data-ttu-id="a3be9-122">O serviço da recomendação usa os dados para treinar modelos da recomendação para as listas **As pessoas também gostam de**, **Frequentemente comprado junto**, **Novo**, **Mais vendidos** e **Mais populares** .</span><span class="sxs-lookup"><span data-stu-id="a3be9-122">The Recommendation service uses the data to train recommendation models for the **People also like**, **Frequently bought together**, **New**, **Best selling**, and **Trending** lists.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a3be9-123">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="a3be9-123">Additional resources</span></span>

[<span data-ttu-id="a3be9-124">Habilitar recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="a3be9-124">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="a3be9-125">Criar curated listas organizadas de recomendação de produtos</span><span class="sxs-lookup"><span data-stu-id="a3be9-125">Create curated product recommendation lists</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="a3be9-126">Gerenciar resultados da recomendação de produtos com base em IA-ML</span><span class="sxs-lookup"><span data-stu-id="a3be9-126">Manage AI-ML-based product recommendation results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="a3be9-127">Adicionar listas de recomendações de produto às páginas</span><span class="sxs-lookup"><span data-stu-id="a3be9-127">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)