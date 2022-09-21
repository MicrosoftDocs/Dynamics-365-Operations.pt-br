---
title: Configurar as experiências de Ajuda para aplicativos de finanças e operações
description: Este artigo fornece informações sobre os componentes do Sistema de ajuda para alguns aplicativos do Microsoft Dynamics 365.
author: edupont04
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: edupont
ms.search.region: Global
ms.author: edupont
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.form: SystemParameters
ms.openlocfilehash: 2c45a203303181c7ea23e20f8fa1bdce1c827aa2
ms.sourcegitcommit: 9c637bcf4e2eb8f711290a861492f038feaf1568
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2022
ms.locfileid: "9462204"
---
# <a name="configure-the-help-experience-for-finance-and-operations-apps"></a>Configurar as experiências de Ajuda para aplicativos de finanças e operações

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Neste artigo, você encontrará uma visão geral dos componentes do sistema de Ajuda para aplicativos de finanças e operações, como Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce e Dynamics 365 Human Resources. O artigo também explica como conectar esses componentes e fornece um resumo do processo para criar Ajuda personalizada.

## <a name="help-architecture"></a>Arquitetura de ajuda

Os aplicativos de finanças e operações incluem visões gerais conceituais e outros tópicos publicados no site de documentação do [Microsoft Dynamics 365](/dynamics365/). Esse conteúdo pode ser acessado no painel **Ajuda** do produto. A ilustração a seguir mostra as partes do sistema de Ajuda.

[![Arquitetura de ajuda.](./media/help-architecture.png)](./media/help-architecture.png)

O sistema de ajuda do produto recebe os artigos do Microsoft Docs e de outros sites conectados. Ele também reúne guias de tarefas que são armazenadas no BPM (Modelador de processo de negócios) no Microsoft Dynamics Lifecycle Services (LCS).

## <a name="adding-task-guides"></a>Adição de guias de tarefas

> [!NOTE]
> No momento, a guia **Guias de tarefas** não está disponível no Human Resources nem no Commerce. <!--We are currently working to enable this functionality in a future release.--> Mas, as guias de tarefas da experiência de Introdução ao Human Resources permanecem disponíveis para a funcionalidade básica. No Human Resources e no Commerce, a Ajuda de procedimentos está disponível no site da [documentação do Microsoft Dynamics 365](/dynamics365/).

Na página **Parâmetros do sistema**, os administradores de sistema podem configurar o acesso às bibliotecas relevantes do guia de tarefas para uma implementação.

> [!NOTE]
> - Para configurar a Ajuda, você precisa entrar usando uma conta no mesmo locatário que o locatário em que o aplicativo é implantado.
> - Uma biblioteca de LCS não pode ser conectada de uma instância do aplicativo que esteja em execução em uma unidade de disco rígido virtual local (VHD).

[![Formulário Parâmetros do Sistema com configurações da Ajuda.](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)

Para configurar guias de tarefas para uma solução, siga estas etapas na página **Parâmetros do sistema**.

> [!IMPORTANT]
> A primeira vez que você abrir a guia de **Ajuda** é necessário conectar-se ao Lifecycle Services. Selecione o link no meio do formulário, aguarde a conexão, feche a caixa de diálogo e selecione **OK** para acessar a página **Parâmetros do Sistema**.
>
> [![Conectar-se ao LCS](./media/connect-to-lcs-crop-1024x365.png "Conectar-se ao LCS.")](./media/connect-to-lcs-crop.png)

1. Selecione o projeto do Lifecycle Services para se conectar.
2. Selecione as bibliotecas do BPM (dentro do projeto selecionado) para recuperar gravações de tarefas delas.
3. Defina a ordem de exibição das bibliotecas do BPM. A ordem de exibição define a ordem em que as gravações de tarefas das bibliotecas aparecerão no painel de **Ajuda**.

Após concluir essas etapas, você poderá abrir o painel **Ajuda** e selecionar **Guias de tarefas**. Agora você verá as guias de tarefas que se aplicam à página que você está utilizando nos aplicativos de finanças e operações. Se nenhum guia de tarefa for encontrado, você pode inserir palavra-chave para refinar a pesquisa.

### <a name="showing-translated-task-guides"></a>Exibindo guias de tarefa traduzidos

Guias de tarefas traduzidas foram liberadas primeiro na Biblioteca Unificada de APQC de maio de 2016 e na biblioteca Introdução. Para exibir a ajuda da guia de tarefas localizadas, verifique se a solução do Dynamics 365 está conectada à biblioteca de maio de 2016. Para mudar o idioma em que uma guia de tarefas aparece, usuários podem alterar as configurações de idioma em **Opções** &gt; **Preferências**.

> [!NOTE]
> Embora muitas guias de tarefas tenham sido traduzidas, no momento o cliente não mostra os nomes de guias de tarefas traduzidos. Além disso, na biblioteca de maio de 2016, foram disponibilizadas traduções apenas para guias de tarefas que foram liberadas em fevereiro de 2016. A Microsoft lançará uma biblioteca atualizada que inclui traduções adicionais.
>
> - Se uma guia de tarefa foi traduzida, quando você abrir esse guia de tarefa, todo o texto do guia de tarefa será exibido no idioma selecionado.
> - Se uma guia de tarefa ainda não foi traduzida, quando você abrir esse guia de tarefa, apenas umas partes do texto (o texto dos controles) aparecerá em seu idioma selecionado.

## <a name="adding-custom-help"></a>Adição de ajuda personalizada

Você pode usar guias de tarefa para criar ajuda personalizada ou conectar um site de ajuda personalizada ao painel de **Ajuda**.

### <a name="create-custom-help-by-using-task-guides"></a>Crie ajuda personalizada com guias de tarefas

Você pode criar ajuda personalizada para aplicativos com suporte criando registros de tarefas que reflitam sua implementação e salvando-os em uma biblioteca de processos comerciais no LCS. Não é possível criar guias de tarefas personalizadas para o Human Resources.

Se você for um parceiro e promover uma biblioteca para uma biblioteca corporativa e incluí-la em uma solução, ela ficará disponível para os clientes. Você também pode fazer uma cópia da biblioteca unificada de APQC, abrir as gravações de tarefas na cópia, editá-las e salvar suas alterações. Para obter mais informações, consulte [Recursos do Gravador de tarefas](../../dev-itpro/user-interface/task-recorder.md).

### <a name="connect-a-custom-help-site"></a>Conecte um site de ajuda personalizado

Os aplicativos de finanças e operações raramente são usados no formulário pronto para uso. Em vez disso, a solução é personalizada e estendida para atender às necessidades da organização. Também é possível personalizar e estender a experiência da ajuda. Por exemplo, você pode adicionar ajuda personalizada ao painel de **ajuda** do produto.

A Microsoft forneceu um kit de ferramentas para ajudar você a implantar e conectar a ajuda personalizada ao painel de **ajuda**. Para obter informações sobre como você pode configurar uma solução de ajuda personalizada que está conectada ao painel de **ajuda**, consulte [Visão geral da ajuda personalizada](../../dev-itpro/help/custom-help-overview.md).

Se você desejar colaborar com a Microsoft em ferramentas e processos para personalizar a ajuda, preencha o formulário em [https://aka.ms/customhelpfeedback](https://aka.ms/customhelpfeedback).

## <a name="see-also"></a>Consulte também

[Sistema de ajuda](help-overview.md)  
[Visão geral da ajuda personalizada](../../dev-itpro/help/custom-help-overview.md)  
[Recursos do Gravador de tarefas](../../dev-itpro/user-interface/task-recorder.md)  
[Criar documentação ou treinamento com o Gravador de tarefas](../../dev-itpro/user-interface/task-recorder-training-docs.md)  
[Repositório do GitHub de ajuda personalizada](https://github.com/microsoft/dynamics356f-o-custom-help)  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
