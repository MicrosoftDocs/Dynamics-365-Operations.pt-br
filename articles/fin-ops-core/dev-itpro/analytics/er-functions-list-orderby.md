---
title: Função de ER ORDERBY
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) ORDERBY é usada.
author: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 23ace859bf75b2adb6ef8604475519a015486948
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282551"
---
# <a name="orderby-er-function"></a>Função de ER ORDERBY

[!include [banner](../includes/banner.md)]

A função `ORDERBY` retorna a lista especificada como um valor de *Lista de registros* após ela ser classificada de acordo com os argumentos especificados. Esses argumentos podem ser definidos como expressões.

## <a name="syntax-1"></a><a name="syntax-1"></a>Sintaxe 1

```vb
ORDERBY (list, expression 1[, expression 2, …, expression N])
```

## <a name="syntax-2"></a><a name="syntax-2"></a>Sintaxe 2

```vb
ORDERBY (location, list, expression 1[, expression 2, …, expression N])
```

> [!NOTE]
> Esta sintaxe é compatível com o Microsoft Dynamics 365 Finance versão 10.0.25 e posterior.

## <a name="arguments"></a>Argumentos

`location`: *[Cadeia de caracteres](er-formula-supported-data-types-primitive.md#string)*

O local em que a classificação deve ser executada. As seguintes opções são válidas:

- "Consulta"
- "InMemory"

`list`: *[Lista de registros](er-formula-supported-data-types-composite.md#record-list)*

O caminho válido de uma fonte de dados do tipo *Lista de registros*.

`expression 1`: *Campo*

O caminho válido de um campo da fonte de dados que é referenciado pelo argumento `list` da função chamada. O campo referenciado deve ser um campo do tipo de dados primitivo. Esse argumento é obrigatório.

`expression N`: *Campo*

O caminho válido de um campo da fonte de dados que é referenciado pelo argumento `list` da função chamada. O campo referenciado deve ser um campo do tipo de dados primitivo. Esses argumentos adicionais são opcionais.

## <a name="return-values"></a>Valores de retorno

*Registrar lista*

A lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

### <a name="syntax-1"></a>Sintaxe 1

A classificação de dados sempre é feita na memória do servidor de aplicativos. Para obter mais detalhes, consulte [exemplo 1](#example-1).

### <a name="syntax-2"></a>Sintaxe 2

### <a name="sorting-in-memory"></a>Classificação na memória

Quando o argumento `location` é especificado como **InMemory**, a classificação de dados é realizada na memória de um servidor de aplicativos. Para obter mais detalhes, consulte [exemplo 2](#example-2).

### <a name="sorting-in-database"></a>Classificar no banco de dados

Quando o argumento `location` é especificado como **Consulta**, a classificação de dados é feita no nível do banco de dados. Nesse caso, o argumento `list` deve apontar para uma das seguintes fontes de dados de [relatório eletrônico (ER)](general-electronic-reporting.md) que especifica a origem do aplicativo para a qual uma consulta de banco de dados direta pode ser estabelecida:

- Fonte de dados do tipo *Registros de tabela*
- Relação de uma fonte de dados do tipo *Registros de tabela*
- Fonte de dados do tipo *Campo de cálculo*

Os argumentos `expression 1` e `expression N` devem apontar para campos de uma fonte de dados de ER que especifique os campos relevantes da origem do aplicativo para a qual uma consulta de banco de dados direta também possa ser estabelecida.

Se não for possível estabelecer uma consulta direta de banco de dados, ocorrerá um [erro](er-components-inspections.md#i18) de validação no designer de mapeamento de modelo de ER. A mensagem recebida informa que a expressão de ER que inclui a função `ORDERBY` não pode ser executada no runtime.

Para obter um melhor desempenho, é recomendável usar a opção **Consulta** quando a classificação estiver configurada para fontes de dados de aplicativos que possam conter o grande número de registros (por exemplo, para tabelas de aplicativos transacionais).

> [!NOTE]
> A função `ORDEBY` em si não pode ser convertida em uma consulta direta de banco de dados. Portanto, uma fonte de dados ER contendo essa função não é consultável. Também não pode ser usado no escopo de funções ER como [FILTER](er-functions-list-filter.md) e [ALLITEMSQUERY](er-functions-list-allitemsquery.md), em que somente as fontes de dados consultáveis podem ser usadas.

Para obter mais detalhes, consulte [exemplo 3](#example-3) e [exemplo 4](#example-4).

### <a name="comparability"></a>Comparabilidade

Como o mecanismo de banco de dados SQL e o servidor de aplicativos Finance podem usar um valor de classificação diferente para um único caractere, o resultado da classificação da mesma lista de registros pode ser diferente quando um campo [Cadeia de caracteres](er-formula-supported-data-types-primitive.md#string) é usado para classificação. Para obter mais detalhes, consulte [exemplo 5](#example-5).

## <a name="example-1-in-memory-default-execution"></a><a name="example-1"></a>Exemplo 1: execução padrão na memória

Se você inserir a fonte de dados **DS** do tipo *Campo calculado* e ela contiver a expressão `SPLIT ("C|B|A", "|")`, a expressão `FIRST( ORDERBY( DS, DS. Value)).Value` retornará o valor de texto **"A"**.

## <a name="example-2-in-memory-explicit-execution"></a><a name="example-2"></a>Exemplo 2: execução explícita na memória

Se **Fornecedor** estiver configurado como uma fonte de dados ER do tipo *Registros de tabela* que se refere à tabela **VendTable**, as expressões `ORDERBY (Vendor, Vendor.'name()')` e `ORDERBY ("InMemory", Vendor, Vendor.'name()')` retornarão uma lista de fornecedores que é classificada por nome em ordem crescente.

Quando você configura a expressão `ORDERBY ("Query", Vendor, Vendor.'name()')` no designer de mapeamento do modelo ER, um [erro](er-components-inspections.md#i8) de validação ocorre no tempo de design, porque o caminho `Vendor.'name()'` se refere a um método de aplicativo que tem lógica que não pode ser convertida em uma consulta direta do banco de dados.

## <a name="example-3-database-query"></a><a name="example-3"></a>Exemplo 3: consulta de banco de dados

Se **TaxTransaction** estiver configurado como uma fonte de dados ER do tipo de *Registros de tabela* que se refere à tabela **TaxTrans**, a expressão `ORDERBY ("Query", TaxTransaction, TaxTransaction.TaxCode)` classificará registros no nível de banco de dados do aplicativo e retornará uma lista de transações de imposto classificada por código de imposto em ordem crescente.

## <a name="example-4-queryable-data-sources"></a><a name="example-4"></a>Exemplo 4: fontes de dados consultáveis

Se **TaxTransaction** estiver configurado como uma fonte de dados ER do tipo *Registros de tabela* que se refere à tabela **TaxTrans**, a fonte de dados ER **TaxTransactionFiltered** poderá ser configurada para que contenha a expressão `FILTER(TaxTransaction, TaxCode="VAT19")` que buscará transações para um código de imposto especificado. Como a fonte de dados ER **TaxTransactionFiltered** configurada é consultável, a expressão `ORDERBY ("Query", TaxTransactionFiltered, TaxTransactionFiltered.TransDate)` pode ser configurada para retornar a lista de transações de impostos filtrados classificadas por data de transação em ordem crescente.

Se você configurar **TaxTransactionOrdered** como uma fonte de dados ER do tipo *Campo calculado* que contém a expressão `ORDERBY ("Query", TaxTransaction, TaxTransaction.TransDate)` e uma fonte de dados ER do tipo *Campo calculado* contendo a expressão `FILTER(TaxTransactionOrdered, TaxCode="VAT19")`, ocorrerá um [erro](er-components-inspections.md#i18) de validação no tempo de design no designer de mapeamento do modelo ER. Esse erro ocorre porque o primeiro argumento da função [FILTER](er-functions-list-filter.md#usage-notes) deve se referir a uma fonte de dados ER consultável, mas a fonte de dados **TaxTransactionOrdered** que contém a função `ORDERBY` não pode ser consultada.

## <a name="example-5-comparability"></a><a name="example-5"></a>Exemplo 5: comparabilidade

### <a name="prerequisites"></a>Pré-requisitos

1. Insira a fonte de dados **DS1** do tipo *Campo calculado* que contém a expressão `SPLIT ("D1|_D2|D3", "|")`.
2. Abra a página **[Valores de dimensão financeira](../../../finance/general-ledger/financial-dimensions.md)** e selecione a dimensão **CostCenter**.
3. Insira os seguintes valores de dimensão: **D1**, **\_D2** e **D3**.

### <a name="sorting-in-memory"></a>Classificação na memória

1. Configure uma fonte de dados **DS2** do tipo *Campo calculado* que contém a expressão `ORDERBY("InMemory", DS1, DS1.Value)`.
2. Observe que a expressão `FIRST(DS2).Value` retorna o valor de texto **"D1"**, a expressão `INDEX(DS2, COUNT(DS2)).Value` retorna o valor de texto **"\_D2"** e a expressão `STRINGJOIN(DS2, DS2.Value, "|")` retorna o valor de texto **"D1\|D3\|\_D2"**.

### <a name="sorting-in-database"></a>Classificar no banco de dados

1. Insira uma fonte de dados **DS3** do tipo *Registros de tabela* que se refere à entidade **FinancialDimensionValueEntity**.
2. Configure uma fonte de dados **DS4** do tipo *Campo calculado* que contém a expressão `FILTER(DS3, DS3.FinancialDimension="CostCenter")`.
3. Configure uma fonte de dados **DS5** do tipo *Campo calculado* que contém a expressão `ORDERBY(DS4, DS4.DimensionValue)`.
4. Observe que a expressão `FIRST(DS5).Value` retorna o valor de texto **"\_D2"**, a expressão `INDEX(DS5, COUNT(DS5)).Value` retorna o valor de texto **"D3"** e a expressão `STRINGJOIN(DS5, DS5.Value, "|")` retorna o valor de texto **"\_D2\|D1\|D3"**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
