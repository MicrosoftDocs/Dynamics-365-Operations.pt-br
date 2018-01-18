---
title: Funcionalidade do call center
description: "Este tópico fornece uma visão geral da funcionalidade de vendas do call center no Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailMCRChannelDetailPage, MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16361
ms.assetid: c8ed2ba4-8d06-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: d9b080ff46a0fbc73ed4f8fa3f03d71e9d758cc2
ms.openlocfilehash: 55bad891f9295eca6b0bf39847ede890b7294370
ms.contentlocale: pt-br
ms.lasthandoff: 01/17/2018

---

# <a name="call-center-functionality"></a><span data-ttu-id="8ebe8-103">Funcionalidade do call center</span><span class="sxs-lookup"><span data-stu-id="8ebe8-103">Call center functionality</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="8ebe8-104">Este artigo fornece uma visão geral da funcionalidade de vendas do call center no Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="8ebe8-104">This article provides an overview of the call center sales functionality in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="8ebe8-105">O Dynamics 365 for Retail também oferece suporte a call centers como um tipo de canal de varejo.</span><span class="sxs-lookup"><span data-stu-id="8ebe8-105">Dynamics 365 for Retail supports call centers as a type of retail channel.</span></span> <span data-ttu-id="8ebe8-106">Em um call center, os trabalhadores recebem ordens de clientes pelo telefone e criam ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="8ebe8-106">In a call center, workers take orders from customers over the phone and create sales orders.</span></span> <span data-ttu-id="8ebe8-107">A funcionalidade do call center inclui recursos criados para facilitar a obtenção de ordens por telefone e controlar o atendimento ao cliente durante todo o processo de preenchimento da ordem.</span><span class="sxs-lookup"><span data-stu-id="8ebe8-107">Call center functionality includes features that are designed to make it easier to take phone orders and handle customer service throughout the order fulfillment process.</span></span> <span data-ttu-id="8ebe8-108">Por exemplo, os trabalhadores do call center podem inserir informações de pagamento diretamente na ordem de venda, bem como podem exibir um resumo detalhado de encargos e pagamentos antes de enviar a ordem.</span><span class="sxs-lookup"><span data-stu-id="8ebe8-108">For example, call center workers can enter payment information directly into the sales order, and can view a detailed summary of charges and payments before they submit the order.</span></span> <span data-ttu-id="8ebe8-109">Os trabalhadores têm opções para controlar a definição de preços e podem acessar vários dados sobre clientes, produtos e preços na página **Ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="8ebe8-109">Workers also have options for controlling pricing, and can access various data about customers, products, and prices from the **Sales order** page.</span></span> <span data-ttu-id="8ebe8-110">Além disso, os call centers aprimoraram a funcionalidade para controlar o histórico do cliente e o status da ordem.</span><span class="sxs-lookup"><span data-stu-id="8ebe8-110">Additionally, call centers have enhanced functionality for tracking customer history and order status.</span></span> <span data-ttu-id="8ebe8-111">Cada call center pode ter seus próprios usuários, métodos de pagamento, grupos de preços, dimensões financeiras e modos de entrega.</span><span class="sxs-lookup"><span data-stu-id="8ebe8-111">Each call center can have its own users, payment methods, price groups, financial dimensions, and modes of delivery.</span></span> <span data-ttu-id="8ebe8-112">Você pode configurar essas opções ao criar o call center.</span><span class="sxs-lookup"><span data-stu-id="8ebe8-112">You can configure these options when you create the call center.</span></span> <span data-ttu-id="8ebe8-113">Você também pode usar a página **Call center** para habilitar ou desabilitar os seguintes grupos de recursos exclusivos de call centers:</span><span class="sxs-lookup"><span data-stu-id="8ebe8-113">Additionally, you can use the **Call center** page to enable or disable the following groups of features that are unique to call centers:</span></span>

-   <span data-ttu-id="8ebe8-114">**Conclusão da ordem** – Este grupo inclui recursos relativos a pagamentos e conclusão de ordens na página **Ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="8ebe8-114">**Order completion** – This group includes features that are related to payments and order completion on the **Sales order** page.</span></span>
-   <span data-ttu-id="8ebe8-115">**Venda direta** – Este grupo inclui recursos relativos aos códigos fonte, scripts e solicitações de catálogo.</span><span class="sxs-lookup"><span data-stu-id="8ebe8-115">**Directed selling** – This group includes features that are related to source codes, scripts, and catalog requests.</span></span>

<span data-ttu-id="8ebe8-116">Após você habilitar esses recursos nas configurações do call center, eles são disponibilizados na página **Ordem de venda** para usuários associados ao call center.</span><span class="sxs-lookup"><span data-stu-id="8ebe8-116">After you enable these features in the call center settings, they are available on the **Sales order** page to users who are associated with the call center.</span></span> <span data-ttu-id="8ebe8-117">A maioria desses recursos exige configuração adicional antes que eles possam ser usados.</span><span class="sxs-lookup"><span data-stu-id="8ebe8-117">Most of these features require additional setup before they can be used.</span></span> <span data-ttu-id="8ebe8-118">Para que os usuários possam criar ordens do call center, você deve adicionar esses usuários ao call center como usuários do call center.</span><span class="sxs-lookup"><span data-stu-id="8ebe8-118">Before users can create call center orders, you must add those users to the call center as call center users.</span></span> <span data-ttu-id="8ebe8-119">Esta etapa habilita a configuração e a funcionalidade específicas de canal do call center.</span><span class="sxs-lookup"><span data-stu-id="8ebe8-119">This step enables the call center channel-specific configuration and functionality.</span></span> <span data-ttu-id="8ebe8-120">Veja alguns exemplos da funcionalidade que é disponibilizada:</span><span class="sxs-lookup"><span data-stu-id="8ebe8-120">Here are some examples of the functionality that becomes available:</span></span>

-   <span data-ttu-id="8ebe8-121">A venda guiada fornece opções de configuração para que scripts de televendas e imagens de produtos ajudem e orientem os auxiliares de vendas quando receberem ordens.</span><span class="sxs-lookup"><span data-stu-id="8ebe8-121">Guided selling provides configuration options for tele-sales scripts and product images to help and guide sales clerks while they take orders.</span></span>
-   <span data-ttu-id="8ebe8-122">As ordens só podem ser concluídas quando os auxiliares de vendas capturam pelo menos um método de pagamento.</span><span class="sxs-lookup"><span data-stu-id="8ebe8-122">Orders can't be completed until sales clerks have captured at least one payment method.</span></span>
-   <span data-ttu-id="8ebe8-123">Regras de venda adicional e de venda cruzada podem ser configuradas para solicitar auxiliares de vendas que promovam produtos específicos para o cliente.</span><span class="sxs-lookup"><span data-stu-id="8ebe8-123">Upsell and cross-sell rules can be configured to prompt sales clerks to promote specific products to the customer.</span></span>
-   <span data-ttu-id="8ebe8-124">Os auxiliares de vendas podem capturar o código de origem para o catálogo no qual um cliente faz pedidos.</span><span class="sxs-lookup"><span data-stu-id="8ebe8-124">Sales clerks can capture the source code for the catalog that a customer is ordering from.</span></span>
-   <span data-ttu-id="8ebe8-125">Os auxiliares de vendas podem adicionar cupons de um varejista à ordem.</span><span class="sxs-lookup"><span data-stu-id="8ebe8-125">Sales clerks can add a retailer's coupons to the order.</span></span>
-   <span data-ttu-id="8ebe8-126">Os auxiliares de vendas podem vender programas de continuidade.</span><span class="sxs-lookup"><span data-stu-id="8ebe8-126">Sales clerks can sell continuity programs.</span></span>
-   <span data-ttu-id="8ebe8-127">As ordens podem ser colocadas em espera, manual ou automaticamente, para indicar que a investigação adicional é necessária antes de a ordem ser processada.</span><span class="sxs-lookup"><span data-stu-id="8ebe8-127">Orders can be put on hold manually or automatically, to indicate that additional investigation is required before the order can be processed.</span></span>





