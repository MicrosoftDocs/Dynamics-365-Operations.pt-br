---
title: Função de ER REPEAT
description: Este artigo fornece informações sobre como usar a função de relatório eletrônico (ER) REPEAT.
author: NickSelin
ms.date: 08/01/2022
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-06-01
ms.dyn365.ops.version: AX 10.0.29
ms.openlocfilehash: c56139a3c63b03f907b1dcbf4365990d2a13c35a
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220682"
---
# <a name="repeat-er-function"></a>Função de ER REPEAT

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

A função `REPEAT` cria um registro que contém o campo que tem um valor que corresponde à entrada especificada. Em seguida, retorna uma nova *lista de registros* de um registro repetido um determinado número de vezes.

## <a name="syntax"></a>Sintaxe

```vb
REPEAT (item, number)
```

## <a name="arguments"></a>Argumentos

`item`: Qualquer [tipo de dados primitivo](er-formula-supported-data-types-primitive.md) ou [composto](er-formula-supported-data-types-composite.md)

O valor a ser repetido.

`number`: *Inteiro*

Número de repetições.

## <a name="return-values"></a>Valores de retorno

*Registrar lista*

A lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

A lista de registros repetidos retornada expõe os seguintes campos:

- Valor especificado (campo `Item`)
- Índice do registro atual (campo `Number`)

> [!NOTE]
> Como o número de uma base é usado para essa função, o campo `Number` apresenta o valor **1** para o primeiro registro da lista resultante.

Você pode usar esta função para multiplicar dados existentes para que possa fazer testes de desempenho e de volume de soluções de [relatório eletrônico (ER)](general-electronic-reporting.md) usando a [Regression Suite Automation Tool (RSAT)](../perf-test/rsat/rsat-overview.md).

## <a name="example"></a>Exemplo

Você deseja gerar um documento no formato XML que deve conter quantos elementos XML `Party` forem especificados em um campo de entrada de dados na caixa de diálogo no runtime, antes que a execução de um formato ER seja iniciada.

A ilustração a seguir mostra o formato [ER](er-overview-components.md#format-component). Nesse formato, o único elemento XML `Party` é adicionado para expor as propriedades de um único participante.

<a href="./media/er-repeat-function-1.png"><img src="./media/er-repeat-function-1.png" alt="Format structure on the Format tab of the Format designer page." class="alignnone size-full" width="929" height="548" /></a>

A próxima ilustração mostra as seguintes fontes de dados configuradas:

- A fonte de dados `Party` que representa um único participante. O campo `Party.Value` é usado para expor um único valor de texto.
- A fonte de dados `NumberOfRepeats` [usada](er-user-input-parameter-data-sources.md) para oferecer um campo de entrada de dados na caixa de diálogo no runtime, de forma que você possa especificar o número de participantes que devem ser inseridos no documento gerado.
- A fonte de dados `Party2` que repete o registro `Party` o número de vezes que você especificou na fonte de dados `NumberOfRepeats`.

<a href="./media/er-repeat-function-2.png"><img src="./media/er-repeat-function-2.png" alt="Configured data sources on the Mapping tab of the Format designer page." class="alignnone size-full" width="1044" height="411" /></a>

A ilustração a seguir mostra a associação de dados do formato ER editável criado para gerar saída no formato XML. Esta saída apresenta participantes individuais como nós enumerados.

<a href="./media/er-repeat-function-3.png"><img src="./media/er-repeat-function-3.png" alt="Configured data bindings on the Mapping tab of the Format designer page." class="alignnone size-full" width="1051" height="417" /></a>

A ilustração a seguir mostra o resultado quando o formato projetado é executado e o valor da fonte de dados `NumberOfRepeats` é especificado como **5**.

<a href="./media/er-repeat-function-4.png"><img src="./media/er-repeat-function-4.png" alt="Result of running the format on a new web browser tab." class="alignnone wp-image-290711 size-full" width="400" height="380" /></a>

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
