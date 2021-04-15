---
title: Configurar gerenciamento de tarefas
description: Este tópico descreve como configurar os recursos de gerenciamento de tarefas no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 742d49b1b7b46952d0a8bb6c8a33cde2a35d124f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791690"
---
# <a name="configure-task-management"></a>Configurar gerenciamento de tarefas

[!include [banner](includes/banner.md)]

Este tópico descreve como configurar os recursos de gerenciamento de tarefas no Microsoft Dynamics 365 Commerce.

Antes que os gerentes e funcionários do Dynamics 365 Commerce possam usar os recursos de gerenciamento de tarefas do Commerce, o gerenciamento de tarefas deve ser configurado. As etapas de configuração incluem a concessão de permissões a gerentes e funcionários, a distribuição de permissões para clientes de ponto de venda (PDV), a configuração de notificações PDV e a configuração do bloco de **Tarefas** na página inicial de um aplicativo de PDV.

## <a name="configure-permissions-for-store-managers"></a>Configurar permissões para gerentes de armazenamento

Cada trabalhador em uma determinada loja pode exibir todas as tarefas atribuídas a essa loja. Eles também podem atualizar o status das tarefas atribuídas a eles. No entanto, as pessoas como gerentes de armazenamento devem ter permissões de gerenciamento de tarefas para gerenciar as tarefas atribuídas à loja e criar tarefas de finalidade única.

Para configurar permissões de gerenciamento de tarefas para os gerentes de armazenamento, siga estas etapas.

1. Vá para **Retail e Commerce \> Funcionários \> Grupos de permissão**.
1. Selecione um grupo de permissões específico (por exemplo **Gerente**) e, em seguida, selecione **Editar**.
1. Na guia **Permissões**, defina a opção **Permitir gerenciamento de tarefas** como **Sim**.
1. Na Guia Rápida **Notificações**, adicione a operação **Gerenciamento de tarefas**, e insira um valor no campo **Exibir ordem**. Por exemplo, digite **2** se a operação **Preenchimento da ordem** já tiver um valor **Exibir ordem** como **1**.
    
> [!NOTE]
> Se uma pessoa que não é gerente deve ter permissões de gerenciamento de tarefas no PDV, você pode conceder permissão à pessoa. Alternativamente, você pode criar um novo grupo de permissão para não-gerentes e definir a opção **Permitir gerenciamento de tarefas** como **Sim**.

A ilustração a seguir mostra como configurar permissões de gerenciamento de tarefas para gerentes de loja.

![Configurar permissões de gerenciamento de tarefas para os gerentes de armazenamento](media/HQ-POS-Tasks-Notifications-User-Permission.png)

## <a name="configure-permissions-for-employees"></a>Configurar permissões para funcionários

Os funcionários devem ter permissões para criar listas de tarefas, gerenciar critérios de atribuição e configurar a recorrência de qualquer lista de tarefas. Para configurar essas permissões, você atribui aos funcionários a função **Gerenciador de tarefas de varejo**.

Para configurar permissões para um funcionário, siga estas etapas.

1. Vá para **Retail e Commerce \> Funcionários \> Usuários**.
1. Selecione um funcionário.
1. Na Guia Rápida **Funções do usuário**, selecione **Atribuir funções**.
1. Na caixa de diálogo **Atribuir funções ao usuário**, selecione a função **Gerenciador de tarefas de varejo** e, em seguida, selecione **OK**.

## <a name="distribute-permissions-to-pos-clients"></a>Distribuir permissões para clientes de PDV

Para que os funcionários possam usar clientes de PDV, as permissões devem ser distribuídas e sincronizadas para esses clientes.

Para distribuir permissões para clientes de PDV, siga estas etapas.

1. Vá para **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**.
1. Selecione a agenda de distribuição **1060** (**Equipe**) e selecione **Executar agora**.
1. Selecione a agenda de distribuição **1070** (**Configuração de canal**) e selecione **Executar agora**.

## <a name="configure-pos-notifications-for-tasks"></a>Configurar notificações de PDV para tarefas

O gerenciamento de tarefas deve ser configurado de forma que as notificações estejam disponíveis no aplicativo de PDV.

Para configurar notificações de PDV para tarefas, siga estas etapas.

1. Vá para **Retail e Commerce \> Configuração de canal \> Configuração do PDV \> PDV \> Operações de PDV**.
1. Encontre a operação **1400** (**Gerenciamento de tarefas**), e marque a caixa de seleção **Habilitar notificações** da operação.

A ilustração a seguir mostra a operação **Gerenciamento de tarefas** na página **Operações de PDV**.

![Operação de gerenciamento de tarefas na página operações de PDV](media/HQ-POS-Tasks-Notifications.png)

Para obter mais informações sobre como configurar notificações POS, consulte [Mostrar notificações de ordem no ponto de venda (PDV)](notifications-pos.md).

## <a name="configure-the-tasks-tile-on-a-pos-application-home-page"></a>Configurar o bloco de tarefas em uma home page do aplicativo de PDV

Antes de configurar o bloco **Tarefas** na página inicial de um aplicativo de PDV, consulte [Layouts de tela do ponto de venda (PDV)](pos-screen-layouts.md) para obter informações sobre como configurar e adicionar novos botões a um layout de tela PDV.

Para configurar o bloco **Tarefas** em uma página inicial do aplicativo de PDV, siga estas etapas.

1. Vá para **Varejo e Comércio \> Configuração de canal \> Configuração do PDV \> PDV \> Layouts da tela**.
1. Selecione um layout de tela, selecione um tamanho de layout e selecione uma grade de botões.
1. Na Guia Rápida **Grades de botões**, selecione **Designer** para editar a grade de botões selecionada.
1. Adicione um bloco de **Tarefas** à seção apropriada da página inicial.

A ilustração a seguir mostra um exemplo de bloco **Tarefas** em uma página inicial do PDV.

![Bloco de tarefas em uma página inicial do PDV](media/POS-home-screen-tasks-button-image.png)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do gerenciamento de tarefas](task-mgmt-overview.md)

[Criar listas de tarefas e adicionar tarefas](task-mgmt-create-lists.md)

[Atribuir listas de tarefas a lojas ou funcionários](task-mgmt-assign-lists.md)

[Gerenciamento de tarefas em PDV](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
