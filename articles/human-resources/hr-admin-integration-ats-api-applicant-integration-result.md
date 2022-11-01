---
title: Resultado da integração do candidato
description: Este artigo descreve o conjunto de opções de resultado de integração do candidato para o Dynamics 365 Human Resources.
author: jaredha
ms.date: 09/12/2022
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
ms.openlocfilehash: 86f3f75e538268644cea4f927f04c07aae115f00
ms.sourcegitcommit: 27ce4fc706100b626b81c3a1023238acd872e76c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2022
ms.locfileid: "9702219"
---
# <a name="applicant-integration-result"></a>Resultado da integração do candidato


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo descreve o conjunto de opções de resultado de integração do candidato para o Dynamics 365 Human Resources.

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
