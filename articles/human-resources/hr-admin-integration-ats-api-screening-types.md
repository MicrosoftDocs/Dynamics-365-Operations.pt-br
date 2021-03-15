---
title: Tipos de triagem
description: Este tópico descreve a entidade Tipos de triagem para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: 227c15acb44e020ea9858961e45c11ad07e18a74
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "5126161"
---
# <a name="screening-types"></a>Tipos de triagem

Este tópico descreve a entidade Tipos de triagem para o Dynamics 365 Human Resources.

Nome físico: mshr_hcmscreeningtypeentity

## <a name="description"></a>descrição

Esta entidade descreve os tipos de triagem configurados pela empresa para processos de pré-contratação e triagem de funcionário em andamento.

## <a name="json-representation"></a>Representação JSON

```json
{
    "mshr_description": "String",
    "mshr_frequencyunit": Int,
    "mshr_generatefrom": Int,
    "mshr_frequencyinterval": Int,
    "mshr_screeningtypeid": "String",
    "mshr_hcmscreeningtypeentityid": "Guid"
}
```

## <a name="properties"></a>Propriedades

| Propriedade<br>**Nome físico**<br>**_Tipo_** | Uso | Descrição |
| --- | --- | --- |
| **ID da entidade do tipo de triagem**<br>mshr_hcmscreeningtypeentityid<br>*GUID* | Somente leitura<br>Obrigatório<br>Gerado pelo sistema | Identificador principal exclusivo do registro de tipo de triagem. |
| **ID de tipo de triagem**<br>mshr_screeningtypeid<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | Identificador exclusivo definido pelo usuário de tipo de triagem. |
| **Descrição**<br>mshr_description<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | A descrição do tipo de triagem. |
| **Unidade de frequência**<br>mshr_frequencyunit<br>*conjunto de opções mshr_hcmfrequencyunit* | Ler/gravar<br>Obrigatório | Descreve a frequência com que a triagem deve ser concluída para a pessoa atribuída. |
| **Gerar de**<br>mshr_generatefrom<br>*conjunto de opções mshr_hcmfrequencygeneratefrom* | Ler/gravar<br>Obrigatório | Se o valor de frequência for qualquer valor diferente de "Apenas ocasional", o valor GenerateFrom determinará a data a partir da qual o próximo evento de triagem será calculado. |
| **Intervalo de frequência**<br>mshr_frequencyinterval<br>*Inteiro* | Ler/gravar<br>Obrigatório | Se o valor de frequência for qualquer valor diferente de "Apenas ocasional", você deverá definir um intervalo para as unidades de tempo entre cada evento de triagem. |

## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Exemplo de consulta de candidato a ser contratado](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]