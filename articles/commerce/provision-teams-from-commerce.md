---
title: Provisionar o Microsoft Teams a partir do Dynamics 365 Commerce
description: Este tópico descreve como provisionar o Microsoft Teams usando dados organizacionais do Dynamics 365 Commerce.
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
ms.openlocfilehash: 54c85d1b6b51b7b2608200a7fa8e343ac6d008d0
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690491"
---
# <a name="provision-microsoft-teams-from-dynamics-365-commerce"></a>Provisionar o Microsoft Teams a partir do Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este tópico descreve como provisionar o Microsoft Teams usando dados organizacionais do Dynamics 365 Commerce.

O Dynamics 365 Commerce oferece uma maneira fácil de provisionar o Teams, se você ainda não tiver configurado equipes para suas lojas de varejo. Ao usufruir das informações bem definidas do Commerce que você deseja usar no Teams, é possível ajudar os funcionários da loja a ingressarem no Teams. Essas informações incluem a hierarquia organizacional, os nomes da loja, as informações sobre funcionários e o Azure Active Directory (Azure AD). 

O processo de provisionamento do Teams tem duas etapas principais:

1. No Teams, crie uma equipe para cada loja de varejo e adicione trabalhadores de loja como membros da equipe apropriada. Se um funcionário estiver associado a mais de uma loja de varejo, o membro da equipe refletirá esse fato. Uma equipe de comunicação que inclui gerentes regionais como membros será criada para ajudar a publicar tarefas do Teams.
1. Carregue sua hierarquia organizacional do Commerce para o Teams.

## <a name="provision-teams-in-commerce-headquarters"></a>Provisionar o Teams no Commerce Headquarters

Antes de provisionar o Microsoft Teams, conclua estas tarefas:

- Confirme se todos os gerentes regionais foram criados com os gerentes de comunicações.
- Confirme se a conta do Azure de todos os gerentes de loja e trabalhador foi associada ao registro de trabalhador do gerente ou do trabalhador no Commerce Headquarters.

Para provisionar o Teams no Commerce headquarters, siga estas etapas:

1. Acesse **Varejo e Comércio \> Configuração do canal \> Configuração de integração do Microsoft Teams**.
1. No Painel de Ações, selecione **Provisionar teams**. Um trabalho em lotes chamado **Provisão do Teams** é criado.
1. Acesse **Administração do sistema \> Consultas \> Trabalhos em lotes**, e localize o trabalho mais recente com a descrição **Provisão do Teams**. Aguarde até que a execução do trabalho tenha sido concluída.

> [!TIP]
> Se nenhum dos gerentes regionais, gerentes de loja e trabalhadores de loja tiverem sido associados a uma licença do Teams, você poderá receber a seguinte mensagem de erro: "Falha ao recuperar as categorias de SKU aplicáveis ao usuário". Para corrigir o problema, selecione **Sincronizar equipes e membros** no Painel de Ações.

<!-- ![Dynamics 365 Commerce - Teams integration configuration.](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)-->

## <a name="validate-teams-provisioning-in-the-teams-admin-center"></a>Validar provisionamento do Teams no centro de administração do Teams

Para validar o provisionamento do Microsoft Teams no centro de administração do Microsoft Teams, siga estas etapas.
    
1. Acesse o [centro de administração do Teams](https://admin.teams.microsoft.com/)e entre como administrador do seu locatário de comércio eletrônico.
1. No painel de navegação esquerdo, selecione **Teams** para expandi-lo e selecione **Gerenciar equipes**.
1. Confirme se uma equipe foi criada para cada loja de varejo do Commerce.
1. Selecione uma equipe e confirme se os trabalhadores da loja foram adicionados a ela como membros.
1. No painel de navegação esquerdo, selecione **Usuários** e confirme se todos os funcionários da loja em todas as lojas foram adicionados como usuários.

A ilustração a seguir mostra um exemplo da página **Gerenciar equipes** no centro de administração do Teams.

![Exemplo da página Gerenciar equipes no centro de administração do Teams.](media/Teams-FLW-Admin-Teams.png)

## <a name="upload-a-commerce-organizational-hierarchy-to-teams"></a>Carregue sua hierarquia organizacional do Commerce para o Teams
    
A hierarquia organizacional do Commerce pode ser usada no Microsoft Teams para publicar tarefas em todas as lojas selecionadas que usam a mesma estrutura hierárquica.

Para carregar uma hierarquia organizacional do Commerce no Teams, siga estas etapas.
    
1. No Commerce headquarters, Acesse **Varejo e Comércio \> Configuração do canal \> Configuração de integração do Microsoft Teams**.
1. Selecione **Baixar hierarquia de destino** e, em seguida, selecione **Lojas de Varejo por Região** para baixar um arquivo CSV (valores separados por vírgula) da hierarquia organizacional.
1. Instale o módulo Microsoft Teams PowerShell seguindo as etapas em [Instalar o Microsoft Teams PowerShell](/microsoftteams/teams-powershell-install).
1. Quando for solicitada na janela Teams PowerShell, entre usando a conta de administrador do seu locatário do Azure AD.
1. Siga as etapas em [Configurar sua hierarquia de destino da equipe](/microsoftteams/set-up-your-team-hierarchy) para carregar o arquivo CSV para a hierarquia de destino.

## <a name="verify-that-the-organizational-hierarchy-was-uploaded-to-teams"></a>Verificar se a hierarquia organizacional foi carregada para o Teams

Para verificar se a hierarquia organizacional foi carregada para o Microsoft Teams, siga estas etapas.

1. Entre no Teams como um gerente de comunicações.
1. No painel de navegação esquerdo, selecione **Tarefas do Planejador**.
1. Na guia **Listas publicadas**, crie uma nova lista que tenha uma tarefa fictícia.
1. Selecione **Publicar**. A hierarquia organizacional deverá aparecer na caixa de diálogo **Selecionar quem publicar em**, conforme mostrado no exemplo da ilustração a seguir.

![Exemplo de uma hierarquia organizacional na caixa de diálogo Selecionar quem publicar em.](media/Microsoft-teams-verify-org-hierarchy.png)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de integração do Dynamics 365 Commerce e do Microsoft Teams](commerce-teams-integration.md)

[Habilitar a integração do Dynamics 365 Commerce e do Microsoft Teams](enable-teams-integration.md)

[Sincronizar o gerenciamento de tarefas entre o PDV do Microsoft Teams e do Dynamics 365 Commerce](synchronize-tasks-teams-pos.md)

[Gerenciar funções do usuário no Microsoft Teams](manage-user-roles-teams.md)

[Mapear lojas e equipes, se houver equipes pré-existentes no Microsoft Teams](map-stores-existing-teams.md)

[Perguntas frequentes sobre a integração do Dynamics 365 Commerce e do Microsoft Teams](teams-integration-faq.md)