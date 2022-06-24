---
title: Tipo de licença
description: Este artigo fornece detalhes e um exemplo de consulta da entidade de tipo de licença no Dynamics 365 Human Resources.
author: marcelbf
ms.date: 06/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6e7905989df92e943b86f86194c87dcb2a7b1446
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893776"
---
# <a name="leave-type"></a>Tipo de licença


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo descreve a entidade de tipo de licença para o Dynamics 365 Human Resources.

### <a name="description"></a>Descrição

Esta entidade fornece informações sobre um tipo de licença determinado.

Nome físico: mshr_essleavetypeentity.

## <a name="properties"></a>Propriedades

| Propriedade</br>**Nome físico**</br>**_Tipo_** | Usar | descrição |
| --- | --- | --- |
| **Id do tipo de licença**</br>mshr_leavetypeid</br>*Sequência de caracteres* | Somente leitura | Id do tipo de licença. |
| **Descrição**</br>mshr_description</br>*Sequência de caracteres* | Somente leitura | Uma descrição do tipo de licença. |
| **Categoria**</br>mshr_category</br>*conjunto de opções mshr_LeaveTypeCategory* | Somente leitura | A categoria do tipo de licença. |
| **Código de motivo obrigatório**</br>mshr_isreasoncoderequired</br>*conjunto de opções mshr_NoYes* | Somente leitura | Define se um código de motivo é necessário para o tipo de licença. |
| **Unidade da licença**</br>mshr_leaveamountunit</br>*conjunto de opções mshr_LeaveAmountUnit* | Somente leitura | A unidade deste tipo de licença. |
| **Habilitar meio dia**</br>mshr_enablehalfdaydefinition</br>*conjunto de opções mshr_NoYes* | Define se o meio dia está habilitado para o tipo de licença. |
| **ID da área de dados**</br>mshr_dataareaid_id</br>*Sequência de caracteres* | Somente leitura | Especifica a entidade legal (empresa). |
| **Entidade de tipo de licença**</br>mshr_essleavetypeentityid</br>*GUID* | Gerado pelo sistema | Um valor GUID gerado pelo sistema para identificar exclusivamente o tipo de licença. |

## <a name="example-query"></a>Exemplo de consulta

**Solicitar**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleavetypeentities?$filter=mshr_leavetypeid eq 'PTO'
```

**Resposta**

```json
{
    "mshr_leavetypeid": "PTO",
    "mshr_description": "Paid time off",
    "mshr_category": 200000000,
    "mshr_isreasoncoderequired": 200000000,
    "mshr_leaveamountunit": 200000000,
    "mshr_enablehalfdaydefinition": 200000000,
    "mshr_dataareaid": "usmf",
    "mshr_essleavetypeentityid": "00000a6c-0000-0000-0000-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Consulte também

[Introdução à API de integração da folha de pagamento](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
