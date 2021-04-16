---
title: Configurar o espaço de trabalho móvel Gerenciamento de ativos
description: Este tópico descreve como configurar o Microsoft Dynamics 365 Supply Chain Management e o aplicativo móvel do Finance and Operations (Dynamics 365) para executar um espaço de trabalho móvel Gerenciamento de ativos que os trabalhadores podem usar para realizar tarefas de gerenciamento de ativos.
author: johanhoffmann
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-22
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: bc170df2fc58ae6b42fbc8834caad0bb7cd16f69
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837768"
---
# <a name="set-up-the-asset-management-mobile-workspace"></a><span data-ttu-id="a7fdd-103">Configurar o espaço de trabalho móvel Gerenciamento de ativos</span><span class="sxs-lookup"><span data-stu-id="a7fdd-103">Set up the Asset management mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a7fdd-104">Este tópico descreve como configurar o Microsoft Dynamics 365 Supply Chain Management e o aplicativo móvel do Finance and Operations (Dynamics 365) para executar um espaço de trabalho móvel **Gerenciamento de ativos** que os trabalhadores podem usar para realizar tarefas de gerenciamento de ativos.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-104">This topic describes how to set up Microsoft Dynamics 365 Supply Chain Management and the Finance and Operations (Dynamics 365) mobile app to run an **Asset management** mobile workspace that workers can use to perform asset management tasks.</span></span>

## <a name="set-up-maintenance-worker-users-in-supply-chain-management"></a><span data-ttu-id="a7fdd-105">Configurar usuários de funcionários de manutenção no Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="a7fdd-105">Set up maintenance worker users in Supply Chain Management</span></span>

<span data-ttu-id="a7fdd-106">Para cada usuário que precisar de acesso ao espaço de trabalho móvel **Gerenciamento de ativos**, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-106">For each user that requires access to the **Asset management** mobile workspace, follow these steps.</span></span>

1. <span data-ttu-id="a7fdd-107">No Supply Chain Management, vá para **Recursos humanos \> Trabalhadores** e verifique se há um registro de trabalhador para o usuário que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-107">In Supply Chain Management, go to **Human resources \> Workers**, and make sure that a worker record exists for the user that you want to set up.</span></span> <span data-ttu-id="a7fdd-108">Crie um novo registro de trabalhador conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-108">Create a new worker record as required.</span></span>
1. <span data-ttu-id="a7fdd-109">Vá para **Gerenciamento de ativos \> Configuração \> Trabalhadores \> Trabalhadores** e verifique se o registro de trabalhador que você identificou (ou criou) na etapa anterior foi mapeado para um registro de funcionário de manutenção.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-109">Go to **Asset management \> Setup \> Workers \> Workers**, and make sure that the worker record that you identified (or created) in the previous step is mapped to a maintenance worker record.</span></span> <span data-ttu-id="a7fdd-110">Crie um novo registro de funcionário de manutenção conforme necessário e defina o campo **Trabalhador** como o registro de trabalhador da etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-110">Create a new maintenance worker record as required, and set the **Worker** field to the worker record from the previous step.</span></span>
1. <span data-ttu-id="a7fdd-111">Vá para **Gerenciamento de ativos \> Configuração \> Trabalhadores \> Grupos de funcionários de manutenção** e verifique se o registro de funcionário de manutenção que você identificou (ou criou) na etapa anterior pertence a um grupo de funcionários de manutenção.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-111">Go to **Asset management \> Setup \> Workers \> Maintenance worker groups**, and make sure that the maintenance worker record that you identified (or created) in the previous step belongs to a maintenance worker group.</span></span>
1. <span data-ttu-id="a7fdd-112">Vá para **Administração do sistema \> Usuários**.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-112">Go to **System administration \> Users**.</span></span>
1. <span data-ttu-id="a7fdd-113">Selecione o usuário relevante na grade.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-113">Select the relevant user in the grid.</span></span>
1. <span data-ttu-id="a7fdd-114">Na FastTab **Detalhes do Usuário**, defina o campo **Pessoa** como a conta de trabalhador que você deseja associar à conta de usuário atual.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-114">On the **User Details** FastTab, set the **Person** field to the worker account that you want to associate with the current user account.</span></span> <span data-ttu-id="a7fdd-115">Essa conta de trabalhador deve ser o registro de trabalhador que você identificou (ou criou) na etapa 1 e mapeou para um registro de funcionário de manutenção na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-115">This worker account should be the worker record that you identified (or created) in step 1 and mapped to a maintenance worker record in step 2.</span></span>

> [!NOTE]
> <span data-ttu-id="a7fdd-116">As permissões de usuário e as funções de segurança se aplicam aos recursos do espaço de trabalho móvel **Gerenciamento de ativos** assim como se aplicam aos recursos da interface de usuário do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-116">User permissions and security roles apply to the features of the **Asset management** mobile workspace just as they apply to the features of the Supply Chain Management user interface.</span></span> <span data-ttu-id="a7fdd-117">Portanto, cada usuário configurado para acessar o espaço de trabalho móvel **Gerenciamento de ativos** deve ter as funções de segurança necessárias para executar operações semelhantes diretamente no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-117">Therefore, every user that you set up to access the **Asset management** mobile workspace must have the security roles that are required to perform similar operations directly in Supply Chain Management.</span></span>

## <a name="publish-the-asset-management-mobile-workspace"></a><span data-ttu-id="a7fdd-118">Publicar o espaço de trabalho móvel Gerenciamento de ativos</span><span class="sxs-lookup"><span data-stu-id="a7fdd-118">Publish the Asset management mobile workspace</span></span>

<span data-ttu-id="a7fdd-119">Para disponibilizar recursos de gerenciamento de ativos no aplicativo móvel do Finance and Operations (Dynamics 365), você deve publicar o espaço de trabalho móvel **Gerenciamento de ativos**.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-119">To make asset management features available in the Finance and Operations (Dynamics 365) mobile app, you must publish the **Asset management** mobile workspace.</span></span>

1. <span data-ttu-id="a7fdd-120">No Supply Chain Management, selecione o botão **Configurações** (o símbolo de engrenagem no canto superior direito) e, em seguida, selecione **Aplicativo móvel** no menu.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-120">In Supply Chain Management, select the **Settings** button (the gear symbol in upper-right corner), and then select **Mobile app** on the menu.</span></span>
1. <span data-ttu-id="a7fdd-121">Na caixa de diálogo **Gerenciar aplicativo móvel**, localize o bloco **Gerenciamento de ativos**.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-121">In the **Manage mobile app** dialog box, find the **Asset Management** tile.</span></span> <span data-ttu-id="a7fdd-122">Se ele contiver o texto "Nos metadados - não publicado", o espaço de trabalho ainda não foi publicado.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-122">If it contains the text "In metadata - not published," the workspace hasn't yet been published.</span></span> <span data-ttu-id="a7fdd-123">Se ele contiver o texto "Nos metadados - publicado", o espaço de trabalho já foi publicado e você poderá ignorar o restante deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-123">If it contains the text "In metadata - published," the workspace has already been published, and you can skip the rest of this procedure.</span></span>

    <span data-ttu-id="a7fdd-124">![Caixa de diálogo Gerenciar aplicativo móvel](media/mobile-workspaces.png "Caixa de diálogo Gerenciar aplicativo móvel")</span><span class="sxs-lookup"><span data-stu-id="a7fdd-124">![Manage mobile app dialog box](media/mobile-workspaces.png "Manage mobile app dialog box")</span></span>

1. <span data-ttu-id="a7fdd-125">Selecione o bloco **Gerenciamento de ativos** e, em seguida, selecione **Publicar** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-125">Select the **Asset Management** tile, and then select **Publish** on the toolbar.</span></span> <span data-ttu-id="a7fdd-126">Após alguns segundos, você receberá uma notificação informando que o espaço de trabalho foi publicado com êxito.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-126">After a few seconds, you should receive a notification that states that the workspace has been successfully published.</span></span> <span data-ttu-id="a7fdd-127">Além disso, o texto no bloco será alterado para "Nos metadados - publicado".</span><span class="sxs-lookup"><span data-stu-id="a7fdd-127">Additionally, the text on the tile should change to "In metadata - published."</span></span>

## <a name="install-and-set-up-the-finance-and-operations-dynamics-365-mobile-app"></a><span data-ttu-id="a7fdd-128">Instalar e configurar o aplicativo móvel do Finance and Operations (Dynamics 365)</span><span class="sxs-lookup"><span data-stu-id="a7fdd-128">Install and set up the Finance and Operations (Dynamics 365) mobile app</span></span>

1. <span data-ttu-id="a7fdd-129">Acesse uma das seguintes lojas de aplicativos para instalar o aplicativo **Microsoft Finance and Operations (Dynamics 365)** no seu dispositivo móvel:</span><span class="sxs-lookup"><span data-stu-id="a7fdd-129">Go to one of the following app stores to install the **Microsoft Finance and Operations (Dynamics 365)** app on your mobile device:</span></span>

    - [<span data-ttu-id="a7fdd-130">Para dispositivos Google Android</span><span class="sxs-lookup"><span data-stu-id="a7fdd-130">For Google Android devices</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
    - [<span data-ttu-id="a7fdd-131">Para dispositivos Apple iOS</span><span class="sxs-lookup"><span data-stu-id="a7fdd-131">For Apple iOS devices</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

1. <span data-ttu-id="a7fdd-132">Abra o aplicativo do Finance and Operations (Dynamics 365).</span><span class="sxs-lookup"><span data-stu-id="a7fdd-132">Open the Finance and Operations (Dynamics 365) app.</span></span> <span data-ttu-id="a7fdd-133">A página de entrada será exibida.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-133">The sign-in page should appear.</span></span> <span data-ttu-id="a7fdd-134">No campo **Entrar**, insira a URL do Supply Chain Management ou selecione uma URL recente na lista **Ambientes recentes** e, em seguida, toque em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-134">In the **Sign in** field, enter your Supply Chain Management URL, or select a recent URL in the **Recent environments** list, and then tap **Connect**.</span></span>

    <span data-ttu-id="a7fdd-135">![Página de entrada](media/mobile-app-sign-in.png "Página de entrada")</span><span class="sxs-lookup"><span data-stu-id="a7fdd-135">![Sign-in page](media/mobile-app-sign-in.png "Sign-in page")</span></span>

1. <span data-ttu-id="a7fdd-136">Se for solicitado que você confirme a conexão, marque a caixa de seleção **Estou ciente** e toque em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-136">If you're prompted to confirm the connection, select the **I understand** check box, and then tap **Connect**.</span></span>
1. <span data-ttu-id="a7fdd-137">Na página **Escolher uma conta**, use sua conta Microsoft para entrar no aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-137">On the **Pick an account** page, use your Microsoft account to sign in to the mobile application.</span></span>

    <span data-ttu-id="a7fdd-138">A página **Espaços de trabalho** será exibida.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-138">The **Workspaces** page appears.</span></span> <span data-ttu-id="a7fdd-139">Ela lista cada espaço de trabalho móvel que foi publicado pela sua instância do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-139">It lists every mobile workspace that has been published by your Supply Chain Management instance.</span></span>

    <span data-ttu-id="a7fdd-140">![Lista de espaços de trabalho](media/mobile-app-workspaces.png "Lista de espaços de trabalho")</span><span class="sxs-lookup"><span data-stu-id="a7fdd-140">![List of workspaces](media/mobile-app-workspaces.png "List of workspaces")</span></span>

1. <span data-ttu-id="a7fdd-141">Se for necessário alterar a entidade legal (empresa), toque no botão Menu (às vezes chamado de hambúrguer ou botão de hambúrguer) no canto superior esquerdo e, em seguida, toque em **Alterar empresa**.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-141">If you must change the legal entity (company), tap the Menu button (sometimes referred to as the hamburger or the hamburger button) in the upper-left corner, and then tap **Change company**.</span></span>

    <span data-ttu-id="a7fdd-142">![Alterar a entidade legal](media/mobile-app-change-comp.png "Alterar a entidade legal")</span><span class="sxs-lookup"><span data-stu-id="a7fdd-142">![Changing the legal entity](media/mobile-app-change-comp.png "Changing the legal entity")</span></span>

1. <span data-ttu-id="a7fdd-143">Na página **Espaços de trabalho**, selecione o espaço de trabalho com o qual você deseja trabalhar para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="a7fdd-143">On the **Workspaces** page, select the workspace that you want to work with to open it.</span></span>

    <span data-ttu-id="a7fdd-144">![Espaço de trabalho móvel de gerenciamento de ativos](media/mobile-app-asset-workspace.png "Espaço de trabalho móvel de gerenciamento de ativos")</span><span class="sxs-lookup"><span data-stu-id="a7fdd-144">![Asset management mobile workspace](media/mobile-app-asset-workspace.png "Asset management mobile workspace")</span></span>

## <a name="work-with-the-asset-management-mobile-workspace"></a><span data-ttu-id="a7fdd-145">Trabalhar com o espaço de trabalho móvel Gerenciamento de ativos</span><span class="sxs-lookup"><span data-stu-id="a7fdd-145">Work with the Asset management mobile workspace</span></span>

<span data-ttu-id="a7fdd-146">Para obter mais informações sobre como trabalhar com o espaço de trabalho móvel **Gerenciamento de ativos**, consulte [Usar o espaço de trabalho móvel Gerenciamento de ativos](asset-management-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="a7fdd-146">For more information about how to work with the **Asset management** mobile workspace, see [Use the Asset management mobile workspace](asset-management-mobile-workspace.md).</span></span>

<span data-ttu-id="a7fdd-147">Para obter mais informações sobre o aplicativo móvel do Finance and Operations (Dynamics 365), consulte a [Home page do aplicativo móvel](../../fin-ops-core/dev-itpro/mobile-apps/Mobile-app-home-page.md).</span><span class="sxs-lookup"><span data-stu-id="a7fdd-147">For more information about the Finance and Operations (Dynamics 365) mobile app, see the [Mobile app home page](../../fin-ops-core/dev-itpro/mobile-apps/Mobile-app-home-page.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]