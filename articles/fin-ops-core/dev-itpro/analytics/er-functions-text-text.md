---
title: Função de ER TEXT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) TEXT é usada.
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: 0694480f5d6892d13fe0c0d9ad191cdf2332dfec
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746090"
---
# <a name="text-er-function"></a>Função de ER TEXT

[!include [banner](../includes/banner.md)]

A função `TEXT` retorna o número especificado como um valor de *Cadeia de caracteres* após ele ser convertido em uma cadeia de caracteres de texto que é formatada de acordo com as configurações de localidade do servidor da instância atual do aplicativo.

## <a name="syntax"></a>Sintaxe

```vb
TEXT (number)
```

## <a name="arguments"></a>Argumentos

`number`: *Inteiro* ou *Real*

Um número que deve ser convertido em uma cadeia de caracteres de texto.

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

Para valores do tipo *Real*, a conversão de cadeia de caracteres é limitada a duas casas decimais.

## <a name="example"></a>Exemplo

Se a localidade do servidor da instância do Microsoft Dynamics 365 Finance for definida como **EN-US**, `TEXT (NOW ())` retornará a data da sessão atual do Finance, 17 de dezembro de 2015, como a cadeia de caracteres de texto **"12/17/2015 07:59:23 AM"**. `TEXT (1/3)` retorna **"0.33"**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]