---
title: Função de ER LISTOFFIELDS
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) LISTOFFIELDS é usada.
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 4f394a557beaeb558f5c7065eefe16f4aadce6ac
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5743765"
---
# <a name="listoffields-er-function"></a>Função de ER LISTOFFIELDS

[!include [banner](../includes/banner.md)]

A função `LISTOFFIELDS` retorna um valor de *Lista de registros* que é criado com base na estrutura do argumento especificado do tipo *Enumeração* ou *Contêiner (registro)*.

## <a name="syntax-1"></a>Sintaxe 1

```vb
LISTOFFIELDS (path)
```

## <a name="syntax-2"></a>Sintaxe 2

```vb
LISTOFFIELDS (path, language)
```

## <a name="arguments"></a>Argumentos

`path`: Referência de fonte de dados

O caminho de referência válido de uma fonte de dados de um dos seguintes tipos de dados:

- Enumeração do modelo
- Enumeração de formato
- Enumeração de aplicativo
- Contêiner (registro)

`language`: *Cadeia de caracteres*

Texto que representa um código de idioma.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

A lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

A lista que é criada consistem em registros que têm os seguintes campos:

- **Nome** (tipo de dados *Cadeia de caracteres*)
- **Rótulo** (tipo de dados *Cadeia de caracteres*)
- **Descrição** (tipo de dados *Cadeia de caracteres*)
- **IsTranslated** (tipo de dados *Booliano*)

Se o argumento `path` se referir a uma fonte de dados do tipo *Contêiner (registro)*, para cada campo do registro de contêiner referenciado, um novo registro será adicionado à lista criada. Para cada registro criado, o campo **Nome** retorna o nome do campo do registro de contêiner referenciado para o qual o registro atual foi criado.

Se o argumento `path` se referir a uma fonte de dados de um dos tipos de *Enumeração*, para cada valor de enumeração da enumeração referenciada, um novo registro será adicionado à lista criada. Para cada registro criado, o campo **Nome** retorna o valor da enumeração referenciada para a qual o registro atual foi criado, o campo **Descrição** retorna a descrição e o campo **Rótulo** retorna o rótulo dessa enumeração.

No tempo de execução, quando a sintaxe 1 é usada, os campos **Rótulo** e **Descrição** devem retornar valores baseados nas configurações de idioma do formato de relatório eletrônico (ER) em execução:

- Se os rótulos e descrições para o idioma solicitado estiverem disponíveis, os campos **Rótulo** e **Descrição** retornarão valores baseados nesse idioma e o campo **IsTranslated** retornará **Verdadeiro**.
- Se os rótulos e descrições para o idioma solicitado não estiverem disponíveis, os campos **Rótulo** e **Descrição** retornarão valores baseados no idioma padrão **EN-US** e o campo **IsTranslated** retornará **Falso**.

No tempo de execução, quando a sintaxe 2 é usada, os campos **Rótulo** e **Descrição** devem retornar valores baseados no idioma definido como o segundo argumento da função chamada:

- Se os rótulos e descrições para o idioma solicitado estiverem disponíveis, os campos **Rótulo** e **Descrição** retornarão valores baseados nesse idioma e o campo **IsTranslated** retornará **Verdadeiro**.
- Se os rótulos e descrições para o idioma solicitado não estiverem disponíveis, os campos **Rótulo** e **Descrição** retornarão valores baseados no idioma **EN-US** e o campo **IsTranslated** retornará **Falso**.

## <a name="example-1"></a>Exemplo 1

Na ilustração a seguir, uma enumeração é apresentada em um modelo de dados de ER.

<a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="Enumeration in a model" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a>

A ilustração a seguir mostra estes detalhes:

- A enumeração do modelo inserida em um relatório como uma fonte de dados.
- Uma expressão de ER usa a enumeração do modelo como um parâmetro da função `LISTOFFIELDS`.
- Uma fonte de dados do tipo *Lista de registros* é inserida em um relatório usando a expressão de ER que é criada.

<a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="Format" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a>

O exemplo a seguir mostra os elementos do formato de ER associados à fonte de dados do tipo *Lista de registros* que foi criada usando a função `LISTOFFIELDS`.

<a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="Format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a>

A ilustração a seguir mostra o formato o resultado quando o formato criado é executado.

<a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="Format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a>

> [!NOTE] 
> Com base nas configurações de idioma dos elementos de formato **FILE** e **FOLDER** pais, o texto traduzido para rótulos e descrições é inserido na saída do formato de ER.

## <a name="example-2"></a>Exemplo 2

Você usa o tipo de fonte de dados *Campo calculado* a fim de configurar as fontes de dados **enumType\_de** e **enumType\_deCH** para a enumeração do modelo de dados **enumType**:

- **enumType\_de** = `LISTOFFIELDS (enumType, "de")`
- **enumType\_deCH** = `LISTOFFIELDS (enumType, "de-CH")`

Nesse caso, você pode usar a seguinte expressão para obter o rótulo do valor de enumeração em alemão suíço, se essa tradução estiver disponível. Se a tradução de alemão suíço não estiver disponível, o rótulo ficará em alemão.

```vb
IF (NOT (enumType_deCH.IsTranslated), enumType_de.Label, enumType_deCH.Label)
```

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]