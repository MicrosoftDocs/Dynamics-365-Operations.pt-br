---
title: Criar um fluxo de trabalho
description: "Este tópico explica como criar um fluxo de trabalho."
author: sericks007
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WorkflowSelectTemplateRnr, WorkflowTableListPageRnr
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195583
ms.assetid: 836ddd01-cc34-45c3-a4b0-20647357dbc6
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ee3f60575d0eaaf56ce08adb1936728a76488dac
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="create-a-workflow"></a>Criar um fluxo de trabalho

[!include [banner](../includes/banner.md)]

Este tópico explica como criar um fluxo de trabalho.

<a name="open-the-workflow-editor"></a>Abrir o editor de fluxo de trabalho
------------------------

O módulo do Microsoft Dynamics 365 for Finance and Operations no qual você está trabalhando determina os tipos de fluxo de trabalho que você pode criar. Siga estas etapas para selecionar o tipo de fluxo de trabalho a ser criado e para abrir o editor de fluxo de trabalho.

1.  Vá para o módulo para o qual deseja criar um novo fluxo de trabalho. Por exemplo, para criar um fluxo de trabalho para requisições de compra, clique em **Compras e fornecimento**.
2.  Clique em **Configuração** &gt; **\[nome do módulo\] fluxos de trabalho**.
3.  Na página de listagem que aparece, no Painel de ação, clique em **Novo**.
4.  Na página **Criar fluxo de trabalho**, selecione o tipo de fluxo de trabalho para criar, e então clique em **Criar fluxo de trabalho**. O editor de fluxo de trabalho aparece. Agora você pode usar os procedimentos a seguir para criar o fluxo de trabalho.

## <a name="drag-workflow-elements-onto-the-canvas"></a>Arrastar os elementos do fluxo de trabalho para a tela
Na área **Elementos de fluxo de trabalho** do editor de fluxo de trabalho contém os elementos que você pode adicionar ao fluxo de trabalho. Para adicionar elementos ao fluxo de trabalho, arraste-os da área para a tela.

## <a name="connect-the-elements"></a>Conectar os elementos
Para conectar um elemento do fluxo de trabalho a outro, mantenha o ponteiro sobre um elemento até que os pontos de conexão apareçam. Clique em um ponto de conexão e arraste-o para outro elemento. Conecte todos os elementos.

## <a name="configure-the-properties-of-the-workflow"></a>Configurar as propriedades do fluxo de trabalho
Execute as etapas abaixo para configurar as propriedades do fluxo de trabalho.

1.  Clique na tela para garantir que nenhum elemento do fluxo de trabalho esteja selecionado.
2.  Clique em **Propriedades** para abrir a página **Propriedades** para o fluxo de trabalho.
3.  Siga os procedimentos no tópico [Configurar as propriedades de um fluxo de trabalho](configure-workflow-properties.md).

## <a name="configure-the-elements-of-the-workflow"></a>Configurar os elementos do fluxo de trabalho
Configure cada elemento que você arrastou para a tela. Para obter informações sobre como configurar cada elemento do fluxo de trabalho, consulte os seguintes tópicos.

-   [Configurar uma tarefa manual](configure-manual-task-workflow.md)
-   [Configurar uma tarefa automatizada](configure-automated-task-workflow.md)
-   [Configurar um processo de aprovação](configure-approval-process-workflow.md)
-   [Configurar uma etapa de aprovação](configure-approval-step-workflow.md)
-   [Configurar uma decisão manual](configure-manual-decision-workflow.md)
-   [Configurar uma decisão condicional](configure-conditional-decision-workflow.md)
-   [Configurar uma atividade paralela](configure-parallel-activity-workflow.md)
-   [Configurar uma ramificação paralela](configure-parallel-branch-workflow.md)
-   [Configurar um fluxo de trabalho de item de linha](configure-line-item-workflow.md)

## <a name="resolve-any-errors-or-warnings"></a>Resolver todos os erros ou avisos
O painel **Erros e avisos**, localizado na parte inferior do editor de fluxo de trabalho, exibe as mensagens geradas para o fluxo de trabalho. Para localizar o elemento que gerou um erro ou aviso, clique duas vezes no erro ou na mensagem de aviso. Todos os erros e avisos devem ser resolvidos para que você possa ativar o fluxo de trabalho.

## <a name="save-and-activate-the-workflow"></a>Salvar e ativar o fluxo de trabalho
Quando estiver pronto para salvar e ativar o fluxo de trabalho, siga estas etapas.

1.  Clique em **Salvar e fechar** para fechar o editor de fluxo de trabalho e abrir a página **Salvar fluxo de trabalho**.
2.  Digite comentários sobre as alterações feitas no fluxo de trabalho e clique em **OK**.
3.  Se todos os erros e avisos foram resolvidos, a página **Ativar fluxo de trabalho** será exibido. Selecione uma das seguintes opções:
    -   Para ativar a versão de fluxo de trabalho, clique em **Ativar a nova versão**. Quando um fluxo de trabalho estiver ativo, os usuários poderão enviar documentos a ele para processamento.
    -   Se não quiser ativar a versão, clique em **Não ativar a nova versão**. É possível ativar o fluxo de trabalho posteriormente.






