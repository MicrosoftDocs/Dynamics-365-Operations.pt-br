---
title: Espaço de trabalho móvel de entrada de tempo do projeto
description: Este tópico fornece informações sobre o espaço de trabalho móvel de entrada de tempo do projeto. Este espaço de trabalho permite que os usuários insiram e economizem tempo com um projeto usando seu dispositivo móvel.
author: KimANelson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 272101
ms.assetid: 4505f021-b9bb-4b87-be24-6bf0bd88ee60
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 717ac188778dc059a90ac2a44dcd6a599106e553
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845922"
---
# <a name="project-time-entry-mobile-workspace"></a><span data-ttu-id="ab2a3-104">Espaço de trabalho móvel de entrada de tempo do projeto</span><span class="sxs-lookup"><span data-stu-id="ab2a3-104">Project time entry mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ab2a3-105">Este tópico fornece informações sobre a área de trabalho móvel de **Entrada de tempo do projeto**.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-105">This topic provides information about the **Project time entry** mobile workspace.</span></span> <span data-ttu-id="ab2a3-106">Este espaço de trabalho permite que os usuários insiram e economizem tempo com um projeto usando seu dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-106">This workspace lets users enter and save time against a project by using their mobile device.</span></span>

<span data-ttu-id="ab2a3-107">Este espaço de trabalho móvel deve ser usado com o Microsoft Dynamics 365 do aplicativo Unified Operations Mobile.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-107">This mobile workspace is intended to be used with the Microsoft Dynamics 365 for Unified Operations mobile app.</span></span> 

## <a name="overview"></a><span data-ttu-id="ab2a3-108">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="ab2a3-108">Overview</span></span>
<span data-ttu-id="ab2a3-109">Como parte do trabalho diário, os recursos de projetos são frequentemente no local ou em trânsito.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-109">As part of their daily work, project resources are often on-site or traveling.</span></span> <span data-ttu-id="ab2a3-110">O espaço de trabalho móvel **Entrada de tempo de projeto** permite que os usuários insiram tempo faturável ou não faturável em um projeto no dispositivo móvel de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-110">The **Project time entry** mobile workspace lets users enter their billable or non-billable time against a project on the mobile device of their choice.</span></span> <span data-ttu-id="ab2a3-111">Portanto, recursos do projeto podem gravar entradas de tempo a qualquer momento e em qualquer lugar.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-111">Therefore, project resources can record time entries anytime and anywhere.</span></span> <span data-ttu-id="ab2a3-112">Também podem exibir as entradas de horas que já foram registradas.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-112">They can also view time entries that have already been recorded.</span></span> 

<span data-ttu-id="ab2a3-113">Especificamente, na área de trabalho móvel **Entrada de tempo do projeto**, os usuários podem executar estas tarefas:</span><span class="sxs-lookup"><span data-stu-id="ab2a3-113">Specifically, in the **Project time entry** mobile workspace, users can perform these tasks:</span></span>

-   <span data-ttu-id="ab2a3-114">Para qualquer data selecionada, insira o número de horas que passou de uma tarefa específica.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-114">For any selected date, enter the number of hours that you spent on a specific task.</span></span>
-   <span data-ttu-id="ab2a3-115">Pesquisar o nome do projeto ou cliente para localizar o projeto para inserir tempo.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-115">Search by project name or customer to find the project to enter time for.</span></span>
-   <span data-ttu-id="ab2a3-116">Especifique a categoria e a atividade do tempo que passou.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-116">Specify the category and activity for the time that you spent.</span></span>
-   <span data-ttu-id="ab2a3-117">Registre o tempo como faturável ou não faturável para o projeto.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-117">Record the time as billable or non-billable for the project.</span></span>
-   <span data-ttu-id="ab2a3-118">Opcionalmente insira comentários internos ou externos.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-118">Optionally enter any external or internal comments.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ab2a3-119">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="ab2a3-119">Prerequisites</span></span>
<span data-ttu-id="ab2a3-120">Os pré-requisitos variam conforme a versão do Microsoft Dynamics 365 implantada na organização.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-120">The prerequisites differ, based on the version of Microsoft Dynamics 365 that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations"></a><span data-ttu-id="ab2a3-121">Pré-requisitos se você usa o Microsoft Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ab2a3-121">Prerequisites if you use Microsoft Dynamics 365 for Finance and Operations</span></span>
<span data-ttu-id="ab2a3-122">Se o Microsoft Dynamics 365 for Finance and Operations foi implantado na organização, o administrador do sistema deverá publicar o espaço de trabalho móvel **Entrada de hora de projeto**.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-122">If Microsoft Dynamics 365 for Finance and Operations has been deployed for your organization, the system administrator must publish the **Project time entry** mobile workspace.</span></span> <span data-ttu-id="ab2a3-123">Para obter instruções, consulte [Publicar um espaço de trabalho móvel](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="ab2a3-123">For instructions, see [Publish a mobile workspace](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a><span data-ttu-id="ab2a3-124">Pré-requisitos se você usa a versão 1611 do Microsoft Dynamics 365 for Operations com a atualização de plataforma 3 ou posterior</span><span class="sxs-lookup"><span data-stu-id="ab2a3-124">Prerequisites if you use Microsoft Dynamics 365 for Operations version 1611 with platform update 3 or later</span></span>
<span data-ttu-id="ab2a3-125">Se o Microsoft Dynamics 365 for Operations versão 1611 com a atualização de plataforma 3 ou posterior foi implantado na organização, o administrador do sistema deverá atender aos pré-requisitos a seguir.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-125">If Microsoft Dynamics 365 for Operations version 1611 with platform update 3 or later has been deployed for your organization, the system administrator must complete the following prerequisites.</span></span> 

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="ab2a3-126">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="ab2a3-126">Prerequisite</span></span></th>
<th><span data-ttu-id="ab2a3-127">Função</span><span class="sxs-lookup"><span data-stu-id="ab2a3-127">Role</span></span></th>
<th><span data-ttu-id="ab2a3-128">descrição</span><span class="sxs-lookup"><span data-stu-id="ab2a3-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">

<td><span data-ttu-id="ab2a3-129">Implementar o KB 4018050.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-129">Implement KB 4018050.</span></span></td>
<td><span data-ttu-id="ab2a3-130">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="ab2a3-130">System administrator</span></span></td>
<td><span data-ttu-id="ab2a3-131">o KB 4018050 é um hotfix de metadados ou atualização X++ que contém o espaço de trabalho móvel <strong>Entrada de tempo do projeto</strong>.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-131">KB 4018050 is an X++ update or metadata hotfix that contains the <strong>Project time entry</strong> mobile workspace.</span></span> <span data-ttu-id="ab2a3-132">Para implementar o KB 4018050, o administrador do sistema deve seguir estas etapas.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-132">To implement KB 4018050, your system administrator must follow these steps.</span></span>
<ol>
<li><span data-ttu-id="ab2a3-133"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Baixe o hotfix de metadados do Microsoft Dynamics Lifecycle Services (LCS)</a>.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-133"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Download the metadata hotfix from Microsoft Dynamics Lifecycle Services (LCS)</a>.</span></span></li>
<li><span data-ttu-id="ab2a3-134"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Instalar o hotfix de metadados</a>.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-134"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Install the metadata hotfix</a>.</span></span></li>
<li><span data-ttu-id="ab2a3-135"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Crie um pacote implantável</a> que contenha os modelos <strong>ApplicationSuite</strong> e <strong>ProjectMobile</strong> e, em seguida, carregue o pacote implantável para o LCS.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-135"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Create a deployable package</a> that contains the <strong>ApplicationSuite</strong> and <strong>ProjectMobile</strong> models, and then upload the deployable package to LCS.</span></span></li>
<li><span data-ttu-id="ab2a3-136"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Aplicar o pacote implantável</a>.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-136"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Apply the deployable package</a>.</span></span></li>

</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ab2a3-137">Publique a área de trabalho móvel <strong>Entrada de tempo do projeto</strong>.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-137">Publish the <strong>Project time entry</strong> mobile workspace.</span></span></td>
<td><span data-ttu-id="ab2a3-138">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="ab2a3-138">System administrator</span></span></td>
<td><span data-ttu-id="ab2a3-139">Consulte <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publicar um espaço de trabalho móvel</a>.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-139">See <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="ab2a3-140">Baixa e instala o aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-140">Download and install the mobile app</span></span>

<span data-ttu-id="ab2a3-141">Baixa e instala o aplicativo móvel Dynamics 365 for Unified Operations:</span><span class="sxs-lookup"><span data-stu-id="ab2a3-141">Download and install the Dynamics 365 for Unified Operations mobile app:</span></span>

-   [<span data-ttu-id="ab2a3-142">Para telefones Android</span><span class="sxs-lookup"><span data-stu-id="ab2a3-142">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="ab2a3-143">Para iPhones</span><span class="sxs-lookup"><span data-stu-id="ab2a3-143">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="ab2a3-144">Entrar no aplicativo móvel</span><span class="sxs-lookup"><span data-stu-id="ab2a3-144">Sign in to the mobile app</span></span>
1.  <span data-ttu-id="ab2a3-145">Inicie o aplicativo móvel no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-145">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="ab2a3-146">Insira sua URL do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-146">Enter your Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="ab2a3-147">Na primeira vez que você iniciar a sessão, será solicitado o nome de usuário e a senha.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-147">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="ab2a3-148">Insira suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-148">Enter your credentials.</span></span>
4.  <span data-ttu-id="ab2a3-149">Depois de entrar, serão exibidos os espaços de trabalho disponíveis da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-149">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="ab2a3-150">Observe que se o seu administrador de sistema publica um novo espaço de de trabalho depois, você terá que atualizar a lista dos espaços de trabalho móveis.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-150">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

<span data-ttu-id="ab2a3-151">[![Efetue pull para atualizar](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="ab2a3-151">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="enter-time-by-using-the-project-time-entry-mobile-workspace"></a><span data-ttu-id="ab2a3-152">Insira o tempo usando o espaço de trabalho móvel Entrada de tempo do projeto</span><span class="sxs-lookup"><span data-stu-id="ab2a3-152">Enter time by using the Project time entry mobile workspace</span></span>
1.  <span data-ttu-id="ab2a3-153">No seu dispositivo móvel, selecione o espaço de trabalho **Entrada de tempo do projeto**.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-153">On your mobile device, select the **Project time entry** workspace.</span></span>
2.  <span data-ttu-id="ab2a3-154">Selecione **Entrada de tempo**.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-154">Select **Time entry**.</span></span> <span data-ttu-id="ab2a3-155">Você verá as datas de calendário da semana atual.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-155">The calendar dates for the current week are shown.</span></span>
3.  <span data-ttu-id="ab2a3-156">Para uma data selecionada, selecione **Ações** &gt; **Nova entrada**.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-156">For a selected date, select **Actions** &gt; **New entry**.</span></span>
4.  <span data-ttu-id="ab2a3-157">Insira o número de horas a serem registradas.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-157">Enter the number of hours to record.</span></span>
5.  <span data-ttu-id="ab2a3-158">Selecionar o projeto para a entrada de hora.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-158">Select the project for the time entry.</span></span> <span data-ttu-id="ab2a3-159">Você verá uma lista de projetos que estão carregados para seu aplicativo para uso offline.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-159">A list shows the projects that are loaded into your app for offline use.</span></span> <span data-ttu-id="ab2a3-160">Por padrão, 50 itens são carregados, mas um desenvolvedor pode alterar esse número.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-160">By default, 50 items are loaded, but a developer can change this number.</span></span> <span data-ttu-id="ab2a3-161">Para obter mais informações, consulte a [Plataforma móvel](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span><span class="sxs-lookup"><span data-stu-id="ab2a3-161">For more information, see [Mobile platform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span></span>
6.  <span data-ttu-id="ab2a3-162">Se o projeto não estiver na lista, selecione **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-162">If your project isn't in the list, select **Search**.</span></span> <span data-ttu-id="ab2a3-163">Pesquisar por nome ou alternar para pesquisar por nome do projeto ou cliente.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-163">Search by name, or switch to search by project name or customer.</span></span>
7.  <span data-ttu-id="ab2a3-164">Selecione uma categoria.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-164">Select a category.</span></span> <span data-ttu-id="ab2a3-165">Você verá uma lista de categorias que estão carregados para seu aplicativo para uso offline.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-165">A list shows the categories that are loaded into your app for offline use.</span></span> <span data-ttu-id="ab2a3-166">Por padrão, 50 itens são carregados, mas um desenvolvedor pode alterar esse número.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-166">By default, 50 items are loaded, but a developer can change this number.</span></span> <span data-ttu-id="ab2a3-167">Para obter mais informações, consulte a [Plataforma móvel](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span><span class="sxs-lookup"><span data-stu-id="ab2a3-167">For more information, see [Mobile platform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span></span>
8.  <span data-ttu-id="ab2a3-168">Se a categoria não estiver na lista, selecione **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-168">If your category isn't in the list, select **Search**.</span></span> <span data-ttu-id="ab2a3-169">Pesquise por categoria ou alterne para pesquisar por nome de categoria.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-169">Search by category, or switch to search by category name.</span></span>
9.  <span data-ttu-id="ab2a3-170">Selecione uma atividade.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-170">Select an activity.</span></span> <span data-ttu-id="ab2a3-171">Você verá uma lista de atividades que estão carregados para seu aplicativo para uso offline.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-171">A list shows the activities that are loaded into your app for offline use.</span></span> <span data-ttu-id="ab2a3-172">Por padrão, 50 itens são carregados, mas um desenvolvedor pode alterar esse número.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-172">By default, 50 items are loaded, but a developer can change this number.</span></span> <span data-ttu-id="ab2a3-173">Para obter mais informações, consulte a [Plataforma móvel](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span><span class="sxs-lookup"><span data-stu-id="ab2a3-173">For more information, see [Mobile platform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span></span>
10. <span data-ttu-id="ab2a3-174">Se a atividade não estiver na lista, selecione **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-174">If your activity isn't in the list, select **Search**.</span></span> <span data-ttu-id="ab2a3-175">Pesquise por número de atividade ou alterne para pesquisar por finalidade.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-175">Search by activity number, or switch to search by purpose.</span></span>

11. <span data-ttu-id="ab2a3-176">Selecionar a propriedade da linha.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-176">Select the line property.</span></span>
12. <span data-ttu-id="ab2a3-177">Opcional: insira comentários internos ou externos.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-177">Optional: Enter any external and internal comments.</span></span>
13. <span data-ttu-id="ab2a3-178">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="ab2a3-178">Select **Done**.</span></span>
