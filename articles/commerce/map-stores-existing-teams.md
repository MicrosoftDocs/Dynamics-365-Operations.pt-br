---
title: Mapear armazenamentos e equipes, se houver equipes pré-existentes no Microsoft Teams
description: Este artigo aborda como mapear armazenamentos e equipes correspondentes no Dynamics 365 Commerce headquarters, se a sua organização já tiver criado equipes no Microsoft Teams antes da integração do Commerce.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 67a1a79dd74d411aa7e21000c8baaa8a069cede7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279110"
---
# <a name="map-stores-and-teams-if-there-are-pre-existing-teams-in-microsoft-teams"></a>Mapear armazenamentos e equipes, se houver equipes pré-existentes no Microsoft Teams

[!include [banner](includes/banner.md)]

Este artigo aborda como mapear armazenamentos e equipes correspondentes no Dynamics 365 Commerce headquarters, se a sua organização já tiver criado equipes no Microsoft Teams antes da integração do Commerce.

Sua organização pode ter equipes criadas para alguns ou todos os armazenamentos antes da integração do Dynamics 365 Commerce e do Microsoft Teams. Se esse for o caso, para estabelecer a sincronização de tarefas entre o Commerce POS e Microsoft Teams você deve fornecer o mapeamento de armazenamentos e a equipe correspondente no Commerce headquarters.

## <a name="map-stores-and-corresponding-teams-in-commerce-headquarters"></a>Mapear armazenamentos e equipes correspondentes no Commerce headquarters 

Para mapear armazenamentos e equipes correspondentes no Commerce headquarters, siga estas etapas.

1. Acesse **Administração de Sistema \> Espaço de trabalho \> Gerenciamento de dados**.
1. Selecione **Exportar**. 
1. No Painel de Ações, selecione **Novo**.
1. Em **Nome do grupo**, digite "Exportar mapeamento do Teams".
1. Na guia rápida **Entidades selecionadas**, selecione **Adicionar entidade**. A caixa de diálogo **Adicionar entidade** será exibida.  
1. Na lista suspensa **Nome da entidade**, selecione **Mapeamento do Teams entre a origem e a equipe**.
1. Na lista suspensa **Formato de dados de destino**, selecione **CSV**.
1. Selecione **Adicionar** e, em seguida, selecione **Fechar**.
1. Na parte superior esquerda, no Painel de Ações, selecione **Exportar agora**.
1. Em **Status de processamento da entidade**, selecione **Baixar arquivo**.
1. No arquivo CSV exportado, insira valores para **SOURCETYPE**, **SOURCEID** e **TEAMID** da seguinte maneira:
    - Para **SOURCETYPE**, digite "RetailStore". 
    - Para **SOURCEID**, insira o número do armazenamento (por exemplo, "000135" para o armazenamento de San Francisco). Você pode encontrar números de armazenamento em **Varejo e Comércio \> Canais \> Armazenamentos**.
    - Para **TEAMID**, insira a ID da equipe correspondente do Microsoft Teams (por exemplo, "5f8bc92b-6aa8-451e-85d1-3949c01ddc6c"). Você pode encontrar informações de ID de equipe em [admin.teams.microsoft.com](https://admin.teams.microsoft.com).
1. Salve o arquivo CSV no computador local.
1. Acesse **Administração do Sistema \> Espaço de Trabalho \> Gerenciamento de dados** e selecione **Importar**.
1. Na guia rápida **Entidades selecionadas**, selecione **Adicionar arquivo**. A caixa de diálogo **Adicionar arquivo** será exibida.
1. Na lista suspensa **Nome da entidade**, selecione **Mapeamento do Teams entre a origem e a equipe**.
1. Na lista suspensa **Formato de dados de origem**, selecione **CSV**.
1. Selecione **Carregar e adicionar**, selecione o arquivo CSV salvo anteriormente e, em seguida, selecione **Abrir**.
1. Na caixa de diálogo **Adicionar arquivo**, selecione **Fechar**.
1. No Painel de Ações, selecione **Salvar** e **Importar**.

A imagem de exemplo a seguir mostra o grupo **Exportar mapeamento do Teams** no Commerce com elementos **Adicionar entidade** e os cabeçalhos de arquivo CSV exportados.

![Exportar grupo de mapeamento de equipes no Commerce com adicionar elementos de entidade e os cabeçalhos de arquivo CSV exportados em destaque.](media/d365-commerce-data-mgmt-export-entity.png)

> [!NOTE]
> Depois de concluir as etapas anteriores, siga as etapas em [Sincronizar gerenciamento de tarefas entre Microsoft Teams e PDV](synchronize-tasks-teams-pos.md) para sincronizar o gerenciamento de tarefas. 

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de integração do Dynamics 365 Commerce e do Microsoft Teams](commerce-teams-integration.md)

[Habilitar a integração do Dynamics 365 Commerce e do Microsoft Teams](enable-teams-integration.md)

[Provisionar o Microsoft Teams desde o Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Sincronizar o gerenciamento de tarefas entre o PDV do Microsoft Teams e do Dynamics 365 Commerce](synchronize-tasks-teams-pos.md)

[Gerenciar funções do usuário no Microsoft Teams](manage-user-roles-teams.md)

[Perguntas frequentes sobre a integração do Dynamics 365 Commerce e do Microsoft Teams](teams-integration-faq.md)
