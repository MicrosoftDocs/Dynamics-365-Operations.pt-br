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
ms.openlocfilehash: 898ca7b33e39ec33990fecc4c3a7229620fbfddd5ce8ad14423af38047187e55
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6761965"
---
# <a name="payroll-worker-address"></a>Endereço do trabalhador da folha de pagamento

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve a entidade Endereço do trabalhador da folha de pagamento para o Dynamics 365 Human Resources.

Nome físico: mshr_payrollworkeraddressentity.

### <a name="description"></a>descrição

Esta entidade fornece a localização da residência de folha de pagamento e a localização do trabalho da folha de pagamento de um determinado funcionário.

## <a name="properties"></a>Propriedades

| Propriedade</br>**Nome físico**</br>**_Tipo_** | Usar | descrição |
| --- | --- | --- |
| **Cidade**</br>mshr_city</br>*Sequência de caracteres* | Somente leitura</br>Obrigatório | A cidade definida para o endereço.   |
| **Número da equipe**</br>mshr_personnelnumber</br>*Cadeia de caracteres* | Somente leitura</br>Obrigatório | O número da equipe exclusiva do funcionário.  |
| **País/região**</br>mshr_countryregionid</br>*Cadeia de caracteres* | Somente leitura</br>Obrigatório | O país ou região definida para o endereço.  |
| **Válido a partir de**</br>mshr_postaladdressvalidfrom</br>*Compensação de Data/Hora* | Somente leitura </br>Obrigatório | Data a partir da qual o endereço é válido. |
| **Endereço em que trabalhou** </br> mshr_isworkedinaddressbr </br>*[conjunto de opções mshr_NoYes](hr-admin-integration-payroll-api-no-yes.md)* | Somente leitura</br>Obrigatório | Indica se o endereço é onde o funcionário trabalha. |
| **Município**</br>mshr_county</br>*Sequência de caracteres* | Somente leitura</br>Obrigatório | O município definido para o endereço.  |
| **ID do endereço do trabalhador da folha de pagamento**</br>mshr_payrollworkeraddressentityid</br>*GUID* | Obrigatório</br>Gerado pelo sistema | Um valor GUID gerado pelo sistema para identificar exclusivamente o endereço.  |
| **Campo principal**</br>mshr_primaryfield</br>*Sequência de caracteres* | Somente leitura</br>Obrigatório |  |
| **Rua**</br>mshr_street</br>*Sequência de caracteres* | Somente leitura</br>Obrigatório | A rua definida para o endereço. |
| **Válida até**</br>mshr_postaladdressvalidto</br>*Compensação de Data/Hora* | Somente leitura </br>Obrigatório | Data até a qual o endereço é válido.  |
| **ID da localização**</br>mshr_locationidbr>*Cadeia de caracteres* | Somente leitura <br>Obrigatório | A ID do endereço.  |
| **CEP**</br>mshr_zipcode<br>*Sequência de caracteres* | Somente leitura <br>Obrigatório |O número de identificação definido para o funcionário.  |
| **Endereço em que morou**</br>mshr_islivedinaddressbr </br> *[conjunto de opções mshr_NoYes](hr-admin-integration-payroll-api-no-yes.md)* | Somente leitura</br>Obrigatório | Indica se o endereço é onde o funcionário mora. |
| **Estado**</br>mshr_state</br>*Sequência de caracteres* | Somente leitura</br>Obrigatório | O estado definido para o endereço.  |

## <a name="example-query"></a>Exemplo de consulta

**Solicitar**

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
