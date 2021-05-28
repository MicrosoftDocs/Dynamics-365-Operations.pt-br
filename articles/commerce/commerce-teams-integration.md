---
title: Visão geral da integração do Dynamics 365 Commerce e do Microsoft Teams
description: Este tópico apresenta uma visão geral da integração do Microsoft Dynamics 365 Commerce e do Microsoft Teams.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c22af9bf76818dd682b4147c3677cd1715e4cbf8
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021980"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-overview"></a>Visão geral da integração do Dynamics 365 Commerce e do Microsoft Teams

[!include [banner](includes/banner.md)]

Este tópico apresenta uma visão geral da integração do Microsoft Dynamics 365 Commerce e do Microsoft Teams.

O Dynamics 365 Commerce está sendo integrado ao Teams para ajudar os clientes e seus funcionários a melhorar a produtividade, sincronizando o gerenciamento de tarefas entre os dois aplicativos. O gerenciamento integrado de tarefas que a integração do Commerce e do Teams oferece aos gerentes de armazenamento e funcionários criam listas de tarefas, atribuem tarefas a vários armazenamentos e rastreiam o status das tarefas em armazenamento, de qualquer um dos aplicativos.

A integração do Commerce e do Teams está disponível a partir da versão 10.0.18. do Commerce.

## <a name="key-features"></a>Recursos principais

Estes são alguns dos recursos principais que a integração do Commerce e do Microsoft Teams fornece:

- Provisionar o Teams tirando proveito das informações bem definidas do Commerce, como a estrutura organizacional e informações sobre armazenamentos, trabalhadores, permissões e contexto comercial.
- Sincronize facilmente as alterações contínuas (por exemplo, a adição de novos armazenamentos ou contratação de novos funcionários) entre Commerce e Teams, mas mantenha o comércio como a origem mestre de dados da estrutura organizacional.
- Integre o gerenciamento de tarefas entre Commerce e o Teams para ajudar a armazenar trabalhadores, gerentes de armazenamento, gerentes regionais e gerentes de comunicações manipule o gerenciamento de tarefas de qualquer um dos aplicativos.

## <a name="prerequisites-for-using-integration-features"></a>Pré-requisitos para o uso de recursos de integração

Os pré-requisitos a seguir devem estar disponíveis para que você possa começar a usar os recursos de integração do Microsoft Teams:

- Licença padrão comercial da Microsoft 365 (esta licença inclui o Teams.)
- Contas do Azure Active Directory( Azure AD) para todos os gerentes e trabalhadores de armazenamento
- Sistemas de ponto de venda (PDV) configurados com a autenticação do Azure AD

## <a name="conceptual-architecture"></a>Arquitetura conceitual

A ilustração a seguir mostra a arquitetura conceitual da integração do Dynamics 365 Commerce e do Microsoft Teams, usando um armazenamento de San Francisco como um exemplo. O aplicativo PDV do Teams e do Commerce usam o Microsoft Planner como um repositório, de forma que as tarefas publicadas do Teams apareçam no aplicativo PDV e as tarefas ad hoc criadas pelos gerentes de armazenamento no aplicativo PDV apareçam no Teams, resultando em uma experiência de gerenciamento de tarefas perfeito entre os aplicativos.    

![Arquitetura de integração do Commerce e do Teams](media/d365-commerce-teams-integration-conceptual-architecture.png)

## <a name="additional-resources"></a>Recursos adicionais

[Habilitar a integração do Dynamics 365 Commerce e do Microsoft Teams](enable-teams-integration.md)

[Provisionar o Microsoft Teams a partir do Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Sincronizar o gerenciamento de tarefas entre o PDV do Microsoft Teams e do Dynamics 365 Commerce](synchronize-tasks-teams-pos.md)

[Gerenciar funções do usuário no Microsoft Teams](manage-user-roles-teams.md)

[Mapear lojas e equipes, se houver equipes pré-existentes no Microsoft Teams](map-stores-existing-teams.md)

[Perguntas frequentes sobre a integração do Dynamics 365 Commerce e do Microsoft Teams](teams-integration-faq.md)
