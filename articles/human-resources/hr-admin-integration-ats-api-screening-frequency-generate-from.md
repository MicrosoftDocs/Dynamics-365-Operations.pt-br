---
title: Geração de frequência de triagem de
description: Este tópico descreve o conjunto de opções de Geração de frequência de triagem de para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: ae5ad3e556f40cedd385d8aadded9ef76447a98b
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054083"
---
# <a name="screening-frequency-generate-from"></a>Geração de frequência de triagem de

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve o conjunto de opções de Geração de frequência de triagem de para o Dynamics 365 Human Resources.

Nome físico: mshr_hcmfrequencygeneratefrom

Essa enumeração fornece o conjunto de opções de valores para determinar a data de início do cálculo para a próxima triagem necessária.

| Valor | Etiqueta | Descrição |
| --- | --- | --- |
| 200000000 Não selecionado | Nenhum valor foi selecionado. |
| 200000001 Data de conclusão | O cálculo é feito a partir da última data de triagem concluída. |
| 200000002 A data é obrigatória | O cálculo é feito a partir da última data de triagem necessária. |

## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Exemplo de consulta de candidato a ser contratado](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]