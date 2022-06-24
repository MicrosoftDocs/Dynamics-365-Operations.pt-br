---
title: Trabalho da posição na folha de pagamento
description: Este artigo fornece detalhes e um exemplo de consulta da entidade Trabalho de posição na folha de pagamento no Dynamics 365 Human Resources.
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
ms.openlocfilehash: fa347f4b99adc7c29d69daf62ad2bbfc14726a19
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864073"
---
# <a name="payroll-position-job"></a>Trabalho da posição na folha de pagamento


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo descreve a entidade de Cargo da folha de pagamento para o Dynamics 365 Human Resources.

### <a name="description"></a>Descrição

Essa entidade fornece o relacionamento entre a posição e um trabalho para um determinado plano de remuneração fixa.

Nome físico: mshr_payrollpositionjobentity.

## <a name="properties"></a>Propriedades

| Propriedade</br>**Nome físico**</br>**_Tipo_** | Usar | Descrição |
| --- | --- | --- |
| **ID da posição**</br>mshr_positionid</br>*Sequência de caracteres* | Somente leitura | A ID da posição. |
| **Válido a partir de**</br>mshr_validto</br>*Compensação de Data/Hora* | Somente leitura | A data a partir da qual o cargo e o relacionamento de trabalho são válidos. |
| **Válida até**</br>mshr_validto</br>*Compensação de Data/Hora* | Somente leitura | A data até a qual a posição e o relacionamento de trabalho são válidos. |
| **ID do trabalho**</br>mshr_jobid</br>*Sequência de caracteres* | Somente leitura | A ID do trabalho. |
| **Campo principal**</br>mshr_primaryfield</br>*Sequência de caracteres* | Gerado pelo sistema | O campo principal. |
| **ID da entidade de trabalho da posição na folha de pagamento**</br>mshr_payrollpositionjobentityid</br>*Guid* | Gerado pelo sistema. | Um valor de GUID (identificador global exclusivo) gerado pelo sistema para identificar de forma exclusiva o trabalho. |

## <a name="relations"></a>Relações

| Valor de propriedade | Entidade relacionada | Propriedade Navegação | Tipo de coleção |
| --- | --- | --- | --- |
| _mshr_fk_fixedcompplan_id_value | mshr_payrollfixedcompensationplanentity | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_Job |
| _mshr_fk_jobdetail_id_value | mshr_hcmjobdetailentity | mshr_FK_JobDetail_id | Não aplicável |
| _mshr_fk_payroll_id_value | mshr_payrollpositionentity | mshr_FK_Payroll_id | mshr_FK_PayrollPositionEntity_Job |

## <a name="example-query"></a>Exemplo de consulta

**Solicitação**

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
