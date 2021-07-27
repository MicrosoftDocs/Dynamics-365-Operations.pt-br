---
title: Detalhes da folha de pagamento para Posições
description: Este tópico fornece detalhes e um exemplo de consulta para os detalhes da folha de pagamento da entidade Posições no Dynamics 365 Human Resources.
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
ms.openlocfilehash: e13a6b3608802eb7bb2bc00686c2e914cc765587
ms.sourcegitcommit: 89bb2a7f402deed32998eddc1e56e75250e3d15e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314156"
---
# <a name="payroll-position"></a>Posição na folha de pagamento

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve a entidade de Cargos da folha de pagamento no Dynamics 365 Human Resources.

Nome físico: mshr_payrollpositionentity.

### <a name="description"></a>descrição

Esta entidade fornece informações de cargo sobre um funcionário determinado.

Nome físico: 

## <a name="properties"></a>Propriedades

| Propriedade<br>**Nome físico**<br>**_Tipo_** | Usar | descrição |
| --- | --- | --- |
| **Horas normais anuais**<br>annualregularhours<br>*Decimal* | Somente leitura<br>Obrigatório | Horas normais anuais definidas na posição.  |
| **ID da entidade Detalhes da posição de folha de pagamento**<br>payrollpositiondetailsentityid<br>*Guid* | Obrigatório<br>Gerado pelo sistema. | Um valor GUID gerado pelo sistema para identificar exclusivamente a posição.  |
| **Campo principal**<br>mshr_primaryfield<br>*Cadeia de caracteres* | Obrigatório<br>Gerado pelo sistema |  |
| **Valor de ID de trabalho da posição**<br>_mshr_fk_positionjob_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave externa: mshr_PayrollPositionJobEntity da mshr_payrollpositionjobentity |A ID do trabalho associado à posição.|
| **Valor da ID do plano de remuneração fixa**<br>_mshr_fk_fixedcompplan_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: mshr_FixedCompPlan_id de mshr_payrollfixedcompensationplanentity  | A ID do plano de remuneração fixa associado à posição. |
| **ID do ciclo de pagamento**<br>mshr_primaryfield<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório | O ciclo de pagamento definido na posição. |
| **Pago por entidade legal**<br>paidbylegalentity<br>*Sequência de caracteres* | Somente leitura<br>Obrigatório | A entidade legal definida na posição responsável pela emissão do pagamento. |
| **ID da posição**<br>mshr_positionid<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório | A ID da posição. |
| **Válida até**<br>validto<br>*Compensação de Data/Hora* | Somente leitura<br>Obrigatório |A data a partir da qual detalhes da posição são válidos.  |
| **Válido a partir de**<br>validfrom<br>*Compensação de Data/Hora* | Somente leitura<br>Obrigatório |A data até a qual detalhes da posição são válidos.  |

## <a name="example-query"></a>Exemplo de consulta

**Solicitar**

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
