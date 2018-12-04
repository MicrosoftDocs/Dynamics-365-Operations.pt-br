---
title: "Opções avançadas de formatação no relatório financeiro"
description: "Quando você cria um relatório no relatório financeiro, funções adicionais de formatação são disponibilizadas, incluindo filtros de dimensões, restrições de colunas e unidades de relatório, linhas não imprimíveis, e instruções IF/THEN/ELSE nos cálculos."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 106571
ms.assetid: 895b5127-01d6-4495-b127-343387b743aa
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 821d8927211d7ac3e479848c7e7bef9f650d4340
ms.openlocfilehash: 8c95f3bfc33730fcf03bd65cd1e66ec104f1e236
ms.contentlocale: pt-br
ms.lasthandoff: 08/13/2018

---

# <a name="advanced-formatting-options-in-financial-reporting"></a>Opções avançadas de formatação no relatório financeiro

[!include [banner](../includes/banner.md)]

Quando você cria um relatório no relatório financeiro, funções adicionais de formatação são disponibilizadas, incluindo filtros de dimensões, restrições de colunas e unidades de relatório, linhas não imprimíveis, e instruções IF/THEN/ELSE nos cálculos. 

A tabela a seguir explica as funções avançadas de formatação disponíveis quando você cria relatórios.

| Função                   | Descrição |
|----------------------------|-------------|
| Filtro de dimensão           | Para acessar conjuntos de dados específicos, você pode usar dimensões na definição de linha e na definição de coluna. Muitos relatórios usam apenas o segmento natural no formato de linha. No entanto, as linhas podem ser alteradas de modo que incluam valores de dimensão. Os filtros de dimensão na definição de coluna são usados para acessar valores de dimensão específicos. |
| Restrição da unidade de relatório | Você pode configurar uma linha do relatório para que mostre apenas as informações vinculadas a uma unidade de relatório específica. |
| Linhas não impressas (NP)     | As linhas não impressas são úteis em muitos relatórios. Se vários cálculos são necessários para obter um valor, esses cálculos podem ser ocultos no relatório impresso. As linhas não impressas também são úteis para solucionar problemas de designs de relatório e para o posicionamento de célula avançado. |
| Restrição de coluna         | A restrição de coluna na definição de linha é útil para ocultar os valores relevantes apenas em algumas linhas do relatório. Quando os cálculos de porcentagem são executados em uma linha, a restrição da coluna impede que o total de colunas ou outras colunas sejam impressas quando esses números não se aplicam. |
| Quebra de coluna               | Você pode adicionar quebras de coluna em uma definição de linha para mostrar informações do relatório lado a lado. Você pode adicionar várias quebras de coluna em uma única definição de linha, e os cabeçalhos de coluna são repetidos na parte superior de cada coluna após a quebra de coluna. Os comentários de um relatório são mostrados entre as quebras de coluna. |
| Instrução IF/THEN/ELSE     | Você pode modificar os cálculos em uma definição de linha ou definição de coluna. |

## <a name="advanced-cell-placement"></a>Posicionamento de célula avançado
O posicionamento de célula avançado, ou *forçamento*, envolve o posicionamento de valores específicos em células específicas. Por exemplo, o forçamento costuma ser usado para mover o saldo correto em um demonstrativo de fluxo de caixa. Você pode usar o forçamento para:

- Mover valores do Microsoft Excel para células específicas.
- Embutir valores específicos em um relatório.
- Modificar sinais copiando um valor de uma célula anterior e multiplicando esse valor por -1.

> [!NOTE]
> Em muitos casos, você deve configurar a definição de relatório de forma que os cálculos de colunas sejam feitos antes dos cálculos de linha. Para concluir esta configuração, siga as etapas abaixo.
> 
> 1. No Designer de Relatórios, abra a definição de relatório.
> 2. Na guia **Configurações**, em **Prioridade de cálculo**, selecione **Executar primeiro o cálculo de coluna e depois de linha**.

## <a name="designing-the-report"></a>Criação do relatório
Ao criar um relatório, você deve primeiro criar todas as linhas de detalhes para garantir que os valores sejam recebidos conforme esperado. Adicione as substituições de formato **NP** (sem impressão) para suprimir o detalhamento que inclui os valores finais.

> [!IMPORTANT]
> Quando usa o código de formato **CAL** na definição de linha, você não pode fazer uma busca detalhada em detalhes da transação.

Para forçar, as fórmulas usam o seguinte formato: &lt;coluna de destino&gt;=&lt;coluna de origem&gt;.&lt;código da linha&gt; Separe todos os posicionamentos adicionais em uma linha com vírgula e espaço. Este é um exemplo: D=C.190, E=C.100

## <a name="examples-of-advanced-formatting-options"></a>Exemplos de opções de formatação avançada
Os exemplos a seguir mostram como formatar a definição de linha e a definição de coluna para forçar um relatório básico de fluxo de caixa (exemplo 1) e um relatório estatístico (exemplo 2).

### <a name="example-1-basic-forcing"></a>Exemplo 1: Forçamento básico

A tabela a seguir mostra um exemplo de uma definição de linha que usa o forçamento básico.

| Código de Linha |           descrição            | Código de formato | Fórmulas/linhas/unidades relacionadas |        Modificador de Linha        | Vincular a Dimensões Financeiras |
|----------|----------------------------------|-------------|-----------------------------|----------------------------|------------------------------|
| 100      | Dinheiro no Início do Período (NP) |             |                             | Modificador da Conta = \[/BB\] | +Segment2 = \[1100\]         |
| 130      | Dinheiro no início do período      | CAL         | C=C.100,F=D.100             |                            |                              |
| 160      |                                  |             |                             |                            |                              |
| 190      |                                  |             |                             |                            |                              |

> [!NOTE] 
> As colunas vazias foram removidas da tabela anterior para fins de apresentação: as colunas Substituição de formato, Saldo normal, Controle de impressão, Restrição de coluna não foram exibidas.

A tabela a seguir mostra um exemplo de definição de coluna que usa o forçamento básico na linha.

|                              | S   | B    | C        | D      | E      | S    |
|------------------------------|-----|------|----------|--------|--------|------|
| Cabeçalho 1                     |     |      |          |        |        |      |
| Cabeçalho 2                     | S   | B    | C        | D      | E      | S    |
| Cabeçalho 3                     |     |      |          |        |        |      |
| Tipo de Coluna                  | ROW | DESC | FD       | FD     | FD     | CALC |
| Código do Cenário/Categoria de Atributo |     |      | ACTUAL   | ACTUAL | ACTUAL |      |
| Ano Fiscal                  |     |      | BASE     | BASE   | BASE   |      |
| Período                       |     |      | BASE     | BASE   | BASE   |      |
| Períodos cobertos              |     |      | PERIODIC | YTD/BB | YTD    |      |
| Fórmula                      |     |      |          |        |        | E-D  |
| Largura da Coluna                 | 5   | 30   | 14       | 14     | 14     | 14   |

### <a name="example-2-statistical-reports"></a>Exemplo 2: Relatórios estatísticos

A tabela a seguir mostra um exemplo de uma definição de linha que usa o forçamento em um relatório estatístico.

| Código de Linha | Descrição               | Código de Formato | Fórmulas/linhas/unidades relacionadas     | Substituição de Formato      | Saldo normal | Vincular a Dimensões Financeiras               |
|----------|---------------------------|-------------|---------------------------------|----------------------|----------------|--------------------------------------------|
| 50       | Informações Estatísticas   | REM         |                                 |                      |                |                                            |
| 100      | Números de funcionários - EUA            | CAL         | 4                               | \#\#\#0.;($\#\#\#0.) |                |                                            |
| 115      | Número de funcionários - Internacional | CAL         | 11                              | \#\#\#0.;($\#\#\#0.) |                |                                            |
| 130      |                           |             |                                 |                      |                |                                            |
| 190      | Vendas dos EUA.                  |             |                                 |                      | C              | +Segment2 = \[41\*\], Segment3 = \[00\]    |
| 220      | Vendas internacionais       |             |                                 |                      | C              | +Segment2 = \[41\*\], Segment3 = \[01:99\] |
| 250      |                           |             |                                 |                      |                |                                            |
| 280      |                           |             |                                 |                      |                |                                            |
| 310      | Vendas dos EUA.                  | CAL         | D=C.190,E=C.100,F=(C.100/C.190) |                      |                |                                            |
| 340      | Vendas internacionais       | CAL         | D=C.220,E=C115,F=(C.220/C.115)  |                      |                |                                            |

> [!NOTE] 
> As colunas vazias foram removidas da tabela anterior para fins de apresentação: as colunas Controle de impressão, Restrição de coluna e Modificador de linha não são exibidas.

A tabela a seguir mostra um exemplo de uma definição de coluna que usa o forçamento em um relatório estatístico.

|                              | A   | B    | C      | D            | E     | S            |
|------------------------------|-----|------|--------|--------------|-------|--------------|
| Cabeçalho 1                     | A   | B    | C      | D            | E     | S            |
| Cabeçalho 2                     | -   | -    | Até a presente data    | Vendas Anuais | Equipe | $ Por Pessoa |
| Cabeçalho 3                     |     |      |        |              |       |              |
| Tipo de coluna                  | LINHA | DESC | FD     | CALC         | CALC  | CALC         |
| Código do Cenário/Categoria de Atributo |     |      | REAL |              |       |              |
| Ano fiscal                  |     |      | BASE   |              |       |              |
| Período                       |     |      | BASE   |              |       |              |
| Período Coberto              |     |      | YTD    |              |       |              |
| Fórmula                      |     |      |        |              |       | E-D          |
| Largura da Coluna                 | 5   | 30   | 14     | 14           | 14    | 14           |

## <a name="restricting-a-row-to-a-specific-reporting-unit"></a>Restringir uma linha a uma unidade de relatório específica
Quando uma linha do relatório está restrita a uma unidade de relatório específica, essa linha mostra os dados vinculados somente para a unidade de relatório nomeada e ignora os dados de outras unidades de relatório na árvore de relatório. Por exemplo, você pode criar uma linha que forneça detalhes das despesas operacionais totais para um departamento específico. O relatório pode conter dados duplicados se o relatório contém uma árvore de relatório e uma definição de linha com mais do que apenas a conta natural. Por exemplo, você tem uma árvore de relatório que lista os seis departamentos da organização, e também tem uma definição de linha que lista uma combinação específica de uma conta e um departamento na linha. Quando você gera o relatório, a combinação específica de uma conta e um departamento é impressa em cada nível da árvore de relatório, mesmo que esse departamento não coincida com o conteúdo da árvore. Esse comportamento ocorre porque a linha substitui o que é filtrado pela definição de relatório. Uma forma de evitar a duplicação de dados é restringir uma linha a uma unidade de relatório específica.

> [!NOTE]
> Se uma linha inclui dimensões, e você restringe essa linha a uma unidade de relatório filho, o valor da linha é incluído para essa unidade filho e para as unidades pai, mas nenhuma duplicação ocorre.

### <a name="restrict-a-row-to-a-reporting-unit"></a>Restringir uma linha para uma unidade de relatório

1. No Designer de Relatórios, clique em **Definições de Linha** e selecione uma definição de linha para modificá-la.
2. Clique duas vezes na célula apropriada **Fórmulas/linhas/unidades relacionadas**.
3. Na caixa de diálogo **Seleção de unidade organizacional**, no campo **Hierarquia organizacional**, selecione a hierarquia que é atribuída à definição de relatório.
4. Selecione uma unidade de relatório e clique em **OK**. A restrição aparece na célula da definição de linha.
5. Clique duas vezes na célula na coluna **Link para Dimensões Financeiras** da linha restrita e insira um link para o sistema de dados financeiros.

## <a name="selecting-print-control-in-a-row-definition"></a>Seleção de controle de impressão em uma definição de linha
Você pode especificar códigos de controle de impressão para cada coluna usando a célula **Controle de Impressão**.

### <a name="add-print-control-codes-to-a-report-row"></a>Adicionar códigos de controle de impressão a uma linha do relatório

1. No Report Designer, abra a definição de linha a ser modificada.
2. Clique duas vezes na célula **Controle de impressão**.
3. Na caixa de diálogo **Controle de Impressão**, selecione um código de controle de impressão, ou pressione e mantenha pressionada a tecla Ctrl para selecionar vários códigos. Você também pode digitar códigos de controle de impressão diretamente na célula **Controle de Impressão**. Use vírgulas para separar vários códigos de controle de impressão.
4. Selecione as opções de impressão condicionais.
5. Clique em **OK**.

### <a name="regular-print-control-codes"></a>Códigos de controle de impressão regulares

A tabela a seguir descreve os códigos de controle de impressão comuns para uma definição de linha.

| Códigos de controle de impressão | Interpretação do código de controle de impressão         | Descrição |
|--------------------|--------------------------------------------------|-------------|
| NP                 | Linha não impressa                                 | Impeça que os valores da linha sejam impressos no relatório, e exclua os valores de cálculos. Para incluir uma coluna sem impressão em um cálculo, indique a coluna diretamente na fórmula de cálculo. Por exemplo, a linha 240 não impressa é incluída no seguinte cálculo: **230+240+250**. Mas, a linha 240 não impressa não é incluída no seguinte cálculo: **230:250**. |
| CS                 | Símbolo da moeda; use o formato de moeda nesta linha | Incluir o símbolo da moeda em todos os valores sem porcentagem. Os valores de porcentagem nunca recebem um símbolo da moeda. |
| XD                 | Suprimir linha no relatório de detalhes da conta            | Suprima a exibição de contas em relatórios de detalhes de contas e de relatórios de detalhes da transação. Esse controle de impressão é útil quando uma linha inclui várias contas que não devem ser listadas no relatório de detalhes da conta ou no relatório de detalhes da transação. |
| X0                 | Suprimir linha se todos forem zero                        | Exclua uma linha do relatório se todas as células nessa linha estiverem vazias ou contiverem zeros. Esse controle de impressão é relevante apenas quando a opção para suprimir o saldo zero não está selecionada na definição de relatório. |
| B0                 | Deixar em branco colunas com zero                         | Deixe colunas em branco em uma linha contendo valores zero. |
| XR                 | Suprimir acúmulo                                  | Suprima um acúmulo. Se o relatório usa uma árvore de relatório, os valores nesta linha não são acumulados em nós pai subsequentes. |
| SR                 | Suprimir arredondamento                                | Evite que os valores dessa linha sejam arredondados. |
| XT                 | Suprimir linha no relatório de detalhes da transação        | Suprima a exibição de transações em relatórios de detalhes da transação. Esse controle de impressão é útil quando uma linha inclui várias contas que não devem ser listadas em um relatório de detalhes da transação. |

### <a name="conditional-print-control-codes"></a>Códigos de controle de impressão condicionais

A tabela a seguir descreve os códigos de controle de impressão condicionais para uma definição de linha.

| Códigos de controle de impressão | Descrição                                  |
|--------------------|----------------------------------------------|
| (nenhum)             | Desmarque a seleção de impressão condicional.       |
| EL                 | Imprimir somente os saldos de débito para esta linha.  |
| CR                 | Imprimir somente os saldos de crédito para esta linha. |

## <a name="column-restriction-cell-in-a-row-definition"></a>Célula de restrição de coluna em uma definição de linha
A célula **Restrição de Coluna** em uma definição de linha tem várias finalidades. Dependendo do tipo de linha, você pode usar a célula **Restrição de Coluna** para especificar uma das seguintes funções:

- A célula pode limitar a impressão de valores de linha a uma coluna específica. Esta função é útil se você está criando um balanço tabular.
- A célula pode especificar a coluna dos valores a serem classificados.

## <a name="using-a-calculation-formula-in-a-row-definition"></a>Uso de uma fórmula de cálculo em uma definição linha
Uma fórmula de cálculo em uma definição de linha pode incluir os operadores **+**, **-**, **\*** e **/** e as instruções **IF/THEN/ELSE**. Além disso, um cálculo pode envolver células individuais e valores absolutos (números reais que são incluídos na fórmula). A fórmula pode conter até 1.024 caracteres. Os cálculos não podem ser aplicados em linhas contendo células do tipo **Link para Dimensões Financeiras** (FD). No entanto, você pode incluir cálculos em linhas consecutivas, suprimir a impressão dessas linhas e totalizar as linhas de cálculo.

### <a name="operators-in-a-calculation-formula"></a>Operadores em uma fórmula de cálculo

Uma fórmula de cálculo usa operadores mais complexos do que uma fórmula de total de linha. No entanto, você pode usar os operadores **\*** e **/** com os operadores adicionais para multiplicar (\*) e dividir (/) valores. Para usar um intervalo ou uma soma em uma fórmula de cálculo, você deve usar uma arroba (@) na frente do código de linha, a menos que esteja usando uma coluna na definição de linha. Por exemplo, para adicionar o valor da linha 100 ao valor da linha 330, você pode usar a fórmula do total de linha **100+330** ou a fórmula de cálculo **@100+@330**.

> [!NOTE]
> Você deve usar uma arroba (@) antes de cada código de linha usado em uma fórmula de cálculo. Caso contrário, o número é lido como um valor absoluto. Por exemplo, a fórmula **@100+330** adiciona US$ 330 ao valor na linha 100. Quando você faz referência a uma coluna em uma fórmula de cálculo, o sinal de arroba (@) não é necessário.

### <a name="create-a-calculation-formula"></a>Criar uma fórmula de cálculo

1. No Designer de Relatórios, clique em **Definições de Linha** e abra a definição de linha para modificá-la.
2. Clique duas vezes na célula **Código de Formato** e selecione **CAL**.
3. Na célula **Fórmulas/Linhas/Unidades Relacionadas**, digite a fórmula de cálculo.

### <a name="example-of-a-calculation-formula-for-specific-rows"></a>Exemplo de uma fórmula de cálculo para linhas específicas

Neste exemplo, a fórmula de cálculo **@100+@330** significa que o valor da linha 100 é adicionado ao valor da linha 330. A fórmula do total de linha **340+370** adiciona o valor da linha 340 ao valor da linha 370. (O valor da linha 370 é o valor da fórmula de cálculo.)

| Código de Linha | Descrição                 | Código de Formato | Fórmulas/Linhas/Unidades Relacionadas | Controle de impressão | Modificador de linha | Link para Dimensões Financeiras |
|----------|-----------------------------|-------------|----------------------------|---------------|--------------|------------------------------|
| 340      | Dinheiro no Início do Período |             |                            | NP            | BB           | +Account=\[1100:1110\]       |
| 370      | Dinheiro no Início do Ano   | CAL         | @100+@330                  | NP            |              |                              |
| 400      | Dinheiro no Início do Período | TOT         | 340+370                    |               |              |                              |

Quando a linha em uma definição de linha tem um código de formato **CAL**, e você insere um cálculo matemático na célula **Fórmulas/Linhas/Unidades Relacionadas**, também deve inserir a letra da coluna e da linha associadas no relatório. Por exemplo, insira **A.120** para representar a coluna A, linha 120. Outra alternativa é usar um arroba (@) para indicar todas as colunas. Por exemplo, insira **@120** para representar todas as colunas da linha 120. Qualquer cálculo matemático sem uma letra de coluna ou um arroba (@) é considerado como um número real.

> [!NOTE]
> Se você usar um código da linha de rótulo para referenciar uma linha, use um ponto (.) como separador entre a letra da coluna e o rótulo (por exemplo, **A.GROSS\_MARGIN/A.SALES**). Se você usa um arroba (a), um separador não é necessário (por exemplo, **@GROSS\_MARGIN/@SALES**).

### <a name="example-of-a-calculation-formula-for-a-specific-column"></a>Exemplo de uma fórmula de cálculo para uma coluna específica

Neste exemplo, a fórmula de cálculo **E=C.340** significa que o cálculo na célula da coluna c, linha 340, é executado apenas na coluna E.

> [!NOTE]
> Quando você faz referência a uma coluna em uma fórmula de cálculo, o sinal de arroba (@) não é necessário.

| Código de Linha | Descrição                 | Código de Formato | Fórmulas/Linhas/Unidades Relacionadas | Controle de impressão | Modificador de linha | Link para Dimensões Financeiras |
|----------|-----------------------------|-------------|----------------------------|---------------|--------------|------------------------------|
| 340      | Dinheiro no Início do Período |             |                            | NP            | BB           | +Account=\[1100:1110\]       |
| 370      | Dinheiro no Início do Ano   | CAL         | E=C.340                    | NP            |              |                              |
| 400      | Dinheiro no Início do Período | TOT         | 340+370                    |               |              |                              |

### <a name="modifying-a-number-in-selected-columns"></a>Alteração de um número em colunas selecionadas

Quando você muda um número ou cálculo em uma coluna de uma linha específica, mas não deseja afetar outras colunas do relatório, pode especificar **CAL** (cálculo) na coluna **Código de Formato** da definição de linha.

- Para executar um cálculo em todas as colunas do relatório (**FD**), não insira uma atribuição de coluna.
- Para restringir uma fórmula a colunas específicas, insira a letra da coluna, um sinal de igual (**=**) e a fórmula.
- Você pode especificar várias colunas. Quando você usa um arroba (@) com posicionamento específico de coluna, o arroba (@) está relacionado à linha.
- Você pode inserir várias fórmulas de coluna em uma linha. Separe as fórmulas usando vírgulas.

### <a name="calculation-examples"></a>Exemplos de cálculo

| Cálculo            | Ação que é criada                                                                                                   |
|------------------------|--------------------------------------------------------------------------------------------------------------------------|
| @130\*.75              | Para cada coluna, o valor da linha 130 é multiplicado por 0,75. O resultado é colocado na linha atual de cada coluna. |
| B=@130\*.75            | O mesmo cálculo é executado apenas na coluna B.                                                                      |
| A,B,C=(@100/@130)\*.75 | A=(A.100/A.130)\*.75 B=(B.100/B.130)\*.75 C=(C.100/C.130)\*.75                                                           |

### <a name="ifthenelse-statements-in-a-row-definition"></a>Instruções IF/THEN/ELSE em uma definição de linha

As instruções **IF/THEN/ELSE** podem ser adicionadas a qualquer cálculo válido e usadas com o formato **CAL**. Você insere fórmulas de cálculo **IF/THEN/ELSE** na célula na coluna **Fórmulas/Linhas/Unidades Relacionadas**. As fórmulas de cálculo **IF/THEN/ELSE** usam o seguinte formato: If &lt;instrução true/false&gt; THEN &lt;fórmula&gt; ELSE &lt;fórmula&gt; A parte **ELSE &lt;fórmula&gt;** da instrução é opcional.

#### <a name="if-statements"></a>Instruções IF

A instrução que vem após a instrução **IF** pode ser qualquer instrução avaliada como verdadeira ou falsa. A instrução que vem após a instrução **IF** pode envolver uma avaliação simples, ou pode ser uma instrução complexa contendo várias expressões. Eis alguns exemplos:

- **IF A.200&gt;0** (avaliação simples)
- **IF A.200&gt;0 AND A.200&lt;10,000** (instrução complexa)
- **IF A.200&gt;10000 OR ((A.340/B.1200)\*2 &lt;1200)** (Instrução complexa que contém várias expressões)

O termo **Periods** em uma instrução **IF** representa o número de pontos do relatório. Este termo costuma ser usado para calcular uma média até a data. Por exemplo, quando você executa um relatório para o período 7 YTD, a instrução **B.150/Periods** significa que o valor da linha 150 da coluna B é dividido por 7.

#### <a name="then-and-else-formulas"></a>Fórmulas THEN e ELSE

As fórmulas **THEN** e **ELSE** podem ser qualquer cálculo válido, desde atribuições de valor muito simples até fórmulas complexas. Por exemplo, a instrução **IF A.200&gt;0 THEN A=B.200** significa “Se o valor na célula na coluna A da linha 200 for maior que 0 (zero), coloque o valor da célula na coluna B da linha 200 na célula da coluna A da linha atual”. A instrução **IF/THEN** precedente coloca um valor em uma coluna da linha atual. No entanto, você também pode usar um arroba (@) em avaliações true/false ou a fórmula para representar todas as colunas. Estes são outros exemplos que são descritos nas seguintes seções:

- **IF A.200 &gt;0 THEN B.200**: se o valor na célula A.200 for positivo, o valor da célula B.200 será colocado em cada coluna da linha atual.
- **IF A.200 &gt;0 THEN @200**: se o valor na célula A.200 for positivo, o valor de cada coluna da linha 200 será colocado na coluna correspondente na linha atual.
- **IF @200 &gt;0 THEN @200**: se o valor da linha 200 da coluna atual for positivo, o valor da linha 200 será colocado na mesma coluna na linha atual.

### <a name="restricting-a-calculation-to-a-reporting-unit-in-a-row-definition"></a>Restrição de um cálculo a uma unidade de relatório em uma definição de linha

Para restringir um cálculo a uma única unidade de relatório em uma árvore de relatório, de forma que o valor resultante não seja acumulado para uma unidade de alto nível, você pode usar o código **@Unit** na célula **Fórmulas/Linhas/Unidades Relacionadas** na definição de linha. O código **@Unit** é listado na coluna B da árvore de relatório **Nome da Unidade**. Quando você usa o código **@Unit**, os valores não são acumulados, mas o cálculo é avaliado em todos os níveis da árvore de relatório.

> [!NOTE]
> Para usar esta função, uma árvore de relatório deve ser associada à definição de linha.

A linha de cálculo pode se referir a uma linha de cálculo ou a uma linha de dados financeiros. O cálculo é registrado na célula **Fórmulas/Linhas/Unidades Relacionadas** da definição de linha e da restrição de tipo de dados financeiros. O cálculo deve usar um cálculo condicional que inicie com uma construção **IF @Unit**. Este é um exemplo: IF @Unit(SALES) THEN @100 ELSE 0. Este cálculo inclui o valor da linha 100 em cada coluna do relatório, mas somente para a unidade SALES. Se várias unidades são denominadas SALES, o valor aparece em cada uma dessas unidades. Além disso, a linha 100 pode ser uma linha de dados financeiros e pode ser definida como não impressa. Nesse caso, o valor será impedido de aparecer em todas as unidades na árvore. Você também pode limitar o valor a uma única coluna do relatório, como a coluna H, usando uma restrição de coluna para imprimir o valor somente nessa coluna do relatório. Você pode incluir combinações **OR** em uma instrução **IF**. Este é um exemplo: IF @Unit(SALES) OR @Unit(SALESWEST) THEN 5 ELSE @100. Você pode especificar uma unidade em uma restrição de tipo de cálculo de uma destas maneiras:

- Inserir um nome de unidade para incluir unidades que coincidam. Por exemplo, **IF @Unit(SALES)** permite que o cálculo para cada unidade seja chamado de SALES, mesmo que existam várias unidades SALES na árvore de relatório.
- Insira a empresa e o nome da unidade para restringir o cálculo a unidades específicas em uma empresa específica. Por exemplo, insira **IF @Unit(ACME:SALES**) para restringir o cálculo a unidades SALES na empresa ACME.
- Insira o código completo da hierarquia de hierarquia organizacional para restringir o cálculo a uma unidade específica. Por exemplo, insira **IF @Unit(SUMMARY^ACME^WEST COAST^SALES)**.

> [!NOTE]
> Para localizar o código completo da hierarquia, clique com o botão direito do mouse na definição da hierarquia organizacional e selecione **Copiar identificador da unidade organizacional (código H)**.

#### <a name="restrict-a-calculation-to-a-reporting-unit"></a>Restringir um cálculo a uma unidade organizacional

1. No Report Designer, clique em **Definições de linha** e abra a definição de linha a ser modificada.
2. Clique duas vezes na célula **Código de Formato** e selecione **CAL**.
3. Clique na célula **Fórmulas/Linhas/Unidades Relacionadas** e insira um cálculo condicional que inicie com uma construção **IF @Unit**.

### <a name="ifthenelse-statements-in-a-column-definition"></a>Instruções IF/THEN/ELSE em uma definição de coluna

Uma instrução **IF/THEN/ELSE** permite que o cálculo dependa dos resultados de qualquer outra coluna. Você pode consultar outras colunas, mas não pode referenciar uma célula de relatório na instrução **IF**. Qualquer cálculo deve ser aplicado à coluna inteira. Por exemplo, a instrução **IF B&gt;100 THEN B ELSE C\*1.25** significa “Se o valor na coluna B for maior que 100, coloque o valor da coluna B na coluna **CALC**. Se o valor na coluna B não for maior que 100, multiplique o valor da coluna C por 1,25. E coloque o resultado na coluna **CALC**”. Siga sempre a instrução **IF** com uma instrução lógica que possa ser avaliado como verdadeira ou falsa. As fórmulas que você usa para as instruções **THEN** e **ELSE** pode conter referências a qualquer número de colunas, e essas fórmulas podem ter o nível de complexidade desejado.

> [!NOTE]
> Você não pode inserir os resultados de um cálculo em outra coluna. Os resultados devem estar na coluna que contém a fórmula.

