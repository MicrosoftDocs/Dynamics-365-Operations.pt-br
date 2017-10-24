---
title: "Definições de linha no designer de relatório financeiro"
description: "Uma definição de linha é um componente de relatório ou bloco de construção que especifica o conteúdo de cada linha em um relatório financeiro. Uma definição de linha pode ser combinada com as definições de coluna, definições de árvore de relatórios e as definições de relatório para criar um grupo do bloco de construção que possa ser usado por várias empresas."
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Management Reporter, UnifiedOperations, Core
ms.custom: 68873
ms.assetid: 2fd7b5da-700f-48cb-9003-90c0d82f818f
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 06a75889e62cbba6e47a8543cf663868df5ae2e3
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="row-definitions-in-financial-report-designer"></a>Definições de linha no designer de relatório financeiro

[!include[banner](../includes/banner.md)]


Uma definição de linha é um componente de relatório ou bloco de construção que especifica o conteúdo de cada linha em um relatório financeiro. Uma definição de linha pode ser combinada com as definições de coluna, definições de árvore de relatórios e as definições de relatório para criar um grupo do bloco de construção que possa ser usado por várias empresas.

<a name="create-a-row-definition"></a>Criar uma definição de linha
-----------------------

1.  No Designer de Relatórios, no painel de navegação, clique em **Definições de linha**.
2.  No menu **Arquivo**, clique em **Novo** e clique em **Definição de Linha**. Para obter mais informações sobre o conteúdo de cada célula, consulte [Modifique células de definição de linha](modify-row-definition-cells-financial-reporting.md).

## <a name="open-a-row-definition"></a>Abrir uma definição de linha
1.  No Designer de Relatórios, no painel de navegação, clique em **Definições de linha**.
2.  Clique duas vezes no nome da definição de linha a ser aberta.
3.  Para exibir todos os blocos de construção que estejam associados à definição de linha, clique com o botão direito do mouse na definição de linha e selecione **Associações**.

## <a name="contents-of-a-row-definition"></a> Conteúdo de uma definição de linha
Uma definição de linha pode conter até 20.000 linhas de dimensão financeira e pode incluir as seguintes informações:

-   O texto descritivo que confere significado ao relatório ao criar títulos, linhas e espaços na seção, como **Pagamento à vista** ou **Receita total**
-   Links para dados financeiros, que podem incluir valores de dimensão no Microsoft Dynamics 365 for Finance and Operations **Observação:** Você pode configurar uma definição de linha para puxar dados do sistema de dimensões financeiras sempre que o relatório é gerado.
-   Os totais de linhas e as fórmulas que se baseiam nos dados financeiros vinculados

Geralmente, cada linha em uma definição de linha contém um dos seguintes tipos de informações:

-   Referências ao sistema de dimensões financeiras
-   Totais ou cálculos que são baseados nos dados
-   Formatação

Há dois métodos para a inserção de informações em uma definição de linha:

-   Insira informações de linha manualmente em uma nova definição de linha. Para obter mais informações, consulte [Modifique células de definição de linha](modify-row-definition-cells-financial-reporting.md).
-   Use o designer de relatórios para extrair informações de linha diretamente das dimensões financeiras. Para obter mais informações, consulte a seção "Fórmulas relacionadas/linhas/unidades" em [Modificar células de definição de linha](modify-row-definition-cells-financial-reporting.md).

## <a name="add-dimensions-in-a-row-definition"></a> Adicionar dimensões em uma definição de linha
Uma dimensão é uma interseção de dados e valores. Você pode agrupar dados e valores no designer de relatórios. Em seguida, você pode classificar e analisar transações mais detalhadamente. É possível usar a caixa de diálogo **Inserir Linhas de Dimensões** para adicionar várias linhas ao mesmo tempo em uma definição de linha. A caixa de diálogo exibe uma coluna para cada dimensão. A tabela a seguir descreve as informações que você pode especificar para cada dimensão.

| Opção                | Descrição                                                                                                                                                                                                                                                                      |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Dimensão             | O padrão que identifica a dimensão a ser adicionada à definição de linha. Este padrão contém um E comercial (&) ou sinal numérico (\#) para cada posição nas dimensões. Em geral, use E comerciais para a dimensão Conta principal e sinais numéricos para outras dimensões. |
| Início do Intervalo de Dimensões | O primeiro valor dessa dimensão para adicionar à definição de linha.                                                                                                                                                                                                                 |
| Fim do Intervalo de Dimensões   | O último valor desta dimensão a ser adicionado à definição de linha.                                                                                                                                                                                                                  |

Para adicionar dimensões a uma definição de linha, siga as etapas a seguir.

1.  No Designer de Relatórios, clique em **Definições de Linha** e abra a definição de linha para modificá-la.
2.  No menu **Editar**, clique em **Inserir Linhas de Dimensões**.
3.  Na caixa de diálogo **Inserir Linhas de Dimensões**, na linha **Dimensões**, selecione a célula da dimensão a ser transferida para a definição de linha e clique em **Todos &&&**.
4.  Para limitar a definição de linha a um intervalo específico de valores de dimensões, digite o valor de dimensão inicial na célula **Início do Intervalo de Dimensões**, e digite o valor de dimensão final na célula **Final do Intervalo de Dimensões**. Para incluir todos os valores da dimensão selecionada, deixe essas células vazias. **Observação:** Os caracteres curinga (\* ou ?) em intervalos de dimensão não podem retornar todos os resultados desejados, dependendo de como o banco de dados ERP agrupa dados.
5.  No campo **Código de linha inicial** para especificar o código de linha para o primeiro valor de dimensão a ser adicionado à definição de linha.
6.  No campo **Incrementar cada linha em** para especificar o intervalo entre os códigos de linha consecutivos. Por exemplo, se o primeiro código de linha é 100 e o valor de incremento é 30, as primeiras novas linhas têm os códigos 100, 130, 160, 190 e 220. Use um valor de incremento que forneça espaço suficiente para inserir novas linhas de formato e fórmula.
7.  Clique em **OK**. Para cada uma dos valores de dimensão selecionados, uma linha é adicionada a definição da linha.

## <a name="adjust-rounding-in-a-row-definition"></a> Ajustar arredondamento em uma definição de linha
Quando você tem um balanço em que os valores são arredondados, talvez os totais estejam sem saldo. Esse problema pode ocorrer se, por exemplo, você usar a opção de arredondamento em um relatório de balancete e a definição de relatório também especificar o arredondamento. Você pode usar a opção de **arredondamento de ajuste** na definição de linha para equilibrar os valores no balanço patrimonial. Você pode desativar o arredondamento ou modificá-lo na guia **Configurações** da definição de relatório. A tabela a seguir mostra como os valores são arredondados. Nesta tabela, os totais das linhas 100 e 200 diferem quando o arredondamento está ativado.

| Código da linha | Valores sem arredondamento | Valor com arredondamento para milhares |
|----------|--------------------------|-----------------------------------------|
| 100      | 3,600                    | 4                                       |
| 200      | 3,700                    | 4                                       |
| Total    | 7,300                    | 8                                       |

Para ajustar o arredondamento em um balanço, siga as etapas a seguir.

1.  No Designer de Relatórios, clique em **Definições de Linha** e abra a definição de linha para modificá-la.
2.  No menu **Editar**, clique em **Ajuste de arredondamento**.
3.  Na caixa de diálogo **Ajustes de Arredondamento**, insira os seguintes valores:
    -   **Linha de ajuste de arredondamento** – O código de linha da linha que deverá ser ajustada para equilibrar o balanço.
    -   **Linha de total de ativos** – O código de linha da linha no balanço que contém os ativos totais.
    -   **Linha de total de passivos e capital próprio** – O código de linha da linha no balanço que contém o total de passivos e capital próprio.
    -   **Limite de valor de ajuste** – Um limite positivo que especifica o limite em ajustes automáticos. Esse valor é comparado ao valor absoluto da diferença de arredondamento real.

    **Observação:** Esses códigos de linha devem estar vinculados aos seus dados financeiros. Em outras palavras, a linha deve ter um valor de dimensão na célula **Link para Dimensões Financeiras**. Não **referencie** uma linha de descrição (**DESC**), calculada (**CALC**) ou totalizada (**TOT**).

Os valores no balanço serão equilibrados agora uniformemente quando o arredondamento estiver ativado. **Observação:** O limite de ajuste é aplicado com base na opção **Precisão de arredondamento** que é especificada para a definição de relatório. Por exemplo, se você selecionar para arredondar o relatório em milhares e inserir **2** no campo **Limite de valor de ajuste**, será exibida uma mensagem de aviso quando o valor identificado no campo **Linha de ajuste de arredondamento** aumentar ou diminuir em mais de US$ 2.000.

## <a name="format-row-and-column-text"></a>Linha de formato e texto da coluna
Você pode personalizar a aparência dos relatórios alterando fontes e formatação de texto. As seções a seguir explicam como formatar a aparência de linhas e colunas em relatórios.

### <a name="manage-font-styles"></a>Gerenciar estilos de fontes

Você pode criar e modificar estilos de fonte para o relatório. Em seguida, você pode aplicar esses estilos para o documento ou a uma linha específica ou uma coluna em um relatório.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Criar um estilo de fonte</td>
<td><ol>
<li>No Designer de Relatórios, no menu <strong>Formato </strong>, clique em <strong>Estilos e Formatação</strong>.</li>
<li>Na caixa de diálogo <strong>Estilos e formatação</strong>, clique em <strong>Novo</strong> e insira um nome exclusivo para o novo estilo.</li>
<li>Faça as seleções de fonte e, em seguida, clique em <strong>OK</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Modificar um estilo de fonte</td>
<td><ol>
<li>No Designer de Relatórios, no menu <strong>Formato </strong>, clique em <strong>Estilos e Formatação</strong>.</li>
<li>Na caixa de diálogo <strong>Estilos e formatação</strong>, selecione um estilo para modificar e clique em <strong>Modificar</strong>.</li>
<li>Faça as seleções de fonte e, em seguida, clique em <strong>OK</strong>.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Aplicar um estilo de fonte</td>
<td><ol>
<li>Em designer de relatório, uma definição ou definição de coluna, ou em cabeçalhos e rodapés, selecione uma ou mais células.</li>
<li>Na lista <strong>Estilo</strong> na barra de ferramentas, selecione um estilo de fonte.</li>
</ol></td>
</tr>
</tbody>
</table>

### <a name="format-row-text"></a>Formatar texto de linha

A formatação que é especificada na definição de coluna substitui a formatação que é especificada na definição de relatório. Você pode modificar o formato do texto usando os controles na barra de ferramentas Formatação. Esses controles são controles padrão do Microsoft Windows.

1.  No Designer de Relatórios, abra a definição de linha a ser modificada.
2.  Selecione as células para formatar. Para selecionar várias células, mantenha pressionada a tecla CTRL enquanto seleciona a célula.
3.  Clique no botão na barra de ferramentas do formato a ser aplicado. Por exemplo, para recuar uma linha, selecione a linha e clique em **Aumentar recuo** ![Aumentar recuo](https://i-technet.sec.s-msft.com/dynimg/IC679497.gif "Aumentar recuo") na barra de ferramentas.

### <a name="adjust-columns-while-you-design-reports"></a>Ajuste colunas ao criar relatórios

Para facilitar a exibição das colunas em que estiver trabalhando na definição de linha, você poderá ajustar a largura de uma coluna, e ocultar (minimizar) ou mostrar colunas no painel de exibição. As modificações que você fizer afetarão somente a tela aparente das colunas. Elas não afetam a coluna de formatação nos relatórios.

### <a name="change-the-width-of-a-column-in-the-view-pane"></a>Alterar a largura de uma coluna no painel de exibição

1.  No Designer de Relatórios, abra a definição de linha a ser modificada.
2.  No menu **Formato**, selecione **Largura da Coluna**.
3.  Na caixa de diálogo **Largura da coluna**, insira um valor, e clique em **OK**. De forma alternativa, você também pode arrastar o limite direito de uma célula de título da coluna para alterar a largura da coluna.

### <a name="hide-columns-in-the-view-pane"></a>Ocultar colunas no painel de exibição

1.  No Designer de Relatórios, abra a definição de linha a ser modificada.
2.  Selecione uma ou mais colunas para minimizar.
3.  Clique no botão direito do mouse e clique em **Ocultar**.

### <a name="show-all-hidden-columns-in-the-view-pane"></a>Mostrar todas as colunas ocultas no painel de exibição

1.  No Designer de Relatórios, abra a definição de linha a ser modificada.
2.  Clique com o botão direito do mouse na coluna minimizada a ser exibida. Clique em **Reexibir**.


<a name="see-also"></a>Consulte também
--------

[Relatórios financeiros](financial-reporting-intro.md)




