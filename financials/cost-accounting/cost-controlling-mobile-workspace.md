---
title: "Espaço de trabalho móvel de controle de custo"
description: "Este tópico fornece informações sobre o espaço de trabalho móvel do controle de custos. Este espaço de trabalho permite que gerentes de centro de custos exibam informações sobre desempenho de centro de custo a qualquer momento e em qualquer lugar."
author: AndersGirke
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: aevengir
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6019634c47bd97fb16ea8aaf029ea176f095b8b6
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---

# <a name="cost-controlling-mobile-workspace"></a><span data-ttu-id="e9b05-104">Espaço de trabalho móvel de controle de custo</span><span class="sxs-lookup"><span data-stu-id="e9b05-104">Cost controlling mobile workspace</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e9b05-105">Este tópico fornece informações sobre o espaço de trabalho móvel do **controle de custos**.</span><span class="sxs-lookup"><span data-stu-id="e9b05-105">This topic provides information about the **Cost controlling** mobile workspace.</span></span> <span data-ttu-id="e9b05-106">Este espaço de trabalho permite que gerentes de centro de custos exibam informações sobre desempenho de centro de custo a qualquer momento e em qualquer lugar.</span><span class="sxs-lookup"><span data-stu-id="e9b05-106">This workspace lets cost center managers view information about cost center performance anytime and anywhere.</span></span>

<span data-ttu-id="e9b05-107">O espaço de trabalho móvel é destinado a ser usado com o Microsoft Dynamics 365 do aplicativo móvel Operações Unificadas.</span><span class="sxs-lookup"><span data-stu-id="e9b05-107">This mobile workspace is intended to be used with the Microsoft Dynamics 365 for Unified Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="e9b05-108">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="e9b05-108">Overview</span></span>
<span data-ttu-id="e9b05-109">O espaço de trabalho móvel **Controle de custos** fornece uma exibição instantânea do desempenho atual dos centros de custo comparando custos reais com os custos orçados.</span><span class="sxs-lookup"><span data-stu-id="e9b05-109">The **Cost controlling** mobile workspace provides an instant view of the current performance of cost centers by comparing actual costs against the budgeted costs.</span></span> <span data-ttu-id="e9b05-110">Você pode fazer uma busca detalhada nos status de elementos de custo individuais.</span><span class="sxs-lookup"><span data-stu-id="e9b05-110">You can drill down to the status of individual cost elements.</span></span>

<span data-ttu-id="e9b05-111">Por exemplo, um funcionário recebe um convite para uma conferência internacional, mas a organização deve cobrir todas despesas de viagem.</span><span class="sxs-lookup"><span data-stu-id="e9b05-111">For example, an employee receives an invitation to an international conference, but the organization must cover all the travel expenses.</span></span> <span data-ttu-id="e9b05-112">O funcionário pergunta a seu gerente se ele pode participar da conferência.</span><span class="sxs-lookup"><span data-stu-id="e9b05-112">The employee asks his manager whether he can attend the conference.</span></span> <span data-ttu-id="e9b05-113">O gerente abre o espaço de trabalho móvel **Controle de custos** no seu dispositivo móvel para ver se dispõe do orçamento para que o funcionário possa ir à conferência.</span><span class="sxs-lookup"><span data-stu-id="e9b05-113">The manager opens the **Cost controlling** mobile workspace on her mobile device to see whether she has budget for the employee to attend the conference.</span></span>

### <a name="data-security"></a><span data-ttu-id="e9b05-114">Segurança de dados</span><span class="sxs-lookup"><span data-stu-id="e9b05-114">Data security</span></span>
<span data-ttu-id="e9b05-115">Os dados no espaço de trabalho móvel **Controle de custos** são protegidos pelas credenciais do usuário.</span><span class="sxs-lookup"><span data-stu-id="e9b05-115">The data in the **Cost controlling** mobile workspace is secured through user credentials.</span></span> <span data-ttu-id="e9b05-116">Os gerentes do centro de custos podem ver os dados somente de seus próprios centros de custo.</span><span class="sxs-lookup"><span data-stu-id="e9b05-116">Cost center managers are allowed to see data only for their own cost center.</span></span> <span data-ttu-id="e9b05-117">A segurança de nível de acesso é gerenciada no módulo **Contabilização de custos**.</span><span class="sxs-lookup"><span data-stu-id="e9b05-117">The access-level security is managed in the **Cost accounting** module.</span></span>

<span data-ttu-id="e9b05-118">Os contadores de custo definem a configuração do espaço de trabalho móvel **Controle de custos** no módulo **Contabilidade de custos**.</span><span class="sxs-lookup"><span data-stu-id="e9b05-118">Cost accountants define the configuration of the **Cost controlling** mobile workspace in the **Cost accounting** module.</span></span> <span data-ttu-id="e9b05-119">Após a publicação do espaço de trabalho no aplicativo móvel, ele fica disponível no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e9b05-119">After the workspace is published to the mobile app, it's available in the app.</span></span> <span data-ttu-id="e9b05-120">Com isso, todos os gerentes de centro de custo da organização podem ver os dados no mesmo formato.</span><span class="sxs-lookup"><span data-stu-id="e9b05-120">Therefore, all cost center managers in the organization can view data in the same format.</span></span>

### <a name="actions-views-and-links"></a><span data-ttu-id="e9b05-121">Ações, exibições e links</span><span class="sxs-lookup"><span data-stu-id="e9b05-121">Actions, views, and links</span></span>
<span data-ttu-id="e9b05-122">O espaço de trabalho móvel **Controle de custo** fornece as seguintes ações, exibições e links:</span><span class="sxs-lookup"><span data-stu-id="e9b05-122">The **Cost controlling** mobile workspace provides the following actions, views, and links:</span></span>

-   <span data-ttu-id="e9b05-123">**Ações:**</span><span class="sxs-lookup"><span data-stu-id="e9b05-123">**Actions:**</span></span>

    -   <span data-ttu-id="e9b05-124">Use **Selecione configuração** para selecionar um layout.</span><span class="sxs-lookup"><span data-stu-id="e9b05-124">Use **Select configuration** to select a layout.</span></span>
    -   <span data-ttu-id="e9b05-125">Use **Selecione o objeto de custo** para selecionar os centros de custos para filtrar dados.</span><span class="sxs-lookup"><span data-stu-id="e9b05-125">Use **Select cost object** to select the cost centers to filter data on.</span></span>
    
        > [!NOTE]
        > <span data-ttu-id="e9b05-126">Os centros de custo exibidos na lista dependem do acesso concedido no módulo **Contabilização de custos**.</span><span class="sxs-lookup"><span data-stu-id="e9b05-126">The cost centers that appear in the list depend on the access that is granted in the **Cost accounting** module.</span></span>

-   <span data-ttu-id="e9b05-127">**Exibições:** com base nas ações que são selecionadas e na configuração do módulo **Contabilidade de custos**, é possível exibir as seguintes informações nos cartões:</span><span class="sxs-lookup"><span data-stu-id="e9b05-127">**Views:** Based on the actions that are selected and the configuration in the **Cost accounting** module, you can view the following information on the cards:</span></span>

    -   <span data-ttu-id="e9b05-128">Real versus orçamento (período atual)</span><span class="sxs-lookup"><span data-stu-id="e9b05-128">Actual vs budget (current period)</span></span>
    -   <span data-ttu-id="e9b05-129">Real versus orçamento revisado (período atual)</span><span class="sxs-lookup"><span data-stu-id="e9b05-129">Actual vs revised budget (current period)</span></span>
    -   <span data-ttu-id="e9b05-130">Real vs. orçamento (período anterior)</span><span class="sxs-lookup"><span data-stu-id="e9b05-130">Actual vs budget (previous period)</span></span>
    -   <span data-ttu-id="e9b05-131">Real vs. orçamento revisado (período anterior)</span><span class="sxs-lookup"><span data-stu-id="e9b05-131">Actual vs revised budget (previous period)</span></span>
    -   <span data-ttu-id="e9b05-132">Real vs. orçamento (desde o início do ano)</span><span class="sxs-lookup"><span data-stu-id="e9b05-132">Actual vs budget (year to date)</span></span>
    -   <span data-ttu-id="e9b05-133">Real vs. orçamento revisado (desde o início do ano)</span><span class="sxs-lookup"><span data-stu-id="e9b05-133">Actual vs revised budget (year to date)</span></span>

    <span data-ttu-id="e9b05-134">Os valores são exibidos em cada cartão: Real, orçamento, variação e % variação.</span><span class="sxs-lookup"><span data-stu-id="e9b05-134">The following amounts are shown on every card: Actual, Budget, Variance, and Variance %.</span></span>

-   <span data-ttu-id="e9b05-135">**Links:**</span><span class="sxs-lookup"><span data-stu-id="e9b05-135">**Links:**</span></span>

    -   <span data-ttu-id="e9b05-136">Detalhes do período atual</span><span class="sxs-lookup"><span data-stu-id="e9b05-136">Details for current period</span></span>
    -   <span data-ttu-id="e9b05-137">Detalhes do período anterior</span><span class="sxs-lookup"><span data-stu-id="e9b05-137">Details for previous period</span></span>
    -   <span data-ttu-id="e9b05-138">Detalhes desde o início do ano</span><span class="sxs-lookup"><span data-stu-id="e9b05-138">Details for year to date</span></span>

    <span data-ttu-id="e9b05-139">Quando você seleciona um link, um cartão será mostrado para cada elemento de custo.</span><span class="sxs-lookup"><span data-stu-id="e9b05-139">When you select a link, a card is shown for each cost element.</span></span> <span data-ttu-id="e9b05-140">Os seguintes valores são mostrados em cada cartão: real, orçamento, variação de orçamento, % variação de orçamento, orçamento revisado, variação do orçamento revisado e % variação de orçamento revisado.</span><span class="sxs-lookup"><span data-stu-id="e9b05-140">The following amounts are shown on every card: Actual, Budget, Budget variance, Budget variance %, Revised budget, Revised budget variance, and Revised budget variance %.</span></span>
    
    <span data-ttu-id="e9b05-141">[![Cartão de um elemento de custo ](./media/Cost-controlling.png)](./media/Cost-controlling.png)</span><span class="sxs-lookup"><span data-stu-id="e9b05-141">[![Card for a cost element](./media/Cost-controlling.png)](./media/Cost-controlling.png)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e9b05-142">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e9b05-142">Prerequisites</span></span>
<span data-ttu-id="e9b05-143">Os pré-requisitos diferem, com base da versão do Microsoft Dynamics 365 que foi implantada para sua organização.</span><span class="sxs-lookup"><span data-stu-id="e9b05-143">The prerequisites differ, based on the version of Microsoft Dynamics 365 that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017-update"></a><span data-ttu-id="e9b05-144">Pré-requisitos se você usar o Microsoft Dynamics 365 for Finance and Operations, Enterprise edition atualização de julho de 2017</span><span class="sxs-lookup"><span data-stu-id="e9b05-144">Prerequisites if you use Microsoft Dynamics 365 for Finance and Operations, Enterprise edition July 2017 update</span></span>
<span data-ttu-id="e9b05-145">Se o Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition de julho de 2017, foi implementado em sua organização, o administrador do sistema deve publicar o espaço de trabalho móvel **Controle de custo**.</span><span class="sxs-lookup"><span data-stu-id="e9b05-145">If Microsoft Dynamics 365 for Finance and Operations, Enterprise edition July 2017 update has been deployed for your organization, the system administrator must publish the **Cost controlling** mobile workspace.</span></span> <span data-ttu-id="e9b05-146">Para obter instruções, consulte [Publicar um espaço de trabalho móvel](/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace).</span><span class="sxs-lookup"><span data-stu-id="e9b05-146">For instructions, see [Publish a mobile workspace](/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace).</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a><span data-ttu-id="e9b05-147">Pré-requisitos se você usar o Microsoft Dynamics 365 for Operations versão 1611 com a atualização da plataforma 3 ou posterior</span><span class="sxs-lookup"><span data-stu-id="e9b05-147">Prerequisites if you use Microsoft Dynamics 365 for Operations version 1611 with platform update 3 or later</span></span>
<span data-ttu-id="e9b05-148">Se o Microsoft Dynamics 365 for Operations versão 1611 com a atualização da plataforma 3 ou posterior tiver sido implantado em sua organização, o administrador do sistema deve completar os seguintes pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="e9b05-148">If Microsoft Dynamics 365 for Operations version 1611 with platform update 3 or later has been deployed for your organization, the system administrator must complete the following prerequisites.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="e9b05-149">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="e9b05-149">Prerequisite</span></span></th>
<th><span data-ttu-id="e9b05-150">Função</span><span class="sxs-lookup"><span data-stu-id="e9b05-150">Role</span></span></th>
<th><span data-ttu-id="e9b05-151">descrição</span><span class="sxs-lookup"><span data-stu-id="e9b05-151">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="e9b05-152">Implementar o KB 4013633.</span><span class="sxs-lookup"><span data-stu-id="e9b05-152">Implement KB 4013633.</span></span></td>
<td><span data-ttu-id="e9b05-153">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="e9b05-153">System administrator</span></span></td>

<td><span data-ttu-id="e9b05-154">O KB 4013633 é uma atualização X++ ou hotfix de metadados que contém o espaço de trabalho móvel de <strong>Controle de custo</strong>.</span><span class="sxs-lookup"><span data-stu-id="e9b05-154">KB 4013633 is an X++ update or metadata hotfix that contains the <strong>Cost controlling</strong> mobile workspace.</span></span> <span data-ttu-id="e9b05-155">Para implementar o KB 4013633, o administrador do sistema deve seguir estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e9b05-155">To implement KB 4013633, your system administrator must follow these steps.</span></span>
<ol>
<li><span data-ttu-id="e9b05-156"><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/download-hotfix-lcs">Baixe o hotfix de metadados do Microsoft Dynamics Lifecycle Services (LCS)</a>.</span><span class="sxs-lookup"><span data-stu-id="e9b05-156"><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/download-hotfix-lcs">Download the metadata hotfix from Microsoft Dynamics Lifecycle Services (LCS)</a>.</span></span></li>
<li><span data-ttu-id="e9b05-157"><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Instalar o hotfix de metadados</a>.</span><span class="sxs-lookup"><span data-stu-id="e9b05-157"><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Install the metadata hotfix</a>.</span></span></li>
<li><span data-ttu-id="e9b05-158"><a href="/dynamics365/unified-operations/dev-itpro/deployment/create-apply-deployable-package">Criar um pacote implantável</a> que contenha o modelo <strong>SCMMobile</strong> e, em seguida, carregar o pacote implantável para o LCS.</span><span class="sxs-lookup"><span data-stu-id="e9b05-158"><a href="/dynamics365/unified-operations/dev-itpro/deployment/create-apply-deployable-package">Create a deployable package</a> that contains the <strong>SCMMobile</strong> model, and then upload the deployable package to LCS.</span></span></li>
<li><span data-ttu-id="e9b05-159"><a href="/dynamics365/unified-operations/dev-itpro/deployment/apply-deployable-package-system">Aplicar o pacote implantável</a>.</span><span class="sxs-lookup"><span data-stu-id="e9b05-159"><a href="/dynamics365/unified-operations/dev-itpro/deployment/apply-deployable-package-system">Apply the deployable package</a>.</span></span></li>

</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e9b05-160">Publicar o espaço de trabalho móvel do <strong>Controle de custo</strong>.</span><span class="sxs-lookup"><span data-stu-id="e9b05-160">Publish the <strong>Cost controlling</strong> mobile workspace.</span></span></td>
<td><span data-ttu-id="e9b05-161">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="e9b05-161">System administrator</span></span></td>
<td><span data-ttu-id="e9b05-162">Consulte <a href="/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace">Publicar um espaço de trabalho móvel</a>.</span><span class="sxs-lookup"><span data-stu-id="e9b05-162">See <a href="/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>


## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="e9b05-163">Baixa e instala o aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="e9b05-163">Download and install the mobile app</span></span>
<span data-ttu-id="e9b05-164">Baixa e instala o aplicativo móvel Dynamics 365 for Unified Operations:</span><span class="sxs-lookup"><span data-stu-id="e9b05-164">Download and install the Dynamics 365 for Unified Operations mobile app:</span></span>

-   [<span data-ttu-id="e9b05-165">Para telefones Android</span><span class="sxs-lookup"><span data-stu-id="e9b05-165">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="e9b05-166">Para iPhones</span><span class="sxs-lookup"><span data-stu-id="e9b05-166">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="e9b05-167">Entrar no aplicativo móvel</span><span class="sxs-lookup"><span data-stu-id="e9b05-167">Sign in to the mobile app</span></span>

1.  <span data-ttu-id="e9b05-168">Inicie o aplicativo móvel no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e9b05-168">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="e9b05-169">Insira sua URL do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e9b05-169">Enter your Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="e9b05-170">Na primeira vez que você iniciar a sessão, será solicitado o nome de usuário e a senha.</span><span class="sxs-lookup"><span data-stu-id="e9b05-170">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="e9b05-171">Insira suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="e9b05-171">Enter your credentials.</span></span>
4.  <span data-ttu-id="e9b05-172">Depois de entrar, serão exibidos os espaços de trabalho disponíveis da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="e9b05-172">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="e9b05-173">Observe que se o seu administrador de sistema publica um novo espaço de de trabalho depois, você terá que atualizar a lista dos espaços de trabalho móveis.</span><span class="sxs-lookup"><span data-stu-id="e9b05-173">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

<span data-ttu-id="e9b05-174">[![Efetue pull para atualizar](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="e9b05-174">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="view-the-performance-of-your-cost-center-by-using-the-cost-controlling-mobile-workspace"></a><span data-ttu-id="e9b05-175">Exiba o desempenho do seu centro de custos usando o espaço de trabalho móvel de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="e9b05-175">View the performance of your cost center by using the Cost controlling mobile workspace</span></span>

1.  <span data-ttu-id="e9b05-176">No seu dispositivo móvel, selecione o espaço de trabalho **Controle de custo**.</span><span class="sxs-lookup"><span data-stu-id="e9b05-176">On your mobile device, select the **Cost controlling** workspace.</span></span>
2.  <span data-ttu-id="e9b05-177">Selecione **Controle de objeto de custo**.</span><span class="sxs-lookup"><span data-stu-id="e9b05-177">Select **Cost object controlling**.</span></span>
3.  <span data-ttu-id="e9b05-178">Selecione **Ações**.</span><span class="sxs-lookup"><span data-stu-id="e9b05-178">Select **Actions**.</span></span>
4.  <span data-ttu-id="e9b05-179">Selecione **Selecionar configuração** para selecionar um layout de controle de custos.</span><span class="sxs-lookup"><span data-stu-id="e9b05-179">Select **Select configuration** to select a cost controlling layout.</span></span>
5.  <span data-ttu-id="e9b05-180">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="e9b05-180">Select **Done**.</span></span>
6.  <span data-ttu-id="e9b05-181">Selecione **Ações**.</span><span class="sxs-lookup"><span data-stu-id="e9b05-181">Select **Actions**.</span></span>
7.  <span data-ttu-id="e9b05-182">Selecione **Selecionar objeto de custo** para selecionar os centros de custo aos quais você tem acesso.</span><span class="sxs-lookup"><span data-stu-id="e9b05-182">Select **Select cost object** to select the cost centers that you've been granted access to.</span></span>
8.  <span data-ttu-id="e9b05-183">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="e9b05-183">Select **Done**.</span></span>
9.  <span data-ttu-id="e9b05-184">Exiba o desempenho geral do seu centro de custo.</span><span class="sxs-lookup"><span data-stu-id="e9b05-184">View the overall performance of your cost center.</span></span>
10. <span data-ttu-id="e9b05-185">Selecione o link **Detalhes do período atual**.</span><span class="sxs-lookup"><span data-stu-id="e9b05-185">Select the **Details for current period** link.</span></span>
11. <span data-ttu-id="e9b05-186">Exiba o desempenho dos elementos de custo individuais.</span><span class="sxs-lookup"><span data-stu-id="e9b05-186">View the performance of individual cost elements.</span></span>
12. <span data-ttu-id="e9b05-187">Você também pode pesquisar elementos de custo específicos.</span><span class="sxs-lookup"><span data-stu-id="e9b05-187">You can also search for specific cost elements.</span></span>


