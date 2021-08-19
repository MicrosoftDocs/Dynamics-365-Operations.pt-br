---
title: Status de isenção de trabalho
description: Este tópico descreve o conjunto de opções de estado de isenção de trabalho para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: 1c3996d8f693b6df0bf6230b25c9339b2aad1ceaf49a790fda90bbfc1b68be41
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6720435"
---
# <a name="job-exempt-status"></a>Status de isenção de trabalho

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve o conjunto de opções de estado de isenção de trabalho para o Dynamics 365 Human Resources.

Nome físico: cdm_jobexemptstatus

Esta enumeração especifica o conjunto de opções de valores de status de isenção de trabalho do FLSA. Isso é fornecido no conjunto de opções de cdm_jobexemptstatus existentes.

| Alíquota | Etiqueta | descrição |
| --- | --- | --- |
| 200000000 | Isenção | O trabalho tem um status de isenção baseado em diretrizes de FLSA. |
| 200000001 | NonExempt | O trabalho tem um status de não isenção baseado em diretrizes de FLSA. |
| 200000002 | Não se Aplica | As diretrizes de status FLSA não se aplicam ao trabalho. |

## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de exemplo de solicitação de recrutamento](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]