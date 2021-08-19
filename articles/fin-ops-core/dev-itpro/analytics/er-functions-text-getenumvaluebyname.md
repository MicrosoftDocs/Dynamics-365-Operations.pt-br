---
title: Função de ER GETENUMVALUEBYNAME
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) GETENUMVALUEBYNAME é usada.
author: NickSelin
ms.date: 09/23/2020
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
ms.openlocfilehash: 03759852e5ceb13b79b0df4592bdcef76eb0a82865725c00df40b9cc5f786240
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6774428"
---
# <a name="getenumvaluebyname-er-function"></a>Função de ER GETENUMVALUEBYNAME

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

## <a name="example-1"></a>Exemplo 1

Na ilustração a seguir, a enumeração de **ReportDirection** é apresentada em um modelo de dados. Observe que os rótulos são definidos para os valores de enumeração.

![Valores disponíveis para uma enumeração de modelo de dados.](./media/ER-data-model-enumeration-values.PNG)

A ilustração a seguir mostra estes detalhes:

- A fonte de dados **$Direction** é configurada em um relatório de ER. Essa fonte de dados é configurada com base na enumeração do modelo **ReportDirection**.
- A expressão `$IsArrivals` foi criada para usar a fonte de dados **$Direction** baseada na enumeração do modelo como um parâmetro desta função.
- O valor dessa expressão de comparação é **TRUE**.

![Exemplo de enumeração de modelo de dados.](./media/ER-data-model-enumeration-usage.PNG)

## <a name="example-2"></a>Exemplo 2

As funções `GETENUMVALUEBYNAME` e [`LISTOFFIELDS`](er-functions-list-listoffields.md) permitem buscar valores e etiquetas de enumerações com suporte como valores de texto. (As enumerações com suporte são enumerações de aplicativo, enumerações de modelo de dados e enumerações de formato.)

Na ilustração a seguir, a fonte de dados **TransType** é apresentada em um mapeamento de modelo. Essa fonte de dados refere-se à enumeração de aplicativo **LedgerTransType**.

![Fonte de dados de um mapeamento de modelo que se refere a uma enumeração de aplicativo.](./media/er-functions-text-getenumvaluebyname-example2-1.png)

A ilustração a seguir mostra a fonte de dados **TransTypeList** configurada em um mapeamento de modelo. Essa fonte de dados é configurada com base na enumeração do aplicativo **TransType**. A função `LISTOFFIELDS` é usada para retornar todos os valores de enumeração como uma lista de registros que contêm campos. Dessa forma, os detalhes de cada valor de enumeração são expostos.

> [!NOTE]
> O campo **EnumValue** é configurado para a fonte de dados **TransTypeList** usando a expressão `GETENUMVALUEBYNAME(TransType, TransTypeList.Name)`. Esse campo retorna um valor de enumeração para cada registro nessa lista.

![Fonte de dados de um mapeamento de modelo que retorna todos os valores de enumeração de uma enumeração selecionada como uma lista de registros.](./media/er-functions-text-getenumvaluebyname-example2-2.png)

A ilustração a seguir mostra a fonte de dados **VendTrans** configurada em um mapeamento de modelo. Essa fonte de dados retorna registros de transações do fornecedor da tabela de aplicativos **VendTrans**. O tipo de razão de cada transação é definido pelo valor do campo **TransType**.

> [!NOTE]
> O campo **TransTypeTitle** é configurado para a fonte de dados **VendTrans** usando a expressão `FIRSTORNULL(WHERE(TransTypeList, TransTypeList.EnumValue = @.TransType)).Label`. Esse campo retorna o rótulo de um valor de enumeração da transação atual como texto, se esse valor de enumeração estiver disponível. Caso contrário, ele retorna um valor de cadeia de caracteres em branco.
>
> O campo **TransTypeTitle** está vinculado ao campo **LedgerType** de um modelo de dados que permite que essas informações sejam usadas em todos os formatos ER que usam o modelo de dados como fonte de dados.

![Fonte de dados de um mapeamento de modelo que retorna as transações do fornecedor.](./media/er-functions-text-getenumvaluebyname-example2-3.png)

A ilustração a seguir mostra como você pode usar o [depurador da fonte de dados](er-debug-data-sources.md) para testar o mapeamento do modelo configurado.

![Uso do depurador de fonte de dados para testar o mapeamento do modelo configurado.](./media/er-functions-text-getenumvaluebyname-example2-4.gif)

O campo **LedgerType** de um modelo de dados expõe etiquetas de tipos de transação conforme o esperado.

Se você planeja usar essa abordagem para uma grande quantidade de dados transacionais, deve considerar o desempenho de execução. Para obter mais informações, consulte [Rastrear a execução de formatos de ER para solucionar problemas de desempenho](trace-execution-er-troubleshoot-perf.md).

## <a name="additional-resources"></a>Recursos adicionais

[Funções de texto](er-functions-category-text.md)

[Rastrear a execução de formatos de ER para solucionar problemas de desempenho](trace-execution-er-troubleshoot-perf.md)

[Função de ER LISTOFFIELDS](er-functions-list-listoffields.md)

[Função de ER FIRSTORNULL](er-functions-list-firstornull.md)

[Função de ER WHERE](er-functions-list-where.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]