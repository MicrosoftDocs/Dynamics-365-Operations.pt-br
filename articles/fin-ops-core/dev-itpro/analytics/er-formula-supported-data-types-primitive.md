---
title: Tipos de dados primitivos compatíveis com as fórmulas de relatório eletrônico
description: Este artigo fornece informações sobre os tipos de dados primitivos que são compatíveis com as fórmulas de relatório eletrônico (ER).
author: NickSelin
ms.date: 06/02/2021
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 41cda188e774630e96c46fba1200fd2e640f9915
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891865"
---
# <a name="supported-primitive-data-types-for-electronic-reporting-formulas"></a>Tipos de dados primitivos compatíveis com as fórmulas de relatório eletrônico

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre os tipos de dados primitivos que são compatíveis com as expressões de [relatório eletrônico (ER)](general-electronic-reporting.md). Veja a seguir uma lista dos tipos de dados primitivos:

- [booliano](#boolean)
- [data](#date)
- [datetime](#datetime)
- [enumeração](#enumeration)
- [guid](#guid)
- [inteiro](#integer)
- [int64](#int64)
- [real](#real)
- [cadeia de caracteres](#string)

## <a name="boolean"></a><a name="boolean"></a>Booleano

O tipo de dados primitivo *booliano* contém um valor que é avaliado como *true* ou *false*. Você pode usar as palavras-chave literais reservadas **True** e **False** sempre que uma expressão *booliana* é esperada. O valor padrão é *false*.

A representação interna de um *booliano* é um *inteiro*. O valor *inteiro* 0 (zero) é avaliado como *false* e todos os outros valores *inteiros* são avaliados como *true*. Quando você [valida](general-electronic-reporting-formula-designer.md#TestFormula) uma expressão configurada que retorna um *booliano* no [designer de fórmulas de ER](er-advanced-formula-editor.md), o painel de resultado do teste apresenta *0* (zero) quando uma expressão retorna como *false*. Caso contrário, o painel de resultado do teste apresentará *1*.

Um *booliano* não tem conversões implícitas. No entanto, você pode usar a função [TEXT](er-functions-text-text.md) para converter explicitamente um *booliano* em uma *cadeia de caracteres*:

- O valor *false* é convertido na cadeia de caracteres de texto **False**.
- O valor *true* é convertido na cadeia de caracteres de texto **True**.

> [!NOTE]
> Essa conversão não depende do [contexto](er-design-multilingual-reports.md) de linguagem e cultura fornecidos.

Os [operadores](er-formula-language.md#Operators) de comparação são o único tipo de operador que pode ser usado com o tipo de dados *booliano*. Os seguintes operadores podem ser usados para comparar dois valores *boolianos*: \<\> e =.

## <a name="date"></a><a name="date"></a>Data

O tipo de dados primitivo *data* contém o dia, o mês e o ano. As datas podem ser iniciadas usando as seguintes funções:

- [DATEVALUE](er-functions-datetime-datevalue.md)
- [NULLDATE](er-functions-datetime-nulldate.md)
- [SESSIONTODAY](er-functions-datetime-sessiontoday.md)
- [TODAY](er-functions-datetime-today.md)

O tipo de dados *data* pode conter datas entre 1º de janeiro de 1900 e 31 de dezembro de 2154. O valor padrão é **nulo**, e a representação interna é a data de 1º de janeiro de 1900.

Uma *data* não tem conversões implícitas. No entanto, você pode usar as seguintes funções de conversão explícitas:

- [DATEFORMAT](er-functions-datetime-dateformat.md)
- [DATETODATETIME](er-functions-datetime-datetodatetime.md)
- [TEXT](er-functions-text-text.md)

A função [ADDDAYS](er-functions-datetime-adddays.md) permite adicionar e subtrair dias de datas. Dessa forma, você pode mover a data para um número específico de dias no futuro e no passado. A função [DAYS](er-functions-datetime-days.md) permite subtrair datas umas das outras e calcular a diferença em dias. Para obter mais informações sobre a transformação dos valores de *data*, consulte [Lista de funções ER na categoria Data e hora](er-functions-category-datetime.md).

Os [operadores](er-formula-language.md#Operators) de comparação são o único tipo de operador que pode ser usado com o tipo de dados *data*. Os seguintes operadores podem ser usados para comparar dois valores *data*: \<\>, \<, \<=, =, \> e \>=.

## <a name="datetime"></a><a name="datetime"></a>Datetime

O tipo de dados primitivo *datetime* combina o tipo de *data* e um valor que representa o tempo que passou desde a meia-noite. O tempo é expresso em horas, minutos, segundos e frações de segundo. Um valor de *datetime* também contém informações sobre o fuso horário.

O tipo de dados *datetime* pode conter datas entre 1º de janeiro de 1900 (1900-01-01T00:00:00.0000000+00:00 no [formato](/dotnet/standard/base-types/standard-date-and-time-format-strings) de ida e volta) e 31 de dezembro de 2154 (2154/12/31T11:59:59.9999999+00:00 no formato de ida e volta). A menor unidade de tempo em um *datetime* é um décimo milionésimo de um segundo.

> [!NOTE]
> Quando o [especificador](/dotnet/standard/base-types/standard-date-and-time-format-strings) **hh** é usado por horas, os valores de tempo acima de 12:59:59:9999999 não podem ser interpretados como tempos válidos.
>
> Quando o especificador **HH** é usado por horas, os valores de tempo acima de 23:59:59:9999999 não podem ser interpretados como tempos válidos.

O valor padrão é **nulo**, e a representação interna é a data de 1º de janeiro de 1900 (1900-01-01T00:00:00.0000000+00:00 no formato de ida e volta).

Os datetimes podem ser iniciados usando as seguintes funções:

- [DATETIMEVALUE](er-functions-datetime-datetimevalue.md)
- [NULNULLDATETIMELDATE](er-functions-datetime-nulldatetime.md)
- [SESSIONNOW](er-functions-datetime-sessionnow.md)
- [NOW](er-functions-datetime-now.md)

Um *datetime* não tem conversões implícitas. No entanto, você pode usar as seguintes funções de conversão explícitas:

- [DATETIMEFORMAT](er-functions-datetime-datetimeformat.md)
- [TEXT](er-functions-text-text.md)

Para obter mais informações sobre a transformação dos valores de *datetime*, consulte [Lista de funções ER na categoria Data e hora](er-functions-category-datetime.md).

Os [operadores](er-formula-language.md#Operators) de comparação são o único tipo de operador que pode ser usado com o tipo de dados *datetime*. Os seguintes operadores podem ser usados para comparar dois valores *datetime*: \<\>, \<, \<=, =, \> e \>=.

## <a name="enumeration"></a><a name="enumeration"></a>Enumeração

O tipo de dados primitivo *enumeração* é uma lista de literais. Você pode usar enumerações definidas no [código-fonte](../dev-ref/xpp-data-primitive.md#enum) do aplicativo. Você também pode introduzir suas próprias enumerações no modelo de dados de ER e nos componentes do formato de ER.

Uma *enumeração* de aplicativo pode ser usada em expressões de qualquer mapeamento de modelo de ER e formato de ER.

A ilustração a seguir mostra como você pode adicionar a enumeração do modelo **CustVendCorrectiveReasonCode** ao modelo de dados de ER editável.

[![Configurando uma enumeração do modelo no designer de modelos de dados de ER.](./media/er-formula-supported-data-types-primitive-enum1.gif)](./media/er-formula-supported-data-types-primitive-enum1.gif)

Uma *enumeração* do modelo pode ser usada em expressões de qualquer mapeamento do modelo de ER e formato de ER que foram criados sob um modelo de dados em que a *enumeração* foi introduzida.

A ilustração a seguir mostra como você pode adicionar a enumeração de formato **Lista de subcategorias de encargos revertidos da Natura** ao formato de ER editável.

[![Configurando uma enumeração de formato no designer de formatos de ER.](./media/er-formula-supported-data-types-primitive-enum2.gif)](./media/er-formula-supported-data-types-primitive-enum2.gif)

Uma *enumeração* de formato só pode ser usada em expressões do formato de ER em que a *enumeração* foi introduzida.

É necessário usar o tipo apropriado de fontes de dados de ER para trazer uma enumeração específica a um componente de ER configurado como uma constante ou como um valor que o usuário que está executando uma solução de ER definiu na caixa de diálogo no runtime.

- As enumerações do aplicativo podem ser acessadas usando as fontes de dados **Dynamics 365 for Operations\Enumeração** e **Geral\Parâmetros de entrada do usuário**. A ilustração a seguir mostra como você pode adicionar ao formato de ER editável as fontes de dados **appenumNoYes** e **uipNoYes** que se referem à enumeração do aplicativo **NoYes**.

    [![Adicionando fontes de dados de enumeração do aplicativo ao designer de formatos de ER.](./media/er-formula-supported-data-types-primitive-enum3a.gif)](./media/er-formula-supported-data-types-primitive-enum3a.gif)

- As enumerações de modelo de dados podem ser acessadas usando as fontes de dados **Modelo de dados\Enumeração** e **Modelo de dados\Parâmetros de entrada do usuário de enumeração**. A ilustração a seguir mostra como você pode adicionar ao formato de ER editável a fonte de dados **CustVendCorrectiveReasonCode** que se refere à enumeração do modelo de dados **CustVendCorrectiveReasonCode**.

    [![Adicionando fontes de dados de enumeração do modelo ao designer de formatos de ER.](./media/er-formula-supported-data-types-primitive-enum3b.gif)](./media/er-formula-supported-data-types-primitive-enum3b.gif)

- As enumerações de formato podem ser acessadas usando as fontes de dados **Formato\Enumeração** e **Formato\Parâmetros de entrada do usuário de enumeração**. A ilustração a seguir mostra como você pode adicionar ao formato de ER editável a fonte de dados **NaturaReverseCharge** que se refere à enumeração de formato **Subcategorias de encargos revertidos da Natura**.

    [![Adicionando fontes de dados de enumeração de formato ao designer de formatos de ER.](./media/er-formula-supported-data-types-primitive-enum3c.gif)](./media/er-formula-supported-data-types-primitive-enum3c.gif)

Uma *enumeração* não tem conversões implícitas. No entanto, você pode usar a função de conversão [TEXT](er-functions-text-text.md) para converter uma *enumeração* em uma cadeia de caracteres de texto. Esta conversão não depende da linguagem. Para saber como você pode associar um valor de *enumeração* aos rótulos específicos de linguagem apropriados, consulte os exemplos de uso das funções [LISTOFFIELDS](er-functions-list-listoffields.md) e [GETENUMVALUEBYNAME](er-functions-text-getenumvaluebyname.md).

Os [operadores](er-formula-language.md#Operators) de comparação são o único tipo de operador que pode ser usado com o tipo de dados de *enumeração*. Os seguintes operadores podem ser usados para comparar dois valores de *enumeração*: \<\> e =.

## <a name="guid"></a><a name="guid"></a>Guid

O tipo de dados primitivo *guid* contém um valor de identificador global exclusivo (GUID). Um GUID é um valor que pode ser usado em todos os computadores e redes, sempre que um identificador exclusivo for necessário. É improvável que o número seja duplicado. Um GUID válido atende a todas as seguintes especificações:

- Deve haver 32 dígitos hexadecimais.
- Além disso, deve haver quatro caracteres de traço incorporados nos seguintes locais: 8-4-4-4-12.
- Além disso, chaves opcionais \{\} podem ser adicionadas no início e no final da cadeia de caracteres. Por exemplo, tanto **\{2CDB0FE7-D7B3-4938-A0F0-FE28FB8FE212\}** quanto **2CDB0FE7-D7B3-4938-A0F0-FE28FB8FE212** são cadeias de caracteres GUID válidas.
- Portanto, deve haver um total de 36 ou 38 caracteres, dependendo se as chaves são adicionadas.
- As letras que são usadas como dígitos hexadecimais podem ser maiúsculas (A-F), minúsculas (a-f) ou mistas.

As seguintes funções de conversão explícitas podem ser usadas:

- [GUIDVALUE](er-functions-text-guidvalue.md)
- [TEXT](er-functions-text-text.md)

Os [operadores](er-formula-language.md#Operators) de comparação são o único tipo de operador que pode ser usado com o tipo de dados *guid*. Os seguintes operadores podem ser usados para comparar dois valores *guid*: \<\> e =.

## <a name="integer"></a><a name="integer"></a>Inteiro

O tipo de dados primitivo *inteiro* representa um número que não possui casas decimais. Os inteiros são usados como variáveis de controle em instruções repetitivas ou como índices em listas de registros.

Um literal *inteiro* é o inteiro, pois é inserido diretamente em uma [expressão](general-electronic-reporting-formula-designer.md#formula-designer-overview) de ER (fórmula), como **12345**. Um *inteiro* tem 32 bits de largura. O valor padrão é **0**, e a representação interna é um número longo. Um *inteiro* é automaticamente convertido em um *real*.

Além disso, as seguintes funções de conversão explícitas podem ser usadas:

- [INTVALUE](er-functions-conversion-intvalue.md)
- [NUMBERFORMAT](er-functions-text-numberformat.md)
- [TEXT](er-functions-text-text.md)

O intervalo de um *inteiro* é \[-2.147.483.647 : 2.147.483.647\]. Todos os inteiros deste intervalo podem ser usados como literais.

Todos os [operadores](er-formula-language.md#Operators) de comparação e matemática podem ser usados com o tipo de dados *inteiro*.

## <a name="int64"></a><a name="int64"></a>Int64

O tipo de dados primitivo *int64* representa um número que não possui casas decimais. Os valores *int64* são usados como variáveis de controle em instruções repetitivas ou como identificadores de registros.

Um *int64* tem 64 bits de largura. O valor padrão é **0**, e a representação interna é um número longo. Um *int64* é automaticamente convertido em um *real*.

Além disso, as seguintes funções de conversão explícitas podem ser usadas:

- [INT64VALUE](er-functions-conversion-int64value.md)
- [NUMBERFORMAT](er-functions-text-numberformat.md)
- [TEXT](er-functions-text-text.md)

O intervalo de um *int64* é \[-9,223,372,036,854,775,807 : 9,223,372,036,854,775,807\].

Todos os [operadores](er-formula-language.md#Operators) de comparação e matemática podem ser usados com o tipo de dados *int64*.

## <a name="real"></a><a name="real"></a>Real

O tipo de dados primitivo *real* pode conter valores decimais, além de inteiros. Você pode usar literais decimais em qualquer lugar em que um *real* seja esperado. Um literal decimal é o decimal, pois é inserido diretamente no código, como **2.19**.

> [!NOTE]
> Nas expressões de ER, um período (.) é sempre usado como separador decimal.

Os reais podem ser usados em todas as expressões e podem ser usados com operadores de comparação e aritméticos. Um *real* tem uma precisão de 16 dígitos significativos. O valor padrão para um *real* é **0,0**, e a representação interna é um número digital com codificação binária (BCD). A codificação BCD permite representações exatas de valores múltiplos de 0,1. O intervalo de uma variável *real* é -(10)<sup>127</sup> a (10)<sup>127</sup>. Todos os reais neste intervalo podem ser usados como literais em expressões de ER.

Um *real* não tem conversões implícitas. No entanto, você pode usar as seguintes funções para converter explicitamente um *real* em outros tipos de dados e outros tipos de dados em um *real*:

- [INTVALUE](er-functions-conversion-intvalue.md)
- [INT64VALUE](er-functions-conversion-int64value.md)
- [NUMBERFORMAT](er-functions-text-numberformat.md)
- [TEXT](er-functions-text-text.md)
- [VALUE](er-functions-conversion-value.md)

Todos os [operadores](er-formula-language.md#Operators) de comparação e matemática podem ser usados com o tipo de dados *real*.

## <a name="string"></a><a name="string"></a>Sequência de caracteres

O tipo de dados primitivo *cadeia de caracteres* representa uma sequência de caracteres que são usados como textos, números de contas, endereços e números de telefone.

Os literais de *cadeia de caracteres* são caracteres colocados entre aspas (""). Os literais de *cadeia de caracteres* podem ser usados sempre que valores de *cadeia de caracteres* são esperados em expressões de ER. Você pode usar cadeias de caracteres em expressões lógicas, como comparações. Também é possível concatenar valores de *cadeia de caracteres* usando o operador **\&** ou a função [CONCATENATE](er-functions-text-concatenate.md).

> [!NOTE]
> Se você concatenar dois valores de *cadeia de caracteres* e quiser que a *cadeia de caracteres* resultante se estenda por mais de uma linha, use o separador de quebra de linha entre os valores. Para a saída TEXT, este separador pode ser um caractere gerado usando a expressão [CHAR](er-functions-text-char.md)(10) ou CHAR(13). Para HTML, pode ser o rótulo **\<br\>**.

O valor padrão de uma *cadeia de caracteres* é uma cadeia de caracteres de texto em branco que não tem caracteres, e a representação interna é uma lista de caracteres.

Não há conversões automáticas para cadeias de caracteres. No entanto, as seguintes funções de conversão explícitas podem ser usadas:

- [CHAR](er-functions-text-char.md)
- [FORMAT](er-functions-text-format.md)
- [LEFT](er-functions-text-left.md)
- [LEN](er-functions-text-len.md)
- [MID](er-functions-text-mid.md)
- [PADLEFT](er-functions-text-padleft.md)
- [REPLACE](er-functions-text-replace.md)
- [RIGHT](er-functions-text-right.md)
- [TEXT](er-functions-text-text.md)
- [TRANSLATE](er-functions-text-translate.md)
- [TRIM](er-functions-text-trim.md)
- [UPPER](er-functions-text-upper.md)

Para saber mais sobre a transformação dos valores de *cadeia de caracteres*, consulte [Lista de funções ER na categoria de texto](er-functions-category-text.md).

Uma *cadeia de caracteres* pode conter um número indefinido de caracteres.

Todos os [operadores](er-formula-language.md#Operators) de comparação podem ser usados com o tipo de dados *cadeia de caracteres*.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral do Relatório Eletrônico](general-electronic-reporting.md)
- [Linguagem da fórmula de relatório eletrônico](er-formula-language.md)
- [Tipos de dados compostos compatíveis](er-formula-supported-data-types-composite.md)
