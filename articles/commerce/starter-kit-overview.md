---
title: Visão geral da biblioteca de módulos
description: Este tópico fornece uma visão geral da biblioteca de módulos do Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4b3440c046ff055c8afa012c80c56aba741fef27
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985552"
---
# <a name="module-library-overview"></a><span data-ttu-id="0be6f-103">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="0be6f-103">Module library overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0be6f-104">Este tópico fornece uma visão geral da biblioteca de módulos do Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0be6f-104">This topic presents an overview of the Microsoft Dynamics 365 Commerce module library.</span></span>

## <a name="overview"></a><span data-ttu-id="0be6f-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="0be6f-105">Overview</span></span>

<span data-ttu-id="0be6f-106">A biblioteca de módulos do Dynamics 365 Commerce é um conjunto de módulos que pode ser usado para criar um site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="0be6f-106">The Dynamics 365 Commerce module library is a collection of modules that can be used to build an e-Commerce website.</span></span> <span data-ttu-id="0be6f-107">Os módulos têm tanto aspectos da interface do usuário (IU) quanto do comportamento funcional.</span><span class="sxs-lookup"><span data-stu-id="0be6f-107">Modules have both user interface (UI) aspects and functional behavior aspects.</span></span>

<span data-ttu-id="0be6f-108">Os temas podem ser aplicados aos módulos na biblioteca de módulos para alterar a aparência.</span><span class="sxs-lookup"><span data-stu-id="0be6f-108">Themes can be applied to the modules in the module library to change their look and feel.</span></span> <span data-ttu-id="0be6f-109">Os temas usam Folhas de Estilos em Cascata (CSS).</span><span class="sxs-lookup"><span data-stu-id="0be6f-109">The themes use Cascading Style Sheets (CSS).</span></span> <span data-ttu-id="0be6f-110">Um tema para um site de comércio eletrônico fictício chamado "Fabrikam" é fornecido como parte da biblioteca de módulos e pode ser usado como uma referência.</span><span class="sxs-lookup"><span data-stu-id="0be6f-110">A theme for a fictitious e-Commerce site that is named "Fabrikam" is provided as part of the module library and can be used as a reference.</span></span>

## <a name="module-library-modules"></a><span data-ttu-id="0be6f-111">Módulos da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="0be6f-111">Module library modules</span></span>

<span data-ttu-id="0be6f-112">Os seguintes tipos de módulos são fornecidos na biblioteca de módulos:</span><span class="sxs-lookup"><span data-stu-id="0be6f-112">The following types of modules are provided in the module library:</span></span>

- <span data-ttu-id="0be6f-113">**Módulo de contêiner** – Um módulo do contêiner é um módulo simples que atua como um host de outros módulos.</span><span class="sxs-lookup"><span data-stu-id="0be6f-113">**Container module** – A container module is a simple module that acts as a host for other modules.</span></span> <span data-ttu-id="0be6f-114">Ele controla o layout de módulos que estão dentro deles.</span><span class="sxs-lookup"><span data-stu-id="0be6f-114">It controls the layout of the modules that are inside it.</span></span>
- <span data-ttu-id="0be6f-115">**Módulos de marketing** – Os módulos de marketing contêm o bloco de conteúdo, bloco de texto, player de vídeo e carrossel.</span><span class="sxs-lookup"><span data-stu-id="0be6f-115">**Marketing modules** – Marketing modules include content block, text block, video player, and carousel modules.</span></span> <span data-ttu-id="0be6f-116">Todos esses módulos podem ser usados para mostrar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="0be6f-116">All these modules can be used to showcase content.</span></span> <span data-ttu-id="0be6f-117">Eles podem ser colocados em qualquer página e direcionados por dados do sistema de gerenciamento de conteúdo (CMS).</span><span class="sxs-lookup"><span data-stu-id="0be6f-117">They can be put on any page and are driven by data from the content management system (CMS).</span></span>
- <span data-ttu-id="0be6f-118">**Módulos de cabeçalho e rodapé** – Os módulos de cabeçalho e rodapé aparecem no cabeçalho e no rodapé de todas as páginas do site.</span><span class="sxs-lookup"><span data-stu-id="0be6f-118">**Header and footer modules** – Header and footer modules appear in the header and footer of all site pages.</span></span> <span data-ttu-id="0be6f-119">Esse módulos podem ser configurados, conforme necessário, por meio de propriedades.</span><span class="sxs-lookup"><span data-stu-id="0be6f-119">These modules can be configured as required through properties.</span></span>
- <span data-ttu-id="0be6f-120">**Módulos de pesquisa** – Os produtos podem ser descobertos usando o módulo de pesquisa no cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="0be6f-120">**Search modules** – Products can be discovered by using the search module in the header.</span></span> <span data-ttu-id="0be6f-121">Os resultados de pesquisa aparecem na página de resultados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="0be6f-121">Search results appear on the search results page.</span></span> <span data-ttu-id="0be6f-122">Os produtos também podem ser descobertos nas páginas da categoria, que são páginas dedicadas para cada categoria suportada na hierarquia de navegação do canal.</span><span class="sxs-lookup"><span data-stu-id="0be6f-122">Products can also be discovered on category pages, which are dedicated pages for each category that is supported in the channel navigation hierarchy.</span></span> <span data-ttu-id="0be6f-123">Além disso, os módulos do refinador podem ser usados para filtrar os resultados nos resultados da pesquisa e nas páginas da categoria.</span><span class="sxs-lookup"><span data-stu-id="0be6f-123">In addition, refiner modules can be used to further filter results on search results and category pages.</span></span>
- <span data-ttu-id="0be6f-124">**Módulos da página de detalhes do produto** – As páginas de detalhes do produto usam vários módulos para mostrar informações sobre o produto.</span><span class="sxs-lookup"><span data-stu-id="0be6f-124">**Product details page modules** – Product details pages use several modules to show product information.</span></span> <span data-ttu-id="0be6f-125">O módulo da caixa de compra permite que os clientes exibam os produtos e os adicionem ao carrinho.</span><span class="sxs-lookup"><span data-stu-id="0be6f-125">The buy box module lets customers view products and add them to the cart.</span></span> <span data-ttu-id="0be6f-126">Outros módulos, tais como módulo específicos de tecnologia, mostram os detalhes do produto.</span><span class="sxs-lookup"><span data-stu-id="0be6f-126">Other modules, such as the tech specs module, show the product details.</span></span> <span data-ttu-id="0be6f-127">O módulo de classificações e opiniões pode ser usado para exibir e fornecer opiniões.</span><span class="sxs-lookup"><span data-stu-id="0be6f-127">The ratings and reviews module can used to view and provide reviews.</span></span>
- <span data-ttu-id="0be6f-128">**Módulo Comprar online, retirar na loja** – O módulo Comprar online, retirar na loja é integrado ao Bing Maps.</span><span class="sxs-lookup"><span data-stu-id="0be6f-128">**Buy online pick up in store module** – The buy online pick up in store module is integrated with Bing Maps.</span></span> <span data-ttu-id="0be6f-129">Pode ser usado para localizar lojas próximas onde os cliente podem retirar os produtos comprados.</span><span class="sxs-lookup"><span data-stu-id="0be6f-129">It can be used to find nearby stores where customers can pick up products that they have purchased.</span></span>
- <span data-ttu-id="0be6f-130">**Módulos de compra** – Os módulos de compra têm o módulo do carrinho que pode ser usado para adicionar itens ao carrinho.</span><span class="sxs-lookup"><span data-stu-id="0be6f-130">**Purchase modules** – Purchase modules include the cart module, which can be used to add items to the cart.</span></span> <span data-ttu-id="0be6f-131">O módulo de finalização de compra captura o endereço de remessa, opções de entrega e vale-presente, programa de fidelidade e informações do cartão de crédito, de forma que uma ordem possa ser processada.</span><span class="sxs-lookup"><span data-stu-id="0be6f-131">The checkout module captures the shipping address, delivery options, and gift card, loyalty program, and credit card information, so that an order can be processed.</span></span> <span data-ttu-id="0be6f-132">Depois que uma ordem é efetuada, o módulo de confirmação de ordem pode ser usado para exibir os detalhes da confirmação.</span><span class="sxs-lookup"><span data-stu-id="0be6f-132">After an order is placed, the order confirmation module can be used to show the confirmation details.</span></span>
- <span data-ttu-id="0be6f-133">**Módulos de gerenciamento da conta** – O módulo de login permite que os clientes entrem em uma conta existente e o módulo de inscrição permite que eles criem uma nova conta.</span><span class="sxs-lookup"><span data-stu-id="0be6f-133">**Account management modules** – The sign-in module lets customers sign in to an existing account, and the sign-up module lets them create a new account.</span></span> <span data-ttu-id="0be6f-134">Depois que uma conta é criada, o módulo do histórico da ordem pode ser usado para exibir as ordens recentes e o módulo de detalhes da ordem pode ser usado para exibir os detalhes da ordem.</span><span class="sxs-lookup"><span data-stu-id="0be6f-134">After an account is created, the order history module can be used to view recent orders, and the order details module can be used to view order details.</span></span>
- <span data-ttu-id="0be6f-135">**Módulo de recomendações** – As recomendações são mostradas usando o módulo de posicionamento do produto.</span><span class="sxs-lookup"><span data-stu-id="0be6f-135">**Recommendations module** – Recommendations are shown by using the product placement module.</span></span> <span data-ttu-id="0be6f-136">Este módulo suporta as listas algorítmicas e de editorial que podem ser apresentadas em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="0be6f-136">This module supports algorithmic and editorial lists that can be showcased on any page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0be6f-137">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="0be6f-137">Additional resources</span></span>

[<span data-ttu-id="0be6f-138">Módulo de contêiner</span><span class="sxs-lookup"><span data-stu-id="0be6f-138">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="0be6f-139">Módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="0be6f-139">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="0be6f-140">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="0be6f-140">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="0be6f-141">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="0be6f-141">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="0be6f-142">Módulo de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="0be6f-142">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="0be6f-143">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="0be6f-143">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="0be6f-144">Módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="0be6f-144">Footer module</span></span>](author-footer-module.md)
