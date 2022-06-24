---
title: Tipo de certificado
description: Este artigo descreve a entidade de tipo Certificado para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: bfe7f06176098a504f8d2ad1c1431a6f60fe059c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886179"
---
# <a name="certificate-type"></a>Tipo de certificado


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo descreve a entidade de tipo Certificado para o Dynamics 365 Human Resources.

Nome físico: mshr_hcmcertificatetypeentity

## <a name="description"></a>descrição

Esta entidade define a lista de tipos de certificados profissionais configurados no Human Resources. A entidade não é específica de uma entidade legal (empresa).

## <a name="json-representation"></a>Representação JSON

```json
{
    "mshr_certificatetype": "String",
    "mshr_description": "String",
    "mshr_requirerenewal": Int,
    "mshr_hcmcertificatetypeentityid": "Guid"
}
```

## <a name="properties"></a>Propriedades

| Propriedade<br>**Nome físico**<br>**_Tipo_** | Usar | Descrição |
| --- | --- | --- |
| **ID da entidade do tipo de certificado**<br>mshr_hcmcertificatetypeentityid<br>*GUID* | Somente leitura<br>Obrigatório 
Gerado pelo sistema | Identificador principal exclusivo do tipo de certificado. |
| **Tipo de certificado**<br>mshr_certificatetype<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | Identificador exclusivo legível pelo usuário do tipo de certificado. |
| **Descrição**<br>mshr_description<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | Descrição do tipo de certificado. |
| **Exigir renovação**<br>mshr_requirerenewal<br>*opção mshr_noyes definida* | Ler/gravar<br>Opcional | Indica se a renovação é necessária para o certificado. |

## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Exemplo de consulta de candidato a ser contratado](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
