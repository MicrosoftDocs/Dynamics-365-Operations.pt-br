---
title: Recomendações de produtos no PDV
description: Este tópico descreve o uso de recomendações de produtos em um dispositivo de ponto de venda (PDV).
author: bebeale
manager: AnnBe
ms.date: 10/01/19
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 98c84e987c40adf136d0240117f7b0f119bf2f59
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811108"
---
# <a name="product-recommendations-on-pos"></a><span data-ttu-id="b9cbf-103">Recomendações de produtos no PDV</span><span class="sxs-lookup"><span data-stu-id="b9cbf-103">Product recommendations on POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b9cbf-104">Essencialmente, as recomendações de produtos são um aplicativo de negócios transformador que abrange todos os espaços de varejo para criar experiências de descoberta de produtos sofisticadas, envolventes e personalizadas.</span><span class="sxs-lookup"><span data-stu-id="b9cbf-104">At its core, product Recommendations are a transformative business application that span across all retail spaces to create rich, engaging, and tailored product discovery experiences.</span></span> <span data-ttu-id="b9cbf-105">Para implementar esse recurso no PDV, siga as etapas sobre [como adicionar recomendações a seus dispositivos de PDV.](add-recommendations-control-pos-screen.md)</span><span class="sxs-lookup"><span data-stu-id="b9cbf-105">To implement this feature on POS, follow the steps on [how to add recommendations to your POS devices.](add-recommendations-control-pos-screen.md)</span></span> 

<span data-ttu-id="b9cbf-106">Para obter mais informações sobre os recursos de recomendações de produtos, leia a [visão geral das recomendações de produtos.](../commerce/product-recommendations.md)</span><span class="sxs-lookup"><span data-stu-id="b9cbf-106">For more information about product recommendations features, read the [product recommendations overview.](../commerce/product-recommendations.md)</span></span> 

## <a name="scenarios"></a><span data-ttu-id="b9cbf-107">Cenários</span><span class="sxs-lookup"><span data-stu-id="b9cbf-107">Scenarios</span></span>

<span data-ttu-id="b9cbf-108">As recomendações de produtos são habilitadas para os seguintes cenários de PDV.</span><span class="sxs-lookup"><span data-stu-id="b9cbf-108">Product recommendations are enabled for the following POS scenarios.</span></span> <span data-ttu-id="b9cbf-109">Estão disponíveis no Cloud POS ou Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="b9cbf-109">They are available in Cloud POS or Modern POS (MPOS).</span></span>

1. <span data-ttu-id="b9cbf-110">Na página **Detalhes de produto**:</span><span class="sxs-lookup"><span data-stu-id="b9cbf-110">On the **Product details** page:</span></span>

    - <span data-ttu-id="b9cbf-111">Se um associado da loja acessa uma página de **Detalhes de produto** ao procurar por transações anteriores entre diferentes canais, o serviço de recomendações sugere itens adicionais que provavelmente podem ser comprados juntos.</span><span class="sxs-lookup"><span data-stu-id="b9cbf-111">If a store associate visits a **Product details** page when looking at previous transactions across different channels, the recommendations service suggests additional items that are likely to be purchased together.</span></span>

    <span data-ttu-id="b9cbf-112">[![Recomendações na página Detalhes do produto](./media/proddetails.png)](./media/proddetails.png)</span><span class="sxs-lookup"><span data-stu-id="b9cbf-112">[![Recommendations on the Product details page](./media/proddetails.png)](./media/proddetails.png)</span></span>

2. <span data-ttu-id="b9cbf-113">Na página **Transação**:</span><span class="sxs-lookup"><span data-stu-id="b9cbf-113">On the **Transaction** page:</span></span>

    - <span data-ttu-id="b9cbf-114">O mecanismo de recomendação sugere itens com base na lista de itens inteira na cesta que são comprados juntos com frequência.</span><span class="sxs-lookup"><span data-stu-id="b9cbf-114">The recommendation engine suggests items based on the entire list of items in the basket that are frequently bought together.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b9cbf-115">Para exibir recomendações na página **Transação**, o varejista precisa atualizar o layout da tela no Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="b9cbf-115">To display recommendations on the **Transaction** page, the retailer needs to update the screen layout in Dynamics 365 for Retail.</span></span> <span data-ttu-id="b9cbf-116">O controle das **Recomendações** deve ser colocado na página de **Transação**.</span><span class="sxs-lookup"><span data-stu-id="b9cbf-116">The **Recommendations** control must be dropped onto the **Transaction** page.</span></span>

    <span data-ttu-id="b9cbf-117">[![Recomendações na página Transação](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span><span class="sxs-lookup"><span data-stu-id="b9cbf-117">[![Recommendations on the Transaction page](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span></span>

## <a name="configure-dynamics-365-retail-to-enable-pos-recommendations"></a><span data-ttu-id="b9cbf-118">Configurar o Dynamics 365 Retail para permitir recomendações PDV</span><span class="sxs-lookup"><span data-stu-id="b9cbf-118">Configure Dynamics 365 Retail to enable POS recommendations</span></span>

<span data-ttu-id="b9cbf-119">Para configurar as recomendações de produtos, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b9cbf-119">To set up product recommendations, follow these steps:</span></span>

1. <span data-ttu-id="b9cbf-120">Verifique se o serviço foi atualizado para a **compilação 10.0.6.**</span><span class="sxs-lookup"><span data-stu-id="b9cbf-120">Ensure your service has been updated to the **10.0.6 build.**</span></span>
2. <span data-ttu-id="b9cbf-121">Sigas as instruções sobre como [habilitar recomendações de produtos](../commerce/enable-product-recommendations.md) para sua empresa.</span><span class="sxs-lookup"><span data-stu-id="b9cbf-121">Follow the instructions on how to [enable product recommendations](../commerce/enable-product-recommendations.md) for your business.</span></span>
3. <span data-ttu-id="b9cbf-122">Opcional: Para exibir recomendações na tela de transação, vá para **Layout de tela**, escolha seu layout de tela, inicie o **Designer do layout da tela** e depois deixe o controle de **recomendações** onde necessário.</span><span class="sxs-lookup"><span data-stu-id="b9cbf-122">Optional: To display recommendations on the transaction screen, go to **Screen Layout**, choose your screen layout, launch the **Screen layout designer**, and then drop the **recommendations** control where needed.</span></span>
4. <span data-ttu-id="b9cbf-123">Vá para **Parâmetros de varejo**, selecione **Aprendizado de máquina**, selecione **Sim** em **Habilitar recomendações de PDV**.</span><span class="sxs-lookup"><span data-stu-id="b9cbf-123">Go to **Retail parameters**, select **Machine-learning**, select **Yes** under **Enable POS recommendations**.</span></span>
5. <span data-ttu-id="b9cbf-124">Para consultar recomendações no PDV, rode o trabalho de configuração global **1110**.</span><span class="sxs-lookup"><span data-stu-id="b9cbf-124">To see recommendations on POS, run global configuration job **1110**.</span></span> <span data-ttu-id="b9cbf-125">Para refletir as alterações feitas ao designer de layout de tela do PDV, rode o trabalho de configuração de canal **1070**.</span><span class="sxs-lookup"><span data-stu-id="b9cbf-125">To reflect changes made to POS screen layout designer, run channel configuration job **1070**.</span></span>



## <a name="troubleshoot-issues-where-you-have-product-recommendations-already-enabled"></a><span data-ttu-id="b9cbf-126">Solucionar problemas em que as recomendações de produtos já estejam habilitadas</span><span class="sxs-lookup"><span data-stu-id="b9cbf-126">Troubleshoot issues where you have Product recommendations already enabled</span></span>

- <span data-ttu-id="b9cbf-127">Navegue até **Parâmetros de Varejo** \> **Listas de recomendação** \> **Desabilitar recomendações de produtos** e execute **Trabalho de configuração global \[9999\]**.</span><span class="sxs-lookup"><span data-stu-id="b9cbf-127">Navigate to **Retail Parameters** \> **Recommendation lists** \> **Disable product recommendations** and run **Global configuration job \[9999\]**.</span></span> 
- <span data-ttu-id="b9cbf-128">Se você adicionou o **Controle de recomendações** à sua tela de transação usando o **Designer do layout da tela**, remova-o também.</span><span class="sxs-lookup"><span data-stu-id="b9cbf-128">If you added the **Recommendations control** to your transaction screen using the **Screen layout designer**, please remove that as well.</span></span>
- <span data-ttu-id="b9cbf-129">Se tiver outras dúvidas, confira as [Perguntas frequentes sobre recomendações do produto](../commerce/faq-recommendations.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b9cbf-129">If you have additional questions, check out the [Product recommendations FAQ](../commerce/faq-recommendations.md) for more information.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b9cbf-130">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b9cbf-130">Additional resources</span></span>

[<span data-ttu-id="b9cbf-131">Adicionar um controle de recomendações à tela de transação em dispositivos do PDV</span><span class="sxs-lookup"><span data-stu-id="b9cbf-131">Add a recommendations control to the transaction screen on POS devices</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="b9cbf-132">Visão geral de recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="b9cbf-132">Product recommendations overview</span></span>](../commerce/product-recommendations.md)

[<span data-ttu-id="b9cbf-133">Habilitar recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="b9cbf-133">Enable product recommendations</span></span>](../commerce/enable-product-recommendations.md) 