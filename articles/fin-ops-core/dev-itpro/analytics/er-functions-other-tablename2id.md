---
title: Função de ER TABLENAME2ID
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) TABLENAME2ID é usada.
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
ms.openlocfilehash: b5deea69d5c43be599ccf02c0344ba8d662a6e0f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886839"
---
# <a name="tablename2id-er-function"></a>Função de ER TABLENAME2ID

[!include [banner](../includes/banner.md)]

A função `TABLENAME2ID` retorna uma representação numérica da ID da tabela para o nome de tabela especificado como um valor *Inteiro*.

## <a name="syntax"></a>Sintaxe

```vb
TABLENAME2ID (text)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadeia de caracteres*

Um valor de texto que representa um nome de tabela válido.

## <a name="return-values"></a>Valores de retorno

*Inteiro*

O valor numérico resultante.

## <a name="usage-notes"></a>Notas de uso

A execução desta função pode ter resultados diferentes em instâncias diferentes do Microsoft Dynamics 365 Finance, mesmo que o mesmo nome de empresa seja usado.

## <a name="example"></a>Exemplo

`TABLENAME2ID ("Intrastat")` retorna **1510**.

## <a name="additional-resources"></a>Recursos adicionais

[Outras funções (específicas de domínio comercial)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]