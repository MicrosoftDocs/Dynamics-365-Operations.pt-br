---
title: Função de ER Base64StringToContainer
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) Base64StringToContainer é usada.
author: NickSelin
ms.date: 12/14/2020
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
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 01f7f032915a5e4170cae5e28a445081aef075fa
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6355361"
---
# <a name="base64stringtocontainer-er-function"></a>Função de ER Base64StringToContainer

[!include [banner](../includes/banner.md)]

A [função](er-formula-language.md#functions) `BASE64STRINGTOCONTAINER` converte a entrada especificada do tipo *Cadeia de caracteres* em um item de dados do tipo *[Contêiner](er-functions-category-container.md)*.

## <a name="syntax"></a>Sintaxe

```vb
BASE64STRINGTOCONTAINER (input)
```

## <a name="arguments"></a>Argumentos

`input`: *Cadeia de caracteres*

O caminho válido de uma fonte de dados do tipo *Cadeia de caracteres*.

## <a name="return-values"></a>Valores de retorno

*Contêiner*

O valor binário resultante no formato binário grande de objeto (BLOB).

## <a name="usage-notes"></a>Notas de uso

A exceção "Parâmetro não válido" será lançada se a cadeia de caracteres de entrada não fornecer um grupo Base64 correto de esquemas de codificação de binário para texto.

## <a name="example"></a>Exemplo

Você define as seguintes fontes de dados no mapeamento de modelo:

- A fonte de dados **DocuTypeGroupEnum** raiz do tipo *Dynamics 365 for Operations / Enumeração* que se refere à enumeração de aplicativo **DocuTypeGroup**
- A fonte de dados **Cliente** raiz do tipo *Dynamics 365 for Operations / Registros de tabela* que se refere ao aplicativo de tabela **CustTable**
- A fonte de dados **\#Media** do tipo *Campo calculado* que é configurada da seguinte maneira:

    - Ela é adicionado como uma fonte de dados filho da fonte de dados **Cliente**.
    - Ela contém a expressão `WHERE(@.'<Relations'.'<Documents', @.'<Relations'.'<Documents'.'docuType()'.TypeGroup = DocuTypeGroupEnum.Image)`.

- A fonte de dados **\#MediaAsBase64String** do tipo *Campo calculado* que é configurada da seguinte maneira:

    - Ela é adicionado como uma fonte de dados filho da fonte de dados **Customer.'\#Media'**.
    - Ela contém a expressão `Customer.'#Media'.'getFileContentAsBase64String()'`.

- A fonte de dados **\#BlobFomBase64** do tipo *Campo calculado* que é configurada da seguinte maneira:

    - Ela é adicionado como uma fonte de dados filho da fonte de dados **Customer.'\#Media'**.
    - Ela contém a expressão `Base64StringToContainer(Customer.'#Media'.'#MediaAsBase64String')'`.

Neste exemplo, a fonte de dados **\#MediaAsBase64String** codifica o conteúdo binário do anexo de mídia atual como texto que representa um grupo Base64 de esquemas de codificação de binário para texto. A fonte de dados **\#BlobFomBase64** decodifica a cadeia de caracteres Base64 e retorna um valor binário no formato BLOB.

![Exemplo de fonte de dados na página Designer de mapeamento do modelo de ER.](./media/er-functions-container-base64stringtocontainer-1.png)

## <a name="additional-resources"></a>Recursos adicionais

[Funções de contêiner](er-functions-category-container.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]