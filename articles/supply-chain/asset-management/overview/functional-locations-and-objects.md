---
title: Locais e ativos funcionais
description: Este tópico descreve locais e ativos funcionais em Gerenciamento de Ativos. O Gerenciamento de Ativos é um módulo avançado para gerenciar ativos e trabalhos de manutenção no Microsoft Dynamics 365 for Finance and Operations.
author: josaw1
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 351e27dfbbd5227a9642f14a48afe194c447a0f3
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783082"
---
# <a name="functional-locations-and-assets"></a><span data-ttu-id="c30dd-104">Locais e ativos funcionais</span><span class="sxs-lookup"><span data-stu-id="c30dd-104">Functional locations and assets</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="c30dd-105">Este tópico descreve locais e ativos funcionais em Gerenciamento de Ativos.</span><span class="sxs-lookup"><span data-stu-id="c30dd-105">This topic describes functional locations and assets in Asset Management.</span></span> <span data-ttu-id="c30dd-106">O Gerenciamento de Ativos é um módulo avançado para gerenciar ativos e trabalhos de manutenção no Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c30dd-106">Asset Management is an advanced module for managing assets and maintenance jobs in Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="overview"></a><span data-ttu-id="c30dd-107">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="c30dd-107">Overview</span></span>

<span data-ttu-id="c30dd-108">O Gerenciamento de Ativos está perfeitamente integrado a vários módulos no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c30dd-108">Asset Management is integrated seamlessly with several modules in Finance and Operations.</span></span> <span data-ttu-id="c30dd-109">A ilustração a seguir mostra as interfaces com outros módulos.</span><span class="sxs-lookup"><span data-stu-id="c30dd-109">The following illustration shows the interfaces with other modules.</span></span>

![Figura 1](media/01-overview-image.png)

<span data-ttu-id="c30dd-111">O Gerenciamento de Ativos permite que você gerencie e execute com eficiência todas as tarefas relacionadas ao gerenciamento e à manutenção de vários tipos de equipamentos na sua empresa.</span><span class="sxs-lookup"><span data-stu-id="c30dd-111">Asset Management lets you efficiently manage and perform all tasks that are related to managing and servicing many types of equipment in your company.</span></span> <span data-ttu-id="c30dd-112">Este equipamento inclui computadores, equipamento de produção e veículos.</span><span class="sxs-lookup"><span data-stu-id="c30dd-112">This equipment includes machines, production equipment, and vehicles.</span></span> <span data-ttu-id="c30dd-113">O Gerenciamento de Ativos também dá suporte a soluções em vários setores.</span><span class="sxs-lookup"><span data-stu-id="c30dd-113">Asset Management also supports solutions across numerous industries.</span></span>

<span data-ttu-id="c30dd-114">A ilustração a seguir mostra uma visão geral da funcionalidade principal que é coberta pelo Gerenciamento de Ativos.</span><span class="sxs-lookup"><span data-stu-id="c30dd-114">The following illustration shows an overview of the main functionality that is covered by Asset Management.</span></span>

![Figura 2](media/02-overview-image.png)

## <a name="functional-locations-and-assets"></a><span data-ttu-id="c30dd-116">Locais e ativos funcionais</span><span class="sxs-lookup"><span data-stu-id="c30dd-116">Functional locations and assets</span></span>

<span data-ttu-id="c30dd-117">Os locais funcionais são usados para gerenciar ativos em locais.</span><span class="sxs-lookup"><span data-stu-id="c30dd-117">Functional locations are used to manage assets on locations.</span></span> <span data-ttu-id="c30dd-118">Este gerenciamento inclui o controle de custos de ativos em locais funcionais.</span><span class="sxs-lookup"><span data-stu-id="c30dd-118">This management includes tracking of asset costs on functional locations.</span></span> <span data-ttu-id="c30dd-119">Os locais funcionais são estruturados hierarquicamente e os locais podem ter sublocais.</span><span class="sxs-lookup"><span data-stu-id="c30dd-119">Functional locations are structured hierarchically, and locations can have sub-locations.</span></span> <span data-ttu-id="c30dd-120">A estrutura de locais funcionais é estática.</span><span class="sxs-lookup"><span data-stu-id="c30dd-120">The structure of functional locations is static.</span></span> <span data-ttu-id="c30dd-121">Ou seja, locais não podem mudar de lugar.</span><span class="sxs-lookup"><span data-stu-id="c30dd-121">In other words, locations can't change place.</span></span> <span data-ttu-id="c30dd-122">Ativos podem ser instalados em locais funcionais e, se necessário, podem ser instalados em outros locais funcionais posteriormente.</span><span class="sxs-lookup"><span data-stu-id="c30dd-122">Assets can be installed on functional locations and, as required, can be installed on other functional locations later.</span></span>

<span data-ttu-id="c30dd-123">Custos de ativos sempre acompanham o local do ativo.</span><span class="sxs-lookup"><span data-stu-id="c30dd-123">Asset costs always follow the location of the asset.</span></span> <span data-ttu-id="c30dd-124">Ou seja, se você instalar um ativo em um novo local funcional, o ativo usará automaticamente as dimensões financeiras que relacionadas ao novo local funcional.</span><span class="sxs-lookup"><span data-stu-id="c30dd-124">In other words, if you install an asset on a new functional location, the asset automatically uses the financial dimensions that are related to the new functional location.</span></span> <span data-ttu-id="c30dd-125">Portanto, os custos de ativos são sempre relacionadas ao local funcional no qual o ativo está instalado no momento.</span><span class="sxs-lookup"><span data-stu-id="c30dd-125">Therefore, asset costs are always related to the functional location that the asset is  currently installed on.</span></span> <span data-ttu-id="c30dd-126">Esta manipulação automática de dimensões financeiras ajuda a garantir o rastreamento completo de custos quando sua empresa faz o controle e relatório de projetos em locais funcionais.</span><span class="sxs-lookup"><span data-stu-id="c30dd-126">This automatic handling of financial dimensions helps guarantee complete tracking of costs when your company does project controlling and reporting on functional locations.</span></span>

<span data-ttu-id="c30dd-127">A maneira que você cria a hierarquia de locais funcionais depende de requisitos da sua empresa para manter equipamentos internos ou atender equipamentos de clientes.</span><span class="sxs-lookup"><span data-stu-id="c30dd-127">The way that you build your hierarchy of functional locations depends on your company's requirements for maintaining internal equipment or servicing customer equipment.</span></span> <span data-ttu-id="c30dd-128">A figura a seguir mostra um exemplo de locais funcionais baseados em localizações geográficas.</span><span class="sxs-lookup"><span data-stu-id="c30dd-128">The following figure shows an example of functional locations that are based on geographical locations.</span></span>

![Figura 3](media/03-overview-image.png)

<span data-ttu-id="c30dd-130">A figura a seguir mostra um exemplo de locais funcionais baseados em clientes.</span><span class="sxs-lookup"><span data-stu-id="c30dd-130">The following figure shows an example of functional locations that are based on customers.</span></span>

![Figura 4](media/04-overview-image.png)
