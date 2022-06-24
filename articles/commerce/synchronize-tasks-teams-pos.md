---
title: Sincronizar o gerenciamento de tarefas entre o Microsoft Teams e o PDV do Dynamics 365 Commerce
description: Este artigo descreve como sincronizar o gerenciamento de tarefas entre o Microsoft Teams e o ponto de venda (PDV) do Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 23da56f4f6aee906aad261939d1c7ef9feac5922
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874860"
---
# <a name="synchronize-task-management-between-microsoft-teams-and-dynamics-365-commerce-pos"></a>Sincronizar o gerenciamento de tarefas entre o Microsoft Teams e o PDV do Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este artigo descreve como sincronizar o gerenciamento de tarefas entre o Microsoft Teams e o ponto de venda (PDV) do Dynamics 365 Commerce.

Uma das principais finalidades da integração do Teams é habilitar a sincronização do gerenciamento de tarefas entre o aplicativo de PDV e o Teams. Dessa forma, os funcionários do armazenamento podem usar o aplicativo de PDV ou o Teams para gerenciar tarefas e não precisam trocar os aplicativos.

Como o Planejador é usado como um repositório de tarefas no Teams, deve haver um link entre o Teams e o Dynamics 365 Commerce. Esse link é estabelecido usando uma ID de plano específica para uma determinada equipe de loja.

Os procedimentos a seguir mostram como configurar a sincronização de gerenciamento de tarefas entre os aplicativos PDV e Teams.

## <a name="publish-a-test-task-list-in-teams"></a>Publicar uma lista de tarefas de teste no Teams

O procedimento a seguir supõe que as equipes de loja estejam usando a integração do gerenciamento de tarefas do Microsoft Teams com o Commerce pela primeira vez.

Para publicar uma lista de tarefas de teste no Teams, siga estas etapas.

1. Entre no Teams como um gerente de comunicações. Normalmente, os gerentes de comunicações são usuários com a função **Gerente regional** no Commerce.
1. No painel de navegação esquerdo, selecione **Tarefas do Planejador**.
1. Na guia **Listas publicadas**, selecione **Nova lista** na parte inferior esquerda e nomeie a nova lista como **Lista de tarefas de teste**.
1. Selecione **Criar**. A nova lista aparece em **Rascunhos**.
1. Em **Título da tarefa**, conceda à primeira tarefa o título **Testando a integração do Teams**. Depois, selecione **Enter**.
1. Na lista **Rascunhos**, selecione a lista de tarefas. Em seguida, selecione **Publicar** no canto superior direito.
1. Na caixa de diálogo **Selecionar quem publicará em**, selecione as equipes que devem receber a lista de tarefas de teste.
1. Selecione **Avançar** para revisar o plano de publicação. Se for necessário fazer alterações, selecione **Voltar**. 
1. Selecione **Confirmar para continuar** e selecione **Publicar**.
1. Depois de concluída a publicação, uma mensagem na parte superior da guia **Listas publicadas** indica se a sua lista de tarefas foi entregue com êxito.

Para obter mais informações, consulte [Publicar listas de tarefas para criar e rastrear trabalho em sua organização](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df).

## <a name="link-pos-and-teams-for-task-management"></a>Vincular PDV e o Teams para o gerenciamento de tarefas

Para vincular os aplicativos de PDV e do Microsoft Teams para o gerenciamento de tarefas no Commerce headquarters, siga estas etapas.

> [!NOTE]
> Antes de tentar integrar o Gerenciamento de tarefas ao Microsoft Teams, habilite a [integração do Dynamics 365 Commerce e do Microsoft Teams](enable-teams-integration.md). 

1. Acesse **Varejo e Comércio \> Gerenciamento de tarefas \> Integração de tarefas com o Microsoft Teams**.
1. No Painel de Ações, selecione **Editar**.
1. Defina a opção **Habilitar a Integração do Gerenciamento de Tarefas** como **Sim**.
1. No Painel de ações, selecione **Salvar**.
1. No Painel de Ações, selecione **Gerenciamento de tarefas de configuração**. Você deve receber uma notificação que indique que um trabalho em lotes chamado **Provisão do Teams** está sendo criado.
1. Acesse **Administração do sistema \> Consultas \> Trabalhos em lotes**, e localize o trabalho mais recente com a descrição **Provisão do Teams**. Aguarde até que a execução do trabalho tenha sido concluída.
1. Execute o **Trabalho CDX 1070** para publicar a ID do plano e as referências da loja no Retail Server.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de integração do Dynamics 365 Commerce e do Microsoft Teams](commerce-teams-integration.md)

[Habilitar a integração do Dynamics 365 Commerce e do Microsoft Teams](enable-teams-integration.md)

[Provisionar o Microsoft Teams desde o Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Gerenciar funções do usuário no Microsoft Teams](manage-user-roles-teams.md)

[Mapear lojas e equipes, se houver equipes pré-existentes no Microsoft Teams](map-stores-existing-teams.md)

[Perguntas frequentes sobre a integração do Dynamics 365 Commerce e do Microsoft Teams](teams-integration-faq.md)
