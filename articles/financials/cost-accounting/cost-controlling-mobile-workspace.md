---
title: Espaço de trabalho móvel de controle de custo
description: Este tópico fornece informações sobre o espaço de trabalho móvel do controle de custos. Este espaço de trabalho permite que gerentes de centro de custos exibam informações sobre desempenho de centro de custo a qualquer momento e em qualquer lugar.
author: AndersGirke
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: aevengir
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: b6cdb69f32de2118e685c149605d50b78105c098
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "317559"
---
# <a name="cost-controlling-mobile-workspace"></a><span data-ttu-id="b319a-104">Espaço de trabalho móvel de controle de custo</span><span class="sxs-lookup"><span data-stu-id="b319a-104">Cost controlling mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b319a-105">Este tópico fornece informações sobre o espaço de trabalho móvel do **controle de custos**.</span><span class="sxs-lookup"><span data-stu-id="b319a-105">This topic provides information about the **Cost controlling** mobile workspace.</span></span> <span data-ttu-id="b319a-106">Este espaço de trabalho permite que gerentes de centro de custos exibam informações sobre desempenho de centro de custo a qualquer momento e em qualquer lugar.</span><span class="sxs-lookup"><span data-stu-id="b319a-106">This workspace lets cost center managers view information about cost center performance anytime and anywhere.</span></span>

<span data-ttu-id="b319a-107">Este espaço de trabalho móvel deve ser usado com o Microsoft Dynamics 365 do aplicativo Unified Operations Mobile.</span><span class="sxs-lookup"><span data-stu-id="b319a-107">This mobile workspace is intended to be used with the Microsoft Dynamics 365 for Unified Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="b319a-108">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="b319a-108">Overview</span></span>
<span data-ttu-id="b319a-109">O espaço de trabalho móvel **Controle de custos** fornece uma exibição instantânea do desempenho atual dos centros de custo comparando custos reais com os custos orçados.</span><span class="sxs-lookup"><span data-stu-id="b319a-109">The **Cost controlling** mobile workspace provides an instant view of the current performance of cost centers by comparing actual costs against the budgeted costs.</span></span> <span data-ttu-id="b319a-110">Você pode fazer uma busca detalhada nos status de elementos de custo individuais.</span><span class="sxs-lookup"><span data-stu-id="b319a-110">You can drill down to the status of individual cost elements.</span></span>

<span data-ttu-id="b319a-111">Por exemplo, um funcionário recebe um convite para uma conferência internacional, mas a organização deve cobrir todas despesas de viagem.</span><span class="sxs-lookup"><span data-stu-id="b319a-111">For example, an employee receives an invitation to an international conference, but the organization must cover all the travel expenses.</span></span> <span data-ttu-id="b319a-112">O funcionário pergunta a seu gerente se ele pode participar da conferência.</span><span class="sxs-lookup"><span data-stu-id="b319a-112">The employee asks his manager whether he can attend the conference.</span></span> <span data-ttu-id="b319a-113">O gerente abre o espaço de trabalho móvel **Controle de custos** no seu dispositivo móvel para ver se dispõe do orçamento para que o funcionário possa ir à conferência.</span><span class="sxs-lookup"><span data-stu-id="b319a-113">The manager opens the **Cost controlling** mobile workspace on her mobile device to see whether she has budget for the employee to attend the conference.</span></span>

### <a name="data-security"></a><span data-ttu-id="b319a-114">Segurança de dados</span><span class="sxs-lookup"><span data-stu-id="b319a-114">Data security</span></span>
<span data-ttu-id="b319a-115">Os dados no espaço de trabalho móvel **Controle de custos** são protegidos pelas credenciais do usuário.</span><span class="sxs-lookup"><span data-stu-id="b319a-115">The data in the **Cost controlling** mobile workspace is secured through user credentials.</span></span> <span data-ttu-id="b319a-116">Os gerentes do centro de custos podem ver os dados somente de seus próprios centros de custo.</span><span class="sxs-lookup"><span data-stu-id="b319a-116">Cost center managers are allowed to see data only for their own cost center.</span></span> <span data-ttu-id="b319a-117">A segurança de nível de acesso é gerenciada no módulo **Contabilização de custos**.</span><span class="sxs-lookup"><span data-stu-id="b319a-117">The access-level security is managed in the **Cost accounting** module.</span></span>

<span data-ttu-id="b319a-118">Os contadores de custo definem a configuração do espaço de trabalho móvel **Controle de custos** no módulo **Contabilidade de custos**.</span><span class="sxs-lookup"><span data-stu-id="b319a-118">Cost accountants define the configuration of the **Cost controlling** mobile workspace in the **Cost accounting** module.</span></span> <span data-ttu-id="b319a-119">Após a publicação do espaço de trabalho no aplicativo móvel, ele fica disponível no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b319a-119">After the workspace is published to the mobile app, it's available in the app.</span></span> <span data-ttu-id="b319a-120">Com isso, todos os gerentes de centro de custo da organização podem ver os dados no mesmo formato.</span><span class="sxs-lookup"><span data-stu-id="b319a-120">Therefore, all cost center managers in the organization can view data in the same format.</span></span>

### <a name="actions-views-and-links"></a><span data-ttu-id="b319a-121">Ações, exibições e links</span><span class="sxs-lookup"><span data-stu-id="b319a-121">Actions, views, and links</span></span>
<span data-ttu-id="b319a-122">O espaço de trabalho móvel **Controle de custo** fornece as seguintes ações, exibições e links:</span><span class="sxs-lookup"><span data-stu-id="b319a-122">The **Cost controlling** mobile workspace provides the following actions, views, and links:</span></span>

-   <span data-ttu-id="b319a-123">**Ações:**</span><span class="sxs-lookup"><span data-stu-id="b319a-123">**Actions:**</span></span>

    -   <span data-ttu-id="b319a-124">Use **Selecione configuração** para selecionar um layout.</span><span class="sxs-lookup"><span data-stu-id="b319a-124">Use **Select configuration** to select a layout.</span></span>
    -   <span data-ttu-id="b319a-125">Use **Selecione o objeto de custo** para selecionar os centros de custos para filtrar dados.</span><span class="sxs-lookup"><span data-stu-id="b319a-125">Use **Select cost object** to select the cost centers to filter data on.</span></span>
    
        > [!NOTE]
        > <span data-ttu-id="b319a-126">Os centros de custo exibidos na lista dependem do acesso concedido no módulo **Contabilização de custos**.</span><span class="sxs-lookup"><span data-stu-id="b319a-126">The cost centers that appear in the list depend on the access that is granted in the **Cost accounting** module.</span></span>

-   <span data-ttu-id="b319a-127">**Exibições:** com base nas ações que são selecionadas e na configuração do módulo **Contabilidade de custos**, é possível exibir as seguintes informações nos cartões:</span><span class="sxs-lookup"><span data-stu-id="b319a-127">**Views:** Based on the actions that are selected and the configuration in the **Cost accounting** module, you can view the following information on the cards:</span></span>

    -   <span data-ttu-id="b319a-128">Real versus orçamento (período atual)</span><span class="sxs-lookup"><span data-stu-id="b319a-128">Actual vs budget (current period)</span></span>
    -   <span data-ttu-id="b319a-129">Real versus orçamento revisado (período atual)</span><span class="sxs-lookup"><span data-stu-id="b319a-129">Actual vs revised budget (current period)</span></span>
    -   <span data-ttu-id="b319a-130">Real vs. orçamento (período anterior)</span><span class="sxs-lookup"><span data-stu-id="b319a-130">Actual vs budget (previous period)</span></span>
    -   <span data-ttu-id="b319a-131">Real vs. orçamento revisado (período anterior)</span><span class="sxs-lookup"><span data-stu-id="b319a-131">Actual vs revised budget (previous period)</span></span>
    -   <span data-ttu-id="b319a-132">Real vs. orçamento (desde o início do ano)</span><span class="sxs-lookup"><span data-stu-id="b319a-132">Actual vs budget (year to date)</span></span>
    -   <span data-ttu-id="b319a-133">Real vs. orçamento revisado (desde o início do ano)</span><span class="sxs-lookup"><span data-stu-id="b319a-133">Actual vs revised budget (year to date)</span></span>

    <span data-ttu-id="b319a-134">Os valores a seguir são exibidos em cada cartão: Real, Orçamento, Variação e % de variação.</span><span class="sxs-lookup"><span data-stu-id="b319a-134">The following amounts are shown on every card: Actual, Budget, Variance, and Variance %.</span></span>

-   <span data-ttu-id="b319a-135">**Links:**</span><span class="sxs-lookup"><span data-stu-id="b319a-135">**Links:**</span></span>

    -   <span data-ttu-id="b319a-136">Detalhes do período atual</span><span class="sxs-lookup"><span data-stu-id="b319a-136">Details for current period</span></span>
    -   <span data-ttu-id="b319a-137">Detalhes do período anterior</span><span class="sxs-lookup"><span data-stu-id="b319a-137">Details for previous period</span></span>
    -   <span data-ttu-id="b319a-138">Detalhes desde o início do ano</span><span class="sxs-lookup"><span data-stu-id="b319a-138">Details for year to date</span></span>

    <span data-ttu-id="b319a-139">Quando você seleciona um link, um cartão será mostrado para cada elemento de custo.</span><span class="sxs-lookup"><span data-stu-id="b319a-139">When you select a link, a card is shown for each cost element.</span></span> <span data-ttu-id="b319a-140">Os valores a seguir são mostrados em cada cartão: Real, Orçamento, Variação do Orçamento, % de Variação do Orçamento, Orçamento revisado, Variação do Orçamento Revisado e % de Variação do Orçamento Revisado.</span><span class="sxs-lookup"><span data-stu-id="b319a-140">The following amounts are shown on every card: Actual, Budget, Budget variance, Budget variance %, Revised budget, Revised budget variance, and Revised budget variance %.</span></span>
    
    <span data-ttu-id="b319a-141">[![Cartão de um elemento de custo](./media/Cost-controlling.png)](./media/Cost-controlling.png)</span><span class="sxs-lookup"><span data-stu-id="b319a-141">[![Card for a cost element](./media/Cost-controlling.png)](./media/Cost-controlling.png)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b319a-142">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b319a-142">Prerequisites</span></span>
<span data-ttu-id="b319a-143">Os pré-requisitos variam conforme a versão do Microsoft Dynamics 365 implantada na organização.</span><span class="sxs-lookup"><span data-stu-id="b319a-143">The prerequisites differ, based on the version of Microsoft Dynamics 365 that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations"></a><span data-ttu-id="b319a-144">Pré-requisitos se você usa o Microsoft Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b319a-144">Prerequisites if you use Microsoft Dynamics 365 for Finance and Operations</span></span>
<span data-ttu-id="b319a-145">Se o Microsoft Dynamics 365 for Finance and Operations foi implantado na organização, o administrador do sistema deverá publicar o espaço de trabalho móvel **Controle de custos**.</span><span class="sxs-lookup"><span data-stu-id="b319a-145">If Microsoft Dynamics 365 for Finance and Operations has been deployed for your organization, the system administrator must publish the **Cost controlling** mobile workspace.</span></span> <span data-ttu-id="b319a-146">Para obter instruções, consulte [Publicar um espaço de trabalho móvel](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="b319a-146">For instructions, see [Publish a mobile workspace](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a><span data-ttu-id="b319a-147">Pré-requisitos se você usa a versão 1611 do Microsoft Dynamics 365 for Operations com a atualização de plataforma 3 ou posterior</span><span class="sxs-lookup"><span data-stu-id="b319a-147">Prerequisites if you use Microsoft Dynamics 365 for Operations version 1611 with platform update 3 or later</span></span>
<span data-ttu-id="b319a-148">Se o Microsoft Dynamics 365 for Operations versão 1611 com a atualização de plataforma 3 ou posterior foi implantado na organização, o administrador do sistema deverá atender aos pré-requisitos a seguir.</span><span class="sxs-lookup"><span data-stu-id="b319a-148">If Microsoft Dynamics 365 for Operations version 1611 with platform update 3 or later has been deployed for your organization, the system administrator must complete the following prerequisites.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="b319a-149">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="b319a-149">Prerequisite</span></span></th>
<th><span data-ttu-id="b319a-150">Função</span><span class="sxs-lookup"><span data-stu-id="b319a-150">Role</span></span></th>
<th><span data-ttu-id="b319a-151">descrição</span><span class="sxs-lookup"><span data-stu-id="b319a-151">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="b319a-152">Implementar o KB 4013633.</span><span class="sxs-lookup"><span data-stu-id="b319a-152">Implement KB 4013633.</span></span></td>
<td><span data-ttu-id="b319a-153">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="b319a-153">System administrator</span></span></td>

<td><span data-ttu-id="b319a-154">O KB 4013633 é uma atualização X++ ou hotfix de metadados que contém o espaço de trabalho móvel de <strong>Controle de custo</strong>.</span><span class="sxs-lookup"><span data-stu-id="b319a-154">KB 4013633 is an X++ update or metadata hotfix that contains the <strong>Cost controlling</strong> mobile workspace.</span></span> <span data-ttu-id="b319a-155">Para implementar o KB 4013633, o administrador do sistema deve seguir estas etapas.</span><span class="sxs-lookup"><span data-stu-id="b319a-155">To implement KB 4013633, your system administrator must follow these steps.</span></span>
<ol>
<li><span data-ttu-id="b319a-156"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Baixe o hotfix de metadados do Microsoft Dynamics Lifecycle Services (LCS)</a>.</span><span class="sxs-lookup"><span data-stu-id="b319a-156"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Download the metadata hotfix from Microsoft Dynamics Lifecycle Services (LCS)</a>.</span></span></li>
<li><span data-ttu-id="b319a-157"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Instalar o hotfix de metadados</a>.</span><span class="sxs-lookup"><span data-stu-id="b319a-157"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Install the metadata hotfix</a>.</span></span></li>
<li><span data-ttu-id="b319a-158"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Criar um pacote implantável</a> que contenha o modelo <strong>SCMMobile</strong> e, em seguida, carregar o pacote implantável para o LCS.</span><span class="sxs-lookup"><span data-stu-id="b319a-158"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Create a deployable package</a> that contains the <strong>SCMMobile</strong> model, and then upload the deployable package to LCS.</span></span></li>
<li><span data-ttu-id="b319a-159"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Aplicar o pacote implantável</a>.</span><span class="sxs-lookup"><span data-stu-id="b319a-159"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Apply the deployable package</a>.</span></span></li>

</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b319a-160">Publicar o espaço de trabalho móvel do <strong>Controle de custo</strong>.</span><span class="sxs-lookup"><span data-stu-id="b319a-160">Publish the <strong>Cost controlling</strong> mobile workspace.</span></span></td>
<td><span data-ttu-id="b319a-161">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="b319a-161">System administrator</span></span></td>
<td><span data-ttu-id="b319a-162">Consulte <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publicar um espaço de trabalho móvel</a>.</span><span class="sxs-lookup"><span data-stu-id="b319a-162">See <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>


## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="b319a-163">Baixa e instala o aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="b319a-163">Download and install the mobile app</span></span>
<span data-ttu-id="b319a-164">Baixa e instala o aplicativo móvel Dynamics 365 for Unified Operations:</span><span class="sxs-lookup"><span data-stu-id="b319a-164">Download and install the Dynamics 365 for Unified Operations mobile app:</span></span>

-   [<span data-ttu-id="b319a-165">Para telefones Android</span><span class="sxs-lookup"><span data-stu-id="b319a-165">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="b319a-166">Para iPhones</span><span class="sxs-lookup"><span data-stu-id="b319a-166">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="b319a-167">Entrar no aplicativo móvel</span><span class="sxs-lookup"><span data-stu-id="b319a-167">Sign in to the mobile app</span></span>

1.  <span data-ttu-id="b319a-168">Inicie o aplicativo móvel no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b319a-168">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="b319a-169">Insira sua URL do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="b319a-169">Enter your Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="b319a-170">Na primeira vez que você iniciar a sessão, será solicitado o nome de usuário e a senha.</span><span class="sxs-lookup"><span data-stu-id="b319a-170">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="b319a-171">Insira suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="b319a-171">Enter your credentials.</span></span>
4.  <span data-ttu-id="b319a-172">Depois de entrar, serão exibidos os espaços de trabalho disponíveis da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="b319a-172">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="b319a-173">Observe que se o seu administrador de sistema publica um novo espaço de de trabalho depois, você terá que atualizar a lista dos espaços de trabalho móveis.</span><span class="sxs-lookup"><span data-stu-id="b319a-173">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

<span data-ttu-id="b319a-174">[![Efetue pull para atualizar](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="b319a-174">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="view-the-performance-of-your-cost-center-by-using-the-cost-controlling-mobile-workspace"></a><span data-ttu-id="b319a-175">Exiba o desempenho do seu centro de custos usando o espaço de trabalho móvel de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="b319a-175">View the performance of your cost center by using the Cost controlling mobile workspace</span></span>

1.  <span data-ttu-id="b319a-176">No seu dispositivo móvel, selecione o espaço de trabalho **Controle de custo**.</span><span class="sxs-lookup"><span data-stu-id="b319a-176">On your mobile device, select the **Cost controlling** workspace.</span></span>
2.  <span data-ttu-id="b319a-177">Selecione **Controle de objeto de custo**.</span><span class="sxs-lookup"><span data-stu-id="b319a-177">Select **Cost object controlling**.</span></span>
3.  <span data-ttu-id="b319a-178">Selecione **Ações**.</span><span class="sxs-lookup"><span data-stu-id="b319a-178">Select **Actions**.</span></span>
4.  <span data-ttu-id="b319a-179">Selecione **Selecionar configuração** para selecionar um layout de controle de custos.</span><span class="sxs-lookup"><span data-stu-id="b319a-179">Select **Select configuration** to select a cost controlling layout.</span></span>
5.  <span data-ttu-id="b319a-180">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="b319a-180">Select **Done**.</span></span>
6.  <span data-ttu-id="b319a-181">Selecione **Ações**.</span><span class="sxs-lookup"><span data-stu-id="b319a-181">Select **Actions**.</span></span>
7.  <span data-ttu-id="b319a-182">Selecione **Selecionar objeto de custo** para selecionar os centros de custo aos quais você tem acesso.</span><span class="sxs-lookup"><span data-stu-id="b319a-182">Select **Select cost object** to select the cost centers that you've been granted access to.</span></span>
8.  <span data-ttu-id="b319a-183">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="b319a-183">Select **Done**.</span></span>
9.  <span data-ttu-id="b319a-184">Exiba o desempenho geral do seu centro de custo.</span><span class="sxs-lookup"><span data-stu-id="b319a-184">View the overall performance of your cost center.</span></span>
10. <span data-ttu-id="b319a-185">Selecione o link **Detalhes do período atual**.</span><span class="sxs-lookup"><span data-stu-id="b319a-185">Select the **Details for current period** link.</span></span>
11. <span data-ttu-id="b319a-186">Exiba o desempenho dos elementos de custo individuais.</span><span class="sxs-lookup"><span data-stu-id="b319a-186">View the performance of individual cost elements.</span></span>
12. <span data-ttu-id="b319a-187">Você também pode pesquisar elementos de custo específicos.</span><span class="sxs-lookup"><span data-stu-id="b319a-187">You can also search for specific cost elements.</span></span>

