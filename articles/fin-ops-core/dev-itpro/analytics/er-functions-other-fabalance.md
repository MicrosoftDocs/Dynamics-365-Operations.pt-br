---
title: Função de ER FA_BALANCE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) FA_BALANCE é usada.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 5570e1295ff6da0eadd7e18143a2206032597ae5
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684826"
---
# <a name="fa_balance-er-function"></a>Função de ER FA_BALANCE

[!include [banner](../includes/banner.md)]

A função `FA_BALANCE` retorna um valor de *Contêiner (registro)* que consiste em dados do saldo de ativo fixo para o item de ativo fixo, o código do método de depreciação, o ano do relatório e a data do relatório especificados.

## <a name="syntax"></a>Sintaxe

```vb
FA_BALANCE (fixed asset code, value model code, reporting year, reporting date)
```

## <a name="arguments"></a>Argumentos

`fixed asset code`: *Cadeia de caracteres*

Um valor de *Cadeia de caracteres* que representa o código de um item de ativo fixo para o qual o saldo é calculado.

`value model code`: *Cadeia de caracteres*

Um valor de *Cadeia de caracteres* que representa o código de um método de depreciação para o qual o saldo é calculado.

`reporting year`: *Valor de enumeração*

Um valor de enumeração da enumeração de aplicativo **AssetYear** que define um período para o cálculo do saldo.

`reporting date`: *Data*

Um valor de *Data* que define uma data para o cálculo do saldo.

## <a name="return-values"></a>Valores de retorno

*Contêiner (registro)*

O valor de registro resultante.

## <a name="example"></a>Exemplo

`FA_ BALANCE ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())` retorna o contêiner de dados de saldos para o ativo fixo **COMP-000001** que foi preparado para o método de depreciação **Atual** na data atual da sessão do aplicativo.

## <a name="additional-resources"></a>Recursos adicionais

[Outras funções (específicas de domínio comercial)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]