---
title: Experiência profissional da pessoa
description: Este artigo descreve a entidade Experiência profissional da pessoa para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: d306213e4c647ecd4be98598cba92376aba0d5bb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856415"
---
# <a name="person-professional-experience"></a>Experiência profissional da pessoa


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo descreve a entidade Experiência profissional da pessoa para o Dynamics 365 Human Resources.

Nome físico: mshr_hcmpersonprofessionalexperienceentity

## <a name="description"></a>Descrição

Esta entidade descreve a experiência profissional ou o histórico de trabalho de um candidato.

## <a name="json-representation"></a>Representação JSON

```json
{
    "mshr_partynumber": "String",
    "mshr_employerposition": "String",
    "mshr_startdate": "Date",
    "mshr_allowcontactemployer": Int,
    "mshr_employerlocation": "String",
    "mshr_employername": "String",
    "mshr_enddate": "Date",
    "mshr_note": "String",
    "mshr_phone": "String",
    "mshr_url": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonprofessionalexperienceentityid": "Guid"
}
```

## <a name="properties"></a>Propriedades

| Propriedade<br>**Nome físico**<br>**_Tipo_** | Uso | Descrição |
| --- | --- | --- |
| **ID de entidade de experiência profissional da pessoa**<br>mshr_hcmpersonprofessionalexperienceentityid<br>*GUID* | Somente leitura<br>Obrigatório | Um identificador exclusivo gerado pelo sistema para o registro de entidade. |
| **Número do participante**<br>mshr_partynumber<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | Identificador exclusivo do registro de pessoa do candidato. |
| **Valor da ID da pessoa**<br>_mshr_fk_person_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: mshr_dirpersonentityid de mshr_dirpersonentity | Identificador exclusivo gerado pelo sistema do registro de entidade da pessoa. |
| **Cargo do empregador**<br>mshr_employerposition<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | O título da posição mantida pelo candidato durante o emprego. |
| **Nome do empregador**<br>mshr_employername<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | O nome do empregador. |
| **Localização do empregador**<br>mshr_employerlocation<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A localização do empregador. Tamanho máximo: 60. Nenhum formato específico definido ou necessário. |
| **Telefone**<br>mshr_phone<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O número de telefone do empregador. |
| **URL**<br>mshr_url<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A URL do site do empregador. |
| **Data de início**<br>mshr_startdate<br>*Datetime* | Ler/gravar<br>Obrigatório | A data de início do emprego do candidato. |
| **Data de término**<br>mshr_enddate<br>*Datetime* | Ler/gravar<br>Opcional | A data final do emprego do candidato, ou nula, se o candidato ainda estiver empregado aqui. |
| **Permitir empregador de contato**<br>mshr_allowcontactemployer<br>*conjunto de opções mshr_hrmblankyesno* | Ler/gravar<br>Opcional | Significa se o candidato permite contatar o empregador anterior. |
| **Observação**<br>mshr_note<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Observações para uso pelo recrutador ou gerente de contratação. |
| **Campo principal**<br>mshr_primaryfield<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório | Campo usado como identificador principal do registro de entidade. Combinação de número de participante, data de início, cargo do empregador e nome do empregador. |

## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Exemplo de consulta de candidato a ser contratado](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
