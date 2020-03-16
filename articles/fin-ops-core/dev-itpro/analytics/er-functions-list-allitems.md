---
title: Função de ER ALLITEMS
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ALLITEMS é usada.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 3aa226be8bc27817b4369b9e5b24faee8ea52b88
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042219"
---
# <a name="ALLITEMS">Função de ER ALLITEMS</a>

[!include [banner](../includes/banner.md)]

A função `ALLITEMS` é executada como uma seleção na memória e retorna um novo valor de *Lista de registros* simplificado como uma lista de registros que representa todos os itens correspondentes ao caminho especificado.

## <a name="syntax"></a>Sintaxe

```vb
ALLITEMS (path)
```

## <a name="arguments"></a>Argumentos

`path`: *Lista de registros*

O caminho válido de uma fonte de dados do tipo *Lista de registros*.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

A lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

O caminho deve ser definido como um caminho de fonte de dados válido de um elemento da fonte de dados do tipo *Lista de registros*. Os elementos de dados, como a cadeia de caracteres e a data do caminho, devem gerar um erro no construtor de expressões de relatório eletrônico (ER) no momento do design.

Não é recomendável usar esta função para fontes de dados transacionais que possam conter um grande volume de dados. Em vez dela, considere usar a função [ALLTEMSQUERY](er-functions-list-allitemsquery.md).

## <a name="example-1"></a>Exemplo 1

Se você inserir `SPLIT("abcdef" , 2)` como a fonte de dados **DS**, a expressão `COUNT( ALLITEMS (DS))` retornará **3**.

## <a name="example-2"></a>Exemplo 2

Se você inserir **Forn.** como a fonte de dados do tipo *Lista de registros* que se refere à tabela do aplicativo VendTable, a expressão `ALLITEMS (Vend.'<Relations'.ContactPerson)` retornará uma lista simplificada de registros que tem a estrutura da tabela **ContactPerson** e contém todas as pessoas de contato que podem ser acessadas usando a relação **ContactPerson.ContactForParty == VendTable.Party**, e isso está disponível para todos os fornecedores da tabela de fornecedores referenciada.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)
