---
title: Função de ER FA_SUM
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) FA_SUM é usada.
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
ms.openlocfilehash: 03bed091350b39601edb22b5af6bda5a83af47eb
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041345"
---
# <a name="FA_SUM">Função de ER FA_SUM</a>

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
