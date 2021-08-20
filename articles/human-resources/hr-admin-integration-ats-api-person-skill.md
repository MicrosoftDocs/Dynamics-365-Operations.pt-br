---
title: Habilidade da pessoa
description: Este tópico descreve a entidade Habilidade da pessoa para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: d2721e3eace401537e85e57b5895d508317e6c4b71d481d15ff176b786a937e4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756187"
---
# <a name="person-skill"></a>Habilidade da pessoa

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve a entidade Habilidade da pessoa para o Dynamics 365 Human Resources.

Nome físico: mshr_hcmpersonskillentity

## <a name="description"></a>descrição

Esta entidade descreve as habilidades de um candidato.

## <a name="json-representation"></a>Representação JSON

```json
{
    "mshr_certifier": "String",
    "mshr_partynumber": "String",
    "mshr_levelid": "String",
    "mshr_ratinglevelexaminer": "String",
    "mshr_skillid": "String",
    "mshr_ratingid": "String",
    "mshr_leveltype": Int,
    "mshr_yearsofexperience": Decimal,
    "mshr_verified": Int,
    "mshr_leveldate": "Date",
    "mshr_primaryfield": "String",
    "_mshr_fk_certifier_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_ratinglevel_id_value": "Guid",
    "_mshr_fk_ratinglevelexaminer_id_value": "Guid",
    "_mshr_fk_skill_id_value": "Guid",
    "mshr_hcmpersonskillentityid": "Guid"
}
```

## <a name="properties"></a>Propriedades

| Propriedade<br>**Nome físico**<br>**_Tipo_** | Uso | Descrição |
| --- | --- | --- |
| **ID da entidade de habilidade da pessoa**<br>mshr_hcmpersonskillentityid<br>*GUID* | Somente leitura<br>Obrigatório | Um identificador exclusivo gerado pelo sistema para o registro de entidade. |
| **Número do participante**<br>mshr_partynumber<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório |   A ID do registro de participante (pessoa) associado. |
| **Valor da ID da pessoa**<br>_mshr_fk_person_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: mshr_dirpersonentityid de mshr_dirpersonentity | O identificador gerado pelo sistema do registro da entidade de participante (pessoa). |
| **Certificador**<br>mshr_certifier<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O número da equipe do trabalhador que certificou esta habilidade. |
| **Valor da ID do certificador**<br>_mshr_fk_certifier_id_value<br>*GUID* | Somente leitura<br>Opcional<br>Chave estrangeira: mshr_hcmworkerentityid de mshr_hcmworkerentity | Identificador exclusivo gerado pelo sistema do registro de trabalhador do trabalhador que certificou a habilidade. |
| **ID da habilidade**<br>mshr_skillid<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | O identificador da habilidade definida no Human Resources. |
| **Valor da ID da habilidade**<br>_mshr_fk_skill_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: mshr_hcmskillentityid de mshr_hcmskillentity | O identificador gerado pelo sistema da habilidade selecionada. |
| **Anos de experiência**<br>mshr_yearsofexperience<br>*Decimal* | Ler/gravar<br>Opcional | Os anos de experiência que o candidato tem nessa habilidade. |
| **ID da classificação**<br>mshr_ratingid<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | O tipo de escala de classificação. Para essa entidade, o valor é **Habilidades**. |
| **Tipo de nível**<br>mshr_leveltype<br>*conjunto de opções mshr_hrmskillleveltype* | Ler/gravar<br>Obrigatório | Uma categorização de tipo para o nível atribuído à habilidade. |
| **ID de nível**<br>mshr_levelid<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | A ID do nível de classificação que o candidato tem para esta habilidade. |
| **Valor de ID de nível de classificação**<br>_mshr_fk_ratinglevel_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: mshr_hcmratinglevelentityid de mshr_hcmratinglevelentity | O identificador gerado pelo sistema do nível de classificação. |
| **Data do nível**<br>mshr_leveldate<br>*Datetime* | Ler/gravar<br>Obrigatório | A data em que o candidato foi classificado na habilidade. |
| **Examinador de nível de classificação**<br>mshr_ratinglevelexaminer<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O número da equipe do trabalhador que classificou o candidato. |
| **Valor de ID de examinador de nível de classificação**<br>_mshr_fk_ratinglevelexaminer_id_value<br>*GUID* | Somente leitura<br>Opcional<br>Chave estrangeira: mshr_hcmworkerentityid de mshr_hcmworkerentity | O identificador gerado pelo sistema do trabalhador que examinou o nível de habilidade do candidato. |
| **Verificada**<br>mshr_verified<br>*conjunto de opções mshr_noyes* | Ler/gravar<br>Obrigatório | Indica se o nível de habilidade avaliado foi verificado. |
| **Campo principal**<br>mshr_primaryfield<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório | Campo a ser usado como identificador do registro de entidade. Combinação de número de participante, tipo de nível, ID de habilidade e data de nível. |

## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Exemplo de consulta de candidato a ser contratado](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]