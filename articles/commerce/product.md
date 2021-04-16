---
title: Adicionar recomendações de produtos no PDV
description: Este tópico descreve o uso de recomendações de produtos em um dispositivo de ponto de venda (PDV).
author: bebeale
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: a1a25e3d5bc1cc5c1c7509186451fdfef50dd6cf
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792330"
---
# <a name="add-product-recommendations-on-pos"></a><span data-ttu-id="75cc5-103">Adicionar recomendações de produtos no PDV</span><span class="sxs-lookup"><span data-stu-id="75cc5-103">Add product recommendations on POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="75cc5-104">Essencialmente, as recomendações de produtos são um aplicativo de negócios transformador que abrange todos os espaços do comércio para criar experiências de descoberta de produtos sofisticadas, envolventes e personalizadas.</span><span class="sxs-lookup"><span data-stu-id="75cc5-104">At its core, product recommendations are a transformative business application that span across all commerce spaces to create rich, engaging, and tailored product discovery experiences.</span></span> <span data-ttu-id="75cc5-105">Para implementar esse recurso no PDV, siga as etapas sobre [como adicionar recomendações a seus dispositivos de PDV.](add-recommendations-control-pos-screen.md)</span><span class="sxs-lookup"><span data-stu-id="75cc5-105">To implement this feature on POS, follow the steps on [how to add recommendations to your POS devices.](add-recommendations-control-pos-screen.md)</span></span> 

<span data-ttu-id="75cc5-106">Para obter mais informações sobre os recursos de recomendações de produtos, leia a [visão geral das recomendações de produtos.](../commerce/product-recommendations.md)</span><span class="sxs-lookup"><span data-stu-id="75cc5-106">For more information about product recommendations features, read the [product recommendations overview.](../commerce/product-recommendations.md)</span></span> 

## <a name="scenarios"></a><span data-ttu-id="75cc5-107">Cenários</span><span class="sxs-lookup"><span data-stu-id="75cc5-107">Scenarios</span></span>

<span data-ttu-id="75cc5-108">As recomendações de produtos são habilitadas para os seguintes cenários de PDV.</span><span class="sxs-lookup"><span data-stu-id="75cc5-108">Product recommendations are enabled for the following POS scenarios.</span></span> <span data-ttu-id="75cc5-109">Estão disponíveis no Cloud POS ou Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="75cc5-109">They are available in Cloud POS or Modern POS (MPOS).</span></span>

1. <span data-ttu-id="75cc5-110">Na página **Detalhes de produto**:</span><span class="sxs-lookup"><span data-stu-id="75cc5-110">On the **Product details** page:</span></span>

    - <span data-ttu-id="75cc5-111">Se um associado da loja acessa uma página de **Detalhes de produto** ao procurar por transações anteriores entre diferentes canais, o serviço de recomendações sugere itens adicionais que provavelmente podem ser comprados juntos.</span><span class="sxs-lookup"><span data-stu-id="75cc5-111">If a store associate visits a **Product details** page when looking at previous transactions across different channels, the recommendations service suggests additional items that are likely to be purchased together.</span></span>

    <span data-ttu-id="75cc5-112">[![Recomendações na página Detalhes do produto](./media/proddetails.png)](./media/proddetails.png)</span><span class="sxs-lookup"><span data-stu-id="75cc5-112">[![Recommendations on the Product details page](./media/proddetails.png)](./media/proddetails.png)</span></span>

2. <span data-ttu-id="75cc5-113">Na página **Transação**:</span><span class="sxs-lookup"><span data-stu-id="75cc5-113">On the **Transaction** page:</span></span>

    - <span data-ttu-id="75cc5-114">O mecanismo de recomendação sugere itens com base na lista de itens inteira na cesta que são comprados juntos com frequência.</span><span class="sxs-lookup"><span data-stu-id="75cc5-114">The recommendation engine suggests items based on the entire list of items in the basket that are frequently bought together.</span></span>

    > [!NOTE]
    > <span data-ttu-id="75cc5-115">Para exibir recomendações na página **Transação**, o varejista precisa atualizar o layout da tela no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="75cc5-115">To display recommendations on the **Transaction** page, the retailer needs to update the screen layout in Dynamics 365 Commerce.</span></span> <span data-ttu-id="75cc5-116">O controle das **Recomendações** deve ser colocado na página de **Transação**.</span><span class="sxs-lookup"><span data-stu-id="75cc5-116">The **Recommendations** control must be dropped onto the **Transaction** page.</span></span>

    <span data-ttu-id="75cc5-117">[![Recomendações na página Transação](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span><span class="sxs-lookup"><span data-stu-id="75cc5-117">[![Recommendations on the Transaction page](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span></span>

## <a name="configure-commerce-to-enable-pos-recommendations"></a><span data-ttu-id="75cc5-118">Configurar o Commerce para permitir recomendações PDV</span><span class="sxs-lookup"><span data-stu-id="75cc5-118">Configure Commerce to enable POS recommendations</span></span>

<span data-ttu-id="75cc5-119">Para configurar as recomendações de produtos, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="75cc5-119">To set up product recommendations, follow these steps:</span></span>

1. <span data-ttu-id="75cc5-120">Verifique se o serviço foi atualizado para a **compilação 10.0.6.**</span><span class="sxs-lookup"><span data-stu-id="75cc5-120">Ensure your service has been updated to the **10.0.6 build.**</span></span>
2. <span data-ttu-id="75cc5-121">Sigas as instruções sobre como [habilitar recomendações de produtos](../commerce/enable-product-recommendations.md) para sua empresa.</span><span class="sxs-lookup"><span data-stu-id="75cc5-121">Follow the instructions on how to [enable product recommendations](../commerce/enable-product-recommendations.md) for your business.</span></span>
3. <span data-ttu-id="75cc5-122">Opcional: Para exibir recomendações na tela de transação, vá para **Layout de tela**, escolha seu layout de tela, inicie o **Designer do layout da tela** e depois deixe o controle de **recomendações** onde necessário.</span><span class="sxs-lookup"><span data-stu-id="75cc5-122">Optional: To display recommendations on the transaction screen, go to **Screen Layout**, choose your screen layout, launch the **Screen layout designer**, and then drop the **recommendations** control where needed.</span></span>
4. <span data-ttu-id="75cc5-123">Vá para **Parâmetros de Commerce**, selecione **Aprendizado de máquina** e **Sim** em **Habilitar recomendações de PDV**.</span><span class="sxs-lookup"><span data-stu-id="75cc5-123">Go to **Commerce parameters**, select **Machine-learning**, select **Yes** under **Enable POS recommendations**.</span></span>
5. <span data-ttu-id="75cc5-124">Para consultar recomendações no PDV, rode o trabalho de configuração global **1110**.</span><span class="sxs-lookup"><span data-stu-id="75cc5-124">To see recommendations on POS, run global configuration job **1110**.</span></span> <span data-ttu-id="75cc5-125">Para refletir as alterações feitas ao designer de layout de tela do PDV, rode o trabalho de configuração de canal **1070**.</span><span class="sxs-lookup"><span data-stu-id="75cc5-125">To reflect changes made to POS screen layout designer, run channel configuration job **1070**.</span></span>

## <a name="troubleshoot-issues-where-you-have-product-recommendations-already-enabled"></a><span data-ttu-id="75cc5-126">Solucionar problemas em que as recomendações de produtos já estejam habilitadas</span><span class="sxs-lookup"><span data-stu-id="75cc5-126">Troubleshoot issues where you have Product recommendations already enabled</span></span>

- <span data-ttu-id="75cc5-127">Navegue até **Parâmetros do Commerce** \> **Listas de recomendação** \> **Desabilitar recomendações de produtos** e execute **Trabalho de configuração global \[9999\]**.</span><span class="sxs-lookup"><span data-stu-id="75cc5-127">Navigate to **Commerce Parameters** \> **Recommendation lists** \> **Disable product recommendations** and run **Global configuration job \[9999\]**.</span></span> 
- <span data-ttu-id="75cc5-128">Se você adicionou o **Controle de recomendações** à sua tela de transação usando o **Designer do layout da tela**, remova-o também.</span><span class="sxs-lookup"><span data-stu-id="75cc5-128">If you added the **Recommendations control** to your transaction screen using the **Screen layout designer**, please remove that as well.</span></span>
- <span data-ttu-id="75cc5-129">Se tiver outras dúvidas, confira as [Perguntas frequentes sobre recomendações do produto](../commerce/faq-recommendations.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="75cc5-129">If you have additional questions, check out the [Product recommendations FAQ](../commerce/faq-recommendations.md) for more information.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="75cc5-130">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="75cc5-130">Additional resources</span></span>

[<span data-ttu-id="75cc5-131">Visão geral das recomendações dos produtos</span><span class="sxs-lookup"><span data-stu-id="75cc5-131">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="75cc5-132">Habilitar Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="75cc5-132">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="75cc5-133">Habilitar recomendações dos produtos</span><span class="sxs-lookup"><span data-stu-id="75cc5-133">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="75cc5-134">Habilitar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="75cc5-134">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="75cc5-135">Cancelar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="75cc5-135">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="75cc5-136">Habilitar recomendações de "comprar looks semelhantes"</span><span class="sxs-lookup"><span data-stu-id="75cc5-136">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="75cc5-137">Adicionar recomendações à tela de transações</span><span class="sxs-lookup"><span data-stu-id="75cc5-137">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="75cc5-138">Ajustar os resultados das recomendações de AI-ML</span><span class="sxs-lookup"><span data-stu-id="75cc5-138">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="75cc5-139">Criar manualmente recomendações selecionadas</span><span class="sxs-lookup"><span data-stu-id="75cc5-139">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="75cc5-140">Criar recomendações com dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="75cc5-140">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="75cc5-141">Perguntas frequentes sobre recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="75cc5-141">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]