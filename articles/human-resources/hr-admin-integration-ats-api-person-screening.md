---
title: Triagem da pessoa
description: Este tópico descreve a entidade Triagem da pessoa para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: d76bb57d85ee16f4faa0bb9cfec77047feb7df5f
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125368"
---
# <a name="person-screening"></a>Triagem da pessoa

Este tópico descreve a entidade Triagem da pessoa para o Dynamics 365 Human Resources.

Nome físico: mshr_hcmpersonscreeningentity

## <a name="description"></a>Descrição

Esta entidade descreve as triagens que um candidato passou ou deve passar para o emprego.

## <a name="json-representation"></a>Representação JSON

```json
{
    "mshr_note": "String",
    "mshr_requiredby": "Date",
    "mshr_status": Int,
    "mshr_partynumber": "String",
    "mshr_screeningtypeid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonscreeningentityid": "Guid",
    "mshr_completeddate": "Date"
}
```

## <a name="properties"></a>Propriedades

| Propriedade<br>**Nome físico**<br>**_Tipo_** | Uso | Descrição |
| --- | --- | --- |
| **ID da entidade de triagem da pessoa**<br>mshr_hcmpersonscreeningentityid<br>*GUID* | Somente leitura<br>Obrigatório<br>Gerado pelo sistema | Identificador principal exclusivo do registro de triagem da pessoa. |
| **Número do participante**<br>mshr_partynumber<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | O número do participante (pessoa) associado ao candidato. |
| **Valor da ID da pessoa**<br>_mshr_fk_person_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: mshr_dirpersonentityid de mshr_dirpersonentity | O identificador gerado pelo sistema do registro da entidade de participante (pessoa). |
| **ID de tipo de triagem**<br>mshr_screeningtypeid<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório<br>Chave estrangeira: ScreeningType | O identificador do tipo de triagem definido em Human Resources. |
| **Valor de ID do tipo de triagem**<br>_mshr_fk_screeningtype_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: mshr_hcmscreeningtypeentityid de mshr_hcmscreeningtypeentity | Identificador gerado pelo sistema do registro de tipo de triagem na entidade associada. |
| **Exigido por**<br>mshr_requiredby<br>*Datetime* | Ler/gravar<br>Opcional | A data na qual a triagem deve ser concluída. |
| **Status**<br>mshr_status<br>*conjunto de opções mshr_hcmcompletionstatus*<br>Ler/gravar<br>Obrigatório | Fornece o status do candidato para a triagem. |
| **Data de conclusão**<br>mshr_completeddate<br>*Datetime* | Ler/gravar<br>Opcional | A data em que a triagem foi concluída. |
| **Observação**<br>mshr_note<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Observações para uso por gerentes e recrutadores de contratação. |

## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Exemplo de consulta de candidato a ser contratado](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

