---
title: Funcionário da folha de pagamento
description: Este tópico fornece detalhes e um exemplo de consulta da entidade Funcionário da folha de pagamento no Dynamics 365 Human Resources.
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
ms.openlocfilehash: 20e74e97f98d0bc0fd454d54cbf969d4f1b46c7c98b2949b0ed8cfe671312dd2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768182"
---
# <a name="payroll-employee"></a>Funcionário da folha de pagamento

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve a entidade Funcionário da folha de pagamento para o Dynamics 365 Human Resources.

Nome físico: mshr_payrollemployeeentity.

### <a name="description"></a>descrição

Esta entidade fornece informações sobre o funcionário. Você deve definir os [parâmetros de integração de folha de pagamento](hr-admin-integration-payroll-api-parameters.md) antes de usar esta entidade.

>[!IMPORTANT] 
>Os campos **FirstName**, **MiddleName**, **LastName**, **NameValidFrom** e **NameValidTo** não estão mais disponíveis nesta entidade. Isso garante que exista apenas uma fonte de dados de data efetiva que apoie a essa entidade.
>Estes campos estarão disponíveis na entidade **DirPersonNameHistoricalEntity**, que foi liberada na atualização 43 da plataforma. Há um relacionamento OData de **PayrollEmployeeEntity** para **DirPersonNameHistoricalEntity** no campo **Pessoa**. 

## <a name="properties"></a>Propriedades

| Propriedade<br>**Nome físico**<br>**_Tipo_** | Usar | descrição |
| --- | --- | --- |
| **Número da equipe**<br>mshr_personnelnumber<br>*Sequência de caracteres* | Somente leitura | O número da equipe exclusiva do funcionário. |
| **Campo principal**<br>mshr_primaryfield<br>*Sequência de caracteres* | Somente leitura<br>Gerado pelo sistema |  |
| **ID da entidade legal**<br>mshr_legalentityID<br>*Sequência de caracteres* | Somente leitura | Especifica a entidade legal (empresa). |
| **Sexo**<br>mshr_gender<br>[conjunto de opções mshr_hcmpersongender](hr-admin-integration-payroll-api-gender.md) | Somente leitura | O sexo do funcionário. |
| **ID da entidade do funcionário da folha de pagamento**<br>mshr_payrollemployeeentityid<br>*GUID* | Obrigatório<br>Gerado pelo sistema | Um valor GUID gerado pelo sistema para identificar exclusivamente o funcionário. |
| **Data de início do emprego**<br>mshr_employmentstartdate<br>*Compensação de data/hora* | Somente leitura | A data de início do emprego do funcionário. |
| **ID de tipo de identificação**<br>mshr_identificationtypeid<br>*Sequência de caracteres* |Somente leitura | O tipo de identificação definido para o funcionário. |
| **Data final do emprego**<br>mshr_employmentenddate<br>*Compensação de data/hora* | Somente leitura |O final do emprego do funcionário.  |
| **ID da área de dados**<br>mshr_dataareaid_id<br>*GUID* | Somente leitura <br>Gerado pelo sistema | Valor GUID gerado pelo sistema identificando a entidade legal (empresa). |
| **Válida até**<br>mshr_namevalidto<br>*Compensação de Data/Hora* |  Somente leitura | Data até a qual as informações do funcionário são válidas. |
| **Data de aniversário**<br>mshr_birthdate<br>*Compensação de Data/Hora* | Somente leitura | A data de nascimento do funcionário |
| **Número de identificação de**<br>mshr_identificationnumber<br>*Sequência de caracteres* | Somente leitura |O número de identificação definido para o funcionário.  |

## <a name="example-query-for-payroll-employee"></a>Exemplo de consulta para funcionário da folha de pagamento

**Solicitar**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollemployeeentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_identificationtypeid eq @idtype and mshr_namevalidfrom le @asofdate and mshr_namevalidto ge @asofdate&@personnelnumber='000041'&@idtype='SSN'&@asofdate=2021-04-01
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
    "mshr_identificationtypeid": "SSN",
    "mshr_identificationnumber": "888-99-9342",
    "mshr_dataareaid": "USMF",
    "mshr_primaryfield": "000041 | USMF | 4/5/2011 07:00:00 am",
    "_mshr_fk_worker_id_value": "000000ad-0000-0000-d5ff-004105000000",
    "_mshr_fk_employment_id_value": "00000d0d-0000-0000-0600-014105000000",
    "_mshr_fk_fixedcompplan_id_value": "0000029f-0000-0000-d5ff-004105000000",
    "mshr_payrollemployeeentityid": "00000d3c-0000-0000-d5ff-004105000000",
    "_mshr_dataareaid_id_value": null
}
```
## <a name="see-also"></a>Consulte também

[Introdução à API de integração da folha de pagamento](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
