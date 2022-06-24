---
title: Número de identificação da pessoa
description: Este artigo descreve a entidade Número de identificação da pessoa para o Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2d3641ffede29b7fda904ffb6cd70cb33d7800d4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858262"
---
# <a name="person-identification-number"></a>Número de identificação da pessoa


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo descreve a entidade Número de identificação da pessoa para o Dynamics 365 Human Resources.

Nome físico: mshr_hcmpersonidentificationnumberentity

## <a name="description"></a>Descrição

Esta entidade descreve os números de identificação para o candidato. Ele permite que o consumidor da API escreva números de identificação, como números de CPF ou números de passaporte, para o registro de candidatos. Os números de identificação são exibidos no registro de trabalho, mas não no registro de candidatos. Um aplicativo de integração pode gravar os valores no banco de dados do Human Resources, mas os números não ficarão visíveis no Human Resources até que o registro de trabalhador do candidato seja criado.

## <a name="json-representation"></a>Representação JSON

```json
{
    "mshr_entrytype": "String",
    "mshr_description": "String",
    "mshr_expirationdate": "Datetime",
    "mshr_isprimary": Int,
    "mshr_identificationnumber": "String",
    "mshr_partynumber": "String",
    "mshr_identificationtypeid": "String",
    "mshr_issuingagencyid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_issuingagency_id_value": "Guid",
    "_mshr_fk_identificationtype_id_value": "Guid",
    "mshr_hcmpersonidentificationnumberentityid": "Guid",
    "mshr_issueddate": "Datetime"
}
```

## <a name="properties"></a>Propriedades

| Propriedade<br>**Nome físico**<br>**_Tipo_** | Uso | Descrição |
| --- | --- | --- |
| **ID de entidade do número de identificação da pessoa**<br>mshr_hcmpersonidentificationnumberentityid<br>*GUID* | Somente leitura<br>Obrigatório<br>Gerado pelo sistema | Identificador principal exclusivo do registro de número de identificação da pessoa. |
| **Tipo de entrada**<br>mshr_entrytype<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Valor livre para fazer referência ao tipo de entrada do número de identificação. |
| **Descrição**<br>mshr_description<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A descrição do número de identificação. |
| **Data de Vencimento**<br>mshr_expirationdate<br>*Datetime* | Ler/gravar<br>Opcional | A data na qual o número de identificação ou o documento associado expira. |
| **É Principal**<br>mshr_isprimary<br>*conjunto de opções mshr_noyes* | Ler/gravar<br>Opcional | Define se o número de identificação é o registro principal da pessoa para esse tipo de identificação. |
| **Número de Identificação**<br>mshr_identificationnumber<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | O número de identificação. |
| **Número do participante**<br>mshr_partynumber<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | O identificador do participante (pessoa) proprietário do número de identificação. |
| **Valor da ID da pessoa**<br>_mshr_fk_person_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: entidade mshr_dirpersonentityid de mshr_dirpersonentity | O identificador exclusivo do participante (pessoa). |
| **ID de tipo de identificação**<br>mshr_identificationtypeid<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | O tipo de número de identificação. |
| **Valor da ID de tipo de identificação**<br>_mshr_fk_identificationtype_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: entidade mshr_hcmidentificationtypeentityid de mshr_hcmidentificationtypeentity | Identificador exclusivo gerado pelo sistema do tipo de identificação. |
| **ID da agência emissora**<br>mshr_issuingagencyid<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A agência ou a organização que emite o número de identificação. |
| **Valor da ID da agência emissora**<br>_mshr_fk_issuingagency_id_value<br>*GUID* | Somente leitura<br>Opcional<br>Chave estrangeira: entidade mshr_hcmissuingagencyentityid de mshr_hcmissuingagencyentity | Identificador exclusivo gerado pelo sistema da agência que emite o número de identificação. |
| **Campo principal**<br>mshr_primaryfield<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório | Campo a ser usado como identificador do registro de entidade. Combinação de número de participante, ID de tipo de identificação e número de identificação. |
| **Data da emissão**<br>mshr_issuedate<br>*Data* | Ler/gravar<br>Opcional | A data em que o número de identificação foi emitido. |

## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Exemplo de consulta de candidato a ser contratado](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
