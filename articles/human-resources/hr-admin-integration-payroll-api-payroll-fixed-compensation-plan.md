---
title: Plano de remuneração fixa da folha de pagamento
description: Este tópico fornece detalhes e um exemplo de consulta da entidade Plano de remuneração fixa da folha de pagamento no Dynamics 365 Human Resources.
author: jcart
ms.date: 08/25/2021
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
ms.openlocfilehash: 14829f18fb5e3adde83e265cd6e70b60e1ff03ac
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8069087"
---
# <a name="payroll-fixed-compensation-plan"></a>Plano de remuneração fixa da folha de pagamento


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve a entidade Plano de remuneração fixa da folha de pagamento para o Dynamics 365 Human Resources.

### <a name="description"></a>descrição

Esta entidade fornece o plano de remuneração fixa atribuído a um determinado cargo de um funcionário.

Nome físico: mshr_payrollfixedcompensationplanentity.

## <a name="properties"></a>Propriedades

| Propriedade</br>**Nome físico**</br>**_Tipo_** | Usar | descrição |
| --- | --- | --- |
| **ID do Plano**</br>mshr_planid</br>*Sequência de caracteres* | Somente leitura | Especifica o plano da remuneração.  |
| **Número da equipe**</br>mshr_personnelnumber</br>*Sequência de caracteres* | Somente leitura | O número da equipe exclusiva do funcionário. |
| **Taxa de pagamento**</br>mshr_payrate</br>*Decimal* | Somente leitura | A taxa de pagamento definida no plano de remuneração fixa. |
| **ID da posição**</br>mshr_positionid</br>*Sequência de caracteres* | Somente leitura | ID do cargo associada ao funcionário e ao registro do plano de remuneração fixa. |
| **Válido a partir de**</br>mshr_validfrom</br>*Compensação de Data/Hora* |  Somente leitura | Data a partir da qual a remuneração fixa do funcionário é válida.  |
| **Válida até**</br>mshr_validto</br>*Compensação de Data/Hora* | Somente leitura | Data até a qual a remuneração fixa do funcionário é válida. |
| **Frequência de pagamento**</br>mshr_payfrequency</br>*Sequência de caracteres* | Somente leitura | A ID da [frequência de pagamento de remuneração](hr-admin-integration-payroll-api-compensation-pay-frequency.md) para a taxa de pagamento especificada. |
| **Moeda**</br>mshr_currency</br>*Sequência de caracteres* | Somente leitura | A moeda definida para o plano de remuneração fixa. |
| **Entidade Plano de remuneração fixa da folha de pagamento**</br>mshr_payrollfixedcompensationplanentityid</br>*GUID* | Gerado pelo sistema | Um valor GUID gerado pelo sistema para identificar exclusivamente o plano de remuneração. |

## <a name="relations"></a>Relações

|Valor de propriedade | Entidade relacionada | Propriedade Navegação | Tipo de coleção |
| --- | --- | --- | --- |
| _mshr_fk_employee_id_value | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | mshr_FK_Employee_id | mshr_FK_PayrollEmployeeEntity_FixedCompPlan |
| _mshr_fk_job_id_value | [mshr_payrollpositionjobentity](hr-admin-integration-payroll-api-payroll-position-job.md) | mshr_FK_Job_id | mshr_FK_PayrollPositionJobEntity_FixedCompPlan |
| _mshr_fk_payrollposition_id_value | [mshr_payrollpositionentity](hr-admin-integration-payroll-api-payroll-position.md) | mshr_FK_PayrollPosition_id | mshr_FK_PayrollPositionEntity_FixedCompPlan |
| _mshr_fk_plan_id_value | mshr_hcmcompfixedplantableentity | mshr_FK_Plan_id | - |
| _mshr_fk_variablecompaward_id_value | [mshr_payrollvariablecompensationawardentity](hr-admin-integration-payroll-api-payroll-variable-compensation-plan.md) | mshr_FK_VariableCompAward_id | mshr_FK_PayrollVariableCompensationAwardEntity_FixedComp |

## <a name="example-query"></a>Exemplo de consulta

**Solicitar**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollfixedcompensationplanentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

**Resposta**

```json
{
    "mshr_planid": "GradeC",
    "mshr_personnelnumber": "000041",
    "mshr_payrate": 75200,
    "mshr_positionid": "000276",
    "mshr_validfrom": "2011-04-05T00:00:00Z",
    "mshr_validto": "2154-12-31T00:00:00Z",
    "mshr_payfrequency": "Annual",
    "mshr_currency": "USD",
    "_mshr_fk_employee_id_value": "00000d3c-0000-0000-d5ff-004105000000",
    "_mshr_fk_plan_id_value": "0000070c-0000-0000-b328-fef003000000",
    "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
    "mshr_payrollfixedcompensationplanentityid": "0000029f-0000-0000-d5ff-004105000000",
    "_mshr_fk_payroll_id_value": null
}
```

## <a name="see-also"></a>Consulte também

[Introdução à API de integração da folha de pagamento](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
