---
title: Posição da solicitação de recrutamento
description: Este artigo descreve a entidade Posição da solicitação de recrutamento para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: 0996532edf09ea5159e143d92fb2a93c4d6f826d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904236"
---
# <a name="recruiting-request-position"></a>Posição da solicitação de recrutamento


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo descreve a entidade Posição da solicitação de recrutamento para o Dynamics 365 Human Resources.

Nome físico: mshr_hcmrecruitingrequestpositionentity

### <a name="description"></a>Descrição

Descreve a posição ou as posições a serem preenchidas para uma solicitação de recrutamento. A adição de uma posição à solicitação de recrutamento é opcional. As propriedades da posição são somente leitura, pois as propriedades de posição não devem ter diferença na solicitação de recrutamento e no registro mestre de posição. Se as propriedades precisarem ser alteradas, isso deverá ser feito no registro mestre de posição antes da adição da posição à solicitação de recrutamento.

### <a name="json-representation"></a>Representação JSON
```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_positionid": "String",
    "mshr_description": "String",
    "mshr_positiontypeid": "String",
    "mshr_status": Int,
    "mshr_departmentnumber": "String",
    "mshr_reportstopositionid": "String",
    "mshr_reportstopersonnelnumber": "String",
    "mshr_financialdimension": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_position_id_value": "Guid",
    "_mshr_fk_positiontype_id_value": "Guid",
    "_mshr_fk_department_id_value": "Guid",
    "_mshr_fk_reportstoposition_id_value": "Guid",
    "_mshr_fk_reportstoworker_id_value": "Guid",
    "mshr_hcmrecruitingrequestpositionentityid": "Guid"
}
```

### <a name="properties"></a>Propriedades

| Propriedade<br>**Nome físico**<br>**_Tipo_** | Usar | Descrição |
| --- | --- | --- |
| **ID de entidade de posição de solicitação de recrutamento**<br>mshr_hcmrecruitingrequestpositionentityid<br>*GUID* | Somente leitura<br>Obrigatório |    O identificador gerado pelo sistema do registro de posição de solicitação de recrutamento. |
| **ID da solicitação de recrutamento**<br>mshr_recruitingrequestid<br>*Cadeia de caracteres* | Gravação única<br>Obrigatório | O identificador exclusivo legível pelo usuário da solicitação de recrutamento. |
| **Valor da ID de solicitação de recrutamento**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: entidade mshr_hcmrecruitingrequestentityid de mshr_hcmrecruitingrequestentity | O identificador gerado pelo sistema da solicitação de recrutamento à qual a posição é atribuída. |
| **ID da posição**<br>mshr_positionid<br>*Cadeia de caracteres* | Gravação única<br>Obrigatório | O identificador exclusivo legível pelo usuário da posição. |
| **Valor de ID de posição**<br>_mshr_fk_position_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: entidade mshr_hcmpositionv2entityid de mshr_hcmpositionv2entity | Identificador da posição gerada pelo sistema. |
| **Descrição**<br>mshr_description<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório | A descrição da posição. |
| **ID do tipo de posição**<br>mshr_positiontypeid<br>*Cadeia de caracteres* | Somente leitura<br>Opcional | O identificador exclusivo legível pelo usuário do tipo de posição para essa posição. |
| **Valor de ID do tipo de posição**<br>_mshr_fk_positiontype_id_value<br>*GUID* | Somente leitura<br>Opcional<br>Chave estrangeira: entidade mshr_hcmpositiontypeentityid de mshr_hcmpositiontypeentity | Um identificador exclusivo gerado pelo sistema do tipo de posição para essa posição. |
| **Status**<br>mshr_status<br>Opção *RecruitingRequestPositionStatus* definida | Ler/gravar<br>Obrigatório | Status da posição da solicitação de recrutamento. |
| **Número do Departamento**<br>mshr_departmentnumber<br>*Cadeia de caracteres* | Somente leitura<br>Opcional<br> | O número do departamento da posição. |
| **Valor de ID do departamento**<br>_mshr_fk_department_id_value<br>*GUID* | Somente leitura<br>Opcional<br>Chave estrangeira: entidade mshr_omdepartmententityid de mshr_omdepartmententity | O identificador exclusivo gerado pelo sistema do departamento da posição. |
| **ID de relatórios para posição**<br>mshr_reportstopositionid<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório | A ID legível pelo usuário da posição à qual a posição recrutada se reporta na hierarquia organizacional. |
| **Valor de ID de posição subordinada a**<br>_mshr_fk_reportstoposition_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: entidade mshr_hcmpositionv2entityid de mshr_hcmpositionv2entity | A ID gerada pelo sistema da posição à qual a posição recrutada se reporta. |
| **Subordinado ao número de pessoal**<br>mshr_reportstopersonnelnumber<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório | A ID de trabalhador do trabalhador à qual o candidato contratado se reportará. |
| **Valor de ID de trabalhador subordinado**<br>_mshr_fk_reportstoworker_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: mshr_hcmworkerbaseentityid de mshr_hcmworkerbaseentity entity | A ID do trabalhador gerada pelo sistema à qual o candidato contratado se reportará. |
| **Dimensão financeira**<br>mshr_financialdimension<br>*Cadeia de caracteres* | Somente leitura<br>Opcional | A dimensão financeira (por exemplo, centro de custo) atribuída à posição. A dimensão financeira é atribuída a cada posição por entidade legal. Os centros de custo definidos nas dimensões podem ser acessados por meio da entidade mshr_dimattributeomcostcenterentity. |
| **ID da área de dados**<br>mshr_dataareaid<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Especifica a entidade legal (empresa) para a posição da solicitação de recrutamento. |
| **Valor da ID da área de dados**<br>_mshr_dataareaid_id_value<br>*GUID* | Somente leitura<br>Opcional<br>Chave estrangeira: cdm_companyid da entidade cdm_company | Valor GUID gerado pelo sistema identificando a entidade legal (empresa) para a posição da solicitação de recrutamento. |
| **Campo principal**<br>mshr_primaryfield<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório | A concatenação do valor de solicitação de recrutamento e a ID de posição como outro método para identificar o registro de forma exclusiva. |

## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de exemplo de solicitação de recrutamento](hr-admin-integration-ats-api-recruiting-request-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
