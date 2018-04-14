---
title: "Definir descontos específicos do canal"
description: "Os fornecedores geralmente definem descontos diferentes em canais diferentes. Este tópico examina os conceitos que você precisa saber para criar um desconto para um canal específico."
author: scott-tucker
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailAffiliationPriceGroup, RetailCatalogPriceGroup, RetailChannelPriceGroup, RetailDiscountPriceGroup, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailStoreItemPriceList, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16401
ms.assetid: d807fd51-86aa-47a0-8e00-6c5ddd21ff6b
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 34039b298e8994e50a7c06ef034698e8c1264389
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="define-channel-specific-discounts"></a><span data-ttu-id="7de53-104">Definir descontos específicos do canal</span><span class="sxs-lookup"><span data-stu-id="7de53-104">Define channel-specific discounts</span></span>

[!INCLUDE [banner](includes/banner.md)]

<span data-ttu-id="7de53-105">Os fornecedores geralmente definem descontos diferentes em canais diferentes.</span><span class="sxs-lookup"><span data-stu-id="7de53-105">Retailers often set different discounts in different channels.</span></span> <span data-ttu-id="7de53-106">Este tópico examina os conceitos que você precisa saber para criar um desconto para um canal específico.</span><span class="sxs-lookup"><span data-stu-id="7de53-106">This topic reviews the concepts you need to know to create a discount for a specific channel.</span></span> 

<a name="channel-specific-discounts"></a><span data-ttu-id="7de53-107">Descontos específicos do canal</span><span class="sxs-lookup"><span data-stu-id="7de53-107">Channel-specific discounts</span></span>
--------------------------

<span data-ttu-id="7de53-108">Os fornecedores geralmente oferecem descontos diferentes em canais diferentes.</span><span class="sxs-lookup"><span data-stu-id="7de53-108">Retailers often offer different discounts in different channels.</span></span> <span data-ttu-id="7de53-109">Isso pode ser feito para lidar com as condições dos mercados locais ou com os varejistas concorrentes.</span><span class="sxs-lookup"><span data-stu-id="7de53-109">This is may be done to address local market conditions or to deal with competing retailers.</span></span>

<span data-ttu-id="7de53-110">O Microsoft Dynamics 365 for Retail usa grupos de preços para definir descontos específicos do canal.</span><span class="sxs-lookup"><span data-stu-id="7de53-110">Microsoft Dynamics 365 for Retail uses price groups to define channel-specific discounts.</span></span> <span data-ttu-id="7de53-111">Grupos de preços podem ser atribuídos a uma ou mais das seguintes entidades: canais, catálogos, afiliações e programas de fidelidade.</span><span class="sxs-lookup"><span data-stu-id="7de53-111">Price groups can be assigned to one or more of the following entities: channels, catalogs, affiliations, and loyalty programs.</span></span> <span data-ttu-id="7de53-112">Este artigo aborda canais, mas os mesmos conceitos se aplicam a descontos de catálogo, descontos de afiliações e descontos de fidelidade.</span><span class="sxs-lookup"><span data-stu-id="7de53-112">This article discusses channels, but the same concepts apply to catalog discounts, affiliations discounts, and loyalty discounts.</span></span>

## <a name="price-groups"></a><span data-ttu-id="7de53-113">Grupos de preços</span><span class="sxs-lookup"><span data-stu-id="7de53-113">Price groups</span></span>

<span data-ttu-id="7de53-114">[![Grupos de preços](./media/price-groups-1024x608.png)](./media/price-groups.png)</span><span class="sxs-lookup"><span data-stu-id="7de53-114">[![Price groups](./media/price-groups-1024x608.png)](./media/price-groups.png)</span></span>

<span data-ttu-id="7de53-115">O diagrama acima ilustra a relação entre entidades que podem estar em uma transação (canal, catálogo, associação, cliente, cartão-fidelidade) e em vários tipos de descontos que podem ser configurados.</span><span class="sxs-lookup"><span data-stu-id="7de53-115">The diagram above illustrates the relationship between entities that may be on a transaction (channel, catalog, affiliation, customer, loyalty card) and the various discount types that can be configured.</span></span> <span data-ttu-id="7de53-116">Todas as transações ocorrem em um canal, motivo pelo qual a presença do canal em uma transação é garantida.</span><span class="sxs-lookup"><span data-stu-id="7de53-116">All transactions occur in a channel, so the channel is guaranteed to be present on a transaction.</span></span> <span data-ttu-id="7de53-117">As demais entidades são opcionais.</span><span class="sxs-lookup"><span data-stu-id="7de53-117">The remaining entities are optional.</span></span> <span data-ttu-id="7de53-118">Em cada página de dados mestres, há um link para uma página de grupos de preços relacionada na qual é possível ver e adicionar grupos de preços quando necessário.</span><span class="sxs-lookup"><span data-stu-id="7de53-118">On each master data pages there is a link to a related price groups page where you can view and add price groups as needed.</span></span> <span data-ttu-id="7de53-119">Um grupo de preços é usado para relacionar quatro tipos de entidades diferentes a descontos, ajustes de preço e contratos comerciais.</span><span class="sxs-lookup"><span data-stu-id="7de53-119">A price group is used to relate four different types of entities to discounts, price adjustments, and trade agreements.</span></span> <span data-ttu-id="7de53-120">Recomendamos que você elabore uma estratégia para nomear seus grupos de preços de modo a mantê-los organizados.</span><span class="sxs-lookup"><span data-stu-id="7de53-120">We recommend that you plan a strategy for how you will name your price groups to keep them organized.</span></span> <span data-ttu-id="7de53-121">Uma das opções é usar um prefixo ou sufixo de letra ou número para distinguir os diferentes tipos.</span><span class="sxs-lookup"><span data-stu-id="7de53-121">One option would be to use a letter or number prefix or suffix to distinguish between the different types.</span></span> <span data-ttu-id="7de53-122">Por exemplo, 1-xxxxx para grupos de preços de canal e 2-xxxxx para grupos de preços de catálogo.</span><span class="sxs-lookup"><span data-stu-id="7de53-122">For example, 1-xxxxx for channel price groups and 2-xxxxx for catalog price groups.</span></span> <span data-ttu-id="7de53-123">Há quatro páginas de consulta com foco em cada uma das entidades de varejo que podem ter descontos associados a elas.</span><span class="sxs-lookup"><span data-stu-id="7de53-123">There are four inquiry pages that focus on each of the retail entities that can have discounts associated to them.</span></span>

-   <span data-ttu-id="7de53-124">**Grupos de preços do canal de varejo**- Essa página mostra uma lista de canais e descontos vinculados entre si para cada grupo de preço.</span><span class="sxs-lookup"><span data-stu-id="7de53-124">**Retail channel price groups** - This page shows a list of channels and discounts linked together for each price group.</span></span>
-   <span data-ttu-id="7de53-125">**Grupos de preços de catálogo**- Essa página mostra uma lista de catálogos e descontos vinculados entre si para cada grupo de preço.</span><span class="sxs-lookup"><span data-stu-id="7de53-125">**Catalog price groups** - This page shows a list of catalogs and discounts linked together for each price group.</span></span>
-   <span data-ttu-id="7de53-126">**Grupos de preços de fidelidade**- Essa página mostra uma lista de programas de fidelidade e descontos vinculados entre si para cada grupo de preço.</span><span class="sxs-lookup"><span data-stu-id="7de53-126">**Loyalty price groups** - This page shows a list of loyalty programs and discounts linked together for each price group.</span></span>
-   <span data-ttu-id="7de53-127">**Grupos de preços de afiliação**- Essa página mostra uma lista de afiliações e descontos vinculados entre si para cada grupo de preço.</span><span class="sxs-lookup"><span data-stu-id="7de53-127">**Affiliation price groups** - This page shows a list of affiliations and discounts linked together for each price group.</span></span>

## <a name="example-channel-discount-set-up"></a><span data-ttu-id="7de53-128">Exemplo de configuração de desconto de canal</span><span class="sxs-lookup"><span data-stu-id="7de53-128">Example channel discount set up</span></span>
<span data-ttu-id="7de53-129">O exemplo a seguir ilustra as tarefas envolvidas na configuração de um desconto de canal.</span><span class="sxs-lookup"><span data-stu-id="7de53-129">The following example illustrates the tasks involved in setting up a channel discount.</span></span>

1.  <span data-ttu-id="7de53-130">No exemplo, você tem um canal denominado **Houston** e criará um desconto denominado **Volta à escola**.</span><span class="sxs-lookup"><span data-stu-id="7de53-130">For this example, you have a channel called **Houston**, and you're going to create a new discount called **Back-to-School.**</span></span>
2.  <span data-ttu-id="7de53-131">Como a estratégia de preços e descontos inclui a possibilidade de descontos de canal, você sempre criará um grupo de preços específico do canal quando criar um canal.</span><span class="sxs-lookup"><span data-stu-id="7de53-131">Because the pricing and discount strategy includes the possibility of channel discounts, you always create a channel-specific price group when you create a channel.</span></span>
3.  <span data-ttu-id="7de53-132">Você tem o grupo de preços **Houston-PG** que é atribuído ao canal **Houston**.</span><span class="sxs-lookup"><span data-stu-id="7de53-132">You have the price group **Houston-PG** and it is assigned to the **Houston** channel.</span></span>
4.  <span data-ttu-id="7de53-133">Após a criação do desconto **Volta à escola**, você precisa clicar em **Grupos de preços** na parte superior da página **Desconto**.</span><span class="sxs-lookup"><span data-stu-id="7de53-133">After you create the new **Back-to-School** discount, you need to click **Price groups** on the top of the **Discount** page.</span></span> <span data-ttu-id="7de53-134">A página **Grupos de preços de desconto** será aberta.</span><span class="sxs-lookup"><span data-stu-id="7de53-134">The **Discount price groups** page will open.</span></span> <span data-ttu-id="7de53-135">Em seguida, clique em **Novo** e selecione o grupo de preços **Houston-GP**.</span><span class="sxs-lookup"><span data-stu-id="7de53-135">Next, click **New** and select the **Houston-PG** price group.</span></span>
5.  <span data-ttu-id="7de53-136">Agora você pode habilitar o desconto e enviá-lo por push ao canal.</span><span class="sxs-lookup"><span data-stu-id="7de53-136">Now you can enable the discount and push it to the channel.</span></span>



<a name="see-also"></a><span data-ttu-id="7de53-137">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7de53-137">See also</span></span>
--------

[<span data-ttu-id="7de53-138">Ajustes de preço e descontos</span><span class="sxs-lookup"><span data-stu-id="7de53-138">Price adjustments and discounts</span></span>](price-adjustments-discounts.md)




