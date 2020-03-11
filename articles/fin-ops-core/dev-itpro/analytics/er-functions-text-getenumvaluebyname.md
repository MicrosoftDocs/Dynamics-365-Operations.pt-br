---
title: Função de ER GETENUMVALUEBYNAME
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) GETENUMVALUEBYNAME é usada.
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
ms.openlocfilehash: 87613978c149b5d41aefc58f9896424229819626
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041149"
---
# <a name="GETENUMVALUEBYNAME">Função de ER GETENUMVALUEBYNAME</a>

[!include [banner](../includes/banner.md)]

A função `GETENUMVALUEBYNAME` procura um valor de *Enum.* específico na fonte de dados de enumeração especificada usando o nome de enumeração especificado como um valor de *Cadeia de caracteres*. Se o valor *Enum.* for encontrado, a função o retornará. Caso contrário, a função retorna o valor de enumeração **nulo**.

## <a name="syntax"></a>Sintaxe

```vb
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a>Argumentos

`enumeration data source path`: *Enumeração*

O caminho válido de uma fonte de dados de um dos seguintes tipos de enumeração:

- Enumeração de modelo de relatório eletrônico (ER)
- Enumeração de formato de ER
- Enumeração do Microsoft Dynamics 365 Finance

`enumeration value text`: *Cadeia de caracteres*

Um valor de cadeia de caracteres que representa o nome de um único valor de enumeração.

## <a name="return-values"></a>Valores de retorno

*Enum.* anulável

O valor de enumeração resultante.

## <a name="usage-notes"></a>Notas de uso

Nenhuma exceção é gerada se um valor de *Enum.* não for encontrado usando o nome do valor de enumeração especificado como um valor de *Cadeia de caracteres*.

## <a name="example"></a>Exemplo

Na ilustração a seguir, a enumeração de **ReportDirection** é apresentada em um modelo de dados. Observe que os rótulos são definidos para os valores de enumeração.

<p><a href="./media/ER-data-model-enumeration-values.PNG"><img src="./media/ER-data-model-enumeration-values.PNG" alt="Available values for a data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

A ilustração a seguir mostra estes detalhes:

- A fonte de dados **$Direction** é configurada em um relatório de ER. Essa fonte de dados é configurada com base na enumeração do modelo **ReportDirection**.
- A expressão `$IsArrivals` foi criada para usar a fonte de dados **$Direction** baseada na enumeração do modelo como um parâmetro desta função.
- O valor dessa expressão de comparação é **TRUE**.

<a href="./media/ER-data-model-enumeration-usage.PNG"><img src="./media/ER-data-model-enumeration-usage.PNG" alt="Example of data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

## <a name="additional-resources"></a>Recursos adicionais

[Funções de texto](er-functions-category-text.md)
