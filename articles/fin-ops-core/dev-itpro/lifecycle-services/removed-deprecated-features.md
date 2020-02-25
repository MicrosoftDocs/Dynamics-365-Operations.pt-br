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
<td>Preterido: o componente de diagramas de fluxograma no BPM deve ser removido em 2020. A seguinte funcionalidade será removida:
<ul>
<li>Os fluxogramas existentes não estarão disponíveis para exibição ou edição. As propriedades de forma associadas a atividades de fluxograma também não estarão disponíveis, pois toda a guia <strong>Fluxograma</strong> será removida. Esses fluxogramas incluem os fluxogramas padrão gerados automaticamente e personalizados que são modificados com base nesses fluxogramas padrão.</li>
<li>O recurso análise de lacuna/ajuste herdado não estará disponível. Portanto, nenhuma lista de lacunas será criada automaticamente ou estará disponível para exportação.
<p><strong>Observação:</strong> este recurso foi substituído anteriormente e substituído pelas integrações do Microsoft Azure DevOps.</p>
</li>
<li>O histórico da versão do fluxograma não estará disponível.</li>
</ul>
</td>
</tr>
</tbody>
</table>
