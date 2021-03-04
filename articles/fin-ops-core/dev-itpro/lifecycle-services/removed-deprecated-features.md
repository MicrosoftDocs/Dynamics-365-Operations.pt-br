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
# <a name="removed-or-deprecated-features-in-lifecycle-services-lcs"></a>Recursos removidos ou preteridos em Lifecycle Services (LCS)

[!include[banner](../includes/banner.md)]

Este tópico descreve os recursos que foram removidos ou substituídos do Microsoft Dynamics Lifecycle Services (LCS).

- Um recurso *removido* não está mais disponível no serviço.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Esta lista é para que você possa considerar essas remoções e reprovações conforme faz seu próprio planejamento.

## <a name="october-2019-announcements"></a>Anúncios de Outubro de 2019

### <a name="flowchart-diagrams-in-business-process-modeler"></a>​Fluxogramas no modelador de processo de negócios​

<table>
<tbody>
<tr>
<td><strong>Motivo para a reprovação/remoção</strong></td>
<td>Estamos preterindo o componente de diagramas de fluxograma no BPM (Business Process Modeler), porque o projeto herdado causou baixo uso.</td>
</tr>
<tr>
<td><strong>Substituída por outro recurso?</strong></td>
<td>Não</td>
</tr>
<tr>
<td><strong>Áreas afetadas</strong></td>
<td>Modelador de processo de negócios</td>
</tr>
<tr>
<td><strong>Status</strong></td>
<td>Preterido: o componente de diagramas de fluxograma no BPM deve ser removido em 2020. A seguinte funcionalidade estará indisponível:
<ul>
<li>Todos os fluxogramas serão somente leitura e não estarão disponíveis para edição. As propriedades de forma associadas a atividades de fluxograma também não estarão disponíveis. Esses fluxogramas incluem os fluxogramas padrão gerados automaticamente e personalizados que são modificados com base nesses fluxogramas padrão.</li>
<li>As etapas do processo serão somente leitura e não estarão disponíveis para edição.</li>     
<li>O recurso análise de lacuna/ajuste herdado não estará disponível. Portanto, nenhuma lista de lacunas será criada automaticamente ou estará disponível para exportação.
<p><strong>Observação:</strong> este recurso foi substituído anteriormente e substituído pelas integrações do Microsoft Azure DevOps.</p>
</li>
<li>O histórico da versão do fluxograma não estará disponível.</li>
</ul>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]