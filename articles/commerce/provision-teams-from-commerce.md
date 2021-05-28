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
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1cb28fb50bdc972d1dae6d03a45f70a2f3a63357
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022437"
---
# <a name="provision-microsoft-teams-from-dynamics-365-commerce"></a><span data-ttu-id="795a6-103">Provisionar o Microsoft Teams a partir do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="795a6-103">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="795a6-104">Este tópico descreve como provisionar o Microsoft Teams usando dados organizacionais do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="795a6-104">This topic describes how to provision Microsoft Teams by using organizational data from Dynamics 365 Commerce.</span></span>

<span data-ttu-id="795a6-105">O Dynamics 365 Commerce oferece uma maneira fácil de provisionar o Teams, se você ainda não tiver configurado equipes para suas lojas de varejo.</span><span class="sxs-lookup"><span data-stu-id="795a6-105">Dynamics 365 Commerce offers an easy way to provision Teams if you haven't yet set up teams for your retail stores there.</span></span> <span data-ttu-id="795a6-106">Ao usufruir das informações bem definidas do Commerce que você deseja usar no Teams, é possível ajudar os funcionários da loja a ingressarem no Teams.</span><span class="sxs-lookup"><span data-stu-id="795a6-106">By taking advantage of well-defined information from Commerce that you want to use in Teams, you can help your store employees get started in Teams.</span></span> <span data-ttu-id="795a6-107">Essas informações incluem a hierarquia organizacional, os nomes da loja, as informações sobre funcionários e o Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="795a6-107">This information includes the organizational hierarchy, store names, employee information, and Azure Active Directory (Azure AD) accounts.</span></span> 

<span data-ttu-id="795a6-108">O processo de provisionamento do Teams tem duas etapas principais:</span><span class="sxs-lookup"><span data-stu-id="795a6-108">The process of provisioning Teams has two main steps:</span></span>

1. <span data-ttu-id="795a6-109">No Teams, crie uma equipe para cada loja de varejo e adicione trabalhadores de loja como membros da equipe apropriada.</span><span class="sxs-lookup"><span data-stu-id="795a6-109">In Teams, create a team for each retail store, and add store workers as members of the appropriate team.</span></span> <span data-ttu-id="795a6-110">Se um funcionário estiver associado a mais de uma loja de varejo, o membro da equipe refletirá esse fato.</span><span class="sxs-lookup"><span data-stu-id="795a6-110">If an employee is associated with more than one retail store, team membership will reflect that fact.</span></span> <span data-ttu-id="795a6-111">Uma equipe de comunicação que inclui gerentes regionais como membros será criada para ajudar a publicar tarefas do Teams.</span><span class="sxs-lookup"><span data-stu-id="795a6-111">A communications team that includes regional managers as members will be created to help publish tasks from Teams.</span></span>
1. <span data-ttu-id="795a6-112">Carregue sua hierarquia organizacional do Commerce para o Teams.</span><span class="sxs-lookup"><span data-stu-id="795a6-112">Upload your organizational hierarchy from Commerce to Teams.</span></span>

## <a name="provision-teams-in-commerce-headquarters"></a><span data-ttu-id="795a6-113">Provisionar o Teams no Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="795a6-113">Provision Teams in Commerce headquarters</span></span>

<span data-ttu-id="795a6-114">Antes de provisionar o Microsoft Teams, conclua estas tarefas:</span><span class="sxs-lookup"><span data-stu-id="795a6-114">Before you provision Microsoft Teams, complete these tasks:</span></span>

- <span data-ttu-id="795a6-115">Confirme se todos os gerentes regionais foram criados com os gerentes de comunicações.</span><span class="sxs-lookup"><span data-stu-id="795a6-115">Confirm that all regional managers have been made communications managers.</span></span>
- <span data-ttu-id="795a6-116">Confirme se a conta do Azure de todos os gerentes de loja e trabalhador foi associada ao registro de trabalhador do gerente ou do trabalhador no Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="795a6-116">Confirm that the Azure account of every store manager and worker has been associated with that manager's or worker's worker record in Commerce headquarters.</span></span>

<span data-ttu-id="795a6-117">Para provisionar o Teams no Commerce headquarters, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="795a6-117">To provision Teams in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="795a6-118">Vá para **Varejo e Comércio \> Configuração do canal \> Configuração de integração do Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="795a6-118">Go to **Retail and Commerce \> Channel setup \> Microsoft Teams Integration Configuration**.</span></span>
1. <span data-ttu-id="795a6-119">No Painel de Ações, selecione **Provisionar teams**.</span><span class="sxs-lookup"><span data-stu-id="795a6-119">On the Action Pane, select **Provision teams**.</span></span> <span data-ttu-id="795a6-120">Um trabalho em lotes chamado **Provisão do Teams** é criado.</span><span class="sxs-lookup"><span data-stu-id="795a6-120">A batch job that is named **Teams provision** is created.</span></span>
1. <span data-ttu-id="795a6-121">Vá para **Administração do sistema \> Consultas \> Trabalhos em lotes**, e localize o trabalho mais recente com a descrição **Provisão do Teams**.</span><span class="sxs-lookup"><span data-stu-id="795a6-121">Go to **System administration \> Inquiries \> Batch jobs**, and find the most recent job that has the description **Teams provision**.</span></span> <span data-ttu-id="795a6-122">Aguarde até que a execução do trabalho tenha sido concluída.</span><span class="sxs-lookup"><span data-stu-id="795a6-122">Wait until this job has finished running.</span></span>

> [!TIP]
> <span data-ttu-id="795a6-123">Se nenhum dos gerentes regionais, gerentes de loja e trabalhadores de loja tiverem sido associados a uma licença do Teams, você poderá receber a seguinte mensagem de erro: "Falha ao recuperar as categorias de SKU aplicáveis ao usuário".</span><span class="sxs-lookup"><span data-stu-id="795a6-123">If none of your regional managers, store managers, and store workers have been associated with a Teams license, you might receive the following error message: "Failed to retrieve appliable Sku categories for the user."</span></span> <span data-ttu-id="795a6-124">Para corrigir o problema, selecione **Sincronizar equipes e membros** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="795a6-124">To correct the issue, select **Sync teams and members** on the Action Pane.</span></span>

<!-- ![Dynamics 365 Commerce - Teams integration configuration](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)-->

## <a name="validate-teams-provisioning-in-the-teams-admin-center"></a><span data-ttu-id="795a6-125">Validar provisionamento do Teams no centro de administração do Teams</span><span class="sxs-lookup"><span data-stu-id="795a6-125">Validate Teams provisioning in the Teams admin center</span></span>

<span data-ttu-id="795a6-126">Para validar o provisionamento do Microsoft Teams no centro de administração do Microsoft Teams, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="795a6-126">To validate Microsoft Teams provisioning in the Microsoft Teams admin center, follow these steps.</span></span>
    
1. <span data-ttu-id="795a6-127">Vá para o [centro de administração do Teams](https://admin.teams.microsoft.com/)e entre como administrador do seu locatário de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="795a6-127">Go to the [Teams admin center](https://admin.teams.microsoft.com/), and sign in as the administrator of your e-commerce tenant.</span></span>
1. <span data-ttu-id="795a6-128">No painel de navegação esquerdo, selecione **Teams** para expandi-lo e selecione **Gerenciar equipes**.</span><span class="sxs-lookup"><span data-stu-id="795a6-128">In the left navigation pane, select **Teams** to expand it, and then select **Manage teams**.</span></span>
1. <span data-ttu-id="795a6-129">Confirme se uma equipe foi criada para cada loja de varejo do Commerce.</span><span class="sxs-lookup"><span data-stu-id="795a6-129">Confirm that one team has been created for each Commerce retail store.</span></span>
1. <span data-ttu-id="795a6-130">Selecione uma equipe e confirme se os trabalhadores da loja foram adicionados a ela como membros.</span><span class="sxs-lookup"><span data-stu-id="795a6-130">Select a team, and confirm that store workers have been added to it as members.</span></span>
1. <span data-ttu-id="795a6-131">No painel de navegação esquerdo, selecione **Usuários** e confirme se todos os funcionários da loja em todas as lojas foram adicionados como usuários.</span><span class="sxs-lookup"><span data-stu-id="795a6-131">In the left navigation pane, select **Users**, and confirm that all store employees in all stores have been added as users.</span></span>

<span data-ttu-id="795a6-132">A ilustração a seguir mostra um exemplo da página **Gerenciar equipes** no centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="795a6-132">The following illustration shows an example of the **Manage teams** page in the Teams admin center.</span></span>

![Exemplo da página Gerenciar equipes no centro de administração do Teams](media/Teams-FLW-Admin-Teams.png)

## <a name="upload-a-commerce-organizational-hierarchy-to-teams"></a><span data-ttu-id="795a6-134">Carregue sua hierarquia organizacional do Commerce para o Teams</span><span class="sxs-lookup"><span data-stu-id="795a6-134">Upload a Commerce organizational hierarchy to Teams</span></span>
    
<span data-ttu-id="795a6-135">A hierarquia organizacional do Commerce pode ser usada no Microsoft Teams para publicar tarefas em todas as lojas selecionadas que usam a mesma estrutura hierárquica.</span><span class="sxs-lookup"><span data-stu-id="795a6-135">The Commerce organizational hierarchy can be used in Microsoft Teams to publish tasks to all or selected stores that use the same hierarchy structure.</span></span>

<span data-ttu-id="795a6-136">Para carregar uma hierarquia organizacional do Commerce no Teams, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="795a6-136">To upload a Commerce organizational hierarchy to Teams, follow these steps.</span></span>
    
1. <span data-ttu-id="795a6-137">No Commerce headquarters, vá para **Varejo e Comércio \> Configuração do canal \> Configuração de integração do Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="795a6-137">In Commerce headquarters, go to **Retail and Commerce \> Channel setup \> Microsoft Teams Integration Configuration**.</span></span>
1. <span data-ttu-id="795a6-138">Selecione **Baixar hierarquia de destino** e, em seguida, selecione **Lojas de Varejo por Região** para baixar um arquivo CSV (valores separados por vírgula) da hierarquia organizacional.</span><span class="sxs-lookup"><span data-stu-id="795a6-138">Select **Download targeting hierarchy**, and then select **Retail Stores by Region** to download a comma-separated values (CSV) file of the organizational hierarchy.</span></span>
1. <span data-ttu-id="795a6-139">Instale o módulo Microsoft Teams PowerShell seguindo as etapas em [Instalar o Microsoft Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="795a6-139">Install the Microsoft Teams PowerShell module by following the steps in [Install Microsoft Teams PowerShell](/microsoftteams/teams-powershell-install).</span></span>
1. <span data-ttu-id="795a6-140">Quando for solicitada na janela Teams PowerShell, entre usando a conta de administrador do seu locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="795a6-140">When you're prompted in the Teams PowerShell window, sign in by using the administrator account for your Azure AD tenant.</span></span>
1. <span data-ttu-id="795a6-141">Siga as etapas em [Configurar sua hierarquia de destino da equipe](/microsoftteams/set-up-your-team-hierarchy) para carregar o arquivo CSV para a hierarquia de destino.</span><span class="sxs-lookup"><span data-stu-id="795a6-141">Follow the steps in [Set up your team targeting hierarchy](/microsoftteams/set-up-your-team-hierarchy) to upload the CSV file for the targeting hierarchy.</span></span>

## <a name="verify-that-the-organizational-hierarchy-was-uploaded-to-teams"></a><span data-ttu-id="795a6-142">Verificar se a hierarquia organizacional foi carregada para o Teams</span><span class="sxs-lookup"><span data-stu-id="795a6-142">Verify that the organizational hierarchy was uploaded to Teams</span></span>

<span data-ttu-id="795a6-143">Para verificar se a hierarquia organizacional foi carregada para o Microsoft Teams, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="795a6-143">To verify that the organizational hierarchy was uploaded to Microsoft Teams, follow these steps.</span></span>

1. <span data-ttu-id="795a6-144">Entre no Teams como um gerente de comunicações.</span><span class="sxs-lookup"><span data-stu-id="795a6-144">Sign in to Teams as a communications manager.</span></span>
1. <span data-ttu-id="795a6-145">No painel de navegação esquerdo, selecione **Tarefas do Planejador**.</span><span class="sxs-lookup"><span data-stu-id="795a6-145">In the left navigation pane, select **Tasks by Planner**.</span></span>
1. <span data-ttu-id="795a6-146">Na guia **Listas publicadas**, crie uma nova lista que tenha uma tarefa fictícia.</span><span class="sxs-lookup"><span data-stu-id="795a6-146">On the **Published lists** tab, create a new list that has a dummy task.</span></span>
1. <span data-ttu-id="795a6-147">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="795a6-147">Select **Publish**.</span></span> <span data-ttu-id="795a6-148">A hierarquia organizacional deverá aparecer na caixa de diálogo **Selecionar quem publicar em**, conforme mostrado no exemplo da ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="795a6-148">The organizational hierarchy should appear in the **Select who to publish to** dialog box, as shown in the example in the following illustration.</span></span>

![Exemplo de uma hierarquia organizacional na caixa de diálogo Selecionar quem publicar em](media/Microsoft-teams-verify-org-hierarchy.png)

## <a name="additional-resources"></a><span data-ttu-id="795a6-150">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="795a6-150">Additional resources</span></span>

[<span data-ttu-id="795a6-151">Visão geral de integração do Dynamics 365 Commerce e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="795a6-151">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="795a6-152">Habilitar a integração do Dynamics 365 Commerce e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="795a6-152">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="795a6-153">Sincronizar o gerenciamento de tarefas entre o PDV do Microsoft Teams e do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="795a6-153">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="795a6-154">Gerenciar funções do usuário no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="795a6-154">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="795a6-155">Mapear lojas e equipes, se houver equipes pré-existentes no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="795a6-155">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="795a6-156">Perguntas frequentes sobre a integração do Dynamics 365 Commerce e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="795a6-156">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)