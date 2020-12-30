---
title: Recursos removidos ou preteridos em Lifecycle Services (LCS)
description: Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção do Microsoft Dynamics Lifecycle Services (LCS).
author: AngelMarshall
manager: AnnBe
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: tsmarsha
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: abf7a1a0a75ac3098efeeab3df65481999b69acc
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687869"
---
# <a name="removed-or-deprecated-features-in-lifecycle-services-lcs"></a><span data-ttu-id="09486-103">Recursos removidos ou preteridos em Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="09486-103">Removed or deprecated features in Lifecycle Services (LCS)</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="09486-104">Este tópico descreve os recursos que foram removidos ou substituídos do Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="09486-104">This topic describes features that have been removed or deprecated for Microsoft Dynamics Lifecycle Services (LCS).</span></span>

- <span data-ttu-id="09486-105">Um recurso *removido* não está mais disponível no serviço.</span><span class="sxs-lookup"><span data-stu-id="09486-105">A *removed* feature is no longer available in the service.</span></span>
- <span data-ttu-id="09486-106">Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.</span><span class="sxs-lookup"><span data-stu-id="09486-106">A *deprecated* feature isn't in active development and might be removed in a future update.</span></span>

<span data-ttu-id="09486-107">Esta lista é para que você possa considerar essas remoções e reprovações conforme faz seu próprio planejamento.</span><span class="sxs-lookup"><span data-stu-id="09486-107">This list is provided so that you can consider these removals and deprecations as you do your own planning.</span></span>

## <a name="october-2019-announcements"></a><span data-ttu-id="09486-108">Anúncios de Outubro de 2019</span><span class="sxs-lookup"><span data-stu-id="09486-108">October 2019 announcements</span></span>

### <a name="flowchart-diagrams-in-business-process-modeler"></a><span data-ttu-id="09486-109">​Fluxogramas no modelador de processo de negócios​</span><span class="sxs-lookup"><span data-stu-id="09486-109">Flowchart diagrams in Business process modeler</span></span>

<table>
<tbody>
<tr>
<td><span data-ttu-id="09486-110"><strong>Motivo para a reprovação/remoção</strong></span><span class="sxs-lookup"><span data-stu-id="09486-110"><strong>Reason for deprecation/removal</strong></span></span></td>
<td><span data-ttu-id="09486-111">Estamos preterindo o componente de diagramas de fluxograma no BPM (Business Process Modeler), porque o projeto herdado causou baixo uso.</span><span class="sxs-lookup"><span data-stu-id="09486-111">We are deprecating the flowchart diagrams component in Business process modeler (BPM), because the legacy design caused low usage.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="09486-112"><strong>Substituída por outro recurso?</strong></span><span class="sxs-lookup"><span data-stu-id="09486-112"><strong>Replaced by another feature?</strong></span></span></td>
<td><span data-ttu-id="09486-113">Não</span><span class="sxs-lookup"><span data-stu-id="09486-113">No</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="09486-114"><strong>Áreas afetadas</strong></span><span class="sxs-lookup"><span data-stu-id="09486-114"><strong>Areas affected</strong></span></span></td>
<td><span data-ttu-id="09486-115">Modelador de processo de negócios</span><span class="sxs-lookup"><span data-stu-id="09486-115">Business process modeler</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="09486-116"><strong>Status</strong></span><span class="sxs-lookup"><span data-stu-id="09486-116"><strong>Status</strong></span></span></td>
<td><span data-ttu-id="09486-117">Preterido: o componente de diagramas de fluxograma no BPM deve ser removido em 2020.</span><span class="sxs-lookup"><span data-stu-id="09486-117">Deprecated: The flowchart diagrams component in BPM is expected to be removed in 2020.</span></span> <span data-ttu-id="09486-118">A seguinte funcionalidade estará indisponível:</span><span class="sxs-lookup"><span data-stu-id="09486-118">The following functionality will be unavailable:</span></span>
<ul>
<li><span data-ttu-id="09486-119">Todos os fluxogramas serão somente leitura e não estarão disponíveis para edição.</span><span class="sxs-lookup"><span data-stu-id="09486-119">All flowcharts will be read-only and unavailable for editing.</span></span> <span data-ttu-id="09486-120">As propriedades de forma associadas a atividades de fluxograma também não estarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="09486-120">The shape properties that are associated with flowchart activities will also be unavailable.</span></span> <span data-ttu-id="09486-121">Esses fluxogramas incluem os fluxogramas padrão gerados automaticamente e personalizados que são modificados com base nesses fluxogramas padrão.</span><span class="sxs-lookup"><span data-stu-id="09486-121">These flowcharts include both the default flowcharts that are automatically generated and customized flowcharts that are modified based on those default flowcharts.</span></span></li>
<li><span data-ttu-id="09486-122">As etapas do processo serão somente leitura e não estarão disponíveis para edição.</span><span class="sxs-lookup"><span data-stu-id="09486-122">The process steps will be read-only and unavailable for editing.</span></span></li>     
<li><span data-ttu-id="09486-123">O recurso análise de lacuna/ajuste herdado não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="09486-123">The legacy fit/gap analysis feature will be unavailable.</span></span> <span data-ttu-id="09486-124">Portanto, nenhuma lista de lacunas será criada automaticamente ou estará disponível para exportação.</span><span class="sxs-lookup"><span data-stu-id="09486-124">Therefore, no gap list will be automatically created or available for export.</span></span>
<p><span data-ttu-id="09486-125"><strong>Observação:</strong> este recurso foi substituído anteriormente e substituído pelas integrações do Microsoft Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="09486-125"><strong>Note:</strong> This feature had previously been deprecated and replaced by Microsoft Azure DevOps integrations.</span></span></p>
</li>
<li><span data-ttu-id="09486-126">O histórico da versão do fluxograma não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="09486-126">The version history of the flowchart will be unavailable.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>
