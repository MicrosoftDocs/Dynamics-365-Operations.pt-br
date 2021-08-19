---
title: Saldo de licença
description: Este tópico fornece detalhes e um exemplo de consulta da entidade de saldo de licença no Dynamics 365 Human Resources.
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
ms.openlocfilehash: ab136e9b40de280387dc3c5207a08a6bb357941feb3a8c736d9671f7850f2bf8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6782674"
---
# <a name="leave-balance"></a>Saldo de licença

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve a entidade saldo de licença para o Dynamics 365 Human Resources.

### <a name="description"></a>descrição

Esta entidade fornece o tipo de saldo por licença para um determinado funcionário.

Nome físico: mshr_essleavebalanceentities.

## <a name="properties"></a>Propriedades

| Propriedade</br>**Nome físico**</br>**_Tipo_** | Usar | descrição |
| --- | --- | --- |
| **Número da equipe**</br>mshr_personnelnumber</br>*Sequência de caracteres* | Somente leitura | O número da equipe exclusiva do funcionário. |
| **Saldo atual**</br>mshr_balanceavailable</br>*Decimal* | Somente leitura | O saldo atual do funcionário. |
| **Tipo**</br>mshr_balanceavailable</br>*Sequência de caracteres* | Somente leitura | Id do tipo de licença. |
| **Taxa da competência**</br>mshr_accrualratedescription</br> | Somente leitura | A taxa de acúmulo. |
| **Último valor postergado**</br>mshr_lastcarryforwardamount</br>*Decimal* | Somente leitura | O Valor de Último postergar. |
| **Tirado este ano**</br>mshr_takenthisyear</br>*Decimal* | Somente leitura | A quantidade de licenças feitas neste ano. |
| **Total neste ano**</br>mshr_totalthisyear</br>*Decimal* | Somente leitura | O valor total deste ano. |
| **ID da área de dados**</br>mshr_dataareaid_id</br>*Sequência de caracteres* | Somente leitura | Especifica a entidade legal (empresa). |
| **Campo principal**</br>mshr_primaryfield</br>*GUID* | Somente leitura</br>Gerado pelo sistema | |
| **Id do tipo de licença**</br>_mshr_fk_leavetype_id_value</br>*GUID* | Somente leitura</br>Chave estrangeira: mshr_essleavetypeentityid da entidade mshr_essleavetypeentity  | ID do tipo de licença |
| **Entidade de saldo de licença**</br>mshr_essleavebalanceentityid</br>*GUID* | Gerado pelo sistema | Um valor GUID gerado pelo sistema para identificar exclusivamente o saldo. |

## <a name="example-query"></a>Exemplo de consulta

**Solicitar**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleavebalanceentities?$filter=mshr_personnelnumber eq '000013'
```

**Resposta**

```json
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 67.76,
    "mshr_leavetypeid": "PTO",
    "mshr_accrualratedescription": "6.16 hrs / Semimonthly",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 67.76,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | PTO",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-0000-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-2703-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 80,
    "mshr_leavetypeid": "Sick",
    "mshr_accrualratedescription": "80.00 hrs / Annually",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 80,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Sick",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-ee02-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-3003-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 0,
    "mshr_leavetypeid": "Bereavement",
    "mshr_accrualratedescription": "0.00 hrs / Annually",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 0,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Bereavement",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-f402-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-4403-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 66.65,
    "mshr_leavetypeid": "Vacation",
    "mshr_accrualratedescription": "13.33 hrs / Monthly",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 66.65,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Vacation",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-f502-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-1009-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Consulte também

[Introdução à API de integração da folha de pagamento](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
