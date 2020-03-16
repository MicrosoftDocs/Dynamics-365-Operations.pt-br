---
title: Função de ER GETCURRENTCOMPANY
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) GETCURRENTCOMPANY é usada.
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d91caff1a1b89e060a16833e53f3647208ed3826
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041414"
---
# <a name="GETCURRENTCOMPANY">Função de ER GETCURRENTCOMPANY</a>

[!include [banner](../includes/banner.md)]

A função `GETCURRENTCOMPANY` retorna um valor de *Cadeia de caracteres* que representa o código da entidade legal (empresa) à qual um usuário está conectado no momento.

## <a name="syntax"></a>Sintaxe

```vb
GETCURRENTCOMPANY ()
```

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="example"></a>Exemplo

`GETCURRENTCOMPANY ()` retorna **USMF** para um usuário que está conectado à empresa **Contoso Entertainment System USA**.

## <a name="additional-resources"></a>Recursos adicionais

[Outras funções (específicas de domínio comercial)](er-functions-category-other.md)
