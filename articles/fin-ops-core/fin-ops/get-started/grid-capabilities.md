---
title: Recursos de grade
description: Este tópico descreve vários recursos avançados do controle de grade. É necessário habilitar o novo recurso de grade para ter acesso a esses recursos.
author: jasongre
ms.date: 04/25/2022
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
ms.openlocfilehash: 57133a853d1700b2d8ebb938f93af475410b82cb
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644338"
---
# <a name="grid-capabilities"></a>Recursos de grade

[!include [banner](../includes/banner.md)]

O novo controle de grade fornece vários recursos úteis e eficientes que você pode usar para melhorar a produtividade do usuário, construir exibições mais interessantes dos dados e obter insights significativos sobre seus dados. Este artigo abordará os seguintes recursos: 

- Calculando totais
- Digitação à frente do sistema
- Avaliação de expressões matemáticas 
- Agrupamento dados tabulares (habilitados separadamente utilizando o recurso **Agrupamento em grades**)
- Congelamento de colunas (habilitados separadamente com o uso do recurso **Congelar colunas em grades**)
- Ajustar automaticamente a largura da coluna
- Colunas alongáveis

## <a name="calculating-totals"></a>Calculando totais
Nos aplicativos de finanças e operações, os usuários podem ver os totais na parte inferior das colunas numéricas em grades. Esses totais são mostrados em uma seção de rodapé na parte inferior da grade. 

### <a name="showing-the-grid-footer"></a>Mostrando o rodapé da grade
Existe uma área de rodapé na parte inferior de cada grade tabular nos aplicativos de finanças e operações. O rodapé pode mostrar informações valiosas relacionadas aos dados que aparecem na grade. Veja alguns exemplos dessas informações:

- O número de linhas selecionadas na tabela (quando mais de um registro é selecionado)
- Totais gerais na parte inferior das colunas numéricas configuradas
- O número de linhas no conjunto de dados 

Esse rodapé é ocultado por padrão, mas ele pode ser ativado. Para mostrar o rodapé de uma grade, selecione o botão **Opções de grade** no cabeçalho de grade e, depois, a opção **Mostrar rodapé**. Depois de ativar o rodapé de uma determinada grade, essa configuração será lembrada até que o usuário opte por ocultar o rodapé. Para ocultar o rodapé, selecione **Ocultar rodapé** no menu **Opções de grade**.

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

Se o cálculo demorar para ser concluído, você poderá cancelar a operação selecionando o botão **Cancelar**. Às vezes, o conjunto de dados será grande demais para calcular os totais (um limite imposto pela sua organização) e você será notificado para filtrar mais os dados. 

> [!NOTE]
> As administrações de sistema podem modificar o limite para o número de registros disponíveis para calcular os totais ajustando o parâmetro **Número máximo de registros locais para cada de grade** na página **Opções de desempenho do cliente**. O valor padrão é 25.000 registros. Os administradores devem ter cuidado ao ajustar esse valor porque um valor muito grande pode esgotar a memória disponível na máquina do usuário. A recomendação não deve exceder 50.000 registros.   

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

- Valor de dados para o grupo 
- Nome da coluna (essas informações são especialmente úteis quando você tem vários níveis de agrupamento)
- Número de linhas de dados neste grupo
- Subtotais de qualquer coluna configurada para mostrar totais

Com a opção [Exibições salvas](saved-views.md) habilitada, você pode salvar o agrupamento como parte de uma exibição em páginas que permitem que as consultas sejam salvas nas exibições. Por exemplo, aquelas com seletores de exibição grandes. Consulte a seção [Alternância entre as exibições](saved-views.md#switching-between-views) para obter mais detalhes. 

### <a name="multiple-levels-of-grouping"></a>Vários níveis de agrupamento
Depois de agrupar os dados por uma única coluna, você poderá agrupar os dados por uma coluna diferente selecionando **Agrupar por esta coluna** na coluna desejada. Esse processo pode ser repetido até que você tenha cinco níveis aninhados de agrupamento, que é a profundidade máxima compatível. Neste ponto, você não poderá mais agrupar por colunas adicionais.

A qualquer momento, você poderá remover o agrupamento em qualquer coluna clicando com o botão direito do mouse nessa coluna e selecionando **Desagrupar**. Você também pode remover o agrupamento de todas as colunas selecionando **Opções de grade** e **Desagrupar tudo**.

### <a name="sorting-grouped-data"></a>Classificação de dados agrupados
Depois de agrupar os dados por uma ou mais colunas, você pode alterar a direção da classificação de qualquer coluna de agrupamento por meio do cabeçalho de coluna correspondente. 

O comportamento quando você classifica as colunas não agrupadas depende da sua versão do produto:

- Na versão 10.0.24 e anterior, se você classificar em uma coluna não agrupada, o agrupamento será removido de todas as colunas e os dados serão classificados na coluna selecionada. 
- Na versão 10.0.25 e posterior, se você classificar em uma coluna não agrupada, o agrupamento permanece intacto, e os dados serão classificados em cada grupo com base na coluna selecionada.

### <a name="expanding-and-collapsing-groups"></a>Como expandir e recolher grupos
O agrupamento inicial de dados terá todos os grupos expandidos. Você pode criar exibições resumidas dos dados recolhendo grupos individuais ou pode usar a expansão e o recolhimento de grupos para auxiliar na navegação pelos dados. Para expandir ou recolher um grupo, selecione o botão de divisa (>) na linha de cabeçalho de grupo correspondente. Observe que o estado de expandir/recolher de grupos individuais **não** é salvo na personalização.

### <a name="selecting-and-unselecting-rows-at-the-group-level"></a>Seleção e cancelamento de seleção de linhas em nível de grupo
Da mesma forma que você pode selecionar (ou cancelar) todas as linhas na grade, marcando a caixa de seleção na parte superior da primeira coluna na grade, você também pode selecionar rapidamente (ou cancelar a seleção) todas as linhas de um grupo marcando a caixa de seleção na linha de cabeçalho de grupo correspondente. A caixa de seleção na linha de cabeçalho de grupo sempre refletirá o estado de seleção atual das linhas desse grupo, independentemente da seleção: todas as linhas, nenhuma linha apenas algumas linhas.

### <a name="hiding-column-names"></a>Ocultar nomes de coluna
Ao agrupar dados, o comportamento padrão é mostrar o nome da coluna na linha de cabeçalho do grupo. Você pode optar por suprimir o nome da coluna em linhas do cabeçalho de grupo, selecionando **Opções de grade** > **Ocultar nome da coluna do grupo**.

### <a name="grouping-on-date-and-time-columns"></a>Agrupamento em colunas de data e hora
A partir da versão 10.0.24, para os campos Data ou DateTime, a opção foi adicionada para agrupamento por ano, mês ou dia. O grupo "valor", na linha de cabeçalho correspondente, corresponderá ao formato desse campo. Além disso, para os campos DateTime e Hora, você poderá agrupar por hora, minuto ou segundo. 

## <a name="freezing-columns"></a>Congelar colunas
Algumas colunas em uma grade podem ser tão importantes para o contexto que você não quer que elas saiam de vista conforme a rolagem. Em vez disso, talvez você deseje que os valores dessas colunas fiquem sempre visíveis. O recurso **Congelar colunas na grade** oferece essa flexibilidade aos usuários. 

Para congelar uma coluna, clique com o botão direito do mouse no cabeçalho da coluna e selecione **Congelar coluna**. Na primeira vez que você concluir esta etapa, a coluna selecionada se tornará a primeira coluna e não sairá mais de vista. Qualquer coluna subsequente que você congelar será adicionada à direita da última coluna congelada. Você pode usar a funcionalidade de movimentação padrão para reordenar colunas congeladas conforme necessário. No entanto, as colunas congeladas não podem ser movidas de forma que apareçam entre o conjunto de colunas descongeladas. Além disso, as colunas congeladas não podem ser movidas de forma que apareçam entre o conjunto de colunas congeladas.

Para descongelar uma coluna, clique com o botão direito do mouse no cabeçalho da coluna congelada e selecione **Descongelar coluna**. 

Observe que a seleção de linha e as colunas de status de linha e status na nova grade ficam sempre congeladas como as duas primeiras colunas. Portanto, quando essas colunas são incluídas em uma grade, elas sempre estarão visíveis para os usuários, independentemente da posição de rolagem horizontal na grade. Essas duas colunas não podem ser reordenadas.

## <a name="autofit-column-width"></a>Ajustar automaticamente a largura da coluna
Como no Excel, os usuários podem forçar o redimensionamento automático de uma coluna com base no conteúdo mostrado atualmente nessa coluna. Para isso, clique duas vezes nas alças de dimensionamento na coluna ou focalize o cabeçalho da coluna e pressione **A** (para ajuste automático). Esse recurso está disponível a partir da versão 10.0.23.

## <a name="frequently-asked-questions"></a>Perguntas frequentes
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>Como habilitar o novo controle de grade no meu ambiente? 

O recurso **Novo controle de grade** está disponível diretamente em Gerenciamento de recursos em qualquer ambiente. Após habilitar o recurso no gerenciamento de recursos, todas as sessões de usuário subsequentes usarão o novo controle de grade. 

Esse recurso é habilitado por padrão a partir da versão 10.0.21 e deve ser obrigatório em outubro de 2022.  

## <a name="developer-opting-out-individual-pages-from-using-the-new-grid"></a>[Desenvolvedor] Impedir que páginas individuais use a nova grade 
Se a sua organização descobre uma página que tem algumas questões usando a nova grade, uma API está disponível para permitir que um formulário individual use o controle de grade herdado enquanto ainda permite que o restante do sistema utilize o novo controle de grade. Para recusar uma página individual da nova grade, adicione a seguinte postagem de chamada `super()` no método do formulário `run()`.

```this.forceLegacyGrid();```

Esta API será honrada até o novo controle de grade se tornar obrigatório. Esta alteração está destinada a outubro de 2022. Se algum problema exigir o uso dessa API, informe-o à Microsoft.

### <a name="forcing-a-page-to-use-the-new-grid-after-previously-opting-out-the-grid"></a>Forçar uma página a usar a nova grade depois de ter recusado anteriormente a grade
Se você tiver recusado o uso da nova grade em uma página individual, convém reabilitar posteriormente a nova grade após os problemas subjacentes terem sido resolvidos. Para isso, você só precisa remover a chamada para `forceLegacyGrid()`. A alteração não terá efeito até que uma das seguintes ações ocorra:

- **Reimplantação do ambiente**: quando um ambiente é atualizado e reimplantado, a tabela que armazena as páginas que recusaram a nova grade (FormControlReactGridState) é automaticamente limpa.
- **Limpeza manual da tabela**: para cenários de desenvolvimento, será necessário usar SQL para limpar a tabela FormControlReactGridState e reiniciar o AOS. Essa combinação de ações redefinirá o armazenamento em cache de páginas que recusaram a nova grade.

## <a name="developer-opting-individual-grids-out-of-the-typing-ahead-of-the-system-capability"></a>[Desenvolvedor] Optar por grades individuais fora da digitação antes do recurso da capacidade
Alguns cenários surgiram que não são propícios a um funcionamento com a capacidade de *Digitação antes do recurso do sistema* da grade. (Por exemplo, um código disparado quando uma linha é validada faz com que uma pesquisa de fonte de dados seja disparada e, em seguida, a pesquisa pode corromper edições não confirmadas em linhas existentes.) Se a sua organização descobre tal cenário, há uma API disponível que permite que um desenvolvedor opte por uma grade individual fora da validação de linha assíncrona e reverta para o comportamento herdado.

Quando a validação de linha assíncrona está desabilitada em uma grade, os usuários não podem criar uma nova linha ou mover para uma linha existente diferente na grade enquanto houver problemas de validação na linha atual. Como um efeito colateral dessa ação, as tabelas não podem ser coladas do Excel em grades do Finance and Operations.

Para optar por uma grade individual fora da validação da linha assíncrona, adicionar a seguinte chamada após `super()` no método do formulário `run()`.

```<gridControl>.allowPreemptiveClient(false);```

> [!NOTE]
> - Essa chamada deve ser invocada somente em casos excepcionais e não deve ser a norma para todas as grades.
> - Não é recomendável que você alterne essa API no runtime depois que o formulário for carregado.

## <a name="developer-size-to-available-width-columns"></a>[Desenvolvedor] Colunas de tamanho para largura disponível
Se um desenvolvedor definir a propriedade **WidthMode** como **SizeToAvailable** para colunas dentro da nova grade, essas colunas terão inicialmente a mesma largura que teriam se a propriedade fosse definida como **SizeToContent**. No entanto, elas se estendem para usar qualquer largura extra disponível dentro da grade. Se a propriedade for definida como **SizeToAvailable** para várias colunas, todas essas colunas compartilham qualquer largura extra disponível dentro da grade. No entanto, se um usuário redimensionar manualmente uma dessas colunas, a coluna se torna estática. Ele permanecerá nessa largura e não será mais esticado para ocupar a largura de grade disponível extra.

## <a name="known-issues"></a>Problemas conhecidos
Esta seção mantém uma lista de problemas conhecidos para o novo controle de grade.

### <a name="open-issues"></a>Questões em aberto
- Depois de habilitar o recurso **Novo controle de grade**, algumas páginas continuarão a usar o controle de grade existente. Isso acontecerá nas seguintes situações:
 
    - Há uma lista de cartões na página que é renderizada em várias colunas.
    - Existe uma lista de placas agrupadas na página.
    - Uma coluna de grade com um controle extensível sem reação.

    Quando um usuário encontra primeiro uma dessas situações, uma mensagem será exibida sobre a atualização da página. Depois que esta mensagem for exibida, a página continuará a utilizar a grade existente para todos os usuários até a próxima atualização da versão do produto. Uma melhor manipulação desses cenários, de forma que a nova grade possa ser utilizada, será considerada para uma atualização futura.

- [KB 4582758] Os registros ficam borrados quando você altera o zoom de 100 para qualquer outro percentual
- [KB 4592012] Erro de cliente inesperado no IE11 ao colar várias linhas do Excel

    A Microsoft não está buscando uma solução para esse problema


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
