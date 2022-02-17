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
ms.openlocfilehash: 29d3c4fd37a219b520172c6866c5fec488c698f7
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8064982"
---
# <a name="job-exempt-status"></a>Status de isenção de trabalho


[!INCLUDE [PEAP](../includes/peap-1.md)]

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
