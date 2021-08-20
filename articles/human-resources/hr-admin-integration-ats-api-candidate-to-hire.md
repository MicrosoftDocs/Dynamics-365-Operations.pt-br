---
title: Candidato para contratação
description: Este tópico descreve a entidade Candidato para contratação para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: aef9f4889d17811026fc36091bb98494412dacd898f847ac661333628e8e32e7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742815"
---
# <a name="candidate-to-hire"></a>Candidato para contratação

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve a entidade Candidato para contratação para o Dynamics 365 Human Resources.

Nome físico: mshr_hcmcandidatetohireentity

## <a name="description"></a>Descrição

Esta entidade fornece detalhes de candidatos usados para criar um trabalhador no Dynamics 365 Human Resources. Ela é usada para ler todos os registros de candidatos e criar registros de candidatos internos e externos, permitindo que você crie detalhes pessoais para o novo candidato.

Ao criar um registro de candidato externo que será um novo registro de pessoa no sistema, você não deve definir um número de participante (pessoa) que lance um novo registro de candidato. O novo registro de entidade de pessoa é criado com o novo registro de candidato.

Quando você criar um registro de candidato interno (um candidato ao cargo que já tem um registro de funcionário com a empresa), defina o número de participante (pessoa) do registro que já existe para a pessoa para a propriedade mshr_partynumber no registro de candidato, em vez de definir informações pessoais (como nome, sexo ou data de nascimento) que seriam usados para criar um novo registro de pessoa.

## <a name="json-representation"></a>Representação JSON

```json
        {
            "mshr_candidateid": "String",
            "mshr_partynumber": "String",
            "mshr_partytype": "String",
            "mshr_recruitingrequestid": "String",
            "mshr_positionid": "String",
            "mshr_firstname": "String",
            "mshr_middlename": "String",
            "mshr_lastnameprefix": "String",
            "mshr_lastname": "String",
            "mshr_gender": Int,
            "mshr_birthdate": "Date",
            "mshr_citizenshipcountrycode": "String",
            "mshr_veteranstatusid": "String",
            "mshr_isdisabledveteran": Int,
            "mshr_availabilitydate": "Date",
            "mshr_iswillingtorelocate": Int,
            "mshr_comments": "String",
            "mshr_applicantintegrationresult": Int,
            "mshr_donothirereasoncodeid": "String",
            "mshr_dataareaid": "String",
            "_mshr_dataareaid_id_value": "Guid",
            "_mshr_fk_person_id_value": "Guid",
            "_mshr_fk_recruitingrequest_id_value": "Guid",
            "_mshr_fk_position_id_value": "Guid",
            "mshr_hcmcandidatetohireentityid": "Guid",
            "_mshr_fk_veteranstatus_id_value": "Guid",
            "_mshr_fk_reasoncode_id_value": "Guid",
            "mshr_militaryserviceenddate": "Guid",
            "mshr_militaryservicestartdate": "Guid"
        }
```

## <a name="properties"></a>Propriedades

| Propriedade<br>**Nome físico**<br>**_Tipo_** | Usar | Descrição |
| --- | --- | --- |
| **ID da entidade de candidato a ser contratado**<br>mshr_hcmcandidatetohireentityid<br>GUID | Somente leitura<br>Obrigatório<br>Gerado pelo sistema | Um identificador exclusivo gerado pelo sistema para o registro de entidade. |
| **ID do Candidato**<br>mshr_candidateid<br>Cadeia de caracteres | Somente leitura<br>Obrigatório<br>Gerado pelo sistema | Um identificador exclusivo para a entidade. |
| **Número do participante**<br>mshr_partynumber<br>Cadeia de caracteres | Somente leitura<br>Obrigatório | O número do participante (pessoa) do registro da pessoa do candidato. |
| **Valor da ID da pessoa**<br>_mshr_fk_person_id_value<br>GUID | Somente leitura<br>Obrigatório<br>Chave estrangeira: mshr_dirpersonentityid de mshr_direpersonentity | O identificador exclusivo gerado pelo sistema para o registro de participante (pessoa) do candidato. |
| **Tipo de participante**<br>mshr_partytype<br>Conjunto de opções mshr_dirpartytype | Somente leitura<br>Obrigatório | O tipo de participante do registro, conforme definido no conjunto de opções mshr_dirpartytype. Para essa entidade, o tipo será sempre "Pessoa". |
| **ID da solicitação de recrutamento**<br>mshr_recruitingrequestid<br>Cadeia de caracteres | Gravação única<br>Opcional | Faz referência à solicitação de recrutamento que esse candidato preenche. |
| **Valor da ID de solicitação de recrutamento**<br>_mshr_fk_recruitingrequest_id_value<br>GUID | Ler/gravar<br>Opcional<br>Chave estrangeira: mshr_hcmrecruitingrequestentityid de mshr_hcmrecruitingrequestentity | O identificador exclusivo gerado pelo sistema da solicitação de recrutamento preenchida pelo candidato. |
| **ID da posição**<br>mshr_positionid<br>Cadeia de caracteres | Ler/gravar<br>Opcional | A ID da posição para a qual o candidato está sendo considerado. |
| **Valor de ID de posição**<br>_mshr_fk_position_if_value<br>GUID | Somente leitura<br>Opcional<br>Chave estrangeira: mshr_hcmpositionv2entityid de mshr_hcmpositionv2entity | Identificador da posição gerada pelo sistema para a qual o candidato está sendo considerado. |
| **Nome**<br>mshr_firstname<br>Cadeia de caracteres | Ler/gravar<br>Obrigatório | Nome do candidato. |
| **Nome do Meio**<br>mshr_middlename<br>Cadeia de caracteres | Ler/gravar<br>Opcional | Nome do meio do candidato. |
| **Prefixo do sobrenome**<br>mshr_lastnameprefix<br>Cadeia de caracteres | Ler/gravar<br>Opcional | Prefixo do sobrenome do candidato. |
| **Sobrenome**<br>mshr_lastname<br>Cadeia de caracteres | Ler/gravar<br>Opcional | Sobrenome do candidato. |
| **Sexo**<br>mshr_gender<br>conjunto de opções mshr_hcmpersongender | Ler/gravar<br>Opcional | O sexo do candidato. |
| **Data de nascimento**<br>mshr_birthdate<br>Datetime | Ler/gravar<br>Opcional | A data de nascimento do candidato. |
| **Código de país da cidadania**<br>mshr_citizenshipcountrycode<br>Cadeia de caracteres | Ler/gravar<br>Opcional | Especifica o país em que o candidato tem cidadania. Os códigos de país válidos estão em mshr_logisticaddresscountryregionentity. |
| **ID de situação militar**<br>mshr_veteranstatusid<br>Cadeia de caracteres | Ler/gravar<br>Opcional | Indica a situação militar do candidato. |
| **Valor de ID de situação militar**<br>_mshr_fk_veteranstatus_id_value<br>GUID | Somente leitura<br>Opcional<br>Chave estrangeira: mshr_hcmveteranstatusentityid de mshr_hcmveteranstatusentity | Identificador exclusivo gerado pelo sistema para o registro de entidade de situação militar. |
| **Data de início do serviço militar**<br>mshr_militaryservicestartdate<br>Datetime | Ler/gravar<br>Opcional | A data inicial do serviço militar do candidato. |
| **Data de término do serviço militar**<br>mshr_militaryserviceenddate<br>Datetime | Ler/gravar<br>Opcional | A data final do serviço militar do candidato. |
| **É Veterano Desabilitado**<br>mshr_isdisabledveteran<br>conjunto de opções mshr_noyes | Ler/gravar<br>Opcional | Indica se o candidato tem situação militar desabilitada. |
| **Data de disponibilidade**<br>mshr_availabilitydate<br>Datetime | Ler/gravar<br>Opcional | A primeira data em que o candidato estará disponível para trabalhar. |
| **Está disposto a ser realocado**<br>mshr_iswillingtorelocate<br>conjunto de opções mshr_noyes | Ler/gravar<br>Opcional | Indica se o candidato está disposto a ser realocado para a posição. |
| **Comentários**<br>mshr_comments<br>Cadeia de caracteres | Ler/gravar<br>Opcional | Comentários a serem usados pelo recrutador ou gerente de contratação. |
| **Resultado de integração de aplicativo**<br>mshr_applcantintegrationresult<br>Conjunto de opções mshr_applicantintegrationresult | Ler/gravar<br>Obrigatório | O status do candidato no processo de contratação relacionado à integração. |
| **ID de código de motivo de não contratação**<br>mshr_donothirereasoncodeid<br>Cadeia de caracteres | Ler/gravar<br>Opcional | Um código de motivo opcionalmente fornecido quando o status (resultado da integração do aplicativo) é definido como "Não contratado". |
| **Valor da ID do código de motivo**<br>_mshr_fk_reasoncode_id_value<br>GUID | Somente leitura<br>Opcional<br>Chave estrangeira: mshr_hcmreasoncodeentityid da entidade mshr_hcmreasoncodeentity | Identificador exclusivo gerado pelo sistema para o código de motivo de **Não contratação**. |
| **ID da área de dados**<br>mshr_dataareaid<br>Cadeia de caracteres | Ler/gravar<br>Opcional |  Especifica a entidade legal (empresa). |
| **Valor da ID da área de dados**<br>_mshr_dataareaid_id_value<br>GUID | Somente leitura<br>Opcional<br>Chave estrangeira: cdm_companyid da entidade cdm_company | Valor GUID gerado pelo sistema identificando a entidade legal (empresa). |

## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Exemplo de consulta de candidato a ser contratado](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]