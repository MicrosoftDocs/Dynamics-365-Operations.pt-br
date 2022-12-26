---
title: Triagem da pessoa
description: Este artigo descreve a entidade Triagem da pessoa para o Dynamics 365 Human Resources.
author: jaredha
ms.date: 12/05/2022
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
ms.openlocfilehash: 3c316e0381f4d407ed7c4c39b5949717b71477bd
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831881"
---
# <a name="person-screening"></a>Triagem da pessoa


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo descreve a entidade Triagem da pessoa para o Dynamics 365 Human Resources.

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
    "_mshr_fk_screeningtype_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonscreeningentityid": "Guid",
    "mshr_completeddate": "Date"
}
```

## <a name="properties"></a>Propriedades

| Propriedade<br>**Nome físico**<br>**_Tipo_** | Uso | descrição |
| --- | --- | --- |
| **Observação**<br>mshr_note<br>*Sequência de caracteres* | Ler/gravar<br>Opcional | Observações para uso por gerentes e recrutadores de contratação. |
| **Exigido por**<br>mshr_requiredby<br>*Datetime* | Ler/gravar<br>Opcional | A data na qual a triagem deve ser concluída. |
| **Status**<br>mshr_status<br>*conjunto de opções mshr_hcmcompletionstatus*|Ler/gravar<br>Obrigatório | Fornece o status do candidato para a triagem. |
| **Número do participante**<br>mshr_partynumber<br>*Sequência de caracteres* | Ler/gravar<br>Obrigatório | O número do participante (pessoa) associado ao candidato. |
| **ID de tipo de triagem**<br>mshr_screeningtypeid<br>*Sequência de caracteres* | Ler/gravar<br>Obrigatório<br>Chave estrangeira: ScreeningType | O identificador do tipo de triagem definido em Human Resources. |
| **Valor de ID do tipo de triagem**<br>_mshr_fk_screeningtype_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: mshr_hcmscreeningtypeentityid de mshr_hcmscreeningtypeentity | Identificador gerado pelo sistema do registro de tipo de triagem na entidade associada. |
| **Campo principal**<br>mshr_primaryfield<br>*Sequência de caracteres* |  Somente leitura<br>Obrigatório | Campo a ser usado como identificador do registro de entidade. |
| **Valor da ID da pessoa**<br>_mshr_fk_person_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: mshr_dirpersonentityid de mshr_dirpersonentity | O identificador gerado pelo sistema do registro da entidade de participante (pessoa). |
| **ID da entidade de triagem da pessoa**<br>mshr_hcmpersonscreeningentityid<br>*GUID* | Somente leitura<br>Obrigatório<br>Gerado pelo sistema| Identificador principal exclusivo do registro de triagem da pessoa. |
| **Data de conclusão**<br>mshr_completeddate<br>*Datetime* | Ler/gravar<br>Opcional | A data em que a triagem foi concluída. |


## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Exemplo de consulta de candidato a ser contratado](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
