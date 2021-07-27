---
title: Solicitação de licença
description: Este tópico fornece detalhes e um exemplo de consulta da entidade de solicitação de licença no Dynamics 365 Human Resources.
author: marcelbf
ms.date: 06/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b7f5744265dd106f11e6ffe7334873e697a7ea13
ms.sourcegitcommit: 89bb2a7f402deed32998eddc1e56e75250e3d15e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314318"
---
# <a name="leave-request"></a>Solicitação de licença

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve a entidade solicitação de licença para o Dynamics 365 Human Resources.

### <a name="description"></a>descrição

Esta entidade fornece informações sobre uma solicitação de licença.

Nome físico: mshr_essleaverequestentity.

## <a name="properties"></a>Propriedades

| Propriedade</br>**Nome físico**</br>**_Tipo_** | Usar | descrição |
| --- | --- | --- |
| **Id da Solicitação**</br>mshr_requestid</br>*Sequência de caracteres* | Somente leitura | O ID da solicitação. |
| **Id do tipo de licença**</br>mshr_leavetypeid</br>*Sequência de caracteres* | Somente leitura | Id do tipo de licença. |
| **Data**</br>mshr_leavedate</br>*Compensação de Data/Hora* | Somente leitura | A data da solicitação de licença. |
| **Valor**</br>mshr_amount</br>*Decimal* | Somente leitura | O valor da solicitação de licença. |
| **Tipo de meio dia**</br>mshr_halfdaydefinition</br>*opção mshr_LeaveHalfDayDefinition definida* | Somente leitura | O tipo de licença de meio dia. |
| **Comentar**</br>mshr_comment</br>*Sequência de caracteres* | Somente leitura | Comentário da solicitação. |
| **Status**</br>mshr_status</br>*conjunto de opções mshr_status* | Somente leitura | O status da solicitação. |
| **Data**</br>mshr_requestdate</br>*Compensação de Data/Hora* | Somente leitura | A data da solicitação. |
| **Número da equipe**</br>mshr_personnelnumber</br>*Sequência de caracteres* | Somente leitura | O número da equipe exclusiva do funcionário. |
| **Id do código do motivo**</br>mshr_reasoncodeid</br>*Sequência de caracteres* | Somente leitura | O ID do código do motivo. |
| **ID da área de dados**</br>mshr_dataareaid</br>*Sequência de caracteres* | Somente leitura | Especifica a entidade legal (empresa). |
| **Campo principal**</br>mshr_primaryfield</br>*GUID* | Somente leitura</br>Gerado pelo sistema | |
| **Entidade de tipo de licença**</br>mshr_essleaverequestentityid</br>*GUID* | Gerado pelo sistema | Um valor GUID gerado pelo sistema para identificar exclusivamente a solicitação de licença. |

## <a name="example-query"></a>Exemplo de consulta

**Solicitar**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleaverequestentities?$filter=mshr_personnelnumber eq '000020'
```

**Resposta**

```json
{
    "mshr_requestid": "USMF-000001",
    "mshr_leavetype": "PTO",
    "mshr_leavedate": "2017-01-02T00:00:00Z",
    "mshr_amount": 8,
    "mshr_halfdaydefinition": 200000000,
    "mshr_comment": "Taking a week off to relax",
    "mshr_status": 200000009,
    "mshr_requestdate": "2017-07-31T00:00:00Z",
    "mshr_personnelnumber": "000020",
    "mshr_reasoncodeid": "",
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "USMF-000001 | PTO | 1/2/2017",
    "mshr_essleaverequestentityid": "000004dd-0000-0000-0f00-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Consulte também

[Introdução à API de integração da folha de pagamento](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
