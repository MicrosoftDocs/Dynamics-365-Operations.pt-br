---
title: Função GETLABELTEXT ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) GETLABELTEXT é usada.
author: NickSelin
ms.date: 03/18/2022
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-01-01
ms.dyn365.ops.version: AX 10.0.25
ms.openlocfilehash: 2ce66c9410abeee16bbd074204262edf79bf6d68
ms.sourcegitcommit: c0f7ee7f8837fec881e97b2a3f12e7f63cf96882
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2022
ms.locfileid: "8462401"
---
# <a name="getlabeltext-er-function"></a>Função GETLABELTEXT ER

[!include [banner](../includes/banner.md)]

A função `GETLABELTEXT` pesquisa uma etiqueta específica para retornar um valor de *[Cadeia de caracteres](er-formula-supported-data-types-primitive.md#string)* que representa a tradução da etiqueta especificada no idioma especificado.

## <a name="syntax"></a>Sintaxe

```vb
GETLABELTEXT (label id, language)
```

## <a name="arguments"></a>Argumentos

### <a name="label-id"></a>ID de etiqueta

`label id`: *ID da cadeia de caracteres* ou *etiqueta*

O ID válido de um dos tipos de etiqueta a seguir:

- [Relatório Eletrônico (ER)](general-electronic-reporting.md), etiqueta
- Microsoft Dynamics 365 Finance- etiqueta

#### <a name="usage-notes"></a>Notas de uso

Esse argumento só pode ser definido como uma constante, usando um dos seguintes padrões suportados:

- Para etiquetas de ER:

    - `@"GER_LABEL:<LABEL ID>"`
    - `"GER_LABEL:<LABEL ID>"`

- Para etiquetas do Finance:

    - `@"<LABEL ID>"`
    - `"<LABEL ID>"`

> [!NOTE]
> Na etapa de design, uma mensagem de erro de validação é mostrada na página **[Fórmula de designer](er-advanced-formula-editor.md)** se nenhuma etiqueta for encontrada usando o ID da etiqueta fornecida.

### <a name="language"></a>Idioma

`language`: *Cadeia de caracteres*

Uma cadeia de caracteres que representa um código de linguagem.

#### <a name="usage-notes"></a>Notas de uso

Esse argumento pode ser definido como uma constante de texto ou como o caminho de um campo de fonte de dados que retorna um valor de *Cadeia de caracteres*.

> [!NOTE]
> Na etapa de design, uma mensagem de erro de validação é mostrada se nenhum código de linguagem puder ser encontrado usando o argumento fornecido `language` quando ele tiver sido definido como uma constante de texto.
>
> Durante o runtime, a tradução para o idioma do sistema `EN-US` é retornada para uma etiqueta especificada se nenhum código de linguagem for encontrado usando o argumento fornecido `language`.

## <a name="return-values"></a>Valores de retorno

*Sequência de caracteres*

O valor de texto resultante.

## <a name="example-1-system-label"></a><a name=example-1></a>Exemplo 1: etiqueta do sistema

As expressões `GETLABELTEXT (@"SYS70894", "en-us")` e `GETLABELTEXT ("SYS70894", "en-us")` devolvem a tradução em inglês "Nada a imprimir" para a etiqueta `@SYS70894` do aplicativo.

## <a name="example-2-er-label"></a><a name=example-2></a>Exemplo 2: etiqueta de ER

Começar a editar uma [configuração de ER](general-electronic-reporting.md#Configuration) que tenha sido derivada [da](er-quick-start2-customize-report.md#DeriveProvidedFormat) configuração de transferência de crédito (DE) **ISO20022,** insira uma nova fonte de dados do tipo *[Campo calculado](er-calculated-field-ds-performance.md)* e configure a expressão `GETLABELTEXT(@"GER_LABEL:VendorName", "de")` para essa fonte de dados. Nesse caso, durante o runtime, a fonte de dados retorna a tradução para o alemão "Kreditorenname" para a etiqueta de ER `@GER_LABEL:VendorName` configurada inicialmente na base **de configuração de ER para** transferência de crédito ISO20022 (DE).

## <a name="additional-resources"></a>Recursos adicionais

[Funções de texto](er-functions-category-text.md)

[Projetar relatórios multilíngues em Relatórios eletrônicos](er-design-multilingual-reports.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
