---
title: Exibições salvas
description: Este tópico descreve como usar os recursos de exibições salvas.
author: jasongre
manager: AnnBe
ms.date: 04/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: Platform update 28
ms.openlocfilehash: fe79558b9d2ac4ef1c83918b949d11983b2cc0d8
ms.sourcegitcommit: cd8a28be0acf31c547db1b8f6703dd4b0f62940c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2020
ms.locfileid: "3260474"
---
# <a name="saved-views"></a>Exibições salvas

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="introduction"></a>Introdução
A personalização desempenha um papel importante ao permitir que usuários e organizações otimizem a experiência do usuário para atender às suas necessidades. Para obter mais detalhes sobre personalização, consulte [Personalizar a experiência do usuário](personalize-user-experience.md).

Com a personalização tradicional, os usuários só poderiam ter um único conjunto de personalizações por formulário. As exibições salvas expandem a personalização de várias maneiras importantes:

-    As exibições permitem que os usuários tenham vários conjuntos nomeados de personalizações por formulário, que podem alternar rapidamente conforme necessário. Isso permite que um usuário crie várias exibições otimizadas de uma página, em que cada exibição foi adaptada para atender às necessidades de execução de uma determinada tarefa comercial. 

-    As exibições criadas para determinados tipos de página também podem incluir filtros ou classificações adicionados pelo usuário, o que permite que os usuários retornem rapidamente a conjuntos de dados filtrados comumente. Consulte a seção [Quais páginas oferecem suporte a exibições](saved-views.md#what-pages-support-views) para obter mais detalhes. 

-    As exibições podem ser publicadas para usuários em funções de segurança específicas e entidades legais específicas. Portanto, todos os usuários com uma função especificada e com acesso a uma entidade legal especificada podem acessar e usar essa visualização, mesmo se não puderem personalizá-la. Esse recurso de publicação permite que as organizações definam exibições padrão corporativas otimizadas para seus negócios. Para obter mais informações, consulte a seção [Gerenciar personalizações no nível organizacional com exibições](saved-views.md#managing-personalizations-at-an-organizational-level-with-views).

-    Diferentemente da personalização tradicional, as exibições não são salvas automaticamente quando um usuário executa personalizações explícitas ou filtra uma lista. São necessários salvamentos explícitos para fornecer flexibilidade na criação de uma exibição antes ou após as alterações associadas a essa exibição e para garantir que as definições de exibição não sejam alteradas de forma não intencional por filtros ou personalizações que não são destinadas a uso de longo prazo.  

-    As exibições podem ser adicionadas a espaços de trabalho, como blocos, listas ou links. Portanto, um conjunto de dados filtrados pode ser exibido em um espaço de trabalho e os usuários podem associar um conjunto de personalizações relevantes para esse conjunto de dados ao bloco ou ao link.

## <a name="switching-between-views"></a>Alternância entre exibições
Após as exibições terem sido habilitadas para um ambiente, qualquer página que oferece suporte a exibições incluirá um controle de seletor de exibição recolhido na parte superior do formulário que mostra o nome da exibição atual.  

Existem duas variações de tamanho para o seletor de exibição: 

-   **Grandes seletores de exibição**: as páginas que apresentam de forma proeminente uma lista terão um seletor de exibição maior por alguns motivos. O mais importante é que o seletor de exibição maior indica as páginas em que a exibição pode incluir filtros definidos pelo usuário. Como os filtros são incluídos nas exibições, o tamanho de seletor maior também é garantido, pois os nomes de exibição geralmente serão a melhor descrição dos dados mostrados na tela, e a expectativa é a de que os usuários alternem entre as exibições com mais frequência nesses tipos de página.  
 
-   **Seletores de exibição pequenos**: todos os outros formulários de página inteira (com a exceção de espaços de trabalho e o painel) têm um seletor de exibição menor que aparece ao lado da legenda da página. As exibições nessas páginas incluem apenas personalizações (e não filtros definidos pelo usuário). Nessas páginas, a legenda do formulário ou o título do registro geralmente é a informação mais importante na parte superior do formulário. O tamanho menor também reflete uma frequência mais baixa esperada de alternância de exibição nessas páginas. 
 
Se você clicar no nome da exibição, o seletor de exibição será aberto e mostrará a lista de exibições disponíveis dessa página.

-    **Exibição padrão**: a exibição **Padrão** (anteriormente conhecida como exibição **Clássica**) é a exibição avançada da página, na qual nenhuma personalização explícita é aplicada.
-    **Exibições pessoais**: as exibições sem cadeados representam suas exibições pessoais. São exibições que você criou ou que um administrador forneceu a você.  
-    **Exibições bloqueadas**: algumas exibições (como a exibição **Padrão** e todas as exibições publicadas na sua função) têm um símbolo de cadeado ao lado no seletor de exibição. Este símbolo indica que não é possível editar essas exibições. No entanto, as personalizações implícitas que refletem o uso da página são salvas automaticamente. Essas personalizações implícitas incluem uma alteração na largura de uma coluna de grade, ou a ação de expandir ou recolher uma Guia Rápida. Entretanto, se você tiver privilégios de personalização, você pode usar a ação **Salvar como** para criar uma exibição pessoal baseada em uma exibição bloqueada.
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
     1.    Selecione **Salvar como**. 
     2.    Insira um nome e (opcionalmente) uma descrição para a exibição.
     3.    Selecione **Salvar**.

## <a name="changing-the-default-view"></a>Alteração da exibição padrão
A exibição padrão é aquela que o sistema tentará abrir quando você navegar pela primeira vez até a página. Você deve defini-la como a exibição que você espera usar com mais frequência.  

Para alterar a exibição padrão de uma página, siga estas etapas: 
1.  Alterne para a exibição que você usa como padrão. 
2.  Selecione o nome da exibição para abrir o seletor de exibição. 
3.  Selecione **Mais** e depois **Fixar como padrão**.  

Como alternativa, ao criar uma exibição (ao usar a ação **Salvar como**), você pode tornar essa nova exibição a exibição padrão, definindo a opção **Fixar como padrão** antes de salvar a exibição.

Observe que, em alguns casos, a consulta associada à exibição padrão não é executada quando você navega pela primeira vez até uma página. Por exemplo, se você navegar por um bloco até uma página, a consulta do bloco será executada, independentemente da consulta associada à exibição padrão. Além disso, se você navegar até uma página com exibição Padrão que já tenha uma consulta definida, a consulta original será executada originalmente no lugar da consulta da exibição padrão. Quando isso acontecer, você será alertado por uma mensagem informativa quando a exibição estiver sendo carregada. A alternância de exibições depois que a página foi carregada deve permitir que a consulta de exibição seja executada conforme o esperado. Iniciando na versão 10.0.10 da atualização de plataforma 34, a mensagem informativa terá uma ação incorporada que permite carregar diretamente a consulta do modo de exibição padrão.

## <a name="managing-personal-views"></a>Gerenciamento de exibições pessoais 
A caixa de diálogo **Gerenciar minhas exibições** oferece recursos básicos de manutenção sobre suas exibições pessoais e a ordem das exibições no seletor de exibição. Para abrir essa página, clique no nome da exibição para abrir o menu suspenso do seletor de exibição, selecione **Mais** e depois selecione **Gerenciar minhas exibições**.  

Para obter uma lista de exibições disponíveis dessa página, o conjunto de ações a seguir está disponível.  
-    **Alterar a exibição padrão**: use a ação **Fixar como padrão** action para tornar a exibição atualmente destacada a exibição padrão dessa página.  
-    **Reordenar suas exibições**: use as ações **Mover para cima** e **Mover para baixo** para reorganizar suas exibições em uma ordem específica.  
-    **Renomear uma exibição**: use a ação **Renomear** para alterar o nome da exibição pessoal atualmente realçada. Essa ação está desativada para exibições bloqueadas. 
-    **Excluir uma exibição**: use a ação **Remover** para excluir permanentemente a exibição realçada da página. Não há como recuperar uma exibição depois de removê-la.  

Quaisquer alterações feitas nessa caixa de diálogo entrarão em vigor após você selecionar o botão **Salvar**.

## <a name="managing-personalizations-at-an-organizational-level-with-views"></a>Gerenciamento de personalizações em nível organizacional com exibições
Para ajudar você a entender como melhorar o gerenciamento de personalizações no nível organizacional, esta seção descreve algumas diferenças no gerenciamento de personalização com e sem o recurso de exibições salvas.

Sem exibições, os administradores aplicariam um conjunto de personalizações para uma página a um usuário ou um grupo de usuários usando a página Personalização. Se esses usuários tivessem direitos de personalização, as personalizações seriam aplicadas a essa página. Contudo, não era possível impedir que os usuários personalizassem ainda mais a página, o que significava que a organização não podia garantir que seus usuários tivessem uma interface de usuário consistente. Se algum desses usuários não tiver direitos de personalização, as personalizações dadas a eles por um administrador não serão carregadas. Além disso, se novos usuários fossem contratados em uma organização, os administradores precisavam carregar manualmente um conjunto de personalizações para o usuário. Não havia mecanismo automático para especificar que um determinado conjunto de personalizações deveria estar disponível para usuários nessa função.

O recurso de exibições salvas torna o gerenciamento organizacional de personalizações significativamente mais fácil, porque as visualizações podem ser publicadas para grupos de usuários. Depois de publicar uma exibição, todos os usuários que tiverem uma das funções de segurança definida e tiverem acesso a uma das entidades legais especificadas poderão visualizar e usar a exibição, mesmo se esses usuários não puderem personalizá-la. Embora cada usuário tenha uma cópia da exibição publicada na qual o uso da página (personalizações implícitas) é aplicado automaticamente, nenhum usuário pode salvar personalizações explícitas ou atualizações na consulta para uma exibição publicada. Em outras palavras, as exibições publicadas estão bloqueadas. Além disso, se novos usuários receberem funções em entidades legais nas quais as exibições são publicadas, eles automaticamente visualizarão as exibições associadas às suas funções e às entidades legais. O administrador não precisa executar ações adicionais. Da mesma forma, se os usuários trocarem de funções em uma organização ou receberem acesso a diferentes entidades legais, eles podem não ter mais acesso às exibições anteriormente publicadas para eles. Novamente, o administrador não precisa executar ações adicionais.

As atualizações de uma exibição publicada podem ser facilmente distribuídas aos usuários, republicando a exibição para as funções de segurança e entidades legais apropriadas.

O recurso de publicação permite que as organizações definam exibições padrão corporativas otimizadas para seus negócios, direcionadas a usuários em funções de segurança específicas.  

## <a name="publishing-views"></a>Publicação de exibições
Durante o processo de publicação, as exibições podem ser atribuídas a uma ou mais funções de segurança ou entidades legais. Portanto, todos os usuários com acesso a uma entidade legal atribuída a uma dessas funções podem acessar e usar as exibições, embora não possam editá-las. Os administradores do sistema têm acesso à ação **Publicar** no menu suspenso do seletor de exibição. No entanto, outros usuários confiáveis em sua organização também podem receber acesso para visualizar a publicação através da nova função **Administrador de exibições salvas**.

Para publicar uma exibição, siga estas etapas: 
1.  Crie e salve uma cópia pessoal da exibição que você deseja publicar. 
2.  Com essa exibição atualmente carregada, selecione o nome da exibição para abrir o menu suspenso do seletor de exibição. 
3.  Selecione o botão **Mais** e depois selecione **Publicar**. A caixa de diálogo Publicar será aberta.  
4.  Insira um nome e (opcionalmente) uma descrição para a exibição. O nome inserido é o nome que os usuários que recebem essa exibição visualizarão em seus seletores de exibição. Os nomes das exibições publicadas em uma página devem ser exclusivos. Nenhum nome duplicado é permitido, mesmo se a lista de funções ou de entidades legais à qual as exibições são aplicadas diferir.
5.  Adicione as funções de segurança que correspondem aos usuários que receberão essa exibição.
6. Adicione as entidades legais para as quais essa exibição deve estar disponível. 
7. [10.0.9/Atualização de plataforma 33 ou mais recente] Determine se a exibição deve ser publicada como padrão para os usuários selecionados. Definir uma exibição como padrão significa que esta é a exibição que os usuários visualizarão na próxima vez em que abrirem a página de destino. Isto modificará a exibição padrão para esses usuários. No entanto, os usuários ainda podem alterar a exibição padrão após a publicação.    
8.  Selecione **Publicar**.

Observe que, em alguns ambientes, pode levar algum tempo (até uma hora) para que os usuários vejam a exibição publicada.

## <a name="modifying-a-published-view"></a>Modificação de uma exibição publicada
Depois de publicar uma exibição, você pode descobrir que deseja fazer alterações em uma exibição publicada. Embora não seja possível fazer alterações ao vivo em uma exibição publicada, como essas exibições estão bloqueadas para edição para todos os usuários (incluindo editores), você pode publicar novamente uma exibição para fazer atualizações.  

Se as alterações que você deseja fazer em uma exibição publicada envolverem apenas os parâmetros de publicação (o nome e a descrição da exibição ou as funções de segurança nas quais a exibição é publicada), faça o seguinte: 
1.  Alterne para a exibição publicada dos parâmetros que você deseja atualizar. 
2.  Selecione **Publicar** no menu suspenso do seletor de exibição. 
3.  Selecione **Sim** se você quiser atualizar a exibição existente (ou **Não** se você quiser publicá-la com um nome diferente).
4.  Atualize o nome, descrição e/ou funções de segurança para a exibição. 
5.  Selecione **Publicar**. 
6.  [10.0.8/Atualização de plataforma 32 ou anterior] Se atualizou o nome da exibição publicada, você também precisará excluir a exibição publicada com o nome antigo (consulte a seção **Gerenciamento de exibições publicadas** para obter mais detalhes). 
7. [10.0.9/Atualização de plataforma 33 ou mais recente] Se tivesse escolhido anteriormente esta exibição publicada como padrão, ela seria a exibição padrão para esses usuários novamente após a nova publicação.  

Se as alterações na exibição publicada envolverem modificações nas personalizações ou nos filtros associados à exibição, siga estas etapas: 
1.  Alterne para a exibição publicada que você deseja modificar. 
2.  Salve uma cópia da exibição publicada para criar um rascunho local da exibição publicada. 
3.  Modifique o rascunho local com as alterações necessárias.
4.  Publique a exibição com o nome original. 

## <a name="managing-published-views"></a>Gerenciamento de exibições publicadas
Como o gerenciamento de exibições pessoais, a caixa de diálogo **Gerenciar minhas exibições** oferece aos usuários com privilégios de publicação os recursos básicos de manutenção das exibições publicadas dessa página (além de suas próprias exibições pessoais). Para abrir essa página, selecione o nome da exibição para abrir o menu suspenso do seletor de exibição, selecione **Mais** e depois selecione **Gerenciar minhas exibições**.

Enquanto todos os usuários veem uma guia **Minhas exibições** mostrando suas exibições pessoais, os usuários com privilégios de publicação também verão uma guia **Publicado** que mostra todas as exibições publicadas dessa página. Como pode haver vários usuários publicando exibições, é importante poder gerenciar a lista completa de exibições publicadas, independentemente de você ser o usuário que realmente publicou a exibição.

Para a lista de todas as exibições publicadas da página, o seguinte conjunto de ações está disponível. 

-    **Publicar**: use a ação **Publicar** para publicar novamente uma exibição após os parâmetros de publicação (nome, descrição, funções de segurança ou entidades legais) terem sido alterados.
-    **Remover**: use a ação **Remover** para excluir permanentemente uma exibição publicada. Essa ação remove a exibição de todos os usuários no sistema. A remoção de exibições publicadas será efetivada após selecionar o botão **Salvar**.

## <a name="frequently-asked-questions"></a>Perguntas frequentes
### <a name="how-do-i-enable-saved-views-in-my-environment"></a>Como faço para habilitar as exibições salvas no meu ambiente? 
Observação: O recurso **Exibições salvas** exige que o sistema de Personalização em Finance and Operations esteja habilitado. Se a personalização estiver desativada para todo o ambiente, as exibições serão desabilitadas mesmo se você seguir as etapas abaixo. 

**10.0.9 / Atualização de plataforma 33 e mais recente** O recurso **Exibições salvas** está disponível diretamente no Gerenciamento de recursos em todos os ambientes. Assim como outros recursos de versão prévia pública, a ativação deste recurso na produção está sujeita ao [Contrato de Termos de Uso Complementares](https://go.microsoft.com/fwlink/?linkid=2105274).  

**10.0.8 / Atualização de plataforma 32 e anterior** O recurso **Exibições salvas** pode ser habilitado nos ambientes da Camada 1 (Desenvolvimento/Teste) e da Camada 2 (Área Restrita) a fim de fornecer testes adicionais e alterações de design seguindo as etapas abaixo.

1.  **Habilitar a versão de pré-lançamento**: execute esta instrução SQL: 

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, enabled, FLIGHTSERVICEID, PARTITION) VALUES('CLISavedViewsEnableFeature', 1, 0, 5637144576);`

2. **Redefinir o IIS** para liberar o cachê de liberação estático. 

3.  **Localizar o recurso**: navegue até o espaço de trabalho **Gerenciamento de recursos**. Se **Exibições salvas** não aparecer na lista, selecione **Verificar se há atualizações**.   

4.  **Habilitar o recurso**: localize o recurso **Exibições salvas** na lista de recursos e selecione **Habilitar agora** no painel de detalhes.

Todas as sessões de usuário subsequentes começarão com exibições salvas habilitadas.


### <a name="what-happens-to-existing-personalizations-when-views-are-enabled"></a>O que acontece com as personalizações existentes quando as exibições estão habilitadas? 
Quando as exibições estão habilitadas, todas as personalizações existentes para um usuário e formulário são salvas em uma nova exibição chamada **Minha exibição**, que é automaticamente definida como a exibição padrão. Isso serve para garantir que haja uma experiência de usuário consistente antes e depois de as exibições serem habilitadas, exceto pelo controle do seletor de exibição que aparece nos formulários.  

### <a name="what-pages-support-views"></a>Quais páginas oferecem suporte a exibições? 
As exibições estão disponíveis na maioria, mas não em todas as páginas. Especificamente, as exibições estão atualmente disponíveis em todas as páginas de tela inteira, exceto nos painéis e espaços de trabalho. As páginas que não são de tela inteira, que incluem caixas de diálogo, diálogos suspensos, pesquisas, visualizações avançadas, não oferecem suporte a exibições no momento. O suporte de exibição para tipos de página adicionais, como espaços de trabalho e caixas de diálogo, pode ser considerado para uma atualização futura.   

### <a name="who-is-allowed-to-publish-views"></a>Quem tem permissão para publicar exibições?
Somente administradores de sistema e usuários que foram atribuídos à função de **Administrador de exibições salvas** têm direitos de publicar exibições. 

### <a name="why-am-i-not-able-to-save-filters-with-this-view"></a>Por que não consigo salvar filtros com essa exibição? 
Existem alguns motivos pelos quais um filtro pode não aparecer para salvar com uma exibição: 

- Pode ser que a página não permita salvar filtros como parte da definição de exibição. Observe que apenas as páginas com grandes seletores de exibição permitem que as personalizações e as modificações de consulta sejam salvas como uma exibição. Consulte a seção **Alternância de exibições** para obter mais informações. 

- A página em questão pode não dar o suporte correto às exibições, já que pode pode ignorar completamente a consulta ou operar em uma tabela temporária cujos dados não sejam persistentes. 

### <a name="what-data-will-i-see-when-i-visit-a-page"></a>Quais dados veremos quando eu acessar uma página? 
Para as páginas com seletores de exibição pequenos (somente as personalizações podem ser salvas na exibição), você sempre verá os mesmos dados que tem visto ao acessar a página. 

Para as páginas com seletores de exibição grandes (personalizações e consultas podem ser salvas na exibição), você verá principalmente os dados vinculados à consulta associada à exibição padrão. Há duas exceções principais: – Se você navegar até uma página de um bloco, a consulta do bloco será executada independentemente da consulta associada à exibição padrão. Se você criou esse bloco após habilitar as exibições, selecionar um bloco abrirá a página com a exibição associada a ele.   
     - Se você navegar até uma página e esse ponto de entrada incluir uma consulta, a consulta original será executada originalmente no lugar da consulta da exibição padrão. Quando isso acontecer, você será alertado por uma mensagem informativa quando a exibição estiver sendo carregada. Você também pode confirmar alternando para essa exibição após o carregamento da página, já que isso deve permitir que a consulta da exibição seja executada independentemente.  


