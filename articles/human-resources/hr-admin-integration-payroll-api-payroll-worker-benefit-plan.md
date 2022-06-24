---
title: Plano de benefícios do trabalhador em folha de pagamento
description: Este artigo fornece detalhes e um exemplo de consulta da entidade Plano de benefícios do trabalhador em folha de pagamento no Dynamics 365 Human Resources.
author: twheeloc
ms.date: 07/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ef45855d9e60131ac065ae6e2769b71ae3f69537
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902275"
---
# <a name="payroll-worker-benefit-plan"></a>Plano de benefícios do trabalhador em folha de pagamento


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo descreve a entidade Plano de benefícios do trabalhador em folha de pagamento para o Dynamics 365 Human Resources.

Nome físico: mshr_payrollworkerbenefitplanentities.

### <a name="description"></a>descrição

Esta entidade fornece informações sobre o plano de benefícios para um determinado trabalhador.

## <a name="properties"></a>Propriedades

| Propriedade</br>**Nome físico**</br>**_Tipo_** | Usar | descrição |
| --- | --- | --- |
| **Número da equipe**</br>mshr_personnelnumber</br>*Cadeia de caracteres* | Somente leitura</br>Obrigatório | O número da equipe exclusiva do funcionário. |
| **ID da entidade legal**</br>mshr_legalentityID</br>*Sequência de caracteres* | Somente leitura | Especifica a entidade legal (empresa). |
| **ID do Período**</br>mshr_periodid</br>*Sequência de caracteres* | Somente leitura | O identificador do período. |
| **ID do Plano**</br>mshr_planid</br>*Sequência de caracteres* | Somente leitura | O identificador do plano. |
| **Opção de cobertura**</br>mshr_coverageoptionid</br>*Sequência de caracteres* | Somente leitura | Identificação da opção de cobertura. |
| **Data de início da dedução**</br>mshr_deductionstartdatetime</br>*Compensação de data/hora* | Somente leitura | Data de início da dedução. |
| **Data de término da dedução**</br>mshr_deductionenddatetime</br>*Compensação de data/hora* | Somente leitura | Data de término da dedução. |
| **Status**</br>mshr_status</br>*[Conjunto de opções do Status do plano de benefícios dos funcionários](hr-admin-integration-payroll-api-benefit-employee-plan-status.md)* | Somente leitura | Status do plano de benefícios. |
| **Válido a partir de**</br>mshr_validfrom</br>*Compensação de Data/Hora* | Somente leitura | Hora a partir da qual o registro será válido. |
| **Válida até**</br>mshr_validto</br>*Compensação de Data/Hora* |  Somente leitura | A hora até a qual o registro é válido. |
| **ID do tipo de plano**</br>mshr_plantypeid</br>*Sequência de caracteres* | Somente leitura | O identificador do tipo de plano. |
| **Código do tipo de plano**</br>mshr_plantypecode</br>*[Conjunto de opções da cobertura do tipo de plano de benefícios](hr-admin-integration-payroll-api-benefit-plan-type-cover.md)* | Somente leitura | A especificação do tipo de plano. |
| **Número de períodos de pagamento**</br>mshr_payperiod</br>*Inteiro* | Somente leitura | O número de períodos de pagamento que representam a frequência com que os funcionários ou o fornecedor de benefícios são pagos. Esse valor será usado para calcular o valor do salário do benefício anual do funcionário. |
| **Valor do funcionário**</br>mshr_amountemployee</br>*Decimal* | Somente leitura | A percentagem ou valor do funcionário. |
| **Valor do empregador**</br>mshr_amountemployer</br>*Decimal* | Somente leitura | A percentagem ou valor do empregador. |
| **Campo principal**</br>mshr_primaryfield</br>*Sequência de caracteres* | Gerado pelo sistema | Campo principal. |
| **Valor da ID do trabalhador** </br>_mshr_fk_worker_id_value</br>*GUID* | Chave estrangeira: mshr_hcmworkerbaseentityid of mshr_hcmworkerbaseentity entity. | Um identificador exclusivo gerado pelo sistema para o trabalhador. |
| **Valor da ID do período**</br> _mshr_fk_period_id_value</br>*GUID* | Chave estrangeira: mshr_benefitperiodentityid of mshr_benefitperiodentity entity. | Um identificador exclusivo gerado pelo sistema para o período. |
| **Valor da ID do plano**</br> _mshr_fk_plan_id_value</br>*GUID* | Chave estrangeira: mshr_benefitplanentityid da entidade mshr_benefitplanentity. | Um identificador exclusivo gerado pelo plano. |
| **Valor da ID do Tipo de Plano**</br> _mshr_fk_plantype_id_value</br>*GUID* | Chave estrangeira: mshr_benefitplantypeentityid da entidade mshr_benefitplantypeentity. | Um identificador exclusivo gerado pelo plano. |
| **Valor da ID da opção de cobertura**</br> _mshr_fk_coverageoption_id_value</br>*GUID* | Chave estrangeira: mshr_benefitcoverageoptionentityid de entidade mshr_benefitcoverageoptionentity. | Um identificador exclusivo gerado pelo plano. |
| **Valor da ID da entidade do plano de benefícios do trabalhador da folha de pagamento**</br> mshr_payrollworkerbenefitplanentityid</br>*GUID* | Somente leitura </br> Gerado pelo sistema | Um identificador exclusivo gerado pelo sistema para o registro. |

## <a name="example-query-for-payroll-worker-benefit-plan"></a>Exemplo de consulta para o Plano de benefícios do trabalhador em folha de pagamento

**Solicitar**

```http
GET [Organization URI]/api/data/v9.1/mshr_payrollworkerbenefitplanentities?$filter=mshr_personnelnumber eq '000020'
```

**Resposta**

```json
{
    "mshr_personnelnumber": "000020",
    "mshr_legalentityid": "USMF",
    "mshr_periodid": "2021",
    "mshr_planid": "Dental plan",
    "mshr_coverageoptionid": "Emp Only",
    "mshr_deductionstartdatetime": "2021-01-01T06:00:00Z",
    "mshr_deductionenddatetime": "2021-12-31T06:00:00Z",
    "mshr_status": 200000001,
    "mshr_validfrom": "2021-01-01T06:00:00Z",
    "mshr_validto": "2021-12-31T06:00:00Z",
    "mshr_plantypeid": "Dental",
    "mshr_plantypecode": 200000001,
    "mshr_payperiod": 12,
    "mshr_amountemployee": 47,
    "mshr_amountemployer": 57,
    "mshr_primaryfield": "000020 | USMF | 2021 | Dental plan",
    "_mshr_fk_worker_id_value": "000000ae-0000-0000-bfff-004105000000",
    "_mshr_fk_period_id_value": "00000807-0000-0000-ee02-005001000000",
    "_mshr_fk_plan_id_value": "00000c61-0000-0000-0200-005001000000",
    "_mshr_fk_plantype_id_value": "0000057c-0000-0000-0200-005001000000",
    "_mshr_fk_coverageoption_id_value": "00000391-0000-0000-0b00-005001000000",
    "mshr_payrollworkerbenefitplanentityid": "000006c4-0000-0000-bfff-004105000000"
}
```
## <a name="see-also"></a>Consulte também

[Introdução à API de integração da folha de pagamento](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
