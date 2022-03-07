---
title: Função de ER SPLITLISTBYLIMIT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) SPLITLISTBYLIMIT é usada.
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 52351c131480119ce9fb98a75307ebf6026cb12b9977e8b4236d3a24ef6a140e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744425"
---
# <a name="splitlistbylimit-er-function"></a>Função de ER SPLITLISTBYLIMIT

[!include [banner](../includes/banner.md)]

A função `SPLITLISTBYLIMIT` divide a lista especificada em uma nova lista de sublistas (lotes). O número de registros em cada lote é calculado dinamicamente. Em seguida, a função retorna o resultado como um novo valor de *Lista de registros* que consiste nos lotes.

## <a name="syntax"></a>Sintaxe

```vb
SPLITLISTBYLIMIT (list, limit value, limit source)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

O caminho válido de uma fonte de dados do tipo *Lista de registros*.

`limit value`: *Inteiro* ou *Real*

O valor máximo do limite usado para dividir a lista original em lotes.

`limit source`: *Campo*

O caminho válido de um campo do tipo *Inteiro* ou *Real* na lista especificada. O valor desse campo define a etapa em que a soma total é aumentada.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

A lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

A lista de lotes retornada contém os seguintes elementos:

- **Valor**: *Lista*

    A lista de registros que pertencem ao lote atual.

- **BatchNumber**: *Inteiro*

    O número do lote atual na lista retornada.

O limite não é aplicado a um único item da lista original, se a fonte do limite exceder o limite definido.

## <a name="example"></a>Exemplo

A ilustração a seguir mostra um formato de relatório eletrônico (ER).

<a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="Format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a>

A ilustração a seguir mostra as fontes de dados que são usadas para o formato.

<a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="Data sources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a>

A ilustração a seguir mostra o resultado quando o formato é executado. Nesse caso, a saída é uma lista simples de itens de mercadoria.

<a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="Output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a>

Nas ilustrações a seguir, o mesmo formato foi ajustado, de forma que apresente a lista de itens de mercadoria em lotes caso um lote único precise incluir mercadorias e o peso total não exceda um limite de 9.

<a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="Adjusted format" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a>

<a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="Data sources for the adjusted format" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a>

A ilustração a seguir mostra o resultado quando o formato ajustado é executado.

<a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="Output of the adjusted format" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a>

> [!NOTE] 
> O limite não será aplicado ao último item da lista original porque o valor (**11**) da fonte de limite (**peso**) excede o limite definido (**9**). Para ignorar as sublistas durante a geração de relatórios, use a função `WHERE` ou a expressão **Habilitada** do elemento de formato correspondente, conforme necessário.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]