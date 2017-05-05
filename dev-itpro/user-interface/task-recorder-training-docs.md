---
title: "Criar documentação ou treinamento utilizando Gravações de tarefas"
description: "Este tópico explica o que são o gravador de tarefas e os guias de tarefas, como criar gravações de tarefas e como personalizar guias de tarefas da Microsoft e incluí-los na sua Ajuda."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysHelpSetup
audience: Application User, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 25391
ms.assetid: 59bf39f8-1464-441e-8b23-9a856c73471b
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b21fd97426b331726c12ea29f89817a46dd445c3
ms.openlocfilehash: 38bce4a843f0db575c8d1ba08b7dc2ece8366663
ms.lasthandoff: 03/31/2017


---

# <a name="create-documentation-or-training-using-task-recordings"></a>Criar documentação ou treinamento utilizando Gravações de tarefas

[!include[banner](../includes/banner.md)]

Este tópico explica o que são o gravador de tarefas e os guias de tarefas, como criar gravações de tarefas e como personalizar guias de tarefas da Microsoft e incluí-los na sua Ajuda.

<a name="learn-about-task-recorder"></a>Aprender sobre o Gravador de tarefas
-------------------------

O gravador de tarefas é uma ferramenta do Microsoft Dynamics 365 for Operations que você pode usar para registrar ações que você tomar na interface do usuário do produto (UI). Quando você utiliza o Gravador de tarefas, todos os eventos executados na UI que são executados em relação ao servidor—incluindo adicionar valores, alterar configurações, remover dados—são capturados. As etapas que você registra são chamadas coletivamente de *gravação de tarefa*. Gravações de tarefas podem ser utilizadas de diversas maneiras:

-   **Gravações de tarefas podem ser executadas como guias de tarefas.** Os guias de tarefas são parte integrante do Dynamics 365 para a experiência de ajuda de operações. Um guia de tarefas é uma experiência controlada, guiada e interativa através das etapas de um processo de negócios. O usuário é instruído na conclusão de cada etapa por meio de um lembrete pop-up (ou "bolha"), que será animado ao longo da UI e irá apontar para o elemento com o qual o usuário deve interagir. A "bolha" também fornece informações sobre como interagir com o elemento, como "Clique aqui" ou "Neste campo, insira um valor Um guia de tarefas é executado no conjunto de dados atual do usuário e os dados inseridos são salvos no ambiente do usuário.
-   **Gravações de tarefas podem ser exibidas como etapas de procedimento no painel de ajuda.** Você pode usar o painel de ajuda para pesquisar e exibir gravações de tarefas. Você pode acessar o painel de Ajuda clicando em **?** ícone na barra de navegação superior ou você pode usar a combinação de teclas de atalho **Ctrl+Shift+?**. Você pode ler as etapas de uma gravação de tarefa no painel de ajuda, ou você pode optar por executar a gravação como um guia de tarefa para que ele te apresente a UI.
-   **Gravações de tarefas podem ser salvas no BPM.** Você pode salvar sua gravação de tarefa à uma linha de uma hierarquia em uma biblioteca do Modelador de Processo de Negócios (BPM) em Lifecycle Services (LCS). Uma lista de etapas e um fluxograma do processo comercial serão gerados a partir da gravação. Gravações de tarefas que foram salvas em uma biblioteca do BPM podem ser exibidas no Dynamics 365 for Operations como ajuda.
-   **Gravações de tarefas podem ser salvas como documentos do Word.** Isso permite que você produza facilmente guias de treinamento imprimíveis.

Você pode criar suas próprias gravações de tarefas, executar gravações de tarefas disponibilizadas pela Microsoft ou modificá-las para refletir a sua configuração. Para obter mais informações sobre o Gravador de Tarefas, consulte [Gravador de tarefas no Dynamics 365 for Operations](task-recorder.md).

## <a name="plan-your-task-recording"></a>Planejar sua gravação de tarefa
Se você estiver criando uma nova gravação de tarefa ou baseando sua gravação em um gravação de tarefa da Microsoft, mantenha as informações a seguir em mente.

-   Planeje sua gravação como você faria com um vídeo. Tome todas suas decisões com antecedência.
-   Percorra o processo comercial uma ou duas vezes sem gravá-lo para entender as etapas.
-   Quando você percorrer o processo antes de gravá-lo, observe onde você utiliza teclas de atalho ou a tecla **Enter**, para que você possa evitar utilizá-las durante a gravação.
-   Identifique os seguintes:
    -   Você deseja agrupar etapas na forma de subtarefas? Subtarefas separam visualmente as seções de um processo. Por exemplo, se você estiver criando uma gravação para "Criando e lançando um produto", você pode querer agrupar as etapas necessárias para criar um produto, e depois agrupar as etapas necessárias para lançar o produto. Subtarefas também fazem com que processos longos se tornem mais fáceis de ler.
    -   Você deseja adicionar anotações e, caso queira, onde? Consulte "Entenda os diferentes tipos de anotações" abaixo para obter mais informações.
    -   Quais valores você irá adicionar nos diversos campos ao completar as etapas do processo comercial? É recomendável saber o que irá selecionar ou inserir ao longo do procedimento de forma que não seja necessário retroceder ou consertar erros durante a gravação.

**Escreva sua descrição e suas anotações antecipadamente**

-   No início de cada gravação de tarefa, existe um campo de descrição que possibilita que você insira uma introdução sobre a gravação. É recomendável escrever e salvar a descrição antecipadamente em um documento separado para que você possa copiar e colar ela na gravação de tarefa durante a gravação. Dessa forma, você pode gastar tempo aprimorando o texto enquanto não esta no processo de gravação. Cortar e colar o texto torna o processo de gravação mais ágil e suave.
-   Para cada etapa em uma gravação de tarefa, você pode criar anotações. Durante a reprodução de um guia de tarefa, anotações aparecem na "bolha" como observações acima ou abaixo do texto da etapa. Quando exibidas como texto no painel de ajuda, anotações aparecem como texto embutido na etapa. Como na descrição, é aconselhável escrever e salvar suas anotações em um documento separado. Quando você estiver gravando a gravação de tarefa, copie e cole as anotações daquele documento.

**Compreenda os diferentes tipos de anotações** Todas as anotações são opcionais. Adicione-as apenas quando forem fornecer informações úteis ao usuário.

-   **Título:** Uma anotação de título aparecerá antes do texto da etapa que o gravador de tarefas gera automaticamente. Na guia da tarefa, a nota de cabeçalho aparece acima do texto gerado automaticamente. Use este tipo de anotação para explicar por que o usuário está executando essa etapa ou para fornecer contexto adicional.

Este é o painel de edição que é exibido quando você adiciona uma anotação durante a criação da gravação. Insira uma nota de título na caixa **Título**. 

[![screen1](./media/screen1.png)](./media/screen1.png) 

É assim que a anotação de título se parece na "bolha" no guia de tarefas. 

[![screen2](./media/screen2.png)](./media/screen2.png)

-   **Observações:** Uma anotação de observação aparecerá depois do texto da etapa que o gravador de tarefas gera automaticamente. No guia de tarefa isso será visível apenas se o usuário clicar no link **Mostrar mais** na bolha da guia de tarefa. Utilize este tipo de anotação para descrever qualquer coisa que um usuário precisa saber para concluir a etapa.

Este é o painel de edição que é exibido quando você adiciona uma anotação durante a criação da gravação. Insira notas de título na caixa **Notas**. 

[![screen3](./media/screen3.png)](./media/screen3.png) 

É assim que as anotações de título se parece na "bolha" no guia de tarefas.

[![screen4](./media/screen4.png)](./media/screen4.png)

-   **Etapa de informações**: Essas anotações são criadas clicando com o botão direito do mouse em um controle ou em qualquer lugar em um formulário &lt; **Registrador de tarefas** &lt; **Adicionar etapa de informações. **As etapas de informações aparecem como um passo numerado no ponto em que você o insere, mesmo que nenhuma ação tenha sido registrada na interface do usuário. Você pode adicionar uma etapa informativa de nível de formulário ou uma etapa informativa associada a um controle. Quando uma etapa informativa está associada a um formulário, a "bolha" do guia de tarefa irá aparecer em algum lugar do formulário, sem um ponteiro, quando o guia de tarefa for executado. Quando uma etapa de informação é associada a um controle, a guia de tarefas "bolha" aponta para o controle quando o guia de tarefas é reproduzido. No painel de Ajuda, uma anotação de passo de informações será exibida como uma etapa numerada com qualquer texto digitado. Utilize etapas informativas para preparar o usuário para as próximas etapas, para descrever etapas que devem ser feitas fora do Dynamics 365 for Operations, ou para fazer referência a outras gravações (embora não seja possível criar hiperlinks nas anotações).

**Determine o tempo para fazer a gravação**

-   O usuário irá, no geral, ler ou executar a gravação do início ao fim, portanto não agrupe etapas ou tarefas que são feitas melhores separadamente.
-   Tente não gravar um cenário longo que realiza múltiplos subprocessos. Por exemplo, "Operar bancada de atendimento ao cliente na loja" é muito amplo; desmembre-a em tarefas mais curtas como "Aceitar devoluções" e "Adicionar ao cartão-presente".
-   Se uma tarefa pode ser realizada como parte de vários processos comerciais diferentes, crie uma gravação separada para ela, e você pode fazer referência à ela nas outras gravações.
-   Se o processo envolve múltiplas tarefas que a pessoa provavelmente fará de uma só vez, você pode manter as tarefas em uma única gravação, por exemplo, "Configurar e atribuir perfis de funcionalidade".
-   Caso seja algo feito uma única vez (como configuração) e então outra tarefa que pode ser realizada logo na sequência mas que poderá ser feita repetidas vezes, e por conta própria, separe-as em duas gravações de tarefa.

**Decida onde, na UI, para iniciar uma gravação** A página em que você está quando inicia a gravação de uma tarefa afeta a página na qual o guia de tarefas é exibido. Por exemplo, se desejar que a gravação da tarefa seja listada no painel Ajuda quando um usuário clicar em Ajuda na página de parâmetros do razão geral, você deve iniciar a gravação na página de parâmetros do razão geral. **Salvar gravações como arquivos .axtr** Quando você terminar de criar ou editar uma gravação de tarefa, existirão diversas opções para baixar ou salvar a gravação. Você pode baixar o arquivo como um pacote de gravação de tarefa (.axtr), baixar como um arquivo de gravação bruto (.xml), baixar como um documento de Word, ou salvar o arquivo a uma biblioteca do LCS. É recomendável sempre salvar sua gravação de tarefa como um pacote de arquivos de gravação de tarefa (.axtr). Isso tornará a manutenção do arquivo mais fácil caso os procedimentos ou anotações precisem ser alterados posteriormente. Se você deseja baixar o arquivo como um documento de Word, salve-o também como um pacote de arquivos de gravação de tarefa.

## <a name="create-your-task-recording"></a>Criar sua gravação de tarefa
Para obter etapas detalhadas, consulte [Como criar uma gravação de tarefas](task-recorder.md).

## <a name="copy-and-customize-microsofts-task-recordings"></a>Copiar e personalizar gravações de tarefas da Microsoft
Você pode baixar e editar gravações de tarefas da Microsoft para utilizá-las em sua própria documentação de ajuda ou materiais de treinamento. Para baixar uma gravação de tarefa do Microsoft, siga as etapas abaixo:

1.  No Dynamics 365 for Operations, abra o gravador de tarefas. O Gravador de tarefas está localizado no menu **Configurações**.
2.  No painel do Gravador de tarefas, clique em **Manter uma gravação.**
3.  Em **Onde está a gravação**, clique em **Está em uma biblioteca do LCS**.
4.  Clique em **Selecionar a biblioteca do LCS**.
5.  Selecione a biblioteca global Microsoft.
6.  Na árvore, selecione o nó da biblioteca de processo comercial ao qual a gravação de tarefa está associada.
7.  Clique em **OK**.
8.  Clique em **Iniciar**.
9.  Nesse ponto, percorra a gravação, alterando os passos à medida que for regravando. **Observação**: Se você só precisar alterar o texto de uma gravação, poderá abrir a gravação no modo **Editar anotações de uma gravação** e então salvá-lo.
10. Assim que a gravação for executado até o final, clique em **Parar** na barra do gravador de tarefas na parte superior da tela.
11. Escolha como você deseja salvar a gravação de tarefa.

## <a name="include-your-task-recordings-in-the-help-pane"></a>Incluir suas gravações de tarefas no painel de ajuda
Para mostrar suas próprias gravações de tarefas personalizadas no painel de ajuda para que possam ser executadas novamente como guias de tarefas ou visualizadas como texto, você deve salvar suas gravações de tarefas à sua própria biblioteca do BPM, e então atualizar os parâmetros do seu sistema de ajuda para que ele aponte para sua biblioteca do BPM. Para obter mais informações, consulte [Conectando o sistema de ajuda.](../get-started/help-connect.md)

<a name="see-also"></a>Consulte também
--------

[Ajuda do Dynamics 365 for Operations](..\get-started\help-overview.md)

[Conectar Help](..\get-started\help-connect.md)

[Gravador de tarefas no Dynamics 365 for Operations](task-recorder.md)

[Recursos recentemente adicionados do registrador de tarefas](\core\get-started\recently-added-editing-features-in-task-recorder)

[Criando novas bibliotecas de treinamento para o Dynamics AX no Lifecycle Services usando o Gravador de tarefas (link externo)](https://docs.com/mufife/163372c6-f366-4c5a-94fa-93e2c25f878a/creating-new-training-libraries-for-dynamics-ax)

[Crie tópicos de ajuda detalhados com o Gravador de tarefas (link externo)](https://mbspartner.microsoft.com/AX/Videos/970)



