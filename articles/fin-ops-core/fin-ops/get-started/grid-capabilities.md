---
title: Recursos de grade
description: Este tópico descreve vários recursos avançados do controle de grade. É necessário habilitar o novo recurso de grade para ter acesso a esses recursos.
author: jasongre
ms.date: 12/01/2021
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
ms.openlocfilehash: 37484ce022085dfac66edba31b7adf9af4095df8
ms.sourcegitcommit: bbe8ab054ad7cc00a63c63e02dc90bfa8ede15bb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2022
ms.locfileid: "7974372"
---
# <a name="grid-capabilities"></a>Recursos de grade

[!include [banner](../includes/banner.md)]

O novo controle de grade fornece vários recursos úteis e eficientes que você pode usar para melhorar a produtividade do usuário, construir exibições mais interessantes dos dados e obter insights significativos sobre seus dados. Este artigo abordará os seguintes recursos: 

-  Calculando totais
-  Digitação à frente do sistema
-  Avaliação de expressões matemáticas 
-  Agrupar dados tabulares (habilitados separadamente com o recurso **Agrupamento em grades**)
-  Congelar colunas
-  Ajustar automaticamente a largura da coluna
-  Colunas alongáveis

## <a name="calculating-totals"></a>Calculando totais
Nos aplicativos de finanças e operações, os usuários podem ver os totais na parte inferior das colunas numéricas em grades. Esses totais são mostrados em uma seção de rodapé na parte inferior da grade. 

### <a name="showing-the-grid-footer"></a>Mostrando o rodapé da grade
Existe uma área de rodapé na parte inferior de cada grade tabular nos aplicativos de finanças e operações. O rodapé pode mostrar informações valiosas relacionadas aos dados que aparecem na grade. Veja alguns exemplos dessas informações:

- O número de linhas selecionadas na tabela (quando mais de um registro é selecionado)
- Totais gerais na parte inferior das colunas numéricas configuradas
- O número de linhas no conjunto de dados 

Esse rodapé é ocultado por padrão, mas pode ser ativado. Para mostrar o rodapé de uma grade, selecione o botão **Opções de grade** no cabeçalho de grade e, depois, a opção **Mostrar rodapé**. Depois de ativar o rodapé de uma determinada grade, essa configuração será lembrada até que o usuário opte por ocultar o rodapé. Para ocultar o rodapé, selecione **Ocultar rodapé** no menu **Opções de grade**.  

### <a name="specifying-columns-with-totals"></a>Especificando colunas com totais
No momento, nenhuma coluna mostra os totais por padrão. Pelo contrário, essa atividade é considerada de configuração única, semelhante ao ajuste das larguras das colunas em grades. Após especificação de que deseja ver os totais de uma coluna, essa configuração será lembrada na próxima vez que você visitar a página.  

Há duas maneiras de configurar uma coluna para mostrar um total: 

- Clique com o botão direito do mouse na coluna da qual você deseja ver um total e selecione **Totalizar esta coluna**. Essa ação causa três eventos:

    1. O rodapé fica visível. 
    2. Sua preferência para ver um total dessa coluna é salva. 
    3. Um cálculo de totais é iniciado para essa coluna e quaisquer outras colunas que você configurou anteriormente para ver totais. O tempo necessário para mostrar um total depende do tamanho do conjunto de dados que você está totalizando.

- Depois que o rodapé estiver visível, selecione **Mostrar total** na área do rodapé na parte inferior da coluna da qual você deseja ver um total. Se não houver colunas configuradas, o botão **Mostrar total** estará disponível para todas as colunas numéricas. 

    Depois que houver pelo menos uma coluna configurada para totais, os botões **Mostrar total** só ficarão disponíveis com a passagem do mouse ou na focalização. A ação de selecionar **Mostrar total** só salva sua preferência para ver um total nesta coluna, a fim de que a preferência seja aplicada durante futuras visitas à página. No rodapé, esse estado é indicado por um traço que aparece na coluna. (Como alternativa, se o conjunto de dados for pequeno o suficiente, um total será mostrado imediatamente.)

Se você cometer um erro e não quiser mais ver um total em uma determinada coluna, clique com o botão direito do mouse na coluna e selecione **Ocultar total** ou selecione o botão **Ocultar total** no rodapé dessa coluna. Essa preferência também será salva para futuras visitas à página. 

### <a name="calculating-totals"></a>Calculando totais
Quando você acessa uma página com o rodapé visível e as colunas já configuradas para totais, os totais podem ou não ser mostrados no rodapé. O comportamento depende do tamanho do conjunto de dados na página. Se o conjunto de dados for suficientemente pequeno, os totais serão mostrados automaticamente, com o número de linhas no conjunto de dados. Se houver traços no rodapé sob as colunas que você configurou para os totais, significa que o conjunto de dados é muito grande para que o sistema mostre os totais imediatamente e uma ação explícita é necessária para calcular os totais. Para isso, clique no botão **Calcular**, no rodapé, ou clique com o botão direito do mouse em uma coluna para a qual deseja o total e selecione **Totalizar esta coluna**.  

Se o cálculo estiver demorando muito, você poderá cancelar a operação selecionando o botão **Cancelar**. Às vezes, no entanto, o conjunto de dados será grande demais para calcular os totais (um limite imposto pela sua organização) e você será notificado para filtrar mais os dados.

Os totais serão atualizados automaticamente à medida que você atualizar, excluir ou criar linhas no conjunto de dados.  

## <a name="typing-ahead-of-the-system"></a>Digitação à frente do sistema
Em vários cenários comerciais, a capacidade de inserir rapidamente dados no sistema é muito importante. Antes que o novo controle de grade tenha sido introduzido, os usuários podem alterar os dados somente na linha atual. Antes de criar uma nova linha ou alternar para uma linha diferente, eles foram forçados a esperar o sistema validar com êxito as alterações. Para reduzir o tempo durante o qual os usuários esperam que as validações sejam concluídas e para melhorar a produtividade do usuário, a nova grade ajusta essas validações para que sejam assíncronas. Portanto, o usuário pode ir para outras linhas para fazer alterações enquanto as validações de linhas anteriores estão pendentes. 

Para dar suporte a esse novo comportamento, uma nova coluna para o status da linha foi adicionada à direita da coluna de seleção de linha quando a grade está no modo de edição. Esta coluna indica um dos seguintes status:

- **Em branco** – Nenhuma imagem de status indica que a linha foi salva com êxito pelo sistema.
- **Processamento pendente** – Este status indica que as alterações na linha ainda não foram salvas pelo servidor, mas que estão em uma fila de alterações que devem ser processadas. Antes de executar a ação fora da grade, você deve aguardar até que todas as alterações pendentes sejam processadas. Além disso, o texto nessas linhas fica em itálico para indicar o status não salvo das linhas. 
- **Estado inválido** – esse status indica que algum aviso ou mensagem foi disparado durante o processamento da linha e pode ter impedido o sistema de salvar as alterações nessa linha. Na grade antiga, se a operação de salvamento não teve êxito, você foi forçado a voltar para a linha para corrigir o problema imediatamente. No entanto, na nova grade, você é notificado de que um problema de validação foi encontrado, mas pode decidir quando deseja corrigir os problemas na linha. Quando estiver pronto para corrigir um problema, você poderá mover o foco manualmente de volta para a linha. Alternativamente, você pode selecionar a ação **Corrigir este problema**. Esta ação move imediatamente o foco para a linha que tem o problema e permite que você faça edições dentro ou fora da grade. Observe que o processamento de linhas pendentes subsequentes é interrompido até que este aviso de validação seja resolvido. 
- **Em pausa** – Esse status indica que o processamento pelo servidor está pausado porque a validação da linha disparou uma caixa de diálogo pop-up que requer entrada do usuário. Como o usuário pode estar inserindo dados em alguma outra linha, a caixa de diálogo pop-up não é imediatamente apresentada ao usuário. Em vez disso, ele será apresentado quando o usuário optar por retomar o processamento. Esse status é acompanhado por uma notificação que informa o usuário sobre a situação. A notificação inclui uma ação **Retomar o processamento** que irá disparar a caixa de diálogo pop-up.  
    
Quando os usuários inserem dados antes do local em que o servidor está processando, eles podem esperar algumas degradações na experiência de entrada de dados, como a falta de pesquisas, a validação no nível de controle e a entrada de valores padrão. Recomenda-se que os usuários que precisam de uma lista suspensa para localizar um valor aguardem até que o servidor volte para a linha atual. A validação do nível de controle e a entrada de valores padrão também ocorrerão quando o servidor processar essa linha.   

### <a name="pasting-from-excel"></a>Colando a partir do Excel
Os usuários sempre foram capazes de exportar dados de grades em aplicativos de finanças e operações para o Microsoft Excel usando o mecanismo **Exportação para o Excel**. No entanto, a capacidade de inserir dados antes do sistema permite que a nova grade dê suporte à cópia de tabelas do Excel e colando-as diretamente em grades em aplicativos de finanças e operações. A célula de grade na qual a operação de colagem é iniciada determina onde a tabela copiada começa a ser colada. O conteúdo da grade é substituído pelo conteúdo da tabela copiada, exceto em dois casos:

- Se o número de colunas na tabela copiada exceder o número de colunas que permanecem na grade, iniciando a partir do local de colagem, o usuário será notificado de que as colunas extras foram ignoradas. 
- Se o número de linhas na tabela copiada exceder o número de linhas na grade, a partir do local de colagem, as células existentes serão sobrescritas pelo conteúdo colado e todas as linhas extras da tabela copiadas serão inseridas como novas linhas na parte inferior da grade. 

## <a name="evaluating-math-expressions"></a>Avaliação de expressões matemáticas
Como um acelerador de produtividade, os usuários podem inserir fórmulas matemáticas em células numéricas em uma grade. Eles não precisam fazer o cálculo em um aplicativo fora do sistema. Por exemplo, se você digitar **=15\*4** e pressionar a tecla **Tab** para sair do campo, o sistema avaliará a expressão e salvará um valor de **60** para o campo.

Para que o sistema reconheça um valor como uma expressão, inicie o valor com um sinal de igualdade (**=**). Para obter mais informações sobre os operadores e a sintaxe permitidos, consulte [Símbolos matemáticos permitidos](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).

## <a name="grouping-tabular-data"></a>Agrupando de dados tabulares
Geralmente, os usuários corporativos precisam executar análises ad hoc de dados. Embora isso possa ser feito por meio da exportação de dados do Microsoft Excel e usando tabelas dinâmicas, o recurso **Agrupamento em grandes**, que depende do novo recurso de controle de grade, permite que usuários organizem dados tabulares de forma interessante em aplicativos de finanças e operações. Como esse recurso estende o recurso **Totais**, o **Agrupamento** permite obter insights significativos sobre os dados fornecendo subtotais no nível de grupo.

Para usar esse recurso, clique com o botão direito do mouse na coluna a ser agrupada e selecione **Agrupar por esta coluna**. Essa ação classificará os dados pela coluna selecionada, adicionará nova coluna **Agrupar por** ao início da grade e inserirá "linhas de cabeçalho" no início de cada grupo. Essas linhas de cabeçalho fornecem as seguintes informações sobre cada grupo: 
-  Valor de dados para o grupo 
-  Nome da coluna (essas informações são especialmente úteis quando você tem vários níveis de agrupamento)  
-  Número de linhas de dados neste grupo
-  Subtotais de qualquer coluna configurada para mostrar totais

Com [Exibições salvas](saved-views.md) habilitadas, esse agrupamento pode ser salvo por personalização como parte de uma exibição para acesso rápido na próxima vez que você visitar a página.  

### <a name="multiple-levels-of-grouping"></a>Vários níveis de agrupamento
Depois de agrupar os dados por uma única coluna, você poderá agrupar os dados por uma coluna diferente selecionando **Agrupar por esta coluna** na coluna desejada. Esse processo pode ser repetido até que você tenha cinco níveis aninhados de agrupamento, que é a profundidade máxima compatível. Neste ponto, você não poderá mais agrupar por colunas adicionais.  

A qualquer momento, você poderá remover o agrupamento em qualquer coluna clicando com o botão direito do mouse nessa coluna e selecionando **Desagrupar**. Você também pode remover o agrupamento de todas as colunas selecionando **Opções de grade** e **Desagrupar tudo**.   

### <a name="expanding-and-collapsing-groups"></a>Como expandir e recolher grupos
O agrupamento inicial de dados terá todos os grupos expandidos. Você pode criar exibições resumidas dos dados recolhendo grupos individuais ou pode usar a expansão e o recolhimento de grupos para auxiliar na navegação pelos dados. Para expandir ou recolher um grupo, selecione o botão de divisa (>) na linha de cabeçalho de grupo correspondente. Observe que o estado de expandir/recolher de grupos individuais **não** é salvo na personalização.

### <a name="selecting-and-unselecting-rows-at-the-group-level"></a>Seleção e cancelamento de seleção de linhas em nível de grupo
Da mesma forma que você pode selecionar (ou cancelar) todas as linhas na grade, marcando a caixa de seleção na parte superior da primeira coluna na grade, você também pode selecionar rapidamente (ou cancelar a seleção) todas as linhas de um grupo marcando a caixa de seleção na linha de cabeçalho de grupo correspondente. A caixa de seleção na linha de cabeçalho de grupo sempre refletirá o estado de seleção atual das linhas desse grupo, independentemente da seleção: todas as linhas, nenhuma linha apenas algumas linhas.

### <a name="hiding-column-names"></a>Ocultar nomes de coluna
Ao agrupar dados, o comportamento padrão é mostrar o nome da coluna na linha de cabeçalho do grupo. Você pode optar por suprimir o nome da coluna em linhas do cabeçalho de grupo, selecionando **Opções de grade** > **Ocultar nome da coluna do grupo**.

### <a name="grouping-on-date-and-time-columns"></a>Agrupamento em colunas de data e hora
A partir da versão 10.0.24, para os campos Data ou DateTime, a opção foi adicionada para agrupar por Ano, Mês ou Dia. O grupo "valor", na linha de cabeçalho correspondente, corresponderá ao formato desse campo. Além disso, para os campos DateTime e Hora, você poderá agrupar por Hora, Minuto ou Segundo.    

## <a name="freezing-columns"></a>Congelar colunas
Algumas colunas em uma grade podem ser tão importantes para o contexto que você não quer que elas saiam de vista conforme a rolagem. Mas, talvez deseje que os valores dessas colunas fiquem sempre visíveis. O recurso **Congelar colunas na grade** oferece essa flexibilidade aos usuários. 

Para congelar uma coluna, clique com o botão direito do mouse no cabeçalho da coluna e selecione **Congelar coluna**. Na primeira vez que você concluir esta etapa, a coluna selecionada se tornará a primeira coluna e não sairá mais de vista. Qualquer coluna subsequente que você congelar será adicionada à direita da última coluna congelada. Você pode usar a funcionalidade de movimentação padrão para reordenar colunas congeladas conforme necessário. No entanto, as colunas congeladas não podem ser movidas de forma que apareçam entre o conjunto de colunas descongeladas. Além disso, as colunas congeladas não podem ser movidas de forma que apareçam entre o conjunto de colunas congeladas.

Para descongelar uma coluna, clique com o botão direito do mouse no cabeçalho da coluna congelada e selecione **Descongelar coluna**. 

Observe que a seleção de linha e as colunas de status de linha e status na nova grade ficam sempre congeladas como as duas primeiras colunas. Portanto, quando essas colunas são incluídas em uma grade, elas sempre estarão visíveis para os usuários, independentemente da posição de rolagem horizontal na grade. Essas duas colunas não podem ser reordenadas.

## <a name="autofit-column-width"></a>Ajustar automaticamente a largura da coluna
Como no Excel, os usuários podem forçar o redimensionamento automático de uma coluna com base no conteúdo mostrado atualmente nessa coluna. Para isso, clique duas vezes nas alças de dimensionamento na coluna ou focalize o cabeçalho da coluna e pressione **A** (para ajuste automático). Esse recurso está disponível a partir da versão 10.0.23.  

## <a name="frequently-asked-questions"></a>Perguntas frequentes
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>Como habilitar o novo controle de grade no meu ambiente? 

O recurso **Novo controle de grade** está disponível diretamente em Gerenciamento de recursos em qualquer ambiente. Após habilitar o recurso no gerenciamento de recursos, todas as sessões de usuário subsequentes usarão o novo controle de grade. 

Esse recurso é habilitado por padrão a partir da versão 10.0.21 e deve ser obrigatório na versão 10.0.25. 

## <a name="developer-opting-out-individual-pages-from-using-the-new-grid"></a>[Desenvolvedor] Impedir que páginas individuais use a nova grade 
Se a sua organização descobre uma página que tem algumas questões usando a nova grade, uma API está disponível para permitir que um formulário individual use o controle de grade herdado enquanto ainda permite que o restante do sistema utilize o novo controle de grade. Para recusar uma página individual da nova grade, adicione a seguinte postagem de chamada `super()` no método do formulário `run()`.

 ```this.forceLegacyGrid();```

Esta API será respeitada até que o novo controle de grade se torne obrigatório, previsto para abril de 2022. Se algum problema exigir o uso dessa API, informe-o à Microsoft.

### <a name="forcing-a-page-to-use-the-new-grid-after-previously-opting-out-the-grid"></a>Forçar uma página a usar a nova grade depois de ter recusado anteriormente a grade
Se você tiver recusado o uso da nova grade em uma página individual, convém reabilitar posteriormente a nova grade após os problemas subjacentes terem sido resolvidos. Para isso, você só precisa remover a chamada para `forceLegacyGrid()`. A alteração não terá efeito até que uma das seguintes ações ocorra:

- **Reimplantação do ambiente**: quando um ambiente é atualizado e reimplantado, a tabela que armazena as páginas que recusaram a nova grade (FormControlReactGridState) é automaticamente limpa.

- **Limpeza manual da tabela**: para cenários de desenvolvimento, será necessário usar SQL para limpar a tabela FormControlReactGridState e reiniciar o AOS. Essa combinação de ações redefinirá o armazenamento em cache de páginas que recusaram a nova grade.  

## <a name="developer-size-to-available-width-columns"></a>[Desenvolvedor] Colunas de tamanho para largura disponível
Se um desenvolvedor definir a propriedade **WidthMode** como **SizeToAvailable** para colunas dentro da nova grade, essas colunas terão inicialmente a mesma largura que teriam se a propriedade fosse definida como **SizeToContent**. No entanto, elas se estendem para usar qualquer largura extra disponível dentro da grade. Se a propriedade for definida como **SizeToAvailable** para várias colunas, todas essas colunas compartilham qualquer largura extra disponível dentro da grade. No entanto, se um usuário redimensionar manualmente uma dessas colunas, a coluna se torna estática. Ele permanecerá nessa largura e não será mais esticado para ocupar a largura de grade disponível extra.  

## <a name="known-issues"></a>Problemas conhecidos
Esta seção mantém uma lista de problemas conhecidos para o novo controle de grade.  

### <a name="open-issues"></a>Questões em aberto
-  Depois de habilitar o recurso **Novo controle de grade**, algumas páginas continuarão a usar o controle de grade existente. Isso acontecerá nas seguintes situações:  
    -  Há uma lista de cartões na página que é renderizada em várias colunas.
    -  Existe uma lista de placas agrupadas na página.
    -  Uma coluna de grade com um controle extensível sem reação.

    Quando um usuário encontra primeiro uma dessas situações, uma mensagem será exibida sobre a atualização da página. Depois que esta mensagem for exibida, a página continuará a utilizar a grade existente para todos os usuários até a próxima atualização da versão do produto. Uma melhor manipulação desses cenários, de forma que a nova grade possa ser utilizada, será considerada para uma atualização futura.    
    
-  [KB 4582758] Os registros ficam borrados quando você altera o zoom de 100 para qualquer outro percentual
-  [KB 4592012] Erro de cliente inesperado no IE11 ao colar várias linhas do Excel
    -  A Microsoft não está buscando uma solução para esse problema

### <a name="fixed-as-part-of-10016"></a>Corrigido como parte do 10.0.16

-  [KB 4598335] Os controles de cadeia de caracteres de várias linhas não respeitam sua DisplayHeights em listas/placas 
-  [KB 4591891] As linhas de proposta de fatura desaparecem ao desmarcar linhas
-  [KB 4592104] Não é possível editar registros após clicar em "Corrigir problema" e mover para uma linha diferente sem corrigir o problema de validação
-  [KB 4594449] Botões "Nunca" e "Limpar" estão faltando no seletor de data 
-  [KB 4594448] A inserção da hora é tratada de forma diferente com a nova grade
-  [KB 4600059] Erro de cliente inesperado com limitação de email
-  [KB 4574584] A visualização do anexo de despesa não fica disponível ao passar o mouse sobre o ícone de recibo

### <a name="fixed-as-part-of-10015"></a>Corrigido como parte do 10.0.15    

-  (Atualização de qualidade) [KB 4594444] Erro de cliente inesperado com versão prévia para controle de entrada segmentada
-  [KB 4582723] Opções de exibição que não aparecem quando executadas posteriormente no ciclo de vida do formulário
-  [KB 4591988] Problemas ao usar o teclado para selecionar um valor de uma pesquisa de ReferenceGroup
-  [KB 4588958] O teste Regression Suite Automation Tool (RSAT) o falha e exibe o erro: TypeError: não é possível ler a propriedade "texto" de indefinido
-  [KB 4591970] Erro de cliente inesperado após colar do Excel imediatamente após clicar na grade
-  [KB 4591904] As alterações de dados não são salvas se, após a edição de um controle, o usuário clicou imediatamente e abriu a pesquisa de um controle diferente
-  [KB 4584752] Erro de cliente inesperado na página Propostas de fatura de projeto
-  [KB 4584540] Não é possível sair da grade depois de colar uma única linha em uma linha do diário
-  [KB 4591908] Ao criar uma nova linha, o foco permanece na coluna em que você estava

### <a name="fixed-as-part-of-10014"></a>Corrigido como parte do 10.0.14

-  (Atualização de qualidade) [KB 4584752] Erro de cliente inesperado na página Propostas de fatura de projeto
-  [KB 4583880] Os testes Regression Suite Automation Tool (RSAT) falham na ação OpenLookup com "Não é possível ler a propriedade RowIndex de indefinido"
-  [KB 4583847] Erro de cliente inesperado ao navegar pelas pesquisas

### <a name="fixed-as-part-of-10013"></a>Corrigido como parte do 10.0.13

-  (Atualização de qualidade) [KB 4584752] Erro de cliente inesperado na página Propostas de fatura de projeto
-  (Atualização de qualidade) [KB 4583880] Os testes da Regression Suite Automation Tool (RSAT) falham na ação OpenLookup com "Não é possível ler a propriedade RowIndex de indefinido"
-  (Atualização de qualidade) [KB 4583847] Erro de cliente inesperado ao navegar pelas pesquisas 
-  (Atualização de qualidade) [Bug 471777] Não é possível selecionar campos em uma grade para editar ou criar um aplicativo móvel
-  [KB 4582727] Congelamento de grade depois que o usuário recebe uma caixa de diálogo para itens com várias quantidades
-  [Bug 474851] Hiperlinks nos controles do grupo de referência não funcionam 
-  [Bug 474848] Visualizações aperfeiçoadas com grades não são exibidas
-  [KB 4582726] A propriedade RotateSign não está sendo respeitada  
-  [Bug 470173] Caixas de seleção em linhas inativas são alternadas quando se clica no espaço em branco na célula
-  [Bug 474848] Visualizações aperfeiçoadas com grades não são exibidas
-  [Bug 474851] Hiperlinks nos controles do grupo de referência não funcionam 
-  [Bug 471777] Não é possível selecionar campos em uma grade para editar ou criar um aplicativo móvel
-  [KB 4569441] Problemas com a renderização de listas de cartões de várias colunas, dicas de ferramentas em imagens e opções de exibição em alguns campos
-  [KB 4575279] Nem todas as linhas marcadas são excluídas no diário geral
-  [KB 4575233] As opções de exibição não são restauradas após a movimentação para outra linha
-  [Bug 477884] As pesquisas retornam valor ou registro incorreto se o novo controle de grade estiver ativado
-  [KB 4571095] O lançamento de recebimento de produtos ocorre quando você pressiona acidentalmente Enter (manipulação correta da ação padrão de uma página)
-  [KB 4575437] Pesquisas com controles editáveis são fechadas inesperadamente
-  [KB 4569418] Linha duplicada criada no formulário agenda de entrega
-  [KB 4575435] A visualização avançada às vezes persiste mesmo quando o ponteiro do mouse não está próximo ao campo
-  [KB 4575434] A pesquisa não filtra quando o campo for modificado
-  [KB 4575430] Os valores nos campos de senha não são mascarados na grade
-  [KB 4569438] "O processamento parou devido a um problema de validação" exibido após a marcação de linhas durante a liquidação de transações do fornecedor
-  [KB 4569434] A atualização do formulário entidades legais resulta em menos registros
-  [KB 4575297] O foco continua movendo-se para o painel do gravador de tarefas durante a edição e a tabulação em uma grade
-  [KB 4566773] Transações de correção não exibidas como negativas na consulta de transações do comprovante 
-  [KB 4575288] O foco é redefinido para a linha ativa ao selecionar a borda entre as linhas em uma lista simples
-  [KB 4575287] O foco não retorna para a primeira coluna quando a seta para baixo é usada para criar uma nova linha em diários
-  [KB 4564819] Não é possível excluir linhas em uma fatura de texto livre (porque a fonte de dados ChangeGroupMode = ImplicitInnerOuter)
-  [KB 4563317] As dicas de ferramentas/visualizações aperfeiçoadas não são mostradas para imagens

### <a name="fixed-as-part-of-10012"></a>Corrigido como parte do 10.0.12

- [KB 4558545] Os controles de tabela não atualizam o conteúdo dos itens exibidos.
- [KB 4558570] Os itens ainda são mostrados na página após a exclusão do registro.
- [KB 4558572] Estilo associado à extensão estendida do painel de listagem **ExtendedStyle** não é aplicado.
- [KB 4558573] Os erros de validação não podem ser corrigidos quando a alteração necessária está fora da grade.
- [KB 4558584] Os números negativos não são renderizados corretamente.
- [KB 4560726] Um "erro de cliente inesperado" ocorre após a troca entre listas usando um controle de modo de exibição de lista.
- [KB 4562141] Os índices de grade são desativados após um novo registro ser adicionado.
- [KB 4562151] As opções de gravador de tarefas **Validar** e **Copiar** não estão disponíveis para controles de data/número. 
- [KB 4562153] As caixas de seleção com várias seleções não ficam visíveis em grades da lista/placa.
- [KB 4562646] Às vezes, você não pode clicar fora da grade após selecionar várias linhas na grade.
- [KB 4562647] O foco é redefinido para o primeiro controle na caixa de diálogo **Publicar** após uma nova linha ser adicionada na grade de funções de segurança.
- [KB 4563310] A visualização avançada não é fechada após a alteração de uma linha.
- [KB 4563313] Um "erro de cliente inesperado" ocorre no Internet Explorer quando um valor é selecionado em uma pesquisa.
- [KB 4564557] As pesquisas e os menus suspensos não são abertos no Internet Explorer
- [KB 4563324] A navegação não funciona após a abertura do espaço de trabalho **Gerenciamento de pessoal**.

### <a name="fixed-as-part-of-10011"></a>Corrigido como parte do 10.0.11

- [Questão 432458] Linhas vazias ou duplicadas são mostradas no início de algumas coleções filhas.
- [KB 4549711] As linhas em uma proposta de pagamento não podem ser removidas corretamente após a habilitação do novo controle de grade.
- [KB 4558374] Os registros que exigem uma caixa de diálogo de seletor polimórfico não podem ser criados.
- [KB 4558375] O texto de ajuda não é exibido em colunas na nova grade.
- [KB 4558376] As grades do painel de lista não são processadas na altura correta em Internet Explorer.
- [KB 4558377] As colunas da caixa de combinação que têm largura de **SizeToAvailable** não são processadas em algumas páginas.
- [KB 4558378] A busca detalhada às vezes abre o registro errado.
- [KB 4558379] Ocorre um erro quando as pesquisas são abertas onde **ReplaceOnLookup**=**Não**.
- [KB 4558380] O espaço disponível na grade não é preenchido imediatamente depois que parte da página é recolhida.
- [KB 4558381] Os números negativos não são renderizados corretamente/os usuários podem ficar presos depois que problemas de validação são encontrados.
- [KB 4558382] Ocorreram erros inesperados do cliente.
- [KB 4558383] Controles fora da grade não são atualizados após o último registro ser excluído.
- [KB 4558587] Os grupos de referência que possuem caixas de combinação para campos de substituição não mostram valores.
- [KB 4562143] Os campos não são atualizados depois que um processamento de alteração/grade de linha fica preso após a exclusão da linha.
- [KB 4562645] Uma exceção ocorre quando uma pesquisa é aberta enquanto os testes da Regression Suite Automation Tool (RSAT) estão em execução.

### <a name="fixed-as-part-of-10010"></a>Corrigido como parte do 10.0.10

- [Questão 414301] Alguns dados das linhas anteriores desaparecem quando novas linhas são criadas.
- [Bug 417044] Não há mensagens de grade vazias para grades de estilo de lista.
- [KB 4539058] Algumas grades (geralmente nas Guias Rápidas) não são renderizadas (mas serão processadas se você sair do zoom).
- [KB 4549734] As linhas ativas não serão tratadas como marcadas se a coluna de marcação estiver oculta.
- [KB 4549796] Os valores não podem ser editados em uma grade quando ela está em modo de exibição.
- [KB 4558367] A seleção de texto fica inconsistente quando as linhas são alteradas.
- [KB 4558368] Várias seleções via teclado são permitidas em cenários de seleção única.
- [KB 4558369] As imagens de status desaparecem na grade hierárquica.
- [KB 4558370] Uma nova linha não é exibida com rolagem na exibição.
- [KB 4558372] A nova grade ficará presa no modo de processamento se o número de colunas no conteúdo colado exceder o número de colunas restantes na grade.
- [KB 4562631] Os valores de tempo não estão formatados corretamente.

### <a name="quality-update-for-1009platform-update-33"></a>Atualização de qualidade para 10.0.9/Platform update 33

- [KB 4550367] Os valores de tempo não estão formatados corretamente.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
