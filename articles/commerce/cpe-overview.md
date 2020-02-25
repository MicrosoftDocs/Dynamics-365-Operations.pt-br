---
title: Visão geral do ambiente de visualização do Dynamics 365 Commerce
description: Este tópico fornece uma visão geral do ambiente de visualização do Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 12/10/2019
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
ms.openlocfilehash: 1ff96aeb5963df9ddee56783a089dad129bbb71c
ms.sourcegitcommit: 4ed1d8ad8a0206a4172dbb41cc43f7d95073059c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024674"
---
# <a name="dynamics-365-commerce-preview-environment-overview"></a><span data-ttu-id="07578-103">Visão geral do ambiente de visualização do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="07578-103">Dynamics 365 Commerce preview environment overview</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="07578-104">Este tópico fornece uma visão geral do ambiente de visualização do Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="07578-104">This topic gives an overview of the Microsoft Dynamics 365 Commerce preview environment.</span></span>

## <a name="overview"></a><span data-ttu-id="07578-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="07578-105">Overview</span></span>

<span data-ttu-id="07578-106">O ambiente de visualização do Commerce é um ambiente opcional de visualização do Dynamics 365 Commerce de ponta a ponta, que permite que os clientes potenciais experimentem o produto do Commerce antes do lançamento geral ao público.</span><span class="sxs-lookup"><span data-stu-id="07578-106">The Commerce preview environment is an optional end-to-end preview environment of Dynamics 365 Commerce that lets potential customers try out the Commerce product before its general release to the public.</span></span>

<span data-ttu-id="07578-107">Além de algumas limitações mínimas que não afetam os recursos ou a funcionalidade, o ambiente de visualização comercial oferece a experiência comercial completa e pode ser usado por clientes e parceiros de implementação para avaliar o produto, fornecer comentários e analisar as necessidades e a análise de lacunas.</span><span class="sxs-lookup"><span data-stu-id="07578-107">Aside from some minor limitations that don't affect features or functionality, the Commerce preview environment provides the complete Commerce experience, and can be used by customers and implementation partners to evaluate the product, provide feedback, and do fit/gap analysis.</span></span>

## <a name="limitations-of-the-commerce-preview-environment"></a><span data-ttu-id="07578-108">Limitações do ambiente de visualização do Commerce</span><span class="sxs-lookup"><span data-stu-id="07578-108">Limitations of the Commerce preview environment</span></span>

<span data-ttu-id="07578-109">Embora o ambiente de visualização do Commerce forneça o conjunto completo de recursos e funcionalidades do Commerce, há algumas limitações mínimas:</span><span class="sxs-lookup"><span data-stu-id="07578-109">Although the Commerce preview environment provides the full set of Commerce features and functionality, there are some minor limitations:</span></span>

- <span data-ttu-id="07578-110">Embora o ambiente de visualização do Commerce não tenha limitações geográficas, os componentes do ambiente, como os aplicativos Retail Cloud Scale Unit (RCSU) e comércio eletrônico, podem ser provisionados somente nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="07578-110">Although the Commerce preview environment itself has no geographical limitations, components of the environment, such as the Retail Cloud Scale Unit (RCSU) and e-Commerce applications, can be provisioned only in the United States.</span></span>
- <span data-ttu-id="07578-111">Uso do ambiente de visualização do Commerce é limitado a 30 dias a partir da data quando o comércio eletrônico foi provisionado.</span><span class="sxs-lookup"><span data-stu-id="07578-111">Use of the Commerce preview environment is limited to 30 days from the date when e-Commerce is provisioned.</span></span>
- <span data-ttu-id="07578-112">O ambiente de visualização do Commerce pode ser implantado com êxito e inicializado somente em um ambiente que usa a topologia de demonstração, na qual todos os componentes de um ambiente são implantados em uma única máquina virtual (VM).</span><span class="sxs-lookup"><span data-stu-id="07578-112">The Commerce preview environment can be successfully deployed and initialized only in an environment that uses the demo topology, where all components of an environment are deployed in a single virtual machine (VM).</span></span> <span data-ttu-id="07578-113">A principal limitação dessa topologia de VM de OneBox é o número de usuários simultâneos que o ambiente de visualização pode suportar.</span><span class="sxs-lookup"><span data-stu-id="07578-113">The main limitation of this OneBox VM topology is the number of concurrent users that the preview environment can support.</span></span>
- <span data-ttu-id="07578-114">O ambiente de visualização do Commerce pode ser avaliado somente até a disponibilidade geral (GA) do produto do Commerce.</span><span class="sxs-lookup"><span data-stu-id="07578-114">The Commerce preview environment can be evaluated only until the general availability (GA) of the Commerce product.</span></span> <span data-ttu-id="07578-115">Novos ambientes de demonstração estarão disponíveis após GA.</span><span class="sxs-lookup"><span data-stu-id="07578-115">New demo environments will be available after GA.</span></span>

## <a name="get-started"></a><span data-ttu-id="07578-116">Comece a usar</span><span class="sxs-lookup"><span data-stu-id="07578-116">Get started</span></span>

<span data-ttu-id="07578-117">Para configurar o ambiente de visualização do Commerce, consulte [Provisionar um ambiente de visualização do Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="07578-117">To provision the Commerce preview environment, see [Provision a Commerce preview environment](provisioning-guide.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="07578-118">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="07578-118">Additional resources</span></span>

[<span data-ttu-id="07578-119">Provisionar um ambiente de visualização do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="07578-119">Provision a Dynamics 365 Commerce preview environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="07578-120">Configurar um ambiente de visualização do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="07578-120">Configure a Dynamics 365 Commerce preview environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="07578-121">Configurar recursos opcionais para um ambiente de visualização do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="07578-121">Configure optional features for a Dynamics 365 Commerce preview environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="07578-122">Perguntas frequentes do ambiente de visualização do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="07578-122">Dynamics 365 Commerce preview environment FAQ</span></span>](cpe-faq.md)
