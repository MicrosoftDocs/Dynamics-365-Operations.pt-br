---
title: Recursos removidos ou obsoletos do Dynamics 365 Supply Chain Management
description: Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção em Dynamics 365 Supply Chain Management.
author: kamaybac
manager: AnnBe
ms.date: 04/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 7502cd16129431d41d152508fb3b49ff85a5a9f8
ms.sourcegitcommit: f1db998ecfccca660eb15cc2739b12c8463fa54d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2020
ms.locfileid: "3331239"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-supply-chain-management"></a><span data-ttu-id="e28d3-103">Recursos removidos ou obsoletos do Dynamics 365 Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="e28d3-103">Removed or deprecated features in Dynamics 365 Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e28d3-104">Este tópico será atualizado à medida que os novos recursos removidos ou obsoletos forem documentados para Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e28d3-104">This topic will be updated as new removed or deprecated features are documented for Dynamics 365 Supply Chain Management.</span></span>

- <span data-ttu-id="e28d3-105">Um recurso *removido* não estará mais disponível no produto.</span><span class="sxs-lookup"><span data-stu-id="e28d3-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="e28d3-106">Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.</span><span class="sxs-lookup"><span data-stu-id="e28d3-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="e28d3-107">Esta lista é destinada a ajudá-lo a considerar essas remoções e reprovações para seu próprio planejamento.</span><span class="sxs-lookup"><span data-stu-id="e28d3-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span>

> [!NOTE]
> <span data-ttu-id="e28d3-108">Informações detalhadas sobre objetos no Finance and Operations apps podem ser encontradas nos [Relatórios de referência técnica](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span><span class="sxs-lookup"><span data-stu-id="e28d3-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="e28d3-109">Você pode comparar as diferentes versões desses relatórios para aprender sobre objetos que foram alterados ou removidos em cada versão do Finance and Operations apps.</span><span class="sxs-lookup"><span data-stu-id="e28d3-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10011-release"></a><span data-ttu-id="e28d3-110">Recursos removidos ou substituídos na versão 10.0.11 do Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="e28d3-110">Features removed or deprecated in the Supply Chain Management 10.0.11 release</span></span>

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios"></a><span data-ttu-id="e28d3-111">Uso do mecanismo de planejamento mestre do Supply Chain Management integrado para cenários de distribuição</span><span class="sxs-lookup"><span data-stu-id="e28d3-111">Use of built-in Supply Chain Management master planning engine for distribution scenarios</span></span>

|   |  |
|------------|--------------------|
| <span data-ttu-id="e28d3-112">**Motivo para a reprovação/remoção**</span><span class="sxs-lookup"><span data-stu-id="e28d3-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="e28d3-113">Para melhorar o desempenho e minimizar o carregamento do banco de dados SQL durante a execução do planejamento mestre, o mecanismo de planejamento mestre interno do Supply Chain Management está sendo substituído pela otimização do planejamento.</span><span class="sxs-lookup"><span data-stu-id="e28d3-113">To enhance performance and minimize the SQL database load during master planning runs, the built-in Supply Chain Management master planning engine is being replaced by Planning Optimization.</span></span> <span data-ttu-id="e28d3-114">A otimização do planejamento permite a execução de planejamentos rápidos que podem ser realizados mesmo durante o horário de expediente.</span><span class="sxs-lookup"><span data-stu-id="e28d3-114">Planning Optimization allows for fast planning runs that can be performed even during office hours.</span></span> <span data-ttu-id="e28d3-115">Isso permite que os planejadores reajam imediatamente a alterações na demanda ou nos parâmetros de planejamento.</span><span class="sxs-lookup"><span data-stu-id="e28d3-115">This enables planners to react immediately to changes in demand or planning parameters.</span></span> |
| <span data-ttu-id="e28d3-116">**Substituída por outro recurso?**</span><span class="sxs-lookup"><span data-stu-id="e28d3-116">**Replaced by another feature?**</span></span>   | <span data-ttu-id="e28d3-117">Sim, a Otimização de Planejamento substituirá o mecanismo de planejamento mestre do Supply Chain Management interno.</span><span class="sxs-lookup"><span data-stu-id="e28d3-117">Yes, Planning Optimization will replace the existing built-in Supply Chain Management master planning engine.</span></span> |
| <span data-ttu-id="e28d3-118">**Áreas afetadas do produto**</span><span class="sxs-lookup"><span data-stu-id="e28d3-118">**Product areas affected**</span></span>         | <span data-ttu-id="e28d3-119">Supply Chain Management - Planejamento mestre</span><span class="sxs-lookup"><span data-stu-id="e28d3-119">Supply Chain Management - Master planning</span></span> |
| <span data-ttu-id="e28d3-120">**Opção de implantação**</span><span class="sxs-lookup"><span data-stu-id="e28d3-120">**Deployment option**</span></span>              | <span data-ttu-id="e28d3-121">Somente nuvem.</span><span class="sxs-lookup"><span data-stu-id="e28d3-121">Cloud only.</span></span> <span data-ttu-id="e28d3-122">A otimização de planejamento não é suportada com implantações locais.</span><span class="sxs-lookup"><span data-stu-id="e28d3-122">Planning Optimization is not supported with on-premises deployments.</span></span> |
| <span data-ttu-id="e28d3-123">**Status**</span><span class="sxs-lookup"><span data-stu-id="e28d3-123">**Status**</span></span>                         | <span data-ttu-id="e28d3-124">Preterido.</span><span class="sxs-lookup"><span data-stu-id="e28d3-124">Deprecated.</span></span> <span data-ttu-id="e28d3-125">Em abril de 2021, os cenários de distribuição não receberão mais suporte com o mecanismo de planejamento mestre interno do Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e28d3-125">On April 2021, distribution scenarios will no longer be supported with the built-in Dynamics 365 Supply Chain Management master planning engine.</span></span> <span data-ttu-id="e28d3-126">Para cenários de distribuição, os clientes devem usar a otimização de planejamento para os cálculos de planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="e28d3-126">For distribution scenarios, customers must use Planning Optimization for master planning calculations.</span></span> <span data-ttu-id="e28d3-127">Para obter mais informações, consulte [Introdução à documentação da Otimização de Planejamento](https://go.microsoft.com/fwlink/?linkid=2105830).</span><span class="sxs-lookup"><span data-stu-id="e28d3-127">For more information, see [Planning Optimization documentation](https://go.microsoft.com/fwlink/?linkid=2105830).</span></span> <span data-ttu-id="e28d3-128">Os clientes com implantações locais do Dynamics 365 Supply Chain Management podem continuar a usar o mecanismo de planejamento mestre de gerenciamento de cadeia de fornecimento para cenários de distribuição depois de 2021 de abril.</span><span class="sxs-lookup"><span data-stu-id="e28d3-128">Customers with on-premises deployments of Dynamics 365 Supply Chain Management may continue to use the Supply Chain Management master planning engine for distribution scenarios after April 2021.</span></span> <span data-ttu-id="e28d3-129">No entanto, não serão fornecidas mais melhorias de recursos.</span><span class="sxs-lookup"><span data-stu-id="e28d3-129">However, no more feature enhancements will be provided.</span></span> |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="e28d3-130">Comunicados anteriores sobre recursos removidos ou obsoletos</span><span class="sxs-lookup"><span data-stu-id="e28d3-130">Previous announcements about removed or deprecated features</span></span>

<span data-ttu-id="e28d3-131">Para saber mais sobre os recursos que foram removidos ou preteridos em versões anteriores, consulte [Recursos removidos ou obsoletos em versões anteriores](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span><span class="sxs-lookup"><span data-stu-id="e28d3-131">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span></span>
