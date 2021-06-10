---
title: Status da solicitação de recrutamento
description: Este tópico descreve o conjunto de opções de Status da solicitação de recrutamento para o Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3b05cc531a84144708ff52913927bbd04574a3b2
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059175"
---
# <a name="recruiting-request-status"></a>Status da solicitação de recrutamento

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve o conjunto de opções de Status da solicitação de recrutamento para o Dynamics 365 Human Resources.

Nome físico: mshr_hcmrecruitingrequeststatus

Essa enumeração fornece o conjunto de opções dos valores de status de um RecruitingRequest.

| Alíquota | Etiqueta | descrição |
| --- | --- | --- |
| 200000000 | Preliminar | A solicitação está em rascunho e não está pronta para recrutamento ativo. |
| 200000001 | Em Revisão | A solicitação foi enviada e está sendo roteada para aprovação por fluxo de trabalho. Disponível apenas quando o fluxo de trabalho está habilitado. |
| 200000002 | Pendente | A solicitação é uma ação de fluxo de trabalho pendente. Disponível apenas quando o fluxo de trabalho está habilitado. |
| 200000003 | Cancelados(as) | A solicitação foi cancelada. Disponível apenas quando o fluxo de trabalho está habilitado. |
| 200000004 | Negada | A solicitação foi negada. Disponível apenas quando o fluxo de trabalho está habilitado. |
| 200000005 | Com atividade | Qualquer fluxo de trabalho é concluído e aprovado, e a solicitação está pronta para o recrutamento ativo. |
| 200000006 | Fechadas | A solicitação de recrutamento está fechada. |

## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de exemplo de solicitação de recrutamento](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]