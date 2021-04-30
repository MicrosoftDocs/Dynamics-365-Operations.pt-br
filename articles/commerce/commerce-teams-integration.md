---
title: Visão geral da integração do Dynamics 365 Commerce e do Microsoft Teams
description: Este tópico apresenta uma visão geral da integração do Microsoft Dynamics 365 Commerce e do Microsoft Teams.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: b9289aca4f53eb2ae8f1fa06d5f80b7ee0bbab8e
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908458"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-overview"></a><span data-ttu-id="0c64d-103">Visão geral da integração do Dynamics 365 Commerce e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0c64d-103">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0c64d-104">Este tópico apresenta uma visão geral da integração do Microsoft Dynamics 365 Commerce e do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0c64d-104">This topic presents an overview of Microsoft Dynamics 365 Commerce and Microsoft Teams integration.</span></span>

<span data-ttu-id="0c64d-105">O Dynamics 365 Commerce está sendo integrado ao Teams para ajudar os clientes e seus funcionários a melhorar a produtividade, sincronizando o gerenciamento de tarefas entre os dois aplicativos.</span><span class="sxs-lookup"><span data-stu-id="0c64d-105">Dynamics 365 Commerce is integrating with Teams to help customers and their employees improve productivity by synchronizing task management between the two applications.</span></span> <span data-ttu-id="0c64d-106">O gerenciamento integrado de tarefas que a integração do Commerce e do Teams oferece aos gerentes de armazenamento e funcionários criam listas de tarefas, atribuem tarefas a vários armazenamentos e rastreiam o status das tarefas em armazenamento, de qualquer um dos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="0c64d-106">The seamless task management that Commerce and Teams integration provides lets store managers and employees create task lists, assign tasks to multiple stores, and track the status of tasks across stores, from either application.</span></span>

<span data-ttu-id="0c64d-107">A integração do Commerce e do Teams está disponível a partir da versão 10.0.18. do Commerce.</span><span class="sxs-lookup"><span data-stu-id="0c64d-107">Commerce and Teams integration is available as of the Commerce version 10.0.18 release.</span></span>

## <a name="key-features"></a><span data-ttu-id="0c64d-108">Recursos principais</span><span class="sxs-lookup"><span data-stu-id="0c64d-108">Key features</span></span>

<span data-ttu-id="0c64d-109">Estes são alguns dos recursos principais que a integração do Commerce e do Microsoft Teams fornece:</span><span class="sxs-lookup"><span data-stu-id="0c64d-109">Here are some of the key features that the Commerce and Microsoft Teams integration provides:</span></span>

- <span data-ttu-id="0c64d-110">Provisionar o Teams tirando proveito das informações bem definidas do Commerce, como a estrutura organizacional e informações sobre armazenamentos, trabalhadores, permissões e contexto comercial.</span><span class="sxs-lookup"><span data-stu-id="0c64d-110">Provision Teams by taking advantage of well-defined information from Commerce, such as the organizational structure and information about stores, workers, permissions, and business context.</span></span>
- <span data-ttu-id="0c64d-111">Sincronize facilmente as alterações contínuas (por exemplo, a adição de novos armazenamentos ou contratação de novos funcionários) entre Commerce e Teams, mas mantenha o comércio como a origem mestre de dados da estrutura organizacional.</span><span class="sxs-lookup"><span data-stu-id="0c64d-111">Easily synchronize ongoing changes (for example, the addition of new stores or hiring of new employees) between Commerce and Teams, but keep Commerce as the master source of organizational structure data.</span></span>
- <span data-ttu-id="0c64d-112">Integre o gerenciamento de tarefas entre Commerce e o Teams para ajudar a armazenar trabalhadores, gerentes de armazenamento, gerentes regionais e gerentes de comunicações manipule o gerenciamento de tarefas de qualquer um dos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="0c64d-112">Integrate task management between Commerce and Teams to help store workers, store managers, regional managers, and communications managers handle task management from either application.</span></span>

## <a name="prerequisites-for-using-integration-features"></a><span data-ttu-id="0c64d-113">Pré-requisitos para o uso de recursos de integração</span><span class="sxs-lookup"><span data-stu-id="0c64d-113">Prerequisites for using integration features</span></span>

<span data-ttu-id="0c64d-114">Os pré-requisitos a seguir devem estar disponíveis para que você possa começar a usar os recursos de integração do Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="0c64d-114">The following prerequisites must be in place before you can start to use Microsoft Teams integration features:</span></span>

- <span data-ttu-id="0c64d-115">Licença padrão comercial da Microsoft 365 (esta licença inclui o Teams.)</span><span class="sxs-lookup"><span data-stu-id="0c64d-115">Microsoft 365 Business Standard License (This license includes Teams.)</span></span>
- <span data-ttu-id="0c64d-116">Contas do Azure Active Directory( Azure AD) para todos os gerentes e trabalhadores de armazenamento</span><span class="sxs-lookup"><span data-stu-id="0c64d-116">Azure Active Directory (Azure AD) accounts for all store managers and workers</span></span>
- <span data-ttu-id="0c64d-117">Sistemas de ponto de venda (PDV) configurados com a autenticação do Azure AD</span><span class="sxs-lookup"><span data-stu-id="0c64d-117">Point of sale (POS) systems that are configured with Azure AD authentication</span></span>

## <a name="conceptual-architecture"></a><span data-ttu-id="0c64d-118">Arquitetura conceitual</span><span class="sxs-lookup"><span data-stu-id="0c64d-118">Conceptual architecture</span></span>

<span data-ttu-id="0c64d-119">A ilustração a seguir mostra a arquitetura conceitual da integração do Dynamics 365 Commerce e do Microsoft Teams, usando um armazenamento de San Francisco como um exemplo.</span><span class="sxs-lookup"><span data-stu-id="0c64d-119">The following illustration shows the conceptual architecture of Dynamics 365 Commerce and Microsoft Teams integration, using a San Francisco store as an example.</span></span> <span data-ttu-id="0c64d-120">O aplicativo PDV do Teams e do Commerce usam o Microsoft Planner como um repositório, de forma que as tarefas publicadas do Teams apareçam no aplicativo PDV e as tarefas ad hoc criadas pelos gerentes de armazenamento no aplicativo PDV apareçam no Teams, resultando em uma experiência de gerenciamento de tarefas perfeito entre os aplicativos.</span><span class="sxs-lookup"><span data-stu-id="0c64d-120">Both Teams and the Commerce POS application use Microsoft Planner as a repository so that tasks published from Teams appear in the POS application and ad hoc tasks created by store managers in the POS application appear in Teams, resulting in a seamless task management experience between the applications.</span></span>    

![Arquitetura de integração do Commerce e do Teams](media/d365-commerce-teams-integration-conceptual-architecture.png)

## <a name="additional-resources"></a><span data-ttu-id="0c64d-122">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="0c64d-122">Additional resources</span></span>

[<span data-ttu-id="0c64d-123">Habilitar a integração do Dynamics 365 Commerce e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0c64d-123">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="0c64d-124">Provisionar o Microsoft Teams a partir do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="0c64d-124">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="0c64d-125">Sincronizar o gerenciamento de tarefas entre o PDV do Microsoft Teams e do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="0c64d-125">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="0c64d-126">Gerenciar funções do usuário no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0c64d-126">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="0c64d-127">Mapear lojas e equipes, se houver equipes pré-existentes no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0c64d-127">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="0c64d-128">Perguntas frequentes sobre a integração do Dynamics 365 Commerce e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0c64d-128">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
