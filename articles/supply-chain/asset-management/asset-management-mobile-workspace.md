---
title: Usar o espaço de trabalho móvel de gerenciamento de ativos
description: Este tópico fornece informações sobre o espaço de trabalho móvel Gerenciamento de ativos.
author: josaw1
manager: tfehr
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.dyn365.ops.version: 10.0.5
ms.search.validFrom: 2019-08-31
ms.openlocfilehash: afda807714f14efb1cbab4ecfdd273aac52f4558
ms.sourcegitcommit: 995c678b4715be267f1f97148902a6b3dde3bcab
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "5033143"
---
# <a name="use-the-asset-management-mobile-workspace"></a><span data-ttu-id="d5f32-103">Usar o espaço de trabalho móvel de gerenciamento de ativos</span><span class="sxs-lookup"><span data-stu-id="d5f32-103">Use the Asset management mobile workspace</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d5f32-104">Este tópico fornece informações sobre o espaço de trabalho móvel **Gerenciamento de ativos**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-104">This topic provides information about the **Asset management** mobile workspace.</span></span> <span data-ttu-id="d5f32-105">Este espaço de trabalho permite aos usuários visualizar e criar solicitações de manutenção e ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="d5f32-105">This workspace lets users view and create maintenance requests and work orders.</span></span> <span data-ttu-id="d5f32-106">Os usuários também podem visualizar os trabalhos de ordens de serviço atribuídos em uma exibição de calendário ou de lista.</span><span class="sxs-lookup"><span data-stu-id="d5f32-106">Users can also view the assigned work order jobs in a calendar or list view.</span></span> <span data-ttu-id="d5f32-107">Os ativos e os locais funcionais também podem ser visualizados e pesquisados.</span><span class="sxs-lookup"><span data-stu-id="d5f32-107">Assets and functional locations can also be viewed and searched for.</span></span>

## <a name="overview"></a><span data-ttu-id="d5f32-108">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="d5f32-108">Overview</span></span>

<span data-ttu-id="d5f32-109">O Gerenciamento de Ativos é um módulo avançado para gerenciar ativos e trabalhos de ordens de serviço no Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d5f32-109">Asset Management is an advanced module for managing assets and work order jobs in Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="d5f32-110">O espaço de trabalho móvel **Gerenciamento de ativos** permite que os usuários vejam rapidamente os trabalhos de ordens de serviço atribuídos no dispositivo móvel de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="d5f32-110">The **Asset management** mobile workspace lets users quickly view assigned work order jobs on the mobile device of their choice.</span></span> <span data-ttu-id="d5f32-111">Os usuários também podem criar e gerenciar solicitações de manutenção, atualizar o estado de ciclo de vida e visualizar detalhes do ativo e local funcional usando o dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="d5f32-111">Users can also create and manage maintenance requests, update lifecycle state, and view asset and functional location details by using their mobile device.</span></span>

<span data-ttu-id="d5f32-112">Especificamente, o espaço de trabalho móvel **Gerenciamento de ativos** permite que os usuários executem estas tarefas:</span><span class="sxs-lookup"><span data-stu-id="d5f32-112">Specifically, the **Asset management** mobile workspace lets users perform these tasks:</span></span>

- <span data-ttu-id="d5f32-113">Criar, exibir e editar solicitações de manutenção, tirar uma foto ou anexar uma imagem existente à solicitação de manutenção, alterar o estado de ciclo de vida da solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="d5f32-113">Create, view, and edit maintenance requests, take a photo or attach an existing image to the maintenance request, change the maintenance request lifecycle state.</span></span> 
- <span data-ttu-id="d5f32-114">Criar, exibir e editar ordens de serviço, tirar uma foto ou anexar uma imagem existente à ordem de serviço, alterar o estado de ciclo de vida da ordem de serviço, exibir trabalhos de ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="d5f32-114">Create, view, and edit work orders, take a photo or attach an existing image to the work order, change the work order lifecycle state, view work order jobs.</span></span>
- <span data-ttu-id="d5f32-115">Exibir trabalhos de ordens de serviço atribuídos em uma exibição de calendário.</span><span class="sxs-lookup"><span data-stu-id="d5f32-115">View assigned work order jobs in a calendar view.</span></span>
- <span data-ttu-id="d5f32-116">Criar, exibir e editar o trabalho da ordem de serviço, atualizar contadores de ativos, exibir lista de verificação de manutenção, exibir e editar notas de trabalho da ordem de serviço, exibir as ferramentas necessárias para o trabalho da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="d5f32-116">Create, view, and edit work order job, update asset counters, view maintenance checklist, view and edit work order job notes, view the tools required for the work order job.</span></span>
- <span data-ttu-id="d5f32-117">Exibir ou procurar um ativo ou local funcional específico.</span><span class="sxs-lookup"><span data-stu-id="d5f32-117">View or search for a specific asset or functional location.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d5f32-118">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d5f32-118">Prerequisites</span></span>

<span data-ttu-id="d5f32-119">Para poder usar o espaço de trabalho móvel **Gerenciamento de ativos**, seu administrador deve configurar as contas de usuário e de trabalho necessárias e publicar o espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d5f32-119">Before you can use the **Asset management** mobile workspace, your admin must set up the required user and worker accounts, and publish the workspace.</span></span> <span data-ttu-id="d5f32-120">Para obter mais informações, consulte [Configurar o espaço de trabalho móvel Gerenciamento de ativos](set-up-asset-management-mobile.md).</span><span class="sxs-lookup"><span data-stu-id="d5f32-120">For more information, see [Set up the Asset management mobile workspace](set-up-asset-management-mobile.md).</span></span>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="d5f32-121">Baixa e instala o aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="d5f32-121">Download and install the mobile app</span></span>

<span data-ttu-id="d5f32-122">Baixa e instala o aplicativo móvel Dynamics 365 for Unified Operations:</span><span class="sxs-lookup"><span data-stu-id="d5f32-122">Download and install the Dynamics 365 for Unified Operations mobile app:</span></span>

- [<span data-ttu-id="d5f32-123">Para telefones Android</span><span class="sxs-lookup"><span data-stu-id="d5f32-123">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
- [<span data-ttu-id="d5f32-124">Para iPhones</span><span class="sxs-lookup"><span data-stu-id="d5f32-124">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="d5f32-125">Entrar no aplicativo móvel</span><span class="sxs-lookup"><span data-stu-id="d5f32-125">Sign in to the mobile app</span></span>

1. <span data-ttu-id="d5f32-126">Inicie o aplicativo móvel no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d5f32-126">Start the app on your mobile device.</span></span>

1. <span data-ttu-id="d5f32-127">Insira sua URL do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d5f32-127">Enter your Dynamics 365 URL.</span></span>

1. <span data-ttu-id="d5f32-128">Na primeira vez que você iniciar a sessão, será solicitado o nome de usuário e a senha.</span><span class="sxs-lookup"><span data-stu-id="d5f32-128">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="d5f32-129">Insira suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="d5f32-129">Enter your credentials.</span></span>

1. <span data-ttu-id="d5f32-130">Depois de entrar, serão exibidos os espaços de trabalho disponíveis da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="d5f32-130">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="d5f32-131">Observe que se o administrador do sistema publicar um novo espaço depois, você terá de atualizar a lista dos espaços de trabalho móveis.</span><span class="sxs-lookup"><span data-stu-id="d5f32-131">Note that if your system administrator publishes a new workspace later, you'll have to refresh the list of mobile workspaces.</span></span>

    <span data-ttu-id="d5f32-132">![Selecionar um espaço de trabalho](media/am-mobile-01.png "Selecionar um espaço de trabalho")</span><span class="sxs-lookup"><span data-stu-id="d5f32-132">![Select a workspace](media/am-mobile-01.png "Select a workspace")</span></span>

## <a name="view-assigned-work-order-jobs-in-calendar-view"></a><span data-ttu-id="d5f32-133">Exibir trabalhos de ordens de serviço atribuídos na exibição de calendário</span><span class="sxs-lookup"><span data-stu-id="d5f32-133">View assigned work order jobs in calendar view</span></span>

1. <span data-ttu-id="d5f32-134">No seu dispositivo móvel, abra o espaço de trabalho **Gerenciamento de ativos**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-134">On your mobile device, open the **Asset management** workspace.</span></span>

1. <span data-ttu-id="d5f32-135">Selecione **Meu calendário de trabalhos de ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-135">Select **My work order jobs calendar**.</span></span>

1. <span data-ttu-id="d5f32-136">Selecione a data cujos trabalhos de ordens de serviço você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="d5f32-136">Select the date you want to view work order jobs for.</span></span> <span data-ttu-id="d5f32-137">Na lista, você verá a ID do ativo e a ID do local funcional para cada trabalho da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="d5f32-137">In the list, you'll see the asset ID and functional location ID for each work order job.</span></span>

1. <span data-ttu-id="d5f32-138">Selecione um trabalho da ordem de serviço na lista para ver os detalhes do trabalho: detalhes do ativo e local funcional, além de outros links de navegação para exibir **Anexos**, **Listas de verificação**, **Ferramentas**, **Contadores de ativos**, **Notas**, **Diários**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-138">Select a work order job in the list to see job details: Asset and functional location details as well as other navigation links to view **Attachments**, **Checklists**, **Tools**, **Asset counters**, **Notes**, **Journals**.</span></span>

    <span data-ttu-id="d5f32-139">![Exibir trabalhos de ordens de serviço atribuídos na exibição de calendário](media/am-mobile-02.png "Exibir trabalhos de ordens de serviço atribuídos na exibição de calendário")</span><span class="sxs-lookup"><span data-stu-id="d5f32-139">![View assigned work order jobs in calendar view](media/am-mobile-02.png "View assigned work order jobs in calendar view")</span></span>

## <a name="create-a-work-order-job"></a><span data-ttu-id="d5f32-140">Criar um trabalho da ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="d5f32-140">Create a work order job</span></span>

1. <span data-ttu-id="d5f32-141">No seu dispositivo móvel, abra o espaço de trabalho **Gerenciamento de ativos**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-141">On your mobile device, open the **Asset management** workspace.</span></span>

1. <span data-ttu-id="d5f32-142">Selecione **Todas as ordens de serviço de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-142">Select **All maintenance work orders**.</span></span>

1. <span data-ttu-id="d5f32-143">Selecione a ordem de serviço para a qual você deseja criar um novo trabalho.</span><span class="sxs-lookup"><span data-stu-id="d5f32-143">Select the work order you want to create a new work order job for.</span></span>

1. <span data-ttu-id="d5f32-144">Selecione o botão **Adicionar linha**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-144">Select the **Add line** button.</span></span>

1. <span data-ttu-id="d5f32-145">Selecione o **Ativo** para o qual você deseja criar um novo trabalho da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="d5f32-145">Select the **Asset** you want to create a work order job for.</span></span>

1. <span data-ttu-id="d5f32-146">Selecione **Tipo de trabalho de manutenção**, **Variação do tipo de trabalho de manutenção** e **Ofício**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-146">Select **Maintenance job type**, **Maintenance job type variant** and **Trade**.</span></span>

1. <span data-ttu-id="d5f32-147">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-147">Select **Done**.</span></span>

    <span data-ttu-id="d5f32-148">![A tela Adicionar linha](media/am-mobile-03.png "A tela Adicionar linha")</span><span class="sxs-lookup"><span data-stu-id="d5f32-148">![The Add line screen](media/am-mobile-03.png "The Add line screen")</span></span>


## <a name="add-attachment-to-a-work-order-job"></a><span data-ttu-id="d5f32-149">Adicionar anexos a um trabalho da ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="d5f32-149">Add attachment to a work order job</span></span>

1. <span data-ttu-id="d5f32-150">No seu dispositivo móvel, abra o espaço de trabalho **Gerenciamento de ativos**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-150">On your mobile device, open the **Asset management** workspace.</span></span>

1. <span data-ttu-id="d5f32-151">Selecione **Todas as ordens de serviço de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-151">Select **All maintenance work orders**.</span></span>

1. <span data-ttu-id="d5f32-152">Selecione a ordem de serviço > trabalho da ordem de serviço ao qual você deseja adicionar um anexo.</span><span class="sxs-lookup"><span data-stu-id="d5f32-152">Select the work order > work order job you want to add an attachment to.</span></span>
    - <span data-ttu-id="d5f32-153">Como opção, você também pode selecionar **Meu calendário de trabalhos de ordens de serviço** ou **Minha lista de trabalhos de ordens de serviço** na home page para navegar até a página **Detalhes do trabalho da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-153">Alternatively, you can also select **My work order jobs calendar** or **My work order jobs list** on the home page to navigate to the **Work order job details** page.</span></span>

1. <span data-ttu-id="d5f32-154">Selecione **Anexos** na página **Detalhes da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-154">Select **Attachments** on the **Work order job details** page.</span></span>

1. <span data-ttu-id="d5f32-155">Você verá os anexos existentes no trabalho da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="d5f32-155">You'll see existing attachments on the work order job.</span></span> <span data-ttu-id="d5f32-156">Selecione **Adicionar anexo**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-156">Select **Add attachment**.</span></span>

1. <span data-ttu-id="d5f32-157">Insira o **Nome** e as **Notas** do anexo.</span><span class="sxs-lookup"><span data-stu-id="d5f32-157">Enter **Name** and **Notes** for the attachment.</span></span>

1. <span data-ttu-id="d5f32-158">Selecione **Escolher imagem** para selecionar uma foto na galeria do dispositivo móvel ou **Tirar foto** para tirar uma foto.</span><span class="sxs-lookup"><span data-stu-id="d5f32-158">Select **Choose image** to select a photo from the mobile gallery, or **Take photo** to take a photo.</span></span>

1. <span data-ttu-id="d5f32-159">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-159">Select **Done**.</span></span>

    <span data-ttu-id="d5f32-160">![Exibir e adicionar anexos a um trabalho da ordem de trabalho](media/am-mobile-04.png "Exibir e adicionar anexos a um trabalho da ordem de trabalho")</span><span class="sxs-lookup"><span data-stu-id="d5f32-160">![View and add attachments for a work order job](media/am-mobile-04.png "View and add attachments for a work order job")</span></span>

## <a name="view-maintenance-checklist-on-a-work-order-job"></a><span data-ttu-id="d5f32-161">Exibir a lista de verificação de manutenção em um trabalho da ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="d5f32-161">View maintenance checklist on a work order job</span></span>

1. <span data-ttu-id="d5f32-162">No seu dispositivo móvel, abra o espaço de trabalho **Gerenciamento de ativos**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-162">On your mobile device, open the **Asset management** workspace.</span></span>

1. <span data-ttu-id="d5f32-163">Selecione **Todas as ordens de serviço de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-163">Select **All maintenance work orders**.</span></span>

1. <span data-ttu-id="d5f32-164">Selecione a ordem de serviço > trabalho da ordem de serviço cujas listas de verificação você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="d5f32-164">Select the work order > work order job you want to view checklists for.</span></span>
    - <span data-ttu-id="d5f32-165">Como opção, você também pode selecionar **Meu calendário de trabalhos de ordens de serviço** ou **Minha lista de trabalhos de ordens de serviço** na home page para navegar até a página **Detalhes do trabalho da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-165">Alternatively, you can also select **My work order jobs calendar** or **My work order jobs list** on the home page to navigate to the **work order job details** page.</span></span>

1. <span data-ttu-id="d5f32-166">Selecione **Listas de verificação** na página **Detalhes do trabalho da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-166">Select **Checklists** on the **Work order job details** page.</span></span>

1. <span data-ttu-id="d5f32-167">Você verá uma lista de linhas da lista de verificação relacionadas ao trabalho da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="d5f32-167">You'll see a list of checklist lines related to the work order job.</span></span> <span data-ttu-id="d5f32-168">Selecione uma linha de lista de verificação para exibir **Instruções** e adicionar **Notas**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-168">Select a checklist line to view **Instructions** and add **Notes**.</span></span>

1. <span data-ttu-id="d5f32-169">Selecione o botão Voltar (**<**) para retornar à página anterior.</span><span class="sxs-lookup"><span data-stu-id="d5f32-169">Select the back button (**<**) to return to the previous page.</span></span>

    <span data-ttu-id="d5f32-170">![Lista de verificação de manutenção e detalhes da linha](media/am-mobile-05.png "Lista de verificação de manutenção e detalhes da linha")</span><span class="sxs-lookup"><span data-stu-id="d5f32-170">![Maintenance checklist and line details](media/am-mobile-05.png "Maintenance checklist and line details")</span></span>

## <a name="view-and-update-asset-counters-on-a-work-order-job"></a><span data-ttu-id="d5f32-171">Exibir e atualizar contadores de ativos em um trabalho da ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="d5f32-171">View and update asset counters on a work order job</span></span>

1. <span data-ttu-id="d5f32-172">No seu dispositivo móvel, abra o espaço de trabalho **Gerenciamento de ativos**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-172">On your mobile device, open the **Asset management** workspace.</span></span>

1. <span data-ttu-id="d5f32-173">Selecione **Todas as ordens de serviço de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-173">Select **All maintenance work orders**.</span></span>

1. <span data-ttu-id="d5f32-174">Selecione a ordem de serviço > trabalho da ordem de serviço cujos contadores de ativos você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="d5f32-174">Select the work order > work order job you want to view asset counters for.</span></span>
    - <span data-ttu-id="d5f32-175">Como opção, você também pode selecionar **Meu calendário de trabalhos de ordens de serviço** ou **Minha lista de trabalhos de ordens de serviço** na home page para navegar até a página **Detalhes do trabalho da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-175">Alternatively, you can also select **My work order jobs calendar** or **My work order jobs list** on the home page to navigate to the **work order job details** page.</span></span>

1. <span data-ttu-id="d5f32-176">Selecione **Contadores de ativos** na página **Detalhes do trabalho da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-176">Select **Asset counters** on the **Work order job details** page.</span></span>

1. <span data-ttu-id="d5f32-177">Você verá uma lista de contadores de ativos relacionadas ao trabalho da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="d5f32-177">You see a list of asset counters related to the work order job.</span></span> <span data-ttu-id="d5f32-178">Selecionar o ícone de lápis em uma linha de contador de ativos para atualizar o valor do contador.</span><span class="sxs-lookup"><span data-stu-id="d5f32-178">Select the pencil icon on an asset counter line to update the counter value.</span></span>

1. <span data-ttu-id="d5f32-179">Insira um novo valor de contador e selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-179">Enter a new counter value, and select **Done**.</span></span>

    <span data-ttu-id="d5f32-180">![Exibir e atualizar contadores de ativos](media/am-mobile-06.png "Exibir e atualizar contadores de ativos")</span><span class="sxs-lookup"><span data-stu-id="d5f32-180">![View and update asset counters](media/am-mobile-06.png "View and update asset counters")</span></span>

## <a name="register-consumption-on-a-work-order-job"></a><span data-ttu-id="d5f32-181">Registrar o consumo em um trabalho da ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="d5f32-181">Register consumption on a work order job</span></span>

1. <span data-ttu-id="d5f32-182">No seu dispositivo móvel, abra o espaço de trabalho **Gerenciamento de ativos**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-182">On your mobile device, open the **Asset management** workspace.</span></span>

1. <span data-ttu-id="d5f32-183">Selecione **Todas as ordens de serviço de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-183">Select **All maintenance work orders**.</span></span>

1. <span data-ttu-id="d5f32-184">Selecione a ordem de serviço > trabalho da ordem de serviço ao qual você deseja adicionar registros de consumo.</span><span class="sxs-lookup"><span data-stu-id="d5f32-184">Select the work order > work order job you want to add consumption registrations for.</span></span>
    - <span data-ttu-id="d5f32-185">Como opção, você também pode selecionar **Meu calendário de trabalhos de ordens de serviço** ou **Minha lista de trabalhos de ordens de serviço** na home page para navegar até a página **Detalhes do trabalho da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-185">Alternatively, you can also select **My work order jobs calendar** or **My work order jobs list** on the home page to navigate to the **work order job details** page.</span></span>

1. <span data-ttu-id="d5f32-186">Selecione **Diários** na página **Detalhes do trabalho da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-186">Select **Journals** on the **Work order job details** page.</span></span>

1. <span data-ttu-id="d5f32-187">Selecione **Adicionar horas** para criar registros de horas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d5f32-187">Select **Add hours** to create work hour registrations.</span></span>
    1. <span data-ttu-id="d5f32-188">Selecione a **Categoria** na pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d5f32-188">Select the **Category** from the lookup.</span></span>
    1. <span data-ttu-id="d5f32-189">No campo **Horas** , insira o número de horas de trabalho gastas no trabalho da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="d5f32-189">In the **Hours** field, enter the number of work hours spent on the work order job.</span></span>
    1. <span data-ttu-id="d5f32-190">Selecione a **Propriedade da linha** apropriada.</span><span class="sxs-lookup"><span data-stu-id="d5f32-190">Select the appropriate **Line property**.</span></span>
    1. <span data-ttu-id="d5f32-191">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-191">Select **Done**.</span></span>

1. <span data-ttu-id="d5f32-192">Selecione **Adicionar itens** para criar registros de itens.</span><span class="sxs-lookup"><span data-stu-id="d5f32-192">Select **Add items** to create item registrations.</span></span>
    1. <span data-ttu-id="d5f32-193">Selecione o **Número do item** na pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d5f32-193">Select the **Item number** from the lookup.</span></span>
    1. <span data-ttu-id="d5f32-194">Selecione o **Site** na pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d5f32-194">Select the **Site** from the lookup.</span></span>
    1. <span data-ttu-id="d5f32-195">Insira a **Quantidade** de itens consumidos.</span><span class="sxs-lookup"><span data-stu-id="d5f32-195">Enter the **Quantity** of items consumed.</span></span>
    1. <span data-ttu-id="d5f32-196">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-196">Select **Done**.</span></span>

1. <span data-ttu-id="d5f32-197">Selecione **Adicionar despesa** para criar registros de despesas.</span><span class="sxs-lookup"><span data-stu-id="d5f32-197">Select **Add expense** to create expense registrations.</span></span>
    1. <span data-ttu-id="d5f32-198">Selecione a **Categoria** na pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d5f32-198">Select the **Category** from the lookup.</span></span>
    1. <span data-ttu-id="d5f32-199">Insira a quantidade do registro de despesas.</span><span class="sxs-lookup"><span data-stu-id="d5f32-199">Enter the quantity for the expense registration.</span></span>
    1. <span data-ttu-id="d5f32-200">Selecione a **Moeda de venda** na pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d5f32-200">Select the **Sales currency** from the lookup.</span></span>
    1. <span data-ttu-id="d5f32-201">Insira o **Preço de custo** do registro da despesa.</span><span class="sxs-lookup"><span data-stu-id="d5f32-201">Enter the **Cost price** for the expense registration.</span></span>
    1. <span data-ttu-id="d5f32-202">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-202">Select **Done**.</span></span>

    <span data-ttu-id="d5f32-203">![Atualizar um diário de ordem de trabalho](media/am-mobile-07.png "Atualizar um diário de ordem de trabalho")</span><span class="sxs-lookup"><span data-stu-id="d5f32-203">![Update a work order journal](media/am-mobile-07.png "Update a work order journal")</span></span>

## <a name="update-lifecycle-state-on-a-work-order"></a><span data-ttu-id="d5f32-204">Atualizar o estado de ciclo de vida em uma ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="d5f32-204">Update lifecycle state on a work order</span></span>

1. <span data-ttu-id="d5f32-205">No seu dispositivo móvel, abra o espaço de trabalho **Gerenciamento de ativos**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-205">On your mobile device, open the **Asset management** workspace.</span></span>

1. <span data-ttu-id="d5f32-206">Selecione **Todas as ordens de serviço de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-206">Select **All maintenance work orders**.</span></span>

1. <span data-ttu-id="d5f32-207">Selecione a ordem de serviço cujo estado de ciclo de vida você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="d5f32-207">Select the work order you want to update lifecycle state for.</span></span>

1. <span data-ttu-id="d5f32-208">Selecione o botão **Atualizar estado** na parte inferior da tela.</span><span class="sxs-lookup"><span data-stu-id="d5f32-208">Select the **Update state** button at the bottom of the screen.</span></span>

1. <span data-ttu-id="d5f32-209">Selecione um novo estado de ciclo de vida na lista.</span><span class="sxs-lookup"><span data-stu-id="d5f32-209">Select a new lifecycle state from the list.</span></span>

1. <span data-ttu-id="d5f32-210">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-210">Select **Done**.</span></span>

    <span data-ttu-id="d5f32-211">![Atualizar o estado de ciclo de vida em uma ordem de serviço](media/am-mobile-08.png "Atualizar o estado de ciclo de vida em uma ordem de serviço")</span><span class="sxs-lookup"><span data-stu-id="d5f32-211">![Update lifecycle state on a work order](media/am-mobile-08.png "Update lifecycle state on a work order")</span></span>

## <a name="create-a-maintenance-request"></a><span data-ttu-id="d5f32-212">Criar uma solicitação de manutenção</span><span class="sxs-lookup"><span data-stu-id="d5f32-212">Create a maintenance request</span></span>

1. <span data-ttu-id="d5f32-213">No seu dispositivo móvel, abra o espaço de trabalho **Gerenciamento de ativos**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-213">On your mobile device, open the **Asset management** workspace.</span></span>

1. <span data-ttu-id="d5f32-214">Selecione **Todas as solicitações de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-214">Select **All maintenance requests**.</span></span>

1. <span data-ttu-id="d5f32-215">Selecione **Ações** na parte inferior da tela e selecione **Criar solicitação de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-215">Select **Actions** at the bottom of the screen, and select **Create maintenance request**.</span></span>

1. <span data-ttu-id="d5f32-216">Se a sequência numérica estiver habilitada para solicitações de manutenção em **Gerenciamento de ativos**, o campo **Solicitação de manutenção** ficará oculto porque ele será preenchido automaticamente. Se o campo **Solicitação de manutenção** estiver visível, insira uma ID da solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="d5f32-216">If number sequence is enabled for maintenance requests in **Asset management**, the **Maintenance request** field is hidden because it is automatically filled out. If the **Maintenance request** field is visible, enter a maintenance request ID.</span></span>

1. <span data-ttu-id="d5f32-217">Selecione um **Tipo de solicitação de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-217">Select a **Maintenance request type**.</span></span>

1. <span data-ttu-id="d5f32-218">Insira uma **Descrição** para a solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="d5f32-218">Enter a **Description** for the maintenance request.</span></span>

1. <span data-ttu-id="d5f32-219">Selecione o **Ativo** para o qual você deseja criar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="d5f32-219">Select the **Asset** you want to create the request for.</span></span>

1. <span data-ttu-id="d5f32-220">Selecione o **Nível de serviço** da solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="d5f32-220">Select the **Service level** for the maintenance request.</span></span>

1. <span data-ttu-id="d5f32-221">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-221">Select **Done**.</span></span>

    <span data-ttu-id="d5f32-222">![Criar uma solicitação de manutenção](media/am-mobile-09.png "Criar uma solicitação de manutenção")</span><span class="sxs-lookup"><span data-stu-id="d5f32-222">![Create a maintenance request](media/am-mobile-09.png "Create a maintenance request")</span></span>

## <a name="add-attachment-to-a-maintenance-request"></a><span data-ttu-id="d5f32-223">Adicionar anexos a uma solicitação de manutenção</span><span class="sxs-lookup"><span data-stu-id="d5f32-223">Add attachment to a maintenance request</span></span>

1. <span data-ttu-id="d5f32-224">No seu dispositivo móvel, abra o espaço de trabalho **Gerenciamento de ativos**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-224">On your mobile device, open the **Asset management** workspace.</span></span>

1. <span data-ttu-id="d5f32-225">Selecione **Todas as solicitações de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-225">Select **All maintenance requests**.</span></span>

1. <span data-ttu-id="d5f32-226">Selecione a solicitação de manutenção à qual você deseja adicionar um anexo.</span><span class="sxs-lookup"><span data-stu-id="d5f32-226">Select the maintenance request you want to add an attachment to.</span></span>

1. <span data-ttu-id="d5f32-227">Selecione **Anexos** na parte inferior da tela.</span><span class="sxs-lookup"><span data-stu-id="d5f32-227">Select **Attachments** at the bottom of the screen.</span></span>

1. <span data-ttu-id="d5f32-228">Selecione **Adicionar anexos**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-228">Select **Add attachments**.</span></span>

1. <span data-ttu-id="d5f32-229">Insira o **Nome** e as **Notas** do anexo.</span><span class="sxs-lookup"><span data-stu-id="d5f32-229">Enter **Name** and **Notes** for the attachment.</span></span>

1. <span data-ttu-id="d5f32-230">Selecione **Escolher imagem** para selecionar uma foto na galeria do dispositivo móvel ou **Tirar foto** para tirar uma foto.</span><span class="sxs-lookup"><span data-stu-id="d5f32-230">Select **Choose image** to select a photo from the mobile gallery or **Take photo** to take a photo.</span></span>

1. <span data-ttu-id="d5f32-231">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="d5f32-231">Select **Done**.</span></span>

    <span data-ttu-id="d5f32-232">![Adicionar um anexo a uma solicitação de manutenção](media/am-mobile-10.png "Adicionar um anexo a uma solicitação de manutenção")</span><span class="sxs-lookup"><span data-stu-id="d5f32-232">![Add an attachment to a maintenance request](media/am-mobile-10.png "Add an attachment to a maintenance request")</span></span>
