---
title: Visão geral do ambiente de avaliação do Dynamics 365 Commerce
description: Este tópico fornece uma visão geral do ambiente de avaliação do Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-chgri
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 25c0574e8d4502bcb846fba0ddf913d81eded87b
ms.sourcegitcommit: 5175e3fae432016246244cf70fe05465f43de88c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2020
ms.locfileid: "3599740"
---
# <a name="dynamics-365-commerce-evaluation-environment-overview"></a><span data-ttu-id="2df7e-103">Visão geral do ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="2df7e-103">Dynamics 365 Commerce evaluation environment overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2df7e-104">Este tópico fornece uma visão geral do ambiente de avaliação do Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2df7e-104">This topic gives an overview of the Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

> [!NOTE]
> <span data-ttu-id="2df7e-105">Os ambientes de avaliação do Commerce não estão disponíveis para o público geral e são concedidos a parceiros e clientes por solicitação.</span><span class="sxs-lookup"><span data-stu-id="2df7e-105">Commerce evaluation environments aren't generally available, and are granted to partners and customers on a per-request basis.</span></span> <span data-ttu-id="2df7e-106">Para obter mais informações, fale com o contato do seu parceiro Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2df7e-106">For more information, reach out to your Microsoft partner contact.</span></span>

## <a name="overview"></a><span data-ttu-id="2df7e-107">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="2df7e-107">Overview</span></span>

<span data-ttu-id="2df7e-108">O ambiente de avaliação do Commerce é um ambiente opcional de ponta a ponta do Dynamics 365 Commerce, que permite aos parceiros e clientes potenciais experimentar o produto do Commerce.</span><span class="sxs-lookup"><span data-stu-id="2df7e-108">The Commerce evaluation environment is an optional end-to-end environment of Dynamics 365 Commerce that lets partners and potential customers try out the Commerce product.</span></span>

<span data-ttu-id="2df7e-109">Os ambientes de avaliação são parcialmente pré-configurados para reduzir as etapas necessárias de pós-provisionamento.</span><span class="sxs-lookup"><span data-stu-id="2df7e-109">Evaluation environments are partially preconfigured to reduce the required post-provisioning steps.</span></span>

<span data-ttu-id="2df7e-110">Com exceção de algumas limitações mínimas que não afetam os recursos ou a funcionalidade, o ambiente de avaliação do Commerce oferece a experiência completa do Commerce e pode ser usado por clientes e parceiros de implementação para avaliar o produto, fornecer comentários e realizar análise de lacuna/ajuste.</span><span class="sxs-lookup"><span data-stu-id="2df7e-110">Aside from some minor limitations that don't affect features or functionality, the Commerce evaluation environment provides the complete Commerce experience, and can be used by customers and implementation partners to evaluate the product, provide feedback, and do fit/gap analysis.</span></span>

## <a name="limitations-of-the-commerce-evaluation-environment"></a><span data-ttu-id="2df7e-111">Limitações do ambiente de avaliação do Commerce</span><span class="sxs-lookup"><span data-stu-id="2df7e-111">Limitations of the Commerce evaluation environment</span></span>

<span data-ttu-id="2df7e-112">Embora o ambiente de avaliação do Commerce forneça o conjunto completo de recursos e funcionalidades do Commerce, há algumas limitações mínimas:</span><span class="sxs-lookup"><span data-stu-id="2df7e-112">Although the Commerce evaluation environment provides the full set of Commerce features and functionality, there are some minor limitations:</span></span>

- <span data-ttu-id="2df7e-113">Embora o ambiente de avaliação do Commerce não tenha limitações geográficas, os componentes do ambiente, como os aplicativos Retail Cloud Scale Unit (RCSU) e e-Commerce, devem ser provisionados somente nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="2df7e-113">Although the Commerce evaluation environment itself has no geographical limitations, components of the environment, such as the Retail Cloud Scale Unit (RCSU) and e-Commerce applications, should be provisioned only in the United States.</span></span>
- <span data-ttu-id="2df7e-114">O uso do ambiente de avaliação do Commerce é limitado a 30 dias a partir da data em que o e-Commerce foi provisionado.</span><span class="sxs-lookup"><span data-stu-id="2df7e-114">Use of the Commerce evaluation environment is limited to 30 days from the date when e-Commerce is provisioned.</span></span>
- <span data-ttu-id="2df7e-115">O ambiente de avaliação do Commerce pode ser implantado e inicializado com êxito somente em um ambiente que use a topologia de demonstração, na qual todos os componentes de um ambiente são implantados em uma única máquina virtual (VM) hospedada na nuvem.</span><span class="sxs-lookup"><span data-stu-id="2df7e-115">The Commerce evaluation environment can be successfully deployed and initialized only in an environment that uses the demo topology, where all components of an environment are deployed on a single cloud-hosted virtual machine (VM).</span></span> <span data-ttu-id="2df7e-116">A principal limitação dessa topologia é o número de usuários simultâneos aos quais o ambiente pode oferecer suporte.</span><span class="sxs-lookup"><span data-stu-id="2df7e-116">The main limitation of this topology is the number of concurrent users that the environment can support.</span></span>

## <a name="get-started"></a><span data-ttu-id="2df7e-117">Iniciado</span><span class="sxs-lookup"><span data-stu-id="2df7e-117">Get started</span></span>

<span data-ttu-id="2df7e-118">Para provisionar o ambiente de avaliação do Commerce, consulte [Provisionar um ambiente de avaliação do Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="2df7e-118">To provision the Commerce evaluation environment, see [Provision a Commerce evaluation environment](provisioning-guide.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2df7e-119">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="2df7e-119">Additional resources</span></span>

[<span data-ttu-id="2df7e-120">Provisionar um ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="2df7e-120">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="2df7e-121">Configurar um ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="2df7e-121">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="2df7e-122">Configurar BOPIS em um ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="2df7e-122">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="2df7e-123">Configurar recursos opcionais para um ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="2df7e-123">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="2df7e-124">Perguntas frequentes sobre o ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="2df7e-124">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)
