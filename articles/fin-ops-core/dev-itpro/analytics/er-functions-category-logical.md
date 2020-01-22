---
title: Lista de funções ER na categoria lógica
description: Este tópico fornece informações sobre as funções lógicas que são compatíveis no relatório eletrônico (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 408b3c5ec37b24e0ccf6e368012a936701eedf0f
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916628"
---
# <a name="list-of-er-functions-in-the-logical-category"></a>Lista de funções ER na categoria lógica

[!include [banner](../includes/banner.md)]

As funções lógicas relatório eletrônico (ER) podem ser usadas para trabalhar com valores lógicos a fim de executar mais de uma comparação em uma única expressão ou testar várias condições. Este tópico fornece um resumo dessas funções.

## <a name="list-of-supported-functions"></a>Lista de funções com suporte

| Função | Descrição |
|----------|-------------|
| [E](er-functions-logical-and.md)                       | Essa função retorna um valor *Booliano* de **TRUE** se todas as condições especificadas forem verdadeiras. Caso contrário, ela retorna um valor *Booliano* de **FALSE**. |
| [Caixa](er-functions-logical-case.md)                     | Essa função avalia o valor da expressão especificada em relação às opções alternativas especificadas e retorna o resultado da primeira opção igual ao valor dessa expressão. Caso contrário, ela retorna um resultado padrão opcional, se um resultado padrão for especificado como o último argumento da função chamada não precedida por uma opção. O valor retornado pode ser um valor de qualquer um dos tipos de dados com suporte. |
| [Se](er-functions-logical-if.md)                         | Essa função retorna o primeiro valor especificado se a condição especificada for atendida. Caso contrário, ele retorna o segundo valor especificado. O valor retornado pode ser um valor de qualquer um dos tipos de dados com suporte. |
| [Não](er-functions-logical-not.md)                       | Essa função retorna o valor lógico revertido da condição especificada como um valor *Booliano*. |
| [Or](er-functions-logical-or.md)                         | Essa função retorna um valor *Booliano* de **FALSE** se todas as condições especificadas forem falsas. Se qualquer condição especificada for verdade, a função retorna um valor *Booliano* como **TRUE**. |
| [ValueIn](er-functions-logical-valuein.md)               | Essa função determina se a entrada especificada corresponde a algum valor de um item especificado na lista especificada. Ela retorna um valor *Booliano* de **TRUE** se a entrada especificada corresponder ao resultado da execução da expressão especificada para pelo menos um registro da lista especificada. Caso contrário, ela retorna um valor *Booliano* de **FALSE**. |

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do Relatório Eletrônico](general-electronic-reporting.md)

[Designer de fórmulas no Relatório eletrônico](general-electronic-reporting-formula-designer.md)

[Linguagem da fórmula de relatório eletrônico](er-formula-language.md)
