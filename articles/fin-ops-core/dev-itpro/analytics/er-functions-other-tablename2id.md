---
title: Função de ER TABLENAME2ID
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) TABLENAME2ID é usada.
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9f9e38f46df8a93b5cb16b8d0d5e5afbff8558a
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743990"
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
