---
title: Criar documentação ou treinamento com o Gravador de tarefas
description: Este tópico explica o que são o gravador de tarefas e os guias de tarefas, como criar gravações de tarefas e como personalizar guias de tarefas da Microsoft e incluí-los na sua Ajuda.
author: josaw1
manager: AnnBe
ms.date: 03/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SysHelpSetup
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: 25391
ms.assetid: 59bf39f8-1464-441e-8b23-9a856c73471b
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b92ef15fc9f3f6a5ebb6ba4ea4eae1a0f7488995
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687783"
---
# <a name="create-documentation-or-training-with-task-recorder"></a>Criar documentação ou treinamento com o Gravador de tarefas

[!include [banner](../includes/banner.md)]

Este tópico explica o que são o gravador de tarefas e os guias de tarefas, como criar gravações de tarefas e como personalizar guias de tarefas da Microsoft e incluí-los na sua Ajuda.

> [!IMPORTANT]
> Você pode registrar suas próprias guias de tarefa para o Dynamics 365 Human Resources, mas não é possível salvá-las em uma biblioteca Modelador de Processo de Negócios (BPM) ou abri-las no painel Ajuda neste momento. Você pode salvá-las localmente ou em um local da rede e, em seguida, abrir e repeti-las usando o Gravador de tarefas. 

<a name="learn-about-task-recorder"></a>Aprender sobre o Gravador de tarefas
-------------------------

O gravador de tarefas é uma ferramenta que você pode usar para gravar ações que você leva na interface do usuário do produto (UI). Quando você utiliza o Gravador de tarefas, todos os eventos executados na interface do usuário executados em relação ao servidor — incluindo adicionar valores, alterar configurações, remover dados — são capturados. As etapas que você registra são chamadas coletivamente de *gravação de tarefa*. Gravações de tarefas podem ser utilizadas de diversas maneiras:

-   **Gravações de tarefas podem ser executadas como guias de tarefas.** As guias de tarefas são parte integrante da experiência de ajuda. Uma guia de tarefas é uma experiência controlada, guiada e interativa por meio de etapas de um processo de negócios. O usuário é instruído a concluir cada etapa por meio de um aviso pop-up (ou "bolha"), que será animado ao longo da interface do usuário e apontará para o elemento com o qual o usuário deve interagir. A "bolha" também fornece informações sobre como interagir com o elemento, como "Clique aqui" ou "Neste campo, insira um valor". Uma guia de tarefas é executada no conjunto de dados atual do usuário e os dados inseridos são salvos no ambiente do usuário.
-   **Gravações de tarefas podem ser salvas como documentos do Word.** Isso permite que você produza facilmente guias de treinamento imprimíveis.

Você pode criar suas próprias gravações de tarefas, executar gravações de tarefas disponibilizadas pela Microsoft ou modificá-las para refletir a sua configuração. Para obter mais informações sobre o Gravador de tarefas, consulte [Gravador de tarefas](task-recorder.md).

## <a name="plan-your-task-recording"></a>Planejar sua gravação de tarefa
Se você estiver criando uma nova gravação de tarefa ou baseando sua gravação em um gravação de tarefa da Microsoft, mantenha as informações a seguir em mente.

-   Planeje sua gravação como você faria com um vídeo. Tome todas suas decisões com antecedência.
-   Percorra o processo comercial uma ou duas vezes sem gravá-lo para entender as etapas.
-   Quando você percorrer o processo antes de gravá-lo, observe onde você utiliza teclas de atalho ou a tecla **Enter**, para que você possa evitar utilizá-las durante a gravação.
-   Identifique os seguintes:
    -   Você deseja agrupar etapas na forma de subtarefas? As subtarefas separam visualmente as seções de um processo. Por exemplo, se estiver criando uma gravação para "Criação e lançamento de um produto", você poderá querer agrupar as etapas necessárias para criar um produto, e depois agrupar as etapas necessárias para lançar o produto. As subtarefas também fazem com que processos longos se tornem mais fáceis de ler.
    -   Você deseja adicionar anotações e, caso queira, onde? Consulte "Entenda os diferentes tipos de anotações" abaixo para obter mais informações.
    -   Quais valores você irá adicionar nos diversos campos ao completar as etapas do processo comercial? É recomendável saber o que irá selecionar ou inserir ao longo do procedimento de forma que não seja necessário retroceder ou consertar erros durante a gravação.

**Escreva sua descrição e suas anotações antecipadamente**

-   No início de cada gravação de tarefa, existe um campo de descrição que possibilita que você insira uma introdução sobre a gravação. É recomendável escrever e salvar a descrição antecipadamente em um documento separado para que você possa copiar e colar ela na gravação de tarefa durante a gravação. Dessa forma, você pode gastar tempo aprimorando o texto enquanto não esta no processo de gravação. Cortar e colar o texto torna o processo de gravação mais ágil e suave.
-   Para cada etapa em uma gravação de tarefa, você pode criar anotações. Durante a reprodução de um guia de tarefas, as anotações aparecem na "bolha" como observações acima ou abaixo do texto da etapa. Quando exibidas como texto no painel Ajuda, as anotações aparecem como texto embutido na etapa. Como na descrição, é aconselhável escrever e salvar suas anotações em um documento separado. Quando você estiver gravando a gravação de tarefa, copie e cole as anotações daquele documento.

**Compreenda os diferentes tipos de anotações** Todas as anotações são opcionais. Adicione-as apenas quando forem fornecer informações úteis ao usuário.

-   **Título:** Uma anotação de título aparecerá antes do texto da etapa que o gravador de tarefas gera automaticamente. Na guia da tarefas, a nota de título aparece acima do texto gerado automaticamente. Use este tipo de anotação para explicar por que o usuário está executando essa etapa ou para fornecer contexto adicional.

Este é o painel de edição que é exibido quando você adiciona uma anotação durante a criação da gravação. Insira uma nota de título na caixa **Título**. 

[![Painel de edição com a anotação do título](./media/screen1.png)](./media/screen1.png) 

É assim que a anotação de título se parece na "bolha" no guia de tarefas. 

[![Aparência da anotação do título na guia de tarefas](./media/screen2.png)](./media/screen2.png)

-   **Observações:** Uma anotação de observação aparecerá depois do texto da etapa que o gravador de tarefas gera automaticamente. No guia de tarefa isso será visível apenas se o usuário clicar no link **Mostrar mais** na bolha da guia de tarefa. Utilize este tipo de anotação para descrever qualquer coisa que um usuário precisa saber para concluir a etapa.

Este é o painel de edição que é exibido quando você adiciona uma anotação durante a criação da gravação. Insira notas de título na caixa **Notas**. 

[![Painel de edição com anotações na caixa Notas](./media/screen3.png)](./media/screen3.png) 

É assim que as anotações de título se parece na "bolha" no guia de tarefas.

[![Aparência da anotação das Notas na guia de tarefas](./media/screen4.png)](./media/screen4.png)

-   **Etapa de informações**: essas anotações são criadas clicando com o botão direito do mouse em um controle ou em qualquer lugar em um formulário &lt; **Gravador de tarefas** &lt; **Adicionar etapa de informações.** As etapas de informações aparecem como um passo numerado no ponto em que você o insere, mesmo que nenhuma ação tenha sido registrada na interface do usuário. Você pode adicionar uma etapa informativa de nível de formulário ou uma etapa informativa associada a um controle. Quando uma etapa informativa está associada a um formulário, a "bolha" do guia de tarefa irá aparecer em algum lugar do formulário, sem um ponteiro, quando o guia de tarefa for executado. Quando uma etapa de informação é associada a um controle, a guia de tarefas "bolha" aponta para o controle quando o guia de tarefas é reproduzido. No painel Ajuda, uma anotação de etapa de informações será exibida como uma etapa numerada com qualquer texto digitado. Utilize etapas informativas para preparar o usuário para as próximas etapas, para descrever etapas que devem ser feitas fora do aplicativo ou para fazer referência a outras gravações (embora não seja possível criar hiperlinks nas anotações).

**Determine o tempo para fazer a gravação**

-   O usuário irá, no geral, ler ou executar a gravação do início ao fim, portanto não agrupe etapas ou tarefas que são feitas melhores separadamente.
-   Tente não gravar um cenário longo que realiza múltiplos subprocessos. Por exemplo, "Operar balcão de atendimento ao cliente na loja" é muito amplo; desmembre-a em tarefas mais curtas como "Aceitar devoluções" e "Adicionar ao cartão-presente".
-   Se uma tarefa pode ser realizada como parte de vários processos comerciais diferentes, crie uma gravação separada para ela, e você pode fazer referência à ela nas outras gravações.
-   Se o processo envolve múltiplas tarefas que a pessoa provavelmente fará de uma só vez, você pode manter as tarefas em uma única gravação, por exemplo, "Configurar e atribuir perfis de funcionalidade".
-   Caso seja algo feito uma única vez (como configuração) e então outra tarefa que pode ser realizada logo na sequência mas que poderá ser feita repetidas vezes, e por conta própria, separe-as em duas gravações de tarefa.

**Decida onde, na UI, para iniciar uma gravação** A página em que você está quando inicia a gravação de uma tarefa afeta a página na qual o guia de tarefas é exibido. Por exemplo, se desejar que a gravação da tarefa seja listada no painel Ajuda quando um usuário clicar em Ajuda na página de parâmetros do razão geral, você deve iniciar a gravação na página de parâmetros do razão geral. **Salvar gravações como arquivos .axtr** Quando você terminar de criar ou editar uma gravação de tarefas, existirão diversas opções para baixar ou salvar a gravação. Você pode baixar o arquivo como um pacote de gravação de tarefa (.axtr), baixar como um arquivo de gravação bruto (.xml), baixar como um documento de Word, ou salvar o arquivo a uma biblioteca do LCS. É recomendável sempre salvar sua gravação de tarefa como um pacote de arquivos de gravação de tarefa (.axtr). Isso tornará a manutenção do arquivo mais fácil caso os procedimentos ou anotações precisem ser alterados posteriormente. Se você quiser baixar o arquivo como um documento de Word, salve-o também como um arquivo de pacote de gravação de tarefas.

## <a name="create-your-task-recording"></a>Criar sua gravação de tarefa
Para obter as etapas detalhadas, consulte [Recursos do Gravador de tarefas](task-recorder.md).

## <a name="copy-and-customize-microsofts-task-recordings"></a>Copiar e personalizar gravações de tarefas da Microsoft
Você pode baixar e editar gravações de tarefas da Microsoft para utilizá-las em sua própria documentação de ajuda ou materiais de treinamento. Para baixar uma gravação de tarefa do Microsoft, siga as etapas abaixo:

1.  Abrir gravador de tarefas. O Gravador de tarefas está localizado no menu **Configurações**.
2.  No painel do Gravador de tarefas, clique em **Manter uma gravação.**
3.  Em **Onde está a gravação**, clique em **Está em uma biblioteca do LCS**.
4.  Clique em **Selecionar a biblioteca do LCS**.
5.  Selecione a biblioteca global Microsoft.
6.  Na árvore, selecione o nó da biblioteca de processo comercial ao qual a gravação de tarefa está associada.
7.  Clique em **OK**.
8.  Clique em **Iniciar**.
9.  Nesse ponto, percorra a gravação, alterando as etapas à medida que for regravando. **Observação**: se só precisar alterar o texto de uma gravação, você poderá abrir a gravação no modo **Editar anotações de uma gravação** e então salvá-la.
10. Assim que a gravação for executado até o final, clique em **Parar** na barra do gravador de tarefas na parte superior da tela.
11. Escolha como você deseja salvar a gravação de tarefa.



<a name="additional-resources"></a>Recursos adicionais
--------

[Sistema de ajuda](../../fin-ops/get-started/help-overview.md)

[Conectar o Sistema de ajuda](../../fin-ops/get-started/help-connect.md)

[Gravador de Tarefas](task-recorder.md)

[Crie tópicos de ajuda detalhados com o Gravador de tarefas (link externo)](https://mbspartner.microsoft.com/AX/Videos/970)
