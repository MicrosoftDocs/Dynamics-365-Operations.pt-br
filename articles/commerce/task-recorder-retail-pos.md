---
title: Gravador de tarefa e Ajuda do Retail Modern POS (MPOS) e Cloud POS
description: Este artigo descreve como utilizar o Gravador de tarefas no Retail Modern POS e no Cloud POS.
author: mugunthanm
ms.date: 06/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailTerminalTable, SystemParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 1205393
ms.assetid: 2f13e9cf-55b5-458b-8c32-3f8cd98c9ecf
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: f9f3e17a6c67dc1cc1d4ba423ce258f2ed1d1ec0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847591"
---
# <a name="task-recorder-and-help-for-retail-modern-pos-mpos-and-cloud-pos"></a>Gravador de tarefa e Ajuda do Retail Modern POS (MPOS) e Cloud POS

[!include [banner](includes/banner.md)]

Este artigo descreve como utilizar o Gravador de tarefas no Retail Modern POS e no Cloud POS.

## <a name="overview"></a>Visão geral

O Gravador de tarefas do Retail Modern POS ou do PDV em Nuvem é uma nova solução que foi criada com foco na alta capacidade de resposta. Ele oferece uma API (interface de programa aplicativo) flexível para extensibilidade e integração direta com os registros dos consumidores do processo de negócios. Além disso, a integração do Gravador de tarefas com a ferramenta BPM (Modelador de processo de negócios) no Microsoft Dynamics Lifecycle Services ([https://bpm.lcs.dynamics.com](https://bpm.lcs.dynamics.com/)) foi apresentada. Portanto, os usuários podem continuar a gerar diagramas sofisticados de processo de negócios a partir de gravações para analisar e projetar seus aplicativos.

## <a name="architecture"></a>Arquitetura

O Gravador de tarefas pode registrar ações de usuário no cliente com fidelidade precisa. Cada controle é instrumentado para notificar o Gravador de tarefas sobre a execução de uma ação de usuário. O controle notifica o Gravador de tarefas sobre a ocorrência de um evento e passa adiante todas as informações pertinentes sobre a ação de usuário correspondente em tempo real. Com essas informações, o Gravador de tarefas pode capturar o tipo de ação de usuário (como um clique de botão, uma entrada de valor ou a navegação) e quaisquer dados relacionados à ação de usuário (como o valor e o tipo dos dados de entrada, o contexto de formulário ou o contexto de registro). O Gravador de tarefas mantém as informações com detalhes suficientes para ajudar a garantir que a reprodução da gravação possa executar as ações gravadas exatamente como o usuário as executaria. (O recurso de reprodução ainda não foi implementado no Retail Modern POS ou no PDV em Nuvem).

## <a name="basic-configuration"></a>Configuração básica

Para habilitar a gravação de tarefas no PDV, siga estas etapas.

1. Clique em **Varejo e Comércio** &gt; **Configuração do canal** &gt; **Configuração do PDV** &gt; **Registros**.
2. Clique em registro em que a gravação de tarefas será habilitada.
3. Na guia **Registrar**, na Guia Rápida **Geral**, defina a opção **Habilitar gravação de tarefas** como **Sim**.
4. Clique em **Salvar**.
5. Acesse **Retail e Commerce** &gt; **TI de Varejo e Comércio** &gt; **Agenda de distribuição**.
6. Selecione o trabalho **Registros (1090)** e então clique em **Executar agora**.

## <a name="create-a-recording"></a>Criar uma gravação

Siga estas etapas para criar uma nova gravação usando o Gravador de tarefas.

1. Inicie o Retail Modern POS ou o Cloud POS e entre.
2. Na página **Configurações**, na seção **Gravador de Tarefas**, clique em **Abrir gravador de tarefas**. O painel **Gravador de tarefas** aparecerá. Você pode clicar no botão **Fechar** (**X**) no canto superior direito para fechar o painel **Gravador de tarefas** antes de iniciar uma nova gravação. Para reabrir o painel, repita a etapa 2.

    [![Painel do Gravador de tarefas.](./media/newrecording-1024x450.jpg)](./media/newrecording.jpg)

3. Insira um nome e uma descrição para a gravação e então clique em **Iniciar**. A sessão de gravação começa assim que você clica em **Iniciar**.

    > [!NOTE]
    > Se você clicar no botão **Fechar** (**X**) no canto superior direito enquanto a gravação estiver em andamento, o painel **Gravador de tarefas** será fechado, mas a sessão de gravação não será encerrada. Para reabrir o painel do Gravador de tarefas, clique no botão **Ajuda** (ponto de interrogação) na parte superior da tela.
    >
    > [![Ponto de interrogação.](./media/help.jpg)](./media/help.jpg)

4. Depois que você clicar em **Iniciar**, o Gravador de tarefas entrará no modo de gravação. O painel **Gravador de tarefas** mostra as informações e os controles relacionados ao processo de gravação.
5. Execute as ações desejadas na IU (interface do usuário) do Retail Modern POS ou do Cloud POS.
6. Para encerrar a sessão de gravação, clique em **Parar**.

## <a name="download-options"></a>Opções de download

Após o encerramento da sessão de gravação, diversas opções são mostradas para que você possa baixar sua gravação.

[![Opções de download.](./media/downlaod-options.jpg)](./media/downlaod-options.jpg)

### <a name="save-to-this-pc"></a>Salvar neste computador

Você pode usar o pacote de gravação para reproduzir um Guia de tarefas, manter a gravação ou editar as anotações na gravação. (Esse recurso ainda não foi implementado no Retail Modern POS ou no Cloud POS).

### <a name="export-as-word-document"></a>Exportar como documento do Word

Você pode salvar a gravação como um documento do Microsoft Word. O documento conterá as etapas gravadas e as capturas de tela que foram feitas.

### <a name="save-as-developer-recording"></a>Salvar como gravação do desenvolvedor

O arquivo bruto de gravação será útil em cenários de desenvolvimento, como a geração de código de teste. (Esse recurso ainda não foi implementado).

## <a name="recording-controls"></a>Controles de gravação

[![Controles de gravação.](./media/controls.jpg)](./media/controls.jpg)

### <a name="stop"></a>Parar

Clique em **Parar** para encerrar a sessão de gravação. Observe que não é possível reiniciar uma sessão depois de encerrá-la. Portanto, certifique-se de que a gravação esteja concluída antes de encerrá-la.

### <a name="pause"></a>Pausa

Clique em **Pausar** para parar temporariamente (pausa) a sessão de gravação e para continuar com a operação. As etapas realizadas depois que você clicar em **Pausar** não serão registradas.

### <a name="continue"></a>Continuar

Para retomar a sessão de gravação depois de pausá-la, clique em **Continuar**.

### <a name="capture-screenshots"></a>Capturar telas

O Gravador de tarefas pode capturar telas da interface do usuário do Retail Modern POS à medida que você registra um processo de negócios. Para ativar o recurso de captura de tela, defina a opção **Capturar tela** como **Sim** e, em seguida, faça a gravação. Depois que o registro for concluído, clique em **Interromper** e baixar o documento do Word. O documento conterá as etapas a capturas de tela relevantes.

> [!NOTE]
> A funcionalidade Capturar tela não tem suporte no Cloud POS.

### <a name="start-task-and-end-task"></a>Iniciar tarefa e Finalizar tarefa

Você pode especificar o início e o final de um conjunto de etapas agrupadas usando os botões **Iniciar tarefa** e **Finalizar** **tarefa**. Clique em **Iniciar tarefa** para adicionar uma etapa "Iniciar Tarefa" e execute as etapas que devem ser incluídas no grupo. Depois de concluir a execução das etapas para o grupo, clique em **Finalizar tarefa**. As tarefas ajudam você a organizar seus procedimentos. As tarefas podem ser aninhadas em outras tarefas. Assim, você pode organizar melhor os processos de negócios muito longos e complexos.

## <a name="adding-annotations"></a>Adição de anotações

Uma anotação é um outro texto adicionado a uma etapa em uma gravação. Por exemplo, você pode usar as anotações para oferecer ao usuário mais contexto ou mais instruções. Você pode adicionar anotações antes ou depois de uma etapa. Você pode adicionar uma anotação a qualquer etapa clicando no botão **Editar** (símbolo de lápis) à direita de etapa.

[![Botão Editar de uma etapa.](./media/annotate.jpg)](./media/annotate.jpg)

### <a name="texts-and-notes"></a>Textos e notas

Você pode usar os campos **Textos** e **Notas** para adicionar o texto que deve ser associado a uma etapa em uma Guia de tarefas.

[![Campos Texto e Notas.](./media/annotatesteps.jpg)](./media/annotatesteps.jpg)

#### <a name="text"></a>Texto

O texto inserido no campo **Texto** aparece *acima* do texto da etapa no Guia de tarefas. Esta localização é apropriada para o texto que o usuário deve ler antes de concluir a etapa.

#### <a name="notes"></a>Observação

O texto inserido no campo **Notas** aparece *abaixo* do texto da etapa no Guia de tarefas. Para ler o texto da nota, o usuário deverá expandir o texto da etapa na janela pop-up. Essa localização é apropriada para o material de leitura opcional ou para outras informações que possam ser úteis para o usuário, mas que não são obrigatórias para a conclusão da ação.

## <a name="help-in-retail-modern-pos-and-cloud-pos"></a>Ajuda do Retail Modern POS e do Cloud POS

Para mostrar suas próprias gravações de tarefas personalizadas no painel da Ajuda do Retail Modern POS e do Cloud BPM para que possam ser executadas novamente como guias de tarefas ou exibidas como texto, você deverá salvar suas gravações de tarefas em sua própria biblioteca do BPM, e então atualizar os parâmetros do seu sistema de ajuda para que ele aponte para sua biblioteca do BPM. Para obter mais informações, consulte [Conectando o sistema de ajuda.](../fin-ops-core/fin-ops/get-started/help-connect.md) A Ajuda do Retail Modern POS e do Cloud POS pesquisa o LCS em tempo real. Ela pesquisa em todas as bibliotecas BPM selecionadas nos parâmetros do sistema da Ajuda do Commerce e mostra os resultados relevantes. Para acessar o menu **Ajuda**, clique no botão **Ajuda** (ponto de interrogação) na parte superior da tela e, na caixa de pesquisa, digite o nome do processo e pressione o botão de pesquisa.

[![Botão Ajuda.](./media/help.jpg)](./media/help.jpg)

Quando você clicar em uma Guia de tarefas nos resultados da pesquisa, poderá exibir as etapas como um artigo da Ajuda ou exportar as etapas para um documento do Word.

> [!NOTE]
> A ajuda no Retail Modern POS e Cloud POS não exibirá guias de tarefas de acordo com o formulário em que você está ou a operação que está fazendo. É necessário digitar o nome do processo na caixa de pesquisa e clique em **Pesquisar**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]