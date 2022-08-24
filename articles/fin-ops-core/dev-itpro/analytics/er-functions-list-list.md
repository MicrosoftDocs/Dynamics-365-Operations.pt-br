---
title: Função de ER LIST
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) LIST é usada.
author: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 7a5f27baa248ec84c75725cf32a1f482841424c2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277622"
---
# <a name="list-er-function"></a>Função de ER LIST

[!include [banner](../includes/banner.md)]

A função `LIST` retorna um valor de *Lista de registros* que consiste em uma nova lista de registros criada a partir dos argumentos especificados.

## <a name="syntax"></a>Sintaxe

```vb
LIST (record 1 [, record 2, …, record N])
```

## <a name="arguments"></a>Argumentos

`record 1`: *Contêiner (registro)*

Uma referência a uma fonte de dados do tipo *Registro*. Esse argumento é obrigatório.

`record N`: *Contêiner (registro)*

Uma referência a uma fonte de dados do tipo *Registro*. Esses argumentos adicionais são opcionais.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

A lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

A estrutura da lista criada contém somente os campos apresentados na estrutura de cada registro mencionado nos argumentos.

## <a name="example"></a>Exemplo

Você insere a fonte de dados **Registro 1** do tipo *Contêiner*. Essa fonte de dados contém os seguintes campos aninhados do tipo *Campo calculado*:

- **Código:** este campo contém uma expressão que retorna um valor do tipo *Cadeia de caracteres*.
- **Valor:** este campo contém uma expressão que retorna um valor do tipo *Real*.

Em seguida, você insere a fonte de dados **Registro 2** do tipo *Contêiner*. Essa fonte de dados contém os seguintes campos aninhados do tipo *Campo calculado*:

- **Valor:** este campo contém uma expressão que retorna um valor do tipo *Real*.
- **IsValid:** este campo contém uma expressão que retorna um valor do tipo *Booliano*.

Nesse caso, a expressão `LIST('Record 1', 'Record 2')` retorna uma nova lista que contém dois registros. A estrutura dessa lista consiste em um único campo **Valor** do tipo *Real*, pois esse campo é o único apresentado em todos os argumentos da função chamada.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
