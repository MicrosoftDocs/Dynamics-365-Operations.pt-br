---
title: Tipos de triagem
description: Este artigo descreve a entidade Tipos de triagem para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: 95f4a3dce6851c7080ac665f5922e3b5877fa9f3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880528"
---
# <a name="screening-types"></a>Tipos de triagem


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo descreve a entidade Tipos de triagem para o Dynamics 365 Human Resources.

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
