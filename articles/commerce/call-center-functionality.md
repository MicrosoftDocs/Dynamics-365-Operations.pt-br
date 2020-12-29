---
title: Funcionalidade de vendas do call center
description: Este tópico mostra uma visão geral da funcionalidade de vendas do call center no Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 04/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
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
ms.openlocfilehash: 7091e8ba7940e358d77c69c63e26c8f3d9337713
ms.sourcegitcommit: 4c6d31f3ebd88212d3d1497a4bba9c64c5300444
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "4410335"
---
# <a name="call-center-sales-functionality"></a><span data-ttu-id="9ddec-103">Funcionalidade de vendas do call center</span><span class="sxs-lookup"><span data-stu-id="9ddec-103">Call center sales functionality</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="9ddec-104">No Dynamics 365 Commerce, call center é um tipo de canal que pode ser definido no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9ddec-104">In Dynamics 365 Commerce, a call center is a type of channel that can be defined in the application.</span></span> <span data-ttu-id="9ddec-105">Definir um canal específico das entidades de call center permite que o sistema una padrões de dados específicos e padrões de processamento de ordem para ordens de vendas criadas por um usuário do canal do call center.</span><span class="sxs-lookup"><span data-stu-id="9ddec-105">Defining a specific channel for your call center entities allows the system to tie specific data defaults and order processing defaults to sales orders created by a user of the call center channel.</span></span>

<span data-ttu-id="9ddec-106">Os recursos de call center incluem preço avançado e promoções, catálogos, cartões-presente, programas de fidelidade e cupons.</span><span class="sxs-lookup"><span data-stu-id="9ddec-106">Call center features include advanced price and promotions, catalogs, gift cards, loyalty programs, and coupons.</span></span> <span data-ttu-id="9ddec-107">Ordens de call center são aproveitadas também por uma aplicação de ponto de venda (PDV) para oferecer suporte a cenários de preenchimento de ordem entre canal.</span><span class="sxs-lookup"><span data-stu-id="9ddec-107">Call center orders are also leveraged by the point of sale (POS) application to support cross-channel order fulfillment scenarios.</span></span>

<span data-ttu-id="9ddec-108">É importante observar que, quando o módulo de call center pode ser utilizado por outros setores fora do Commerce, a versão atual do aplicativo de call center não foi otimizada para uso em cenários de processamento de ordens B2B (entre empresas) ou em cenários em que as ordens tenham um grande número de linhas de venda.</span><span class="sxs-lookup"><span data-stu-id="9ddec-108">It's important to note that while the call center module can be utilized by other industries outside of Commerce, the current release of the call center application hasn't been optimized for use in business-to-business (B2B) order processing scenarios, or scenarios where orders have a large number of sales lines.</span></span> <span data-ttu-id="9ddec-109">Recomenda-se que os usuários que desejam utilizar os recursos do call center para processamento de ordem fora de um processamento de transação direto ao consumidor típico, levem o tempo adequado para testar e validar essa funcionalidade de call center para estar compatível com as necessidades funcional e de desempenho.</span><span class="sxs-lookup"><span data-stu-id="9ddec-109">It's recommended that users who want to utilize the call center features for order processing outside of typical direct-to-consumer transaction processing, take adequate time to test and validate that enabling call center functionality will meet functional and performance needs.</span></span>

<span data-ttu-id="9ddec-110">Além da criação da ordem de atendimento, o módulo de call center também fornece um aplicativo de serviço ao cliente amigável que facilita para que os usuários encontrem contas de cliente e examina todos os dados relacionados e atributos da ordem de cliente.</span><span class="sxs-lookup"><span data-stu-id="9ddec-110">In addition to supporting order creation, the call center module also provides a user-friendly customer service application that makes it easier for users to locate customer accounts and review all of the related customer order data and attributes.</span></span> <span data-ttu-id="9ddec-111">A tela de serviço do cliente foi projetada para habilitar um usuário a acessar rapidamente os dados da ordem relacionada que permitirão que ele responda às questões relacionadas a ordem mais comuns recebidas dos clientes.</span><span class="sxs-lookup"><span data-stu-id="9ddec-111">The customer service screen is designed to enable a user to quickly access order-related data that will allow them to answer the most common order-related questions received from customers.</span></span>

<span data-ttu-id="9ddec-112">Esta página fornece links para documentação relevante relacionada à instalação, à configuração e ao uso funcional dos recursos de call center.</span><span class="sxs-lookup"><span data-stu-id="9ddec-112">This page provides links to relevant documentation related to the setup, configuration, and functional use of the call center features.</span></span>


## <a name="configure-the-call-center"></a><span data-ttu-id="9ddec-113">Configurar o call center</span><span class="sxs-lookup"><span data-stu-id="9ddec-113">Configure the call center</span></span>

[<span data-ttu-id="9ddec-114">Configurar canais de call center</span><span class="sxs-lookup"><span data-stu-id="9ddec-114">Set up call center channels</span></span>](set-up-order-processing-options.md)

## <a name="configure-order-processing"></a><span data-ttu-id="9ddec-115">Configurar processamento de ordem</span><span class="sxs-lookup"><span data-stu-id="9ddec-115">Configure order processing</span></span>

[<span data-ttu-id="9ddec-116">Configurar e trabalhar com alertas de fraude de call center</span><span class="sxs-lookup"><span data-stu-id="9ddec-116">Set up and work with call center fraud alerts</span></span>](set-up-fraud-alerts.md)

[<span data-ttu-id="9ddec-117">Configurar e trabalhar com bloqueios de ordem do call center</span><span class="sxs-lookup"><span data-stu-id="9ddec-117">Configure and work with call center order holds</span></span>](work-with-order-holds.md)

## <a name="configure-payment-processing"></a><span data-ttu-id="9ddec-118">Configurar processamento de pagamento</span><span class="sxs-lookup"><span data-stu-id="9ddec-118">Configure payment processing</span></span>

[<span data-ttu-id="9ddec-119">Meios de pagamento nos call centers</span><span class="sxs-lookup"><span data-stu-id="9ddec-119">Payment methods in call centers</span></span>](work-with-payments.md)

## <a name="configure-delivery-modes"></a><span data-ttu-id="9ddec-120">Configurar modos de entrega</span><span class="sxs-lookup"><span data-stu-id="9ddec-120">Configure delivery modes</span></span>

[<span data-ttu-id="9ddec-121">Configurar modos de entrega e encargos do call center</span><span class="sxs-lookup"><span data-stu-id="9ddec-121">Configure call center delivery modes and charges</span></span>](configure-call-center-delivery.md)

## <a name="configure-direct-marketing"></a><span data-ttu-id="9ddec-122">Configurar marketing direto</span><span class="sxs-lookup"><span data-stu-id="9ddec-122">Configure direct marketing</span></span>

[<span data-ttu-id="9ddec-123">Catálogos do call center</span><span class="sxs-lookup"><span data-stu-id="9ddec-123">Call center catalogs</span></span>](call-center-catalogs.md)

[<span data-ttu-id="9ddec-124">Configurar análise de Recency, frequência e valor monetário (RFM)</span><span class="sxs-lookup"><span data-stu-id="9ddec-124">Set up Recency, Frequency, and Monetary (RFM) analysis</span></span>](set-up-rfm-analysis.md)

## <a name="configure-continuity-programs"></a><span data-ttu-id="9ddec-125">Configurar programas de continuidade</span><span class="sxs-lookup"><span data-stu-id="9ddec-125">Configure continuity programs</span></span>

[<span data-ttu-id="9ddec-126">Configurar programas de continuidade para call centers</span><span class="sxs-lookup"><span data-stu-id="9ddec-126">Set up continuity programs for call centers</span></span>](set-up-continuity-program.md)
