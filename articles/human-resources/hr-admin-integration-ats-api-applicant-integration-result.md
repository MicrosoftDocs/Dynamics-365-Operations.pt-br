---
title: Resultado da integração do candidato
description: Este tópico descreve o conjunto de opções de resultados de integração do candidato para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: 425fc78edc933b79879c330284ef911c6fd4fd1c
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066359"
---
# <a name="applicant-integration-result"></a>Resultado da integração do candidato


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve o conjunto de opções de resultados de integração do candidato para o Dynamics 365 Human Resources.

Nome físico: mshr_hcmapplicantintegrationresult

Essa enumeração fornece o status de um registro de candidato.

| Alíquota | Etiqueta | descrição |
| --- | --- | --- |
| 200000000 | Não processado | O candidato ainda está em análise. |
| 200000001 | Contratado | O candidato foi contratado. |
| 200000002 | Não contratado | Foi decidido não contratar o candidato. |
| 200000003 | Ignorado | O candidato foi ignorado na análise. |

## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Exemplo de consulta de candidato a ser contratado](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
