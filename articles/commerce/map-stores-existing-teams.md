---
title: Mapear armazenamentos e equipes, se houver equipes pré-existentes no Microsoft Teams
description: Este tópico aborda como mapear armazenamentos e equipes correspondentes no Dynamics 365 Commerce headquarters, se a sua organização já tiver criado equipes no Microsoft Teams antes da integração do Commerce.
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
ms.openlocfilehash: 5a711c1057b87bd792755ef91a84d1c28879c590
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908486"
---
# <a name="map-stores-and-teams-if-there-are-pre-existing-teams-in-microsoft-teams"></a><span data-ttu-id="d3c18-103">Mapear armazenamentos e equipes, se houver equipes pré-existentes no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d3c18-103">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d3c18-104">Este tópico aborda como mapear armazenamentos e equipes correspondentes no Dynamics 365 Commerce headquarters, se a sua organização já tiver criado equipes no Microsoft Teams antes da integração do Commerce.</span><span class="sxs-lookup"><span data-stu-id="d3c18-104">This topic covers how to map stores and corresponding teams in Dynamics 365 Commerce headquarters if your organization has already created teams in Microsoft Teams before Commerce integration.</span></span>

<span data-ttu-id="d3c18-105">Sua organização pode ter equipes criadas para alguns ou todos os armazenamentos antes da integração do Dynamics 365 Commerce e do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d3c18-105">Your organization may have teams created for some or all of your stores before integrating Dynamics 365 Commerce and Microsoft Teams.</span></span> <span data-ttu-id="d3c18-106">Se esse for o caso, para estabelecer a sincronização de tarefas entre o Commerce POS e Microsoft Teams você deve fornecer o mapeamento de armazenamentos e a equipe correspondente no Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="d3c18-106">If this is the case, to establish task synchronization between Commerce POS and Microsoft Teams you must provide the mapping of stores and corresponding team in Commerce headquarters.</span></span>

## <a name="map-stores-and-corresponding-teams-in-commerce-headquarters"></a><span data-ttu-id="d3c18-107">Mapear armazenamentos e equipes correspondentes no Commerce Headquarters</span><span class="sxs-lookup"><span data-stu-id="d3c18-107">Map stores and corresponding teams in Commerce headquarters</span></span> 

<span data-ttu-id="d3c18-108">Para mapear armazenamentos e equipes correspondentes no Commerce Headquarters, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="d3c18-108">To map stores and corresponding teams in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="d3c18-109">Vá para **Administração de Sistema \> Espaço de trabalho \> Gerenciamento de dados**.</span><span class="sxs-lookup"><span data-stu-id="d3c18-109">Go to **System Administration \> Workspace \> Data management**.</span></span>
1. <span data-ttu-id="d3c18-110">Selecione **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="d3c18-110">Select **Export**.</span></span> 
1. <span data-ttu-id="d3c18-111">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="d3c18-111">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="d3c18-112">Em **Nome do grupo**, digite "Exportar mapeamento do Teams".</span><span class="sxs-lookup"><span data-stu-id="d3c18-112">Under **Group name**, enter "Export Teams mapping".</span></span>
1. <span data-ttu-id="d3c18-113">Na guia rápida **Entidades selecionadas**, selecione **Adicionar entidade**.</span><span class="sxs-lookup"><span data-stu-id="d3c18-113">On the **Selected entities** FastTab, select **Add entity**.</span></span> <span data-ttu-id="d3c18-114">A caixa de diálogo **Adicionar entidade** será exibida.</span><span class="sxs-lookup"><span data-stu-id="d3c18-114">The **Add entity** dialog box appears.</span></span>  
1. <span data-ttu-id="d3c18-115">Na lista suspensa **Nome da entidade**, selecione **Mapeamento do Teams entre a origem e a equipe**.</span><span class="sxs-lookup"><span data-stu-id="d3c18-115">In the **Entity name** drop-down list, select **Teams mapping between source and team**.</span></span>
1. <span data-ttu-id="d3c18-116">Na lista suspensa **Formato de dados de destino**, selecione **CSV**.</span><span class="sxs-lookup"><span data-stu-id="d3c18-116">In the **Target data format** drop-down list, select **CSV**.</span></span>
1. <span data-ttu-id="d3c18-117">Selecione **Adicionar** e, em seguida, selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="d3c18-117">Select **Add**, and then select **Close**.</span></span>
1. <span data-ttu-id="d3c18-118">Na parte superior esquerda, no Painel de Ações, selecione **Exportar agora**.</span><span class="sxs-lookup"><span data-stu-id="d3c18-118">On the top left under the Action Pane, select **Export now**.</span></span>
1. <span data-ttu-id="d3c18-119">Em **Status de processamento da entidade**, selecione **Baixar arquivo**.</span><span class="sxs-lookup"><span data-stu-id="d3c18-119">Under **Entity processing status**, select **Download file**.</span></span>
1. <span data-ttu-id="d3c18-120">No arquivo CSV exportado, insira valores para **SOURCETYPE**, **SOURCEID** e **TEAMID** da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d3c18-120">In the exported CSV file, enter values for **SOURCETYPE**, **SOURCEID**, and **TEAMID** as follows:</span></span>
    - <span data-ttu-id="d3c18-121">Para **SOURCETYPE**, digite "RetailStore".</span><span class="sxs-lookup"><span data-stu-id="d3c18-121">For **SOURCETYPE**, enter "RetailStore".</span></span> 
    - <span data-ttu-id="d3c18-122">Para **SOURCEID**, insira o número do armazenamento (por exemplo, "000135" para o armazenamento de San Francisco).</span><span class="sxs-lookup"><span data-stu-id="d3c18-122">For **SOURCEID**, enter the store number (for example, "000135" for the San Francisco store).</span></span> <span data-ttu-id="d3c18-123">Você pode encontrar números de armazenamento em **Varejo e Comércio \> Canais \> Armazenamentos**.</span><span class="sxs-lookup"><span data-stu-id="d3c18-123">You can find store numbers at **Retail and Commerce \> Channels \> Stores**.</span></span>
    - <span data-ttu-id="d3c18-124">Para **TEAMID**, insira a ID da equipe correspondente do Microsoft Teams (por exemplo, "5f8bc92b-6aa8-451e-85d1-3949c01ddc6c").</span><span class="sxs-lookup"><span data-stu-id="d3c18-124">For **TEAMID**, enter the corresponding team ID from Microsoft Teams (for example, "5f8bc92b-6aa8-451e-85d1-3949c01ddc6c").</span></span> <span data-ttu-id="d3c18-125">Você pode encontrar informações de ID de equipe em [admin.teams.microsoft.com](https://admin.teams.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="d3c18-125">You can find team ID information at [admin.teams.microsoft.com](https://admin.teams.microsoft.com).</span></span>
1. <span data-ttu-id="d3c18-126">Salve o arquivo CSV no computador local.</span><span class="sxs-lookup"><span data-stu-id="d3c18-126">Save the CSV file to your local machine.</span></span>
1. <span data-ttu-id="d3c18-127">Vá para **Administração do Sistema \> Espaço de Trabalho \> Gerenciamento de dados** e selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="d3c18-127">Go to **System Administration \> Workspace \> Data management**, and then select **Import**.</span></span>
1. <span data-ttu-id="d3c18-128">Na guia rápida **Entidades selecionadas**, selecione **Adicionar arquivo**.</span><span class="sxs-lookup"><span data-stu-id="d3c18-128">On the **Selected entities** FastTab, select **Add file**.</span></span> <span data-ttu-id="d3c18-129">A caixa de diálogo **Adicionar arquivo** será exibida.</span><span class="sxs-lookup"><span data-stu-id="d3c18-129">The **Add file** dialog box appears.</span></span>
1. <span data-ttu-id="d3c18-130">Na lista suspensa **Nome da entidade**, selecione **Mapeamento do Teams entre a origem e a equipe**.</span><span class="sxs-lookup"><span data-stu-id="d3c18-130">In the **Entity name** drop-down list, select **Teams mapping between source and team**.</span></span>
1. <span data-ttu-id="d3c18-131">Na lista suspensa **Formato de dados de origem**, selecione **CSV**.</span><span class="sxs-lookup"><span data-stu-id="d3c18-131">In the **Source data format** drop-down list, select **CSV**.</span></span>
1. <span data-ttu-id="d3c18-132">Selecione **Carregar e adicionar**, selecione o arquivo CSV salvo anteriormente e, em seguida, selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="d3c18-132">Select **Upload and add**, select the CSV file that you saved previously, and then select **Open**.</span></span>
1. <span data-ttu-id="d3c18-133">Na caixa de diálogo **Adicionar arquivo**, selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="d3c18-133">In the **Add file** dialog box, select **Close**.</span></span>
1. <span data-ttu-id="d3c18-134">No Painel de Ações, selecione **Salvar** e **Importar**.</span><span class="sxs-lookup"><span data-stu-id="d3c18-134">On the Action Pane, select **Save** , and then select **Import**.</span></span>

<span data-ttu-id="d3c18-135">A imagem de exemplo a seguir mostra o grupo **Exportar mapeamento do Teams** no Commerce com elementos **Adicionar entidade** e os cabeçalhos de arquivo CSV exportados.</span><span class="sxs-lookup"><span data-stu-id="d3c18-135">The following example image shows the **Export teams mapping** group in Commerce with **Add entity** elements and the exported CSV file headers highlighted.</span></span>

![Exportar grupo de mapeamento de equipes no Commerce com adicionar elementos de entidade e os cabeçalhos de arquivo CSV exportados em destaque](media/d365-commerce-data-mgmt-export-entity.png)

> [!NOTE]
> <span data-ttu-id="d3c18-137">Depois de concluir as etapas anteriores, siga as etapas em [Sincronizar gerenciamento de tarefas entre Microsoft Teams e PDV](synchronize-tasks-teams-pos.md) para sincronizar o gerenciamento de tarefas.</span><span class="sxs-lookup"><span data-stu-id="d3c18-137">After you complete the preceeding steps, follow the steps in [Synchronize task management between Microsoft Teams and POS](synchronize-tasks-teams-pos.md) to synchronize task management.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="d3c18-138">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="d3c18-138">Additional resources</span></span>

[<span data-ttu-id="d3c18-139">Visão geral de integração do Dynamics 365 Commerce e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d3c18-139">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="d3c18-140">Habilitar a integração do Dynamics 365 Commerce e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d3c18-140">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="d3c18-141">Provisionar o Microsoft Teams desde o Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="d3c18-141">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="d3c18-142">Sincronizar o gerenciamento de tarefas entre o PDV do Microsoft Teams e do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="d3c18-142">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="d3c18-143">Gerenciar funções do usuário no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d3c18-143">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="d3c18-144">Perguntas frequentes sobre a integração do Dynamics 365 Commerce e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d3c18-144">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
