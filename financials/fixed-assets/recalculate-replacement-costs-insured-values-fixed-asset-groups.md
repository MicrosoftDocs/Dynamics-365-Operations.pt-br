---
title: Recalcular os custos e valores segurados para grupos de ativos fixos
description: "Este processo explica o processo para atualizar os custos de substituição e os valores segurados para ativos fixos."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3261
ms.assetid: b8876f83-8772-4f2a-b277-12724e2a0c44
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: c67bbc5be31d337c5247851eba4ec00705451aa1
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="recalculate-replacement-costs-and-insured-values-for-fixed-asset-groups"></a>Recalcular os custos e valores segurados para grupos de ativos fixos

[!include[banner](../includes/banner.md)]


Este processo explica o processo para atualizar os custos de substituição e os valores segurados para ativos fixos.

Periodicamente, você pode ser notificado que o custo para substituir ou segurar ativos fixos específicos foi alterado. Por exemplo, seu gerente pode informar que a inflação foi de 3 por cento no ano passado, então você terá de aumentar o custo de substituição em 3 por cento para todos os ativos fixos. 

Embora seja possível editar o custo de substituição e o valor segurado para ativos fixos individuais no formulário Ativos fixos, você pode usar o formulário Atualizar custos de substituição e valores segurados para atualizar esses valores para um grupo inteiro de ativos de uma vez. Estas informações descrevem como atualizar os valores para grupos de ativos fixos ou para ativos específicos nos grupos.

## <a name="how-values-are-updated"></a>Como os valores são atualizados
Para recalcular custos de substituição e valores segurados para grupos de ativos fixos, você deve primeiramente especificar a porcentagem pela qual os custos de substituição e os valores segurados existentes serão alterados, executando em seguida a atualização periódica para recalcular os valores. Especifique a porcentagem nos campos Fator de custo de substituição e Fator de valor segurado no formulário Grupos de ativos fixos. Embora seja possível especificar esses fatores para grupo inteiro de ativos fixos, ao usar o formulário Atualizar custos de substituição e valores segurados, você pode calcular novamente o custo de substituição e o valor segurado somente para ativos fixos específicos em um grupo. 

Ao usar o formulário Atualizar custos de substituição e valores segurados para recalcular o custo de substituição e o valor segurado para os ativos, as seguintes fórmulas são usadas:

-   \[(Fator de substituição de custo de um grupo de ativos/ 100) + 1\] \* O custo de substituição existente de um ativo
-   \[(Fator de valor segurado de um grupo de ativos/ 100) + 1\] \* O valor segurado existente de um ativo

> [!NOTE] 
> Quando você usar o formulário Atualizar custos de substituição e valores segurados, tanto o custo de substituição quanto o valor segurado serão atualizados para os ativos selecionados; não é possível especificar que apenas um valor será atualizado. Para deixar um valor inalterado e atualizar o outro valor, insira 0 (zero) como fator no formulário Grupos de ativos fixos. Um fator igual a zero ou em branco faz com que o cálculo seja ignorado na atualização. O valor contábil e o valor líquido contábil de ativos fixos não são afetados pela atualização periódica. 

## <a name="how-to-use-a-date-to-select-which-items-to-update"></a>Como usar a data para selecionar quais itens devem ser atualizados
Por padrão, o processo de atualização atualiza os ativos selecionados que não foram atualizados na dia atual, mas que podem ter sido atualizados em dias anteriores. Por exemplo, &lt; data atual significa “antes de hoje”. Você pode alterar a data em Atualizar custos de substituição e o formulário de valores segurados clicando no botão Selecionar. O critérios de data especificado é comparado a data da última atualização periódica para o ativo (o campo Última atualização periódica de valor/custo no formulário Ativos fixos). Cada vez que você atualiza com êxito o custo de substituição ou o valor segurado para um ativo fixo, o campo Última atualização periódica de valor/custo é automaticamente atualizado com a data atual. 

Exemplo 

Você atualizou o custo de substituição dos grupos de Veículos, Móveis de escritório e Edifícios em 5 por cento ontem e agora esses ativos são considerados como atualizados com exatidão. Para excluir esses ativos ao atualizar todos os outros ativos fixos hoje, você insere uma data no campo Última atualização periódica de valor/custo, que é anterior a ontem (&lt; data de ontem) porque a última atualização periódica para os grupos Veículos, Móveis de Escritório e Edifícios ocorreu fora do critério de data inserido.

## <a name="cumulative-effect-of-each-update"></a>Efeito cumulativo de cada atualização
Cada atualização tem um efeito cumulativo. Portanto, você deve planejar suas atualizações com cuidado. Por exemplo, se você aumentar todos os ativos em 3 por cento na terça e, em seguida, aumentar o dos móveis de escritório em 4 por cento na sexta, os móveis de escritório aumentarão em um total de 7,12 por cento.

## <a name="scenario"></a>Cenário
Seu gerente o notifica das seguintes alterações para ativos fixos:
-   Aumentar o custo de substituição de todos os ativos fixos, com exceção de computadores, em 3,25 por cento.
-   Aumentar o custo de substituição para todos os móveis de escritório em 1 por cento adicional.
-   Diminuir o custo de substituição e o calor segurado de todos os computadores em 10 por cento.

Você faz as seguintes alterações:
1.  No formulário Grupos de ativos fixos, para todos os grupos de ativos fixos, com exceção do grupo Móveis de Escritório e o grupo Computadores, digite 3,25 no campo Fator de custo de substituição e 0 no campo Fator de valor segurado.
2.  Para o grupo Móveis de Escritório, digite 4,25 no campo Fator de custo de substituição e 0 no campo Fator de valor segurado.
3.  Para o grupo Computadores, digite 10 no campo Fator de custo de substituição e -10 no campo Fator de valor segurado.
4.  No formulário Atualizar custos de substituição e valores segurados, clique em OK para executar o recálculo para todos os ativos fixos.

No dia seguinte, seu gerente informa que os computadores diminuíram em 8 por cento, em vez de 10 por cento, então você terá que corrigir os custos de substituição e os valores segurados. Para corrigir o erro, você pode usar um dos dois métodos:
-   Altere manualmente os campos Valor segurado e Custo de substituição no formulário Ativos fixos para cada ativo fixo no grupo de ativos fixos de Computadores. Calcule e insira manualmente os valores como se você tivesse diminuído o valor original em 8 por cento. Usando este método, você não deverá usar o formulário Atualizar custos de substituição e valores segurados.
-   Insira os fatores de custo de substituição e de valor segurado para o grupo Computadores nos campos Fator de custo de substituição e Fator de valor segurado no formulário Grupos de ativos fixos. Isso irá redefinir os ativos de volta para o valor original (antes da redução de 10 por cento) e aplicará a redução de 8 por cento ao valor original. Em seguida, use o formulário atualizar custos de substituição e valores segurados para recalcular os valores, dependendo dos fatores inseridos.

> [!NOTE]  
> Não é possível reverter o fator -10 ao inserir um fator de 10 positivo (ou um fator de 2, a diferença entre -10 e -8), porque as valores não serão calculados como você tem intenção. 






