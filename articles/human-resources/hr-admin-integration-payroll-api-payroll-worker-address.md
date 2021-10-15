---
title: Endereço do trabalhador da folha de pagamento
description: Este tópico fornece detalhes e um exemplo de consulta da entidade Endereço do trabalhador da folha de pagamento no Dynamics 365 Human Resources.
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
ms.openlocfilehash: bf3fc5f333333b9a832ecb9c185473e476ac231d
ms.sourcegitcommit: 12e26ef25c492e5032260733b50cd642cbd6164d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2021
ms.locfileid: "7559500"
---
# <a name="payroll-worker-address"></a>Endereço do trabalhador da folha de pagamento

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve a entidade Endereço do trabalhador da folha de pagamento para o Dynamics 365 Human Resources.

Nome físico: mshr_payrollworkeraddressentity.

### <a name="description"></a>descrição

Esta entidade fornece a localização da residência de folha de pagamento e a localização do trabalho da folha de pagamento de um determinado funcionário.

## <a name="properties"></a>Propriedades

| Propriedade</br>**Nome físico**</br>**_Tipo_** | Usar | Descrição |
| --- | --- | --- |
| **Número da equipe**</br>mshr_personnelnumber</br>*Sequência de caracteres* | Somente leitura | O número da equipe exclusiva do funcionário. |
| **ID da localização**</br>mshr_locationidbr>*Cadeia de caracteres* | Somente leitura | A ID do endereço. |
| **Endereço em que morou**</br>mshr_islivedinaddressbr </br> *[conjunto de opções mshr_NoYes](hr-admin-integration-payroll-api-no-yes.md)* | Somente leitura | Um valor que indica se o endereço é onde o funcionário reside. |
| **Endereço em que trabalhou** </br> mshr_isworkedinaddressbr </br>*[conjunto de opções mshr_NoYes](hr-admin-integration-payroll-api-no-yes.md)* | Somente leitura | Um valor que indica se o endereço é onde o funcionário trabalha. |
| **País/região**</br>mshr_countryregionid</br>*Sequência de caracteres* | Somente leitura</br>Obrigatório | O país ou região definido para o endereço. |
| **CEP**</br>mshr_zipcode<br>*Sequência de caracteres* | Somente leitura | O número de identificação definido para o funcionário. |
| **Rua**</br>mshr_street</br>*Sequência de caracteres* | Somente leitura | A rua definida para o endereço. |
| **Cidade**</br>mshr_city</br>*Sequência de caracteres* | Somente leitura | A cidade definida para o endereço. |
| **Estado**</br>mshr_state</br>*Sequência de caracteres* | Somente leitura | O estado ou província definido para o endereço. |
| **Região**</br>mshr_county</br>*Sequência de caracteres* | Somente leitura | A região definida para o endereço. |
| **Válido a partir de**</br>mshr_postaladdressvalidfrom</br>*Compensação de Data/Hora* | Somente leitura | A data a partir da qual o endereço é válido. |
| **Válida até**</br>mshr_postaladdressvalidto</br>*Compensação de Data/Hora* | Somente leitura | A data até a qual o endereço é válido. |
| **Campo principal**</br>mshr_primaryfield</br>*Sequência de caracteres* | Somente leitura | O campo principal. |
| **ID do endereço do trabalhador da folha de pagamento**</br>mshr_payrollworkeraddressentityid</br>*GUID* | Gerado pelo sistema | Um valor de GUID (identificador global exclusivo) gerado pelo sistema para identificar de forma exclusiva o endereço. |

## <a name="relations"></a>Relações

| Valor de propriedade | Entidade relacionada | Propriedade Navegação | Tipo de coleção |
| --- | --- | --- | --- |
| _mshr_fk_worker_id_value | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | mshr_FK_Worker_id | mshr_FK_PayrollEmployeeEntity_Address |

## <a name="example-query"></a>Exemplo de consulta

**Solicitação**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollworkeraddressentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_postaladdressvalidfrom le @asofdate and mshr_postaladdressvalidto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

**Resposta**

```json
{
    "mshr_personnelnumber": "000041",
    "mshr_locationid": "000000538",
    "mshr_islivedinaddress": 200000001,
    "mshr_isworkedinaddress": 200000000,
    "mshr_countryregionid": "USA",
    "mshr_zipcode": "99025",
    "mshr_street": "6543 Cypress Ave",
    "mshr_city": "Tacoma",
    "mshr_state": "WA",
    "mshr_county": "KING",
    "mshr_postaladdressvalidfrom": "2012-09-20T20:14:27Z",
    "mshr_postaladdressvalidto": "2154-12-31T23:59:59Z",
    "mshr_primaryfield": "000041 | 000000538 | 9/20/2012 08:14:27 pm",
    "_mshr_fk_worker_id_value": "00000d3c-0000-0000-d5ff-004105000000",
    "mshr_payrollworkeraddressentityid": "000006f0-0000-0000-f90f-014105000000"

}
```

## <a name="see-also"></a>Consulte também

[Introdução à API de integração da folha de pagamento](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
