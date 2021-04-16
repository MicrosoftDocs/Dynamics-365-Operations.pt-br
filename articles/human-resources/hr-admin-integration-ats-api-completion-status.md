---
title: Status de conclusão
description: Este tópico descreve o conjunto de opções de status de conclusão para o Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f1b0c61ac9d9dc611d2a4700a1a004e3d15b4445
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798360"
---
# <a name="completion-status"></a>Status de conclusão

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