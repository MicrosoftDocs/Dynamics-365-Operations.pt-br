---
title: Função LISTJOIN ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) LISTJOIN é usada.
author: NickSelin
manager: kfend
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3b5b82917e3083b5ffe4546a6a15fd14938383a
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "3249026"
---
# <a name=""></a><a name="LISTJOIN">Função LISTJOIN ER</a>

[!include [banner](../includes/banner.md)]

A função `LISTJOIN` retorna um valor de *Lista de registros* que representa uma nova lista associada de registros criada dos argumentos especificados.

## <a name="syntax"></a>Sintaxe

```vb
LIST (list 1 [, list 2, …, list N])
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

Nesse caso, a expressão `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` retorna uma nova lista que contém dois registros. A estrutura dessa lista consiste em um único campo **Valor** do tipo `Real`, pois esse campo é o único apresentado em todos os argumentos da função chamada.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)
