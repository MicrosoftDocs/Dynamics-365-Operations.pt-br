---
title: Função de ER GETCURRENTCOMPANY
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) GETCURRENTCOMPANY é usada.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: fcb5ef2f218a85bab25f830db583343504c46e98
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567535"
---
# <a name="getcurrentcompany-er-function"></a>Função de ER GETCURRENTCOMPANY

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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]