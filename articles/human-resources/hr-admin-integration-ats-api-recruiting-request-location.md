---
title: Localização da solicitação de recrutamento
description: Este artigo descreve a entidade Localização da solicitação de recrutamento para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: d31af9ab62db310b89fbc7a2d7099621b59a356d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893806"
---
# <a name="recruiting-request-location"></a>Localização da solicitação de recrutamento


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo descreve a entidade Localização da solicitação de recrutamento para o Dynamics 365 Human Resources.

Nome físico: mshr_hcmrecruitingrequestlocationentity

### <a name="description"></a>Descrição

A lista de locais definida como locais em que os funcionários recrutados trabalharão na contratação. Estes são locais criados entre as entidades legais.

### <a name="json-representation"></a>Representação JSON

```
{
    "mshr_recruitingrequestlocationid": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_countryregionid": "String",
    "mshr_zipcode": "String",
    "mshr_street": "String",
    "mshr_city": "String",
    "mshr_state": "String",
    "mshr_county": "String",
    "mshr_telephone": "String",
    "mshr_email": "String",
    "mshr_internetaddress": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_dataareaid": "String",
    "_mshr_fk_countryregion_id_value": "Guid",
    "mshr_hcmrecruitingrequestlocationentityid": "Guid"
}
```

### <a name="properties"></a>Propriedades

| Propriedade<br>**Nome físico**<br>**_Tipo_** | Usar | Descrição |
| --- | --- | --- |
| **ID da localização**<br>mshr_locationid<br>*Cadeia de caracteres* | Gravação única<br>Obrigatório | O identificador gerado pelo sistema, legível pelo usuário, para o local de recrutamento. |
| **Local da solicitação de recrutamento**<br>mshr_recruitingrequestlocationid<br>*Cadeia de caracteres* | Gravação única<br>Obrigatório | Identificador exclusivo definido pelo usuário para o local de recrutamento. |
| **ID de entidade de local de solicitação de recrutamento**<br>mshr_hcmrecruitingrequestlocationentityid<br>*GUID* | Somente leitura<br>Obrigatório | Identificador exclusivo gerado pelo sistema para o registro de local da solicitação de recrutamento. |
| **Descrição**<br>mshr_description<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | Descrição da localização. |
| **ID de país/região**<br>mshr_countryregionid<br>*Cadeia de caracteres* | Somente leitura<br>Opcional | Especifica o país ou a região em que o candidato tem cidadania. |
| **ID de valor de país/região**<br>_mshr_fk_countriregion_id_value<br>*GUID* | Somente leitura<br>Opcional<br>Chave estrangeira: mshr_logisticaddresscountryregionentityid de mshr_logisticsaddresscountryregionentity | O identificador exclusivo gerado pelo sistema do país/região do endereço. |
| **ZipCode**<br>mshr_zipcode<br>*Cadeia de caracteres* | Somente leitura<br>Opcional | CEP/código postal. |
| **Rua**<br>mshr_street<br>*Cadeia de caracteres* | Somente leitura<br>Opcional | Endereço. |
| **Cidade**<br>mshr_city<br>*Cadeia de caracteres* | Somente leitura<br>Opcional | Cidade. |
| **Estado**<br>mshr_state<br>*Cadeia de caracteres* | Somente leitura<br>Opcional | Estado ou província. |
| **Município**<br>mshr_county<br>*Cadeia de caracteres* | Somente leitura<br>Opcional | Município. |
| **Telefone**<br>mshr_telephone<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Número de telefone do local. |
| **Email**<br>mshr_email<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Endereço de email. |
| **Endereço na Internet**<br>mshr_internetaddress<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | URL do site do local. |
| **ID da área de dados**<br>mshr_dataareaid<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Especifica a entidade legal (empresa). |
| **Valor da ID da área de dados**<br>_mshr_dataareaid_id_value<br>*GUID* | Somente leitura<br>Opcional<br>Chave estrangeira: cdm_companyid da entidade cdm_company | Valor GUID gerado pelo sistema identificando a entidade legal (empresa). |

## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de exemplo de solicitação de recrutamento](hr-admin-integration-ats-api-recruiting-request-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
