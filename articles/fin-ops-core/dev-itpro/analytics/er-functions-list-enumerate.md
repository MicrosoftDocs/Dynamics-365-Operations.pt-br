---
title: Função de ER ENUMERATE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ENUMERATE é usada.
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
ms.openlocfilehash: 34ebbec94644276be4ef9beb1c77638606dd37a0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679453"
---
# <a name="enumerate-er-function"></a>Função de ER ENUMERATE

[!include [banner](../includes/banner.md)]

A função `ENUMERATE` retorna um novo valor de *Lista de registros* que consiste em registros enumerados da lista especificada.

## <a name="syntax"></a>Sintaxe

```vb
ENUMERATE (list)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

O caminho válido de uma fonte de dados do tipo *Lista de registros*.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

A lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

A lista de registros enumerados que é retornada expõe os seguintes elementos adicionais:

- O registro de campos (componente **Valor**)
- O índice do registro atual (componente **Número**)

## <a name="example"></a>Exemplo

Na ilustração a seguir, uma fonte de dados **Enumerada** é criada como uma lista enumerada de registros do fornecedor da fonte de dados **Fornecedores** que se refere à tabela VendTable.

<a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a>

A ilustração a seguir mostra o formato de relatório eletrônico (ER). Nesse formato, as associações são criadas para gerar saída no formato XML. Esta saída apresenta fornecedores individuais como nós enumerados.

<a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a>

A ilustração a seguir mostra o formato o resultado quando o formato criado é executado.

<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a>

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)
