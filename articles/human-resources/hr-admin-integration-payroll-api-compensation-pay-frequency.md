---
title: Frequência de pagamento de remuneração
description: Este tópico fornece detalhes e um exemplo de consulta da entidade Frequência de pagamento de remuneração no Dynamics 365 Human Resources.
author: marcelbf
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b864d0db8ff1b380749b6099fa74a40045932b67
ms.sourcegitcommit: 12e26ef25c492e5032260733b50cd642cbd6164d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2021
ms.locfileid: "7559626"
---
# <a name="compensation-pay-frequency"></a>Frequência de pagamento de remuneração

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve a entidade Frequência de pagamento de remuneração no Dynamics 365 Human Resources.

Nome físico: mshr_hcmpayrateconversionentity.

### <a name="description"></a>Descrição

Esta entidade fornece informações sobre a conversão da taxa de pagamento para determinada frequência de pagamento de remuneração.

## <a name="properties"></a>Propriedades

| Propriedade</br>**Nome físico**</br>**_Tipo_** | Usar | Descrição |
| --- | --- | --- |
| **Conversão anual da taxa de pagamento**</br>mshr_annualconversionfactor</br>*Decimal* | Somente leitura | O fator de conversão anual para a frequência de pagamento. |
| **Descrição**</br>mshr_description</br>*Sequência de caracteres* | Somente leitura | A descrição da taxa de conversão. |
| **Conversão por hora da taxa de pagamento**</br>mshr_hourlyconversionfactor</br>*Decimal* | Somente leitura | O fator de conversão por hora para a frequência de pagamento. |
| **Conversão mensal da taxa de pagamento**</br>mshr_monthlyconversionfactor</br>*Decimal* | Somente leitura | O fator de conversão mensal para a frequência de pagamento. |
| **Conversão da taxa de pagamento**</br>mshr_payrateconversion</br>*Sequência de caracteres* | Somente leitura | Uma cadeia de caracteres exclusiva para identificar a taxa de conversão. |
| **Período**</br>mshr_period</br>*Opção de período definida* | Somente leitura | O período principal da conversão de determinada taxa de pagamento. |
| **Conversão semanal da taxa de pagamento**</br>mshr_weeklyconversionfactor</br>*Decimal* | Somente leitura | O fator de conversão semanal para a frequência de pagamento. |
| **ID da área de dados**</br>mshr_dataareaid</br>*Sequência de caracteres* | Somente leitura | A entidade legal (empresa). |
| **ID da entidade de frequência de pagamento de remuneração**</br>mshr_dirpersonnamehistoricalentityid</br>*GUID* | Gerado pelo sistema | Um valor de GUID (identificador global exclusivo) gerado pelo sistema para identificar de forma exclusiva o registro. |

## <a name="example-query-for-payroll-employee"></a>Exemplo de consulta para funcionário da folha de pagamento

**Solicitação**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_hcmpayrateconversionentities?$filter=mshr_payrateconversion eq 'Annual' and mshr_dataareaid eq 'usmf'
```

**Resposta**

```json
{
    "mshr_annualconversionfactor": 1,
    "mshr_description": "Annual",
    "mshr_hourlyconversionfactor": 0.0004807692,
    "mshr_monthlyconversionfactor": 0.0833333333,
    "mshr_payrateconversion": "Annual",
    "mshr_period": 200000000,
    "mshr_weeklyconversionfactor": 0.0192307692,
    "mshr_dataareaid": "usmf",
    "mshr_hcmpayrateconversionentityid": "0000056e-0000-0000-b027-fef003000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Consulte também

[Introdução à API de integração da folha de pagamento](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
