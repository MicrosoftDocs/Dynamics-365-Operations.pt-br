---
title: Plano de remuneração variável da folha de pagamento
description: Este tópico fornece detalhes e um exemplo de consulta da entidade Plano de remuneração variável da folha de pagamento no Dynamics 365 Human Resources.
author: marcelbf
ms.date: 06/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-15
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5dc096c08ed808f577c8cdc96ca84000a0b80679
ms.sourcegitcommit: 89bb2a7f402deed32998eddc1e56e75250e3d15e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314320"
---
# <a name="payroll-variable-compensation-plan"></a>Plano de remuneração variável da folha de pagamento

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve a entidade Plano de remuneração variável da folha de pagamento para o Dynamics 365 Human Resources.

### <a name="description"></a>descrição

Esta entidade fornece o plano de remuneração variável atribuído a um determinado cargo de um funcionário.

Nome físico: mshr_payrollvariablecompensationawardentity.

## <a name="properties"></a>Propriedades

| Propriedade</br>**Nome físico**</br>**_Tipo_** | Usar | descrição |
| --- | --- | --- |
| **Número da equipe**</br>mshr_personnelnumber</br>*Cadeia de caracteres* | Somente leitura</br>Obrigatório |O número da equipe exclusiva do funcionário.  |
| **Data do prêmio**</br>mshr_awarddate</br>*Compensação de Data/Hora* | Somente leitura</br>Obrigatório | Data do prêmio. |
| **Tipo de prêmio**</br>mshr_awardtype</br>*[conjunto de opções mshr_HrmCompVarAwardEmplType](hr-admin-integration-payroll-api-award-type.md)* | Somente leitura</br>Obrigatório | O tipo de prêmio definido para o plano de remuneração variável. |
| **Moeda**</br>mshr_unitcurrencycode</br>*Sequência de caracteres* | Somente leitura </br>Obrigatório |A moeda definida para o plano de remuneração variável.   |
| **ID do plano de remuneração fixa**</br>mshr_fixedplanid</br>*Sequência de caracteres* | Somente leitura | O plano de remuneração fixa que é usado como base para o cálculo do prêmio. |
| **Valor unitário**</br>mshr_awardamount</br>*Decimal* | Somente leitura | O valor da unidade |
| **Tipo de processo**</br>mshr_processtype</br>*[conjunto de opções mshr_hrmCompProcessType](hr-admin-integration-payroll-api-process-type.md)* | Somente leitura | O tipo de processo. |
| **Tipo de plano de remuneração variável**</br>Sequência de caracteres</br>*mshr_typeid* | Somente leitura | O tipo de plano de remuneração variável. |
| **ID de plano de remuneração variável**</br>Sequência de caracteres</br>*mshr_planid* | Somente leitura | O id do plano de remuneração variável. |
| **Campo principal**</br>mshr_primaryfield</br>*GUID* | Somente leitura</br>Gerado pelo sistema. | |
| **ID do Funcionário**</br>mshr_fk_employee_id_value</br>*GUID* | Somente leitura</br>Obrigatório</br>Chave estrangeira: mshr_Employee_id da entidade mshr_payrollemployeeentity  | ID do Funcionário. |
| **Entidade Plano de remuneração variável da folha de pagamento**</br>mshr_payrollvariablecompensationawardentityid</br>*GUID* | Obrigatório</br>Gerado pelo sistema | Um valor GUID gerado pelo sistema para identificar exclusivamente o plano de remuneração. |


## <a name="example-query"></a>Exemplo de consulta

**Solicitar**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollvariablecompensationawardentities?$filter=mshr_personnelnumber eq '000001'
```

**Resposta**

```json
{
    "mshr_personnelnumber": "000001",
    "mshr_awarddate": "2015-01-15T00:00:00Z",
    "mshr_awardtype": 200000000,
    "mshr_unitcurrencycode": "USD",
    "mshr_fixedplanid": "",
    "mshr_awardamount": 1,
    "mshr_processtype": 200000003,
    "mshr_typeid": "Bonus",
    "mshr_planid": "MgBonus",
    "mshr_primaryfield": "000001 | MgBonus | Bonus | 1/15/2015",
    "_mshr_fk_employee_id_value": "00000655-0000-0000-adff-004105000000",
    "mshr_payrollvariablecompensationawardentityid": "000001a1-0000-0000-adff-004105000000",
    "_mshr_fk_fixedcomp_id_value": null
}
```

## <a name="see-also"></a>Consulte também

[Introdução à API de integração da folha de pagamento](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
