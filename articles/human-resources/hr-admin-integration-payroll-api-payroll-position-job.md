---
title: Trabalho da posição na folha de pagamento
description: Este tópico fornece detalhes e um exemplo de consulta da entidade Trabalho de posição na folha de pagamento no Dynamics 365 Human Resources.
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d5f84a1a6ff794cdc8b4b81e8518983789a0b33f1708719906f6ad094d9c4285
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722622"
---
# <a name="payroll-position-job"></a>Trabalho da posição na folha de pagamento

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve a entidade de Cargo da folha de pagamento para o Dynamics 365 Human Resources.

### <a name="description"></a>descrição

Essa entidade fornece o relacionamento entre a posição e um trabalho para um determinado plano de remuneração fixa.

Nome físico: mshr_payrollpositionjobentity.

## <a name="properties"></a>Propriedades

| Propriedade<br>**Nome físico**<br>**_Tipo_** | Usar | descrição |
| --- | --- | --- |
| **ID do trabalho**<br>mshr_jobid<br>*Sequência de caracteres* | Somente leitura<br>Obrigatório |A ID do trabalho. |
| **Válido a partir de**<br>mshr_validto<br>*Compensação de Data/Hora* | Somente leitura <br>Obrigatório | Data a partir da qual o cargo e o relacionamento de trabalho são válidos. |
| **Válida até**<br>mshr_validto<br>*Compensação de Data/Hora* | Somente leitura <br>Obrigatório | Data até a qual a posição e o relacionamento de trabalho são válidos.  |
| **ID da posição**<br>mshr_positionid<br>*Sequência de caracteres* | Somente leitura<br>Obrigatório | A ID da posição. |
| **Campo principal**<br>mshr_primaryfield<br>*Sequência de caracteres* | Obrigatório<br>Gerado pelo sistema |  |
| **Valor de ID de trabalho da posição**<br>_mshr_fk_positionjob_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave externa: mshr_PayrollPositionJobEntity da mshr_payrollpositionjobentity |A ID do trabalho associado à posição.|
| **Valor da ID do plano de remuneração fixa**<br>_mshr_fk_fixedcompplan_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: mshr_FixedCompPlan_id de mshr_payrollfixedcompensationplanentity  | A ID do plano de remuneração fixa associado à posição. |
| **ID da entidade de trabalho da posição na folha de pagamento**<br>mshr_payrollpositionjobentityid<br>*Guid* | Obrigatório<br>Gerado pelo sistema. | Um valor GUID gerado pelo sistema para identificar exclusivamente o trabalho.  |

## <a name="example-query"></a>Exemplo de consulta

**Solicitar**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionjobentities?$filter=mshr_positionid eq '000276'
```

**Resposta**

```json
{
    "mshr_positionid": "000276",
    "mshr_validfrom": "2016-07-06T18:11:33Z",
    "mshr_validto": "2154-12-31T23:59:59Z",
    "mshr_jobid": "Accountant",
    "mshr_primaryfield": "000276 | Accountant | 7/6/2016 06:11:33 pm",
    "_mshr_fk_jobdetail_id_value": "00000b8d-0000-0000-b0ff-004105000000",
    "_mshr_fk_fixedcompplan_id_value": "0000058a-0000-0000-d5ff-004105000000",
    "_mshr_fk_payroll_id_value": "00000427-0000-0000-df00-014105000000",
    "mshr_payrollpositionjobentityid": "00000906-0000-0000-df00-014105000000"
}
```

## <a name="see-also"></a>Consulte também

[Introdução à API de integração da folha de pagamento](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
