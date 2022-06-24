---
title: Detalhes da folha de pagamento para Posições
description: Este artigo fornece detalhes e um exemplo de consulta para os detalhes da folha de pagamento da entidade Cargos no Dynamics 365 Human Resources.
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
ms.openlocfilehash: ac36b0386312e1631528b8ab5976db2cb3924caf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904120"
---
# <a name="payroll-position"></a>Posição na folha de pagamento


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo descreve a entidade Cargos da folha de pagamento no Dynamics 365 Human Resources.

Nome físico: mshr_payrollpositionentity.

### <a name="description"></a>descrição

Esta entidade fornece informações de cargo sobre um funcionário determinado.

Nome físico: mshr_payrollpositionentity.

## <a name="properties"></a>Propriedades

| Propriedade</br>**Nome físico**</br>**_Tipo_** | Usar | Descrição |
| --- | --- | --- |
| **ID da posição**</br>mshr_positionid</br>*Sequência de caracteres* | Somente leitura | A ID da posição. |
| **ID do ciclo de pagamento**</br>mshr_paycycleid</br>*Sequência de caracteres* | Somente leitura | O ciclo de pagamento definido na posição. |
| **Horas normais anuais**</br>annualregularhours</br>*Decimal* | Somente leitura | O horário normal anual definido na posição. |
| **Pago por entidade legal**</br>paidbylegalentity</br>*Sequência de caracteres* | Somente leitura | A entidade legal definida na posição e no responsável pela emissão do pagamento. |
| **Válida até**</br>validto</br>*Compensação de Data/Hora* | Somente leitura | A data até a qual os detalhes da posição são válidos. |
| **Válido a partir de**</br>validfrom</br>*Compensação de Data/Hora* | Somente leitura | A data a partir da qual os detalhes da posição são válidos. |
| **Campo principal**</br>mshr_primaryfield</br>*Sequência de caracteres* | Gerado pelo sistema | O campo principal. |
| **ID da entidade Detalhes da posição de folha de pagamento**</br>payrollpositiondetailsentityid</br>*Guid* | Obrigatório</br>Gerado pelo sistema. | Um valor de GUID (identificador global exclusivo) gerado pelo sistema para identificar de forma exclusiva a posição. |

## <a name="relations"></a>Relações

| Valor de propriedade | Entidade relacionada | Propriedade Navegação | Tipo de coleção |
| --- | --- | --- | --- |
| _mshr_fk_fixedcompplan_id_value | [mshr_payrollfixedcompensationplanentity](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md) | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_PayrollPosition |
| _mshr_fk_hcmpositionhierarchy_id_value | mshr_hcmpositionhierarchyentity | mshr_FK_HcmPositionHierarchy_id | Não aplicável |
| _mshr_fk_job_id_value | mshr_payrollpositionjobentity | mshr_FK_Job_id | mshr_FK_PayrollPositionJobEntity_Payroll |
| _mshr_fk_positionassignmentv2_id_value | mshr_hcmpositionworkerassignmentv2entity | mshr_FK_PositionAssignmentV2_id | Não aplicável |

## <a name="example-query"></a>Exemplo de consulta

**Solicitação**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionentities?$filter=mshr_positionid eq @positionid and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@positionid='000276'&@asofdate=2021-04-01
```

**Resposta**

```json
{
    "mshr_positionid": "000276",
    "mshr_paycycleid": "w",
    "mshr_annualregularhours": 3000,
    "mshr_paidbylegalentity": "USMF",
    "mshr_validfrom": "2021-03-14T00:00:00Z",
    "mshr_validto": "2154-12-31T00:00:00Z",
    "mshr_primaryfield": "000276 | 3/14/2021",
    "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
    "_mshr_fk_fixedcompplan_id_value": "0000029f-0000-0000-d5ff-004105000000",
    "mshr_payrollpositionentityid": "00010097-0000-0000-df00-014105000000"
}
```

## <a name="see-also"></a>Consulte também

[Introdução à API de integração da folha de pagamento](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
