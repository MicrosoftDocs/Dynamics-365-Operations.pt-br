---
title: Funcionário da folha de pagamento
description: Este artigo fornece detalhes e um exemplo de consulta da entidade Funcionário da folha de pagamento no Dynamics 365 Human Resources.
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
ms.openlocfilehash: b07fbc76b997600b2c076c00a63d1f6d865326d0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872200"
---
# <a name="payroll-employee"></a>Funcionário da folha de pagamento


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo descreve a entidade Funcionário da folha de pagamento para o Dynamics 365 Human Resources.

Nome físico: mshr_payrollemployeeentity.

### <a name="description"></a>descrição

Esta entidade fornece informações sobre o funcionário. Você deve definir os [parâmetros de integração de folha de pagamento](hr-admin-integration-payroll-api-parameters.md) antes de usar esta entidade.

>[!IMPORTANT] 
>Os campos **FirstName**, **MiddleName**, **LastName**, **NameValidFrom** e **NameValidTo** não estão mais disponíveis nesta entidade. Isso garante que exista apenas uma fonte de dados de data efetiva que apoie a essa entidade.
>Estes campos estarão disponíveis na entidade **DirPersonNameHistoricalEntity**, que foi liberada na atualização 43 da plataforma. Há um relacionamento OData de **PayrollEmployeeEntity** para **DirPersonNameHistoricalEntity**. 

## <a name="properties"></a>Propriedades

| Propriedade</br>**Nome físico**</br>**_Tipo_** | Usar | descrição |
| --- | --- | --- |
| **ID da entidade legal**</br>mshr_legalentityid</br>*Sequência de caracteres* | Somente leitura | Especifica a entidade legal (empresa). |
| **Número da equipe**</br>mshr_personnelnumber</br>*Sequência de caracteres* | Somente leitura | O número da equipe exclusiva do funcionário. |
| **Data de início do emprego**</br>mshr_employmentstartdate</br>*Compensação de data/hora* | Somente leitura | A data de início do emprego do funcionário. |
| **Data final do emprego**</br>mshr_employmentenddate</br>*Compensação de data/hora* | Somente leitura |O final do emprego do funcionário.  |
| **Data de aniversário**</br>mshr_birthdate</br>*Compensação de Data/Hora* | Somente leitura | A data de nascimento do funcionário. |
| **Sexo**</br>mshr_gender</br>[conjunto de opções mshr_hcmpersongender](hr-admin-integration-payroll-api-gender.md) | Somente leitura | O sexo do funcionário. |
| **Tipo de emprego**</br>mshr_employmenttype</br>[conjunto de opções mshr_hcmemploymenttype](hr-admin-integration-payroll-api-hcmemploymenttype.md) | Somente leitura | O tipo de emprego. |
| **ID de tipo de identificação**</br>mshr_identificationtypeid</br>*Sequência de caracteres* |Somente leitura | O tipo de identificação definido para o funcionário. |
| **Número de identificação de**</br>mshr_identificationnumber</br>*Sequência de caracteres* | Somente leitura |O número de identificação definido para o funcionário. |
| **Pronto para Pagar**</br>mshr_readytopay</br>[conjunto de opções mshr_noyes](hr-admin-integration-payroll-api-no-yes.md) | Somente leitura | Indica se o funcionário está marcado como pronto para pagar. |
| **ID da entidade do funcionário da folha de pagamento**</br>mshr_payrollemployeeentityid</br>*GUID* | Gerado pelo sistema | Um valor de GUID (identificador global exclusivo) gerado pelo sistema para identificar de forma exclusiva o funcionário. |

## <a name="relations"></a>Relações

|Valor de propriedade | Entidade relacionada | Propriedade Navegação | Tipo de coleção |
| --- | --- | --- | --- |
| _mshr_fk_employment_id_value | mshr_hcmemploymentdetailentity | mshr_FK_Employment_id | mshr_FK_HcmEmploymentDetailEntity_PayrollEmployee |
| _mshr_fk_fixedcompplan_id_value | [mshr_payrollfixedcompensationplanentity](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md) | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_Employee |
| _mshr_fk_name_id_value | mshr_dirpersonnamehistoricalentity | mshr_FK_Name_id | - |
| _mshr_fk_worker_id_value | mshr_hcmworkerbaseentity | mshr_FK_Worker_id | mshr_FK_HcmWorkerBaseEntity_PayrollEmployee |
| _mshr_fk_workerbankaccount_id_value | mshr_hcmworkerbankaccountentity | mshr_FK_WorkerBankAccount_id | mshr_FK_HcmWorkerBankAccountEntity_PayrollEmployee |
| _mshr_fk_variablecompaward_id_value | [mshr_payrollvariablecompensationawardentity](hr-admin-integration-payroll-api-payroll-variable-compensation-plan.md) | mshr_FK_VariableCompAward_id | mshr_FK_PayrollVariableCompensationAwardEntity_Employee |
| _mshr_fk_address_id_value | [mshr_payrollworkeraddressentity](hr-admin-integration-payroll-api-payroll-worker-address.md) | mshr_FK_Address_id | mshr_FK_PayrollWorkerAddressEntity_Worker |

## <a name="example-query-for-payroll-employee"></a>Exemplo de consulta para funcionário da folha de pagamento

**Solicitar**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollemployeeentities?$filter=mshr_personnelnumber eq '000041'
```

**Resposta**

```json
{
    "mshr_legalentityid": "USMF",
    "mshr_personnelnumber": "000041",
    "mshr_employmentstartdate": "2011-04-05T07:00:00Z",
    "mshr_employmentenddate": "2154-12-31T23:59:59Z",
    "mshr_birthdate": "1987-09-12T00:00:00Z",
    "mshr_gender": 200000002,
    "mshr_employmenttype": 200000000,
    "mshr_identificationtypeid": "SSN",
    "mshr_identificationnumber": "888-99-9342",
    "mshr_readytopay": 200000000,
    "mshr_dataareaid": "USMF",
    "mshr_primaryfield": "000041 | USMF | 4/5/2011 07:00:00 am",
    "_mshr_fk_employment_id_value": "00000d4e-0000-0000-0600-014105000000",
    "_mshr_fk_fixedcompplan_id_value": "00000598-0000-0000-4cd0-fda002000000",
    "_mshr_fk_name_id_value": "00000832-0000-0000-d700-014105000000",
    "_mshr_fk_worker_id_value": "000000af-0000-0000-d5ff-004105000000",
    "_mshr_fk_workerbankaccount_id_value": "000006f2-0000-0000-b7ff-004105000000",
    "mshr_payrollemployeeentityid": "00000666-0000-0000-d5ff-004105000000",
    "_mshr_fk_address_id_value": null,
    "_mshr_fk_variablecompaward_id_value": null,
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Consulte também

[Introdução à API de integração da folha de pagamento](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
