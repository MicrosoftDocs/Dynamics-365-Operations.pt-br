---
title: Fluxos de trabalho de aprovação de diário de estoque
description: Este artigo descreve como configurar e usar fluxos de trabalho de aprovação do diário do estoque para vários tipos de transações de estoque físico. Os fluxos de trabalho de diários de estoque ajudam a garantir que somente diários de estoque aprovados possam ser lançados em transações.
author: yufeihuang
ms.date: 08/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalTableWorkflowDropDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-07-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 3a97eaeae24850282c39196a61e3baa29307aa93
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334645"
---
# <a name="inventory-journal-approval-workflows"></a>Fluxos de trabalho de aprovação de diário de estoque

[!include [banner](../includes/banner.md)]

Este artigo descreve como configurar e usar fluxos de trabalho de aprovação de diário de estoque para transações de estoque físico de vários tipos, como saídas e recebimentos, movimentos de estoque, listas de materiais (BOMs) e reconciliação de estoque físico. Os fluxos de trabalho de diários de estoque ajudam a garantir que somente diários de estoque aprovados possam ser lançados em transações.

> [!NOTE]
> Os fluxos de trabalho de aprovação de diário de estoque se aplicam somente a transações registradas usando o módulo gerenciamento de estoque. Eles não funcionam com diários de estoque iniciados do módulo de gerenciamento de depósito.

## <a name="turn-the-inventory-journal-approval-workflows-feature-on-or-off"></a>Ativar ou desativar o recurso Fluxos de trabalho de aprovação de diário de estoque

Para usar esse recurso, você deve habilitá-lo no seu sistema. A partir do Supply Chain Management versão 10.0.21, o recurso está ativado por padrão. A partir do Supply Chain Management versão 10.0.29, o recurso é obrigatório e não pode ser desativado. Se você estiver executando uma versão anterior à 10.0.29, os administradores poderão ativar ou desativar essa funcionalidade procurando o recurso *Fluxo de trabalho de aprovação do diário de estoque* no espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="create-your-inventory-journal-approval-workflows"></a>Criar seus fluxos de trabalho de aprovação de diário de estoque

Para configurar esse recurso, você deve criar um fluxo de trabalho para cada um dos tipos de diário de estoque que deseja controlar. Como diferentes tipos de diários de estoque podem ter hierarquias de aprovação e etapas de fluxo de trabalho diferentes, você pode configurar fluxos de trabalho individuais para cada tipo de diário de estoque.

Os fluxos de trabalho dão suporte ao controle de versão, e cada um tem uma ID de fluxo de trabalho e uma versão ativa. Você pode optar por ativar cada nova versão do fluxo de trabalho imediatamente após a criação ou mantê-la inativa. Se você precisar de fluxos de trabalho diferentes para o mesmo tipo de diário, crie vários fluxos de trabalho para esse tipo de diário e atribua cada um deles a um nome de diário diferente que use esse tipo.

Para criar seus fluxos de trabalho de aprovação de diário de estoque:

1. Acesse **Gerenciamento de Estoque \> Configuração\> Fluxos de trabalho de gerenciamento de estoque**.
1. Selecione **Novo** no Painel de Ações.
1. Escolha o tipo de diário de estoque para o qual você deseja configurar um fluxo de trabalho:
    - **Diário de contagem de etiquetas de estoque**
    - **Diário de alteração de propriedade de estoque**
    - **Diários de movimento de estoque**
    - **Diário de transferência de estoque**
    - **Diário de contagem de estoque**
    - **Diário BOM do estoque**
    - **Diário de ajuste de estoque**

    ![A caixa de diálogo Criar fluxo de trabalho.](media/journal-workflow-create-workflow.png "A caixa de diálogo Criar fluxo de trabalho")

1. O aplicativo do editor de fluxo de trabalho é iniciado no seu computador. (Talvez seja solicitado que você aprove esta ação.) Use-o para criar seu fluxo de trabalho, conforme necessário. Para obter detalhes sobre como usar o editor de fluxo de trabalho, consulte [Visão geral do sistema de fluxo de trabalho](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md).
1. Depois de salvar e fechar o aplicativo do editor de fluxo de trabalho, escolha se a versão do fluxo de trabalho deve ser ativada ou mantida como inativa.

> [!NOTE]
> Os fluxos de trabalho fornecem controle de versão, o que significa que você pode exibir uma lista de versões que você criou e escolher qual delas está ativa. Para exibir a lista de versões disponíveis e escolher quais ativar, selecione um fluxo de trabalho listado na página **fluxos de trabalho de gerenciamento de estoque**. No painel de ações, abra a guia **Fluxo de trabalho** e selecione **Versões**. Somente uma versão pode estar ativa por vez para cada ID de fluxo de trabalho.

## <a name="assign-approval-workflows-to-inventory-journal-names"></a>Atribuir fluxos de trabalho de aprovação aos nomes do diário de estoque

A próxima etapa é atribuir um fluxo de trabalho de diário de estoque a cada nome de diário de estoque. Para cada tipo de diário de estoque, você pode configurar vários nomes de diários de estoque.

Para associar um fluxo de trabalho de diário de estoque a um nome de diário de estoque:

1. Acesse **Gerenciamento de estoque \> Configuração \> Nomes do diário \> Estoque**.
1. Selecione um nome de diário na coluna da lista para abrir a página de configurações.
1. Na guia rápida **Geral**, defina a opção **Workflow de aprovação** como **Sim**. Se for solicitado para você aprovar a ação, selecione **Sim**.

    ![Atribuir um fluxo de trabalho a um nome de diário.](media/journal-workflow-journal-name.png "Atribuir um fluxo de trabalho a um nome de diário")

1. Abra a lista suspensa **Fluxo de trabalho** e selecione o fluxo de trabalho apropriado. A lista mostra cada fluxo de trabalho ativo que você criou usando o aplicativo do editor de fluxo de trabalho.

## <a name="create-an-inventory-journal-and-send-it-for-approval"></a>Criar um diário de estoque e enviá-lo para aprovação

Depois de associar um nome de diário de estoque ao fluxo de trabalho de aprovação de diário de estoque correspondente, você poderá criar novos diários de estoque que usam esse nome e enviar esses diários para aprovação usando esse fluxo de trabalho. Você não poderá lançar o diário de estoque até que ele tenha sido aprovado pelos aprovadores configurados no fluxo de trabalho.

1. No painel de navegação, expanda **Gerenciamento de estoque \> Entradas de diários \> Itens** e selecione um tipo de diário de estoque.
1. Selecione **Novo** para criar um novo diário do tipo selecionado.
1. A caixa de diálogo **Criar diário de estoque** é aberta. Preencha o formulário, conforme necessário, e selecione **OK** para salvar o diário.
1. Preencha o diário, conforme necessário.
1. Quando você cria ou abre um diário de estoque com um fluxo de trabalho de aprovação associado a ele, o botão **Fluxo de trabalho** estará ativo no painel de ações. Quando estiver pronto para enviar o diário para aprovação, selecione o botão **Fluxo de trabalho** para abrir uma caixa de diálogo suspensa e selecione **Enviar**. A solicitação de aprovação será roteada para o aprovador relevante, que será alertado usando o método de notificação configurado para o fluxo de trabalho.

    ![Enviar um diário para aprovação.](media/journal-workflow-inventory-journal.png "Enviar um diário para aprovação")

Para cancelar uma solicitação de aprovação, abra o diário relevante, selecione o botão **Fluxo de trabalho** e, em seguida, selecione **Cancelar**. Isso redefinirá o fluxo de trabalho.

Quando o diário tiver sido aprovado, você poderá lançá-lo. Para lançar o diário, selecione **Lançar** no painel de ações. Se o botão **Lançar** não estiver ativo, o diário ainda não foi aprovado.

## <a name="respond-to-an-inventory-journal-approval-request"></a>Responder a uma solicitação de aprovação de diário de estoque

Se você for aprovador, deverá receber uma mensagem sempre que a aprovação for necessária (conforme configurado no fluxo de trabalho relevante). Em seguida, você pode aprovar ou rejeitar uma solicitação de aprovação de diário, fazendo o seguinte:

1. No painel de navegação, expanda **Gerenciamento de estoque \> Entradas de diários \> Itens** e selecione um tipo de diário de estoque.
1. Abra o diário relevante e revise-o.
1. Selecione o botão **Fluxo de trabalho** no painel de ações para abrir uma caixa de diálogo suspensa. Selecione uma das seguintes opções:
    - **Aprovar** - para aprovar a solicitação.
    - **Rejeitar** -para rejeitar a solicitação.
    - **Mais \> Alteração da solicitação** - Para enviar uma mensagem ao solicitante solicitando que ele altere algo específico e reenvie.
    - **Mais \> Delegar** - Para delegar a aprovação a outro usuário.
    - **Mais \> Cancelar** - Para cancelar a solicitação de aprovação (redefine o fluxo de trabalho).
    - **Mais \> Histórico de fluxo de trabalho** – Para exibir o histórico deste fluxo de trabalho de aprovação até agora.

## <a name="review-the-approval-history"></a>Revisar o histórico de aprovação

Como outros tipos de fluxos de trabalho, você pode usar a página **Histórico do fluxo de trabalho** para exibir o histórico do fluxo de trabalho de aprovação para qualquer diário.

Para revisar o histórico do fluxo de trabalho para um diário:

1. No painel de navegação, expanda **Gerenciamento de estoque \> Entradas de diários \> Itens** e selecione um tipo de diário de estoque.
1. Abra o diário relevante.
1. Selecione o botão **Fluxo de trabalho** no painel de ações para abrir uma caixa de diálogo suspensa. Selecione **Histórico do fluxo de trabalho**. Para obter mais informações, consulte [Exibir histórico do fluxo de trabalho](../../fin-ops-core/fin-ops/organization-administration/tasks/view-workflow-history.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]