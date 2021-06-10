---
title: Nível de avaliação
description: Este tópico descreve a entidade Nível de avaliação para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: 8bbd10bcc47a928070da7cd82e6d996f71c65698
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054827"
---
# <a name="rating-level"></a>Nível de avaliação

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve a entidade Nível de avaliação para o Dynamics 365 Human Resources.

Nome físico: mshr_hcmratinglevelentity

## <a name="description"></a>descrição

Esta entidade fornece os níveis de classificação disponíveis para as habilidades. Os níveis de classificação se aplicam a todas as entidades legais.

## <a name="json-representation"></a>Representação JSON

```json
{
    "mshr_description": "String",
    "mshr_factor": Int,
    "mshr_note": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_ratingmodelentity_id_value": "Guid",
    "mshr_hcmratinglevelentityid": "Guid"
}
```

## <a name="properties"></a>Propriedades

| Propriedade<br>**Nome físico**<br>**_Tipo_** | Uso | Descrição |
| --- | --- | --- |
| **ID de entidade de nível de classificação**<br>mshr_hcmratinglevelentityid<br>*GUID* | Somente leitura<br>Obrigatório<br>Gerado pelo sistema | O identificador exclusivo gerado pelo sistema para o nível. |
| **ID de nível de classificação**<br>mshr_ratinglevelid<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | Identificador exclusivo legível pelo usuário para o nível. |
| **ID do modelo de classificação**<br>mshr_ratingmodelid<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | O modelo de avaliação ao qual o nível de classificação pertence. |
| **ID de entidade de modelo de classificação**<br>_mshr_fk_ratingmodelentity_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: mshr_hcmratingmodelentityid de mshr_hcmratingmodelentity | O identificador gerado pelo sistema para o modelo de avaliação ao qual o nível de classificação pertence. |
| **Descrição**<br>mshr_description<br>*Cadeia de caracteres* | Ler/gravar<br>Obrigatório | A descrição do nível de classificação. |
| **Fator**<br>mshr_factor<br>*Inteiro* | Ler/gravar<br>Obrigatório | O fator para o nível de classificação. Ao comparar itens com um número diferente de níveis de classificação, o fator é usado para normalizar as pontuações. O valor deve ser um inteiro entre 0 e 9. |
| **Nota**<br>mshr_note<br>*Cadeia de caracteres* | Ler/gravar<br>Opcional | Qualquer nota associada ao nível de classificação. |
| **Campo principal**<br>mshr_primaryfield<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório | Campo a ser usado como identificador do registro de entidade. Combinação de ID do nível de classificação e ID do modelo de avaliação. |

## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Exemplo de consulta de candidato a ser contratado](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]