---
title: Status de isenção de trabalho
description: Este tópico descreve o conjunto de opções de estado de isenção de trabalho para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: 1f211002468384227acb2343ed6cbc6ae2a215d1
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464443"
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