---
title: Contato do participante
description: Este tópico descreve a entidade Contato do participante para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: f5a942ef93af4348404c74d8b15d98ae6fa796ff
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466726"
---
# <a name="party-contact"></a>Contato do participante

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve a entidade Contato do participante para o Dynamics 365 Human Resources.

Nome físico: mshr_dirpartycontactentities

## <a name="description"></a>Descrição

Esta entidade descreve as informações de contato do candidato, incluindo o telefone, o email e as contas de mídia social.

## <a name="json-representation"></a>Representação JSON

```json
{
    "mshr_partynumber": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_type": Int,
    "mshr_countryregioncode": "String",
    "mshr_locator": "String",
    "mshr_locatorextension": "String",
    "mshr_purpose": "String",
    "mshr_ismobilephone": Int,
    "mshr_isinstantmessage": Int,
    "mshr_isprimary": Int,
    "mshr_isprivate": Int,
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "String",
    "mshr_dirpartycontactentityid": "String"
}
```

## <a name="properties"></a>Propriedades

| Propriedade<br>**Nome físico**<br>**_Tipo_** | Usar | Descrição |
| --- | --- | --- |
| **ID da entidade de contato do participante**<br>mshr_dirpartycontactentityid<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório | Um identificador exclusivo gerado pelo sistema para o registro de entidade. |
| **Número do participante**<br>mshr_partynumber<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | A ID do registro de participante (pessoa) associado. |
| **Valor da ID da pessoa**<br>_mshr_fk_person_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: mshr_dirpersonentityid de mshr_dirpersonentity | O identificador gerado pelo sistema do registro da entidade de participante (pessoa). |
| **ID da localização**<br>mshr_locationid<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | A ID de localização do registro do endereço. Configure na entidade mshr_logisticspostaladdresslocationcdsentity. |
| **Descrição**<br>mshr_description<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | A descrição dos detalhes do contato. |
| **Tipo**<br>mshr_type<br>*Opção mshr_logisticselectronicaddressmethodtype definida* | Ler/gravar<br>Obrigatório | O tipo de detalhe do contato. |
| **Código do país/região**<br>mshr_countryregioncode<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O país ou região do endereço |
| **Localizador**<br>mshr_locator<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Os detalhes do contato. Por exemplo, se o tipo for **Endereço de email**, este campo conterá o endereço de email do candidato. |
| **Extensão do localizador**<br>mshr_locatorextension<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A extensão do localizador. Por exemplo, se o tipo for **Telefone**, esta propriedade conterá a extensão de número de telefone. |
| **É móvel**<br>mshr_ismobile<br>*opção mshr_noyes definida* | Ler/gravar<br>Obrigatório | Especifica se o número de telefone é um número de celular. |
| **É mensagem instantânea**<br>mshr_isinstantmessage<br>*opção mshr_noyes definida* | Ler/gravar<br>Obrigatório | Especifica se o telefone está habilitado para mensagens instantâneas. |
| **É principal**<br>mshr_isprimary<br>*opção mshr_noyes definida* | Ler/gravar<br>Obrigatório | Determina o contato principal do tipo de contato. Deve haver somente um registro principal por tipo de contato. |
| **É particular**<br>mshr_isprivate<br>*opção mshr_noyes definida* | Ler/gravar<br>Obrigatório | Identifica se este endereço é um endereço particular da pessoa. |
| **Finalidade**<br>mshr_purpose<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A finalidade/função de detalhes do contato. |
| **Campo principal**<br>mshr_primaryfield<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório | Campo usado como identificador principal do registro de entidade. Combinação de número, tipo, descrição e localizador do participante. |

## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Exemplo de consulta de candidato a ser contratado](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]