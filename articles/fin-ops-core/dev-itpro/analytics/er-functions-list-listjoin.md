---
title: Função LISTJOIN ER
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) LISTJOIN é usada.
author: kfend
ms.date: 04/01/2020
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: ec8a5985277de8036ec8ad51b947a8bab098a1c3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291194"
---
# <a name="listjoin-er-function"></a>Função LISTJOIN ER

[!include [banner](../includes/banner.md)]

A função `LISTJOIN` retorna um valor de *Lista de registros* que representa uma nova lista associada de registros criada dos argumentos especificados.

## <a name="syntax"></a>Sintaxe

```vb
LISTJOIN (list 1 [, list 2, …, list N])
```

## <a name="arguments"></a>Argumentos

`list 1`: *Lista de registros*

Uma referência a uma fonte de dados do tipo *Lista de registros*. Esse argumento é obrigatório.

`list N`: *Lista de registros*

Uma referência a uma fonte de dados do tipo *Lista de registros*. Esses argumentos adicionais são opcionais.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

A lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

A estrutura da lista criada contém somente os campos presentes na estrutura de cada lista de registro mencionada nos argumentos.

## <a name="example"></a>Exemplo

Você insere a fonte de dados **Registro 1** do tipo `Container`. Essa fonte de dados contém os seguintes campos aninhados do tipo `Calculated field`:

- **Código**: este campo contém uma expressão que retorna um valor do tipo `String`.
- **Valor**: este campo contém uma expressão que retorna um valor do tipo `Real`.

Em seguida, você insere a fonte de dados **Registro 2** do tipo `Container`. Essa fonte de dados contém os seguintes campos aninhados do tipo `Calculated field`:

- **Valor**: este campo contém uma expressão que retorna um valor do tipo `Real`.
- **IsValid**: este campo contém uma expressão que retorna um valor do tipo `Boolean`.

![Página de designer de mapeamento de modelo de ER.](./media/er-functions-list-listjoin-image1.gif)

Nesse caso, a expressão `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` retorna uma nova lista que contém dois registros.

![Página de designer de mapeamento de modelo de ER com dois registros.](./media/er-functions-list-listjoin-image2.gif)

A estrutura dessa lista consiste em um único campo **Valor** do tipo `Real`, pois esse campo é o único apresentado em todos os argumentos da função chamada.

![Campo Valor da página de designer de mapeamento de modelo de ER.](./media/er-functions-list-listjoin-image3.gif)

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)

[Depurar fontes de dados de um formato de relatório eletrônico executado para analisar o fluxo de dados e a transformação](er-debug-data-sources.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
