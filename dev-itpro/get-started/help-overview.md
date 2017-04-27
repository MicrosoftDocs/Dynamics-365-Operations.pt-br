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

-   Um site de documentação
-   Guias de tarefas

Você pode acessar tanto os artigos quanto os guias de tarefas através do painel Ajuda no Dynamics 365 for Operations, conforme mostrado na captura de tela a seguir. [![Painel de ajuda](./media/help-pane-ops-task-guides-1024x741.png)](./media/help-pane-ops-task-guides.png) Este artigo descreve o sistema de Ajuda, e explica como você pode criar documentação personalizada e recursos de treinamento para sua organização.

## <a name="help-on-docsmicrosoftcom"></a>Ajuda no docs.microsoft.com
O site docs.microsoft.com site ([docs.microsoft.com/dynamics365/operations](https://docs.microsoft.com/en-us/dynamics365/#pivot=solutions&panel=solutions_operations) é a fonte principal de documentação do produto para o Dynamics 365 for Operations. O site oferece os seguintes recursos:

-   **Acesso ao conteúdo mais atualizado**– O site fornece uma maneira mais rápida e flexível para criar, entregar e atualizar a documentação do produto. Portanto, ajuda a garantir que você tenha acesso às informações técnicas mais recentes.
-    **Conteúdo escrito por especialistas**– O site fornece um conjunto rico de documentação do produto que pode ser aprimorado por membros da comunidade tanto de dentro quanto de fora da Microsoft.
-   ** Acesso aos diferentes tipos de conteúdo** – O site permite acessar rapidamente diferentes tipos de conteúdo sobre o Dynamics 365 for Operations, como apresentações em Microsoft Office Mix, guias de tarefas, vídeos e artigos da wiki.
-    **Conteúdo que oferece suporte aos seus processos comerciais**– O site inclui conteúdo focado em processo comercial que se aproveita do Modelador de Processo de Negócios (BPM) no Microsoft Dynamics Lifecycle Services (LCS).

Nós migramos todo o conteúdo de nosso wiki anterior da ajuda para os docs. Nós estamos muito animados em relação ao novo site e esperamos que você também fique.

### <a name="when-can-we-use-it"></a>Quando poderemos usá-la?

Você pode ler o conteúdo nos docs agora mesmo -- é totalmente público e pesquisável sem a necessidade de cadastro. Você pode utilizar qualquer uma das suas ferramentas de pesquisa favoritas para encontrar conteúdo. Você pode comentar em artigos no site se quiser, conectando com uma conta de GitHub.


## <a name="task-guides"></a>Guias de tarefas
Um guia de tarefa é uma experiência controlada, guiada, interativa que irá guiá-lo durante as etapas de uma tarefa, ou processo comercial. Você pode abrir (executar) um guia de tarefas através do painel de Ajuda. Quando você clicar pela primeira vez em um guia de tarefas, o painel de Ajuda irá exibir as instruções passo a passo para a tarefa. Os guias de tarefas localizados agora estão disponíveis. [![Visualização de leitura do guia de tarefas](./media/task-guide-ops-1024x742.png)](./media/task-guide-ops.png) Para iniciar a experiência guiada, interativa, clique em **Iniciar guia de tarefa** na parte inferior do painel de Ajuda. Um ponteiro preto abre e indica a ação que você precisa executar. Siga as direções que aparecem na UI, e insira os dados conforme instruído. [![Instrução da etapa do guia de tarefas](./media/task-guide-step-1-ops.png)](./media/task-guide-step-1-ops.png) **Importante:** Os dados inseridos quando você executa um guia de tarefa são reais. Se você estiver em um ambiente de produção, os dados serão inseridos na empresa que você está usando atualmente.

### <a name="it-all-begins-with-task-recorder"></a>Tudo começa com o Gravador de Tarefas

Guias de tarefas são criados usando o Gravador de Tarefas. Quando você utiliza o Gravador de Tarefas, todas as ações que você realiza na IU do Dynamics 365 for Operations (como clicar em menus, alterar configurações, e inserir dados) são registradas. As etapas que você registra são chamadas coletivamente de gravação de tarefa. Como explicamos na seção anterior, as gravações de tarefas podem ser exibidas no painel de Ajuda e executadas como guias de tarefas. No entanto, existem outras maneiras de utilizar gravações de tarefas:

-   **Salvar gravações de tarefas ao BPM** – Você pode salvar uma gravação de tarefa à uma linha de uma hierarquia em uma biblioteca do BPM em LCS. Quando você salva uma gravação de tarefa ao BPM, um fluxograma é gerado e exibido, junto com as etapas da gravação. **Observação:** Para exibir uma gravação de tarefa no painel de Ajuda do Dynamics 365 for Operations e executá-la como um guia de tarefa, você deve salvar a gravação à uma biblioteca do BPM.
-   **Salvar gravações de tarefa como documentos Word** – Ao salvar uma gravação de tarefa como um documento Microsoft Word, você pode facilmente produzir guias de treinamento imprimíveis para sua organização.

Para obter mais informações sobre o Gravador de Tarefas, consulte [Gravador de tarefas no Dynamics 365 for Operations](../user-interface/task-recorder.md).

### <a name="creating-customized-task-recordings"></a>Criando gravações de tarefas personalizadas

Você pode criar suas próprias gravações de tarefas, ou você pode baixar e personalizar gravações de tarefas que a Microsoft oferece. Consequentemente, você pode criar Ajuda personalizada para sua organização que reflete sua implementação específica do Dynamics 365 for Operations. Para exibir uma gravação de tarefas no painel de Ajuda do Dynamics 365 for Operations e executá-la como um guia de tarefas, você terá que salvar a gravação em uma biblioteca BPM no LCS. Se for um parceiro e promover uma biblioteca como uma biblioteca corporativa, e incluí-la em uma solução, ela ficará disponível para os clientes. Para obter instruções completas, consulte [Utilizando gravações de tarefas para criar documentação ou treinamento](../user-interface/task-recorder.md).

## <a name="in-product-help"></a>Ajuda sobre produto
Para acessar o conteúdo de Ajuda dentro do Dynamics 365 for Operations, clique no ícone **Ajuda** (**?**) e escolha Ajuda ou pressione Ctrl+Shift+?. Em ambos os casos, o painel de Ajuda abre. No painel de Ajuda, você pode acessar artigos ou guias de tarefas. [![](./media/help-pane-wiki-1024x684.png)](./media/help-pane-wiki.png)

### <a name="accessing-articles-from-the-help-pane"></a>Acessando artigos do painel de Ajuda

No painel de Ajuda, você pode acessar artigos que se aplicam ao cliente do Dynamics 365 for Operations. Quando você abrir pela primeira vez o painel da Ajuda e clicar na guia **Wiki**, você verá os artigos que se aplicam à página na qual você está atualmente no Dynamics 365 for Operations. Se nenhum artigo for encontrado, você poderá inserir palavras-chave para refinar a pesquisa. Quando você clicar em um artigo no painel de Ajuda, uma nova aba será aberta no seu navegador e exibirá o artigo. 

### <a name="accessing-task-guides-from-the-help-pane"></a>Acessando guias de tarefas através do painel de Ajuda

Antes que você possa acessar os guias de tarefas do painel de Ajuda, um Administrador do sistema deve ir até a página **Parâmetros do sistema** no Dynamics 365 for Operations e configurar algumas definições. **Observações:**

-   Para configurar a Ajuda, você precisa estar conectado com uma conta do inquilino mesmo como o locatário em que Dynamics 365 for Operations é implantado.
-   Não é possível conectar-se a uma biblioteca de LCS de uma instância do Dynamics 365 for Operations em execução em uma unidade de disco rígida virtual local (VHD).

[![Formulário de parâmetros do sistema com configurações de ajuda](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) Na página **Parâmetros do sistema**, siga estas etapas:

1.  **Importante: **A primeira vez que você abrir a guia da ajuda, é necessário conectar serviços do ciclo de vida. Certifique-se de clicar no link no meio do formulário, aguarde a conexão, feche a caixa de diálogo e depois clique em OK para ir para o formulário de parâmetros.[![Conectar-se ao LCS](./media/connect-to-lcs-crop-1024x365.png)](./media/connect-to-lcs-crop.png)
2.  Selecione o projeto do Lifecycle Services para se conectar.
3.  Selecione as bibliotecas do BPM (dentro do projeto selecionado) para recuperar gravações de tarefas delas.
4.  Defina a ordem de exibição das bibliotecas do BPM. Isso determina a ordem em que as gravações de tarefas das bibliotecas irão aparecer no painel de Ajuda.

Assim que um Administrador do sistema completar essas etapas, você pode abrir o painel de Ajuda e clicar na aba **Guias de tarefas**. Agora você verá os guias da tarefa que se aplicam à página que está sendo atualmente usada no Dynamics 365 for Operations. Se nenhum guia de tarefas for encontrado, você poderá inserir palavras-chave para refinar a pesquisa. Depois de clicar em um guia de tarefas no painel de Ajuda, o painel de Ajuda exibirá as instruções passo a passo, e você pode executar o guia de tarefas. [![Visualização de leitura do guia de tarefas](./media/task-guide-ops-1024x742.png)](./media/task-guide-ops.png)

### <a name="where-are-the-translated-task-guides"></a>Onde estão os guias de tarefa traduzidos?

Os guias da tarefa são liberados em bibliotecas com "Todos os idiomas" no título. No Dynamics 365 for Operations, para ver a ajuda do guia de tarefas localizada, certifique-se de que você está conectado à uma biblioteca apropriada. O idioma que aparece em um guia de tarefas é controlado para cada usuário pelas configurações de Idioma em **Opções** &gt; **Preferências**. 
-   Se um guia de tarefas foi traduzido, quando você abrir esse guia de tarefas, todo o texto do guia de tarefas será exibido no idioma selecionado.
-   Se um guia de tarefas ainda não foi traduzido, quando você abri-lo, apenas algumas partes do texto (o texto dos controles) aparecerão em seu idioma selecionado.

## <a name="additional-resources"></a>Recursos adicionais
A tabela a seguir lista os sites que fornecem conteúdo sobre o Dynamics 365 for Operations. Nossos sites de conteúdo são organizados para oferecer suporte ao ciclo de vida do cliente. Cada fase recebe suporte de um conjunto diferente de sites. Os sites que têm um asterisco (\*) ao lado do nome exigem que você se conecte usando uma conta que esteja associada à um plano de serviço.

| Site                                                                     | descrição                                                                                                                                                                                                                                |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Docs.microsoft.com](https://docs.microsoft.com/en-us/dynamics365/#pivot=solutions&panel=solutions_operations) | Hospeda ou vincula-se a toda a documentação de produto para o Dynamics 365 for Operations.                                                                                                                                                               |
| [Lifecycle Services](http://lcs.dynamics.com/en/)\*                      | Fornece um espaço de trabalho colaborativo baseado em nuvem o qual clientes e parceiros podem utilizar para gerenciar projetos no Dynamics 365 for Operations desde pré-vendas até implementação e operações. Esse site é útil em todas as fases de uma implementação. |
| [CustomerSource](http://www.customersource.com/)\*                       | Hospeda recursos de treinamento extensivo e é o site do titular principal do Dynamics 365 for Operations. Entrar pode ser necessário para acessar recursos específicos do site.                                                                      |
| [Blog de suporte](http://aka.ms/AXSupportBlog)                              | Fornece dicas e truques postadas pela Equipe de suporte do Dynamics 365 for Operations.                                                                                                                                                  |
| [MSDN](http://aka.ms/AXMSDN)                                             | Hospeda conteúdo de versões anteriores escrito por desenvolvedores.                                                                                                                                                                       |
| [TechNet](http://aka.ms/TechNet)                                         | Hospeda conteúdo de versões anteriores escrito para profissionais de TI e usuários que solicitam emprego.                                                                                                                                           |
| [Comunidade do Dynamics](http://community.dynamics.com/en/)                  | Hospeda blogs, fóruns, e vídeos.                                                                                                                                                                                                           |
| [Microsoft.com/Dynamics/](http://www.microsoft.com/dynamics/)                 | Fornece avaliação e informações de vendas.                                                                                                                                                                                                 |



<a name="see-also"></a>Consulte também
--------

[Sistema de ajuda do Dynamics 365 for Operations (baixar planilha de fatos)](https://mbs.microsoft.com/files/public/CS/AX2012R3/DynamicsAXHelpSystemFactSheet.pdf)

[Gravador de tarefas no Microsoft Dynamics 365 for Operations](../user-interface/task-recorder.md)

[Criar documentação ou treinamento utilizando Gravações de tarefas](../user-interface/task-recorder.md)

[Guias de tarefas novos ou atualizados (Novembro de 2016)](new-task-guides-november-2016.md)
[Guias de tarefas novos ou atualizados (Agosto de 2016)](new-updated-task-guides-available-august-2016.md)
[Guias de tarefas novos ou atualizados (Maio de 2016)](new-updated-task-guides-available-may-2016.md)
[Guias de tarefas novos (Fevereiro de 2016)](new-task-guides-available-february-2016.md)






