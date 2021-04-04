---
title: Status da posição da solicitação de recrutamento
description: Este tópico descreve o conjunto de opções de status de posição da solicitação de recrutamento para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: 01e8aa5157d0ad1c01f996886e7845e49ab97603
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464709"
---
# <a name="recruiting-request-position-status"></a>Status da posição da solicitação de recrutamento

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve o conjunto de opções de status de posição da solicitação de recrutamento para o Dynamics 365 Human Resources.

Nome físico: mshr_hcmrecruitingrequestpositionstatus

Essa enumeração fornece o conjunto de opções para os valores de status de cada posição em uma solicitação de recrutamento na entidade RecruitingRequestPosition.

| Alíquota | Etiqueta | Descrição |
| --- | --- | --- |
| 200000000 | Em Aberto | A posição na solicitação de recrutamento está aberta para recrutamento. Isso não indica que não há atribuição de posição ativa no momento para a posição. Pode haver um funcionário na posição no momento do recrutamento. Isso indica apenas que a posição está disponível para recrutamento no contexto da solicitação de recrutamento. |
| 200000001 | Preenchida | Um trabalhador foi selecionado para atribuição à posição. |
| 200000002 | Cancelado | A solicitação de recrutamento para essa posição foi cancelada. |

## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de exemplo de solicitação de recrutamento](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]