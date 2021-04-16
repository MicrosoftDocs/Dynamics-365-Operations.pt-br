---
title: Certificado de pessoa
description: Este tópico descreve a entidade Certificado de pessoa para o Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 796a57a5f97de08ff8c8440bc00d4dc5ced18f58
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798120"
---
# <a name="person-certificate"></a>Certificado de pessoa

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve a entidade Certificado de pessoa para o Dynamics 365 Human Resources.

Nome físico: mshr_hcmpersoncertificateentity

## <a name="description"></a>Descrição

Esta entidade descreve os certificados profissionais de um candidato.

## <a name="json-representation"></a>Representação JSON

```json
{
    "mshr_certificatetypeid": "String",
    "mshr_startdate": "Date",
    "mshr_enddate": "Date",
    "mshr_notes": "String",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_certificatetype_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersoncertificateentityid": "Guid"
}
```

## <a name="properties"></a>Propriedades

| Propriedade<br>**Nome físico**<br>**_Tipo_** | Uso | Descrição |
| --- | --- | --- |
| **ID da entidade do certificado da pessoa**<br>mshr_hcmpersoncertificateentityid<br>*GUID* | Somente leitura<br>Obrigatório | Identificador exclusivo gerado pelo sistema para o registro de entidade do certificado da pessoa. |
| **Número do participante**<br>mshr_partynumber<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | A ID de participante (pessoa) do candidato. |
| **Valor da ID da pessoa**<br>_mshr_fk_person_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: mshr_dirpersonentityid de mshr_dirpersonentity | O identificador gerado pelo sistema do registro da entidade de participante (pessoa). |
| **ID de tipo de certificado**<br>mshr_certificatetypeid<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório |  O identificador do tipo de certificado definido em Human Resources. |
| **Valor de ID de tipo de certificado**<br>_mshr_fk_certificatetype_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: mshr_hcmcertificatetypeentityid de mshr_hcmcertificatetypeentity | Identificador exclusivo gerado pelo sistema do tipo de certificado da entidade associada. |
| **Data de início**<br>mshr_startdate<br>*Datetime* | Ler/gravar<br>Obrigatório | A data em que o certificado foi emitido. |
| **Data de término**<br>mshr_enddate<br>*Datetime* | Ler/gravar<br>Opcional | A data em que o certificado expirará. |
| **Observações**<br>mshr_notes<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Observações para uso por gerentes e recrutadores de contratação. |
| **Campo principal**<br>mshr_primaryfield<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório |  Campo a ser usado como identificador do registro de entidade. Combinação de número de participante, ID de tipo de certificado e data de início. |

## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Exemplo de consulta de candidato a ser contratado](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]