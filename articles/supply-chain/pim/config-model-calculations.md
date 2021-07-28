---
title: Cálculo de modelo de configuração de produto
description: Este tópico descreve como criar cálculos para atributos em um modelo de configuração de produto
author: t-benebo
ms.date: 03/18/2021
ms.topic: article
ms.search.form: PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-03-18
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f0806a5b36b04e77a5a6d10f3c2eb3d7ba680e75
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356407"
---
# <a name="product-configuration-model-calculations"></a>Cálculo de modelo de configuração de produto

[!include [banner](../includes/banner.md)]

Este tópico descreve como criar cálculos para atributos em um modelo de configuração de produto.

## <a name="prerequisites"></a>Pré-requisitos

Os cálculos são usados em um modelo de configuração de produto para calcular os valores da configuração de um produto. Antes de começar a configurar cálculos, o modelo de configuração de produto relacionado deve existir. Para obter uma visão geral do processo de configuração dos modelos de configuração e das tarefas relacionadas, consulte [Configurar um modelo de configuração de produto](set-up-maintain-product-configuration-model.md).

## <a name="create-a-calculation"></a>Criar um cálculo

Um cálculo consiste em uma expressão e em um atributo de destino. Para obter mais informações, consulte [Perguntas frequentes sobre cálculos para modelos de configuração de produto](calculate-product-configuration-models.md).

Para criar um cálculo para um modelo de produto existente, siga estas etapas.

1. Vá para **Gerenciamento de informações sobre produtos \> Comum \> Modelos de configuração do produto**.
1. Abra um modelo de configuração de produto e selecione **Editar**.
1. Na guia rápida **Cálculos**, selecione **Adicionar** para adicionar um cálculo e defina os seguintes campos:

    - **Nome** – insira um nome para o cálculo.
    - **Descrição** – insira uma descrição do cálculo.
    - **Atributo de destino** – selecione o atributo para o qual você está fazendo o cálculo.

1. Selecione **Editar expressão**.
1. Na caixa de diálogo **Inserir um cálculo**, adicione os atributos, operadores e valores necessários à expressão. Para obter mais informações sobre como trabalhar com esses elementos, consulte [Restrições de expressão e restrições de tabela nos modelos de configuração do produto](expression-constraints-table-constraints-product-configuration-models.md).
1. Quando a expressão estiver pronta, selecione **OK**.

## <a name="calculation-examples"></a>Exemplos de cálculo

Esta seção fornece alguns exemplos que mostram como os cálculos funcionam.

### <a name="example-1"></a>Exemplo 1

O atributo de destino é booliano e o cálculo usa a seguinte expressão condicional:

`If[(decimalAttribute1 / decimalAttribute2) < 1, True, False]`

This eEssa expressão retornará um valor *Verdadeiro* para o atributo de destino se `decimalAttribute2` for maior ou igual a `decimalAttribute1`. Caso contrário, ela retorna um valor *Falso*.

### <a name="example-2"></a>Exemplo 2

Este exemplo usa o atributo de texto `textFixedList` como o atributo de destino. Este atributo contém a lista fixa a seguir.

| Alíquota | Valor do agente de resolução |
|---|---|
| A | 1a |
| E | 2b |
| E | 2c |

A captura de tela a seguir mostra como as configurações desse atributo podem aparecer no seu sistema.

![Configurações de tipo de atributo, por exemplo 2.](media/model-calculations-example2.png "Configurações de tipo de atributo, por exemplo 2")

O atributo é usado na seguinte instrução condicional:

`If[integerAttribute < 150, 0, 2]`

Se `integerAttribute` for menor que 150, esta instrução retornará o valor de texto do primeiro registro na lista fixa, *A*. Caso contrário, ele retorna o valor de texto do terceiro registro na lista fixa, *C*.

> [!NOTE]
> A lista fixa é equivalente a uma enumeração baseada em zero (enum) e seus valores são acessados pelo valor inteiro apropriado. Portanto, o primeiro valor de lista fixo (*A*) é correspondido como *0*, o segundo valor (*B*) corresponde a *1* e o terceiro valor (*C*) corresponde a *2*.

### <a name="example-3"></a>Exemplo 3

Este exemplo usa o atributo de texto `textFixedList` do exemplo anterior. Ele também usa outro atributo de texto, `textAttribute` que contém a lista fixa a seguir.

| Alíquota | Valor do agente de resolução |
|---|---|
| AA | 1aa |
| BB | 2bb |

A captura de tela a seguir mostra como as configurações desse atributo podem aparecer no seu sistema.

![Configurações de tipo de atributo, por exemplo 3.](media/model-calculations-example3.png "Configurações de tipo de atributo, por exemplo 3")

O valor do atributo `textFixedList` é calculado usando a seguinte instrução condicional:

`If[textAttribute == "1aa", 0, 2]`

Se o valor `textAttribute` tiver um valor de resolução igual a *1aa*, esta expressão retornará o valor de texto do primeiro registro na lista fixa `textFixedList`, *A*. Caso contrário, ele retorna o valor de texto do terceiro n lista fixa `textFixedList`, *C*.

> [!NOTE]
> - A instrução condicional deve usar o valor de resolução do atributo.
> - Somente atributos de texto de lista fixa podem ser usados em cálculos.

## <a name="see-also"></a>Consulte também

- [Perguntas frequentes sobre cálculos para modelos de configuração de produto](calculate-product-configuration-models.md)
- [Adicionar uma restrição de expressão para um modelo de configuração de produto](tasks/add-expression-constraint-product-configuration-model.md)
- [Visão geral dos modelos de configuração de produto](product-configuration-models.md)
