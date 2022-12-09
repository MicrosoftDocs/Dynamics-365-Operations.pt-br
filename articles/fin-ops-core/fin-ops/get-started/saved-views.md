---
title: Exibições salvas
description: Este artigo descreve como usar os recursos de exibições salvas.
author: jasongre
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: Platform update 28
ms.openlocfilehash: 571a4f403da0d20256f788c791cab273827c91b5
ms.sourcegitcommit: fb9b6969218f2b82f0a4c72bfad75387fe00395c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/22/2022
ms.locfileid: "9799482"
---
# <a name="saved-views"></a>Exibições salvas

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

[!INCLUDE [PEAP](../../../includes/peap-1.md)]

## <a name="introduction"></a>Introdução

A personalização desempenha um papel importante ao permitir que usuários e organizações otimizem a experiência do usuário para atender às suas necessidades. Para obter mais detalhes sobre personalização, consulte [Personalizar a experiência do usuário](personalize-user-experience.md).

A personalização tradicional permite que usuários tenham apenas um conjunto de personalizações por página. O recurso **Exibições salvas** expande a personalização de várias maneiras importantes:

- As exibições permitem que os usuários tenham vários conjuntos nomeados de personalizações por formulário, que podem alternar rapidamente conforme necessário. Isso permite que um usuário crie várias exibições otimizadas de uma página, em que cada exibição foi adaptada para atender às necessidades de execução de uma determinada tarefa comercial. 
- As exibições criadas para determinados tipos de página também podem incluir filtros ou classificações adicionados pelo usuário, o que permite que os usuários retornem rapidamente a conjuntos de dados filtrados comumente. Consulte a seção [Quais páginas oferecem suporte a exibições](saved-views.md#what-pages-support-views) para obter mais detalhes. 
- As exibições podem ser publicadas para usuários em funções de segurança específicas e entidades legais específicas. Portanto, qualquer usuário com uma função especificada e acesso a uma entidade legal especificada poderá acessar e usar essa exibição, mesmo que não tenha permissão para personalizar. Esse recurso de publicação permite que as organizações definam exibições padrão corporativas otimizadas para seus negócios. Para obter mais informações, consulte a seção [Gerenciar personalizações no nível organizacional com exibições](saved-views.md#managing-personalizations-at-an-organizational-level-with-views).
- Diferentemente da personalização tradicional, as exibições não são salvas automaticamente quando um usuário executa personalizações ou filtra uma lista. Os salvamentos explícitos são necessários para dar aos usuários a flexibilidade de criar uma exibição antes ou depois que as alterações associadas a essa exibição forem feitas. Esse requisito também garante que as definições de exibição não sejam alteradas acidentalmente por filtros ou personalizações destinadas ao uso de longo prazo. Os itens que o sistema armazena automaticamente como parte do uso de página comum (por exemplo, larguras de coluna ou o estado expandido ou recolhido de seções) serão salvos por exibição.
- As exibições podem ser adicionadas a espaços de trabalho, como blocos, listas ou links. Portanto, um conjunto de dados filtrados pode ser exibido em um espaço de trabalho e os usuários podem associar um conjunto de personalizações relevantes para esse conjunto de dados a um bloco ou link.

## <a name="switching-between-views"></a>Alternância entre exibições

Após a disponibilização de exibições para um ambiente, a parte superior de qualquer página que ofereça suporte a exibições incluirá um controle de seletor de exibição recolhido que mostra o nome da exibição atual.

Existem duas variações de tamanho para o seletor de exibição: 

- **Grandes seletores de exibição** – as páginas que apresentam de forma proeminente uma lista terão um seletor de exibição maior por alguns motivos. O mais importante é que o seletor de exibição maior indica as páginas em que a exibição pode incluir filtros e classificações definidos pelo usuário. Como os filtros e classificações são incluídos nas exibições, o tamanho de seletor maior também é garantido, pois os nomes de exibição geralmente serão a melhor descrição dos dados mostrados na tela, e a expectativa é a de que os usuários alternem entre as exibições com mais frequência nesses tipos de página. O agrupamento em uma grade também pode ser salvo em exibições de uma página com seletores de exibição grandes. 
    
    [![Grande seletor de exibição que oferece suporte às modificações da consulta na exibição.](./media/views-largeViewSelector.png)](./media/views-largeViewSelector.png)

- **Seletores de exibição pequenos** – todas as outras páginas inteiras (exceto espaços de trabalho e o painel) têm um seletor de exibição menor que aparece ao lado da legenda da página. As exibições nessas páginas incluem apenas personalizações, não filtros definidos pelo usuário. Nessas páginas, a legenda ou o título do registro costuma ser a informação mais importante na parte superior da página. O tamanho menor do seletor de exibição também reflete a frequência mais baixa de alternância de exibição que é esperada nessas páginas. 
    
    [![Pequeno seletor de exibição que não oferece suporte às modificações da consulta na exibição.](./media/views-smallViewSelector.png)](./media/views-smallViewSelector.png)
 
Se você selecionar o nome da exibição, o seletor de exibição será aberto e mostrará a lista de exibições disponíveis para a página.

Se o recurso **Suporte à entidade legal aperfeiçoado para exibições salvas** estiver ativado, o seletor de exibições mostrará as exibições disponíveis em duas seções. A primeira seção mostra todas as exibições específicas da entidade legal atual, e a segunda mostra as exibições disponíveis para todas as entidades legais. A primeira seção será visível apenas se houver exibições específicas da entidade legal para a página.

- **Exibição padrão** – a exibição **padrão** é a exibição pronta para uso da página, em que nenhuma personalização é aplicada.
- **Exibições pessoais** – as exibições sem cadeados representam as exibições pessoais. São exibições que você criou ou que um administrador forneceu a você.
- **Exibições bloqueadas** – algumas exibições (como a exibição **Padrão** e todas as exibições publicadas na sua função) têm um símbolo de cadeado ao lado no seletor de exibição. Este símbolo indica que não é possível editar essas exibições. No entanto, as alterações que refletem o uso da página são salvas automaticamente. Essas alterações incluem alterações na largura de uma coluna de grade e alterações no estado expandido ou recolhido de uma Guia Rápida. Entretanto, se você tiver privilégios de personalização, você pode usar a ação **Salvar como** para criar uma exibição pessoal baseada em uma exibição bloqueada.
- **Novas exibições** – as exibições publicadas que ainda não foram abertas têm um símbolo de spark à esquerda do nome da exibição.

Para alternar para uma exibição diferente, primeiro abra o seletor de exibição e selecione a exibição que deseja carregar. 

## <a name="creating-and-modifying-views"></a>Criação e modificação de exibições

Diferentemente da personalização tradicional, as exibições não são salvas automaticamente quando um usuário personaliza a página ou quando um usuário aplica um filtro a uma lista ou o classifica. Uma ação explícita é necessária para salvar essas alterações em uma exibição. Esse requisito dá aos usuários a flexibilidade de criar uma exibição antes ou depois da execução das alterações associadas a essa exibição. Ele também garante que as definições de exibição não sejam alteradas acidentalmente por filtros ou personalizações ocasionais. Note que itens de uso de página típicos (por exemplo, larguras de coluna ou o estado expandido ou recolhido de seções) são salvos automaticamente na exibição atual, até mesmo para exibições bloqueadas.

Para garantir que o estado atual da exibição seja conhecido, quando você começar a alterar uma exibição, personalizando-a ou filtrando-a, um asterisco (\*) aparecerá ao lado do nome da exibição atual. Esse símbolo indica que você está vendo uma versão da exibição não salva e modificada.

[![Alterações não salvas em uma exibição.](./media/views-unsavedChanges.png)](./media/views-unsavedChanges.png)

Se você quiser salvar essas alterações, siga as etapas a seguir.

1. Selecione o nome da exibição para abrir o seletor de exibição.
2. Para modificar a exibição existente, selecione **Salvar**. Note que esta ação não está disponível para exibições bloqueadas. 
3. Para criar uma exibição:

    1. Selecione **Salvar como**. 
    2. No painel **Salvar exibição como**, insira um nome e, opcionalmente, uma descrição para a exibição.
    3. Se desejar que essa seja sua exibição padrão, selecione **Fixar como padrão**. Para obter mais informações sobre as exibições padrão, consulte a seção [Alterar a exibição padrão](#changing-the-default-view) a seguir. 
    4. Se o recurso **Suporte à entidade legal aperfeiçoado para exibições salvas** estiver ativado, você poderá selecionar se deseja que essa exibição esteja disponível para todas as entidades legais ou apenas um subconjunto delas.
    5. Selecione **Salvar**.

## <a name="changing-the-default-view"></a>Alteração da exibição padrão

A exibição padrão é aquela que o sistema tenta abrir quando você abre a página pela primeira vez. Você deve definir a exibição padrão como a exibição que você espera usar com mais frequência. 

> [!NOTE]
> - No recurso de base **Exibições salvas**, há uma exibição padrão global única em todas as entidades legais. Se você alterar a exibição padrão, essa exibição será aberta por padrão, seja qual for a entidade legal utilizada no momento.
> - Quando o recurso **Suporte à entidade legal aperfeiçoado para exibições salvas** está ativado, cada entidade legal pode ter sua própria exibição padrão por página.

Para alterar a exibição padrão de uma página, siga estas etapas:

1. Alterne para a exibição que você usa como padrão. 
2. Selecione o nome da exibição para abrir o seletor de exibição. 
3. Selecione **Mais** e depois **Fixar como padrão**.

Como alternativa, ao criar uma exibição (ao usar a ação **Salvar como**), você pode tornar essa nova exibição a exibição padrão, definindo a opção **Fixar como padrão** antes de salvar a exibição.

> [!WARNING]
> Em alguns casos, a consulta que é associada à exibição padrão não é executada quando você abre uma página pela primeira vez. Por exemplo, se você abrir a página por meio de um bloco, a consulta do bloco será executada, independentemente da consulta que estiver associada à exibição padrão. Além disso, se você abrir uma página com uma exibição **padrão** que já tenha uma consulta definida, a consulta original será executada em vez da consulta da exibição padrão. Neste caso, você receberá uma mensagem informativa quando a exibição for carregada com uma ação incorporada que permita carregar diretamente a consulta da exibição padrão. Se você alternar exibições depois que a página for carregada, a consulta de exibição deverá poder ser executada conforme esperado. 

## <a name="managing-personal-views"></a>Gerenciamento de exibições pessoais

A caixa de diálogo **Gerenciar minhas exibições** oferece recursos básicos de manutenção sobre suas exibições pessoais e a ordem das exibições no seletor de exibição. Para abrir essa página, selecione o nome da exibição para abrir o menu suspenso do seletor de exibição, selecione **Mais** e depois selecione **Gerenciar minhas exibições**.

Se o recurso **Suporte à entidade legal aperfeiçoado para exibições salvas** estiver ativado, a seção **Minhas exibições** da caixa de diálogo **Gerenciar minhas exibições** mostrará as exibições disponíveis para a página em seções. Todas as exibições específicas da entidade legal atual são mostradas em sua própria seção. A seção **Exibições globais** sempre é mostrada, para que você possa gerenciar as exibições que estão disponíveis para a página em todas as entidades legais. 

Para obter uma lista de exibições disponíveis dessa página, o conjunto de ações a seguir está disponível.

- **Alterar a exibição padrão** – use a ação **Fixar como padrão** para tornar a exibição selecionada no momento a exibição padrão dessa página. Se o recurso **Suporte à entidade legal aperfeiçoado para exibições salvas** estiver ativado, a seção **Exibições globais** permitirá que você torne uma exibição o padrão para a entidade legal atual ou todas as entidades legais.
- **Reordenar suas exibições** – use as ações **Mover para cima** e **Mover para baixo** para reorganizar exibições em uma ordem específica.
- **Renomear uma exibição** – use a ação **Renomear** para alterar o nome da exibição pessoal selecionada no momento. Essa ação está desativada para exibições bloqueadas. 
- **Excluir uma exibição** – use a ação **Excluir** para excluir permanentemente a exibição selecionada no momento da página. Não há como recuperar uma exibição depois de removê-la.

Todas as alterações feitas nessa caixa de diálogo entrarão em vigor após você selecionar o botão **Atualizar**.

## <a name="managing-personalizations-at-an-organizational-level-with-views"></a>Gerenciamento de personalizações em nível organizacional com exibições

Para ajudar você a entender como melhorar o gerenciamento de personalizações no nível organizacional, esta seção descreve algumas diferenças no gerenciamento de personalização com e sem o recurso **Exibições salvas**.

Sem exibições, os administradores aplicariam um conjunto de personalizações para uma página a um usuário ou um grupo de usuários usando a página Personalização. Se esses usuários tivessem direitos de personalização, as personalizações seriam aplicadas a essa página. Contudo, não era possível impedir que os usuários personalizassem ainda mais a página, o que significava que a organização não podia garantir que seus usuários tivessem uma interface de usuário consistente. Se algum desses usuários não tiver direitos de personalização, as personalizações dadas a eles por um administrador não serão carregadas. Além disso, se novos usuários fossem contratados em uma organização, os administradores precisavam carregar manualmente um conjunto de personalizações para o usuário. Não havia mecanismo automático para especificar que um determinado conjunto de personalizações deveria estar disponível para usuários nessa função.

O recurso **Exibições salvas** facilita muito o gerenciamento organizacional de personalizações porque as exibições podem ser publicadas para grupos de usuários. Depois de publicar uma exibição, qualquer usuário com um direito de acesso definido e acesso a uma das entidades legais especificadas poderá visualizar e usar a exibição, mesmo que esse usuário não tenha acesso para personalização. Embora todo usuário tenha uma cópia da exibição publicada, na qual itens de uso da página são aplicados automaticamente, nenhum usuário pode salvar personalizações ou atualizações de consulta para uma exibição publicada. Em outras palavras, as exibições publicadas estão bloqueadas. Além disso, se funções forem atribuídas a novos usuários em entidades legais nas quais as exibições são publicadas, eles automaticamente verão as exibições associadas às funções e entidades legais deles. O administrador não precisa executar ações adicionais. Da mesma forma, se os usuários trocarem de funções em uma organização ou receberem acesso a diferentes entidades legais, eles podem não ter mais acesso às exibições anteriormente publicadas para eles. Novamente, o administrador não precisa executar ações adicionais.

As atualizações de uma exibição publicada podem ser facilmente distribuídas aos usuários, republicando a exibição para as funções de segurança e entidades legais apropriadas.

O recurso de publicação permite que as organizações definam exibições padrão corporativas otimizadas para seus negócios, direcionadas a usuários em funções de segurança específicas.

## <a name="publishing-views"></a>Publicação de exibições

Durante o processo de publicação, as exibições podem ser atribuídas a uma ou mais funções de segurança ou entidades legais. Portanto, qualquer usuário com acesso a uma entidade legal e atribuído a uma dessas funções pode acessar e usar as exibições. No entanto, o usuário não pode editar as exibições. Por padrão, os administradores do sistema têm acesso à ação **Publicar** no menu suspenso do seletor de exibição. No entanto, outros usuários confiáveis em sua organização também podem receber acesso para visualizar a publicação através da nova função **Administrador de exibições salvas**.

Para publicar uma exibição, siga estas etapas:

1. Crie e salve uma cópia pessoal da exibição que você deseja publicar. 
2. Com essa exibição atualmente carregada, selecione o nome da exibição para abrir o menu suspenso do seletor de exibição. 
3. Selecione o botão **Mais** e depois selecione **Publicar**. A caixa de diálogo **Publicar** será aberta.
4. Insira um nome para a exibição. O nome inserido é o nome que os usuários que recebem essa exibição visualizarão em seus seletores de exibição. Os nomes das exibições publicadas em uma página devem ser exclusivos. Nenhum nome duplicado é permitido, mesmo se a lista de funções ou de entidades legais à qual as exibições são aplicadas diferir.
5. Se o recurso **Suporte à tradução para exibições da organização** estiver ativado, você poderá adicionar traduções para o seu nome de exibição em quantos idiomas forem necessários para a organização selecionando o botão **Traduções** ao lado do campo **Nome**. O nome da exibição será mostrado aos usuários no seu idioma atual. Você também pode definir o idioma padrão para especificar a tradução que será mostrada aos usuários que estão executando idiomas para os quais nenhuma tradução foi definida.
5. Opcional: digite uma descrição para a exibição de modo que os usuários que receberem essa exibição possam compreender melhor sua finalidade. 
6. Determine se a exibição deve ser publicada como a exibição padrão para os usuários selecionados. Quando uma exibição se tornar padrão, os usuários a exibirão na próxima vez em que abrirem a página de destino. A única exibição padrão global de cada usuário direcionado será alterada. No entanto, os usuários ainda podem alterar a exibição padrão após a publicação.

    > [!NOTE]
    > Lembre-se do seguinte comportamento ao publicar uma exibição como o padrão:
    >
    > - Se você publicar uma exibição como o padrão para algumas das entidades legais ou todas elas, ocorrerá o seguinte comportamento:
    >
    >    - Se apenas o recurso de base **Exibições salvas** estiver ativado, a exibição padrão global única será alterada para cada usuário direcionado. 
    >    - Se o recurso **Suporte à entidade legal aperfeiçoado para exibições salvas** estiver ativado e você publicar a exibição em um subconjunto de entidades legais, a exibição padrão dessas entidades legais será alterada para cada usuário direcionado.
    >
    > - Se um usuário tiver funções em que várias exibições sejam publicadas como exibição padrão, a última exibição publicada será usada como a exibição padrão do usuário. 
    > - A publicação não funcionará para atribuições de função feitas usando grupos AAD. 

8. Adicione as funções de segurança que correspondem aos usuários que receberão essa exibição. 
9. Determine se você deseja publicar a exibição para as funções filho de cada função de segurança selecionada. Se fizer isso, marque a caixa de seleção **Incluir funções filho** na linha para as funções de segurança apropriadas. Observe que esta caixa de seleção não está disponível para funções sem funções filho.
10. Adicione as entidades legais para as quais essa exibição deve estar disponível. 

    > [!NOTE]
    > Lembre-se do seguinte comportamento se você publicar uma exibição para uma entidade legal específica, mas não publicar essa exibição como o padrão:
    >
    > - Se apenas o recurso de base **Exibições salvas** estiver ativado, o seletor de exibição do usuário para a página mostrará inicialmente a exibição apenas para as entidades legais especificadas. No entanto, depois que a exibição for carregada pela primeira vez, o seletor de exibição da página sempre a mostrará, independentemente da entidade legal.
    > - Se o recurso **Suporte à entidade legal aperfeiçoado para exibições salvas** estiver ativado, o seletor de exibição só mostrará a exibição para as entidades legais especificadas.

11. Selecione **Publicar**.

Observe que, em alguns ambientes, pode levar algum tempo (até uma hora) para que os usuários vejam a exibição publicada.

## <a name="modifying-a-published-view"></a>Modificação de uma exibição publicada

Depois de publicar uma exibição, talvez você deseje alterá-la. Embora não seja possível fazer alterações ao vivo em uma exibição publicada, como essas exibições estão bloqueadas para edição para todos os usuários (incluindo editores), você pode republicar uma exibição para atualizá-la.

Se as alterações que você deseja fazer em uma exibição publicada envolverem apenas os parâmetros de publicação (o nome e a descrição da exibição ou as funções de segurança nas quais a exibição é publicada), faça o seguinte:

1. Alterne para a exibição publicada dos parâmetros que você deseja atualizar. 
2. No menu suspenso do seletor de exibição, selecione **Republicar**. Se você estiver usando a versão 10.0.12 ou anterior, selecione **Publicar** e, depois, **Sim** para atualizar a exibição existente.
3. Atualize o nome, a descrição, funções de segurança e entidades legais para a exibição. 
4. Selecione **Publicar**. Se você tiver originalmente selecionado essa exibição publicada como a exibição padrão, ela voltará a ser a exibição padrão para os usuários após ser republicada. 

Se as alterações na exibição publicada envolverem modificações nas personalizações ou nos filtros associados a ela, siga estas etapas.

1. Carregue a exibição publicada que você deseja alterar. 
2. Faça as alterações necessárias no rascunho local.
3. No menu suspenso do seletor de exibição, selecione **Republicar**.
4. Selecione **Sim** para indicar que você deseja publicar a exibição junto com as alterações não salvas. 
5. Ajuste parâmetros de publicação que exijam ajuste e selecione **Publicar**. 

## <a name="managing-published-views"></a>Gerenciamento de exibições publicadas

Como o gerenciamento de exibições pessoais, a caixa de diálogo **Gerenciar minhas exibições** oferece aos usuários com privilégios de publicação os recursos básicos de manutenção das exibições publicadas dessa página (além de suas próprias exibições pessoais). Para abrir essa página, selecione o nome da exibição para abrir o menu suspenso do seletor de exibição, selecione **Mais** e depois selecione **Gerenciar minhas exibições**.

Embora todos os usuários tenham uma guia **Minhas exibições** que mostra exibições pessoais, os usuários com privilégios de publicação também têm uma guia **Exibições da organização** que mostra todas as exibições publicadas e não publicadas dessa página. Como vários usuários podem estar publicando exibições, é importante poder gerenciar a lista completa de exibições publicadas, mesmo que você não seja o usuário que publicou uma exibição específica.

Para a lista de todas as exibições publicadas da página, o seguinte conjunto de ações está disponível. 

- **Republicar** - use a ação **Republicar** para republicar uma exibição após a alteração dos parâmetros de publicação (nome, descrição, funções de segurança ou entidades legais).
- **Publicar** – use a ação **Publicar** para publicar uma exibição que não esteja publicada no momento. 
- **Cancelar publicação** – use a ação **Cancelar publicação** para tornar uma exibição inativa. A exibição ainda estará disponível no sistema, mas os usuários não a verão no seletor de exibição até que ela seja republicada.
- **Salvar como pessoal** – use a ação **Salvar como pessoal** para criar uma cópia de rascunho pessoal da exibição publicada. Esse recurso pode ajudá-lo a compreender o conteúdo de uma exibição que não foi publicada ou que ainda não foi publicada. Você também pode usá-lo para editar e depois republicar uma exibição.
- **Excluir** – use a ação **Excluir** para excluir permanentemente uma exibição publicada ou com publicação cancelada. Essa ação também remove a exibição para todos os usuários no sistema. A remoção de exibições publicadas entra em vigor após a seleção do botão **Salvar**. Não é possível recuperar uma exibição após ela ser excluída. 

## <a name="managing-views-globally"></a>Como gerenciar exibições globalmente

Embora alguns recursos de gerenciamento sejam reproduzidos em todas as páginas, como indicado neste artigo, os **administradores do sistema** e os **administradores da exibição salva** podem gerenciar as exibições de forma mais holística para o sistema por meio da página **Personalização**. Em particular, essa página tem as seguintes seções e recursos: 

- **Exibições publicadas** – essa seção lista todas as exibições que foram publicadas para sua organização. A partir daqui, você pode republicar uma exibição depois de ajustar as funções de segurança ou entidades legais de destino da exibição. Você também pode exportar, excluir ou cancelar a publicação de exibições. Você pode usar a ação **Salvar como pessoal** para criar uma cópia pessoal de uma exibição, de forma que possa atualizá-la ou entender melhor seu conteúdo. 
- **Exibições não publicadas** – esta seção lista todas as exibições da organização no sistema que não estão publicadas no momento. Essas exibições geralmente entram no sistema por meio do recurso de importação. Você pode publicar, exportar ou excluir essas exibições. A ação **Publicação rápida** adicionada à versão 10.0.12 permite que várias exibições desta seção sejam publicadas em uma ação, usando as configurações de direito de acesso e entidade legal existentes. Você pode usar a ação **Salvar como pessoal** para criar cópias pessoais dessas exibições, de forma que possa entender melhor seu conteúdo.
- **Exibições pessoais** – essa seção lista todas as exibições criadas por usuários no sistema. A partir daqui, você pode publicar uma exibição pessoal para a organização ou copiar uma ou mais dessas exibições para outros usuários. Você também pode exportar ou excluir essas exibições, conforme necessário.
- **Configurações do usuário** – selecione um usuário para exibir ou ajustar a capacidade do usuário de usar a personalização para o sistema inteiro ou para páginas específicas que o usuário visitou. Você pode exibir e interagir com as personalizações do usuário no sistema. Também é possível excluir todas as personalizações para esse usuário ou redefinir textos explicativos do recurso para o usuário. Se textos explicativos do recurso forem redefinidos, qualquer janela pop-up que apresente novos recursos, e que o usuário tenha ignorado antes, será reexibida na próxima vez que ele encontrar esses recursos.
- **Configurações do sistema** – é possível desativar temporariamente personalizações para todos os usuários no sistema. Nesse caso, nenhuma personalização é aplicada a usuários e todas as páginas são redefinidas para o estado padrão. Se, mais tarde, você ativar novamente a personalização, todas as personalizações serão reaplicadas. Também é possível excluir permanentemente todas as personalizações de todos os usuários do sistema. Não é possível recuperar as personalizações que foram excluídas. Portanto, antes de executar essa tarefa, verifique se você exportou todas as personalizações de que talvez precise posteriormente.

Os usuários com acesso à página **Personalização** também podem importar exibições pessoais ou de organização usando o botão **Importar exibições** no Painel de Ações. Para exibições da organização, você pode selecionar **Publicar imediatamente** a fim de disponibilizá-las aos usuários sem uma publicação explícita adicional.

## <a name="known-issues"></a>Problemas conhecidos

Para obter uma lista de problemas conhecidos com exibições salvas, consulte os [Criar formulários que utilizam totalmente as exibições salvas](../../dev-itpro/user-interface/understanding-saved-views.md).

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="how-do-i-enable-saved-views-in-my-environment"></a>Como faço para habilitar as exibições salvas no meu ambiente?

> [!NOTE]
> O recurso **Exibições salvas** exige que o sistema de Personalização nos aplicativos de finanças e operações esteja habilitado. Se a personalização estiver desativada para todo o ambiente, as exibições serão desabilitadas mesmo se você seguir as etapas abaixo. 

Você pode ativar e desativar o recurso **Exibições salvas** por meio do Gerenciamento de recursos em qualquer ambiente. Após serem ativadas, as exibições salvas serão habilitadas em todas as sessões de usuário subsequentes.

### <a name="what-happens-to-existing-personalizations-when-views-are-enabled"></a>O que acontece com as personalizações existentes quando as exibições estão habilitadas? 

Quando as exibições estão habilitadas, todas as personalizações existentes para um usuário e formulário são salvas em uma nova exibição chamada **Minha exibição**, que é automaticamente definida como a exibição padrão. Isso serve para garantir que haja uma experiência de usuário consistente antes e depois de as exibições serem habilitadas, exceto pelo controle do seletor de exibição que aparece nos formulários.

### <a name="what-pages-support-views"></a>Quais páginas oferecem suporte a exibições? 

As exibições estão disponíveis na maioria, mas não em todas as páginas. Especificamente, as exibições estão atualmente disponíveis em todas as páginas de tela inteira, exceto nos painéis. A exibição de suporte para espaços de trabalho está disponível por meio do recurso **Suporte às exibições salvas de espaços de trabalho**. A maioria das páginas que não são de tela inteira, que incluem caixas de diálogo suspensas, pesquisas, visualizações avançadas, não oferecem suporte a exibições no momento. A exibição de suporte para caixas de diálogo está disponível por meio do recurso **Suporte às exibições salvas de caixas de diálogo**.

### <a name="who-is-allowed-to-publish-views"></a>Quem tem permissão para publicar exibições?

Somente administradores de sistema e usuários que foram atribuídos à função de **Administrador de exibições salvas** têm direitos de publicar exibições. 

### <a name="why-am-i-not-able-to-save-filters-with-this-view"></a>Por que não consigo salvar filtros com essa exibição? 

Existem alguns motivos pelos quais um filtro pode não aparecer para salvar com uma exibição: 

- Pode ser que a página não permita salvar filtros como parte da definição de exibição. Observe que apenas as páginas com grandes seletores de exibição permitem que as personalizações e as modificações de consulta sejam salvas como uma exibição. Consulte a seção **Alternância de exibições** para obter mais informações. 
- A página em questão pode não dar o suporte correto às exibições, já que pode pode ignorar completamente a consulta ou operar em uma tabela temporária cujos dados não sejam persistentes. 

### <a name="what-data-will-i-see-when-i-visit-a-page"></a>Quais dados veremos quando eu acessar uma página?

Para páginas com seletores de exibição pequenos (somente as personalizações podem ser salvas na exibição), você sempre verá os mesmos dados ao acessar a página. 

Para páginas com seletores de exibição grandes (personalizações e consultas podem ser salvas na exibição), normalmente você verá os dados que estão vinculados à consulta associada à exibição padrão. Há duas exceções principais:

- Se você navegar até uma página de um bloco, a consulta do bloco será executada independentemente da consulta associada à exibição padrão. Se você criou esse bloco após habilitar as exibições, selecionar um bloco abrirá a página com a exibição associada a ele.
- Se você navegar até uma página e esse ponto de entrada incluir uma consulta, a consulta original será executada originalmente no lugar da consulta da exibição padrão. Quando isso acontecer, você será alertado por uma mensagem informativa quando a exibição estiver sendo carregada. Você também pode confirmar alternando para essa exibição após o carregamento da página, já que isso deve permitir que a consulta da exibição seja executada independentemente.

### <a name="why-is-a-view-that-was-published-for-a-specific-legal-entity-visible-in-all-legal-entities"></a>Por que uma exibição publicada para uma entidade legal específica é visível em todas as entidades legais?

Se você publicar uma exibição para uma entidade legal específica, mas não publicar essa exibição como o padrão, ocorrerá o seguinte comportamento:

- Se apenas o recurso de base **Exibições salvas** estiver ativado, o seletor de exibição do usuário para a página mostrará inicialmente a exibição apenas para as entidades legais especificadas. No entanto, depois que a exibição for carregada pela primeira vez, o seletor de exibição da página sempre a mostrará, independentemente da entidade legal. Esse comportamento ocorre porque os usuários obtêm sua própria cópia pessoal da exibição publicada quando ela é carregada, e as exibições pessoais são globais.
- Se o recurso **Suporte à entidade legal aperfeiçoado para exibições salvas** estiver ativado, o seletor de exibição só mostrará a exibição para as entidades legais especificadas. Esse comportamento ocorre porque o recurso permite que as exibições (inclusive exibições pessoais) sejam vinculadas a entidades legais específicas.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

