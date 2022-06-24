---
title: Perguntas frequentes sobre a integração do Dynamics 365 Commerce e do Microsoft Teams
description: Este artigo fornece respostas às perguntas frequentes sobre a integração do Microsoft Dynamics 365 Commerce e do Microsoft Teams.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 02f10e446349803ce5629fed0be4176f2df2be0c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869118"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-faq"></a>Perguntas frequentes sobre a integração do Dynamics 365 Commerce e do Microsoft Teams

[!include [banner](includes/banner.md)]

Este artigo fornece respostas às perguntas frequentes sobre a integração do Microsoft Dynamics 365 Commerce e do Microsoft Teams.

### <a name="who-in-the-store-becomes-an-owner-of-a-team-while-provisioning-teams-from-commerce"></a>Quem na loja se tornará um proprietário de uma equipe ao provisionar o Teams do Commerce? 

Todos os gerentes de loja são adicionados automaticamente como proprietários ao grupo de equipe correspondente para que possam executar operações, como adicionar um canal privado e adicionar ou excluir membros. 

### <a name="how-do-i-assign-the-communications-manager-role-to-an-employee-in-commerce-headquarters"></a>Como faço para atribuir a função "gerente de comunicações" a um funcionário no Commerce headquarters? 

Os gerentes de comunicação do Microsoft Teams têm a capacidade de criar e publicar listas de tarefas. Os funcionários da organização que precisam se tornar gerentes de comunicação devem ter a função "gerente de tarefas de varejo" atribuída a eles no Commerce headquarters.

Para atribuir a função de gerente de tarefas de varejo a um funcionário no Commerce headquarters, siga estas etapas.

1. Acesse **Retail e Commerce \> Funcionários \> Usuários**.
1. Selecione um funcionário.
1. Na Guia Rápida **Funções do usuário**, selecione **Atribuir funções**.
1. Na caixa de diálogo **Atribuir funções ao usuário**, selecione a função **Gerenciador de tarefas de varejo** e, em seguida, selecione **OK**.

### <a name="how-do-i-make-a-specific-organization-hierarchy-available-to-upload-into-microsoft-teams"></a>Como posso disponibilizar uma hierarquia da organização específica para carregar no Microsoft Teams?

No Commerce headquarters, a hierarquia de cada organização é associada a uma ou mais finalidades. Verifique se a hierarquia para a qual você deseja provisionar o Microsoft Teams tem a finalidade **Relatório de varejo** associada a ela, conforme mostrado na imagem de exemplo a seguir. 

![Exemplo de uma finalidade de hierarquia organizacional no Commerce headquarters.](media/d365-commerce-organization-hierarchies-purpose.png)

### <a name="how-do-i-enable-retail-store-workers-to-sign-in-to-commerce-point-of-sale-pos-using-azure-active-directory-azure-ad"></a>Como faço para habilitar trabalhadores de loja de varejo a entrar no ponto de venda (PDV) do Commerce usando o Azure Active Directory (Azure AD)?

Para obter informações sobre como configurar a experiência de entrada no PDV do Commerce para usar a autenticação do Azure AD, consulte [Habilitar a autenticação do Azure Active Directory para entrada no PDV](aad-pos-logon.md).

### <a name="how-do-i-map-stores-and-corresponding-teams-in-commerce-headquarters-if-my-organization-has-already-created-teams-in-microsoft-teams"></a>Como faço para mapear lojas e equipes correspondentes no Commerce headquarters se minha organização já tiver criado equipes no Microsoft Teams?

Para obter informações sobre como mapear lojas e equipes se houver equipes pré-existentes, consulte [Mapear lojas e equipes correspondentes caso sua organização tenha equipes pré-existentes no Microsoft Teams](map-stores-existing-teams.md).

### <a name="how-do-i-clear-the-microsoft-graph-api-token-stored-in-the-session-storage"></a>Como faço para limpar o token da API do Microsoft Graph armazenado no armazenamento da sessão?

Um usuário que tiver entrado no ponto de venda (PDV) com uma conta do Azure Active Directory (Azure AD) deverá sair do PDV ou fechar o aplicativo para limpar o armazenamento da sessão. 

> [!TIP]
> Uma prática recomendada é sempre fazer com que os trabalhadores de loja bloqueiem o terminal de PDV ou saiam de uma sessão quando não estiverem usando o terminal. 

### <a name="what-happens-if-a-store-doesnt-have-store-managers"></a>O que acontecerá se uma loja não tiver gerentes de loja?

Se uma loja não tiver gerentes, um grupo de equipe não será criado para a loja ou no Teams. 

### <a name="what-happens-if-a-store-manager-leaves-the-company"></a>O que acontecerá se um gerente de loja sair da empresa?

Qualquer pessoa com a função de proprietário poderá adicionar um novo gerente de loja no Commerce headquarters e reprovisionar o Teams para que o novo gerente tenha os privilégios necessários no Teams para o grupo. 

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de integração do Dynamics 365 Commerce e do Microsoft Teams](commerce-teams-integration.md)

[Habilitar a integração do Dynamics 365 Commerce e do Microsoft Teams](enable-teams-integration.md)

[Provisionar o Microsoft Teams desde o Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Sincronizar o gerenciamento de tarefas entre o PDV do Microsoft Teams e do Dynamics 365 Commerce](synchronize-tasks-teams-pos.md)

[Gerenciar funções do usuário no Microsoft Teams](manage-user-roles-teams.md)

[Mapear lojas e equipes, se houver equipes pré-existentes no Microsoft Teams](map-stores-existing-teams.md)
