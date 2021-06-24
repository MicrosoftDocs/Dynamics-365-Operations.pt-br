---
title: Linguagem da fórmula de relatório eletrônico
description: Este tópico fornece informações sobre como usar o idioma de fórmulas no relatório eletrônico (ER).
author: NickSelin
ms.date: 05/04/2020
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
ms.openlocfilehash: 470b4fa1c8b15ae4a9e9ebef81af9e4ca107422d
ms.sourcegitcommit: 15aacd0e109b05c7281407b5bba4e6cd99116c28
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "6223977"
---
# <a name="electronic-reporting-formula-language"></a>Linguagem da fórmula de relatório eletrônico

[!include [banner](../includes/banner.md)]

O relatório eletrônico (ER) oferece uma poderosa experiência de transformação de dados. O idioma usado para expressar as manipulações de dados necessárias no designer de [fórmulas ERr](general-electronic-reporting-formula-designer.md) é semelhante ao idioma da fórmula no Microsoft Excel.

## <a name="basic-syntax"></a>Sintaxe básica

As expressões de ER podem conter alguns ou todos os elementos da seguir:

- [Constantes](#Constants)
- [Operadores](#Operators)
- [Referências](#References)
- [Caminhos](#Paths)
- [Funções](#Functions)

## <a name="constants"></a><a name="Constants"></a>Constantes

Quando você cria expressões, você pode usar constantes numéricas e de texto (isto é, valores que não são calculados). Por exemplo, a expressão `VALUE ("100") + 20` usa a constante numérica **20** e a cadeia constante **“100”**, e ele devolve o valor numérico **120**.

O designer da fórmula de ER suporta sequências de escape. Portanto, você pode especificar uma sequência de caracteres da expressão que deve ser tratada de maneira diferente. Por exemplo, a expressão `"Leo Tolstoy ""War and Peace"" Volume 1"` retorna a sequência de caracteres de texto **Leo Tolstoy "War and Peace" Volume 1**.

## <a name="operators"></a><a name="Operators"></a>Operadores

A tabela a seguir mostra os operadores aritméticos que você pode usar para executar operações matemáticas, como adição, subtração, multiplicação e divisão.

| Operador | Significado               | Exemplo     |
|----------|-----------------------|-------------|
| +        | Adição              | `1+2`       |
| -        | Subtração, negação | `5-2`, `-1` |
| \*       | Multiplicação        | `7\*8`      |
| /        | Divisão              | `9/3`       |

A tabela a seguir mostra os operadores de comparação que são suportados. Você pode usar esses operadores para comparar dois valores.

| Operador | Significado                  | Exemplo      |
|----------|--------------------------|--------------|
| =        | Equivalente                    | `X=Y`        |
| &gt;     | Maior que             | `X>Y`        |
| &lt;     | Menor que                | `X<Y`        |
| &gt;=    | Maior que ou igual a | `X>=Y`       |
| &lt;=    | Menor que ou igual a    | `X<=Y`       |
| &lt;&gt; | Diferente de             | `X<>Y`       |

Além disso, você pode usar um E comercial (&) como um operador de concatenação de texto. Assim, você pode adicionar, ou concatenar, uma ou mais sequências de texto em uma única parte do texto.

| Operador | Significado     | Exemplo                                               |
|----------|-------------|-------------------------------------------------------|
| &        | Concatenar | `"Nothing to print:" & " " & "no records found"`      |

### <a name="operator-precedence"></a>Precedência do operador

A ordem em que as partes de uma expressão composta são avaliadas é importante. Por exemplo, o resultado da expressão `1 + 4 / 2` varia, dependendo de qual adição ou divisão é executada primeiro. Você pode usar parênteses para definir explicitamente como uma expressão será avaliada. Por exemplo, para indicar que a operação de adição deve ser executada primeiro, você pode alterar a expressão precedente para `(1 + 4) / 2`. Se não indicar explicitamente a ordem das operações em uma expressão, a ordem será baseada na precedência padrão atribuída aos operadores suportados. A tabela a seguir mostra a precedência que está atribuída a cada operador. Os operadores que têm uma precedência maior (por exemplo, 7) são avaliados antes dos operadores que têm uma precedência menor (por exemplo, 1).

| Precedência | Operadores      | Sintaxe                                                                  |
|------------|----------------|-------------------------------------------------------------------------|
| 7          | Agrupamento       | ( … )                                                                   |
| 6          | Acesso do membro  | … . …                                                                   |
| 5          | Chamada de função  | … ( … )                                                                 |
| 4          | Multiplicativo | … \* …<br>… / …                                                         |
| 3          | Aditivo       | … + …<br>… - …                                                          |
| 2          | Comparação     | … &lt; …<br>… &lt;= …<br>… =&gt; …<br>… &gt; …<br>… = …<br>… &lt;&gt; … |
| 1          | Separação     | … , …                                                                   |

Se uma expressão tiver vários operadores consecutivos com a mesma precedência, essas operações serão avaliadas da esquerda para a direita. Por exemplo, a expressão `1 + 6 / 2 \* 3 > 5` retorna **verdadeiro**. É recomendável usar parênteses para indicar explicitamente a ordem desejada das operações nas expressões, de forma que as expressões fiquem mais fáceis de ler e manter.

## <a name="references"></a><a name="References"></a>Referências

Todas as fontes de dados do componente do ER atual que estão disponíveis durante a criação de uma expressão podem ser usadas como referências nomeadas. O componente ER atual pode ser um mapeamento de modelo ou um formato. Por exemplo, o atual mapeamento de modelo do ER contém a fonte de dados **ReportingDate**, que retorna um valor do tipo de dados [*DateTime*](er-formula-supported-data-types-primitive.md#datetime). Para formatar corretamente esse valor no documento gerado, você pode fazer referência à fonte de dados na expressão como `DATETIMEFORMAT (ReportingDate, "dd-MM-yyyy")`.

Todos os caracteres no nome de uma fonte de dados de referência que não representam uma letra de alfabeto devem ser precedidos por aspas simples ('). Se o nome de uma fonte de dados de referência contiver pelo menos um símbolo que não representa uma letra de alfabeto, o nome deve ser colocado entre aspas simples. Por exemplo, estes símbolos não alfabéticos podem ser marcas de pontuação ou outros símbolos escritos. Eis alguns exemplos:

- A fonte de dados **Data e hora de hoje** deve ser referenciada em uma expressão de ER como `'Today''s date & time'`.
- O método **name()** da fonte de dados **Customers** deve ser referenciado na expressão de ER da seguinte maneira `Customers.'name()'`.

Se os métodos de fontes de dados do aplicativo tiverem parâmetros, a seguinte sintaxe será usada para chamar esses métodos:

- Se o método **isLanguageRTL** da fonte de dados **Sistema** tiver um parâmetro **EN-US** do tipo de dados [*Cadeia*](er-formula-supported-data-types-primitive.md#string), este método deve ser referenciado em uma expressão do ER como `System.isLanguageRTL("EN-US")`.
- Não é obrigatório o uso de aspas quando um nome de método contiver apenas símbolos alfanuméricos. Porém elas são obrigatórias para o método de uma tabela, se o nome tiver colchetes.

Quando a fonte de dados **Sistema** é adicionada a um mapeamento de ER que se refere à classe do aplicativo **Global**, a expressão `System.isLanguageRTL("EN-US ")` retorna o valor *booliano* como **FALSE**. A expressão modificada `System.isLanguageRTL("AR")` retorna o valor *Booliano* **TRUE**.

Você pode delimitar a maneira como os valores são passados para parâmetros desse tipo de método:

- Apenas as constantes podem ser aprovadas para os métodos deste tipo. Os valores das constantes são definidos no tempo de design.
- Somente os tipos de dados (básicos) [primitivos](er-formula-supported-data-types-primitive.md) são compatíveis para parâmetros deste tipo. Os tipos de dados primitivos incluem *Inteiro*, *Real*, *Booliano* e *Cadeia de caracteres*.

## <a name="paths"></a><a name="Paths"></a>Caminhos

Quando uma expressão referencia uma fonte de dados estruturada, você pode usar a definição do caminho para selecionar um elemento específico primitivo dessa fonte de dados. Um caractere de ponto (.) é usado para separar os elementos individuais de uma fonte de dados estruturada. Por exemplo, o modelo atual de mapeamento ER contém a fonte de dados **InvoiceTransactions** e essa origem de dados retorna uma lista de registros. A estrutura de registro **InvoiceTransactions** contém os campos **AmountDebit** e **AmountCredit** e esses campos retornam valores numéricos. Portanto, você pode criar a seguinte expressão para calcular o valor faturado: `InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit`. A construção `InvoiceTransactions.AmountDebit` nessa expressão é o caminho usado para acessar o campo **AmountDebit** da fonte de dados **InvoiceTransactions** do tipo de *Lista de registros*.

### <a name="relative-path"></a>Caminho relativo

Se o caminho de uma fonte de dados estruturada começar com um sinal de "arroba" (@), é um caminho relativo. O sinal de "at" é mostrado em vez da parte restante do caminho absoluto da estrutura de árvore hierárquica que é usada. A ilustração a seguir mostra um exemplo. Aqui, o caminho absoluto `Ledger.'accountingCurrency()'` indica que o valor da moeda contábil da fonte de dados **Razão** é inserido no campo **AccountingCurrency** do modelo de dados.

![Exemplo de um caminho absoluto na página do designer de mapeamento do modelo ER](./media/ER-FormulaLanguage-AbsolutePath.png)

O exemplo na ilustração a seguir mostra como um caminho relativo é usado. O caminho relativo `@.AccountNum` indica que o campo **AccountNum** da fonte de dados **Intrastat** (que aparece um nível acima do campo **AccountNum** na árvore hierárquica do modelo de dados) é usado para inserir o número de conta do cliente ou do fornecedor no campo **AccountNum** do modelo de dados.

![Exemplo de um caminho relativo na página do designer de mapeamento do modelo ER](./media/ER-FormulaLanguage-RelativePath1.png)

A parte restante do caminho absoluto também é mostrada no [Editor de fórmula ER](general-electronic-reporting-formula-designer.md).

![Parte restante do caminho absoluto na página do designer de fórmula ER](./media/ER-FormulaLanguage-RelativePath2.png)

Para obter mais informações, consulte [Usar um caminho relativo em associações de dados de modelos e formatos de ER](relative-path-data-bindings-er-models-format.md).

## <a name="functions"></a><a name="Functions"></a>Funções

As funções internas do ER podem ser usadas em expressões ER. Todas as fontes de dados do contexto da expressão (ou seja, modelo atual do mapeamento ER ou formato ER) podem ser usadas como parâmetros de funções de chamada, de acordo com a lista de argumentos das funções de chamada. As constantes também podem ser usadas como parâmetros de funções de chamada. Por exemplo, o modelo atual de mapeamento ER contém a fonte de dados **InvoiceTransactions** e essa origem de dados retorna uma lista de registros. A estrutura de registro **InvoiceTransactions** contém os campos **AmountDebit** e **AmountCredit** e esses campos retornam valores numéricos. Portanto, para calcular o valor faturado, você pode criar a seguinte expressão que usa a função de arredondamento de ER incorporada: `ROUND (InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit, 2)`.

Ao criar mapeamentos de modelo de ER e relatórios ER, você pode usar as funções ER das seguintes categorias:

- [Funções de data e de hora](er-functions-category-datetime.md)
- [Funções de listagem](er-functions-category-list.md)
- [Funções lógicas](er-functions-category-logical.md)
- [Funções matemáticas](er-functions-category-mathematical.md)
- [Funções de registro](er-functions-category-record.md)
- [Funções de texto](er-functions-category-text.md)
- [Funções de coleta de dados](er-functions-category-data-collection.md)
- [Outras funções (específicas de domínio comercial)](er-functions-category-other.md)
- [Funções de conversão de tipo](er-functions-category-type-conversion.md)

## <a name="functions-list-extension"></a>Extensão da lista de funções

ER deixa você estender a lista de funções que são usadas em expressões ER. Isso exige alguns esforços de engenharia. Para informações detalhadas, consulte [Estender a lista de funções do ER (Relatórios eletrônicos)](general-electronic-reporting-formulas-list-extension.md).

## <a name="compound-expressions"></a>Expressões compostas

Você pode criar expressões compostas que usam funções de diferentes categorias, desde que os tipos de dados coincidam. Ao usar funções juntas, relacione o tipo de dados da saída de uma função ao tipo de dados de entrada exigido por outra função. Por exemplo, para evitar um erro de "lista está vazia" possível em uma associação de um campo a um elemento de formato ER, combine funções da categoria [Lista](er-functions-category-list.md) com uma função da categoria [Lógica](er-functions-category-logical.md), como mostra o exemplo a seguir. Aqui, a fórmula usa a função [IF](er-functions-logical-if.md) para testar se a lista **IntrastatTotals** está vazia antes de retornar o valor da agregação necessária nessa lista. Se a lista **IntrastatTotals** estiver vazia, a fórmula retornará **0** (zero).

```vb
IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded') 
```

## <a name="multiple-solutions"></a>Várias soluções

Geralmente, você pode obter o mesmo resultado de transformação de dados de várias formas, usando funções de diferentes categorias ou funções diferentes da mesma categoria. Por exemplo, a expressão anterior também pode ser configurada usando a função [COUNT](er-functions-list-count.md) da categoria [Lista](er-functions-category-list.md).

```vb
IF(COUNT (IntrastatTotals)=0, 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded') 
```

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do Relatório Eletrônico](general-electronic-reporting.md)

[Designer de fórmulas no Relatório eletrônico](general-electronic-reporting-formula-designer.md)

[Estender a lista de funções de Relatório eletrônico](general-electronic-reporting-formulas-list-extension.md)

[Tipos de dados primitivos compatíveis](er-formula-supported-data-types-primitive.md)

[Tipos de dados compostos compatíveis](er-formula-supported-data-types-composite.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
