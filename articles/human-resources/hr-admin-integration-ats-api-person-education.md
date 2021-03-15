---
title: Educação da pessoa
description: Este tópico descreve a entidade Educação da pessoa para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: b3f3c5a94d7deedd70af0d031c15ecf631dce4d7
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125320"
---
# <a name="person-education"></a>Educação da pessoa

Este tópico descreve a entidade Educação da pessoa para o Dynamics 365 Human Resources.


Nome físico: mshr_hcmpersoneducationentity

## <a name="description"></a>descrição

Esta entidade contém o histórico educacional da pessoa que é o candidato. A educação está vinculada ao registro de pessoa que permite que a educação seja associada a qualquer outra função criada para a pessoa, além do registro de candidatos (trabalhador, prestador de serviço etc.).

## <a name="json-representation"></a>Representação JSON

```json
{
    "mshr_creditbasis": Int,
    "mshr_creditscompleted": Decimal,
    "mshr_creditsearned": Decimal,
    "mshr_creditsneeded": Decimal,
    "mshr_description": "String",
    "mshr_duration": Decimal,
    "mshr_durationunit": Int,
    "mshr_educationdisciplineid": "String",
    "mshr_educationinstitutionid": "String",
    "mshr_educationlevelid": "String",
    "mshr_enddate": "Date",
    "mshr_gradepointaverage": Decimal,
    "mshr_gradescale": "String",
    "mshr_notes": "String",
    "mshr_secondaryemphasis": "String",
    "mshr_startdate": "Date",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_educationdiscipline_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_educationinstitution_id_value": "Guid",
    "_mshr_fk_educationlevel_id_value": "Guid",
    "mshr_hcmpersoneducationentityid": "Guid"
}
```

## <a name="properties"></a>Propriedades

| Propriedade<br>**Nome físico**<br>**_Tipo_** | Uso | Descrição |
| --- | --- | --- |
| **ID da entidade de educação da pessoa**<br>mshr_hcmpersoneducationentityid<br>*GUID* | Somente leitura<br>Obrigatório | Identificador exclusivo gerado pelo sistema do registro de entidade de educação da pessoa. |
| **Número do participante**<br>mshr_partynumber<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | O identificador exclusivo d registro de participante (pessoa) do candidato. |
| **Valor da ID da pessoa**<br>_mshr_fk_person_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: mshr_dirpersonentityid de mshr_dirpersonentity | O identificador exclusivo gerado pelo sistema para o registro de pessoa do candidato. |
| **Base de crédito**<br>mshr_creditbasis<br>*conjunto de opções mshr_hcmeducationcreditbasis* | Ler/gravar<br>Opcional | A base de crédito do nível de formação educacional. |
| **Créditos concluídos**<br>mshr_creditscompleted<br>*Decimal* | Ler/gravar<br>Opcional | O número de créditos concluídos para a formação educacional. |
| **Créditos obtidos**<br>mshr_creditsearned<br>*Decimal* | Ler/gravar<br>Opcional | O número de créditos obtidos para o registro de formação educacional de um grau em andamento. |
| **Créditos necessários**<br>mshr_creditsneeded<br>*Decimal* | Ler/gravar<br>Opcional | O número de créditos necessários para um grau em andamento. |
| **Descrição**<br>mshr_description<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Uma descrição do grau do candidato. |
| **ID de nível de educação**<br>mshr_educationlevelid<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A ID do nível de educação. | 
| **Valor de ID de nível de educação**<br>_mshr_fk_educationlevel_id_value<br>*GUID* | Somente leitura<br>Opcional<br>Chave estrangeira: entidade mshr_hcmeducationdegreeentityid de mshr_hcmeducationdegreeentity | Um identificador gerado pelo sistema para o registro de nível de formação educacional. Esse identificador fornece os graus e níveis de formação educacional definidos para a organização. |
| **ID da disciplina de educação**<br>mshr_educationdisciplineid<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório<br>Chave estrangeira: EducationDiscipline | A ID da disciplina de educação. |
| **Valor da ID da disciplina de educação**<br>_mshr_fk_educationdiscipline_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: mshr_hcmeducationdisciplineentityid de mshr_hcmeducationdisciplineentity | O identificador exclusivo gerado pelo sistema da disciplina de educação do registro de educação. |
| **Ênfase secundária**<br>mshr_secondaryemphasis<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A ênfase secundária do nível obtido. |
| **ID da instituição educacional**<br>mshr_educationinstitutionid<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A ID da instituição educacional assistida. |
| **Valor de ID da instituição educacional**<br>_mshr_fk_educationinstitution_id_value<br>*GUID* | Somente leitura<br>Opcional<br>Chave estrangeira: mshr_hcmeducationinstitutionentityid de mshr_hcmeducationinstitutionentity | Identificador gerado pelo sistema da instituição educacional. |
| **Data de início**<br>mshr_startdate<br>*Datetime* | Ler/gravar<br>Opcional | A data de início da formação educacional para o nível obtido. |
| **Data de término**<br>mshr_enddate<br>*Datetime* | Ler/gravar<br>Obrigatório | A data em que a credencial foi emitida. |
| **Duração**<br>mshr_duration<br>*Decimal* | Ler/gravar<br>Opcional | A duração do registro de formação educacional. |
| **Unidade de duração**<br>mshr_durationunit<br>*conjunto de opções mshr_periodunit* | Ler/gravar<br>Opcional | A unidade de tempo associada à duração do registro de formação educacional. |
| **Média da pontuação**<br>mshr_gradepointaverage<br>*Decimal* | Ler/gravar<br>Opcional | A média da pontuação obtida para o grau. |
| **Escala de pontuação**<br>mshr_gradescale<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | A escala usada para a média de pontuação. |
| **Observação**<br>mshr_notes<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Observações para uso pelo recrutador ou gerente de contratação. |
| **Campo principal**<br>mshr_primaryfield<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório | Campo usado como outro identificador principal do registro de entidade. Combinação de número de participante, ID da disciplina de educação, ID da instituição educacional e ID de nível de formação educacional. |

## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Exemplo de consulta de candidato a ser contratado](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]