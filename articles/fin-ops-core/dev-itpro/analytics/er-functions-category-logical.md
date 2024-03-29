---
title: Lista de funções ER na categoria lógica
description: Este artigo fornece informações sobre as funções lógicas que são compatíveis no relatório eletrônico (ER).
author: kfend
ms.date: 02/11/2021
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 1d011968d9cfa4125e7283ca36c3558e3e79b93a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291284"
---
# <a name="list-of-er-functions-in-the-logical-category"></a>Lista de funções ER na categoria lógica

[!include [banner](../includes/banner.md)]

As funções lógicas relatório eletrônico (ER) podem ser usadas para trabalhar com valores lógicos a fim de executar mais de uma comparação em uma única expressão ou testar várias condições. Este artigo fornece um resumo dessas funções.

## <a name="list-of-supported-functions"></a>Lista de funções com suporte

| Função | Descrição |
|----------|-------------|
| [E](er-functions-logical-and.md)                       | Essa função retorna um valor *Booliano* de **TRUE** se todas as condições especificadas forem verdadeiras. Caso contrário, ela retorna um valor *Booliano* de **FALSE**. |
| [Caixa](er-functions-logical-case.md)                     | Essa função avalia o valor da expressão especificada em relação às opções alternativas especificadas e retorna o resultado da primeira opção igual ao valor dessa expressão. Caso contrário, ela retorna um resultado padrão opcional, se um resultado padrão for especificado como o último argumento da função chamada não precedida por uma opção. O valor retornado pode ser um valor de qualquer um dos tipos de dados com suporte. |
| [Contém](er-functions-logical-contains.md)             | Esta função determina se a entrada especificada contém o texto especificado. Ele retorna um valor *Booliano* **TRUE** se a entrada especificada contém o texto especificado. Caso contrário, ela retorna um valor *Booliano* de **FALSE**. |
| [EndsWith](er-functions-logical-endswith.md)             | Esta função determina se a entrada especificada termina com o texto especificado. Ele retorna um valor *Booliano* **TRUE** se a entrada especificada termina com o texto especificado. Caso contrário, ela retorna um valor *Booliano* de **FALSE**. |
| [Se](er-functions-logical-if.md)                         | Essa função retorna o primeiro valor especificado se a condição especificada for atendida. Caso contrário, ele retorna o segundo valor especificado. O valor retornado pode ser um valor de qualquer um dos tipos de dados com suporte. |
| [Não](er-functions-logical-not.md)                       | Essa função retorna o valor lógico revertido da condição especificada como um valor *Booliano*. |
| [Or](er-functions-logical-or.md)                         | Essa função retorna um valor *Booliano* de **FALSE** se todas as condições especificadas forem falsas. Se qualquer condição especificada for verdade, a função retorna um valor *Booliano* como **TRUE**. |
| [StartsWith](er-functions-logical-startswith.md)         | Esta função determina se a entrada especificada começa com o texto especificado. Ele retorna um valor *Booliano* **TRUE** se a entrada especificada começa com o texto especificado. Caso contrário, ela retorna um valor *Booliano* de **FALSE**. |
| [ValueIn](er-functions-logical-valuein.md)               | Essa função determina se a entrada especificada corresponde a algum valor de um item especificado na lista especificada. Ela retorna um valor *Booliano* de **TRUE** se a entrada especificada corresponder ao resultado da execução da expressão especificada para pelo menos um registro da lista especificada. Caso contrário, ela retorna um valor *Booliano* de **FALSE**. |
| [ValueInLarge](er-functions-logical-valueinlarge.md)     | Esta função determina se a entrada especificada do tipo *Int64* ou *Inteiro* corresponde a algum valor de um item especificado na lista especificada. Ela retorna um valor *Booliano* de **TRUE** se a entrada especificada corresponder ao resultado da execução da expressão especificada para pelo menos um registro da lista especificada. Caso contrário, ela retorna um valor *Booliano* de **FALSE**. |


## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do Relatório Eletrônico](general-electronic-reporting.md)

[Designer de fórmulas no Relatório eletrônico](general-electronic-reporting-formula-designer.md)

[Linguagem da fórmula de relatório eletrônico](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
