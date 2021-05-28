---
title: Notificações de execução do ciclo
description: Este tópico descreve as notificações de execução do ciclo e explica como configurá-las.
author: mirzaab
ms.date: 04/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WhsWaveNotificationPolicy, WHSParameters, WHSWaveTemplateTable, BusinessEventsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2022-04-01
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: fee112d3211f619b2146dd21c4f8a52ad33667d6
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019145"
---
# <a name="wave-execution-notifications"></a>Notificações de execução do ciclo

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

O recurso *Notificações de execução do ciclo* usa eventos comerciais e a Central de ações para entregar notificações relacionadas à execução do ciclo. Ele permite que você especifique os tipos de eventos que geram notificações, os depósitos que as geram e os usuários que as recebem.

O botão **Mostrar mensagens** (símbolo de sino) no lado direito da barra de navegação indica quando uma mensagem da Central de ações está disponível para o usuário atual. O usuário pode selecionar o botão **Mostrar mensagens** para abrir a Central de ações e revisar as mensagens.

Os eventos comerciais ocorrem quando processos comerciais são executados. Os processos comerciais são compostos de tarefas. Durante um processo comercial, os usuários que participam dele executam ações comerciais para concluir essas tarefas. Os eventos de negócios fornecem um mecanismo que permite que os sistemas externos recebam notificações de aplicativos do Finance and Operations. Dessa forma, os sistemas podem executar ações comerciais em resposta aos eventos comerciais. Para obter mais informações, consulte [Visão geral de alertas comerciais](../../fin-ops-core/dev-itpro/business-events/home-page.md).

## <a name="turn-on-the-wave-execution-notifications-feature"></a>Ativar o recurso Notificações de execução do ciclo

Antes de usar o recurso *Notificações de execução do ciclo*, ele deverá estar ativado no seu sistema. Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário. Nesse caso, o recurso é listado da seguinte maneira:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Notificações de execução do ciclo*

## <a name="scenario-send-wave-batch-execution-notifications-to-the-action-center"></a>Cenário: enviar notificações de execução em lotes do ciclo para a Central de ações

Este cenário mostra o fluxo de ponta a ponta para enviar notificações sobre erros de execução em lotes de ciclos a uma função específica por meio da Central de ações.

### <a name="make-demo-data-available"></a>Disponibilizar dados de demonstração

Para seguir este cenário, você deve ter dados de demonstração instalados e deve selecionar a entidade legal **USMF**.

### <a name="make-sure-that-waves-are-run-in-batch-mode"></a>Verificar se os ciclos são executados no modo de lote

1. Vá para **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**.
1. Na Guia Rápida **Processamento do ciclo**, defina a opção **Processar ciclos em lotes** como *Sim*.

> [!NOTE]
> Se você quiser desabilitar as notificações de execução em lotes do ciclo, defina a opção **Desabilitar notificações em lotes de processamento do ciclo** como *Sim*.

### <a name="configure-a-wave-notification-policy"></a>Configurar uma política de notificação do ciclo

As políticas de notificação do ciclo definem os tipos de notificação enviadas e os usuários notificados.

1. Vá para **Gerenciamento de depósito \> Configuração \> Ciclos \> Políticas de notificação do ciclo**.
1. Crie um registro com as seguintes configurações:

    - **Política de notificação do ciclo:** *24BatchError*
    - **Descrição:** *Erro de lote do ciclo do Depósito 24*
    - **Enviar notificação em:** *Somente erro*
    - **Para a função:** *Administrador do sistema*

        > [!NOTE]
        > Como esse cenário usa dados de demonstração, a função *Administrador do sistema* foi selecionada para simplificar. Portanto, como você está conectado como um usuário administrador do sistema, receberá as notificações. No entanto, na prática, geralmente você deve selecionar uma função mais específica para notificar sobre erros de execução de lotes do ciclo, como *Gerente de depósito*.

1. No Painel de ações, selecione **Salvar**.

### <a name="configure-a-wave-template"></a>Configurar um modelo de onda

Os modelos do ciclo permitem vincular instâncias específicas de métodos do ciclo a modelos de etiqueta do ciclo correspondentes.

1. Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Modelos de onda**.
1. No painel de lista, defina o campo **Tipo de modelo do ciclo** como *Remessa* e selecione o modelo do ciclo *Remessa Padrão 24* para o depósito 24.
1. Na Guia Rápida **Geral**, defina o campo **Política de notificação do ciclo** como *24BatchError*.

### <a name="configure-a-work-template"></a>Configurar um modelo de trabalho

Os modelos de trabalho são usados durante a execução do ciclo para gerar trabalho. Para este cenário, a execução do ciclo deve disparar um erro. Ao configurar a consulta de modelo de trabalho para usar um depósito não existente, você garantirá que a execução do ciclo falhe e, dessa forma, envie uma notificação.

1. Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.
1. No painel de lista, defina o campo **Tipo de modelo de trabalho** como *Ordens de venda* e selecione o modelo de trabalho *Preparo SO 24* para o depósito 24.
1. No Painel de Ações, selecione **Editar consulta**.
1. Na caixa de diálogo do editor de consultas, na guia **Intervalo**, edite a linha a seguir (ou adicione-a se ela não existir):

    - **Tabela:** *Transações de trabalho temporário*
    - **Tabela derivada:** *Transações de trabalho temporário*
    - **Campo:** *Depósito*
    - **Critérios:** altere o valor de *24* para *Erro*.

1. Selecione **OK** e confirme a alteração.

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Criar uma ordem de venda e liberá-la para o depósito

1. Vá para **Vendas e marketing \> Ordem de venda \> Todas as ordens de venda**.
1. Crie uma ordem de venda com as seguintes configurações:

    - **Conta de cliente:** *US-001*
    - **Depósito:** *24*

1. Na Guia Rápida **Linhas da ordem de venda**, adicione uma linha de ordem de venda que tenha as seguintes configurações:

    - **Número de item:** *A0001*
    - **Quantidade:** *10*

    > [!NOTE]
    > Esses itens e quantidades são apenas exemplos. O depósito especificado deve conter estoque suficiente.

1. Com a nova linha de ordem ainda selecionada na Guia Rápida **Linhas de ordem de venda**, selecione **Estoque \> Reserva** na barra de ferramentas.
1. Na página **Reserva**, no Painel de Ação, selecione **Reservar lote**. Depois feche a página.
1. No Painel de Ações, na guia **Depósito**, selecione **Liberar para o depósito**.

### <a name="notifications-from-wave-batch-job-execution"></a>Notificações da execução do trabalho em lotes do ciclo

Dependendo da configuração dos eventos comerciais, você receberá, eventualmente, uma notificação sobre a falha na execução do ciclo. A mensagem da Central de ações será semelhante ao exemplo a seguir e incluirá um link para o ciclo que falhou.

> **Erro durante execução do ciclo**  
> Ocorreu um erro ao executar o ciclo USMF -000000001.  
> Últimas mensagens: nenhum trabalho foi criado para o ciclo USMF-000000001.
>
> **STATUS**  
> Com Atividade
>
> Abrir detalhes do ciclo

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
