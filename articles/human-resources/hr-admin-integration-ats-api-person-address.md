---
title: Endereço da pessoa
description: Este tópico descreve a entidade Endereço da pessoa para o Dynamics 365 Human Resources.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0bca48c9e980f95e4dd72a075b34824331ae05dc
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466535"
---
# <a name="person-address"></a>Endereço da pessoa

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve a entidade Endereço da pessoa para o Dynamics 365 Human Resources.

Nome físico: mshr_hcmpersonaddressentities

## <a name="description"></a>Descrição

Esta entidade contém a lista de endereços postais para registros de candidatos.

## <a name="json-representation"></a>Representação JSON

```json
{
    "mshr_partynumber": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_roles": "String",
    "mshr_countryregionid": "String",
    "mshr_zipcode": "String",
    "mshr_street": "String",
    "mshr_city": "String",
    "mshr_state": "String",
    "mshr_county": "String",
    "mshr_isprimary": Int,
    "mshr_isprivate": Int,
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_countryregion_id_value": "Guid",
    "mshr_hcmpersonaddressentityid": "Guid"
}
```

## <a name="properties"></a>Propriedades

| Propriedade<br>**Nome físico**<br>**_Tipo_** | Uso | Descrição |
| --- | --- | --- |
| **ID da entidade de endereço da pessoa**<br>mshr_hcmpersonaddressentityid<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório | Um identificador exclusivo gerado pelo sistema para o registro de entidade. |
| **Número do participante**<br>mshr_partynumber<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | A ID do registro de participante (pessoa) associado. |
| **Valor da ID da pessoa**<br>_mshr_fk_person_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: mshr_dirpersonentityid de mshr_dirpersonentity | O identificador gerado pelo sistema do registro da entidade de participante (pessoa). |
| **ID da localização**<br>mshr_locationid<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | A ID de localização do registro do endereço. Configure na entidade mshr_logisticspostaladdresslocationcdsentity. |
| **Descrição**<br>mshr_description<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | Uma descrição do endereço do candidato. |
| **Funções**<br>mshr_roles<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | As funções atribuídas a este endereço. Pode-se atribuir mais de uma função. Cada função deve ser separada por um ponto e vírgula. Os valores válidos contidos na entidade mshr_logisticslocationroleentity. |
| **Rua**<br>mshr_street<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O número da rua. |
| **Cidade**<br>mshr_city<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A cidade do endereço. Configurado na entidade mshr_logisticsaddresscityentity. |
| **Estadual**<br>mshr_state<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O estado do endereço. Configurado na entidade mshr_logisticsaddressstateentity. |
| **Município**<br>mshr_county<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A região do endereço. Configurado na entidade mshr_logisticsaddresscountyentity. |
| **CEP**<br>mshr_zipcode<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O CEP/código postal do endereço. Configurado na entidade mshr_logisticsaddresspostalcodeentity. |
| **ID de país/região**<br>mshr_countryregionid<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O país ou região do endereço |
| **ID de valor de país/região**<br>_mshr_fk_countriregion_id_value<br>*GUID* | Somente leitura<br>Opcional<br>Chave estrangeira: mshr_logisticaddresscountryregionentityid de mshr_logisticsaddresscountryregionentity | O identificador exclusivo gerado pelo sistema do país/região do endereço. |
| **É Principal**<br>mshr_isprimary<br>*conjunto de opções mshr_noyes* | Ler/gravar<br>Obrigatório | Identifica se este endereço é o endereço principal da pessoa da função definida. |
| **É particular**<br>mshr_isprivate<br>*conjunto de opções mshr_noyes* | Ler/gravar<br>Obrigatório | Identifica se este endereço é um endereço particular da pessoa. |
| **Campo principal**<br>mshr_primaryfield<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório | Campo usado como identificador principal do registro de entidade. Combinação de número de participante e ID de local. |

## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Exemplo de consulta de candidato a ser contratado](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]