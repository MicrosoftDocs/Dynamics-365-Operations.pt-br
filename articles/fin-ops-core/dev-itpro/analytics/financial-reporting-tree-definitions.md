---
title: Definições da árvore de relatórios em relatórios financeiros
description: Este artigo descreve as definições de árvore de relatórios. Uma definição de árvore de relatórios é um componente de relatório que define a estrutura de uma organização.
author: ShylaThompson
manager: AnnBe
ms.date: 10/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 57592
ms.assetid: 747faa47-9a23-4277-bc11-8d0a1267c3a4
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 17f749863af3c37658935d5065cf053d0a165c1e
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093891"
---
# <a name="reporting-tree-definitions-in-financial-reports"></a>Definições da árvore de relatórios em relatórios financeiros

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre definições da árvore de relatório. Uma relatório definição de árvore é um componente de relatório ou bloco de construção, que ajuda a definir a estrutura e a hierarquia de sua organização.

O relatório financeiro dá suporte ao relatório flexível, tornando fácil fazer alterações à medida que a estrutura de negócios muda. Relatórios são criados a partir de vários componentes, ou blocos de construção. Um desses blocos de construção é uma definição de árvore de relatórios. Uma relatório de definição de árvore ajuda a definir a estrutura e a hierarquia de sua organização. Você pode criar hierarquias em várias dimensões com base nas relações dimensionais nos dados financeiros. Ele fornece informações no nível de unidade de geração de relatórios e no nível de resumo para todas as unidades na árvore. As definições de árvore de relatórios podem ser combinadas com as definições de coluna e as definições de relatório para criar um grupo do bloco de construção que possa ser usado por várias empresas. Uma unidade de relatório é usada para cada caixa em um organograma. Uma unidade organizacional pode ser um departamento individual de dados financeiros, ou pode ser uma unidade de resumo de alto nível que combina informações de outras unidades organizacionais. Para obter uma definição de relatório que inclua uma árvore de relatório, um relatório é gerado para cada unidade de relatório e para o nível de resumo. Todos esses relatórios usam as definições de linhas e colunas que são especificadas na definição de relatório, a menos que a definição de relatório especifique a árvore de relatório da definição de linha que deve ser usada. As definições de linhas e colunas são componentes importantes no design e funcionalidade de relatórios financeiros. As árvores de relatório aumentam a potência dos componentes e dão suporte a relatórios flexíveis à medida que a estrutura muda. Relatórios financeiros não baseados no uso de uma árvore de relatório usam apenas alguns recursos do relatório financeiro. Você pode usar várias definições de árvore de relatório com as mesmas definições de linhas e colunas para exibir os dados da organização de várias formas.

## <a name="reporting-tree-best-practices"></a>Práticas recomendadas da árvore de relatório
Antes de criar uma árvore de relatório, considere estas práticas recomendadas:

- Primeiro, determine as dimensões de relatório que a entidade legal ou empresa requer.
- Considere como você configurou sua estrutura, e desenhe um organograma da sua empresa. O organograma o ajudará a visualizar como agrupar as unidades organizacionais em uma ou mais hierarquias organizacionais.
- Comece com o menor nível de detalhes disponível, como os departamentos e projetos que são definidos nos dados financeiros. Adicione as caixas necessárias no nível de detalhe para mostrar divisões ou regiões de nível superior. Cada caixa representa uma unidade de relatório potencial em qualquer árvore de relatório criada.
- Considere também a melhor maneira de criar as árvores. Você pode usar um processo de criação automatizado para criar uma árvore de relatório manualmente, ou pode criar uma árvore de relatório. É importante compreender os dois métodos antes de criar as árvores.
- Você pode usar as unidades de relatório que são definidas no sistema de dados financeiros para adicionar unidades de relatório na definição da árvore de relatório.

## <a name="create-multiple-reporting-trees"></a> Criar várias árvores de relatório
Você pode criar um número ilimitado de árvores de relatório para exibir os dados da organização de várias formas. Cada hierarquia organizacional pode conter combinações de departamentos e unidades de resumo. Uma definição de relatório pode conter um link para uma árvore de relatório de cada vez. Ao reorganizar a estrutura das unidades de relatório, você pode criar diferentes árvores de relatório. Você pode usar a mesma linha e coluna para cada árvore de geração de relatórios. Dessa maneira, você pode rapidamente criar layouts diferentes de relatórios financeiros. Se você criar várias árvores de relatório distintas, poderá imprimir uma série de demonstrativos financeiros a cada mês, que analisam e apresentam as operações da empresa de diversas formas. Para mais informações, veja os exemplos de estruturas da unidade de relatório no final deste artigo.

## <a name="create-a-reporting-tree-definition"></a> Criar uma definição da árvore de relatório
A definição da árvore de relatório contém as colunas descritas na tabela a seguir.

| Coluna da árvore de relatório | Descrição |
|-----------------------|-------------|
| Empresa               | O nome da empresa para a unidade organizacional. O valor **\@ANY**, que geralmente é atribuído apenas ao nível resumido, permite que a hierarquia organizacional seja usada em todas as empresas. Todas as ramificações filho que têm uma empresa atribuída a elas. |
| Nome da unidade             | O código que identifica esta unidade de relatório na árvore gráfica do relatório. Certifique-se de estabelecer um sistema de codificação exclusivo que é consistente e que seja fácil de entender. |
| Descrição da Unidade      | O título da unidade de relatório aparece no cabeçalho ou rodapé do relatório se você insere **UnitDesc** como um código na guia **Cabeçalhos e Rodapés** da definição de relatório. O título aparece na descrição da linha do relatório se você insere **UnitDesc** na célula **Descrição** de definição da linha. |
| Dimensões            | Uma unidade de relatório que obtém informações diretamente dos dados financeiros. Ela define o posicionamento e os comprimentos lógicos da conta e os segmentos relacionados. Cada linha de unidade de relatório deve ter uma dimensão nesta coluna. Você também pode colocar uma dimensão em uma linha de resumo de unidade (por exemplo, para as despesas que estão diretamente relacionadas a essa unidade). Se você inserir uma dimensão em uma linha da unidade de resumo, as contas usadas em unidades pai não deverão ser usadas em unidades filho. Caso contrário, os valores podem ser duplicados. |
| Definições de Linha       | O nome da definição de linha para a unidade de relatório. A mesma definição de linha é usada para cada unidade da hierarquia organizacional. Ao gerar um relatório, essa definição de linha é usada para cada unidade organizacional. A definição de linha pode incluir vários links de dimensões financeiras. Se uma definição de linha for especificada na hierarquia organizacional, marque a caixa de seleção **Usar a definição de linha da hierarquia organizacional** na guia **Relatório** da definição de relatório. |
| Link da linha              | O link de linha a ser usado para a unidade organizacional. Os links de linha são definidos para que a definição de linha identifique as dimensões financeiras às quais se vincular. |
| Link externo         | O link de linha a ser usado para essa unidade organizacional. Os links de linhas são definidos para a definição de linha para identificar os relatórios para vínculo. |
| Arquivo externo         | O caminho do arquivo da planilha de relatórios financeiro para extrair dados de. |
| Opções de Página          | Esta coluna controla se os detalhes para a unidade de relatório são suprimidos quando o relatório é visualizado ou impresso. |
| % Acumulado              | A porcentagem da unidade de relatório que deve ser alocada para a unidade pai. A porcentagem inserida nesta coluna se aplica a cada linha da definição de linha antes de o valor da linha ser adicionado ao relatório pai. Por exemplo, se uma unidade filho deve ser dividida uniformemente entre dois departamentos, os valores em cada linha seriam multiplicados por 50% antes do valor ser adicionado ao relatório do departamento. Uma unidade de relatório não pode ter duas unidades pai. Para alocar os valores de uma unidade de relatório em duas unidades pai, crie outra unidade de relatório com a mesma dimensão para acumular os 50% adicionais. Digite os percentuais inteiros sem um ponto decimal. Por exemplo, **25** representa a alocação de 25% para o pai. Se você incluir um ponto decimal (**25**), porcentagem de 0,25 é alocada para o pai. Para usar uma porcentagem menor do que 1%, use a opção **Permitir Acúmulo &lt;1%** na definição de relatório. Esta é uma opção da guia **Opções Adicionais** na caixa de diálogo **Configurações de Relatório**. Acesse essa caixa de diálogo do botão **Outros** na guia **Configurações** da definição de relatório. |
| Segurança de Unidade         | As restrições do acesso de usuários e grupos às informações da unidade de relatório. |
| Texto Adicional       | O texto que é incluído no relatório. |

Para criar uma definição de árvore de relatório, siga estas etapas.

1. Abra o Designer de Relatórios.
2. Clique em **Arquivo** &gt; **Novo** &gt; **Definição de Árvore de Relatório**.
3. Clique em **Editar** &gt; **Inserir Unidades de Relatório de Dimensões**.
4. Na caixa de diálogo **Inserir Unidades de Relatório de Dimensões**, marque a caixa de seleção para cada dimensão a ser incluída na árvore de relatório. A caixa de diálogo **Inserir Unidades de Relatório de Dimensões** contém as seções a seguir.

    | Seção                          | Descrição |
    |----------------------------------|-------------|
    | Segmentação de dimensão de relatório | Use os botões **Dividir Segmentos** e **Combinar Segmentos** para alterar o número e o tamanho dos segmentos.<blockquote>[!NOTE] Você só pode combinar segmentos que foram divididos. Para combinar várias dimensões, use caracteres curinga nos valores de dimensão.</blockquote> |
    | Incluir/Posição do caractere       | Lista as dimensões que são definidas nos dados financeiros e mostra o número de caracteres no maior valor definido para cada dimensão. Marque uma caixa de seleção de uma dimensão para incluir essa dimensão na hierarquia de árvore de relatório. |
    | Hierarquia e intervalos de segmento     | A seção mostra a hierarquia de dimensão. Você pode mover as dimensões na lista para alterar a ordem de relatório. Especifique um intervalo de valores em cada dimensão nos campos **Da Dimensão** e **Para Dimensão**. Se você não especificar um intervalo, todos os valores de dimensão são inseridos na árvore de relatório.<blockquote>[!NOTE] Se você estiver usando mais de uma dimensão, apenas as combinações de dimensão que foram lançadas serão retornadas nos resultados.</blockquote> |

    Uma captura de tela que mostra um exemplo da caixa de diálogo **Inserir Unidades de Relatório de Dimensões**, consulte a seção "Exemplo de caixa de diálogo Inserir Unidades de Relatório de Dimensões" posteriormente neste artigo.

5. Para criar segmentos adicionais (como a quebra de um segmento em dois segmentos mais curtos), clique no local correto em um campo **Posição do caractere** e clique em **Dividir Segmentos**.
6. Para mesclar dois segmentos em um segmento, clique em uma das caixas de segmento para mesclar os segmentos e, depois, em **Combinar Segmentos**.
7. A hierarquia define como as dimensões se reportam umas às outras, e o intervalo de cada dimensão. Para mudar a hierarquia das dimensões na área **Hierarquia e intervalos de segmento**, selecione a dimensão a ser movida e clique em **Mover para Cima** ou **Mover para Baixo**.
8. Para especificar um intervalo de valores de dimensão para adicionar à nova árvore de relatório, na área **Hierarquia e intervalos de segmento**, siga estas etapas:

    1. No campo **Da Dimensão** dessa dimensão, digite o primeiro valor no intervalo.
    2. No campo **Da dimensão**, insira o último valor no intervalo.

9. Repita as etapas 7 a 8 para cada dimensão na área **Hierarquia e intervalos de segmento**.
10. Ao concluir a definição de como as unidades de relatório são trazidas para a nova árvore de relatório, clique em **OK**.
11. Clique em **Arquivo** &gt; **Salvar** para salvar a árvore de relatório. Insira um nome exclusivo e uma descrição da árvore de relatório. Clique em **OK**.

### <a name="open-an-existing-reporting-tree-definition"></a>Abrir uma definição de árvore de relatório existente

1. No Designer de Relatórios, clique em **Definições de Árvore de Relatórios** no painel de navegação.
2. Clique duas vezes em um nome na lista de árvore de relatório para abri-lo.
3. Para exibir os blocos de construção associados à árvore de relatório, clique com o botão direito do mouse na definição de árvore de relatório e selecione **Associações**.

### <a name="roll-up-data-in-a-reporting-tree"></a>Acumular dados em uma árvore de relatório

Quando usa uma árvore de relatório, você pode agregar valores de unidades de relatório filho no nível da unidade de relatório pai. Essa agregação é conhecida como acúmulo de dados. As seguintes regras são usadas para acumular valores para unidades pai em uma árvore do relatório:

- Na árvore de relatório, as unidades filho devem conter dimensões, a menos que a árvore de relatório seja uma árvore de nível único. As unidades pai em geral não contêm dimensões em uma árvore de relatório.

    > [!NOTE]
    > Especificar dimensões para unidades filho e unidades pai pode causar a duplicação de dados no relatório.

- As unidades de relatório que contêm dimensões na árvore de relatório correspondem às dimensões que são usadas nas definições de linha e coluna. A combinação de dimensões determina os valores retornados para essa unidade. Por exemplo, no exemplo 2 posteriormente neste artigo, as linhas 6 e 7 devolvem valores apenas para departamentos 00 e 01, respectivamente.
- Os valores das unidades de relatório pai que não contêm dimensões na árvore do relatório são determinados a partir do relatório de unidade filho e acumulam o valor para a unidade pai especificada. Por exemplo, se a unidade pai (consulte Contoso EUA no exemplo 2 dos exemplos de acúmulo de dados) tiver duas unidades filhos (022 e 023) e não contiver dimensões, será gerado um relatório para cada filho e o pai. O total de pai é a soma dos dois valores filho.

### <a name="manage-reporting-units"></a>Gerenciar unidades de relatório

Cada relatório de definição de árvore é exibido em modos de exibição exclusivos. Há uma exibição gráfica para visualizar a hierarquia pai/filho, e uma exibição de planilha que mostra as informações específicas para cada unidade de relatório. A exibição gráfica e a exibição de planilha estão associadas. Quando você seleciona uma unidade de relatório em uma exibição, ela também é selecionada na outra exibição. Você pode criar hierarquias em várias dimensões com base nas relações dimensionais nos dados financeiros. Quando você cria uma definição de árvore de relatório, pode usar as mesmas definições de linha repetidamente, esteja gerando um demonstrativo de receita do departamento ou um resumo do demonstrativo de receita consolidada. As dimensões definidas na definição de linha podem ser combinadas com as dimensões na definição de árvore de relatório para fornecer várias visões do desempenho da organização.

### <a name="reporting-unit-structure"></a> Estrutura da unidade de relatório

Os seguintes tipos de unidades de relatório são usados no relatório financeiro:

- Uma unidade de detalhe obtém informações diretamente dos dados financeiros, de um arquivo de planilha do Excel ou de outra planilha do relatório financeiro.
- Uma unidade de resumo resume dados de unidades de nível inferior.

Uma unidade de relatório pai é uma unidade de resumo que agrega informações resumidas de uma unidade de detalhes. Uma unidade de resumo pode ser tanto uma unidade de detalhes e um resumo. Portanto, uma unidade de resumo pode desenhar informações de uma unidade de nível inferior, ou dados financeiros ou uma planilha do Excel. Uma unidade pai pode ser a unidade filho de uma unidade pai superior. Uma unidade de relatório filho pode ser uma unidade de detalhes que obtém informações diretamente dos dados financeiros ou de uma planilha Excel. Uma unidade de relatório filho também pode ser uma unidade de resumo intermediária. Em outras palavras, é a unidade primária de uma unidade de nível inferior e também a unidade filho de uma unidade de resumo de nível superior. O cenário mais comum de unidades de relatório são unidades pai com uma célula em branco na coluna **Dimensões** e unidades filho com links para combinações específicas ou de dimensão de curinga.

### <a name="organize-reporting-units"></a> Organizar unidades de relatório

Você pode reorganizar a estrutura organizacional de uma definição de hierarquia organizacional movendo as unidades organizacionais na exibição gráfica. Também é possível promover unidades de relatório para um nível superior na árvore de relatório e movê-los para um nível inferior.

1. No Designer de Relatórios, abra a definição de árvore de relatório a ser modificada.
2. Na exibição gráfica da definição de árvore de relatório, selecione uma unidade de relatório.
3. Arraste a unidade para uma nova posição. De forma alternativa, clique com o botão direito do mouse na unidade e selecione **Promover Unidade de Relatório** ou **Rebaixar Unidade de Relatório**.
4. Clique em **Arquivo** &gt; **Salvar** para salvar as alterações.

### <a name="add-text-about-a-reporting-unit"></a> Adicionar texto sobre uma unidade de relatório

Uma entrada de texto adicional é uma cadeia de texto estático, com até 255 caracteres, que adiciona informações à definição de árvore de relatório. Por exemplo, o texto adicional pode ser uma descrição de pequena empresa. Você pode criar até dez entradas de texto adicional para cada unidade de relatório em uma definição de árvore de relatório. O texto adicional aparece no relatório para a unidade de relatório à qual o texto é atribuído. Você pode adicionar entradas de texto da coluna **Descrição** da definição de linha e da guia **Cabeçalhos e Rodapés** na definição de relatório.

1. No Designer de Relatórios, abra a definição de árvore de relatório a ser modificada.
2. Clique duas vezes na célula **Texto Adicional** para a linha de unidade de relatório.
3. Na caixa de diálogo **Texto adicional**, na primeira linha em branco, insira o texto. A primeira linha que contém o texto é referenciada como UnitText1, independentemente de sua posição na caixa de diálogo **Texto Adicional**.
4. Para adicionar mais entradas de texto para essa unidade de relatório, digite o texto em uma linha em branco.
5. Clique em **OK**.

### <a name="remove-additional-text-from-a-reporting-unit"></a>Remover texto adicional de uma unidade de relatório

1. No Report Designer, abra a definição de hierarquia organizacional a ser modificada.
2. Clique duas vezes na célula **Texto adicional** para a linha de unidade organizacional.
3. Na caixa de diálogo **Texto Adicional**, selecione a entrada a ser removida e clique em **Limpar**. Como alternativa, clique com botão direito na entrada e, em seguida, selecione **Recortar**.
4. Clique em **OK**.

### <a name="restrict-access-to-a-reporting-unit"></a>Restringir o acesso a uma unidade de relatório

Você pode impedir que certos usuários e grupos acessem uma unidade de relatório. Você também pode definir restrições para que elas se apliquem aos relatórios secunDiários da unidade de geração de relatórios.

1. No Designer de Relatórios, abra a definição de árvore de relatório a ser modificada.
2. Clique duas vezes na célula **Segurança de Unidade** para a qual a linha da unidade organizacional restringe acesso.
3. Na caixa de diálogo **Segurança de Unidade**, clique em **Usuários e Grupos**.
4. Selecione os usuários ou grupos que terão acesso à unidade de relatório restrita e clique em **OK**.
5. Para restringir o acesso às unidades de relatório filho, marque a caixa de seleção **Adicionar segurança a unidades de relatório filho**.
6. Clique em **OK**.

### <a name="remove-access-to-a-reporting-unit"></a>Remover o acesso a uma unidade de relatório

1. No Designer de Relatórios, abra a definição de árvore de relatório a ser modificada.
2. Clique duas vezes na célula **Segurança de Unidade** da linha de unidade de relatório para remover o acesso.
3. Na caixa de diálogo **Segurança de Unidade**, selecione um nome e clique em **Remover**.
4. Clique em **OK**.

### <a name="link-to-reports"></a>Link para relatórios

Após criar uma coluna **relatório** na definição de linha e especificar o relatório para incluir no relatório, você deverá atualizar a árvore de relatório com a coluna vinculada e as informações sobre o relatório. Um relatório pode ser importado para qualquer unidade na árvore de relatório.

### <a name="identify-the-report-in-a-reporting-tree"></a>Identificar o relatório em uma árvore de relatório

1. No Designer de Relatórios, abra a definição de árvore de relatório a ser modificada.
2. As células na coluna **Definições de Linha** exibem informações baseadas nos dados da linha selecionada, pois a mesma definição de linha deve ser usada em todas as unidades da árvore de relatório. Clique duas vezes na célula **Definições de Linha**. Selecione a definição de linha que contém informações sobre o relatório.
3. Na célula **Link de Planilha** para uma unidade de relatório, selecione o nome do link que corresponde ao relatório.
4. Na célula **Caminho da Pasta de Trabalho ou do Relatório** para uma unidade de relatório, digite o nome do relatório ou navegue para selecionar o relatório.
5. Para especificar uma planilha em um relatório, digite o nome da planilha na célula **Nome da planilha**.
6. Repita as etapas 3 a 5 para cada unidade de relatório que deve receber dados de um relatório. Para evitar que dados incorretos apareçam no relatório, verifique se os nomes corretos de relatório aparecem na unidade correspondente da árvore de relatório.

## <a name="examples"></a>Exemplos
### <a name="reporting-unit-structure--example-1"></a>Estrutura da unidade de relatório - Exemplo 1

Aqui está a estrutura das unidades de relatório na árvore de relatórios a seguir:

- A unidade de emissão de relatórios de Contoso Japão é uma unidade pai das unidades filho de Contoso Japão vendas e consultoria da Contoso Japão.
- A unidade de divisão de Vendas Contoso Japão é uma unidade filho da unidade Contoso Japão e uma unidade pai nas unidades de Vendas Locais e de Vendas de Auto.
- As unidades de relatório de detalhe de nível inferior (Vendas locais, vendas de auto, serviços do cliente e operações) representam departamentos nos dados financeiros. Essas unidades de relatório estão na área sombreada do diagrama.
- As unidades de resumo de nível superior resumem informações das unidades de detalhes.

[![ContosoEntertainmentSummaryReportStructure](./media/contosoentertainmentsummaryreportstructure.png)](./media/contosoentertainmentsummaryreportstructure.png)

### <a name="reporting-unit-structure--example-2"></a>Estrutura da unidade de relatório - Exemplo 2

O diagrama a seguir mostra uma árvore de relatório que exibe uma estrutura organizacional que é dividida pela função de negócios.

[![summaryofallunitscontoso](./media/summaryofallunitscontoso.png)](./media/summaryofallunitscontoso.png)

### <a name="example-of-the-insert-reporting-units-from-dimensions-dialog-box"></a>Exemplo da caixa de diálogo Inserir Unidades de Relatório de Dimensões

Neste exemplo, a caixa de diálogo **Inserir Unidades de Relatório de Dimensões** contém as informações a seguir. Para este exemplo, os resultados retornarão a combinação de unidades de negócios, departamentos e centros de custo.

[![InsertReportingUnits](./media/insertreportingunits.png)](./media/insertreportingunits.png)

A definição de árvore relatório resultante é classificada por unidade de negócios, pelo Centro de custo e, em seguida, por departamento. A dimensão da quinta unidade de relatório é **Unidade de negócios = \[001\], Centro de custos =\[\], Departamento = \[022\]**, e identifica uma unidade de emissão de relatórios para contas que são específicas da unidade de negócios 001 e do departamento 022.

[![ReportingTree](./media/reportingtree-1024x646.png)](./media/reportingtree.png)

### <a name="examples-of-data-roll-up"></a>Exemplos de acúmulo de dados

Os exemplos a seguir mostram informações possíveis usadas em uma definição de árvore de relatório para um exemplo de acúmulo de dados.

#### <a name="example-1"></a>Exemplo 1

[![MutliCompanyRollUp](./media/mutlicompanyrollup.png)](./media/mutlicompanyrollup.png)

#### <a name="example-2"></a>Exemplo 2

[![CrossCompanyDepartmentRollUp](./media/crosscompanydepartmentrollup.png)](./media/crosscompanydepartmentrollup.png)

## <a name="additional-resources"></a>Recursos adicionais

[Relatórios financeiros](financial-reporting-intro.md)
