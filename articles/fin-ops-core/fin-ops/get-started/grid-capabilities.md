---
title: Recursos de grade
description: Este artigo descreve vários recursos avançados do controle de grade. É necessário habilitar o novo recurso de grade para ter acesso a esses recursos.
author: jasongre
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: a8968a1263dfafd67b07b4beb78c51493e95756e
ms.sourcegitcommit: 47534a943f87a9931066e28f5d59323776e6ac65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/11/2022
ms.locfileid: "9258937"
---
# <a name="grid-capabilities"></a>Recursos de grade

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

O novo controle de grade fornece vários recursos úteis e eficientes que você pode usar para melhorar a produtividade do usuário, construir exibições mais interessantes dos dados e obter insights significativos sobre seus dados. Este artigo abordará os seguintes recursos: 

- Mostrar valores calculados 
- Digitação à frente do sistema
- Avaliação de expressões matemáticas 
- Agrupamento dados tabulares (habilitados separadamente utilizando o recurso **Agrupamento em grades**)
- Congelamento de colunas (habilitados separadamente com o uso do recurso **Congelar colunas em grades**)
- Ajustar automaticamente a largura da coluna
- Colunas alongáveis

## <a name="showing-calculated-values"></a>Mostrar valores calculados
Em aplicativos de finanças e operações, os usuários podem exibir um valor calculado para cada coluna numérica em uma grade. Os valores calculados são mostrados em uma seção de rodapé na parte inferior da grade.

[![Mostrar valores calculados em grades](./media/grids-aggregation.png)](./media/grids-aggregation.png)

Em versões anteriores a 10.0.29, o total é o único valor calculado com suporte. No entanto, a partir da versão 10.0.29, depois de habilitar o recurso **Recursos de agregação de grade estendida**, os usuários podem selecionar entre os quatro valores calculados a seguir:

- Mínimo
- Máximo
- Total
- Médio

Uma única coluna pode mostrar somente um tipo de valor calculado. No entanto, cada coluna na grade pode ser configurada para mostrar um tipo diferente de valor calculado.

### <a name="showing-the-grid-footer"></a>Mostrando o rodapé da grade
Existe uma área de rodapé na parte inferior de cada grade tabular nos aplicativos de finanças e operações. O rodapé pode mostrar informações valiosas relacionadas aos dados que aparecem na grade. Veja alguns exemplos dessas informações:

- O número de linhas selecionadas na tabela (quando mais de um registro é selecionado)
- Valores calculados na parte inferior das colunas numéricas configuradas (por exemplo, totais gerais)
- O número de linhas no conjunto de dados 

Esse rodapé é ocultado por padrão, mas ele pode ser ativado. Para mostrar o rodapé de uma grade, selecione o botão **Opções de grade** no cabeçalho de grade e, depois, a opção **Mostrar rodapé**. Depois de ativar o rodapé de uma determinada grade, essa configuração será lembrada até que o usuário opte por ocultar o rodapé. Para ocultar o rodapé, selecione **Ocultar rodapé** no menu **Opções de grade**.

### <a name="specifying-columns-with-calculated-values"></a>Especificação de colunas com valores calculados
No momento, nenhuma coluna mostra os valores calculados por padrão. Em vez disso, a configuração é considerada uma atividade única, como ajustar as larguras das colunas nas grades. Após s especificação de que deseja ver valores calculados de uma coluna, essa configuração será lembrada na próxima vez que você visitar a página.

Há duas maneiras de configurar uma coluna para mostrar um valor calculado:

- Selecione e segure (ou clique com o botão direito do mouse) na coluna para a qual você deseja exibir um valor calculado. Se o recurso **Recursos de agregação de grade estendida** estiver habilitado, selecione **Exibir totais de coluna** e selecione o valor calculado desejado. Se esse recurso não estiver habilitado, selecione **Total desta coluna**. Essa ação causa três eventos:

    1. O rodapé da grade fica visível. 
    2. Sua preferência para exibir um valor calculado para a coluna é salva. 
    3. O cálculo desejado é iniciado para essa coluna e quaisquer outras colunas que você configurou anteriormente para ver os valores calculados. O tempo necessário para mostrar os valores calculados depende do tamanho do conjunto de dados.

- Depois que o rodapé estiver visível, selecione **Exibir total** (ou **Selecionar o valor calculado** se o recurso **Recursos de agregação de grade estendida** estiver habilitado) na área de rodapé na parte inferior da coluna para a qual você deseja exibir um valor calculado. Se não houver colunas configuradas, esse botão estará disponível no rodapé para todas as colunas numéricas.

    Depois que pelo menos uma coluna for configurada para mostrar um valor calculado, o botão **Exibir total** (ou **Selecionar valor calculado**) só estará disponível ao passar o mouse ou com a opção de focar. A ação de selecionar o botão só salva sua preferência para exibição de um valor calculado na coluna, a fim de que a preferência seja aplicada durante futuras visitas à página. No rodapé, esse estado é indicado por um traço que aparece na coluna. (Observe que o valor calculado aparecerá imediatamente se o conjunto de dados for pequeno o suficiente.)

Se cometer um erro e não quiser mais exibir um valor calculado em uma coluna específica, selecione e mantenha a seleção (ou clique com o botão direito do mouse) na coluna e selecione **Ocultar total** (ou **Exibir totais da coluna \> Nenhum** se o recurso dos **Recursos de agregação de grade estendida** estiver habilitado). Alternativamente, selecione **Ocultar total** (ou **Ocultar valor calculado**) no rodapé dessa coluna. Essa preferência também será salva para futuras visitas à página. 

### <a name="calculating-aggregate-values"></a>Cálculo de valores agregados
Quando você vai para uma página na qual o rodapé está visível e as colunas já estão configuradas para mostrar valores calculados, esses valores não podem ser mostrados no rodapé. O comportamento irá depender do tamanho do conjunto de dados na página. Se o conjunto de dados for suficientemente pequeno, os valores calculados serão mostrados automaticamente, com o número de linhas no conjunto de dados. Se houver traços no rodapé sob as colunas que você configurou, o conjunto de dados é muito grande para que o sistema mostre os valores calculados imediatamente. Nesse caso, uma ação explícita é necessária para calcular os valores. Para calcular os valores, selecione o botão **Calcular** no rodapé. Como alternativa, selecione e mantenha a seleção (ou clique com o botão direito do mouse) na coluna que deseja visualizar o total e selecione **Total da coluna** (ou **Exibir totais da coluna** e então o valor calculado desejado se o recurso **Recursos de agregação de grade estendida** estiver habilitado).

Se o cálculo demorar para ser concluído, você poderá cancelar a operação a qualquer momento selecionando o botão **Cancelar**. Às vezes, o conjunto de dados será grande demais para calcular valores agregados (um limite imposto pela sua organização). Nesse caso, você será notificado para filtrar ainda mais os dados.

> [!NOTE]
> Administradores de sistema podem modificar o limite para o número de registros disponíveis para calcular os totais agregados ajustando o parâmetro **Número máximo de registros locais para cada de grade** na página **Opções de desempenho do cliente**. O valor padrão é 25.000 registros. Os administradores devem ter cuidado ao ajustar esse valor, já que um valor muito grande pode esgotar a memória disponível na máquina do usuário. Recomendamos que o valor não exceda 50.000 registros.

Os valores calculados serão atualizados automaticamente à medida que você atualizar, excluir ou criar linhas no conjunto de dados.

## <a name="typing-ahead-of-the-system"></a>Digitação à frente do sistema
Em vários cenários comerciais, a capacidade de inserir rapidamente dados no sistema é muito importante. Antes que o novo controle de grade seja introduzido, os usuários podem alterar os dados somente na linha atual. Portanto, depois que os dados forem alterados em uma linha, os usuários não poderão alternar para uma linha diferente ou criar uma nova linha até que o sistema tenha validado com êxito as alterações na linha atual e (no caso de criação de linha) executado toda a lógica associada à criação de uma nova linha. Para ajudar a reduzir o tempo que os usuários esperam para que as operações sejam concluídas e para ajudar a otimizar a produtividade do usuário, a nova grade ajusta essas ações para que sejam assíncronas. Os usuários podem criar novas linhas ou mover para outras linhas para fazer alterações enquanto as validações de linhas anteriores e a lógica de criação da linha estão pendentes. 

[![Digitação antecipada do sistema](./media/gridFastEntry-07-25-2022.gif)](./media/gridFastEntry-07-25-2022.gif)

Para dar suporte a esse novo comportamento, uma nova coluna para o status da linha foi adicionada à direita da coluna de seleção de linha quando a grade está no modo de edição. Esta coluna indica um dos seguintes status:

- **Em branco** – Nenhuma imagem de status indica que a linha foi salva com êxito pelo sistema.
- **Processamento pendente** – Este status indica que as alterações na linha ainda não foram salvas pelo servidor, mas que estão em uma fila de alterações que devem ser processadas. Antes de executar a ação fora da grade, você deve aguardar até que todas as alterações pendentes sejam processadas. Além disso, o texto nessas linhas fica em itálico para indicar o status não salvo das linhas. 
- **Estado inválido** – esse status indica que algum aviso ou mensagem foi disparado durante o processamento da linha e pode ter impedido o sistema de salvar as alterações nessa linha. Na grade antiga, se a operação de salvamento não teve êxito, você foi forçado a voltar para a linha para corrigir o problema imediatamente. No entanto, na nova grade, você é notificado de que um problema de validação foi encontrado, mas pode decidir quando deseja corrigir os problemas na linha. Quando estiver pronto para corrigir um problema, você poderá mover o foco manualmente de volta para a linha. Alternativamente, você pode selecionar a ação **Corrigir este problema**. Esta ação move imediatamente o foco para a linha que tem o problema e permite que você faça edições dentro ou fora da grade. Observe que o processamento de linhas pendentes subsequentes é interrompido até que este aviso de validação seja resolvido. 
- **Em pausa** – Esse status indica que o processamento pelo servidor está pausado porque a validação da linha disparou uma caixa de diálogo pop-up que requer entrada do usuário. Como o usuário pode estar inserindo dados em alguma outra linha, a caixa de diálogo pop-up não é imediatamente apresentada ao usuário. Em vez disso, ele será apresentado quando o usuário optar por retomar o processamento. Esse status é acompanhado por uma notificação que informa o usuário sobre a situação. A notificação inclui uma ação **Retomar o processamento** que irá disparar a caixa de diálogo pop-up.

### <a name="differences-when-entering-data-ahead-of-the-system"></a>Diferenças ao inserir dados antes do sistema
Ao inserir dados antes do local em que o sistema está processando, você pode esperar algumas alterações na experiência de entrada de dados:

- Você notará que não há listas suspensas de pesquisa, os valores de campo não serão validados depois que você mover para uma coluna diferente na mesma linha, e as colunas não mostrarão inicialmente os valores padrão. Esse comportamento ocorre quando você cria ou atualiza uma opção antes do sistema. No entanto, depois que o sistema se atualizar reconhecendo o local em que você está editando, a experiência padrão será retomada. Se você tiver feito alterações em um campo que geralmente recebe um valor padrão, as alterações substituirão o valor do campo padrão quando o servidor começar a processar a linha.
- Se você criar uma nova linha usando a tecla **Seta para baixo**, todas as colunas na grade aparecerão como editáveis. Por padrão, o foco será colocado na primeira coluna da nova linha. Essa coluna pode não ser a mesma coluna que recebeu o foco inicial na grade herdada ou a mesma coluna que recebe o foco depois que você seleciona um **Novo** botão. Sua organização pode personalizar o sistema e alterar a coluna que receberá o foco inicial quando a tecla **Seta para baixo** estiver selecionada. Para obter mais informações, consulte a seção [Especificação da coluna que receberá o foco inicial quando novas linhas forem criadas usando a tecla](#developer-specifying-the-column-that-receives-the-initial-focus-when-new-rows-are-created-by-using-the-down-arrow-key) Seta para baixo. Independentemente disso, você pode usar a personalização para otimizar cada grade para entrada de dados. Especificamente, você pode reordenar os campos para que a primeira coluna seja a coluna na qual você deseja começar a inserir dados. Você também pode desejar reordenar os campos em geral para entrada de dados, a fim de reduzir as interrupções de tabulação e ocultar os campos que não são necessários para entrada de dados neste modo de exibição específico.

### <a name="pasting-from-excel"></a>Colando a partir do Excel
Os usuários sempre foram capazes de exportar dados de grades em aplicativos de finanças e operações para o Microsoft Excel usando o mecanismo **Exportar para Excel**. No entanto, a capacidade de inserir dados antes do sistema permite que a nova grade dê suporte à cópia de tabelas do Excel e colando-as diretamente em grades em aplicativos de finanças e operações. A célula de grade na qual a operação de colagem é iniciada determina onde a tabela copiada começa a ser colada. O conteúdo da grade é substituído pelo conteúdo da tabela copiada, exceto em dois casos:

- Se o número de colunas na tabela copiada exceder o número de colunas que permanecem na grade, iniciando a partir do local de colagem, o usuário será notificado de que as colunas extras foram ignoradas. 
- Se o número de linhas na tabela copiada exceder o número de linhas na grade, a partir do local de colagem, as células existentes serão sobrescritas pelo conteúdo colado e todas as linhas extras da tabela copiadas serão inseridas como novas linhas na parte inferior da grade. 

## <a name="evaluating-math-expressions"></a>Avaliação de expressões matemáticas
Como um acelerador de produtividade, os usuários podem inserir fórmulas matemáticas em células numéricas em uma grade. Eles não precisam fazer o cálculo em um aplicativo fora do sistema. Por exemplo, se você digitar **=15\*4** e pressionar a tecla **Tab** para sair do campo, o sistema avaliará a expressão e salvará um valor de **60** para o campo.

[![Avaliação de expressões matemáticas.](./media/gridMathExpression-07-25-2022.gif)](./media/gridMathExpression-07-25-2022.gif)

Para que o sistema reconheça um valor como uma expressão, inicie o valor com um sinal de igualdade (**=**). Para obter mais informações sobre os operadores e a sintaxe permitidos, consulte [Símbolos matemáticos permitidos](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).

A partir da versão 10.0.29, a capacidade de avaliar expressões matemáticas em controles numéricos foi estendida e agora está disponível fora da grade também.

## <a name="grouping-tabular-data"></a>Agrupando de dados tabulares
Geralmente, os usuários de negócios precisam executar análises ad hoc de dados. Embora essa análise possa ser feita por meio da exportação de dados para o Microsoft Excel e usando tabelas dinâmicas, o recurso **Agrupamento em grandes**, que depende do novo recurso de controle de grade, permite que usuários organizem dados tabulares de forma interessante em aplicativos de finanças e operações. Como esse recurso estende o recurso **Valores calculados**, o **Agrupamento** permite obter insights significativos sobre os dados fornecendo valores calculados (por exemplo, subtotais) no nível de grupo.

[![Agrupamento de dados em uma grade.](./media/grids-groupingWithTotals.png)](./media/grids-groupingWithTotals.png)

Para usar esse recurso, clique com o botão direito do mouse na coluna a ser agrupada e selecione **Agrupar por esta coluna**. Essa ação classificará os dados pela coluna selecionada, adicionará nova coluna **Agrupar por** ao início da grade e inserirá "linhas de cabeçalho" no início de cada grupo. Essas linhas de cabeçalho fornecem as seguintes informações sobre cada grupo:

- Valor de dados para o grupo 
- Nome da coluna (essas informações são especialmente úteis quando você tem vários níveis de agrupamento)
- Número de linhas de dados neste grupo
- Valores calculados para qualquer coluna configurada (por exemplo, subtotais se a coluna estiver configurada para mostrar um total)

Com a opção [Exibições salvas](saved-views.md) habilitada, você pode salvar o agrupamento como parte de uma exibição em páginas que permitem que as consultas sejam salvas nas exibições. Por exemplo, aquelas com seletores de exibição grandes. Consulte a seção [Alternância entre as exibições](saved-views.md#switching-between-views) para obter mais detalhes. 

### <a name="multiple-levels-of-grouping"></a>Vários níveis de agrupamento
Depois de agrupar os dados por uma única coluna, você poderá agrupar os dados por uma coluna diferente selecionando **Agrupar por esta coluna** na coluna desejada. Esse processo pode ser repetido até que você tenha cinco níveis aninhados de agrupamento, que é a profundidade máxima compatível. Neste ponto, você não poderá mais agrupar por colunas adicionais.

A qualquer momento, você poderá remover o agrupamento em qualquer coluna clicando com o botão direito do mouse nessa coluna e selecionando **Desagrupar**. Você também pode remover o agrupamento de todas as colunas selecionando **Opções de grade** e **Desagrupar tudo**.

### <a name="sorting-grouped-data"></a>Classificação de dados agrupados
Depois de agrupar os dados por uma ou mais colunas, você pode alterar a direção da classificação de qualquer coluna de agrupamento por meio do cabeçalho de coluna correspondente. 

Se você classificar em uma coluna não agrupada, o agrupamento permanecerá intacto. Os dados são classificados dentro de cada grupo, com base na coluna selecionada.

### <a name="expanding-and-collapsing-groups"></a>Como expandir e recolher grupos
O agrupamento inicial de dados terá todos os grupos expandidos. Você pode criar exibições resumidas dos dados recolhendo grupos individuais ou pode usar a expansão e o recolhimento de grupos para auxiliar na navegação pelos dados. Para expandir ou recolher um grupo, selecione o botão de divisa (>) na linha de cabeçalho de grupo correspondente. Observe que o estado de expandir/recolher de grupos individuais **não** é salvo na personalização.

### <a name="selecting-and-unselecting-rows-at-the-group-level"></a>Seleção e cancelamento de seleção de linhas em nível de grupo
Da mesma forma que você pode selecionar (ou cancelar) todas as linhas na grade, marcando a caixa de seleção na parte superior da primeira coluna na grade, você também pode selecionar rapidamente (ou cancelar a seleção) todas as linhas de um grupo marcando a caixa de seleção na linha de cabeçalho de grupo correspondente. A caixa de seleção na linha de cabeçalho de grupo sempre refletirá o estado de seleção atual das linhas desse grupo, independentemente da seleção: todas as linhas, nenhuma linha apenas algumas linhas.

### <a name="hiding-column-names"></a>Ocultar nomes de coluna
Ao agrupar dados, o comportamento padrão é mostrar o nome da coluna na linha de cabeçalho do grupo. Você pode optar por suprimir o nome da coluna em linhas do cabeçalho de grupo, selecionando **Opções de grade** > **Ocultar nome da coluna do grupo**.

### <a name="grouping-on-date-and-time-columns"></a>Agrupamento em colunas de data e hora
Ao agrupar os campos "Datas" ou "Data/Hora", você tem a opção de agrupá-los por ano, mês ou dia. O grupo "valor", na linha de cabeçalho correspondente, corresponderá ao formato desse campo. Além disso, para os campos DateTime e Hora, você poderá agrupar por hora, minuto ou segundo.

> [!IMPORTANT]
> Os usuários não podem adicionar uma coluna de agrupamento no momento depois de agrupá-las em um segmento de uma coluna de data ou hora.

## <a name="freezing-columns"></a>Congelar colunas
Algumas colunas em uma grade podem ser tão importantes para o contexto que você não quer que elas saiam de vista conforme a rolagem. Em vez disso, talvez você deseje que os valores dessas colunas fiquem sempre visíveis. O recurso **Congelar colunas na grade** oferece essa flexibilidade aos usuários. 

[![Colunas de congelamento em uma grade](./media/gridFreezingColumns-07-25-2022.gif)](./media/gridFreezingColumns-07-25-2022.gif)

Para congelar uma coluna, clique com o botão direito do mouse no cabeçalho da coluna e selecione **Congelar coluna**. Na primeira vez que você concluir esta etapa, a coluna selecionada se tornará a primeira coluna e não sairá mais de vista. Qualquer coluna subsequente que você congelar será adicionada à direita da última coluna congelada. Você pode usar a funcionalidade de movimentação padrão para reordenar colunas congeladas conforme necessário. No entanto, as colunas congeladas não podem ser movidas de forma que apareçam entre o conjunto de colunas descongeladas. Além disso, as colunas congeladas não podem ser movidas de forma que apareçam entre o conjunto de colunas congeladas.

Para descongelar uma coluna, clique com o botão direito do mouse no cabeçalho da coluna congelada e selecione **Descongelar coluna**. 

Observe que a seleção de linha e as colunas de status de linha e status na nova grade ficam sempre congeladas como as duas primeiras colunas. Portanto, quando essas colunas são incluídas em uma grade, elas sempre estarão visíveis para os usuários, independentemente da posição de rolagem horizontal na grade. Essas duas colunas não podem ser reordenadas.

## <a name="autofit-column-width"></a>Ajustar automaticamente a largura da coluna
Como no Excel, os usuários podem forçar o redimensionamento automático de uma coluna com base no conteúdo exibido atualmente nessa coluna. Basta dar um toque duplo (ou clicar duas vezes) nas alças de dimensionamento da coluna. Como alternativa, coloque o foco no cabeçalho da coluna e selecione a chave **A** (para autoajuste).

## <a name="frequently-asked-questions"></a>Perguntas frequentes
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>Como habilitar o novo controle de grade no meu ambiente? 

O recurso **Novo controle de grade** está disponível diretamente em Gerenciamento de recursos em qualquer ambiente. Após habilitar o recurso no gerenciamento de recursos, todas as sessões de usuário subsequentes usarão o novo controle de grade. 

Esse recurso começou a ser habilitado por padrão na versão 10.0.21. Ele deve se tornar obrigatório em outubro de 2022.

## <a name="developer-opting-out-individual-pages-from-using-the-new-grid"></a>[Desenvolvedor] Impedir que páginas individuais use a nova grade 
Se a sua organização descobre uma página que tem algumas questões usando a nova grade, uma API está disponível para permitir que um formulário individual use o controle de grade herdado enquanto ainda permite que o restante do sistema utilize o novo controle de grade. Para recusar uma página individual da nova grade, adicione a seguinte postagem de chamada `super()` no método do formulário `run()`.

```this.forceLegacyGrid();```

Essa API será eventualmente preterida para permitir a remoção do controle da grade herdada. No entanto, ela permanecerá disponível por pelo menos 12 meses depois que a substituição for anunciada. Se algum problema exigir o uso dessa API, informe-o à Microsoft.

### <a name="forcing-a-page-to-use-the-new-grid-after-previously-opting-out-the-grid"></a>Forçar uma página a usar a nova grade depois de ter recusado anteriormente a grade
Se você tiver recusado o uso da nova grade em uma página individual, convém reabilitar posteriormente a nova grade após os problemas subjacentes terem sido resolvidos. Para isso, você só precisa remover a chamada para `forceLegacyGrid()`. A alteração não terá efeito até que uma das seguintes ações ocorra:

- **Reimplantação do ambiente**: quando um ambiente é atualizado e reimplantado, a tabela que armazena as páginas que recusaram a nova grade (FormControlReactGridState) é automaticamente limpa.
- **Limpeza manual da tabela**: para cenários de desenvolvimento, será necessário usar SQL para limpar a tabela FormControlReactGridState e reiniciar o AOS. Essa combinação de ações redefinirá o armazenamento em cache de páginas que recusaram a nova grade.

## <a name="developer-opting-individual-grids-out-of-the-typing-ahead-of-the-system-capability"></a>[Desenvolvedor] Optar por grades individuais fora da digitação antes do recurso da capacidade
Alguns cenários surgiram que não são propícios a um funcionamento com a capacidade de *Digitação antes do recurso do sistema* da grade. (Por exemplo, um código disparado quando uma linha é validada faz com que uma pesquisa de fonte de dados seja disparada e, em seguida, a pesquisa pode corromper edições não confirmadas em linhas existentes.) Se a sua organização descobre tal cenário, há uma API disponível que permite que um desenvolvedor opte por uma grade individual fora da validação de linha assíncrona e reverta para o comportamento herdado.

Quando a validação de linha assíncrona está desabilitada em uma grade, os usuários não podem criar uma nova linha ou mover para uma linha existente diferente na grade enquanto houver problemas de validação na linha atual. Como um efeito colateral dessa ação, as tabelas não podem ser coladas do Excel em grades do aplicativo de finanças e operações.

Para optar por uma grade individual fora da validação da linha assíncrona, adicionar a seguinte chamada após `super()` no método do formulário `run()`.

```<gridControl>.allowPreemptiveClient(false);```

> [!NOTE]
> - Essa chamada deve ser invocada somente em casos excepcionais e não deve ser a norma para todas as grades.
> - Não é recomendável que você alterne essa API no runtime depois que o formulário for carregado.

## <a name="developer-size-to-available-width-columns"></a>[Desenvolvedor] Colunas de tamanho para largura disponível
Se um desenvolvedor definir a propriedade **WidthMode** como **SizeToAvailable** para colunas dentro da nova grade, essas colunas terão inicialmente a mesma largura que teriam se a propriedade fosse definida como **SizeToContent**. No entanto, elas se estendem para usar qualquer largura extra disponível dentro da grade. Se a propriedade for definida como **SizeToAvailable** para várias colunas, todas essas colunas compartilham qualquer largura extra disponível dentro da grade. No entanto, se um usuário redimensionar manualmente uma dessas colunas, a coluna se torna estática. Ele permanecerá nessa largura e não será mais esticado para ocupar a largura de grade disponível extra.

## <a name="developer-specifying-the-column-that-receives-the-initial-focus-when-new-rows-are-created-by-using-the-down-arrow-key"></a>[Desenvolvedor] Especificação da coluna que receberá o foco inicial quando novas linhas forem criadas usando a tecla "Seta para baixo"
Como foi discutido na seção [Diferenças ao inserir dados antes do sistema](#differences-when-entering-data-ahead-of-the-system), se o recurso "Digitação antecipada do sistema" estiver habilitado e um usuário criar uma nova linha usando a tecla **Seta para baixo**, o comportamento padrão é colocar o foco na primeira coluna da nova linha. Essa experiência pode diferir da experiência na grade herdada ou quando um **Novo** botão é selecionado.

Os usuários e as organizações podem criar exibições salvas que são otimizadas para entrada de dados. (Por exemplo, você pode reordenar colunas para que a primeira coluna seja aquela na qual você deseja começar a inserir dados.) Além disso, a partir da versão 10.0.29, as organizações podem ajustar esse comportamento usando o método **selectedControlOnCreate()**. Este método leva um desenvolvedor a especificar a coluna que deverá receber o foco inicial quando novas linhas forem criadas usando a tecla **Seta para baixo**. Como entrada, essa API assume a ID de controle que corresponde à coluna que deve receber o foco inicial.

## <a name="known-issues"></a>Problemas conhecidos
Esta seção mantém uma lista de problemas conhecidos para o novo controle de grade.

### <a name="open-issues"></a>Questões em aberto
- Depois de habilitar o recurso **Novo controle de grade**, algumas páginas continuarão a usar o controle de grade existente. Isso acontecerá nas seguintes situações:
 
    - Há uma lista de cartões na página que é renderizada em várias colunas.
    - Existe uma lista de placas agrupadas na página.
    - Uma coluna de grade com um controle extensível sem reação.

    Quando um usuário encontra primeiro uma dessas situações, uma mensagem será exibida sobre a atualização da página. Depois que esta mensagem for exibida, a página continuará a utilizar a grade existente para todos os usuários até a próxima atualização da versão do produto. Uma melhor manipulação desses cenários, de forma que a nova grade possa ser utilizada, será considerada para uma atualização futura.

- [KB 4582758] Os registros ficam borrados quando você altera o zoom de 100 para qualquer outro percentual

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

