---
title: Solicitação de recrutamento
description: Este tópico descreve a entidade Solicitação de recrutamento para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: a1f160d828c8fe5babb96d39afd911052767f67b
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8068575"
---
# <a name="recruiting-request"></a>Solicitação de recrutamento


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve a entidade Solicitação de recrutamento para o Dynamics 365 Human Resources.

Nome físico: mshr_hcmrecruitingrequestentity

### <a name="description"></a>descrição

Descreve uma solicitação de recrutamento para um trabalho.

### <a name="json-representation"></a>Representação JSON

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_hiringmanagerpersonnelnumber": "String",
    "mshr_recruiterpartynumber": "String",
    "mshr_status": Int,
    "mshr_description": "String",
    "mshr_recruitingrequestlocationid": "String",
    "mshr_comments": "String",
    "mshr_jobid": "String",
    "mshr_titleid": "String",
    "mshr_jobfunctionid": "String",
    "mshr_defaultfulltimeequivalency": Decimal,
    "mshr_regulatoryjobcategory": Int,
    "mshr_jobtypeid": "String",
    "mshr_exemptstatus": Int,
    "mshr_estimatedstartdate": "Date",
    "mshr_externaldescription": "String",
    "mshr_compensationlevelid": "String",
    "mshr_compensationlowthreshold": Decimal,
    "mshr_compensationcontrolpoint": Decimal,
    "mshr_compensationhighthreshold": Decimal,
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "_mshr_fk_hiringmanager_id_value": "Guid",
    "_mshr_fk_recruiter_id_value": "Guid",
    "_mshr_fk_job_id_value": "Guid",
    "_mshr_fk_title_id_value": "Guid",
    "_mshr_fk_jobtype_id_value": "Guid",
    "_mshr_fk_compensationlevel_id_value": "Guid",
    "mshr_hcmrecruitingrequestentityid": "Guid",
    "_mshr_fk_recruitingrequestlocation_id_value": “Guid”
}
```

### <a name="properties"></a>Propriedades

| Propriedade<br>**Nome físico**<br>**_Tipo_** | Uso | Descrição |
| --- | --- | --- |
| **ID de solicitação de recrutamento**<br>mshr_recruitingrequestid<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório<br>Gerado pelo sistema | Um identificador exclusivo legível pelo usuário para a solicitação exibida no aplicativo de RH. Sequência numérica. |
| **ID de entidade de solicitação de recrutamento**<br>mshr_hcmrecruitingrequestentityid<br>*GUID* | Somente leitura<br>Obrigatório<br>Gerado pelo sistema | Um valor GUID gerado pelo sistema para identificar exclusivamente a solicitação e recrutamento. |
| **ID da área de dados**<br>mshr_dataareaid<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional<br> | Especifica a entidade legal (empresa) para a solicitação de recrutamento. |
| **Valor da ID da área de dados**<br>_mshr_dataareaid_id_value<br>*GUID*<br> | Somente leitura<br>Opcional<br>Chave estrangeira: cdm_companyid da entidade cdm_company | Valor GUID gerado pelo sistema identificando a entidade legal (empresa) para a solicitação e recrutamento. |
| **Número de pessoal do gerente de contratação**<br>mshr_hiringmanagerpersonnelnumber<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O número da equipe do gerente de contratação associado a essa solicitação de recrutamento. |
| **Valor da ID do gerente de contratação**<br>_mshr_fk_hiringmanager_id_value<br>*GUID* | Somente leitura<br>Opcional<br>Chave estrangeira: mshr_hcmworkerbaseentityid de mshr_hcmworkerbaseentity entity | Valor GUID gerado pelo sistema para identificar o gerente associado à solicitação de recrutamento. |
| **Número de participante do recrutador**<br>mshr_recruiterpartynumber<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O número da pessoa (participante) do recrutador selecionado para a solicitação. |
| **Valor da ID do recrutador**<br>_mshr_fk_recruiter_id_value<br>*GUID* | Somente leitura<br>Opcional<br>Chave estrangeira: entidade mshr_dirpersonentityid de mshr_dirpersonentity | Valor GUID gerado pelo sistema para identificar o recrutador associado à solicitação de recrutamento. |
| **Status**<br>mshr_status<br>Conjunto de opções *RecruitingRequestStatus* | Ler/gravar<br>Obrigatório<br> | Indica o status da solicitação de recrutamento. |
| **Descrição**<br>mshr_description<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | Descreve a solicitação. |
| **ID da localização da solicitação de recrutamento**<br>mshr_recruitingrequestlocationid<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O identificador exclusivo legível pelo usuário do local de trabalho associado a esta solicitação. |
| **Valor da ID de local de recrutamento**<br>_mshr_fk_recruitinglocation_id_value<br>*GUID* | Somente leitura<br>Opcional<br>Chave estrangeira: entidade mshr_hcmrecruitingrequestlocationentityid de mshr_hcmrecruitingrequestlocationentity | Valor GUID gerado pelo sistema para identificar o local de solicitação de recrutamento selecionado para a solicitação. |
| **Comentários**<br>mshr_comments<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Comentários sobre a solicitação de uso por gerentes de contratação e recrutadores. |
| **ID do trabalho**<br>mshr_jobid<br>*Cadeia de caracteres* | Gravação única<br>Obrigatório |   O identificador exclusivo legível pelo usuário do trabalho compartilhado por todas as posições associadas a esta solicitação. |
| **Valor de ID do trabalho**<br>_mshr_fk_job_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: entidade mshr_hcmjobentityid de mshr_hcmjobentity | O identificador exclusivo gerado pelo sistema do trabalho compartilhado por todas as posições associadas à solicitação de recrutamento. |
| **ID do título**<br>mshr_titleid<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório | O identificador exclusivo legível pelo usuário do título de trabalho associado a esta solicitação. |
| **Valor de ID do título**<br>_mshr_fk_title_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: entidade mshr_hcmtitleid de mshr_hcmtitleentity | O identificador exclusivo gerado pelo sistema do título do trabalho selecionado para a solicitação de recrutamento. |
| **ID de Função de Trabalho**<br>mshr_jobfunctionid<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório<br>Chave estrangeira: entidade mshr_jobfunctionid de mshr_hcmjobfunctionentity | O identificador exclusivo legível pelo usuário da função de trabalho associada a esta solicitação. |
| **Equivalência ao horário integral padrão**<br>mshr_defaultfulltimeequivalency<br>*Duplo* | Somente leitura<br>Obrigatório | O valor equivalente de tempo integral para o trabalho, no qual 1,0 representa um trabalhador de horário integral. |
| **Categoria de trabalho regulatório**<br>mshr_regulatoryjobcategory<br>Conjunto de opções *RegulatoryJobCategory* | Somente leitura<br>Opcional | A categoria de trabalho EEO da função de trabalho selecionada para o trabalho. Valores válidos incluídos no conjunto de opções HcmRegulatoryJobCatetory (mshr_hcmregulatoryjobcategory). |
| **ID de tipo de trabalho**<br>mshr_jobtypeid<br>*Cadeia de caracteres* | Somente leitura<br>Opcional | O tipo do trabalho associado à posição. Os tipos de trabalho são valores definidos pelo usuário, disponíveis na entidade mshr_hcmjobtypeentity. |
| **Valor de ID do tipo de trabalho**<br>_mshr_fk_jobtype_id_value<br>*GUID* | Somente leitura<br>Opcional<br>Chave estrangeira: entidade mshr_hcmjobtypeentityid de mshr_hcmjobtypenentity | O identificador exclusivo gerado pelo sistema do tipo de trabalho associado ao trabalho para a solicitação de recrutamento. |
| **Status de isenção**<br>mshr_exemptstatus<br>Conjunto de opções *JobExemptStatus* | Somente leitura<br>Opcional | O status de isenção de FLSA com base no tipo de trabalho. |
| **Data de início estimada**<br>mshr_estimatedstartdate<br>*Data* | Ler/gravar<br>Obrigatório | A data estimada em que um candidato iniciaria o trabalho. |
| **Descrição externa**<br>mshr_externaldescription<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Uma descrição do trabalho/cargo voltado para o candidato. | 
| **Limite baixo de remuneração**<br>mshr_compensationlowthreshold<br>*Duplo* | Ler/gravar<br>Opcional | Limite inferior para o nível de remuneração. |
| **Ponto de controle de remuneração**<br>mshr_compensationcontrolpoint<br>*Duplo* | Ler/gravar<br>Opcional | Ponto de controle do nível de remuneração. |
| **Limite alto de remuneração**<br>mshr_compensationhighthreshold<br>*Duplo* | Ler/gravar<br>Opcional | Limite superior para o nível de remuneração. |
| **Nível de remuneração**<br>mshr_compensationlevelid<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | O nível de remuneração do trabalho. Um trabalho pode ser configurado com vários níveis de remuneração. Este atributo indica o nível de remuneração do trabalho selecionado para esta solicitação. |
| **ID de remuneração do trabalho**<br>_mshr_fk_jobcompensation_id_value<br>*GUID* | Somente leitura<br>Opcional<br>Chave estrangeira: entidade mshr_hcmjobcompensationentityid de mshr_hcmjobcompensationentity | O identificador exclusivo gerado pelo sistema para o nível de remuneração associado ao trabalho da solicitação de recrutamento. |

## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de exemplo de solicitação de recrutamento](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
