---
title: Função de ER CONVERTCURRENCY
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) CONVERTCURRENCY é usada.
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: dc71ccedcdfc8a3dc9d7e087d29467bd3bbe72c3c5588872dbeaf3aa1dd35d2b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738591"
---
# <a name="convertcurrency-er-function"></a>Função de ER CONVERTCURRENCY

[!include [banner](../includes/banner.md)]

A função `CONVERTCURRENCY` retorna um valor *Real* que representa o resultado da conversão do valor monetário especificado da moeda de origem especificada para a moeda de destino especificada usando as configurações da empresa especificada na data especificada.

## <a name="syntax"></a>Sintaxe

```vb
CONVERTCURRENCY (amount, source currency, target currency, date, company)
```

## <a name="arguments"></a>Argumentos

`amount`: *Inteiro* ou *Real*

Um valor numérico que representa o valor monetário que deve ser convertido.

`source currency`: *Cadeia de caracteres*

O código da moeda de origem.

`target currency`: *Cadeia de caracteres*

O código da moeda de destino.

`date`: *Data*

Um valor de *Data* que representa a data usada para determinar a taxa de câmbio da conversão.

`company`: *Cadeia de caracteres*

Um valor de *Cadeia de caracteres* que representa o código de uma empresa que fornece as configurações usadas para a conversão.

## <a name="return-values"></a>Valores de retorno

*Real*

O valor numérico resultante.

## <a name="example"></a>Exemplo

`CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")` retorna o equivalente a um euro em dólares norte-americanos na data da sessão atual, com base nas configurações da empresa **DEMF**.

## <a name="additional-resources"></a>Recursos adicionais

[Outras funções (específicas de domínio comercial)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]