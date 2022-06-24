---
title: Status de isenção de trabalho
description: Este artigo descreve o conjunto de opções de status Isenção de trabalho para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: e59a71264d50cecce4d31dfa26ad7f05ef3f34e4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894662"
---
# <a name="job-exempt-status"></a>Status de isenção de trabalho


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo descreve o conjunto de opções de status Isenção de trabalho para o Dynamics 365 Human Resources.

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
