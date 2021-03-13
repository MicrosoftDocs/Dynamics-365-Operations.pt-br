---
title: Habilidade de solicitação de recrutamento
description: Este tópico descreve a entidade Habilidade de solicitação de recrutamento para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: 83a9956b9aa820e8aca9bf6b2ab920a45c1061f6
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125993"
---
# <a name="recruiting-request-skill"></a>Habilidade de solicitação de recrutamento

Este tópico descreve a entidade Habilidade de solicitação de recrutamento para o Dynamics 365 Human Resources.

Nome físico: mshr_hcmrecruitingrequestskillentity

### <a name="description"></a>descrição

Descreve os requisitos de habilidades de um RecruitingRequest.

### <a name="json-representation"></a>Representação JSON

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_skillid": "String",
    "mshr_skilldescription": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_ratingleveldescription": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_skill_id_value": "Guid",
    "_mshr_fk_ratinglevel_id_value": "Guid",
    "_mshr_fk_ratingmodel_id_value": "Guid",
    "mshr_hcmrecruitingrequestskillentityid": "Guid"
}
```

### <a name="properties"></a>Propriedades

| Propriedade<br>**Nome físico**<br>**_Tipo_** | Usar | Descrição |
| --- | --- | --- |
| **ID de entidade de habilidade de solicitação de recrutamento**<br>mshr_hcmrecruitingrequestskillentityid<br>*GUID* | Somente leitura<br>Obrigatório | Identificador exclusivo gerado pelo sistema para o registro **Habilidade de Solicitação de Recrutamento**. |
| **ID de solicitação de recrutamento**<br>mshr_recruitingrequestid<br>*Cadeia de caracteres* | Gravação única<br>Obrigatório | O identificador exclusivo legível pelo usuário da solicitação de recrutamento associada. |
| **Valor da ID de solicitação de recrutamento**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br> Chave estrangeira: entidade mshr_hcmrecruitingrequestentityid de mshr_hcmrecruitingrequestentity | O identificador exclusivo gerado pelo sistema da solicitação de recrutamento associada. |
| **ID da habilidade**<br>mshr_skillid<br>*Cadeia de caracteres*<br> | Gravação única<br>Obrigatório | O identificador exclusivo legível pelo usuário da habilidade necessária. |
| **Valor da ID da habilidade**<br>_mshr_fk_skill_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: entidade mshr_hcmskillentityid de mshr_hcmskillentity | Identificador exclusivo gerado pelo sistema da habilidade necessária. |
| **ID de nível de classificação**<br>mshr_ratinglevelid<br>*Cadeia de caracteres* | Gravação única<br>Opcional | O valor do nível de habilidade necessário selecionado para o trabalho, com base no modelo de classificação atribuído à habilidade. |
| **Valor de ID de nível de classificação**<br>_mshr_fk_ratinglevel_id_value<br>*GUID* | Somente leitura<br>Opcional<br>Chave estrangeira: entidade mshr_hcmratinglevelentityid de mshr_hcmratinglevelentity | Um identificador exclusivo gerado pelo sistema para o nível. |
| **Descrição da habilidade**<br>mshr_skilldescription<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório | A descrição da habilidade. |
| **Descrição do nível de classificação**<br>mshr_ratingleveldescription<br>*Sequência de caracteres* | Somente leitura<br>Opcional | A descrição do nível de habilidade selecionado. |
| **ID da área de dados**<br>mshr_dataareaid<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Especifica a entidade legal (empresa). |
| **Valor da ID da área de dados**<br>_mshr_dataareaid_id_value<br>*GUID* | Somente leitura<br>Opcional<br>Chave estrangeira: cdm_companyid da entidade cdm_company | Valor GUID gerado pelo sistema identificando a entidade legal (empresa). |
| **Campo principal**<br>mshr_primaryfield<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório | A concatenação do valor de solicitação de recrutamento, a ID de habilidade como outro método para identificar o registro de forma exclusiva. |
| **ID do modelo de classificação**<br>mshr_ratingmodelid<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | O modelo de classificação usado para classificar a habilidade. |
| **Valor de ID do modelo de classificação**<br>_mshr_fk_hcmratingmodel_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: entidade mshr_hcmratingmodelentityid de mshr_hcmratingmodelentity | Identificador exclusivo gerado pelo sistema do modelo de classificação usado para classificar a habilidade. |

## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de exemplo de solicitação de recrutamento](hr-admin-integration-ats-api-recruiting-request-example-query.md)
