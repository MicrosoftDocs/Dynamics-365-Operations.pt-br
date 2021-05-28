---
title: Perguntas frequentes sobre a integração do Dynamics 365 Commerce e do Microsoft Teams
description: Este tópico fornece respostas às perguntas frequentes sobre a integração do Microsoft Dynamics 365 Commerce e do Microsoft Teams.
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
ms.openlocfilehash: 3fc7cff0a3f8d0fbfb196ec5951b138088afece7
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019461"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-faq"></a><span data-ttu-id="57c9f-103">Perguntas frequentes sobre a integração do Dynamics 365 Commerce e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="57c9f-103">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="57c9f-104">Este tópico fornece respostas às perguntas frequentes sobre a integração do Microsoft Dynamics 365 Commerce e do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="57c9f-104">This topic provides answers to frequently asked questions regarding Microsoft Dynamics 365 Commerce and Microsoft Teams integration.</span></span>

### <a name="who-in-the-store-becomes-an-owner-of-a-team-while-provisioning-teams-from-commerce"></a><span data-ttu-id="57c9f-105">Quem na loja se tornará um proprietário de uma equipe ao provisionar o Teams do Commerce?</span><span class="sxs-lookup"><span data-stu-id="57c9f-105">Who in the store becomes an owner of a team while provisioning Teams from Commerce?</span></span> 

<span data-ttu-id="57c9f-106">Todos os gerentes de loja são adicionados automaticamente como proprietários ao grupo de equipe correspondente para que possam executar operações, como adicionar um canal privado e adicionar ou excluir membros.</span><span class="sxs-lookup"><span data-stu-id="57c9f-106">All store managers are automatically added as owners to the corresponding team group so that they can perform operations such as adding a private channel and adding or deleting members.</span></span> 

### <a name="how-do-i-assign-the-communications-manager-role-to-an-employee-in-commerce-headquarters"></a><span data-ttu-id="57c9f-107">Como faço para atribuir a função "gerente de comunicações" a um funcionário na sede do Commerce?</span><span class="sxs-lookup"><span data-stu-id="57c9f-107">How do I assign the "communications manager" role to an employee in Commerce headquarters?</span></span> 

<span data-ttu-id="57c9f-108">Os gerentes de comunicação do Microsoft Teams têm a capacidade de criar e publicar listas de tarefas.</span><span class="sxs-lookup"><span data-stu-id="57c9f-108">Communication managers in Microsoft Teams have the ability to create and publish task lists.</span></span> <span data-ttu-id="57c9f-109">Os funcionários da organização que precisam se tornar gerentes de comunicação devem ter a função "gerente de tarefas de varejo" atribuída a eles na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="57c9f-109">Organization employees who need to become communication managers must have the "retail task manager" role assigned to them in Commerce headquarters.</span></span>

<span data-ttu-id="57c9f-110">Para atribuir a função de gerente de tarefas de varejo a um funcionário na sede do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="57c9f-110">To assign the retail task manager role to an employee in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="57c9f-111">Vá para **Retail e Commerce \> Funcionários \> Usuários**.</span><span class="sxs-lookup"><span data-stu-id="57c9f-111">Go to **Retail and Commerce \> Employees \> Users**.</span></span>
1. <span data-ttu-id="57c9f-112">Selecione um funcionário.</span><span class="sxs-lookup"><span data-stu-id="57c9f-112">Select an employee.</span></span>
1. <span data-ttu-id="57c9f-113">Na Guia Rápida **Funções do usuário**, selecione **Atribuir funções**.</span><span class="sxs-lookup"><span data-stu-id="57c9f-113">On the **User's roles** FastTab, select **Assign roles**.</span></span>
1. <span data-ttu-id="57c9f-114">Na caixa de diálogo **Atribuir funções ao usuário**, selecione a função **Gerenciador de tarefas de varejo** e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="57c9f-114">In the **Assign roles to user** dialog box, select the **Retail task manager** role, and then select **OK**.</span></span>

### <a name="how-do-i-make-a-specific-organization-hierarchy-available-to-upload-into-microsoft-teams"></a><span data-ttu-id="57c9f-115">Como posso disponibilizar uma hierarquia da organização específica para carregar no Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="57c9f-115">How do I make a specific organization hierarchy available to upload into Microsoft Teams?</span></span>

<span data-ttu-id="57c9f-116">Na sede do Commerce, a hierarquia de cada organização é associada a uma ou mais finalidades.</span><span class="sxs-lookup"><span data-stu-id="57c9f-116">In Commerce headquarters, every organization's hierarchy is associated with one or more purposes.</span></span> <span data-ttu-id="57c9f-117">Verifique se a hierarquia para a qual você deseja provisionar o Microsoft Teams tem a finalidade **Relatório de varejo** associada a ela, conforme mostrado na imagem de exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="57c9f-117">Make sure the hierarchy that you want to provision into Microsoft Teams has the **Retail reporting** purpose associated with it, as shown in the following example image.</span></span> 

![Exemplo de uma finalidade de hierarquia organizacional na sede do Commerce](media/d365-commerce-organization-hierarchies-purpose.png)

### <a name="how-do-i-enable-retail-store-workers-to-sign-in-to-commerce-point-of-sale-pos-using-azure-active-directory-azure-ad"></a><span data-ttu-id="57c9f-119">Como faço para habilitar trabalhadores de loja de varejo a entrar no ponto de venda (PDV) do Commerce usando o Azure Active Directory (Azure AD)?</span><span class="sxs-lookup"><span data-stu-id="57c9f-119">How do I enable retail store workers to sign in to Commerce point of sale (POS) using Azure Active Directory (Azure AD)?</span></span>

<span data-ttu-id="57c9f-120">Para obter informações sobre como configurar a experiência de entrada no PDV do Commerce para usar a autenticação do Azure AD, consulte [Habilitar a autenticação do Azure Active Directory para entrada no PDV](aad-pos-logon.md).</span><span class="sxs-lookup"><span data-stu-id="57c9f-120">For information about how to configure the Commerce POS sign-in experience to use Azure AD authentication, see [Enable Azure Active Directory authentication for POS sign-in](aad-pos-logon.md).</span></span>

### <a name="how-do-i-map-stores-and-corresponding-teams-in-commerce-headquarters-if-my-organization-has-already-created-teams-in-microsoft-teams"></a><span data-ttu-id="57c9f-121">Como faço para mapear lojas e equipes correspondentes na sede do Commerce se minha organização já tiver criado equipes no Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="57c9f-121">How do I map stores and corresponding teams in Commerce headquarters if my organization has already created teams in Microsoft Teams?</span></span>

<span data-ttu-id="57c9f-122">Para obter informações sobre como mapear lojas e equipes se houver equipes pré-existentes, consulte [Mapear lojas e equipes correspondentes caso sua organização tenha equipes pré-existentes no Microsoft Teams](map-stores-existing-teams.md).</span><span class="sxs-lookup"><span data-stu-id="57c9f-122">For information on how to map stores and teams if there are pre-existing teams, see [Map stores and corresponding teams if your organization has pre-existing teams in Microsoft Teams](map-stores-existing-teams.md).</span></span>

### <a name="how-do-i-clear-the-microsoft-graph-api-token-stored-in-the-session-storage"></a><span data-ttu-id="57c9f-123">Como faço para limpar o token da API do Microsoft Graph armazenado no armazenamento da sessão?</span><span class="sxs-lookup"><span data-stu-id="57c9f-123">How do I clear the Microsoft Graph API token stored in the session storage?</span></span>

<span data-ttu-id="57c9f-124">Um usuário que tiver entrado no ponto de venda (PDV) com uma conta do Azure Active Directory (Azure AD) deverá sair do PDV ou fechar o aplicativo para limpar o armazenamento da sessão.</span><span class="sxs-lookup"><span data-stu-id="57c9f-124">A user who has signed in to the point of sale (POS) with an Azure Active Directory (Azure AD) account should sign out from the POS or close the application to clear the session storage.</span></span> 

> [!TIP]
> <span data-ttu-id="57c9f-125">Uma prática recomendada é sempre fazer com que os trabalhadores de loja bloqueiem o terminal de PDV ou saiam de uma sessão quando não estiverem usando o terminal.</span><span class="sxs-lookup"><span data-stu-id="57c9f-125">A recommended best practice is to always have store workers lock the POS terminal or sign out from a session when not using the terminal.</span></span> 

### <a name="what-happens-if-a-store-doesnt-have-store-managers"></a><span data-ttu-id="57c9f-126">O que acontecerá se uma loja não tiver gerentes de loja?</span><span class="sxs-lookup"><span data-stu-id="57c9f-126">What happens if a store doesn't have store managers?</span></span>

<span data-ttu-id="57c9f-127">Se uma loja não tiver gerentes, um grupo de equipe não será criado para a loja ou no Teams.</span><span class="sxs-lookup"><span data-stu-id="57c9f-127">If a store doesn't have managers, a team group will not be created for the store or in Teams.</span></span> 

### <a name="what-happens-if-a-store-manager-leaves-the-company"></a><span data-ttu-id="57c9f-128">O que acontecerá se um gerente de loja sair da empresa?</span><span class="sxs-lookup"><span data-stu-id="57c9f-128">What happens if a store manager leaves the company?</span></span>

<span data-ttu-id="57c9f-129">Qualquer pessoa com a função de proprietário poderá adicionar um novo gerente de loja na sede do Commerce e reprovisionar o Teams para que o novo gerente tenha os privilégios necessários no Teams para o grupo.</span><span class="sxs-lookup"><span data-stu-id="57c9f-129">Anyone with the owner role can add a new store manager in Commerce headquarters and reprovision Teams so that the new manager will have the necessary privileges in Teams for the group.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="57c9f-130">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="57c9f-130">Additional resources</span></span>

[<span data-ttu-id="57c9f-131">Visão geral de integração do Dynamics 365 Commerce e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="57c9f-131">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="57c9f-132">Habilitar a integração do Dynamics 365 Commerce e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="57c9f-132">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="57c9f-133">Provisionar o Microsoft Teams desde o Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="57c9f-133">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="57c9f-134">Sincronizar o gerenciamento de tarefas entre o PDV do Microsoft Teams e do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="57c9f-134">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="57c9f-135">Gerenciar funções do usuário no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="57c9f-135">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="57c9f-136">Mapear lojas e equipes, se houver equipes pré-existentes no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="57c9f-136">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)
