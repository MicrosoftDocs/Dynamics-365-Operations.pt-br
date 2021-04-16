---
title: Recalcular os custos e valores segurados para grupos de ativos fixos
description: Este processo explica o processo para atualizar os custos de substituição e os valores segurados para ativos fixos.
author: ShylaThompson
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 3261
ms.assetid: b8876f83-8772-4f2a-b277-12724e2a0c44
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0509c0ea2fe6e4d04aeec451969a81eb33b1d19
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826290"
---
# <a name="recalculate-replacement-costs-and-insured-values-for-fixed-asset-groups"></a>Recalcular os custos e valores segurados para grupos de ativos fixos

[!include [banner](../includes/banner.md)]

Este processo explica o processo para atualizar os custos de substituição e os valores segurados para ativos fixos.

Periodicamente, você pode ser notificado que o custo para substituir ou segurar ativos fixos específicos foi alterado. Por exemplo, seu gerente pode informar que a inflação foi de 3 por cento no ano passado, então você terá de aumentar o custo de substituição em 3 por cento para todos os ativos fixos. 

Embora seja possível editar o custo de substituição e o valor segurado para ativos fixos individuais na página **Ativos fixos**, você pode usar a página **Atualizar custos de substituição e valores segurados** para atualizar esses valores para um grupo de ativos de uma só vez. Estas informações descrevem como atualizar os valores para grupos de ativos fixos ou para ativos específicos nos grupos.

## <a name="how-values-are-updated"></a>Como os valores são atualizados
Para recalcular custos de substituição e valores segurados para grupos de ativos fixos, você deve primeiramente especificar a porcentagem pela qual os custos de substituição e os valores segurados existentes serão alterados, executando em seguida a atualização periódica para recalcular os valores. Especifique a porcentagem nos campos **Fator de custo de substituição** e **Fator de valor segurado** na página **Grupos de ativos fixos**. Embora seja possível especificar esses fatores para o grupo de ativos fixos, ao usar a página **Atualizar custos de substituição e valores segurados**, você pode recalcular o custo de substituição e o valor segurado somente para ativos fixos específicos em um grupo. 

Ao usar a página **Atualizar custos de substituição e valores segurados** para recalcular o custo de substituição e o valor segurado para os ativos, as seguintes fórmulas são usadas:

-   \[(Fator de substituição de custo de um grupo de ativos/ 100) + 1\] \* O custo de substituição existente de um ativo
-   \[(Fator de valor segurado de um grupo de ativos/ 100) + 1\] \* O valor segurado existente de um ativo

> [!NOTE] 
> Ao usar o formulário **Atualizar custos de substituição e valores segurados**, tanto o custo de substituição quanto o valor segurado serão atualizados para os ativos selecionados. Não é possível especificar que apenas um valor seja atualizado. Para deixar um valor inalterado e atualizar o outro valor, insira 0 (zero) como fator na página **Grupos de ativos fixos**. Um fator igual a zero ou em branco faz com que o cálculo seja ignorado na atualização. O valor contábil e o valor líquido contábil de ativos fixos não são afetados pela atualização periódica. 

## <a name="how-to-use-a-date-to-select-which-items-to-update"></a>Como usar a data para selecionar quais itens devem ser atualizados
Por padrão, o processo de atualização atualiza os ativos selecionados que não foram atualizados na dia atual, mas que podem ter sido atualizados em dias anteriores. Por exemplo, &lt; data atual significa “antes de hoje”. Você pode alterar a data na página **Atualizar custos de substituição e valores segurados** clicando no botão **Selecionar**. Os critérios de data especificados são comparados com a data da última atualização periódica para o ativo (o campo **Última atualização periódica de valor/custo** na página **Ativos fixos** ). Toda vez que você atualizar com êxito o custo de substituição ou o valor segurado para um ativo fixo, o campo **Última atualização periódica de valor/custo** será atualizado com a data atual automaticamente. 

Exemplo 

Você atualizou o custo de substituição dos grupos de Veículos, Móveis de escritório e Edifícios em 5 por cento ontem e agora esses ativos são considerados como atualizados com exatidão. Para excluir esses ativos quando você atualizar todos os outros ativos fixos hoje, insira uma data no campo **Última atualização periódica de valor/custo** que seja anterior a ontem (&lt; data de ontem), pois a última atualização periódica para os grupos **Veículos**, **Móveis de escritório** e **Edifícios** ocorreu fora dos critérios de data inseridos.

## <a name="cumulative-effect-of-each-update"></a>Efeito cumulativo de cada atualização
Cada atualização tem um efeito cumulativo. Portanto, você deve planejar suas atualizações com cuidado. Por exemplo, se você aumentar todos os ativos em 3 por cento na terça e, em seguida, aumentar o dos móveis de escritório em 4 por cento na sexta, os móveis de escritório aumentarão em um total de 7,12 por cento.

## <a name="scenario"></a>Cenário
Seu gerente o notifica das seguintes alterações para ativos fixos:
-   Aumentar o custo de substituição de todos os ativos fixos, com exceção de computadores, em 3,25 por cento.
-   Aumentar o custo de substituição para todos os móveis de escritório em 1 por cento adicional.
-   Diminuir o custo de substituição e o calor segurado de todos os computadores em 10 por cento.

Você faz as seguintes alterações:
1.  Na página **Grupos de ativos fixos**, para todos os grupos de ativos fixos, com exceção dos grupos **Móveis de Escritório** e **Computadores**, digite 3,25 no campo **Fator de custo de substituição** e 0 no campo **Fator de valor segurado**.
2.  Para o grupo **Móveis de Escritório**, digite 4,25 no campo **Fator de custo de substituição** e 0 no campo **Fator de valor segurado**.
3.  Para o grupo **Computadores**, digite -10 no campo **Fator de custo de substituição** e -10 no campo **Fator de valor segurado**.
4.  Na página **Atualizar custos de substituição e valores segurados**, clique em **OK** para executar o recálculo para todos os ativos fixos.

No dia seguinte, seu gerente informa que os computadores diminuíram em 8 por cento, em vez de 10 por cento, então você terá que corrigir os custos de substituição e os valores segurados. Para corrigir o erro, você pode usar um dos dois métodos:
-   Altere manualmente os campos **Valor segurado** e **Custo de substituição** na página **Ativos fixos** para cada ativo fixo no grupo de ativos fixos **Computadores**. Calcule e insira manualmente os valores como se você tivesse diminuído o valor original em 8 por cento. Usando este método, você não deve usar a página **Atualizar custos de substituição e valores segurados**.
-   Insira os fatores de custo de substituição e de valor segurado para o grupo **Computadores** nos campos **Fator de custo de substituição** e **Fator de valor segurado** na página **Grupos de ativos fixos**. Isso irá redefinir os ativos de volta para o valor original (antes da redução de 10 por cento) e aplicará a redução de 8 por cento ao valor original. Em seguida, use a página **Atualizar custos de substituição e valores segurados** para recalcular os valores, dependendo dos fatores inseridos.

> [!NOTE]  
> Não é possível reverter o fator -10 ao inserir um fator de 10 positivo (ou um fator de 2, a diferença entre -10 e -8), porque as valores não serão calculados como você tem intenção. 







[!INCLUDE[footer-include](../../includes/footer-banner.md)]