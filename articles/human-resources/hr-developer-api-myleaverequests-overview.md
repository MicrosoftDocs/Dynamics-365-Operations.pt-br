---
title: Visão geral de MyLeaveRequests
description: A entidade MyLeaveRequests no Microsoft Dynamics 365 Human Resources fornece a lista de solicitações de licença no sistema, com escopo (limitado) para as solicitações acessíveis ao usuário atual que consulta a entidade.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 44e23a076733bac782a0366aeba3456911522abe
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803624"
---
# <a name="myleaverequests-overview"></a>Visão geral de MyLeaveRequests

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A entidade MyLeaveRequests no Microsoft Dynamics 365 Human Resources fornece a lista de solicitações de licença no sistema, com escopo (limitado) para as solicitações acessíveis ao usuário atual que consulta a entidade.

## <a name="key"></a>Chave

  | Nome da Propriedade | Tipo de Dados |
  |---------------|-----------|
  | dataAreaId    | Sequência de caracteres    |
  | RequestId     | Sequência de caracteres    |
  | LeaveType     | Sequência de caracteres    |
  | LeaveDate     | Data       |
  
## <a name="properties"></a>Propriedades

  | Nome da Propriedade     | Tipo de Dados | Obrigatório |
  |-------------------|-----------|----------|
  | dataAreaId        | Sequência de caracteres    | X        |
  | RequestId         | Sequência de caracteres    | X        |
  | LeaveType         | Sequência de caracteres    | X        |
  | LeaveDate         | Data       | X        |
  | ReasonCodeId      | Sequência de caracteres    |          |
  | PersonnelNumber   | Sequência de caracteres    | X        |
  | RequestDate       | Data       | X        |
  | Comentário           | Sequência de caracteres    |          |
  | Status            | Enumeração      | X        |
  | Valor            | Real      |          |
  | HalfDayDefinition | Enumeração      |          |

## <a name="actions"></a>Ações

 | Nome da Ação                               | Descrição                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [enviar](hr-developer-api-myleaverequests-submit.md)   | Envie a solicitação para ser processada pelo fluxo de trabalho. |

## <a name="see-also"></a>Consulte também

- [Enviar uma solicitação de licença para o fluxo de trabalho](hr-developer-api-myleaverequests-submit.md)
- [Autenticação](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]