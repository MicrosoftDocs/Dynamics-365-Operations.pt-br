---
title: Status da solicitação de recrutamento
description: Este artigo descreve o conjunto de opções Status da solicitação de recrutamento para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: 6a8cb8bc61786425c996b976a2914e7b650e3941
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859594"
---
# <a name="recruiting-request-status"></a>Status da solicitação de recrutamento


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo descreve o conjunto de opções Status da solicitação de recrutamento para o Dynamics 365 Human Resources.

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
