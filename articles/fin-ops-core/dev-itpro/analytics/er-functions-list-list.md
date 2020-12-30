---
title: Função de ER LIST
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) LIST é usada.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c7f8e701ec2836206d2299abba5e5b8542b4cf92
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683078"
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
