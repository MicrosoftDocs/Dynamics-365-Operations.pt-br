---
title: Habilitar recomendações de produtos
description: Este tópico explica como fazer recomendações de produto com base aprendizado de máquina de inteligência artificial (AI-ML) disponível para Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 03/12/2020
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
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 879fccb063ca0b74e0f022a9edf6a15f7d1311ae
ms.sourcegitcommit: 1e7e7c4bc197b0a42e4d53d2a54600a2fb125b69
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/13/2020
ms.locfileid: "3127873"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="8b2d4-103">Habilitar recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="8b2d4-103">Enable product recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8b2d4-104">Este tópico explica como fazer recomendações de produto com base aprendizado de máquina de inteligência artificial (AI-ML) disponível para Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8b2d4-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="8b2d4-105">Para obter mais informações sobre listas de recomendações de produtos, consulte [Visão geral das recomendações de produtos.](product-recommendations.md)</span><span class="sxs-lookup"><span data-stu-id="8b2d4-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="8b2d4-106">Recomendações de pré-verificação</span><span class="sxs-lookup"><span data-stu-id="8b2d4-106">Recommendations pre-check</span></span>

<span data-ttu-id="8b2d4-107">Antes de habilitar, observe que as recomendações de produto são suportadas apenas para clientes do Commerce que migraram seu armazenamento para usar o Azure Data Lake Storage (ADLS).</span><span class="sxs-lookup"><span data-stu-id="8b2d4-107">Before enabling, please note that product recommendations are only supported for Commerce customers who have migrated their storage to using Azure Data Lake Storage (ADLS).</span></span> 

<span data-ttu-id="8b2d4-108">Para ver etapas de como habilitar o ADLS, consulte [Como habilitar o ADLS em um ambiente do Dynamics 365](enable-ADLS-environment.md).</span><span class="sxs-lookup"><span data-stu-id="8b2d4-108">For steps on enabling ADLS, see [How to enable ADLS in a Dynamics 365 environment](enable-ADLS-environment.md).</span></span>

<span data-ttu-id="8b2d4-109">Adicionalmente, verifique se as medições do RetailSale estão habilitadas.</span><span class="sxs-lookup"><span data-stu-id="8b2d4-109">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="8b2d4-110">Para saber mais sobre esse processo de configuração, clique [aqui.](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures)</span><span class="sxs-lookup"><span data-stu-id="8b2d4-110">To learn more about this set up process, go [here.](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures)</span></span>


## <a name="turn-on-recommendations"></a><span data-ttu-id="8b2d4-111">Ative as recomendações</span><span class="sxs-lookup"><span data-stu-id="8b2d4-111">Turn on recommendations</span></span>

<span data-ttu-id="8b2d4-112">Para ativar as recomendações de produtos, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="8b2d4-112">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="8b2d4-113">Acesse **Retail e Commerce &gt; Recomendações de produto &gt; Parâmetros de recomendação**.</span><span class="sxs-lookup"><span data-stu-id="8b2d4-113">Go to **Retail and Commerce &gt; Product recommendations &gt; Recommendation parameters**.</span></span>
1. <span data-ttu-id="8b2d4-114">Na lista de parâmetros compartilhados, selecione **Listas de Recomendação**.</span><span class="sxs-lookup"><span data-stu-id="8b2d4-114">In the list of shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="8b2d4-115">Defina a opção **Habilitar recomendações** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="8b2d4-115">Set the **Enable recommendations** option to **Yes**.</span></span>

![habilitar recomendações de produtos](./media/enableproductrecommendations.png)

> [!NOTE]
> <span data-ttu-id="8b2d4-117">Este procedimento inicia o processo de geração de listas recomendação de produto.</span><span class="sxs-lookup"><span data-stu-id="8b2d4-117">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="8b2d4-118">Até várias horas poderá ser necessário antes que as listas estejam disponíveis e possam ser vistas no ponto de venda (PDV) ou em Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8b2d4-118">Up to several hours might be required before the lists are available and can be seen at the point of sale (POS) or in Dynamics 365 Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="8b2d4-119">Configurar parâmetros da lista de recomendação</span><span class="sxs-lookup"><span data-stu-id="8b2d4-119">Configure recommendation list parameters</span></span>

<span data-ttu-id="8b2d4-120">Por padrão, a lista de recomendação de produtos baseada em AI-ML fornece valores sugeridos.</span><span class="sxs-lookup"><span data-stu-id="8b2d4-120">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="8b2d4-121">Você pode alterar os valores sugeridos padrão para se adequar ao fluxo de seus negócios.</span><span class="sxs-lookup"><span data-stu-id="8b2d4-121">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="8b2d4-122">Para saber mais sobre como alterar os parâmetros padrão, acesse [Gerenciar resultados de recomendação de produto baseado em AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="8b2d4-122">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="8b2d4-123">Mostrar recomendações em dispositivos POS</span><span class="sxs-lookup"><span data-stu-id="8b2d4-123">Show recommendations on POS devices</span></span>

<span data-ttu-id="8b2d4-124">Após habilitar recomendações no back office do Commerce, o painel de recomendações deverá ser adicionado à tela PDV de controle por meio da ferramenta de layout.</span><span class="sxs-lookup"><span data-stu-id="8b2d4-124">After enabling recommendations in Commerce back office, the recommendations panel must be added to the control POS screen using the layout tool.</span></span> <span data-ttu-id="8b2d4-125">Para saber mais sobre esse processo, consulte [Adicionar um controle de recomendações à tela de transações em dispositivos de PDV](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="8b2d4-125">To learn about this process, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span> 

## <a name="enable-personalized-recommendations"></a><span data-ttu-id="8b2d4-126">Habilitar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="8b2d4-126">Enable personalized recommendations</span></span>

<span data-ttu-id="8b2d4-127">Para saber mais sobre como receber recomendações personalizadas, consulte [Habilitar recomendações personalizadas](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="8b2d4-127">To learn more about how to receive personalized recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8b2d4-128">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="8b2d4-128">Additional resources</span></span>

[<span data-ttu-id="8b2d4-129">Visão geral de recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="8b2d4-129">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="8b2d4-130">Habilitar ADLS em um ambiente do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="8b2d4-130">Enable ADLS in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="8b2d4-131">Habilitar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="8b2d4-131">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="8b2d4-132">Cancelar recomendações personalizados</span><span class="sxs-lookup"><span data-stu-id="8b2d4-132">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="8b2d4-133">Adicionar listas de recomendações a um site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="8b2d4-133">Add recommendation lists to an e-Commerce site</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="8b2d4-134">Adicionar recomendações de produtos no PDV</span><span class="sxs-lookup"><span data-stu-id="8b2d4-134">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="8b2d4-135">Adicionar recomendações à tela de transação</span><span class="sxs-lookup"><span data-stu-id="8b2d4-135">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="8b2d4-136">Ajustar os resultados das recomendações de AI-ML</span><span class="sxs-lookup"><span data-stu-id="8b2d4-136">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="8b2d4-137">Criar manualmente recomendações selecionadas</span><span class="sxs-lookup"><span data-stu-id="8b2d4-137">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="8b2d4-138">Criar recomendações com dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="8b2d4-138">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="8b2d4-139">Perguntas frequentes sobre recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="8b2d4-139">Product recommendations FAQ</span></span>](faq-recommendations.md)

