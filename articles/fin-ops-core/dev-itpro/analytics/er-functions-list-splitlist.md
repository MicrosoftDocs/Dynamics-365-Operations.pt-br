---
title: Função de ER SPLITLIST
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) SPLITLIST é usada.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: af8c413726ca8d9f92eff18807e7fa9002fc9d37
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559129"
---
# <a name="splitlist-er-function"></a>Função de ER SPLITLIST

[!include [banner](../includes/banner.md)]

A função `SPLITLIST` divide a lista especificada em sublistas (ou lotes) e cada uma delas contém o número de registros especificado. Em seguida, ela retorna o resultado como um novo valor de *Lista de registros* que consiste nos lotes.

## <a name="syntax"></a>Sintaxe

```vb
SPLITLIST (list, number)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

O caminho válido de uma fonte de dados do tipo *Lista de registros*.

`number`: *Inteiro*

O número máximo de registros por lote.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

A lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

A lista de lotes retornada contém os seguintes elementos:

 - **Valor:** *Lista*

    A lista de registros que pertencem ao lote atual.

- **BatchNumber:** *Inteiro*

    O número do lote atual na lista retornada.

## <a name="example"></a>Exemplo

Na ilustração a seguir, uma fonte de dados **Linhas** é criada como uma lista de registros com três registros. Esta lista é dividida em lotes, cada um contendo até dois registros.

<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

A ilustração a seguir mostra o formato de layout criado. Nesse formato de layout, as associações à fonte de dados de **Linhas** são criados para gerar saída no formato XML. Esta saída apresenta nós individuais para cada lote e os registros existentes nele.

<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>

A ilustração a seguir mostra o formato o resultado quando o formato criado é executado.

<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]