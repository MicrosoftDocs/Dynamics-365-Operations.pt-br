---
title: Exibições salvas
description: Este tópico descreve como usar os recursos de exibições salvas.
author: jasongre
manager: AnnBe
ms.date: 06/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: Platform update 28
ms.openlocfilehash: ea2f2dbd615480bb76e1d04a106ae69bf6f45f4b
ms.sourcegitcommit: fcae2e7938d7dbd94b76b0948b084d90d5fc919c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2019
ms.locfileid: "1620769"
---
# <a name="saved-views"></a>Exibições salvas

[!include [banner](../includes/banner.md)]
[!include [private preview banner](../includes/private-preview-banner.md)]

## <a name="introduction"></a>Introdução
A personalização desempenha um papel importante ao permitir que usuários e organizações otimizem a experiência do usuário no Microsoft Dynamics 365 for Finance and Operations para atender às suas necessidades. Para obter mais detalhes sobre personalização, consulte [Personalizar a experiência do usuário](personalize-user-experience.md).

Com a personalização tradicional, os usuários só poderiam ter um único conjunto de personalizações por formulário. As exibições salvas expandem a personalização de várias maneiras importantes:

-    As exibições permitem que os usuários tenham vários conjuntos nomeados de personalizações por formulário, que podem alternar rapidamente conforme necessário. Isso permite que um usuário crie várias exibições otimizadas de uma página, em que cada exibição foi adaptada para atender às necessidades de execução de uma determinada tarefa comercial. 

-    As exibições criadas para determinados tipos de página também podem incluir filtros ou classificações adicionados pelo usuário, o que permite que os usuários retornem rapidamente a conjuntos de dados filtrados comumente. Consulte a seção [Quais páginas oferecem suporte a exibições](saved-views.md#what-pages-support-views) para obter mais detalhes. 

-    As visualizações podem ser publicadas em funções de segurança, o que significa que qualquer usuário com essa função poderá acessar e usar essa exibição, independentemente da capacidade de personalização do usuário. Esse recurso de publicação permite que as organizações definam exibições padrão corporativas otimizadas para seus negócios. Consulte a seção [Gerenciar personalizações em nível organizacional com exibições](saved-views.md#managing-personalizations-at-an-organizational-level-with-views) para obter mais informações.

-    Diferentemente da personalização tradicional, as exibições não são salvas automaticamente quando um usuário executa personalizações explícitas ou filtra uma lista. São necessários salvamentos explícitos para fornecer flexibilidade na criação de uma exibição antes ou após as alterações associadas a essa exibição e para garantir que as definições de exibição não sejam alteradas de forma não intencional por filtros ou personalizações que não são destinadas a uso de longo prazo.  

## <a name="switching-between-views"></a>Alternância entre exibições
Após as exibições terem sido habilitadas para um ambiente, qualquer página que oferece suporte a exibições incluirá um controle de seletor de exibição recolhido na parte superior do formulário que mostra o nome da exibição atual.  

Existem duas variações de tamanho para o seletor de exibição: 

-   **Grandes seletores de exibição**: as páginas que apresentam de forma proeminente uma lista terão um seletor de exibição maior por alguns motivos. O mais importante é que o seletor de exibição maior indica as páginas em que a exibição pode incluir filtros definidos pelo usuário. Como os filtros são incluídos nas exibições, o tamanho de seletor maior também é garantido, pois os nomes de exibição geralmente serão a melhor descrição dos dados mostrados na tela, e a expectativa é a de que os usuários alternem entre as exibições com mais frequência nesses tipos de página.  
 
-   **Seletores de exibição pequenos**: todos os outros formulários de página inteira têm um seletor de exibição menor que aparece ao lado da legenda da página. As exibições nessas páginas incluem apenas personalizações (e não filtros definidos pelo usuário). Nessas páginas, a legenda do formulário ou o título do registro geralmente é a informação mais importante na parte superior do formulário. O tamanho menor também reflete uma frequência mais baixa esperada de alternância de exibição nessas páginas. 
 
Se você clicar no nome da exibição, o seletor de exibição será aberto e mostrará a lista de exibições disponíveis dessa página.

-    **Exibição clássica**: a exibição clássica é a aquela pronta para uso da página sem nenhuma personalização explícita aplicada.  
-    **Exibições pessoais**: as exibições sem cadeados representam suas exibições pessoais. São exibições que você criou ou que um administrador forneceu a você.  
-    **Exibições bloqueadas**: algumas exibições (como a exibição clássica e as exibições publicadas na sua função) têm um cadeado ao lado delas no seletor de exibição, indicando que você não pode editar essas exibições. Contudo, as personalizações implícitas em torno do uso da página são salvas automaticamente, como alterar a largura de uma coluna de grade ou expandir ou recolher uma Guia Rápida. Você pode, porém, criar uma exibição pessoal com base em uma exibição bloqueada usando a ação **Salvar uma cópia**, se tiver privilégios de personalização.
-    **Novas exibições**: as exibições publicadas que ainda não foram abertas são delineadas com uma faísca à esquerda do nome da exibição.  

Para alternar para uma exibição diferente, primeiro abra o seletor de exibição e selecione a exibição que deseja carregar. 

## <a name="creating-and-modifying-views"></a>Criação e modificação de exibições
Diferentemente da personalização tradicional, as exibições não são salvas automaticamente quando um usuário executa personalizações explícitas (ou filtra uma lista). Uma ação explícita é necessária para salvar essas alterações em uma exibição. Isso proporciona flexibilidade ao usuário na criação de uma exibição antes ou depois de as alterações associadas a essa exibição terem sido feitas e também garante que as definições de exibição não sejam alteradas involuntariamente por filtros ou personalizações ocasionais. Observe que as personalizações implícitas (como expandir ou recolher uma Guia Rápida ou alterar a largura de uma coluna da grade) são salvas automaticamente na exibição atual, mesmo para exibições bloqueadas. 

Para garantir que o estado atual da exibição seja conhecido, quando você começar a fazer alterações em uma exibição executando uma personalização ou filtragem explícita, um asterisco aparecerá ao lado do nome da exibição atual, indicando que você está olhando para uma versão não salva e modificada dessa exibição.

Se você quiser salvar essas alterações, siga as etapas a seguir.
1.  Selecione o nome da exibição para abrir o seletor de exibição.
2.  Para modificar a exibição existente:
     1. Selecione **Salvar**. Observe que essa ação não será habilitada para exibições bloqueadas. 
3.  Para criar uma exibição:
     1.    Selecione **Salvar uma cópia**. 
     2.    Insira um nome e (opcionalmente) uma descrição para a exibição.
     3.    Selecione **Salvar**.

## <a name="changing-the-default-view"></a>Alteração da exibição padrão
A exibição padrão é aquela que o sistema tentará abrir quando você navegar pela primeira vez até a página. Você deve defini-la como a exibição que você espera usar com frequência.  

Para alterar a exibição padrão de uma página, siga estas etapas: 
1.  Alterne para a exibição que você usa como padrão. 
2.  Selecione o nome da exibição para abrir o seletor de exibição. 
3.  Selecione **Mais** e depois **Fixar como padrão**.  

Como alternativa, ao criar uma exibição (usando a ação **Salvar uma cópia**), você pode tornar essa nova exibição a exibição padrão, definindo a opção **Fixar como padrão** antes de salvar a exibição.  

Observe que, em alguns casos, a consulta associada à exibição padrão não é executada quando você navega pela primeira vez até uma página. Por exemplo, se você navegar por um bloco até uma página, a consulta do bloco será executada, independentemente da consulta associada à exibição padrão. Além disso, se você navegar até uma página cuja exibição clássica já tenha uma consulta definida, a consulta original será executada originalmente no lugar da consulta da exibição padrão. Quando isso acontecer, você será alertado por uma mensagem informativa quando a exibição estiver sendo carregada. A alternância de exibições depois que a página foi carregada deve permitir que a consulta de exibição seja executada conforme o esperado.

## <a name="managing-personal-views"></a>Gerenciamento de exibições pessoais 
A caixa de diálogo **Gerenciar minhas exibições** oferece recursos básicos de manutenção sobre suas exibições pessoais e a ordem das exibições no seletor de exibição. Para abrir essa página, clique no nome da exibição para abrir o menu suspenso do seletor de exibição, selecione **Mais** e depois selecione **Gerenciar minhas exibições**.  

Para obter uma lista de exibições disponíveis dessa página, o conjunto de ações a seguir está disponível.  
-    **Alterar a exibição padrão**: use a ação **Fixar como padrão** action para tornar a exibição atualmente destacada a exibição padrão dessa página.  
-    **Reordenar suas exibições**: use as ações **Mover para cima** e **Mover para baixo** para reorganizar suas exibições em uma ordem específica.  
-    **Renomear uma exibição**: use a ação **Renomear** para alterar o nome da exibição pessoal atualmente realçada. Essa ação está desativada para exibições bloqueadas. 
-    **Excluir uma exibição**: use a ação **Remover** para excluir permanentemente a exibição realçada da página. Não há como recuperar uma exibição depois de removê-la.  

Quaisquer alterações feitas nessa caixa de diálogo entrarão em vigor após você selecionar o botão **Salvar**.

## <a name="managing-personalizations-at-an-organizational-level-with-views"></a>Gerenciamento de personalizações em nível organizacional com exibições
Para entender as melhorias no gerenciamento de personalizações em nível organizacional, vamos analisar primeiro como o gerenciamento da personalização funcionou antes das exibições.  

Sem exibições, os administradores aplicariam um conjunto de personalizações para uma página a um usuário, grupo de usuários ou usuários usando o formulário Personalização. Se esses usuários tivessem direitos de personalização, as personalizações seriam aplicadas a essa página. Contudo, não era possível impedir que os usuários personalizassem ainda mais a página, o que significava que a organização não podia garantir que seus usuários tivessem uma interface de usuário consistente. Se algum desses usuários não tiver direitos de personalização, as personalizações dadas a eles por um administrador não serão carregadas. Além disso, se novos usuários fossem contratados em uma organização, os administradores precisavam carregar manualmente um conjunto de personalizações para o usuário. Não havia mecanismo automático para especificar que um determinado conjunto de personalizações deveria estar disponível para esse usuário.

Com o recurso de exibições salvas, o gerenciamento organizacional de personalizações é significativamente mais fácil, principalmente em decorrência da capacidade de publicar exibições para funções de segurança. Depois que uma exibição for publicada, qualquer usuário com essa função poderá acessar e usar a exibição, independentemente da capacidade de personalização do usuário. Embora cada usuário tenha uma cópia da exibição publicada na qual o uso da página (personalizações implícitas) é aplicado automaticamente, nenhum usuário pode salvar personalizações explícitas ou exibições na consulta para a exibição publicada (o que significa que as exibições publicadas estão bloqueadas). Além disso, se novos usuários receberem uma função para a qual a exibição foi publicada, eles verão automaticamente as exibições associadas a suas funções sem qualquer ação do administrador. Da mesma forma, se um usuário alterar funções em uma organização, as exibições associadas à sua função antiga não estarão mais acessíveis a elas, novamente sem qualquer ação do administrador. As atualizações de uma exibição publicada podem ser facilmente distribuídas aos usuários, republicando a exibição para as funções de segurança apropriadas.

O recurso de publicação permite que as organizações definam exibições padrão corporativas otimizadas para seus negócios, direcionadas a usuários em funções de segurança específicas.  

## <a name="publishing-views"></a>Publicação de exibições
Durante o processo de publicação, as exibições podem ser atribuídas a uma ou mais funções de segurança, o que significa que qualquer usuário com essa função poderá acessar e usar essa exibição, embora não possa editar a exibição. Atualmente, somente os administradores do sistema têm direitos para a ação **Publicar** no menu suspenso do seletor de exibição.  

Para publicar uma exibição, siga estas etapas: 
1.  Crie e salve uma cópia pessoal da exibição que você deseja publicar. 
2.  Com essa exibição atualmente carregada, selecione o nome da exibição para abrir o menu suspenso do seletor de exibição. 
3.  Selecione o botão **Mais** e depois selecione **Publicar**. A caixa de diálogo Publicar será aberta.  
4.  Forneça um nome e (opcionalmente) uma descrição para a exibição. Trata-se do nome que os usuários que recebem essa exibição verão em seus seletores de exibição. Observe que nenhum nome duplicado para exibições publicadas é permitido para uma página, mesmo se a lista de funções às quais eles são aplicados diferir.  
5.  Adicione qualquer função de segurança que corresponda aos usuários que receberão essa exibição.  
6.  Selecione **Publicar**.

Observe que, em alguns ambientes, pode levar algum tempo (até uma hora) para que os usuários vejam a exibição publicada.

## <a name="modifying-a-published-view"></a>Modificação de uma exibição publicada
Depois de publicar uma exibição, você pode descobrir que deseja fazer alterações em uma exibição publicada. Embora não seja possível fazer alterações ao vivo em uma exibição publicada, como essas exibições estão bloqueadas para edição para todos os usuários (incluindo editores), você pode publicar novamente uma exibição para fazer atualizações.  

Se as alterações que você deseja fazer em uma exibição publicada envolverem apenas os parâmetros de publicação (o nome e a descrição da exibição ou as funções de segurança nas quais a exibição é publicada), faça o seguinte: 
1.  Alterne para a exibição publicada dos parâmetros que você deseja atualizar. 
2.  Selecione **Publicar** no menu suspenso do seletor de exibição. 
3.  Selecione **Sim** se você quiser atualizar a exibição existente (ou **Não** se você quiser publicá-la com um nome diferente).
4.  Atualize o nome, descrição e/ou funções de segurança para a exibição. 
5.  Selecione **Publicar**. 
6.  Se atualizou o nome da exibição publicada, você também precisará excluir a exibição publicada com o nome antigo (consulte a seção **Gerenciamento de exibições publicadas** para obter mais detalhes). 

Se as alterações na exibição publicada envolverem modificações nas personalizações ou nos filtros associados à exibição, siga estas etapas: 
1.  Alterne para a exibição publicada que você deseja modificar. 
2.  Salve uma cópia da exibição publicada para criar um rascunho local da exibição publicada. 
3.  Modifique o rascunho local com as alterações necessárias.
4.  Publique a exibição com o nome original. 

## <a name="managing-published-views"></a>Gerenciamento de exibições publicadas
Como o gerenciamento de exibições pessoais, a caixa de diálogo **Gerenciar minhas exibições** oferece aos usuários com privilégios de publicação os recursos básicos de manutenção das exibições publicadas dessa página (além de suas próprias exibições pessoais). Para abrir essa página, selecione o nome da exibição para abrir o menu suspenso do seletor de exibição, selecione **Mais** e depois selecione **Gerenciar minhas exibições**.

Enquanto todos os usuários veem uma guia **Minhas exibições** mostrando suas exibições pessoais, os usuários com privilégios de publicação também verão uma guia **Publicado** que mostra todas as exibições publicadas dessa página. Como pode haver vários usuários publicando exibições, é importante poder gerenciar a lista completa de exibições publicadas, independentemente de você ser o usuário que realmente publicou a exibição.

Para a lista de todas as exibições publicadas da página, o seguinte conjunto de ações está disponível. 

-    **Publicar**: use a ação **Publicar** para publicar novamente uma exibição com parâmetros de publicação modificados (nome, descrição, funções de segurança).  
-    **Remover**: use a ação **Remover** para excluir permanentemente uma exibição publicada. Essa ação remove a exibição de todos os usuários no sistema.  
 
Quaisquer alterações feitas nessa caixa de diálogo entrarão em vigor depois que o botão **Salvar** for selecionado.

## <a name="frequently-asked-questions"></a>Perguntas frequentes
### <a name="how-do-i-enable-saved-views-in-my-environment"></a>Como faço para habilitar as exibições salvas no meu ambiente? 
Para habilitar as exibições salvas, o administrador do sistema deve fazer o seguinte: 
1.  Vá para a página **Personalização** usando a pesquisa de navegação. 
2.  Selecione a guia **Configurações**.
3.  Defina a opção **Habilitar exibições salvas** como **Sim**.

Depois que esse recurso for habilitado, todas as sessões de usuário subsequentes serão iniciadas com as exibições habilitadas.  

Observe que, se a personalização estiver desativada para o ambiente, as exibições serão habilitadas mesmo se você seguir as etapas acima. Isso ocorre porque o recurso de exibições é baseado no subsistema de personalização.

### <a name="what-happens-to-existing-personalizations-when-views-are-enabled"></a>O que acontece com as personalizações existentes quando as exibições estão habilitadas? 
Quando as exibições estão habilitadas, todas as personalizações existentes para um usuário e formulário são salvas em uma nova exibição chamada **Minha exibição**, que é automaticamente definida como a exibição padrão. Isso serve para garantir que haja uma experiência de usuário consistente antes e depois de as exibições serem habilitadas, exceto pelo controle do seletor de exibição que aparece nos formulários.  

### <a name="what-pages-support-views"></a>Quais páginas oferecem suporte a exibições? 
As exibições estão disponíveis na maioria das páginas, mas não no Finance and Operations. Especificamente, as exibições estão atualmente disponíveis em todas as páginas de tela inteira, exceto nos painéis e espaços de trabalho. As páginas que não são de tela inteira, que incluem caixas de diálogo, diálogos suspensos, pesquisas, visualizações avançadas, também não oferecem suporte a exibições no momento. O suporte de exibição para tipos de página adicionais, como espaços de trabalho e caixas de diálogo, pode ser considerado para uma atualização futura.   

### <a name="who-is-allowed-to-publish-views"></a>Quem tem permissão para publicar exibições?
Atualmente, os administradores do sistema são os únicos usuários que têm direitos para publicar exibições.  Uma nova função de segurança é planejada, o que forneceria aos clientes mais flexibilidade para quem pode publicar.  

### <a name="why-am-i-not-able-to-save-filters-with-this-view"></a>Por que não consigo salvar filtros com essa exibição? 
Existem alguns motivos pelos quais um filtro pode não aparecer para salvar com uma exibição: 

- Pode ser que a página não permita salvar filtros como parte da definição de exibição. Observe que apenas as páginas com grandes seletores de exibição permitem que as personalizações e as modificações de consulta sejam salvas como uma exibição. Consulte a seção "Alternância de exibições" para obter mais informações. 

- Se a exibição for a exibição padrão e o caminho de navegação até a página incluir uma consulta, a consulta da exibição pode não ser aplicada inicialmente. Os dois cenários principais para isso são: 
     - Se você navegar até uma página de um bloco, a consulta do bloco será executada independentemente da consulta associada à exibição padrão. 
     - Se você navegar até uma página e esse ponto de entrada incluir uma consulta, a consulta original será executada originalmente no lugar da consulta da exibição padrão. 
     
  Você deve ser alertado quando essas situações ocorrerem por uma mensagem informativa quando a exibição estiver sendo carregada. Você também pode confirmar alternando para essa exibição após o carregamento da página, já que isso deve permitir que a consulta da exibição seja executada independentemente.  

- A página em questão pode não oferecer suporte adequado às exibições, pois ela pode ignorar completamente a consulta da exibição. Relate quaisquer casos por meio do mecanismo **Comentários**. Para chegar à página de comentários, clique em **Ajuda e suporte** e depois **Comentários**.  
