---
title: Status de conclusão
description: Este tópico descreve o conjunto de opções de status de conclusão para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: da91084d30873b79033d789beab829da9fbdb010
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8065537"
---
# <a name="completion-status"></a>Status de conclusão


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve o conjunto de opções de status de conclusão para o Dynamics 365 Human Resources.

Nome físico: mshr_hcmcompletionstatus

Essa enumeração fornece o conjunto de opções de valores de status de triagens de candidato. 

| Valor | Etiqueta | Descrição |
| --- | --- | --- |
| 200000000 | Não concluído | O candidato ainda não concluiu a triagem. |
| 200000001 | Aprovado | O candidato passou na triagem. |
| 200000002 | Falha | O candidato falhou na triagem. |

## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Exemplo de consulta de candidato a ser contratado](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
