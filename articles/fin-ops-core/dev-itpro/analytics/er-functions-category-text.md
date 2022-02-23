---
title: Lista de funções ER na categoria de texto
description: Este tópico fornece informações sobre as funções de texto que são compatíveis no relatório eletrônico (ER).
author: NickSelin
manager: kfend
ms.date: 04/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 228620afc81e154eced572f3b6024d6836d00d66
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686018"
---
# <a name="list-of-er-functions-of-the-text-category"></a>Lista de funções ER na categoria de texto

[!include [banner](../includes/banner.md)]

As funções de texto de relatório eletrônico (ER) podem ser usadas para realizar operações em fontes de dados do tipo de dado *Cadeia de caracteres*. Este tópico fornece um resumo dessas funções.

## <a name="list-of-supported-functions"></a>Lista de funções com suporte

| Função | Descrição |
|----------|-------------|
| [Char](er-functions-text-char.md) | Essa função retorna um valor de *Cadeia de caracteres* que apresenta um caractere único referenciado pelo número Unicode especificado. |
| [Concatenar](er-functions-text-concatenate.md) | Essa função retorna todas as cadeias de caracteres de texto especificadas como um valor de *Cadeia de caracteres* depois que elas são unidas em uma cadeias de caracteres. |
| [Formato](er-functions-text-format.md) | Essa função retorna a cadeia de caracteres especificada como um valor de *Cadeia de caracteres* após ela ser formatada, substituindo todas as ocorrências de **%N** pelo *N* º argumento. |
| [GetEnumValueByName](er-functions-text-getenumvaluebyname.md) | Essa função procura um valor de *Enum.* específico na fonte de dados de enumeração especificada usando o nome de enumeração especificado como um valor de *Cadeia de caracteres*. Se o valor *Enum.* for encontrado, a função o retornará. |
| [GuidValue](er-functions-text-guidvalue.md) | Essa função converte a entrada especificada do tipo *Cadeia de caracteres* em um item de dados do tipo *GUID*. |
| [JsonValue](er-functions-text-jsonvalue.md) | Essa função analisa os dados no formato JSON (JavaScript Object Notation) que são acessados no caminho especificado e extrai um valor escalar baseado na ID especificada. Em seguida, ela retorna o valor escalar extraído como um valor de *Cadeia de caracteres*. |
| [Esquerdo](er-functions-text-left.md) | Essa função retorna um valor de *Cadeia de caracteres* que apresenta o número de caracteres especificado a partir do início da cadeia de caracteres especificada. |
| [Len](er-functions-text-len.md) | Essa função retorna um valor *Inteiro* que representa o número de caracteres na cadeia de caracteres específica. |
| [Lower](er-functions-text-lower.md) | Essa função retorna a cadeia de caracteres de texto especificada como um valor de *Cadeia de caracteres* após ser convertida em letras minúsculas. |
| [Mid](er-functions-text-mid.md) | Essa função retorna um valor de *Cadeia de caracteres* que apresenta o número de caracteres especificado da cadeia de caracteres especificada, a partir da posição especificada. |
| [NumberFormat](er-functions-text-numberformat.md) | Essa função retorna um valor de *Cadeia de caracteres* que apresenta o número especificado no formato especificado e em uma cultura opcionalmente especificada. |
| [NumeralsToText](er-functions-text-numeralstotext.md) | Essa função retorna o número especificado como um valor de *Cadeia de caracteres* após ele ser soletrado (ou seja, convertido em cadeias de caracteres de texto) no idioma especificado. |
| [PadLeft](er-functions-text-padleft.md) | Essa função retorna um valor de *Cadeia de caracteres* do tamanho especificado, em que o início da cadeia de caracteres especificada é preenchido com uma ou mais instâncias dos caracteres especificados. |
| [QrCode](er-functions-text-qrcode.md) | Essa função retorna um valor de *Contêiner* que apresenta a imagem do código de Resposta Rápida (código QR) para a cadeia de caracteres especificada em formato binário. |
| [Substituir](er-functions-text-replace.md) | Essa função retorna a cadeia de caracteres de texto especificada como um valor de *Cadeia de caracteres* após toda ou parte dela ser substituída por outra cadeia de caracteres. |
| [Direito](er-functions-text-right.md) | Essa função retorna um valor de *Cadeia de caracteres* que apresenta o número de caracteres especificado a partir do final da cadeia de caracteres especificada. |
| [Texto](er-functions-text-text.md) | Essa função retorna o número especificado como um valor de *Cadeia de caracteres* após ele ser convertido em uma cadeia de caracteres de texto que é formatada de acordo com as configurações de localidade do servidor da instância atual do aplicativo. |
| [Traduzir](er-functions-text-translate.md) | Esta função retorna um valor *Cadeia de caracteres* que contém o resultado da substituição do texto especificado em caracteres para outro conjunto de caracteres fornecido. |
| [Trim](er-functions-text-trim.md) | Essa função retorna a cadeia de caracteres de texto especificada como um valor de *Cadeia de caracteres* após os espaços à direita e à esquerda serem truncados e após vários espaços entre as palavras serem removidos. |
| [Upper](er-functions-text-upper.md) | Essa função retorna a cadeia de caracteres de texto especificada como um valor de *Cadeia de caracteres* após ser convertida em letras maiúsculas. |

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do Relatório Eletrônico](general-electronic-reporting.md)

[Designer de fórmulas no Relatório eletrônico](general-electronic-reporting-formula-designer.md)

[Linguagem da fórmula de relatório eletrônico](er-formula-language.md)
