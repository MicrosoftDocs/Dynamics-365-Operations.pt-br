---
title: Habilitar recomendações de produtos
description: Este tópico explica como fazer recomendações de produto com base aprendizado de máquina de inteligência artificial (AI-ML) disponível para Microsoft Dynamics 365 Commerce.
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
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ecda571a356c6968196d09cc19923105cf4544ab
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770130"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="19c67-103">Habilitar recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="19c67-103">Enable product recommendations</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="19c67-104">Este tópico explica como fazer recomendações de produto com base aprendizado de máquina de inteligência artificial (AI-ML) disponível para Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="19c67-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="19c67-105">Para obter mais informações sobre listas de recomendações de produtos, consulte [Visão geral das recomendações de produtos.](product-recommendations.md)</span><span class="sxs-lookup"><span data-stu-id="19c67-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="19c67-106">Recomendações de pré-verificação</span><span class="sxs-lookup"><span data-stu-id="19c67-106">Recommendations pre-check</span></span>
<span data-ttu-id="19c67-107">Antes de habilitar, observe que as recomendações de produto são suportadas apenas para clientes F&O compatível com versão 10.0.6 e migraram seu armazenamento usando BDL.</span><span class="sxs-lookup"><span data-stu-id="19c67-107">Before enabling, please note that product recommendations are only supported for F&O customers supporting build 10.0.6 and have migrated their storage to using BDL.</span></span> 

<span data-ttu-id="19c67-108">Adicionalmente, verifique se as medições do RetailSale estão habilitadas.</span><span class="sxs-lookup"><span data-stu-id="19c67-108">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="19c67-109">Para saber mais sobre o processo de instalação, vá [aqui.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)</span><span class="sxs-lookup"><span data-stu-id="19c67-109">To Learn more about this set up process, go [here.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)</span></span>


## <a name="turn-on-recommendations"></a><span data-ttu-id="19c67-110">Ative as recomendações</span><span class="sxs-lookup"><span data-stu-id="19c67-110">Turn on recommendations</span></span>

<span data-ttu-id="19c67-111">Para ativar as recomendações de produtos, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="19c67-111">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="19c67-112">Acesse **Varejo** &gt; **Recomendações de produto** &gt; **Parâmetros de recomendação**.</span><span class="sxs-lookup"><span data-stu-id="19c67-112">Go to **Retail** &gt; **Product recommendations** &gt; **Recommendation parameters**.</span></span>
1. <span data-ttu-id="19c67-113">Na lista de parâmetros de varejo compartilhados, selecione **Listas de recomendação**.</span><span class="sxs-lookup"><span data-stu-id="19c67-113">In the list of retail shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="19c67-114">Defina a opção **Habilitar recomendações** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="19c67-114">Set the **Enable recommendations** option to **Yes**.</span></span>

![habilitar recomendações de produtos](./media/enableproductrecommendations.png)

> [!NOTE]
> <span data-ttu-id="19c67-116">Este procedimento inicia o processo de geração de listas recomendação de produto.</span><span class="sxs-lookup"><span data-stu-id="19c67-116">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="19c67-117">Até várias horas poderá ser necessário antes que as listas estejam disponíveis e possam ser vistas no ponto de venda (PDV) ou em Dynamics 365 for Commerce.</span><span class="sxs-lookup"><span data-stu-id="19c67-117">Up to several hours might be required before the lists are available and can be seen at the point of sale (POS) or in Dynamics 365 for Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="19c67-118">Configurar parâmetros da lista de recomendação</span><span class="sxs-lookup"><span data-stu-id="19c67-118">Configure recommendation list parameters</span></span>
<span data-ttu-id="19c67-119">Por padrão, a lista de recomendação de produtos baseada em AI-ML fornece valores sugeridos.</span><span class="sxs-lookup"><span data-stu-id="19c67-119">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="19c67-120">Você pode alterar os valores sugeridos padrão para se adequar ao fluxo de seus negócios.</span><span class="sxs-lookup"><span data-stu-id="19c67-120">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="19c67-121">Para saber mais sobre como alterar os parâmetros padrão, acesse [Gerenciar resultados de recomendação de produto baseado em AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="19c67-121">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="19c67-122">Mostrar recomendações em dispositivos POS</span><span class="sxs-lookup"><span data-stu-id="19c67-122">Show recommendations on POS devices</span></span>
<span data-ttu-id="19c67-123">Após habilitar recomendações no back office, o painel de recomendações deve ser adicionado à tela PDV de controle por meio da ferramenta de layout.</span><span class="sxs-lookup"><span data-stu-id="19c67-123">After enabling recommendations in the back office, the recommendations pannel must be added to the control POS screen via the layout tool.</span></span> <span data-ttu-id="19c67-124">Para saber mais sobre esse processo, vá [aqui.](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)</span><span class="sxs-lookup"><span data-stu-id="19c67-124">To learn about this process, go [here.](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)</span></span>


## <a name="additional-resources"></a><span data-ttu-id="19c67-125">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="19c67-125">Additional resources</span></span>

[<span data-ttu-id="19c67-126">Visão geral de recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="19c67-126">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="19c67-127">Adicionar listas de recomendações de produto às páginas</span><span class="sxs-lookup"><span data-stu-id="19c67-127">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="19c67-128">Adicionar painel de recomendações a dispositivos POS</span><span class="sxs-lookup"><span data-stu-id="19c67-128">Add recommendations panel to POS devices</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)


