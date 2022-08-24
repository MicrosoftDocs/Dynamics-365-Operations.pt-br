---
title: Função de ER QRCODE
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) QRCODE é usada.
author: kfend
ms.date: 12/10/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 9de62eefb82942ccc72e81bd9bf36eed07c99dba
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287178"
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
