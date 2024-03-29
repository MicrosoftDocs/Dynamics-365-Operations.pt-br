---
title: Definições de coluna nos relatórios financeiros
description: Este artigo fornece informações sobre definições de coluna. Uma definição de coluna é um componente de relatório, que define o conteúdo das colunas em um relatório.
author: aprilolson
ms.date: 10/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 106601
ms.assetid: 66e72a48-edab-4e9d-815f-596a1623c258
ms.search.form: FinancialReports
ms.openlocfilehash: 97f6c869e8d05e37ec3001d5de262ab8927d735a
ms.sourcegitcommit: d27fef61593c6d1e9e26d5c9fad21411bc52fabc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/23/2022
ms.locfileid: "9802787"
---
# <a name="column-definitions-in-financial-reports"></a>Definições de coluna nos relatórios financeiros

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre definições de coluna. Uma definição de coluna é um componente de relatório, ou um bloco de construção, que define o conteúdo das colunas em um relatório. Assim como as definições de linha, as definições básicas de coluna podem ser usadas em vários relatórios.

## <a name="create-and-modify-a-column-definition"></a>Criar e modificar uma definição de coluna

Uma definição de coluna pode conter duas a 255 colunas.

### <a name="create-a-column-definition"></a>Criar uma definição de coluna

1. No Report Designer, no painel de navegação, clique em **Definições de coluna**.
2. No menu **Arquivo**, clique em **Novo** e depois em **Definição de coluna**.
3. Adicionar conteúdos à definição da coluna.

### <a name="open-a-column-definition"></a>Abrir uma definição de coluna

1. No Report Designer, no painel de navegação, clique em **Definições de coluna**.
2. Clique duas vezes em definição da coluna para abri-la.

### <a name="add-a-column-to-a-column-definition"></a>Adicionar uma coluna a uma definição de coluna

1. No Report Designer, clique em **Definições de coluna** e abra a definição de coluna para modificá-la.
2. Selecione a coluna na qual uma nova coluna deve ser inserida.
3. No menu **Editar**, clique em **Inserir coluna**. A coluna aparece à esquerda da coluna que você selecionou.

### <a name="delete-a-column-from-a-column-definition"></a>Excluir uma coluna da definição de colunas

1. No Report Designer, clique em **Definições de coluna** e abra a definição de coluna para modificá-la.
2. Selecione a coluna a ser excluída.
3. No menu **Editar**, clique em **Excluir coluna**.

## <a name="contents-of-a-column-definition"></a>Conteúdos de uma definição de coluna
Uma definição de coluna inclui as seguintes informações:

- Uma coluna das descrições da definição de linha
- Colunas de valores que mostram dados financeiros ou cálculos que são baseados em outros dados na definição de coluna.
- Colunas de formatação
- Colunas de atributos

Estas informações são exibidas nas áreas a seguir na definição de colunas:

- A área dos cabeçalhos da definição de coluna contém o texto e a formatação do cabeçalho que aparece no relatório. Um cabeçalho pode ser aplicado a uma única coluna de dados, pode se estender entre várias colunas ou pode ser aplicado nas colunas em uma base condicional. A definição de colunas pode incluir quantas linhas de cabeçalho de colunas forem necessárias.

    > [!NOTE]
    > Os cabeçalhos da coluna se aplicam a cada coluna de dados no relatório. Os cabeçalhos do relatório se aplicam ao todo o relatório. Você define os cabeçalhos de relatório na guia **Cabeçalhos e rodapés** da definição de relatório.

- As linhas de detalhes da coluna são as linhas que estão abaixo do cabeçalho na definição da coluna. As linhas de detalhes da coluna definem as informações a serem incluídas no relatório. A tabela a seguir lista e descreve as linhas de detalhes da coluna.

    | Nome da linha de detalhe da coluna                                                | Descrição                                                    |
    |-----------------------------------------------------------------------|-------------------------------------------------------------------------|
    | Tipo de Coluna                                                           | (Obrigatório) Especificar o tipo de dados desta coluna.                                      |
    | Código do Cenário/Categoria de Atributo                                          | Especifique as informações de dados financeiros para as coluna dos tipos **FD** e **ATTR**.     |
    | Períodos do período do ano fiscal abrangidos                                    | Especifique as informações de dados financeiros para as coluna do tipo **FD**.              |
    | Fórmula                                                               | Especifique uma fórmula de cálculo para as colunas do tipo **CALC**.                  |
    | Espaços adicionais de largura da coluna antes do controle de impressão sobreposta do formato da coluna | Especificar opções especiais de formato.                                               |
    | Restrições de Coluna                                                   | Restringir dados                                                                        |
    | Unidade Organizacional                                                        | Limita a coluna, para mostrar somente os dados da unidade organizacional especificada.      |
    | Filtro na moeda de exibição de moeda                                      | Formatar moeda.                                                                      |
    | Filtro de Dimensão                                                      | Especifica um filtro para restringir os dados em determinadas unidades organizacionais de dados financeiros.           |
    | Filtro de Atributo                                                      | Especifica um filtro para restringir os dados financeiros.                                      |
    | Data de início Data de fim                                                   | Restringir os dados financeiros a dados específicos.                                    |
    | Justificação                                                         | Centraliza, alinha à esquerda ou à direita o texto da descrição especificado na definição de linha. |

## <a name="column-restrictions-in-a-column-definition"></a>Restrições de coluna em uma definição de coluna
É possível usar as limitações de coluna para especificar como uma definição de coluna usa os dados ou calcula as informações. Também é possível restringir uma coluna de relatório a uma unidade específica ou para datas específicas.

> [!NOTE]
> Uma código de **Restrição da coluna** substitui qualquer configuração em conflito que é atribuída na definição de linha.

### <a name="column-restrictions-cell"></a>Célula Restrições da coluna

A célula **Restrições da coluna** pode incluir códigos que restringem ou suprimem informações, como formatação, detalhes e valores de linhas, dessa coluna.

#### <a name="add-a-column-restriction-in-a-column-definition"></a>Adicionar uma restrição de coluna em uma definição de coluna

1. No Report Designer, abra a definição de coluna que será modificada.
2. Clique duas vezes na célula **Restrições da coluna** para que a coluna seja restringida.
3. Na caixa de diálogo **Restrições da coluna**, selecione um ou mais códigos da lista e depois clique em **OK**.

### <a name="column-restriction-codes"></a>Códigos de restrição da coluna

A tabela a seguir descreve os códigos de restrição de colunas.

| Código de restrição da coluna | Descrição |
|-------------------------|-------------|
| SU                      | Suprima o sublinhado de uma coluna na qual um comando de sublinhado (**---**) ou um comando de sublinhado duplo (**===**) é inserido na definição de linha. Por exemplo, você pode não querer sublinhar os valores que são produzidos pelo cálculo de uma porcentagem. |
| ST                      | Suprime totais para que apenas os detalhes sejam exibidos na coluna (por exemplo, uma coluna estatística). |
| SD                      | Suprima os detalhes para que apenas as linhas **TOT** e **CAL** (da definição de linha) sejam mostradas na coluna. |
| DR                      | Restrinja os valores em uma coluna **FD** para valores de débito. |
| CR                      | Restrinja os valores em uma coluna **FD** para valores de crédito. |
| ADJ                     | Restringe os valores na coluna para excluir os valores de ajuste de período, se esses valores estiverem disponíveis. |
| XAD                     | Restringe os valores na coluna para excluir os valores de ajuste de período. |
| PT                      | Restringe os valores na coluna, para que apenas transações lançadas sejam incluídas, se essas transações estiverem disponíveis. |
| UPT                     | Restrinja os valores na coluna, para que apenas as transações não lançadas sejam incluídas, se essas transações estiverem disponíveis.<p><strong>Observação:</strong> nem todos os dados são compatíveis com as transações não lançadas. </p> |

### <a name="restrict-a-column-to-a-reporting-unit"></a>Restringir uma coluna a uma unidade organizacional

1. No Report Designer, abra a definição de coluna que será modificada.
2. Clique duas vezes na célula **Unidade de relatório** para restringir a coluna.
3. Na caixa de diálogo **Seleção de unidade de relatório**, na lista **Árvore de relatórios**, selecione uma árvore.
4. Expanda ou recolha a lista de unidades, selecione uma unidade de relatório e depois clique em **OK**.

## <a name="format-column-headers"></a>Formatar cabeçalhos de coluna
É possível adicionar, alterar e excluir os cabeçalhos que aparecem na parte superior das colunas em um relatório. Você também pode configurar o campo **Período** das definições de coluna e o campo **Período base** das definições de relatório. O Período base é um recurso que ajuda a economizar tempo ao criar relatórios de previsão contínua.

### <a name="create-and-manage-column-headers"></a>Criar e gerenciar cabeçalhos de coluna

Você pode usar a caixa de diálogo **Cabeçalho da coluna** para adicionar, modificar e excluir os cabeçalhos que aparecem no topo das colunas em um relatório. A tabela a seguir descreve os campos na caixa de diálogo **Cabeçalho da coluna**.

| Campo                 | Descrição |
|-----------------------|-------------|
| Texto de cabeçalho da coluna    | Esse texto é exibido no cabeçalho da coluna. Você pode digitar o texto diretamente neste campo ou clicar em **Inserir AutoTexto** para selecionar uma opção que atualize o cabeçalho da coluna toda vez que o relatório for gerado. Para incluir vários códigos de AutoTexto, clique em **Inserir AutoTexto** novamente e, depois, clique em outro código na lista. |
| Opções de formato        | Aplicar formatação a um cabeçalho de coluna, como caixa ou sublinhado. |
| Difundir de Difundir para | Definir a coluna ou colunas às quais o texto do cabeçalho se aplica. |
| Justificação         | Especifique como o texto do cabeçalho da coluna deve ser alinhado para a coluna ou intervalo de colunas especificados nos campos **Propagar de** e **Propagar para**. |

### <a name="create-a-column-header"></a>Criar um cabeçalho de coluna

1. No Report Designer, abra a definição de coluna que será modificada.
2. Clique duas vezes em uma célula de cabeçalho.
3. Na caixa de diálogo **Cabeçalho de coluna**, insira o texto do cabeçalho da coluna. Outra alternativa é clicar em **Inserir AutoTexto** e selecionar uma opção.
4. No campo **Opções de formato**, selecione um formato para o cabeçalho.
5. No campo **Propagar de**, insira a letra da coluna na qual o cabeçalho da coluna deve começar. No campo **Propagar para**, insira a letra da coluna na qual o cabeçalho da coluna deve terminar.
6. Em **Justificação**, decida se o texto do cabeçalho da coluna deve ser justificado à esquerda, no centro ou à direita.
7. Clique em **OK**.

### <a name="add-a-column-header-row"></a>Adicionar uma linha de cabeçalho de coluna

1. No Report Designer, abra a definição de coluna que será modificada.
2. Selecionar uma célula na linha de cabeçalho.
3. No menu **Editar**, clique em **Inserir linha**. A nova linha é inserida acima da linha selecionada na etapa 2.

> [!NOTE]
> Se houver quatro ou mais linhas de cabeçalhos em um relatório, os cabeçalhos serão sobrepostos quando o relatório for exportado para uma planilha do Excel. Para exibir todos os cabeçalhos no relatório, aumente a margem superior da definição de relatório.

### <a name="delete-a-column-header-row"></a>Excluir uma linha de cabeçalho de coluna

1. No Report Designer, abra a definição de coluna que será modificada.
2. Selecionar uma célula na linha de cabeçalho para exclusão.
3. No menu **Editar**, clique em **Excluir linha**.

### <a name="create-an-automatically-generated-header"></a>Criar uma cabeçalho gerado automaticamente

O designer de relatórios pode gerar automaticamente cabeçalhos de coluna, com base em códigos de AutoTexto. Os códigos de Autotexto são variáveis atualizadas sempre que um relatório é gerado. Qualquer cabeçalho de coluna pode incluir esses códigos para especificar informações, como número de data ou do período, que podem variar para os relatórios. Consequentemente, você pode usar uma definição de coluna para várias definições de relatório, períodos de tempo hierarquias organizacionais. Como os códigos de AutoTexto dependem de informações do calendário das linhas de detalhe da coluna de definição, eles são compatíveis apenas para as colunas **CALC** e **FD**. A maneira que um código de autotexto é exibida na célula do cabeçalho da coluna afeta como essas informações são exibidas no relatório. Na caixa de diálogo **Cabeçalho de coluna**, os códigos de AutoTexto aparecem em letras maiúsculas e minúsculas. Consequentemente, o texto será exibido em minúscula no relatório. Por exemplo, em um ano civil padrão, **\@CalMonthLong** resolve o mês **7** como **julho**. Se o nome do mês precisar estar em maiúscula (por exemplo **JULHO**), insira o código do autotexto em caracteres maiúsculos no campo **Texto do cabeçalho da coluna**. Por exemplo, insira **\@CALMONTHLONG**. Você pode misturar códigos e texto. Por exemplo, você insere o seguinte texto de cabeçalho: **Período \@FiscalPeriod-\@FiscalYear de \@StartDate a \@EndDate**. O título do relatório que é gerado se parece com o seguinte texto: **Período 1-02 de 01/01/02 a 31/01/02**.

> [!NOTE]
> O formato de alguns textos, como o de data completa, depende das configurações regionais no servidor. Para alterar essas configurações, clique no botão **Início**, em **Painel de controle** e depois em **Região e idioma**. A tabela a seguir lista as opções disponíveis de autotexto para cabeçalhos da coluna.


| Opção e código de AutoTexto                | Descrição |
|-----------------------------------------|-------------|
| Nome do mês (@CalMonthLong)              | Imprime o nome do mês atual no título de coluna. Se você decidir arredondar os valores no relatório para milhares, milhões ou bilhões, ou se você definir a largura da coluna no relatório para menos de nove caracteres, o nome do mês será abreviado com os três primeiros caracteres. |
| Nome do mês abreviado (@CalMonthShort) | Imprime o nome abreviado do mês para o período fiscal selecionado. |
| Número do período (@FiscalPeriod)           | Imprime o formato numérico do período fiscal identificado para essa coluna. Se a coluna abranger vários períodos, o último período no intervalo será impresso. |
| Descrição do período (@FiscalPeriodName)  | Imprime a descrição do período fiscal que é identificada pelos dados financeiros. |
| Ano fiscal (@FiscalYear)               | Imprime o ano fiscal para a coluna no formato numérico. |
| Ano do calendário (@CalYear)                | Imprime o ano civil para a coluna no formato numérico. |
| Data inicial (@StartDate)                 | Selecione a data inicial da coluna. |
| Data de Término (@EndDate)                     | Selecione a data final da coluna. |
| Nome da unidade da hierarquia (@UnitName)         | Se você restringir uma coluna a uma unidade específica da hierarquia organizacional, imprima o nome da unidade no cabeçalho da coluna. |
| Descrição da unidade (@UnitDesc)            | Se você restringir uma coluna a uma unidade específica da hierarquia organizacional, imprima a descrição da unidade no cabeçalho da coluna. |
| Código do Cenário (@BookCode)                   | Imprime o código do cenário especificado na coluna. |
| Linha em branco (@Blank)                     | Insere uma linha em branco no cabeçalho da coluna. |

### <a name="create-a-conditional-spanning-header"></a>Criar um cabeçalho de medida condicional

Os cabeçalhos de medida condicionais podem abranger várias colunas com base em dados específicos do período. Por exemplo, se você tiver um relatório de orçamento para o ano fiscal e desejar exibir os orçamentos reais dos meses passados junto com os orçamentos projetados dos meses futuros, é possível usar um cabeçalho de medida condicional para atualizar automaticamente o cabeçalho do relatório. Lembre-se das seguintes situações ao criar um cabeçalho de medida condicional:

- Qualquer condição de parada (campo **Propagar para**) que seja correspondente antes que uma condição de início (campo **Propagar de**) seja ignorada. Por exemplo, se a coluna B tiver a condição de propagação definida como BASE+1 até BASE, e se BASE estiver na coluna C e BASE+1 na coluna D. Neste caso, a condição de parada na coluna C é ignorada e a impressão do cabeçalho começa na coluna D.
- Se você especificar os cabeçalhos de coluna que se sobrepõem, eles serão impressos de forma sobreposta no relatório. O relatório será gerado, mas o seguinte aviso aparecerá no campo **Status da fila de relatórios**: "Os cabeçalhos de coluna usando Base fazem interseção com outros cabeçalhos de coluna e talvez causem sobreposição de texto." Por exemplo, a definição de cabeçalho da coluna B é B para BASE+1 e a definição de cabeçalho da coluna D é BASE+1 para F. Nesse caso, os cabeçalhos são impressos na parte superior um do outro e são ilegíveis. Sempre que BASE for usado em uma definição **Propagar de/Propagar para**, certifique-se de exibir o relatório que é gerado para verificar se há sobreposição de cabeçalhos.
- Se especificar BASE na definição propagada em uma coluna (**NP**) sem impressão, ela é ignorada, independentemente do que é definido na coluna de definição. Basicamente, esse cenário é o mesmo que não criar uma definição do cabeçalho da coluna.
- Em colunas de impressão condicionais (**P&lt;B**, **P&gt;=B**), os cabeçalhos de propagação condicionais comportam-se como qualquer definição de cabeçalho de coluna. Por exemplo, se a condição for falsa, toda a correspondência subsequente de coluna para a condição de propagação inicia a impressão de cabeçalho.

#### <a name="create-a-conditional-spanning-header"></a>Criar um cabeçalho de medida condicional

1. No Report Designer, abra a definição de coluna que será modificada.
2. Clique duas vezes em uma célula de cabeçalho.
3. Na caixa de diálogo **Cabeçalho de coluna**, insira o texto do cabeçalho da coluna. Outra alternativa é clicar em **Inserir AutoTexto** e selecionar uma opção.
4. No campo **Opções de formato**, selecione um estilo de formatação para o cabeçalho.
5. Especificar um período relativo ao período base que é especificado quando o relatório é gerado. Nos campos **Propagar de** e **Propagar para**, insira um dos seguintes valores: **BASE**, **BASE-X** ou **BASE+X**, onde X é o número dos períodos do período base. Por exemplo, se inserir **BASE** no campo **Propagar de**, o texto do cabeçalho da coluna de propagação condicional começará no cabeçalho da coluna onde o valor **Período base** da definição de relatório é igual ao valor **Período** da definição de coluna. Terminará na coluna que é indicada no campo **Propagar de**. Por isso, se o propagado for BASE para M e o valor **Período base** da definição de relatório for **4**, o cabeçalho começará na coluna onde o período é definido como **4** e terminará na coluna M. Os cabeçalhos param e começam a imprimir somente as colunas.
6. Em **Justificação**, decida se o texto do cabeçalho da coluna deve ser justificado à esquerda, no centro ou à direita.
7. Clique em **OK**.

#### <a name="example-of-a-conditional-spanning-header"></a>Exemplo de um cabeçalho de medida condicional

Um usuário está criando um relatório para uma previsão de seis meses dinâmica. O usuário quer que a palavra "Real" seja impressa nas colunas que contiverem dados reais, e a palavra "Orçamento" seja impressa nas colunas que contiverem previsões de orçamento. Cada mês em que o relatório é executado, há uma coluna real a mais e uma coluna de orçamento a menos. Embora o usuário possa alterar a definição de coluna manualmente cada vez que o relatório é gerado para ajustar os cabeçalhos, mas ela decide economizar tempo e esforço, e criar os cabeçalhos de medida condicionais que criarão automaticamente os cabeçalhos sobre as colunas apropriadas cada vez que o relatório for executado. O usuário abre o Report Designer, clica em **Definição de Coluna** no painel de navegação e abre a definição de coluna do relatório. O usuário insere as informações a seguir. O período base na definição de relatório é 4.

|  Formatar   |  A   | E     | E      | B       | E        | S       | G       | H      | I             | J             | K             | L             | S             |
|-----------|------|-------|--------|---------|----------|---------|---------|---------|-------------|---------------|---------------|---------------|---------------|
| Cabeçalho 1   |    | Real    | Orçamento        |         |         |        |       |          |        |               |               |               |               |
| Cabeçalho 2   |      | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong |
| Cabeçalho 3    |      |       |        |        |        |         |        |          |               |               |               |               |               |
| Tipo de coluna  | DESC | FD   | FD     | FD    | FD   | FD    | FD      | FD            | FD            | FD            | FD            | FD            | FD            |
| Código/atributo do cenário |      | ACTUAL        | ORÇAMENTO2012    | ACTUAL        | ORÇAMENTO2012    | ACTUAL        | ORÇAMENTO2012    | ACTUAL        | ORÇAMENTO2012    | ACTUAL        | ORÇAMENTO2012    | ACTUAL        | ORÇAMENTO2012    |
| Ano fiscal |  | BASE   | BASE   | BASE   | BASE   | BASE    | BASE    | BASE     | BASE          | BASE          | BASE          | BASE          | BASE          |
| Período  |     | 1      | 1       | 2      | 2      | 3       | 3       | 4        | 4             | 5             | 5             | 6             | 6             |
| Períodos cobertos     |      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      |
| Largura da coluna   | 30   | 10    | 10     | 10     | 10    | 10    | 10    | 10     | 10            | 10            | 10            | 10            | 10            |
| Controle de Impressão  |    | P&lt;=B    | P&gt;B   | P&lt;=B  | P&gt;B   | P&lt;=B   | P&gt;B   | P&lt;=B  | P&gt;B   | P&lt;=B  | P&gt;B   | P&lt;=B       | P&gt;B        |

O usuário clica duas vezes em uma célula do cabeçalho da coluna B para abrir a caixa de diálogo **Cabeçalho da coluna** e insere as informações a seguir.

| Campo              | Alíquota                 |
|--------------------|-----------------------|
| Texto de cabeçalho da coluna | Real                |
| Inserir AutoTexto    | Nenhuma seleção feita. |
| Opções de formato     | Caixa                   |
| Justificativa      | Nenhuma seleção feita. |
| Difundir de        | E                     |
| Difundir para          | BASE                  |

Depois de inserir as informações, o usuário clica em **OK**. O usuário clica duas vezes na célula do cabeçalho da coluna C para abrir a caixa de diálogo **Cabeçalho da coluna** e insere as informações a seguir.

| Campo              | Alíquota                 |
|--------------------|-----------------------|
| Texto de cabeçalho da coluna | Orçamento                |
| Inserir AutoTexto    | Nenhuma seleção feita. |
| Opções de formato     | Caixa                   |
| Justificativa      | Nenhuma seleção feita. |
| Difundir de        | BASE+1                |
| Difundir para          | S                     |

Agora, toda vez que esse relatório é gerado, a palavra "Real" será impressa nas colunas que contiverem dados reais, e a palavra "Orçamento" será impressa nas colunas que contiverem previsões de orçamento. Além disso, o número das colunas será ajustado cada mês.

## <a name="apply-column-justification"></a>Aplicar a justificação de coluna
A célula **Justificação** é usada para aplicar formatação de justificação a uma coluna de descrição em um relatório. Esta opção afeta somente as descrições da coluna, não os valores reais.

1. No Report Designer, abra a definição de coluna que será modificada.
2. Clique duas vezes na célula **Justificação**.
3. Selecione um dos seguintes valores na lista:

    - **Nenhuma** – Nenhuma justificação é aplicada.
    - **Esquerda** – Alinhe as descrições da coluna à esquerda.
    - **Centro** – Alinhe as descrições da coluna no centro.
    - **Direita** – Alinhe as descrições da coluna à direita.

## <a name="add-special-formatting-options"></a>Adicionar opções de formatação especiais
Na definição de coluna, as linhas de detalhes da coluna de formatação aplicam a formatação especial nas colunas selecionadas. Embora algumas das opções de **Controle de impressão** e **Restrições de coluna** sejam específicas das colunas **FD**, a maioria das opções se aplicam a todos os tipos de colunas. A formatação especificada na definição de linha substitui a formatação especificada na definição da coluna e do relatório. Entretanto, a formatação especificada na definição de linha substitui a formatação especificada na definição da coluna. As linhas a seguir são consideradas linhas de formatação:

- Largura da coluna
- Espaços Extras Antes da Coluna
- Substituição de formato/moeda
- Controle de Impressão

### <a name="changing-the-column-width"></a>Alterando a largura da coluna

A célula **Largura da coluna** especifica o número de caracteres que serão usados na largura dessa coluna no relatório impresso. A largura da coluna é importante para colunas que contêm valores (colunas do tipo **CALC**, **WKS** ou **FD**), descrições (colunas do tipo **DESC**) ou preenchimento (colunas do tipo **FILL**). A opção **AutoFit** é selecionada por padrão, para que a largura de cada coluna seja automaticamente ajustada para se adequar ao conteúdo.

#### <a name="specify-the-width-of-a-column-on-a-report"></a>Especificar a largura de uma coluna em um relatório

1. No Report Designer, abra a definição de coluna que será modificada.
2. Na célula **Largura da coluna**, insira o número de espaços da largura da coluna. A largura máxima de qualquer coluna é 255 caracteres (esse número inclui centavos, vírgulas e parênteses). Como alternativa, para habilitar o Report Designer para selecionar a largura apropriada para a coluna, com base no conteúdo da célula, clique duas vezes na célula **Largura da coluna** e, depois, clique em **AutoAjuste**.

### <a name="add-space-between-columns"></a>Adicionar espaços entre colunas

A célula **Espaços extras antes da coluna** especifica a largura do separador entre uma coluna e as colunas adjacentes na definição da coluna. A configuração **Espaços extras antes da coluna** afeta todas as linhas de detalhe da coluna, mas não as linhas de cabeçalho da coluna. Use essa opção para separar grupos de colunas ou adicionar alguns espaços antes da descrição, de modo que a coluna de descrição seja recuada a partir dos títulos alinhados à esquerda que estão no relatório. O número padrão de espaços entre cada coluna é dois. Você pode alterar essa configuração na guia **Configurações** na definição de relatório.

#### <a name="specify-the-space-between-columns"></a>Especificar o espaço entre as colunas

1. No Report Designer, abra a definição de coluna que será modificada.
2. Na célula **Espaços extras antes da coluna**, insira o número de espaços que serão inseridos entre as colunas.

### <a name="specify-a-format-currency-override"></a>Especificar uma substituição de moeda de formato

A célula **Substituição de formato/moeda** especifica a formatação dos valores decimais, monetários e percentuais na coluna. Essa formatação substitui qualquer formatação que esteja especificada na definição de relatório ou padrões de sistema.

#### <a name="assign-a-format-currency-override-to-a-report-column"></a>Atribuir uma substituição de formato de moeda a uma coluna do relatório

1. No Report Designer, abra a definição de coluna que será modificada.
2. Clique duas vezes em uma célula **Substituição de formato/moeda** em uma coluna de valor.
3. Na caixa de diálogo **Substituição de formato**, selecione as opções de formatação.

### <a name="add-a-print-control-code"></a>Adicionar um código de controle de impressão

A célula **Controle de impressão** pode conter códigos que ajustam a exibição ou as características de impressão de uma coluna. Há dois tipos de códigos de controle de impressão: códigos de controle de impressão comuns e condicionais.

#### <a name="regular-print-control-codes"></a>Códigos comuns de controle de impressão

| Código de controle de impressão | Tradução                                     | Descrição |
|--------------------|-------------------------------------------------|-------------|
| NP                 | Não imprimível                                     | Impede que os valores dessa coluna sejam impressos no relatório e nos cálculos. Para incluir uma coluna não imprimível em um cálculo, consulte a coluna diretamente na fórmula do cálculo. Por exemplo, a coluna C sem impressão é incluída no seguinte cálculo: **B+C+D**. No entanto, a coluna C sem impressão não é incluída no seguinte cálculo: **B:D**. |
| XCR                | Alterar o sinal se o saldo típico da linha for crédito | Cria um orçamento, ou um relatório comparativo, no qual uma variação desfavorável (como um déficit de receita ou uma despesa excedente) é sempre negativa. Aplique este código a uma coluna **CALC** para reverter o sinal do valor da coluna se o saldo típico de uma determinada linha for crédito (como identificado por um **C** na coluna **Saldo normal** da definição da linha).<p><strong>Observação:</strong> para as linhas <strong>TOT</strong> e </strong>CAL</strong> que geralmente contêm um saldo de crédito, certifique-se de inserir o <strong>C</strong> na coluna <strong>Saldo normal</strong> na definição da coluna.</p> |
| X0            | Suprimir a coluna se todas as células contiverem zero ou estiverem em branco   | Exclua uma coluna **FD** do relatório se todas as células na coluna estiverem vazias ou contiverem zeros. |
| SR                 | Suprimir arredondamento                               | Impede que os valores dessa coluna sejam arredondados. |
| XR                 | Suprimir acúmulo                                 | Suprime um acúmulo. Se o relatório usa uma hierarquia organizacional, os valores dessa coluna não são acumulados em nós pais subsequentes. |
| RP                 | Repetir a coluna em cada página                      | Repete uma coluna especificada em cada página de um relatório. Por exemplo, você pode usar o código de controle de impressão **RP** para incluir uma coluna do tipo **ROW** que reúne códigos de linha em todas as páginas. |
| WT                 |  Quebrar texto                                      |  Se o texto em uma coluna for muito longo para se ajustar ao espaço, quebre o texto para mantê-lo inteiro na coluna. |

#### <a name="conditional-print-control-codes"></a>Códigos condicionais de controle de impressão

| Código condicional de controle de impressão | descrição                                                                             |
|--------------------------------|-----------------------------------------------------------------------------------------|
| (nenhum)                         | Desmarque a seleção de impressão condicional.                                                  |
| P&lt;B                         | Exiba uma coluna especifica apenas se os períodos forem inferiores ao período base.             |
| P&gt;B                         | Exiba uma coluna especifica apenas se os períodos forem superiores ao período base.             |
| P=B                            | Exiba uma coluna especifica apenas se os períodos forem iguais ao período base.              |
| P&lt;=B                        | Exiba uma coluna especifica apenas se os períodos forem inferiores ou iguais ao período base. |
| P&gt;=B                        | Exiba uma coluna especifica apenas se os períodos forem maiores ou iguais ao período base. |

#### <a name="add-print-control-codes-to-a-report-column"></a>Adicionar códigos de controle de impressão em uma coluna do relatório

1. No Report Designer, abra a definição de coluna que será modificada.
2. Clique duas vezes na célula **Controle de impressão**.
3. Na caixa de diálogo **Controle de impressão**, selecione um código na lista **Selecionar opções de controle de impressão**. Para selecionar mais de um código, mantenha a tecla CTRL pressionada enquanto seleciona os códigos.
4. Selecione uma opção no campo **Opções de impressão condicionais**. Por padrão, **(nenhum)** é selecionado. Você pode selecionar somente um código de impressão condicional de cada vez.
5. Clique em **OK**.

> [!TIP]
> Também é possível inserir os códigos de impressão diretamente na célula **Controle de impressão**. Separe os diversos códigos de controle de impressão por vírgulas.

## <a name="column-types"></a>Tipos de coluna
O tipo de informações que cada coluna em um relatório inclui é especificado pelo valor na linha **Tipo de coluna** na definição de coluna. Cada definição de coluna deve conter pelo menos uma coluna (**DESC**) de descrição e um valor (**FD**, **WKS** ou **CALC**).

> [!NOTE]
> Os códigos de tipo de coluna não se aplicam a todos os sistemas contábeis. Se você selecionar um tipo que não é válido com o sistema contábil, essa coluna aparece em branco no relatório.

### <a name="specify-a-column-type"></a>Especifique um tipo de coluna

1. No Report Designer, abra a definição de coluna que será modificada.
2. Na coluna apropriada, clique duas vezes em uma célula na linha **Tipo de coluna**.
3. Selecione um tipo de colina a partir da lista. A tabela a seguir descreve os vários tipos de colunas.

    <table>
    <thead>
    <tr>
    <th>Código do tipo de coluna</th>
    <th>Descrição</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>FD</td>
    <td>Exiba dados financeiros quando ao usar uma coluna <strong>Link para Dimensões Financeiras</strong> na definição da linha. Quando você seleciona o tipo de coluna <strong>FD</strong>, as configurações padrão são especificadas automaticamente nas linhas a seguir: <ul>
    <li><strong>Código do cenário/Categoria de atributo:</strong> ACTUAL</li>
    <li><strong>Código do cenário/Categoria de atributo:</strong> ACTUAL</li>
    <li><strong>Ano fiscal:</strong> BASE</li>
    <li><strong>Período:</strong> BASE</li>
    <li><strong>Períodos cobertos:</strong> PERIODIC</li>
    <li><strong>Largura da coluna:</strong> 14</li>
    </ul>
Essas configurações padrão podem ser alteradas.</td>
    </tr>
    <tr>
    <td>CALC</td>
    <td>Exiba o resultado de um cálculo simples ou complexo que é especificado na célula <strong>Fórmula</strong>. Para obter mais informações, consulte <a href="advanced-formatting-options-financial-reporting.md">Opções avançadas de formatação no relatório financeiro</a>.</td>
    </tr>
    <tr>
    <td>DESC</td>
    <td>Exiba a descrição da linha da definição de linha. Embora a coluna de descrição se geralmente a primeira coluna no relatório, ela pode estar em qualquer posição.</td>
    </tr>
    <tr>
    <td>ROW</td>
    <td>Exiba os códigos de linhas individuais das linhas financeiras da coluna <strong>Código de linha</strong> na definição de linha. Para obter mais informações, consulte <a href="row-definitions-financial-reporting.md">Definições de linha no relatório financeiro</a>.</td>
    </tr>
    <tr>
    <td>ACCT (Códigos de conta)</td>
    <td>Exiba os valores de segmento ou dimensão dos dados financeiros que se aplicam a cada linha. Para relatórios de conta e de detalhes da transação, a conta totalmente qualificada é impressa (por exemplo, <strong>110140-070-0101</strong>). Se os intervalos foram especificados na coluna <strong>Vincular a dimensões financeiras</strong> em uma definição de linha associada, eles serão incluídos em colchetes e são tratados como se fossem um valor único (por exemplo, <strong>[110140:110700]-070-[0101:0200]</strong>). Como os relatórios financeiros e de alto nível que são uma combinação de várias contas, o link de dados financeiros da definição de linha é impresso (por exemplo, <strong>1100:1200</strong>).</td>
    </tr>
    <tr>
    <td>FILL</td>
    <td>Preenche a célula com um caractere que é incluído entre aspas simples. Se você não inserir um caractere, a coluna ficará em branco. Por exemplo, para preencher uma coluna com reticências (...), insira <strong>FILL</strong> <strong>'.'</strong>.</td>
    </tr>
    <tr>
    <td>PAGE</td>
    <td>Insere uma quebra de página vertical no relatório. As colunas que estão à direita da coluna <strong>PAGE</strong> aparecem na coluna em uma página diferente.</td>
    </tr>
    <tr>
    <td>ATTR</td>
    <td>Se o seu sistema contábil oferece suporte aos atributos, exiba um atributo da conta ou transação na coluna. Um atributo, que deve ser aplicado a uma única conta total, extrai as informações da conta ou transação subjacente dos dados financeiros. Os atributos no nível da conta exibem dados da conta e atributos no nível da transação exibem dados que ocorrem no momento em que a transação é lançada. Se você selecionas <strong>ATTR</strong> como tipo de coluna, especifique a categoria de atributo na linha do detalhe <strong>Categoria do atributo</strong> na definição de coluna.</td>
    </tr>
    </tbody>
    </table>

### <a name="financial-dimensions-column"></a>Coluna de dimensões financeiras

As definições da linha **Definição de coluna** a seguir aplicam-se às colunas com um tipo de coluna **FD** (valores de dimensões financeiras).

#### <a name="book-codeattribute-category-cell"></a>Célula Código do Cenário/Categoria de Atributo

A célula **Código do livro/categoria do atributo** identifica o código do livro da data na coluna **FD**. Uma definição de coluna pode incluir várias colunas atuais, de orçamento e estatística. Uma definição de coluna também exibe diferentes períodos, como a data atual ou o acumulado no ano, e valores diferentes. A lista de códigos de livro reflete as opções reais, orçamentárias e estatísticas (não financeiras) que foram estabelecidas nos seus dados financeiros.

#### <a name="fiscal-year-cell"></a>Célula Ano fiscal

A célula **Ano fiscal** identifica o ano fiscal que a coluna deve incluir. O ano pode ser relativo ao ano base que é especificado quando o relatório é gerado. As opções a seguir estão disponíveis.

| Opção  | Descrição                                                                                                                  |
|---------|------------------------------------------------------------------------------------------------------------------------------|
| BASE    | Use o ano base que é especificado no momento do relatório.                                                                          |
| BASE+\# | Use o ano que é nº (\#) de anos após o ano base. Por exemplo, para usar o terceiro ano após o ano base, insira **BASE+3**. |
| BASE-\# | Use o ano que é nº (\#) de anos antes do ano base. Por exemplo, para usar o ano anterior, insira **BASE-1**.                 |
| \#      | Insira a ano fiscal real.                                                                                                |

#### <a name="period-cell"></a>Célula Período

A célula **Período** identifica os períodos fiscais que a coluna deve incluir. O período pode ser relativo ao período base que é especificado quando o relatório é gerado. As opções a seguir estão disponíveis.

| Opção          | descrição |
|-----------------|-------------|
| BASE            | Use o período base. |
| BASE+\#         | Use o período que é nº (\#) de períodos após o período base. Por exemplo, para usar o terceiro período após o período base, insira **BASE+3**. |
| BASE-\#         | Use o período que é nº (\#) de períodos antes o período base. Por exemplo, para usar o período anterior, insira **BASE-1**. |
| BASE-\#:BASE    | Use vários períodos, de diversos períodos antes do período base até o período base. Por exemplo, para usar os três períodos anteriores e o período base, insira **BASE-3:BASE**. |
| BASE:BASE+\#    | Use vários períodos, do período base até diversos períodos após o período base. Por exemplo, para usar o período base e os dois períodos a seguir, insira **BASE:BASE+2**. |
| BASE-\#:BASE+\# | Use vários períodos, de diversos períodos antes do período base até diversos períodos após o período base. Por exemplo, para usar os três períodos anteriores, o período base e os dois períodos a seguir, insira **BASE-3:BASE+2**. |
| 1:BASE          | Use vários períodos, do primeiro período ao período base. |
| \#              | Sempre use um número de período específico. Não recomendamos o uso dessa opção, porque ela reduz a flexibilidade da definição de coluna. |
| \#:\#           | Sempre use um intervalo específico de períodos. Não recomendamos o uso dessa opção, porque ela reduz a flexibilidade da definição de coluna. |

Você pode ultrapassar os limites do ano fiscal em qualquer uma das especificações de período e pode misturar anos em um intervalo de períodos. Por exemplo, você pode especificar os períodos como **BASE-5** (para representar os últimos seis períodos) e executar um relatório base de 2. Nesse caso, o relatório mostra os dados dos primeiros dois períodos do ano fiscal especificado e dos últimos quatro períodos do ano fiscal anterior.

### <a name="specify-the-periods-for-an-fd-column"></a>Especificar os períodos para uma coluna FD

1. No Report Designer, abra a definição de coluna que será modificada.
2. Em uma coluna **FD**, clique duas vezes na célula na linha **Período** e depois selecione uma opção na lista.
3. Na barra da fórmula acima do painel de navegação ou na célula **Período**, complete a fórmula. Substitua qualquer sinal numérico (\#) com o valor apropriado.

#### <a name="periods-covered-cell"></a>Célula Período coberto

A célula **Período coberto** identifica o valor que a coluna deve exibir. Esse valor é relativo ao valor nas células **Ano fiscal** e **Período** da coluna. As opções a seguir estão disponíveis.

| Opção      | Descrição                                                                 |
|-------------|-----------------------------------------------------------------------------|
| PERIODIC    | Exibe a soma da atividade do período atual ou do intervalo de períodos. |
| PERIODIC/BB | Exibe o saldo inicial do período atual ou do intervalo de períodos.   |
| YTD         | Exibe a soma da atividade do acumulado no ano.                               |
| YTD/BB      | Exibe o saldo inicial do ano.                                 |

### <a name="specify-the-periods-that-are-covered-for-an-fd-column"></a>Especifica os períodos cobertos para uma coluna FD

1. No Report Designer, abra a definição de coluna que será modificada.
2. Em uma coluna **FD**, clique duas vezes na célula na linha **Período coberto** e selecione uma opção na lista.

### <a name="attribute-filter-in-a-column-definition"></a>Filtro de atributo em uma definição de coluna

Os atributos são valores de dados financeiros que também definem uma conta ou uma transação. Os atributos da conta incluem **Ativo**, **Passivo**, **Receita** e **Despesa**. Os atributos da transação incluem **Descrição da transação** e **Data da aplicação da transação**. O suporte ao atributo pode ser diferente no Microsoft Dynamics 365 Finance. A célula **Filtro de atributo** restringe os dados em colunas **FD** para especificar valores e intervalos específicos de categorias do atributo. Embora esse recurso possa ser usado com uma coluna **ATTR**, a coluna **ATTR** não é necessária. Em uma coluna **FD**, há um limite nas contas ou transações que o relatório incluirá do filtro de atributos.

> [!NOTE]
> Para ver a quais atributos seu sistema ERP oferece suporte, consulte o guia de integração do sistema.

#### <a name="apply-an-attribute-filter-for-an-fd-column-on-a-report"></a>Aplicar um filtro de atributos para uma coluna FD em um relatório

1. No Report Designer, abra a definição de coluna que será modificada.
2. Clique duas vezes na célula **Filtro de atributo** de uma coluna **FD**.
3. Na caixa de diálogo **Filtro de atributo**, clique duas vezes em uma célula na coluna **Atributo** e, depois, selecione o tipo de filtro.
4. Para limitar mais os resultados, insira um intervalo nas colunas **De** e **Para**. A célula **De** deve conter um valor.
5. Clique em **OK**.

#### <a name="example-of-an-attribute-filter"></a>Exemplo de um filtro de atributo

Os exemplos a seguir mostram parte da descrição de uma coluna que tem um atributo de conta na linha **Código do livro/categoria do atributo**. O Filtro de Atributos dessa coluna especifica o intervalo de valores para incluir no relatório.

|      Filtro                  | A    | E                   |
|------------------------------|------|---------------------|
| Tipo de Coluna                  | DESC | FD                  |
| Código do Cenário/Categoria de Atributo |      | REAL              |
| Ano fiscal                  |      | BASE                |
| Período                       |      | 1:BASE              |
| Períodos Cobertos              |      | PERIODIC            |
| ...                          |      |                     |
| Largura da coluna                 | 30   |                     |
| ...                          |      |                     |
| Filtro de atributo             |      | Reference=\[01:10\] |

### <a name="dimension-filter-in-a-column-definition"></a>Filtro de dimensão em uma definição de coluna

Um filtro de dimensão é usado para restringir a coluna **FD** a valores de dimensão específicos. O filtro pode incluir uma única dimensão, um intervalo de dimensões, ou um grupo de dimensões. O filtro também pode incluir conjuntos de valores de dimensão. Como os valores de dimensão podem variar, um sistema baseado em dimensão ..\\financial-dimensions\\não precisa corresponder a um comprimento exato. O filtro é aplicado, independentemente de o relatório incluir ou não uma árvore de relatório. Você pode usar um caractere curinga (\* ou ?) em qualquer posição. Quando você especificar várias contas, coloque uma vírgula entre as contas, como no seguinte exemplo: +conta=\[1200\], +conta=\[1100\], departamento=\[01?\] para receber todos os departamentos de uma conta específica, é possível excluir a dimensão Departamento do filtro de dimensão. Por exemplo, ambos os filtros de dimensão a seguir são tratados da mesma forma:

- +Conta=\[1100\],Departamento
- +Conta=\[1100\]

Você também pode usar qualquer combinação de caracteres alfanuméricos para correspondência exata, bem como definir dimensões parciais. Por exemplo, **Local = \[10\*\]** inclui todos os valores de dimensão locais que começam com 10.

#### <a name="apply-a-dimension-filter-for-a-column-on-a-report"></a>Aplicar um filtro de dimensão a uma coluna em um relatório

1. No Report Designer, abra a definição de coluna que será modificada.
2. Clique duas vezes na célula **Filtro de dimensão** de uma coluna **FD**.
3. Na caixa de diálogo **Dimensões**, insira os filtros que serão aplicados.
4. Clique em **OK**.

### <a name="format-a-multiple-currency-report-in-a-column-definition"></a>Formatar um relatório de várias moedas em uma definição de coluna

Um relatório de várias moedas pode exibir valores na moeda contábil do razão, nos relatórios do razão, na moeda da transação de origem ou na moeda do relatório traduzido. A moeda contábil de uma empresa é definida na configuração dos razões. Não confunda essa configuração com a configuração das opções regionais do sistema operacional onde você pode configurar os símbolos de moeda padrão que são usados nos relatórios. As células relacionadas a moeda a seguir estão disponíveis na definição de coluna:

- **Exibição da moeda** – Especifique o tipo de moeda (contabilidade, relatório, transação ou relatório convertido) em que as transações são exibidas. Às vezes, a funcionalidade Convertida para uma moeda de relatório é chamada de conversão de moeda. Conversão de moeda é a capacidade de relatar valores da contabilidade em uma moeda que não seja a moeda funcional ou de relatório da empresa, nem a moeda na qual a transação foi inserida.
- **Filtro de moeda** – Especifique um filtro de moeda. Apenas as transações inseridas na moeda selecionada são mostradas no relatório.


Para determinar a moeda contábil de uma empresa, faça o seguinte:

1. No Report Designer, no menu **Empresa**, clique em **Empresas**.
2. Na caixa de diálogo **Empresas**, selecione uma empresa e depois clique em **Exibir**.
3. Na caixa de diálogo **Exibir empresa**, em **Opções regionais**, você pode exibir a moeda que é definida para a empresa selecionada.

#### <a name="specify-the-currency-on-a-multiple-currency-report"></a>Especificar a moeda em um relatório de várias moedas

1. No Report Designer, abra a definição de coluna que será modificada.
2. Clique duas vezes na célula **Exibição de moeda** na coluna apropriada **FD** e selecione a opção para exibir informações da moeda: **Moeda contábil do razão**, **Relatório do razão**, moeda da transação ou selecione para converter para outra moeda de relatório.
3. Clique duas vezes na célula **Filtro de moeda** na coluna **FD** apropriada e depois selecione o código de moeda adequado na lista. Apenas as transações inseridas nessa moeda serão mostradas no relatório.


### <a name="example-for-currency-display-and-currency-filter-cells"></a>Exemplo de células exibição de moeda e filtro de moeda

Um usuário fez as seguintes seleções de moeda em sua definição de coluna:

- **Filtro de moeda:** ienes
- **Exibição da moeda:** moeda contábil do razão (dólares americanos)

Devido ao filtro de moeda selecionado, o relatório inclui apenas as transações que foram inseridas em iene japonês (JPY). Por causa da seleção de exibição da moeda, o relatório exibe as transações na moeda contábil, dólares americanos (USD).

#### <a name="currency-filter-and-currency-display-combinations"></a>Combinações de filtro de moeda e exibição de moeda

A tabela a seguir mostra os resultados do relatório que podem ocorrer em várias combinações das opções nas células **Exibição de moeda** e **Filtro de moeda** por causa das seleções feitas. A moeda funcional é USD.


| Célula Exibição de Moeda                        | Célula Filtro de Moeda | Resultado do relatório |
|----------------------------------------------|----------------------|---------------|
| Moeda da transação                 | **YEN**              | **Ұ6.000** – O resultado mostra apenas transações que foram inseridas em JPY. |
| Moeda contábil do razão | **YEN**              |**US$60** – O resultado mostra apenas transações que foram inseridas em JPY e exibe as transações em USD.<p><strong>Observação:</strong> a taxa de conversão é de aproximadamente 100 JPY por USD.</p> |
| Moeda contábil do razão | Vazio                | **US$ 2.310** – O resultado mostra todos os dados na moeda contábil que é especificada no razão.<p><strong>Observação:</strong> Este valor é a soma de todas as transações na moeda contábil.</p> |
| Moeda da transação                 | Vazio                | **US$2.250** – O resultado mostra todos os valores na moeda na qual a transação foi realizada. Isso significa que o total está adicionando valores de diferentes moedas. |

### <a name="calculation-column-in-a-column-definition"></a>Coluna de cálculo em uma definição de coluna

Um tipo de coluna de **CALC** em uma definição de coluna que permite cálculos complexos na célula **Fórmula** e pode incluir os operadores **+**, **-**, **\**_ e _*/** e também as Instruções **IF/THEN/ELSE**. Uma coluna de cálculo também pode fazer referência a qualquer outra coluna, até mesmo colunas subsequentes. Além disso, uma coluna de cálculo também pode incluir o ano fiscal e o período para dar suporte aos cabeçalhos da coluna. A fórmula de cálculo pode ter até 1024 caracteres. Para expressar o resultado do cálculo como uma porcentagem, use uma substituição de formato especial.

> [!NOTE]
> Os resultados das fórmulas de cálculo não incluem os valores em intervalos não imprimíveis da coluna. Por exemplo, **A:D** imprime **0** (zero), enquanto **A+B+C** dos valores sem impressão calcula o valor.

#### <a name="operators-in-calculation-columns"></a>Operadores em colunas de cálculo

Para adicionar, subtrair, multiplicar ou dividir colunas, digite as letras da coluna na ordem de cálculo e use o operador apropriado para separar cada letra da coluna. A seguinte tabela explica os operadores que você pode usar em uma coluna de cálculo.

| Operador | Exemplo de cálculo | descrição |
|----------|---------------------|-------------|
| +        | A+C                 | Adicione o valor na coluna A ao valor na coluna C. |
| :        | A:C A:C-D           | Adicionar um intervalo de colunas consecutivas. Por exemplo, a fórmula **A:C** adiciona as somas das colunas A a C e a fórmula **A:C-D** adiciona as somas das colunas A a C e depois subtrai o valor na coluna D. |
| -        | A-C                 | Subtrair o valor na coluna A do valor na coluna C.<p><strong>Observação:</strong> você também pode usar o sinal de menos (-) para reverter os sinais em uma coluna. Por exemplo, use <strong>-A+B</strong> para adicionar o reverso do valor na coluna A ao valor na coluna B.</p> |
| \*       | A\*C                | Multiplique o valor na coluna A pelo valor na coluna C. |
| /        | A/C                 | Divida o valor na coluna A pelo valor na coluna C. |

#### <a name="use-a-calculation-formula-in-a-column-definition"></a>Usar uma fórmula de cálculo em uma definição de coluna

1. No Report Designer, abra a definição de coluna que será modificada.
2. Na coluna **CALC** apropriada, insira uma fórmula na célula **Fórmula**.

#### <a name="complex-calculations"></a>Cálculos complexos

Um cálculo complexo pode conter qualquer combinação de referências de células, operadores, dos valores e de níveis de parênteses aninhados. Por exemplo, para calcular a média das colunas A e B, use a fórmula de cálculo **((A+B)/2)**.

#### <a name="specify-report-cells-in-a-column-calculation"></a>Especificar as células do relatório em um cálculo de coluna

Você pode fazer referência a uma célula de relatório específica digitando uma letra de coluna e um código de linha. Por exemplo, **B.100** indica o código de linha 100 na coluna B. Você pode dividir uma coluna inteira pelo valor de uma célula de relatório específica que está na mesma coluna. Por exemplo, o cálculo **B/B.100** significa que o valor na coluna B deve ser dividido pelo valor no código de linha 100 na coluna B. Se o cálculo indicar uma coluna que depende de outra coluna, a coluna dependente é convertida primeiro. Se você relacionar uma coluna a outra que, por sua vez, se refere à primeira coluna, você causará um erro de referência circular.

> [!NOTE]
> O cálculo pode ficar incorreto se você alterar a prioridade de cálculo para o relatório. Você pode definir a prioridade de cálculo na guia **Configurações** da definição de relatório.

#### <a name="multiply-or-divide-a-column-by-a-base-row"></a>Multiplicar ou dividir uma coluna por uma linha de base

Você pode criar uma coluna que exibe todos os valores em uma coluna especificada como uma porcentagem de um número de base. Portanto, você pode mostrar os relacionamentos entre linhas, como uma porcentagem de uma linha de venda ou uma porcentagem de uma linha de despesas totais. Para multiplicar ou dividir cada linha em uma coluna especifica por uma linha base, insira a coluna que será usada no cálculo e depois insira **\*BASEROW** ou **/BASEROW**. Por exemplo, insira **C\*BASEROW** ou **C/BASEROW**.

> [!NOTE]
> Quando você usa um cálculo de linha de base em uma definição de coluna, verifique se cada definição de linha que é usada em essa definição de coluna contém pelo menos uma linha de base para cálculos.

#### <a name="divide-the-amount-in-a-column-by-the-number-of-periods"></a>Dividir o valor na coluna pelo número de períodos

Você pode dividir o valor em uma coluna por um número especificado de períodos. Por exemplo, **B/Períodos** divide o valor na coluna B pelo número de períodos na coluna B. Se o cálculo abranger várias colunas, especifique o número de períodos que serão usados no cálculo. Por exemplo, a fórmula **(B+C)/Períodos** adiciona os valores na coluna B e coluna C e depois divide o resultado pelo valor do período.

## <a name="additional-resources"></a>Recursos adicionais

[Definições de linha no designer de relatório financeiro](row-definitions-financial-reporting.md)

[Opções avançadas de formatação no relatório financeiro](advanced-formatting-options-financial-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
