---
title: Plano de remuneração fixa da folha de pagamento
description: Este tópico fornece detalhes e um exemplo de consulta da entidade Plano de remuneração fixa da folha de pagamento no Dynamics 365 Human Resources.
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 85cfce6f626090adab422ea6c60fc0778fd1ac67
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021287"
---
# <a name="payroll-fixed-compensation-plan"></a>Plano de remuneração fixa da folha de pagamento

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico fornece detalhes e um exemplo de consulta da entidade Plano de remuneração fixa da folha de pagamento no Dynamics 365 Human Resources.

## <a name="properties"></a>Propriedades

| Propriedade<br>**Nome físico**<br>**_Tipo_** | Uso | Descrição |
| --- | --- | --- |
| **ID do Funcionário**<br>mshr_fk_employee_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: mshr_Employee_id da entidade mshr_payrollemployeeentity  | ID do Funcionário |
| **Taxa de pagamento**<br>mshr_payrate<br>*Decimal* | Somente leitura<br>Obrigatório | A taxa de pagamento definida no plano de remuneração fixa. |
| **ID do Plano**<br>mshr_planid<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório |Especifica o plano da remuneração.  |
| **Válido a partir de**<br>mshr_validfrom<br>*Compensação de Data/Hora* |  Somente leitura<br>Obrigatório |Data a partir da qual a remuneração fixa do funcionário é válida.  |
| **Entidade Plano de remuneração fixa da folha de pagamento**<br>mshr_payrollfixedcompensationplanentityid<br>*GUID* | Obrigatório<br>Gerado pelo sistema | Um valor GUID gerado pelo sistema para identificar exclusivamente o plano de remuneração. |
| **Frequência de pagamento**<br>mshr_payfrequency<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório |A frequência com que o funcionário será pago.  |
| **Válida até**<br>mshr_validto<br>*Compensação de Data/Hora* | Somente leitura <br>Obrigatório | Data até a qual a remuneração fixa do funcionário é válida. |
| **ID da posição**<br>mshr_positionid<br>*Cadeia de caracteres* | Somente leitura <br>Obrigatório | ID da posição associada ao funcionário e ao registro do plano de remuneração fixa. |
| **Moeda**<br>mshr_currency<br>*Cadeia de caracteres* | Somente leitura <br>Obrigatório |A moeda definida para o plano de remuneração fixa   |
| **Número da equipe**<br>mshr_personnelnumber<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório |O número da equipe exclusiva do funcionário.  |

**Consulta**

**Solicitação**

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
