---
title: Função de ER QRCODE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) QRCODE é usada.
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 92665936decc87b29f2fabb346f4d16745d0a30b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562652"
---
# <a name="qrcode-er-function"></a>Função de ER QRCODE

[!include [banner](../includes/banner.md)]

A função `QRCODE` retorna um valor de *Contêiner* que apresenta a imagem do código de Resposta Rápida (código QR) para a cadeia de caracteres especificada em formato binário.

## <a name="syntax"></a>Sintaxe

```vb
QRCODE (text)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadeia de caracteres*

Um valor de *Cadeia de caracteres* que representa o texto original.

## <a name="return-values"></a>Valores de retorno

*Contêiner*

O fluxo binário resultante.

## <a name="example"></a>Exemplo

Você pode configurar um formato de relatório eletrônico (ER) para gerar um documento de saída em um formato do Microsoft Office (pastas de trabalho do Excel ou documentos do Word) usando um modelo predefinido. Esse modelo pode conter um objeto **Imagem** (pasta de trabalho do Excel) ou um **Controle de Conteúdo de Imagem** (documento do Word) como um espaço reservado para uma imagem de código QR. Você deve adicionar ao formato de ER configurado um elemento **Célula** que será usado para preencher esse espaço reservado. Para especificar quais informações serão armazenadas em um código QR, você precisa definir uma associação para esse elemento **Célula**. Por exemplo, você pode configurar essa associação como contendo a seguinte expressão:

```vb
QRCODE (model.ListOfShelfLabels.LabelText)`
```

Ao executar o formato de ER configurado, o valor de texto do campo **LabelText** da fonte de dados **model.ListOfShelfLabels** será usado para gerar uma imagem de código QR. Essa imagem substituirá um espaço reservado de imagem de código QR no modelo de documento usado para gerar um documento de saída. Quando essa imagem do documento gerado for digitalizada, ela retornará o texto obtido do campo **LabelText** da fonte de dados **model.ListOfShelfLabels**. Para obter mais informações, consulte [Inserir imagens e formas em documentos que você gerar usando ER](electronic-reporting-embed-images-shapes.md).

## <a name="additional-resources"></a>Recursos adicionais

[Funções de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]