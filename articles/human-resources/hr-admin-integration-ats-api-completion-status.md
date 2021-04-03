---
title: Status de conclusão
description: Este tópico descreve o conjunto de opções de status de conclusão para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: d8ea90785f303301a21a4ac799578b08cabd0e3d
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5468194"
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