---
title: Modificar células de definição de linha
description: Este artigo descreve as informações que são necessárias para cada célula em uma definição de linha em um relatório financeiro e explica como inserir essas informações.
author: ShylaThompson
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 58881
ms.assetid: 0af492df-a84e-450c-8045-78ef1211abaf
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b06c59e3ec35d0eea7fc4b81af540e0bcca144fb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905102"
---
# <a name="modify-row-definition-cells"></a>Modificar células de definição de linha

[!include [banner](../includes/banner.md)]

Este artigo descreve as informações que são necessárias para cada célula em uma definição de linha em um relatório financeiro e explica como inserir essas informações.

## <a name="specify-a-row-code-in-a-row-definition"></a>Especifique um código de linha em uma definição de linha

Em definições de linha, os números ou rótulos na célula **Código da Linha** identificam cada linha na definição de linha. É possível especificar o código de linha para referir-se aos dados nos cálculos e totais.

### <a name="row-code-requirements"></a>Requisitos do código de linha

Um código de linha é necessário para todas as linhas. Você pode misturar códigos de linha numéricos, alfanuméricos e não definidos (vazios) em uma definição de linha. O código de linha pode ser qualquer inteiro positivo (abaixo de 100.000.000) ou uma etiqueta descritiva que identifica a linha. Uma etiqueta descritiva deve seguir estas regras:

- O rótulo deve começar com um caractere alfabético (de a até z ou de A até Z), e pode ser qualquer combinação de letras e números com até 16 caracteres.

    > [!NOTE]
    > Um rótulo pode incluir o caractere sublinhado (\_), mas outros caracteres especiais não são permitidos.

- O rótulo não pode usar as seguintes palavras reservadas: AND, OR, IF, THEN, ELSE, PERIODS, TO, BASEROW, UNIT, NULL, CPO ou RPO.

Os seguintes exemplos são códigos de linha válidos:

- 320
- TL\_NET\_INCOME
- TL\_NET\_94

### <a name="change-a-row-code-in-a-row-definition"></a>Altere um código de linha em uma definição de linha

1. No Designer de Relatórios, clique em **Definições de Linha** e abra a definição de linha para modificá-la.
2. Na linha apropriada, insira o novo valor na célula na coluna **Código de Linha**.

### <a name="reset-numeric-row-codes"></a>Redefinir códigos de linha numéricos

1. No Designer de Relatórios, clique em **Definições de Linha** e abra a definição de linha para modificá-la.
2. No menu **Editar**, clique em **Renumerar Linhas**.
3. Na caixa de diálogo **Renumerar Linhas**, especifique novos valores para o código de linha inicial e o incremento do código de linha. É possível redefinir os códigos numéricos de linha para valores equidistantes. No entanto, o designer de relatórios renumera somente códigos de linha que começam com os números (por exemplo, 130 ou 246). Ele não renumera códigos de linha que começam com letras (por exemplo, INCOME\_93 ou TP0693).

> [!NOTE]
> Quando você renumera códigos de linha, o designer de relatórios atualiza automaticamente as referências **TOT** e **CAL**. Por exemplo, se uma linha **TOT** se refere a um intervalo que começa com o código de linha 100, e você renumera linhas, começando por 90, a referência inicial **TOT** muda de 100 para 90.

## <a name="add-a-description"></a>Adicionar uma descrição
A célula de descrição fornece a descrição dos dados financeiros na linha do relatório, como "Receita" ou "Rendimento Líquido". O texto na célula **Descrição** aparece no relatório exatamente quando você o insere na definição de linha.

> [!NOTE]
> A largura da coluna de descrição no relatório é definida na definição da coluna. Se o texto na coluna **Descrição** da definição de linha for longo, verifique a largura da coluna **DESC**. Quando você usa a caixa de diálogo **Inserir linhas de**, os valores na coluna **Descrição** são os valores de segmento ou de dimensão dos dados financeiros. Você pode inserir linhas para adicionar texto descritivo, como um título de seção ou um total da seção, e para adicionar formatação, como uma linha antes de uma linha de total. Se o relatório incluir uma hierarquia organizacional, você poderá incluir o texto adicional que é definido para as unidades organizacionais na hierarquia organizacional. Você também pode restringir o texto adicional a uma unidade organizacional específica.

### <a name="add-the-description-for-a-line-on-a-report"></a>Adicionar a descrição para uma linha em um relatório

1. No Designer de Relatórios, clique em **Definições de Linha** e abra a definição de linha para modificá-la.
2. Selecione a célula **Descrição** e insira o nome da linha do relatório.
3. Aplique a formatação.

### <a name="add-additional-text-from-a-reporting-tree-in-the-description"></a>Adicionar outro texto de uma hierarquia organizacional na descrição

1. No Designer de Relatórios, clique em **Definições de Linha** e abra a definição de linha para modificá-la.
2. Insira o código do texto adicional e qualquer outro texto na célula **Descrição** apropriado.
3. Aplique a formatação.

### <a name="limit-the-additional-text-to-a-specific-reporting-unit"></a>Limitar o texto adicional a uma unidade organizacional específica

1. No Designer de Relatórios, clique em **Definições de Linha** e abra a definição de linha para modificá-la.
2. Localize a linha em que o texto adicional deve ser criado. Clique duas vezes na célula na coluna **Fórmulas/Linhas/Unidades Relacionadas**.
3. Na caixa de diálogo **Seleção de Unidade de Relatório**, no campo **Árvore de relatório**, selecione uma árvore de relatório.
4. No campo **Selecione uma unidade de relatório para restrição**, expanda ou recolha a árvore de relatório, e selecione uma unidade de relatório.

## <a name="add-a-format-code"></a>Adicionar um código de formato
A célula **Código de Formato** oferece uma seleção de opções pré-formatadas para o conteúdo dessa linha. Se a célula **Código de Formato** estiver em branco, a linha será interpretada como uma linha de detalhes de dados financeiros.

> [!NOTE]
> Se um relatório contiver linhas de formatação sem valor que estão relacionadas a linhas de valor que foram suprimidas (por exemplo, devido a saldo zero), você pode usar a coluna **Fórmulas/Linhas/Unidades Relacionadas** para impedir que as linhas de título e formato sejam impressas.

### <a name="add-a-format-code-to-a-report-row"></a>Adicionar um código de formato a uma linha do relatório

1. No Designer de Relatórios, clique em **Definições de Linha** e selecione uma definição de linha para modificá-la.
2. Clique duas vezes na célula **Código de Formato**.
3. Selecione um código de formato na lista. A tabela a seguir descreve os códigos de formato e suas ações.

    | Código de formato                   | Interpretação do código de formato | Ação |
    |-------------------------------|-----------------------------------|--------|
    | (Nenhuma)                        |                                   | Desmarca a célula **Código de Formato**. |
    | TOT                           | Total                             | Identifica uma linha que usa operadores matemáticos na coluna **Fórmulas/Linhas/Unidades Relacionadas**. Os totais contêm operadores simples, como **+** ou **-**. |
    | CAL                           | Cálculo                       | Identifica uma linha que usa operadores matemáticos na coluna **Fórmulas/Linhas/Unidades Relacionadas**. Os cálculos contêm operadores complexos, como as instruções **+**, **-**, **\**_, _*/** e **IF/THEN/ELSE**. |
    | DES                           | descrição                       | Identifica uma linha de título ou uma linha em branco em um relatório. |
    | LFT RGT CEN                   | Esquerdo Direito Centro                 | Alinha o texto da descrição da linha na página do relatório, independente da posição do texto na definição da coluna. |
    | CBR                           | Alterar linha de base                   | Identifica uma linha que define a linha de base para cálculos da coluna. |
    | COLUMN                        | Quebra de coluna                      | Inicia uma nova coluna no relatório. |
    | PAGE                          | Quebra de página                        | Inicia uma nova página no relatório. |
    | \---                          | Sublinhado único                  | Coloca uma única linha em todas as colunas de valor do relatório. |
    | ===                           | Sublinhado duplo                  | Coloca uma linha dupla em todas as colunas de valor do relatório. |
    | LINE1                         | Linha fina                         | Inclui uma linha única e fina na página. |
    | LINE2                         | Linha grossa                        | Inclui uma linha única e grossa na página. |
    | LINE3                         | Linha pontilhada                       | Inclui uma linha única e pontilhada na página. |
    | LINE4                         | Linha grossa e linha fina          | Inclui uma linha dupla na página. A linha de cima é grossa, e a linha de baixo é fina. |
    | LINE5                         | Linha fina e linha grossa          | Inclui uma linha dupla na página. A linha de cima é fina, e a linha de baixo é grossa |
    | BXB BXC                       | Linha em caixa                         | Desenha uma caixa ao redor das linhas do relatório que começam com a linha **BXB** e terminam com a linha **BXC**. |
    | REM                           | Comentário                            | Identifica uma linha que é uma linha de comentários e não deve ser impressa no relatório. Por exemplo, uma linha de comentários pode explicar as técnicas de formatação. |
    | SORT ASORT SORTDESC ASORTDESC | Classificar                              | Classifica despesas e receitas, define sequência de um relatório de variação real ou de orçamento pela variação maior ou classifica as descrições da linha em ordem alfabética. |

## <a name="specify-related-formulasrowsunits"></a>Especificar fórmulas/linhas/unidades relacionadas
A célula **Fórmulas/Linhas/Unidades Relacionadas** tem várias finalidades. Dependendo do tipo de linha, uma célula **Fórmulas/Linhas/Unidades Relacionadas** pode realizar uma das seguintes funções:

- Definir as linhas a serem incluídas em um cálculo quando você usa um código de formato **TOT** ou **CAL**.
- Vincular uma linha de formatação a uma linha de valor, para imprimir a formatação apenas quando o valor relacionado for impresso.
- Limitar uma linha a uma unidade organizacional específica.
- Definir a linha base para cálculos quando você usa o código de formato **BASEROW**.
- Defina as linhas a serem classificadas ao usar um dos códigos de formato de classificação.

### <a name="use-a-row-total-in-a-row-definition"></a>Usar um total de linha em uma definição de linha

Use uma fórmula do total da linha para adicionar ou subtrair valores em outras linhas. Uma fórmula para criar um total da linha pode incluir os operadores + e - para combinar códigos de linha e intervalos individuais. Os intervalos são indicados por dois pontos (:). A fórmula pode conter até 1.024 caracteres. Este é um exemplo de fórmula padrão da totalização: 400+420+430+450+460LIABILITIES+EQUITY520:546520:546-LIABILITIES

### <a name="components-of-a-row-total-formula"></a>Componentes de uma fórmula do total da linha

Quando você criar uma fórmula de total de linha, deverá usar códigos de linha para especificar quais linhas adicionam ou subtraem na definição de linha atual, e deverá usar operadores para especificar como as linhas serão combinadas. As linhas e valores totais podem ser usadas em uma combinação.

> [!NOTE]
> Todas as linhas de total que estejam em um intervalo serão excluídas. Para criar um total geral, você pode especificar o intervalo de linhas. Se a primeira linha de um intervalo é uma linha total, essa linha será incluída no novo total. A tabela a seguir descreve como os operadores são usados em fórmulas de total de linha.

| Operador | Exemplo de fórmula | descrição                                                 |
|----------|-----------------|-------------------------------------------------------------|
| +        | 100+330         | Adiciona o valor da linha 100 ao valor da linha 330.        |
| :        | 100:330         | Adiciona os totais de todas as linhas entre a linha 100 e a linha 330.    |
| -        | 100-330         | Subtrai o valor da linha 100 do valor da linha 330. |

### <a name="create-a-row-total"></a>Criar um total da linha

1. No Report Designer, clique em **Definições de linha** e abra a definição de linha a ser modificada.
2. Clique duas vezes na célula **Código de Formato** na definição de linha, e selecione **TOT**.
3. Na célula **Fórmulas/Linhas/Unidades Relacionadas**, insira a fórmula total.

### <a name="relate-a-format-row-to-an-amount-row"></a>Relacionar uma linha de formato a uma linha de valor

Na coluna **Código de Formato** em uma definição de linha, os códigos de formato **DES**, **LFT**, **RGT**, **CEN**, **---** e **===** aplicam formatação a linhas sem valor. Para impedir que esta formatação seja impressa quando as linhas de valor relacionado forem suprimidas (por exemplo, porque as linhas de valor contêm valores zero ou nenhuma atividade no período), você deve relacionar as linhas de formato às linhas de valor correspondente. Essa funcionalidade é útil quando você deseja evitar que cabeçalhos ou formatação relativos a subtotais sejam impressos quando não há detalhes para impressão no período.

> [!NOTE]
> Você também pode impedir que linhas de valor detalhado sejam impressas desmarcando a opção para exibir linhas sem valores. Esta opção está localizada na guia **Configurações** da definição de relatório. Por padrão, as contas de detalhes da transação com um saldo zero ou nenhuma atividade de período são suprimidas dos relatórios. Para mostrar essas contas de detalhes da transação, marque a caixa de seleção **Exibir linhas sem valores** na guia **Configurações** da definição de relatório.

### <a name="relate-a-format-row-to-an-amount-row"></a>Relacionar uma linha de formato a uma linha de valor

1. No Designer de Relatórios, clique em **Definições de Linha** e selecione uma definição de linha para modificá-la.
2. Na linha de formatação, na célula **Fórmulas/Linhas/Unidades Relacionadas**, insira o código de linha da linha de valor a ser suprimida.

    > [!NOTE]
    > Para suprimir uma linha de valor, o saldo da linha deve ser 0 (zero). Uma linha de valor que tem um saldo que não é suprimido.

3. No menu **Arquivo**, clique em **Salvar**.

### <a name="example-of-preventing-printing-of-rows"></a>Exemplo de prevenção de impressão de linhas

No exemplo a seguir, um usuário quer impedir a impressão do título e sublinhados da linha **Caixa Total** do seu relatório porque não houve atividade nas contas de caixa. Então, na linha 220 (que, como indicado pelo código de formato **---**, é uma linha de formatação), na célula **Fórmulas/Linhas/Unidades Relacionadas**, o usuário insere **250**, que é o código de linha da linha de valor que o usuário deseja suprimir.

[![RelatedRowsRowDefinition.](./media/relatedrowsrowdefinition-1024x144.png)](./media/relatedrowsrowdefinition.png)

## <a name="select-the-base-row-for-a-column-calculation"></a>Selecione a linha de base para um cálculo de coluna
No relatório relacional, você atribui uma ou mais linhas base na definição de linha usando o código de formato **CBR** (alterar a linha base). Então, a linha de base é referenciada por um cálculo na definição de coluna. Veja alguns exemplos típicos de cálculos de CBR:

- Porcentagem da receita total pois ela se refere a itens individuais da receita
- Porcentagem de despesa total, pois ela se refere a itens de despesa individual
- Porcentagem de margem bruta, pois ela se refere a detalhes de divisão ou departamento.

Uma ou mais linha de base são definidas na definição de linha e a definição de coluna determina a relação na qual a linha de base é relatada. O código usado na fórmula de coluna é **BASEROW**. As operações matemáticas básicas a seguir são usadas com **BASEROW**: dividir, multiplicar, adicionar ou subtrair. A operação que é usada com mais frequência é dividir por **BASEROW**, na qual o resultado aparece como uma porcentagem. Os cálculos de coluna que usam **BASEROW** na fórmula empregam a definição de linha para os códigos de linha base relacionados. As linhas **CBR** têm as seguintes características:

- As linhas **CBR** não são impressas no relatório completo.
- O código de formato **CBR** e o código de linha relacionado são posicionados acima da linha ou seção que exibe os cálculos relacionados.

Em uma definição de coluna, o tipo de coluna **CALC** indica uma coluna que especifica uma fórmula na linha **Fórmula**. Essa fórmula opera sobre os dados desta coluna do relatório e usa a palavra-chave Baserow para basear os cálculos nos códigos de formato **CBR** na linha. Na definição de linha, o código de formato **CBR** define a linha base para as colunas que calculam uma porcentagem ou multiplicam pela linha base para cada linha no relatório. Você pode ter vários códigos de formato **CBR** em um formato de linha, como um para vendas líquidas, um para vendas brutas e um para despesas totais. Geralmente, o código de formato **CBR** é usado para criar uma porcentagem para contas que são comparadas a uma linha total. Uma linha de base é usada para todos os cálculos até que outra linha de base seja definida. Você deve definir um código de formato **CBR** inicial e um código de formato **CBR** final. Por exemplo, para determinar despesas como uma porcentagem de vendas líquidas, você pode dividir o valor em cada linha de despesas pelo valor na linha de vendas líquidas. Nesse caso, a linha de vendas líquidas é a linha base. Você pode definir uma definição de coluna que informa resultados acumulados no ano, juntamente com uma porcentagem de base de cada resultado, como mostrado no exemplo a seguir. Comece com o demonstrativo de rendimento detalhado.

### <a name="select-the-base-row-in-a-row-definition-for-a-column-calculation"></a>Seleciona a linha de base em uma definição de linha para o cálculo de uma coluna

1. No Designer de Relatórios, clique em **Definições de Coluna** e abra a definição de coluna para um demonstrativo de receita.
2. Adicione uma nova coluna à definição de coluna, e defina o tipo de coluna como **CALC**.
3. Na célula **Fórmula** da nova coluna, insira a fórmula **X/BASEROW**, onde **X** é o tipo de coluna **FD** para ver uma porcentagem.
4. Clique duas vezes na célula **Substituição de Formato/Moeda**.
5. Na caixa de diálogo **Substituição de Formato**, na lista **Categoria de Formato**, selecione **Porcentagem** e clique em **OK**.
6. No menu **Arquivo**, clique em **Salvar Como** para salvar a definição de coluna com um novo nome. Anexe **CBR** ao nome de arquivo atual (por exemplo, **CUR\_YTD\_CBR**). Esta definição de coluna é a definição de coluna da linha base
7. No Designer de Relatórios, clique em **Definições de Linha** e abra a definição de linha a ser alterada usando o cálculo de linha base.
8. Inserir uma nova linha acima da linha onde o cálculo da linha base deve começar.
9. Clique duas vezes na célula **Código de Formato** da definição de linha, e selecione **CBR**.
10. Na célula **Fórmulas/Linhas/Unidades Relacionadas**, insira o número de código de linha da linha base.

### <a name="example-of-base-row-calculation"></a>Exemplo de cálculo de linha de base

No exemplo a seguir de uma definição de linha, a linha 100 mostra que a linha base dos cálculos é a linha 280.

[![Exemplo de cálculo de linha base.](./media/cbrrowdefinition.png)](./media/cbrrowdefinition.png)

No exemplo a seguir de uma definição de coluna, os cálculos usam o código de formato **CBR**. O cálculo na coluna C divide o valor na coluna B do relatório pelo valor da linha 280 da coluna B. A substituição do formato na coluna B imprime o resultado do cálculo como uma porcentagem. Da mesma forma, cada valor na coluna E é o valor na coluna D como uma porcentagem das vendas líquidas.

[![Exemplo de definição de coluna.](./media/cbrcolumndefinition2.png)](./media/cbrcolumndefinition2.png)

O exemplo a seguir mostra um relatório que pode ser gerado com base nos cálculos anteriores.

[![Relatório de exemplo baseado em cálculos de exemplo anteriores.](./media/cbrreport-1024x272.png)](./media/cbrreport.png)

## <a name="select-a-sorting-code-for-a-row-definition"></a>Selecione um código de classificação para uma definição de linha
Os códigos de classificação classificam contas ou valores, definem um código de variação real ou de orçamento pela variação maior ou classifica as descrições da linha em ordem alfabética. Os códigos de classificação a seguir estão disponíveis:

- **SORT** – Classifica o relatório em ordem crescente, com base nos valores na coluna especificada.
- **ASORT** – Classifica o relatório em ordem crescente, com base no valor absoluto dos valores na coluna especificada. Em outras palavras, o sinal de cada valor é ignorado quando o valor é classificado. Esse código de formato define a sequência dos valores por magnitude da variação, independentemente se a variação é positiva ou negativa.
- **SORTDESC** – Classifica o relatório em ordem decrescente, com base nos valores na coluna especificada.
- **ASORTDESC** – Classifica o relatório em ordem decrescente, com base no valor absoluto dos valores na coluna especificada.

### <a name="select-a-sorting-code"></a>Selecionar um código de classificação

1. No Designer de Relatórios, clique em **Definições de Linha** e abra a definição de linha para modificá-la.
2. Clique duas vezes na célula **Código do Formato** e selecione um código de classificação.
3. Na célula **Fórmulas/Linhas/Unidades Relacionadas**, especifique o intervalo de códigos de linha para classificação. Para especificar um intervalo, insira o primeiro código de linha, dois pontos (:), e então o último código de linha. Por exemplo, insira **160:490** para especificar que o intervalo é da linha 160 até a linha 490.
4. Na célula **Restrição de Coluna**, insira a letra da coluna do relatório a ser usada para a classificação.

    > [!NOTE]
    > Inclua apenas as linhas de valor em um cálculo de classificação.

### <a name="examples-of-ascending-and-descending-column-values"></a>Exemplos de valores de coluna crescentes e decrescentes

No exemplo a seguir, os valores na coluna D do relatório serão classificados em ordem ascendente para linhas 160 a 490. Além disso, os valores absolutos na coluna G do relatório serão classificados em ordem descendente das linhas 610 a 940.

| Código de Linha | Descrição                                         | Código de formato | Fórmulas/linhas/unidades relacionadas | Saldo normal | Restrição da coluna | Vincular a Dimensões Financeiras |
|----------|-----------------------------------------------------|-------------|-----------------------------|----------------|--------------------|------------------------------|
| 100      | Classificados por variação mensal em ordem crescente       | DES         |                             |                |                    |                              |
| 130      |                                                     | SORT        | 160:490                     |                | D                  |                              |
| 160      | Venda                                               |             |                             | C              |                    | 4100                         |
| 190      | Devolução de venda                                       |             |                             |                |                    | 4110                         |
|          | ...                                                 |             |                             |                |                    |                              |
| 490      | Rendimento de juros                                     |             |                             | C              |                    | 7000                         |
| 520      |                                                     | DES         |                             |                |                    |                              |
| 550      | Classificados por variação absoluta de YTD em ordem decrescente | DES         |                             |                |                    |                              |
| 580      |                                                     | ASORTDESC   | 610:940                     |                | G                  |                              |
| 610      | Vendas                                               |             |                             | C              |                    | 4100                         |
| 640      | Devolução de venda                                       |             |                             |                |                    | 4110                         |
|          | ...                                                 |             |                             |                |                    |                              |
| 940      | Rendimento de juros                                     |             |                             | C              |                    | 7000                         |


## <a name="specify-a-format-override-cell"></a>Especificar uma Célula de Substituição de Formato
A célula **Substituição de Formato** especifica a formatação que é usada para a linha quando o relatório é impresso. Essa formatação substitui a formatação que esteja especificada na definição da coluna e na definição do relatório. Por padrão, a formatação especificada nessas definições é a moeda. Se uma linha do relatório listar o número de ativos, como o número de compilações, e outra linha listar valor monetário desses ativos, é possível substituir a formatação de moeda e inserir a formatação numérica para a linha que especifica o número de compilações. Especifique essas informações na caixa de diálogo **Substituição de Formato**. As opções disponíveis dependem da categoria de formato selecionada. A área **Exemplo** da caixa de diálogo mostra os formatos de exemplo. As categorias de formato a seguir estão disponíveis:

- Formatação de moeda
- Formatação numérica
- Formatação de porcentagem
- Formatação personalizada

### <a name="override-cell-formatting"></a>Substituir a formatação da célula

1. No Report Designer, abra a definição de linha a ser modificada.
2. Na linha para substituir o formato, clique duas vezes na célula na coluna **Substituição de Formato**.
3. Na caixa de diálogo **Substituição de Formato**, selecione as opções de formatação a serem usadas para essa linha no relatório.
4. Clique em **OK**.

### <a name="currency-formatting"></a>Formatação de moeda

A formatação de moeda se aplica a um valor fiscal e inclui o símbolo de moeda. As opções a seguir estão disponíveis:

- **Símbolo de moeda** – o símbolo da moeda para o relatório. Esse valor substitui a configuração **Opções Regionais** para as informações da empresa.
- **Números negativos** – Os números negativos podem ter um sinal de subtração (-), podem aparecer entre parênteses ou ter um triângulo (∆).
- **Casas decimais** – O número de dígitos que aparecem após o ponto decimal.
- **Texto de substituição de valor zero** – O texto a ser incluído no relatório quando o valor é 0 (zero). Esse texto aparece como a última linha na área **Exemplo**.

    > [!NOTE]
    > Em caso de supressão da impressão de valores zero ou nenhuma atividade no período, este texto será suprimido.

### <a name="numeric-formatting"></a>Formatação numérica

A formatação numérica se aplica a qualquer valor e não inclui um símbolo de moeda. As opções a seguir estão disponíveis:

- **Números negativos** – Os números negativos podem ter um sinal de subtração (-), podem aparecer entre parênteses ou ter um triângulo (∆).
- **Casas decimais** – O número de dígitos que aparecem após o ponto decimal.
- **Texto de substituição de valor zero** – O texto a ser incluído no relatório quando o valor é 0 (zero). Esse texto aparece como a última linha na área **Exemplo**.

    > [!NOTE]
    > Em caso de supressão da impressão de valores zero ou nenhuma atividade no período, este texto será suprimido.

### <a name="percentage-formatting"></a>Formatação de porcentagem

A formatação de porcentagem inclui o sinal de porcentagem (%). As opções a seguir estão disponíveis:

- **Números negativos** – Os números negativos podem ter um sinal de subtração (-), podem aparecer entre parênteses ou ter um triângulo (∆).
- **Casas decimais** – O número de dígitos a serem exibidos após o ponto decimal.
- **Texto de substituição de valor zero** – O texto a ser incluído no relatório quando o valor é 0 (zero). Esse texto aparece como a última linha na área **Exemplo**.

    > [!NOTE]
    > Em caso de supressão da impressão de valores zero ou nenhuma atividade no período, este texto será suprimido.

### <a name="custom-formatting"></a>Formatação personalizada

Use a categoria de formato personalizado para criar uma substituição de formato personalizado. As opções a seguir estão disponíveis:

- **Tipo** – o formato personalizado.
- **Texto de substituição de valor zero** – O texto a ser incluído no relatório quando o valor é 0 (zero). Esse texto aparece como a última linha na área **Exemplo**.

    > [!NOTE]
    > Em caso de supressão da impressão de valores zero ou nenhuma atividade no período, este texto será suprimido.

O tipo deve representar o valor positivo e, em seguida, o valor negativo. Em geral, você insere um formato semelhante que diferencia-se entre os valores positivos e negativos. Por exemplo, para especificar que os valores positivos e negativos têm duas casas decimais, mas os valores negativos aparecem entre parênteses, insira **0,00;(0,00)**. A tabela a seguir mostra os formatos personalizadas que você pode usar para controlar o formato de seus valores. Todos os exemplos começam com o valor 1234,56.

| Formato                         | Positiva   | Negativo     | Zero    |
|--------------------------------|------------|--------------|---------|
| 0                              | 1235       | -1235        | 0       |
| 0;0                            | 1235       | 1235         | 0       |
| 0;(0);-                        | 1235       | 1235         | -       |
| \#,\#\#\#;(\#,\#\#\#);""       | 1.235      | (1.235)      | (Em branco) |
| \#,\#\#0,00;(\#,\#\#0,00);zero | 1.234,56   | (1.234,56)   | zero    |
| 0,00%;(0,00%)                  | 123456,00% | (123456,00%) | 0,00%   |

## <a name="specify-a-normal-balance-cell"></a>Especificar uma célula de Saldo normal
A célula **Saldo Normal** em uma definição de linha controla o sinal dos valores em uma linha. Para reverter o sinal de uma linha, ou se o saldo normal de uma conta for um crédito, insira um **C** na célula **Saldo Normal** dessa linha. O criador de relatório reverte o sinal em todas as contas de saldo de crédito nessa linha. Quando o designer de relatórios converte essas contas, ele remove a característica de débito/crédito de todos os valores e torna a totalização simples. Por exemplo, para calcular o rendimento líquido, você subtrai as despesas da renda. Normalmente, as linhas calculadas e totalizadas não são afetadas por um código **C**. No entanto, o controle de impressão **XCR** na definição de coluna reverte o sinal de qualquer linha contendo um **C** na coluna **Saldo Normal**. Essa formatação é especialmente importante quando você deseja mostrar todas as variações desfavoráveis como valores negativos. Se um número totalizado ou calculado tiver um sinal errado, insira um **C** na célula **Saldo Normal** para a linha para reverter o sinal.

## <a name="specify-a-row-modifier-cell"></a>Especificar uma célula de Modificador de linha
O conteúdo da célula **Modificador da Linha** em uma definição de linha substitui os anos fiscais, períodos e outras informações especificadas na definição de coluna dessa linha. O modificador selecionado se aplica a cada conta na linha. Você pode alterar cada linha usando um ou mais dos tipos de modificadores a seguir:

- Modificadores de conta
- Modificadores do código do cenário
- Atributos de conta e de transação

### <a name="override-a-column-definition"></a>Substituir uma definição de coluna

1. No Report Designer, abra a definição de linha a ser modificada.
2. Na linha em que você deseja substituir a definição de coluna, clique duas vezes na célula **Modificador da Linha**.
3. Na caixa de diálogo **Modificador da Linha**, selecione uma opção no campo **Modificador da Conta**. Para obter uma descrição das opções, consulte a seção "Modificadores de conta".
4. No campo **Modificador de código do livro**, selecione o código do livro a ser usado para a linha.
5. Em **Atributos**, siga estas etapas para adicionar uma entrada para cada atributo que deve ser incluído com o código de linha:

    1. Clique duas vezes na célula **Atributo** e selecione um nome de atributo.

        > [!IMPORTANT]
        > Substitua o sinal numérico (\#) por um valor numérico.

    2. Clique duas vezes na célula **De** e insira o primeiro valor do intervalo.
    3. Clique duas vezes na célula **Até** e insira o último valor do intervalo.

6. Clique em **OK**.

### <a name="account-modifiers"></a>Modificadores da conta

Quando você seleciona uma conta específica, o designer de relatórios costuma combinar a conta e os anos fiscais, períodos e outras informações especificadas na definição de coluna. Você pode usar informações diferentes, como períodos fiscais diferentes, para linhas específicas. A tabela a seguir mostra os modificadores de conta que estão disponíveis. Substitua o sinal numérico (\#) por um valor que seja igual ou menor ao número de períodos de um ano fiscal.

| Modificador da conta | O que é impresso                                                                           |
|------------------|-------------------------------------------------------------------------------------------|
| /BB              | O saldo inicial de uma conta.                                                     |
| /\#              | O saldo do período especificado.                                                     |
| /-\#             | O saldo do período que é \# períodos antes do período atual.                  |
| /+\#             | O saldo do período que é \# períodos após o período atual.                   |
| /C               | O saldo do período atual.                                                       |
| /C-\#            | O saldo do período que é \# períodos antes do período atual.                  |
| /C+\#            | O saldo do período que é \# períodos após o período atual.                   |
| /Y               | O saldo de ano até a data no período atual.                                      |
| /Y-\#            | O saldo do ano até a data ao longo do período que é \# períodos antes do período atual. |
| /Y+\#            | O saldo de ano até a data ao longo do período que é \# períodos antes do período atual.  |

### <a name="book-code-modifiers"></a>Modificadores de código do livro

Você pode limitar uma linha a um código de livro existente. A definição de coluna deve incluir pelo menos uma coluna **FD** que tem um código de livro.

> [!NOTE]
> A restrição do código de livro para uma linha substitui as restrições de códigos de livro na definição de coluna para essa linha.

### <a name="account-and-transaction-attributes"></a>Atributos de conta e de transação

Alguns sistemas contábeis oferecem suporte para atributos de contas e de transações nos dados financeiros. Esses atributos funcionam como segmentos virtuais da conta, e podem conter informações adicionais sobre a conta ou transação. Essas informações adicionais podem ser IDs de contas, IDs do lote, CEP ou outros atributos. Se seu sistema contábil oferece suporte para atributos, você pode usar atributos de contas ou de transações como modificadores de linha na definição de linha. Para obter informações sobre como substituir informações de linha, consulte a seção "Substituir definição de coluna" exibida anteriormente neste artigo.

## <a name="specify-a-link-to-financial-dimensions-cell"></a>Especificar uma célula Link para Dimensões Financeiras
A célula **Link para Dimensões Financeiras** contém links para os dados financeiros que devem ser incluídos em cada linha de um relatório. Esta célula contém valores de dimensão. Para abrir a caixa de diálogo **Dimensões**, clique duas vezes na célula **Link para Dimensões Financeiras**.

> [!NOTE]
> O Designer de Relatórios não pode selecionar contas, dimensões ou campos do sistema ERP no Microsoft Dynamics que incluam qualquer um dos seguintes caracteres reservados: &, \*, \[, \], {, ou }. Para especificar informações para uma linha que já está na definição de linha, adiciona e informação na célula **Vincular a dimensões financeiras**. Para adicionar novas linhas que sejam vinculadas aos dados financeiros, use a caixa de diálogo **Inserir Linhas de** para criar novas linhas na definição de relatório. O título de coluna é alterado de acordo com a forma na qual as colunas são configuradas, conforme exibido na tabela a seguir.

| Tipo de link selecionado       | A descrição na coluna do link é alterada para |
|----------------------------------|----------------------------------------------------|
| Dimensões Financeiras             | Link para Dimensões Financeiras                       |
| Planilha de relatório                 | Relatório Relatórios Financeiros                         |

### <a name="specify-a-dimension-or-range"></a>Especifique uma dimensão ou intervalo.

1. No Designer de Relatórios, abra a definição de linha a ser modificada.
2. Clique duas vezes na coluna **Vincular a dimensões financeiras**.
3. Na caixa de diálogo **Dimensões**, clique duas vezes na célula no nome da dimensão.
4. Na caixa de diálogo da dimensão, selecione **Individual ou intervalo**.
5. No campo **De**, digite a dimensão inicial ou clique em ![Pequisar.](media/browse.gif "Procurar") para procurar dimensões disponíveis. Para inserir um intervalo de dimensões, insira a dimensão final no campo **Até**.
6. Clique em **OK** para fechar a caixa de diálogo para a dimensão. A caixa de diálogo **Dimensões** exibe a dimensão ou o intervalo atualizado.
7. Clique em **OK** para fechar a caixa de diálogo **Dimensões**.

## <a name="display-zero-balance-accounts-in-a-row-definition"></a>Exibir contas de saldo zero em uma definição de linha
Por padrão, o designer de relatórios não imprime linhas sem um saldo correspondente nos dados financeiros. Consequentemente, você pode criar uma definição de linha que inclui todos os valores do segmento natural ou todos os valores de dimensão e depois usar essa definição de linha com algum de seus departamentos.

### <a name="modify-zero-balance-settings"></a>Alterar configurações de saldo zerado

1. No Report Designer, abra a definição do relatório a ser modificada.
2. Na guia **Configurações**, em **Outra formatação**, selecione opções para a definição de linha que são usadas na definição de relatório.
3. No menu **Arquivo**, clique em **Salvar** para salvar as alterações.

## <a name="use-wildcard-characters-and-ranges-in-a-row-definition"></a>Use caracteres curinga e variações em uma definição de linha
Ao inserir um valor de segmento natural na caixa de diálogo **Dimensões**, você pode colocar um caractere curinga (? ou \*) em uma posição de um segmento. O Criador de relatórios extrai todos os valores das posições definidas sem considerar os caracteres curinga. Por exemplo, a definição de linha contém somente valores de segmento natural, e os segmentos naturais têm quatro caracteres. Inserindo **6???** em uma linha, você instrui o desenvolvedor de relatório para incluir todas as contas que têm um valor de segmento natural que inicia com 6. Se você inserir **6\**_, os mesmos resultados são devolvidos, mas os resultados também incluem valores de largura variável como _* 60** e **600000**. O designer de relatórios substitui cada caractere curinga (?) pelo intervalo completo dos valores possíveis, que incluem letras e caracteres especiais. Por exemplo, no intervalo de **12?0** até **12?4**, o caractere curinga em **12?0** é substituído pelo menor valor no conjunto de caracteres, e o caractere curinga em **12?4** é substituído pelo maior valor no conjunto de caracteres.

> [!NOTE]
> Você deve evitar usar caracteres curinga para as contas inicial e final nos intervalos. Se você usar caracteres curingas na conta inicial ou final, resultados inesperados poderão ser recebidos.

### <a name="single-segment-or-single-dimension-ranges"></a>Intervalos de dimensão única ou de segmento único

É possível especificar um intervalo de valores de segmento ou de valores de dimensão. A vantagem de especificar um intervalo é não precisar atualizar a definição de linha sempre que um novo valor de segmento ou valor de dimensão é adicionado aos dados financeiros. Por exemplo, o intervalo **+Account=\[6100:6900\]** recebe os valores da conta 6100 até 6900 para o valor da linha. Quando um intervalo inclui um caractere curinga (?), o designer de relatórios não avalia o intervalo caractere por caractere. As extremidades inferior e superior do intervalo são determinadas. Depois, os valores finais e todos os valores entre eles são incluídos.

> [!NOTE]
> O Designer de Relatórios não pode selecionar contas, dimensões ou campos do sistema ERP no Microsoft Dynamics que incluam qualquer um dos seguintes caracteres reservados: &, \*, \[, \], {, ou }. Você pode adicionar um E comercial (&) somente quando cria automaticamente definições de linha usando a caixa de diálogo **Inserir Linhas de Dimensões**.

### <a name="multiple-segment-or-multiple-dimension-ranges"></a>Intervalos de vários segmentos ou de várias dimensões

Quando você insere um intervalo usando várias combinações de valores de dimensão, a comparação de intervalo é feita em uma base de ..\\dimensões financeiras\\dimensão por dimensão. A comparação de intervalo não pode ser feita caractere por caractere ou com base em segmento parcial. Por exemplo, o intervalo **+Account=\[5000:6000\], Department=\[1000:2000\], Cost center=\[00\]** inclui apenas as contas que correspondem a cada segmento. Neste cenário, a primeira dimensão deve estar no intervalo de 5000 a 6000, a segunda dimensão deve estar no intervalo de 1000 até 2000, e a última deve ser 00. Por exemplo, **+Account=\[5100\], Department=\[1100\], Cost center=\[01\]** não está incluído no relatório porque o último segmento está fora da variação especificada. Se um valor de segmento incluir espaços, coloque esse valor entre colchetes (\[ \]). Os seguintes valores são válidos para um segmento de quatro caracteres: **\[ 234\], \[123 \], \[1 34\]**. Os valores de dimensão devem ser colocados entre colchetes (\[ \]), e o designer de relatórios adiciona esses colchetes para você. Quando um intervalo de vários segmentos ou de várias dimensões contém caracteres curingas (? ou \*), as extremidades inferior e superior do intervalo de segmento múltiplo completo ou dimensão múltipla são determinadas. Depois, os valores finais e todos os valores entre eles são incluídos. Se tiver um grande intervalo, como o intervalo de todas as contas de 40000 a 99999, procure especificar uma conta inicial e uma conta final válidas, sempre que possível.

> [!NOTE] 
> O Designer de Relatórios não pode selecionar contas, dimensões ou campos do sistema ERP no Microsoft Dynamics que incluam qualquer um dos seguintes caracteres reservados: &, \*, \[, \], {, ou }. Você pode adicionar um E comercial (&) somente quando cria automaticamente definições de linha usando a caixa de diálogo **Inserir Linhas de Dimensões**.

## <a name="add-or-subtract-from-other-accounts-in-a-row-definition"></a>Adicionar ou subtrair de outras contas em uma definição de linha
Para adicionar ou subtrair os valores monetários em uma conta dos valores monetários em outra conta, você pode usar o sinal de adição (+) e o sinal de subtração (-) na célula **Link para Dimensões Financeiras**. A tabela a seguir mostra formatos aceitáveis para adicionar e subtrair links para dados financeiros.

| Operação                                                                               | Usar este formato                                                                                              |
|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| Adicionar duas contas totalmente qualificadas                                                       | +Division=\[000\], Account=\[1205\], Department=\[00\]+Division=\[100\], Account=\[1205\], Department=\[00\] |
| Adicionar dois valores de segmento.                                                                 | +Account=\[1205\]+Account=\[1210\]                                                                           |
| Adicionar valores de segmento que incluam caracteres curinga.                                    | +Account=\[120?+Account=\[11??\]                                                                             |
| Adicionar um intervalo de contas totalmente qualificadas                                                | +Division=\[000:100\], Account=\[1205\], Department=\[00\]                                                   |
| Adicionar um intervalo de valores de segmento.                                                          | +Account=\[1200:1205\]                                                                                       |
| Adicionar um intervalo de valores de segmento que incluam caracteres curinga.                         | +Account=\[120?:130?\]                                                                                       |
| Subtrair uma conta totalmente qualificada de outra conta totalmente qualificada.              | +Division=\[000\], Account=\[1205\], Department=\[00\]-Division=\[100\], Account=\[1205\], Department=\[00\] |
| Subtrair um valor de segmento de outro valor de segmento.                                  | +Account=\[1205\]-Account=\[1210\]                                                                           |
| Subtrair um valor de segmento que inclua um caractere curinga de outro valor de segmento. | +Account=\[1200\]-Account=\[11??\]                                                                           |
| Subtrair um intervalo de contas totalmente qualificadas                                           | -Division=\[000:100\], Account=\[1200:1205\], Department=\[00:01\]                                           |
| Subtrair um intervalo de valores de segmento.                                                     | -Account=\[1200:1205\]                                                                                       |
| Subtrair um intervalo de valores de segmento que incluam caracteres curinga.                    | -Account=\[120?:130?\]                                                                                       |

Embora você possa mudar as contas diretamente, também pode usar a caixa de diálogo **Dimensões** para aplicar a formatação correta aos links de dados financeiros. Qualquer um dos valores podem incluir caracteres curinga (? ou \*). Porém, o Designer de Relatórios não pode selecionar contas, dimensões ou campos do sistema ERP no Microsoft Dynamics que incluam qualquer um dos seguintes caracteres reservados: &, \*, \[, \], {, ou }.

> [!NOTE]
> Para subtrair valores, você deve colocar esses valores entre parênteses. Por exemplo, se você insere **450?-(4509)**, ele é exibido como **+Account=\[4509\]-Account=\[450?\]**, e você está orientando o designer de relatórios a subtrair o valor do segmento de conta 4509 do valor de qualquer segmento de conta que inicie com 450.

### <a name="add-or-subtract-accounts-from-other-accounts"></a>Adicionar ou subtrair contas de outras contas

1. No Designer de Relatórios, abra a definição de linha a ser modificada.
2. Na linha apropriada, clique duas vezes na célula na coluna **Link para Dimensões Financeiras**.
3. Na primeira linha na caixa de diálogo **Dimensões**, siga estas etapas:

    1. No primeiro campo, selecione todas as dimensões (padrão), ou clique par abrir a caixa de diálogo **Gerenciar Conjuntos de Dimensões**, onde você pode criar, modificar, copiar ou excluir um conjunto.
    2. Clique duas vezes na célula **Operador +/-** e selecione o operador de adição (**+**) ou de subtração (**-**) que se aplica a um ou mais valores ou conjuntos de dimensão na linha.
    3. Na coluna apropriada do valor de dimensão, clique duas vezes na célula para abrir a caixa de diálogo **Dimensões**, e selecione se este valor de dimensão é para individual ou intervalo, um conjunto de valores de dimensão ou contas de totalização. Para obter descrições dos campos da caixa de diálogo **Dimensões**, consulte a seção "Descrição da caixa de diálogo Dimensão".
    4. Insira os valores de segmento nas colunas **De** e **Até**.

4. Repita as etapas 2 a 3 para adicionar mais operações.

> [!NOTE]
> O operador se aplica a todas as dimensões na linha.

## <a name="description-of-the-dimensions-dialog-box"></a>Descrição da caixa de diálogo Dimensões.
A tabela a seguir descreve os campos na caixa de diálogo **Dimensões**.

| Item                | Descrição |
|---------------------|-------------|
| Individual ou intervalo | No campo **De**, insira o nome da conta ou clique no botão **Pesquisar** ![Pesquisar.](media/browse.gif "Procurar") para procurar a conta. Para selecionar um intervalo, insira ou procure um valor no campo **Até**. |
| Conjunto de Valores de Dimensões | No campo **Nome**, insira o nome de um conjunto de valores de dimensão. Para criar, modificar, copiar ou excluir um conjunto, clique em **Gerenciar Conjuntos de Valores de Dimensão**. O campo **Fórmula** é preenchido com a fórmula da célula **Link para Dimensões Financeiras** para este conjunto de valores de dimensão na definição de linha. |
| Contas de totalização   | No campo **Nome**, insira ou procure uma dimensão da totalização de contas. O campo **Fórmula** é preenchido com a fórmula na célula **Link para Dimensões Financeiras** para esta conta de totalização na definição de relatório. |

## <a name="add-dimension-value-sets-in-a-row-definition"></a>Adicionar conjuntos de valores de dimensão em uma definição de linha
Um conjunto de valores de dimensão é um grupo nomeado de valores de dimensão. Um conjunto de valores de dimensão só pode conter valores em uma única dimensão, mas você pode usar um conjunto de valores de dimensão em várias definições de linha, definições de coluna, definições de árvore de relatório e definições de relatório. Você também pode combinar conjuntos de valores de dimensão em uma definição de relatório. Quando uma alteração nos dados financeiros exige que você altere o conjunto do valor de dimensões, você pode atualizar a definição do conjunto de valores da dimensão e essa atualização será aplicada para todas as áreas que usam o conjunto de valores de dimensão. Por exemplo, se você indica com frequência um intervalo de valores a ser vinculado aos dados financeiros, como os valores de 5100 a 5600, você deve atribuir esse intervalo ao conjunto de contas intitulado Vendas. Depois de criar um conjunto de valores de dimensão, você pode selecionar este conjunto como seu vínculo de dados financeiros. Em outro exemplo, se você tiver o intervalo de valor de 5100 a 5600 atribuído às Vendas e 4175 para os descontos, é possível determinar vendas subtraindo-se descontos de vendas. Esta operação é indicada como **(5100:5600)-4175**.

### <a name="create-a-set-of-dimension-values"></a>Criar um conjunto de valores de dimensão.

1. No Designer de Relatórios, abra a linha, a coluna ou a definição de árvore a ser modificada.
2. No menu **Editar**, clique em **Gerenciar Conjuntos de Valores de Dimensão**.
3. Na caixa de diálogo **Gerenciar Conjuntos de Valores de Dimensão**, no campo **Dimensão**, selecione o tipo do conjunto de valores de dimensão a ser criado e clique em **Novo**.
4. Na caixa de diálogo **Novo**, insira um nome e uma descrição para o conjunto.
5. Na coluna **De**, clique duas vezes em uma célula.
6. Na caixa de diálogo **Conta**, selecione o nome da conta na lista, ou procure a entrada no campo **Pesquisar**. Clique em **OK**.
7. Repita as etapas 5 a 6 na coluna **Até** para criar uma fórmula para esse operador.
8. Quando a fórmula for concluída, clique em **OK**.
9. Na caixa de diálogo **Gerenciar conjuntos de dimensão**, clique em **Fechar**.

### <a name="update-a-set-of-dimension-values"></a>Atualizar um conjunto de valores de dimensão

1. No Report Designer, abra a linha, coluna ou hierarquia de definição a ser alterada.
2. No menu **Editar**, clique em **Gerenciar Conjuntos de Valores de Dimensão**.
3. Na caixa de diálogo **Gerenciar Conjuntos de Valores de Dimensão**, no campo **Dimensão**, selecione o tipo de dimensão.
4. Na lista, selecione o conjunto de valores de dimensão a ser atualizado, e clique em **Modificar**.
5. Na caixa de diálogo **Modificar**, modifique os valores da fórmula a ser incluída no conjunto.

    > [!NOTE]
    > Se você adicionar novas contas ou dimensões, verifique se mudou os conjuntos existentes de valores de dimensão para incorporar as alterações.

6. Clique duas vezes na célula, e selecione o operador apropriado, a conta **De** e a conta **Até**.
7. Clique em **OK** para fechar a caixa de diálogo **Modificar** e salvar as alterações.

### <a name="copy-a-dimension-set"></a>Copiar um conjunto de dimensões

1. No Report Designer, abra a linha, coluna ou hierarquia de definição a ser alterada.
2. No menu **Editar**, clique em **Gerenciar Conjuntos de Valores de Dimensão**.
3. Na caixa de diálogo **Gerenciar Conjuntos de Valores de Dimensão**, no campo **Dimensão**, selecione o tipo de dimensão.
4. Na lista, selecione o conjunto a ser copiado e clique em **Salvar Como**.
5. Insira um novo nome para o grupo copiado e clique em **OK**.

### <a name="delete-a-dimension-set"></a>Excluir um conjunto de dimensões

1. No Report Designer, abra a linha, coluna ou hierarquia de definição a ser alterada.
2. No menu **Editar**, clique em **Gerenciar Conjuntos de Valores de Dimensão**.
3. Na caixa de diálogo **Gerenciar Conjuntos de Valores de Dimensão**, no campo **Dimensão**, selecione o tipo de dimensão.
4. Selecione o conjunto a ser excluído e clique em **Excluir**. Clique em **Sim** para excluir permanentemente o conjunto de valores de dimensão.

## <a name="additional-resources"></a>Recursos adicionais

[Relatórios financeiros](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
