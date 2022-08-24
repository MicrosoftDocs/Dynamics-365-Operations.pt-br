---
title: Tipos de dados compostos compatíveis para fórmulas do Relatório Eletrônico
description: Este artigo fornece informações sobre os tipos de dados compostos que são compatíveis nas fórmulas do ER (Relatório Eletrônico).
author: kfend
ms.date: 06/02/2021
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: ea6f8ab1f0cd26fd2414a17be559aa60fc52e7d3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272702"
---
# <a name="supported-composite-data-types-for-electronic-reporting-formulas"></a>Tipos de dados compostos compatíveis para fórmulas do Relatório Eletrônico

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre os tipos de dados compostos que são compatíveis nas expressões do [ER (Relatório Eletrônico)](general-electronic-reporting.md). Os tipos de dados compostos são [classe](#class), [contêiner](#container), [registro](#record), [lista de registros](#record-list) e [objeto](#object).

## <a name="class"></a><a name="class"></a>Classe

O tipo de dado *classe* refere-se a uma classe de aplicativo público. No ER, ela é representada como um [*registro*](#record) que contém um campo separado para cada método público da classe referenciada. Quando a chamada do método é parametrizado, você também deve especificar os argumentos necessários dos tipos adequados em uma expressão do ER que seja configurada para chamar o método.

Nos componentes de mapeamento e formato de ER, você pode adicionar a fonte de dados **Classe** que é apresentada como fonte de dados e retorna um valor do tipo *classe*. Esta fonte de dados expõe os métodos públicos da classe que pode ser chamada no runtime.

> [!NOTE]
> Somente os métodos que retornam um valor podem ser chamados de expressões do ER.
>
> Somente os métodos que têm um intervalo de zero a oito argumentos podem ser chamados de expressões do ER.

O valor padrão de uma *classe* é **nulo**.

A ilustração a seguir mostra como a fonte de dados **Informações do sistema(xInfo)** do tipo **Classe** é adicionada para criar a instância da classe de aplicativo **xInfo** e chamar seu método **productName()** para receber o nome do aplicativo atual. O nome do aplicativo atual é obtido no runtime executando a vinculação `xInfo.productName` que foi configurada para o campo **Nome do software(SoftwareName)** do modelo de dados do ER. Esta vinculação chama o método do `productName()` da classe de aplicativo **xInfo** que é representada no mapeamento do modelo atual como a fonte de dados **Informações do sistema(xInfo)**.

[![Configurar uma fonte de dados Classe no designer de mapeamento de modelo do ER.](./media/er-formula-supported-data-types-composite-class1.gif)](./media/er-formula-supported-data-types-composite-class1.gif)

A ilustração a seguir mostra como o formato do ER é configurado para inserir o nome do aplicativo fornecido nos documentos gerados. O campo **Nome do software(SoftwareName)** do modelo de dados usado foi vinculado ao componente **Cadeia de caracteres** que está aninhado no no elemento XML **softwareUsed** do formato ER. Portanto, o nome do aplicativo atual é inserido no runtime para o elemento XML **softwareUsed** de um documento gerado no formato XML.

[![Configurar a estrutura de um documento eletrônico de saída no designer de formatos do ER.](./media/er-formula-supported-data-types-composite-class2.png)](./media/er-formula-supported-data-types-composite-class2.png)

## <a name="container"></a><a name="container"></a>Contêiner

O tipo de dados *contêiner* contém conteúdo binário. Um valor de *contêiner* pode ser usado para passar informações específicas do armazenamento para um documento gerado. Na estrutura do ER, este tipo de dados costuma ser usado para inserir conteúdo de mídia, como um logotipo de empresa, nos documentos gerados.

> [!NOTE]
> Embora todo item de mídia possa ser representado como um valor de *contêiner*, nem todo valor de *contêiner* representa um item de mídia. Portanto, se você configurar um formato do ER para que ele use um *contêiner* para inserir uma imagem nos documentos gerados, mas o *contêiner* referenciado não retornar conteúdo de mídia, uma excepção que lembra o seguinte exemplo pode ser lançada: "Erro ao executar o código: Binário (objeto), método constructFromContainer chamado com parâmetros inválidos".

O valor padrão de um *contêiner* é **nulo**.

A seguinte ilustração mostra como o campo **Bitmap(Image)** do tipo *Contêiner* é vinculado ao campo **Logotipo** do modelo de dados do tipo **Contêiner** no mapeamento de modelo **Fatura de venda**. A vinculação torna o logotipo da empresa disponível para qualquer formato do ER que seja atribuído para a definição raiz **SalesInvoice** e que use este mapeamento de modelo no runtime.

[![Vincular um campo do tipo Contêiner no designer de mapeamento de modelo do ER.](./media/er-formula-supported-data-types-composite-container.png)](./media/er-formula-supported-data-types-composite-container.png)

## <a name="record"></a><a name="record"></a>Registro

Um *registro* é uma coleção de campos nomeados, e cada um é associado com um valor de um tipo de dados [primitivo](er-formula-supported-data-types-primitive.md) ou de um tipo de dados composto. Geralmente, um *registro* é usado para representar um único registro de uma lista de registros. Neste caso, todo item representa campos, métodos e relações individuais.

O valor padrão de um *registro* é **vazio**.

> [!NOTE]
> Quando você obtém o valor de um campo de um *registro* vazio, o valor padrão do tipo de dados apropriado é retornado.

Um *registro* pode ser obtida usando as seguintes funções:

- [FIRST](er-functions-list-first.md)
- [FIRSTORNULL](er-functions-list-firstornull.md)
- [EMPTYRECORD](er-functions-record-emptyrecord.md)
- [NULLCONTAINER](er-functions-record-nullcontainer.md)

Para obter mais informações sobre a transformação de valores de *registro*, consulte [Lista de funções do ER na categoria de lista](er-functions-category-list.md).

## <a name="record-list"></a><a name="record-list"></a>Registrar lista

Uma *lista de registros* é uma lista de itens do tipo *registro*. Geralmente, uma *lista de registros* é usado para representar a lista de registros que foi recuperada de uma tabela do banco de dados.

Por padrão, os registros de uma *lista de registro* são acessados sequencialmente. Para acessar um registro específico, você pode usar a função [INDEX](er-functions-list-index.md) e especifique o índice *inteiro*.

O valor padrão de uma *lista de registros* é **vazio**. Você pode usar a função [ISEMPTY](er-functions-list-isempty.md) para avaliar se uma *lista de registros* está vazia.

> [!NOTE]
> Se uma *lista de registros* estiver vazia, qualquer tentativa de obter um valor de campo para um *registro* nele faz com que uma exceção seja lançada no runtime. Para saber como você pode ajudar a evitar exceções no runtime deste tipo, consulte [Consideração de casos de lista vazia](er-components-inspections.md#i9).

Uma *lista de registros* pode ser iniciada usando as seguintes funções:

- [ALLITEMS](er-functions-list-allitems.md)
- [ALLITEMSQUERY](er-functions-list-allitemsquery.md)
- [EMPTYLIST](er-functions-list-emptylist.md)
- [LIST](er-functions-list-list.md)
- [LISTDISTINCT](er-functions-list-listdistinct.md)

Para obter mais informações sobre a transformação de valores de *lista de registros*, consulte [Lista de funções do ER na categoria de lista](er-functions-category-list.md). Para saber como introduzir itens de *lista de registros*, preenchê-los com os dados do aplicativo e então usar os dados para gerar documentos de negócios, consulte [Desenvolver uma nova solução do ER para imprimir um relatório personalizado](er-quick-start1-new-solution.md).

## <a name="object"></a><a name="object"></a>Objeto

Um *objeto* refere-se a uma instância com estado de uma *classe*. Geralmente, um *objeto* é iniciado no código fonte. Em seguida, ele é passado para um mapeamento de modelo do ER e fornece detalhes sobre o contexto da execução.

O valor padrão de um *objeto* é **nulo**.

A seguinte ilustração mostra como a fonte de dados **ReportDataContract** do tipo *Objeto* é adicionada para passar informações sobre uma fatura gerada de um código fonte para o mapeamento de modelo **Fatura do projeto**. Por exemplo, o texto da instância da fatura é passado como parte do contexto de execução. Este texto é obtido do código fonte no runtime executando a vinculação `ReportDataContract.parmInvoiceInstanceText` que foi configurada para o campo **Nota** do modelo de dados do ER. Esta vinculação chama o método do `parmInvoiceInstanceText()` da classe de aplicativo **PSAProjInvoiceContract** que é representada no mapeamento do modelo atual como a fonte de dados **ReportDataContract**.

[![Configurar uma fonte de dados Objeto no designer de mapeamento de modelo do ER.](./media/er-formula-supported-data-types-composite-object.gif)](./media/er-formula-supported-data-types-composite-object.gif)

Para saber como passar detalhes sobre o contexto de execução do código fonte para a solução do ER em execução, consulte [Desenvolver artefatos de aplicativo para chamar o relatório atribuído](er-quick-start1-new-solution.md#DevelopCustomCode).

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral do Relatório Eletrônico](general-electronic-reporting.md)
- [Linguagem da fórmula de relatório eletrônico](er-formula-language.md)
- [Tipos de dados primitivos compatíveis](er-formula-supported-data-types-primitive.md)
