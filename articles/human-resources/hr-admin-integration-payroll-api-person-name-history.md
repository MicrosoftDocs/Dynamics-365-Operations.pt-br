---
title: Histórico de nome da pessoa
description: Este artigo fornece detalhes e um exemplo de consulta da entidade Histórico de nomes da pessoa no Dynamics 365 Human Resources.
author: twheeloc
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e34b0d7bebd1c4037347161087ff3a4485a58878
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875761"
---
# <a name="person-name-history"></a>Histórico de nome da pessoa


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo descreve a entidade Histórico de nomes da pessoa no Dynamics 365 Human Resources.

Nome físico: mshr_dirpersonnamehistoricalentity.

### <a name="description"></a>Descrição

Esta entidade fornece informações sobre o histórico de nomes para uma determinada pessoa.

> [!IMPORTANT] 
> Os campos **FirstName**, **MiddleName**, **LastName**, **NameValidFrom** e **NameValidTo** não estão mais disponíveis na entidade Funcionária da folha de pagamento. Eles foram removidos para garantir que somente uma fonte de dados de data efetiva que apoie essa entidade.

## <a name="properties"></a>Propriedades

| Propriedade</br>**Nome físico**</br>**_Tipo_** | Usar | Descrição |
| --- | --- | --- |
| **Nome**</br>mshr_firstname</br>*Sequência de caracteres* | Somente leitura | O nome. |
| **Prefixo do sobrenome**</br>mshr_lastnameprefix</br>*Cadeia de caracteres*) | Somente leitura | O prefixo do sobrenome. |
| **Sobrenome**</br>mshr_lastname</br>*Cadeia de caracteres*) | Somente leitura | O sobrenome. |
| **Nome do meio**</br>mshr_middlename</br>*Cadeia de caracteres*) | Somente leitura | O nome do meio. |
| **Válida até**</br>mshr_validto</br>*Cadeia de caracteres*) | Somente leitura | A data até a qual o nome é válido. |
| **Número do participante**</br>mshr_partynumber</br>*Sequência de caracteres* | Somente leitura | Um identificador único gerado pelo sistema, legível pelo usuário, para a pessoa. |
| **Campo principal**</br>mshr_primaryfield</br>*Sequência de caracteres* | Somente leitura | O identificador exclusivo do registro. |
| **ID da entidade do Histórico de nomes da pessoa**</br>mshr_dirpersonnamehistoricalentityid</br>*GUID* | Gerado pelo sistema | Um valor de GUID (identificador global exclusivo) gerado pelo sistema para identificar de forma exclusiva o registro. |

## <a name="relations"></a>Relações

| Valor de propriedade | Entidade relacionada | Propriedade Navegação | Tipo de coleção |
| --- | --- | --- | --- |
| Não aplicável | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | Não aplicável | mshr_FK_PayrollEmployeeEntity_Name |

## <a name="example-query-for-payroll-employee"></a>Exemplo de consulta para funcionário da folha de pagamento

**Solicitação**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_dirpersonnamehistoricalentities?$filter=mshr_partynumber eq 'HR000001606'
```

**Resposta**

```json
{
    "mshr_firstname": "Agustina",
    "mshr_lastnameprefix": "",
    "mshr_lastname": "Fierro",
    "mshr_middlename": "middle",
    "mshr_validto": "2021-09-10T21:23:53Z",
    "mshr_partynumber": "HR000001606",
    "mshr_primaryfield": "HR000001606 | ",
    "mshr_dirpersonnamehistoricalentityid": "00000832-0000-0000-c12b-014105000000",
    "mshr_validfrom": null
},
{
    "mshr_firstname": "Agustina",
    "mshr_lastnameprefix": "",
    "mshr_lastname": "Fierro",
    "mshr_middlename": "",
    "mshr_validto": "2154-12-31T23:59:59Z",
    "mshr_partynumber": "HR000001606",
    "mshr_primaryfield": "HR000001606 | 9/10/2021 09:23:54 pm",
    "mshr_dirpersonnamehistoricalentityid": "00000832-0000-0000-d20b-000010000000",
    "mshr_validfrom": "2021-09-10T21:23:54Z"
}
```

## <a name="see-also"></a>Consulte também

[Introdução à API de integração da folha de pagamento](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
