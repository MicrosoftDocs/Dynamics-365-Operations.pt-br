---
title: Formação educacional de solicitação de recrutamento
description: Este tópico descreve a entidade Formação educacional de solicitação de recrutamento para Dynamics 365 Human Resources.
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
ms.openlocfilehash: 4976e51dbe0cb7f50290b40d6342bcc18044cd52
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6057421"
---
# <a name="recruiting-request-education"></a>Formação educacional de solicitação de recrutamento

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve a entidade Formação educacional de solicitação de recrutamento para Dynamics 365 Human Resources.

Nome físico: mshr_hcmrecruitingrequesteducationentity

### <a name="description"></a>Descrição

Descreve os requisitos de formação educacional de um RecruitingRequest.

### <a name="json-representation"></a>Representação JSON

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_educationdisciplineid": "String",
    "mshr_educationdisciplinedescription": "String",
    "mshr_educationlevelid": "String",
    "mshr_educationleveldescription": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_educationdiscipline_id_value": "Guid",
    "_mshr_fk_educationlevel_id_value": "Guid",
    "mshr_hcmrecruitingrequesteducationentityid": "Guid"
}
```

### <a name="properties"></a>Propriedades

| Propriedade<br>**Nome físico**<br>**_Tipo_** | Usar | Descrição |
| --- | --- | --- |
| **ID de Entidade Formação educacional de solicitação de recrutamento**<br>mshr_hcmrecruitingrequesteducationentityid<br>*GUID* | Somente leitura<br>Obrigatório | Identificador exclusivo gerado pelo sistema para o registro de Formação educacional da solicitação de recrutamento. |
| **ID da solicitação de recrutamento**<br>mshr_recruitingrequestid<br>*Cadeia de caracteres* | Gravação única<br>Obrigatório | O identificador exclusivo legível pelo usuário da solicitação de recrutamento relacionada. |
| **Valor da ID de solicitação de recrutamento**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: mshr_hcmrecruitingrequestentityid de mshr_hcmrecruitingrequestentity | O identificador exclusivo gerado pelo sistema da solicitação de recrutamento relacionada. |
| **ID de nível de formação educacional**<br>mshr_educationlevelid<br>*Cadeia de caracteres* | Gravação única<br>Obrigatório | O nível de formação educacional necessário. |
| **Valor de ID de nível de formação educacional**<br>_mshr_fk_educationlevel_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: mshr_hcmeducationlevelentityid de mshr_hcmeducationlevelentity | Identificador exclusivo gerado pelo sistema do nível de formação educacional necessário. |
| **Descrição do nível de formação educacional**<br>mshr_educationleveldescription<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório | A descrição do nível necessário para a habilidade. |
| **ID da disciplina de educação**<br>mshr_educationdisciplinedescription<br>*Cadeia de caracteres* | Gravação única<br>Obrigatório | A área da disciplina educacional. |
| **Valor da ID da disciplina de educação**<br>_mshr_fk_educationdiscipline_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: mshr_hcmeducationdisciplineentityid de mshr_hcmeducationdisciplineentity | Identificador exclusivo gerado pelo sistema da área de disciplina educacional. |
| **Descrição da disciplina educacional**<br>mshr_educationdisciplinedescription<br>Cadeia de caracteres | Somente leitura<br>Obrigatório | A descrição da área da disciplina educacional. |
| **ID da área de dados**<br>mshr_dataareaid<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Especifica a entidade legal (empresa).|
| **Valor da ID da área de dados**<br>_mshr_dataareaid_id_value<br>*GUID* | Somente leitura<br>Opcional<br>Chave estrangeira: cdm_companyid da entidade cdm_company | Valor GUID gerado pelo sistema identificando a entidade legal (empresa). |
| **Campo principal**<br>mshr_primaryfield<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório | A concatenação do valor de solicitação de recrutamento, a ID de nível de formação educacional e a ID de disciplina de educação como outro método para identificar o registro de forma exclusiva. |

## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de exemplo de solicitação de recrutamento](hr-admin-integration-ats-api-recruiting-request-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]