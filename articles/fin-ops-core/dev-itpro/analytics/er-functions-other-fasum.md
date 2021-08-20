---
title: Função de ER FA_SUM
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) FA_SUM é usada.
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
ms.openlocfilehash: 96b579cff1a61b8e1131317917ededb3b26963677e99da0e294501817cda26d1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740302"
---
# <a name="fa_sum-er-function"></a>Função de ER FA_SUM

[!include [banner](../includes/banner.md)]

A função `FA_SUM` retorna um valor de *Contêiner (registro)* que consiste em dados dos valores de ativo fixo para o item de ativo fixo, o código do método de depreciação e o período de datas especificados.

## <a name="syntax"></a>Sintaxe

```vb
FA_SUM (fixed asset code, value model code, start date, end date)
```

## <a name="arguments"></a>Argumentos

`fixed asset code`: *Cadeia de caracteres*

Um valor de *Cadeia de caracteres* que representa o código de um item de ativo fixo para o qual o saldo é calculado.

`value model code`: *Cadeia de caracteres*

Um valor de *Cadeia de caracteres* que representa o código de um método de depreciação para o qual o saldo é calculado.

`start date`: *Data*

Um valor de *Data* que representa a data inicial de um período para o qual os valores de ativo fixo são calculados.

`end date`: *Data*

Um valor de *Data* que representa a data final de um período para o qual os valores de ativo fixo são calculados.

## <a name="return-values"></a>Valores de retorno

*Contêiner (registro)*

O valor de registro resultante.

## <a name="example"></a>Exemplo

`FA_SUM ("COMP-000001", "Current", Date1, Date2)` retorna o contêiner de dados para o ativo fixo **COMP-000001** que foi preparado para o método de depreciação **Atual** e para o período de **Date1** a **Date2**.

## <a name="additional-resources"></a>Recursos adicionais

[Outras funções (específicas de domínio comercial)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]