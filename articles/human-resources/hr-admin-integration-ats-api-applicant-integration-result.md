---
title: Resultado da integração do candidato
description: Este tópico descreve o conjunto de opções de resultados de integração do candidato para o Dynamics 365 Human Resources.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 157864cd0eee879013724615ce31306c99c5aa68
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125800"
---
# <a name="applicant-integration-result"></a>Resultado da integração do candidato

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
