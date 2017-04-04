---
title: "Visão geral da ajuda"
description: "Este artigo fornece uma visão geral dos componentes do sistema de ajuda do Microsoft Dynamics 365 for Operations. Também explica como você pode fornecer a documentação personalizada e treinamento a sua organização."
author: margoc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16381
ms.assetid: 018c148c-9cbd-41e0-8186-d75dbf66288f
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 240060606c8a2955c3f0a0d47fb25b0cde64c187
ms.lasthandoff: 03/31/2017


---

# <a name="help-overview"></a>Visão geral da ajuda

Este artigo fornece uma visão geral dos componentes do sistema de ajuda do Microsoft Dynamics 365 for Operations. Também explica como você pode fornecer a documentação personalizada e treinamento a sua organização. 

Dynamics 365 for Operations inclui um sistema de Ajuda totalmente novo que é baseado em dois componentes principais:

-   Um site da documentação
-   Guias de tarefas

Você pode acessar os e artigos obrigar guias do painel da ajuda em dynamics 365 para operações conforme mostrado na captura de tela. [painel da ajuda do![(]. /media/help-pane-ops-task-guides-1024x741.png)](. Este artigo de /media/help-pane-ops-task-guides.png) descreve o sistema de ajuda, e explica como criar documentação personalizado e recursos de treinamento para sua organização.

## <a name="help-on-docsmicrosoftcom"></a>Ajuda em docs.microsoft.com
Site em docs.microsoft.com docs.microsoft.com/dynamics365/operations ([] (https://docs.microsoft.com/en-us/dynamics365/#pivot=solutions&panel=solutions_operations) é a fonte principal de documentos de produtos para dynamics 365 para as operações. Site oferece os seguintes recursos:

-   ** O acesso ao conteúdo mais atualizado ** – o local dá-nos modo mais rápido e mais flexível de criar, entregar e atualizar, a documentação do produto. Portanto, ajuda a garantir que você tenha acesso às informações técnicas mais recentes.
-    ** Satisfaça gravado em por especialistas ** – o mais fornece um conjunto de documentação do rich produto que pode ser aprimorado por membros da Comunidade seguir em como fora Microsoft.
-   ** Acesso a diferentes tipos de conteúdo ** – o site permite acessar rapidamente diferentes tipos de informações sobre o dynamics 365 para operações, como mostra combinados Microsoft Office, guias da tarefa, exibe, e artigos de wiki.
-    ** Satisfaça suporta que seus processos empresariais ** – o local - inclui conteúdo focado aproveita negócios que se do Modelador de processo de negócios (BPM) em serviços (LCS) do Microsoft Dynamics lifecycle.

Nós migramos qualquer conteúdo de nosso wiki anterior da ajuda docs. Nós somos muito entusiasmados sobre nossa novo site e esperamos que você será muito.

### <a name="when-can-we-use-it"></a>Quando poderemos usá-la?

Você pode ler o conteúdo em docs agora -- é totalmente público e pesquisável sem exigir o logon. Você pode utilizar qualquer uma das suas ferramentas de pesquisa favoritas para encontrar conteúdo. Você pode comentar em artigos o site se você escolher, conectando com uma conta de GitHub.


## <a name="task-guides"></a>Guias de tarefas
Uma guia de tarefas é uma experiência o realizar por etapas de uma tarefa, um processo comercial, controlado guiado, interativo. Você pode abrir (jogo) tarefa uma guia do painel da ajuda. Quando você clica primeiro uma guia da tarefa, o painel da ajuda mostrará as instruções passo a passo para a tarefa. As guias da tarefa são agora disponíveis. [guia de![tarefa exibição de leitura (]. /media/task-guide-ops-1024x742.png)](. /media/task-guide-ops.png) Comece a experiência guiada, interativo, clique ** inicie guia ** de tarefa na parte inferior do painel da ajuda. Um ponteiro preto abre e indica a ação que você precisa executar. Siga as direções que aparecem na UI, e insira os dados conforme instruído. [instrução da etapa de guia de![tarefa (]. /media/task-guide-step-1-ops.png)](. /media/task-guide-step-1-ops.png) ** importante: ** Os dados inseridos quando você executa uma guia da tarefa são reais. Se você estiver em um ambiente de produção, os dados serão inseridos na empresa que você está usando atualmente.

### <a name="it-all-begins-with-task-recorder"></a>Tudo começa com o Gravador de Tarefas

Guias de tarefas são criados usando o Gravador de Tarefas. Quando você utiliza o Gravador de Tarefas, todas as ações que você realiza na IU do Dynamics 365 for Operations (como clicar em menus, alterar configurações, e inserir dados) são registradas. As etapas que você registra são chamadas coletivamente de gravação de tarefa. Como explicamos na seção anterior, as gravações de tarefas podem ser exibidas no painel de Ajuda e executadas como guias de tarefas. No entanto, existem outras maneiras de utilizar gravações de tarefas:

-   **Salvar gravações de tarefas ao BPM** – Você pode salvar uma gravação de tarefa à uma linha de uma hierarquia em uma biblioteca do BPM em LCS. Quando você salva uma gravação de tarefa ao BPM, um fluxograma é gerado e exibido, junto com as etapas da gravação. **Observação:** Para exibir uma gravação de tarefa no painel de Ajuda do Dynamics 365 for Operations e executá-la como um guia de tarefa, você deve salvar a gravação à uma biblioteca do BPM.
-   **Salvar gravações de tarefa como documentos Word** – Ao salvar uma gravação de tarefa como um documento Microsoft Word, você pode facilmente produzir guias de treinamento imprimíveis para sua organização.

Para obter mais informações sobre o task recorder, consulte [task recorder em dynamics 365] (para operações. /user-interface/task-recorder.md).

### <a name="creating-customized-task-recordings"></a>Criando gravações de tarefas personalizadas

Você pode criar suas próprias gravações de tarefas, ou você pode baixar e personalizar gravações de tarefas que a Microsoft oferece. Consequentemente, você pode criar Ajuda personalizada para sua organização que reflete sua implementação específica do Dynamics 365 for Operations. Para exibir uma tarefa que registra em dynamics 365 para operações ajudar o painel e fazê-lo como um guia de tarefa, você terá que salvar o registro em uma biblioteca de BPM em LCS. Se você for um parceiro, e você eleva uma biblioteca em uma biblioteca corporativo e inclui a uma solução, estará disponível para os clientes. Para obter instruções completas, consulte usando registros [de tarefa para a criar documentação ou] (instrução. /user-interface/task-recorder.md).

## <a name="in-product-help"></a>Ajuda sobre produto
Para acessar o conteúdo da ajuda dentro do 365 para operações, ou clicar ** ajuda ** ** (? ** o ícone) e escolhe a ajuda ou pressione Ctrl+Shift+?. Em ambos os casos, o painel de Ajuda abre. O painel da ajuda, você poderá acessar ou artigos obrigar guias. [![](./media/help-pane-wiki-1024x684.png)](./media/help-pane-wiki.png)

### <a name="accessing-articles-from-the-help-pane"></a>Acessando artigos o painel da ajuda

O painel da ajuda, é possível acessar os itens aplicáveis o dynamics 365 para o cliente de operações. Quando você abre primeiro o painel da ajuda e clica ** Wiki ** guia, verá os itens que se aplicam a página que é atualmente sobre em dynamics 365 para as operações. Se um item for encontrado, você poderá inserir palavra-chave para refinar a pesquisa. Quando você clica em um item no painel da ajuda, um novo guia abre no navegador e exibe o item. 

### <a name="accessing-task-guides-from-the-help-pane"></a>Acessando tarefa guias do painel da ajuda

Para poder acessar tarefa guias do painel da ajuda, um administrador do sistema precisa para funcionar ** parâmetros de sistema ** pagina em dynamics 365 para operações e configurar algumas configurações. **Observações:**

-   Para configurar a Ajuda, você precisa estar conectado com uma conta do inquilino mesmo como o locatário em que Dynamics 365 for Operations é implantado.
-   Não é possível conectar-se a uma biblioteca de LCS de uma instância do Dynamics 365 for Operations em execução em uma unidade de disco rígida virtual local (VHD).

[os parâmetros do sistema![com as configurações da ajuda (]. /media/system-parameters_ops-1024x437.png)](. /media/system-parameters_ops.png) ** ** Parâmetros do sistema na página, acompanham estas etapas:

1.  **Importante: **A primeira vez que você abrir a guia da ajuda, é necessário conectar serviços do ciclo de vida. Verifique no link no meio do formulário, a conexão espere, feche a caixa de diálogo, clique em OK para obter os parâmetros o formulário. [conectar ao![(LCS]. /media/connect-to-lcs-crop-1024x365.png)](. /media/connect-to-lcs-crop.png)
2.  Selecione o projeto do Lifecycle Services para se conectar.
3.  Selecione as bibliotecas do BPM (dentro do projeto selecionado) para recuperar gravações de tarefas delas.
4.  Defina a ordem de exibição das bibliotecas do BPM. Isso determina a ordem em que as gravações de tarefas das bibliotecas irão aparecer no painel de Ajuda.

Assim que um Administrador do sistema completar essas etapas, você pode abrir o painel de Ajuda e clicar na aba **Guias de tarefas**. Agora você verá as guias da tarefa que se aplicam a página que é atualmente sobre em dynamics 365 para as operações. Se nenhum da tarefa for encontrado, você poderá inserir palavra-chave para refinar a pesquisa. Após clicar uma guia de tarefa no painel da ajuda, o painel da ajuda mostra as instruções passo a passo, e você pode executar o guia de tarefa. [guia de![tarefa exibição de leitura (]. /media/task-guide-ops-1024x742.png)](. /media/task-guide-ops.png)

### <a name="where-are-the-translated-task-guides"></a>Onde as guias estão traduzidos de tarefa?

As guias da tarefa são liberados em bibliotecas “com todos os idiomas no título.” Em dynamics 365 para operações, para ver a ajuda encontrada da guia da tarefa, verifique se você está conectado à biblioteca de apppropriate. O idioma que uma guia de tarefas é controlado em aparece para cada usuário por configurações de idioma em opções ** ** &gt; ** preferências **. 
-   Se uma guia da tarefa foi traduzido, quando você abre que a tarefa de texto da guia de tarefa aparecerá no idioma selecionado.
-   Se uma guia de tarefas não foi traduzido ainda, ao abrir o, somente alguns de texto (o texto) controla aparecerá no idioma selecionado.

## <a name="additional-resources"></a>Recursos adicionais
A tabela a seguir lista os sites que fornecem conteúdo sobre o Dynamics 365 for Operations. Nossos sites de conteúdo são organizados para oferecer suporte ao ciclo de vida do cliente. Cada fase recebe suporte de um conjunto diferente de sites. Os locais que possuem um asterisco (\*) próximo ao nome exigem que você entra usando uma conta que é associada com um plano de serviço.

| Site                                                                     | descrição                                                                                                                                                                                                                                |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [] Docs.microsoft.com (https://docs.microsoft.com/en-us/dynamics365/#pivot=solutions&panel=solutions_operations) | Hospeda ou vincula-se a toda a documentação de produto para o Dynamics 365 for Operations.                                                                                                                                                               |
| [Lifecycle Services](http://lcs.dynamics.com/en/)\*                      | Fornece um espaço de trabalho colaborativo baseado em nuvem o qual clientes e parceiros podem utilizar para gerenciar projetos no Dynamics 365 for Operations desde pré-vendas até implementação e operações. Esse site é útil em todas as fases de uma implementação. |
| CustomerSource [] (http://www.customersource.com/)\*                       | Hospeda recursos de treinamento extensivo e é o site do titular principal do Dynamics 365 for Operations. Entrar pode ser necessário para acessar recursos específicos do site.                                                                      |
| Blog [] de suporte (http://aka.ms/AXSupportBlog)                              | Fornece dicas e truques postadas pela Equipe de suporte do Dynamics 365 for Operations.                                                                                                                                                  |
| [] MSDN (http://aka.ms/AXMSDN)                                             | Hospeda conteúdo de versões anteriores escrito por desenvolvedores.                                                                                                                                                                       |
| [] TechNet (http://aka.ms/TechNet)                                         | Hospeda conteúdo de versões anteriores escrito para profissionais de TI e usuários que solicitam emprego.                                                                                                                                           |
| [] Da comunidade dinâmica (http://community.dynamics.com/en/)                  | Hospeda blogs, fóruns, e vídeos.                                                                                                                                                                                                           |
| [] (Microsoft.com/Dynamics/ http://www.microsoft.com/dynamics/)                 | Fornece avaliação e informações de vendas.                                                                                                                                                                                                 |



<a name="see-also"></a>Consulte também
--------

[Dynamics 365 para o sistema de ajuda de operações (ficha técnicas passível])(https://mbs.microsoft.com/files/public/CS/AX2012R3/DynamicsAXHelpSystemFactSheet.pdf)

[Task recorder no Microsoft Dynamics 365] (para operações. /user-interface/task-recorder.md)

[Criar documentação ou treinamento utilizando Gravações de tarefas](../user-interface/task-recorder.md)

[Novas guias ou atualizados a tarefa ()] em novembro de 2016(new-task-guides-november-2016.md
) [novas guias ou atualizados a tarefa ()] em agosto de 2016(new-updated-task-guides-available-august-2016.md
) [novas guias ou atualizados a tarefa ()] em maio de 2016(new-updated-task-guides-available-may-2016.md
) [novas guias da tarefa ()] em fevereiro de 2016(new-task-guides-available-february-2016.md)






