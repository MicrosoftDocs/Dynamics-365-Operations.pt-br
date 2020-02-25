---
title: Recursos removidos ou preteridos em Lifecycle Services (LCS)
description: Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção do Microsoft Dynamics Lifecycle Services (LCS).
author: AngelMarshall
manager: AnnBe
ms.date: 02/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: tsmarsha
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 96ecd040ef8661765c0a3861d8e07fee3c241161
ms.sourcegitcommit: fb7d0efd97754f1ae0b5aa765d0eeb3f57b8078f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3027971"
---
# <a name="removed-or-deprecated-features-in-lifecycle-services-lcs"></a><span data-ttu-id="4e7f9-103">Recursos removidos ou preteridos em Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="4e7f9-103">Removed or deprecated features in Lifecycle Services (LCS)</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="4e7f9-104">Este tópico descreve os recursos que foram removidos ou substituídos do Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="4e7f9-104">This topic describes features that have been removed or deprecated for Microsoft Dynamics Lifecycle Services (LCS).</span></span>

- <span data-ttu-id="4e7f9-105">Um recurso *removido* não está mais disponível no serviço.</span><span class="sxs-lookup"><span data-stu-id="4e7f9-105">A *removed* feature is no longer available in the service.</span></span>
- <span data-ttu-id="4e7f9-106">Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.</span><span class="sxs-lookup"><span data-stu-id="4e7f9-106">A *deprecated* feature isn't in active development and might be removed in a future update.</span></span>

<span data-ttu-id="4e7f9-107">Esta lista é para que você possa considerar essas remoções e reprovações conforme faz seu próprio planejamento.</span><span class="sxs-lookup"><span data-stu-id="4e7f9-107">This list is provided so that you can consider these removals and deprecations as you do your own planning.</span></span>

## <a name="october-2019-announcements"></a><span data-ttu-id="4e7f9-108">Anúncios de Outubro de 2019</span><span class="sxs-lookup"><span data-stu-id="4e7f9-108">October 2019 announcements</span></span>

### <a name="flowchart-diagrams-in-business-process-modeler"></a><span data-ttu-id="4e7f9-109">​Fluxogramas no modelador de processo de negócios​</span><span class="sxs-lookup"><span data-stu-id="4e7f9-109">Flowchart diagrams in Business process modeler</span></span>

<table>
<tbody>
<tr>
<td><span data-ttu-id="4e7f9-110"><strong>Motivo para a reprovação/remoção</strong></span><span class="sxs-lookup"><span data-stu-id="4e7f9-110"><strong>Reason for deprecation/removal</strong></span></span></td>
<td><span data-ttu-id="4e7f9-111">Estamos preterindo o componente de diagramas de fluxograma no BPM (Business Process Modeler), porque o projeto herdado causou baixo uso.</span><span class="sxs-lookup"><span data-stu-id="4e7f9-111">We are deprecating the flowchart diagrams component in Business process modeler (BPM), because the legacy design caused low usage.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4e7f9-112"><strong>Substituída por outro recurso?</strong></span><span class="sxs-lookup"><span data-stu-id="4e7f9-112"><strong>Replaced by another feature?</strong></span></span></td>
<td><span data-ttu-id="4e7f9-113">Não</span><span class="sxs-lookup"><span data-stu-id="4e7f9-113">No</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4e7f9-114"><strong>Áreas afetadas</strong></span><span class="sxs-lookup"><span data-stu-id="4e7f9-114"><strong>Areas affected</strong></span></span></td>
<td><span data-ttu-id="4e7f9-115">Modelador de processo de negócios</span><span class="sxs-lookup"><span data-stu-id="4e7f9-115">Business process modeler</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4e7f9-116"><strong>Status</strong></span><span class="sxs-lookup"><span data-stu-id="4e7f9-116"><strong>Status</strong></span></span></td>
<td><span data-ttu-id="4e7f9-117">Preterido: o componente de diagramas de fluxograma no BPM deve ser removido em 2020.</span><span class="sxs-lookup"><span data-stu-id="4e7f9-117">Deprecated: The flowchart diagrams component in BPM is expected to be removed in 2020.</span></span> <span data-ttu-id="4e7f9-118">A seguinte funcionalidade será removida:</span><span class="sxs-lookup"><span data-stu-id="4e7f9-118">The following functionality will be removed:</span></span>
<ul>
<li><span data-ttu-id="4e7f9-119">Os fluxogramas existentes não estarão disponíveis para exibição ou edição.</span><span class="sxs-lookup"><span data-stu-id="4e7f9-119">Existing flowcharts will be unavailable for viewing or editing.</span></span> <span data-ttu-id="4e7f9-120">As propriedades de forma associadas a atividades de fluxograma também não estarão disponíveis, pois toda a guia <strong>Fluxograma</strong> será removida.</span><span class="sxs-lookup"><span data-stu-id="4e7f9-120">The shape properties that are associated with flowchart activities will also be unavailable, because the whole <strong>Flowchart</strong> tab will be removed.</span></span> <span data-ttu-id="4e7f9-121">Esses fluxogramas incluem os fluxogramas padrão gerados automaticamente e personalizados que são modificados com base nesses fluxogramas padrão.</span><span class="sxs-lookup"><span data-stu-id="4e7f9-121">These flowcharts include both the default flowcharts that are automatically generated and customized flowcharts that are modified based on those default flowcharts.</span></span></li>
<li><span data-ttu-id="4e7f9-122">O recurso análise de lacuna/ajuste herdado não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="4e7f9-122">The legacy fit/gap analysis feature will be unavailable.</span></span> <span data-ttu-id="4e7f9-123">Portanto, nenhuma lista de lacunas será criada automaticamente ou estará disponível para exportação.</span><span class="sxs-lookup"><span data-stu-id="4e7f9-123">Therefore, no gap list will be automatically created or available for export.</span></span>
<p><span data-ttu-id="4e7f9-124"><strong>Observação:</strong> este recurso foi substituído anteriormente e substituído pelas integrações do Microsoft Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="4e7f9-124"><strong>Note:</strong> This feature had previously been deprecated and replaced by Microsoft Azure DevOps integrations.</span></span></p>
</li>
<li><span data-ttu-id="4e7f9-125">O histórico da versão do fluxograma não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="4e7f9-125">The version history of the flowchart will be unavailable.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>
