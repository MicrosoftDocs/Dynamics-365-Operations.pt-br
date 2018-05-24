---
title: Funcionalidade do call center
description: "Este tópico fornece uma visão geral da funcionalidade de vendas do call center no Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 04/03/2018
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: e85b65e116b32adca09e46252d7d3bbe5101e1cf
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="call-center"></a><span data-ttu-id="46524-103">Call center</span><span class="sxs-lookup"><span data-stu-id="46524-103">Call center</span></span> 

[!include [banner](includes/banner.md)]

<span data-ttu-id="46524-104">No In Dynamics 365 for Retail, um call center é um tipo de canal de Varejo que pode ser definido no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="46524-104">In Dynamics 365 for Retail, a call center is a type of Retail channel that can be defined in the application.</span></span> <span data-ttu-id="46524-105">Definir um canal específico das entidades de call center permite que o sistema una padrões de dados específicos e padrões de processamento de ordem para ordens de vendas criadas por um usuário do canal do call center.</span><span class="sxs-lookup"><span data-stu-id="46524-105">Defining a specific channel for your call center entities allows the system to tie specific data defaults and order processing defaults to sales orders created by a user of the call center channel.</span></span>

<span data-ttu-id="46524-106">Os recursos de call center incluem preço de varejo avançado e promoções, catálogos, cartões-presente, programas de lealdade e cupons.</span><span class="sxs-lookup"><span data-stu-id="46524-106">Call center features include advanced retail price and promotions, catalogs, gift cards, loyalty programs, and coupons.</span></span> <span data-ttu-id="46524-107">Ordens de call center são aproveitadas também por uma aplicação de ponto de venda (PDV) para oferecer suporte a cenários de preenchimento de ordem entre canal.</span><span class="sxs-lookup"><span data-stu-id="46524-107">Call center orders are also leveraged by the point of sale (POS) application to support cross-channel order fulfillment scenarios.</span></span>

<span data-ttu-id="46524-108">É importante observar que quando o módulo de call center pode ser utilizado por outras indústrias fora de varejo, a versão atual do aplicativo de call center do Dynamics 365 for Retail foi otimizada para uso em cenários interempresariais (B2B) de processamento de ordens, ou cenários onde ordens têm uma grande quantidade de linhas de venda.</span><span class="sxs-lookup"><span data-stu-id="46524-108">It's important to note that while the call center module can be utilized by other industries outside of Retail, the current release of the Dynamics 365 for Retail call center application hasn't been optimized for use in business-to-business (B2B) order processing scenarios, or scenarios where orders have a large amount of sales lines.</span></span> <span data-ttu-id="46524-109">Recomenda-se que os usuários que desejam utilizar os recursos do call center para processamento de ordem fora de um processamento de transação direto ao consumidor típico, levem o tempo adequado para testar e validar essa funcionalidade de call center para estar compatível com as necessidades funcional e de desempenho.</span><span class="sxs-lookup"><span data-stu-id="46524-109">It's recommended that users who want to utilize the call center features for order processing outside of typical direct-to-consumer transaction processing, take adequate time to test and validate that enabling call center functionality will meet functional and performance needs.</span></span>

<span data-ttu-id="46524-110">Além da criação da ordem de atendimento, o módulo de call center também fornece um aplicativo de serviço ao cliente amigável que facilita para que os usuários encontrem contas de cliente e examina todos os dados relacionados e atributos da ordem de cliente.</span><span class="sxs-lookup"><span data-stu-id="46524-110">In addition to supporting order creation, the call center module also provides a user-friendly customer service application that makes it easier for users to locate customer accounts and review all of the related customer order data and attributes.</span></span> <span data-ttu-id="46524-111">A tela de serviço do cliente é projetada para habilitar um usuário a acessar rapidamente os dados da ordem relacionada que permitirão que eles respondam às questões relacionadas a ordem mais comuns recebidas dos clientes.</span><span class="sxs-lookup"><span data-stu-id="46524-111">The customer service screen is designed to enable a user to quickly access order related data that will allow them to answer the most common order-related questions received from customers.</span></span>

<span data-ttu-id="46524-112">Essa página fornece links para a documentação relevante antes da instalação, a configuração, e o uso de recursos funcional de call center no Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="46524-112">This page provides links to relevant documentation related to the setup, configuration, and functional use of the call center features in Dynamics 365 for Retail.</span></span>

## <a name="configure-the-call-center"></a><span data-ttu-id="46524-113">Configurar o call center</span><span class="sxs-lookup"><span data-stu-id="46524-113">Configure the call center</span></span>
[<span data-ttu-id="46524-114">Configurar opções de processamento de ordens</span><span class="sxs-lookup"><span data-stu-id="46524-114">Set up order processing options</span></span>](set-up-order-processing-options.md)

## <a name="configure-order-processing"></a><span data-ttu-id="46524-115">Configurar processamento de ordem</span><span class="sxs-lookup"><span data-stu-id="46524-115">Configure order processing</span></span>
<span data-ttu-id="46524-116">[Configurar alertas de fraude](set-up-fraud-alerts.md)
[Pendência de ordem manual](work-with-order-holds.md)</span><span class="sxs-lookup"><span data-stu-id="46524-116">[Set up fraud alerts](set-up-fraud-alerts.md)
[Manual Order Holds](work-with-order-holds.md)</span></span>

## <a name="configure-payment-processing"></a><span data-ttu-id="46524-117">Configurar processamento de pagamento</span><span class="sxs-lookup"><span data-stu-id="46524-117">Configure payment processing</span></span>
[<span data-ttu-id="46524-118">Métodos de pagamento em um call center</span><span class="sxs-lookup"><span data-stu-id="46524-118">Payment methods in a call center</span></span>](work-with-payments.md)

## <a name="configure-direct-marketing"></a><span data-ttu-id="46524-119">Configurar marketing direto</span><span class="sxs-lookup"><span data-stu-id="46524-119">Configure direct marketing</span></span>
[<span data-ttu-id="46524-120">Catálogos do call center</span><span class="sxs-lookup"><span data-stu-id="46524-120">Call center catalogs</span></span>](call-center-catalogs.md)

[<span data-ttu-id="46524-121">Configurar análise RFM</span><span class="sxs-lookup"><span data-stu-id="46524-121">Set up RFM analysis</span></span>](set-up-rfm-analysis.md)

## <a name="configure-continuity-programs"></a><span data-ttu-id="46524-122">Configurar programas de continuidade</span><span class="sxs-lookup"><span data-stu-id="46524-122">Configure continuity programs</span></span>
[<span data-ttu-id="46524-123">Configurar um programa de continuidade para um call center</span><span class="sxs-lookup"><span data-stu-id="46524-123">Set up a continuity program for a call center</span></span>](set-up-continuity-program.md)


