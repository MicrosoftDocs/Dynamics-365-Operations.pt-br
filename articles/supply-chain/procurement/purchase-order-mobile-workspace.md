---
title: Área de trabalho móvel para aprovação de ordem de compra
description: Este tópico fornece informações sobre a área de trabalho móvel de aprovação do pedido de compra, que permite visualizar pedidos e responder a eles através de ações. Por exemplo, você pode aprovar ou rejeitar uma ordem de compra.
author: mkirknel
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchVendorPortalRequests
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 30211
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b7f5d61ade071e75d53d5036a47fea438d8afbe6
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249416"
---
# <a name="purchase-order-approval-mobile-workspace"></a><span data-ttu-id="66a63-104">Área de trabalho móvel para aprovação de ordem de compra</span><span class="sxs-lookup"><span data-stu-id="66a63-104">Purchase order approval mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

<span data-ttu-id="66a63-105">Este tópico fornece informações sobre a área de trabalho móvel de **Aprovação de ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="66a63-105">This topic provides information about the **Purchase order approval** mobile workspace.</span></span> <span data-ttu-id="66a63-106">Esta área de trabalho permite que você veja pedidos e responda através de ações.</span><span class="sxs-lookup"><span data-stu-id="66a63-106">This workspace lets you view purchase orders and respond to them through actions.</span></span> <span data-ttu-id="66a63-107">Por exemplo, você pode aprovar ou rejeitar uma ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="66a63-107">For example, you can approve or reject a purchase order.</span></span>
 
## <a name="overview"></a><span data-ttu-id="66a63-108">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="66a63-108">Overview</span></span> 
<span data-ttu-id="66a63-109">As ordens de compra que exigem aprovação passam por um fluxo de trabalho de aprovação.</span><span class="sxs-lookup"><span data-stu-id="66a63-109">Purchase orders that requires approval go through an approval workflow.</span></span> <span data-ttu-id="66a63-110">O fluxo de trabalho pode incluir várias etapas que exigem que uma ou mais pessoas ajam.</span><span class="sxs-lookup"><span data-stu-id="66a63-110">The workflow can include various steps that require that one or more people take action.</span></span> <span data-ttu-id="66a63-111">Por exemplo, uma pessoa pode ter que completar uma tarefa ou aprovar a ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="66a63-111">For example, a person might have to complete a task or approve the purchase order.</span></span> 

<span data-ttu-id="66a63-112">A área de trabalho móvel **Aprovação de ordem de compra** permite facilmente responder e exibir ordens de compra no dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="66a63-112">The **Purchase order approval** mobile workspace lets you easily view and respond to purchase orders from your mobile device.</span></span> <span data-ttu-id="66a63-113">Este espaço de trabalho também permite tomar as mesmas medidas de fluxo de trabalho que você toma no cliente Web.</span><span class="sxs-lookup"><span data-stu-id="66a63-113">This workspace also lets you take the same workflow actions that you can take from the web client.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="66a63-114">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="66a63-114">Prerequisites</span></span>
<span data-ttu-id="66a63-115">Os pré-requisitos variam, dependendo da versão do Supply Chain Management que foi implantada para sua organização.</span><span class="sxs-lookup"><span data-stu-id="66a63-115">The prerequisites vary, depending on the version of Supply Chain Management that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-supply-chain-management"></a><span data-ttu-id="66a63-116">Pré-requisito para usar o Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="66a63-116">Prerequisites if you use Supply Chain Management</span></span> 
<span data-ttu-id="66a63-117">Se o Finance and Operations foi implantado na organização, o administrador do sistema deverá publicar o espaço de trabalho móvel **Aprovação de ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="66a63-117">If Finance and Operations has been deployed for your organization, the system administrator must publish the **Purchase order approval** mobile workspace.</span></span> <span data-ttu-id="66a63-118">Para obter instruções, consulte [Publicar um espaço de trabalho móvel](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="66a63-118">For instructions, see [Publish a mobile workspace](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a><span data-ttu-id="66a63-119">Pré-requisitos se você usa a versão 1611 do Microsoft Dynamics 365 for Operations com a atualização de plataforma 3 ou posterior</span><span class="sxs-lookup"><span data-stu-id="66a63-119">Prerequisites if you use Microsoft Dynamics 365 for Operations version 1611 with Platform update 3 or later</span></span>
<span data-ttu-id="66a63-120">Se o Microsoft Dynamics 365 for Operations versão 1611 com a atualização de plataforma 3 ou posterior foi implantado na organização, o administrador do sistema deverá atender aos pré-requisitos a seguir.</span><span class="sxs-lookup"><span data-stu-id="66a63-120">If Microsoft Dynamics 365 for Operations version 1611 with Platform update 3 or later has been deployed for your organization, the system administrator must complete the following prerequisites.</span></span> 

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="66a63-121">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="66a63-121">Prerequisite</span></span></th>
<th><span data-ttu-id="66a63-122">Função</span><span class="sxs-lookup"><span data-stu-id="66a63-122">Role</span></span></th>
<th><span data-ttu-id="66a63-123">descrição</span><span class="sxs-lookup"><span data-stu-id="66a63-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="66a63-124">Implementar o KB 4017918.</span><span class="sxs-lookup"><span data-stu-id="66a63-124">Implement KB 4017918.</span></span></td>
<td><span data-ttu-id="66a63-125">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="66a63-125">System administrator</span></span></td>
<td><span data-ttu-id="66a63-126">o KB 4017918 é um hotfix de metadados ou atualização X++ que contém a área de trabalho móvel <strong>Aprovação de ordem de compra</strong>.</span><span class="sxs-lookup"><span data-stu-id="66a63-126">KB 4017918 is an X++ update or metadata hotfix that contains the <strong>Purchase order approval</strong> mobile workspace.</span></span> <span data-ttu-id="66a63-127">Para implementar o KB 4017918, o administrador do sistema deve seguir estas etapas.</span><span class="sxs-lookup"><span data-stu-id="66a63-127">To implement KB 4017918, your system administrator must follow these steps.</span></span>
<ol>
<li><span data-ttu-id="66a63-128"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Baixe o hotfix de metadados do Microsoft Dynamics Lifecycle Services (LCS)</a>.</span><span class="sxs-lookup"><span data-stu-id="66a63-128"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Download the metadata hotfix from Microsoft Dynamics Lifecycle Services (LCS)</a>.</span></span></li>
<li><span data-ttu-id="66a63-129"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Instalar o hotfix de metadados</a>.</span><span class="sxs-lookup"><span data-stu-id="66a63-129"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Install the metadata hotfix</a>.</span></span></li>
<li><span data-ttu-id="66a63-130"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Criar um pacote implantável</a> que contenha o modelo <strong>SCMMobile</strong> e, em seguida, carregar o pacote implantável para o LCS.</span><span class="sxs-lookup"><span data-stu-id="66a63-130"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Create a deployable package</a> that contains the <strong>SCMMobile</strong> model, and then upload the deployable package to LCS.</span></span></li>
<li><span data-ttu-id="66a63-131"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Aplicar o pacote implantável</a>.</span><span class="sxs-lookup"><span data-stu-id="66a63-131"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Apply the deployable package</a>.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="66a63-132">Publicar a área de trabalho móvel de <strong>Aprovação de ordem de compra</strong>.</span><span class="sxs-lookup"><span data-stu-id="66a63-132">Publish the <strong>Purchase order approval</strong> mobile workspace.</span></span></td>
<td><span data-ttu-id="66a63-133">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="66a63-133">System administrator</span></span></td>
<td><span data-ttu-id="66a63-134">Consulte <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publicar um espaço de trabalho móvel</a>.</span><span class="sxs-lookup"><span data-stu-id="66a63-134">See <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="66a63-135">Baixa e instala o aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="66a63-135">Download and install the mobile app</span></span>
<span data-ttu-id="66a63-136">Baixe e instale o aplicativo móvel Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="66a63-136">Download and install the Finance and Operations mobile app:</span></span>

- [<span data-ttu-id="66a63-137">Para telefones Android</span><span class="sxs-lookup"><span data-stu-id="66a63-137">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
- [<span data-ttu-id="66a63-138">Para iPhones</span><span class="sxs-lookup"><span data-stu-id="66a63-138">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)


## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="66a63-139">Entrar no aplicativo móvel</span><span class="sxs-lookup"><span data-stu-id="66a63-139">Sign in to the mobile app</span></span>

1. <span data-ttu-id="66a63-140">Inicie o aplicativo móvel no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="66a63-140">Start the app on your mobile device.</span></span>
2. <span data-ttu-id="66a63-141">Insira a URL do Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="66a63-141">Enter your Microsoft Dynamics 365 URL.</span></span>
3. <span data-ttu-id="66a63-142">Na primeira vez que você iniciar a sessão, será solicitado o nome de usuário e a senha.</span><span class="sxs-lookup"><span data-stu-id="66a63-142">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="66a63-143">Insira suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="66a63-143">Enter your credentials.</span></span>
4. <span data-ttu-id="66a63-144">Depois de entrar, serão exibidos os espaços de trabalho disponíveis da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="66a63-144">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="66a63-145">Observe que se o seu administrador de sistema publica um novo espaço de de trabalho depois, você terá que atualizar a lista dos espaços de trabalho móveis.</span><span class="sxs-lookup"><span data-stu-id="66a63-145">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

![A área de trabalho de aprovação de ordem de compra na lista dos espaços de trabalho disponíveis](./media/po-workspaces.png)

## <a name="view-orders-that-are-assigned-to-you"></a><span data-ttu-id="66a63-147">Exibir ordens atribuídos a você</span><span class="sxs-lookup"><span data-stu-id="66a63-147">View orders that are assigned to you</span></span>
1. <span data-ttu-id="66a63-148">No seu dispositivo móvel, selecione a área de trabalho **Aprovação de ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="66a63-148">On your mobile device, select the **Purchase order approval** workspace.</span></span>
2. <span data-ttu-id="66a63-149">Selecione **Ordens atribuída a mim** para exibir todas as ordens de compra para a qual foi solicitado a você tomar uma ação no fluxo de trabalho de aprovação de ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="66a63-149">Select **Orders assigned to me** to view all the purchase orders for which you've been asked to take action in the purchase order approval workflow.</span></span>
3. <span data-ttu-id="66a63-150">Selecione uma ordem.</span><span class="sxs-lookup"><span data-stu-id="66a63-150">Select an order.</span></span> <span data-ttu-id="66a63-151">Na página **Detalhes da ordem**, você verá as informações e as linhas de cabeçalho da ordem.</span><span class="sxs-lookup"><span data-stu-id="66a63-151">On the **Order details** page, you will see the order header information and lines.</span></span> <span data-ttu-id="66a63-152">Também é possível localizar diretrizes de tarefas de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="66a63-152">You can also find guidelines from the workflow task.</span></span>
4. <span data-ttu-id="66a63-153">Selecione **Distribuições contábeis** para abrir a página **Distribuições contábeis de cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="66a63-153">Select **Accounting distributions** to open the **Header accounting distributions** page.</span></span>
5. <span data-ttu-id="66a63-154">Retorne à página **Detalhes da ordem**, e selecione uma linha.</span><span class="sxs-lookup"><span data-stu-id="66a63-154">Return to the **Order details** page, and select a line.</span></span> <span data-ttu-id="66a63-155">Nos detalhes de linha de ordem, você também pode explorar distribuições contábeis específicas de linha.</span><span class="sxs-lookup"><span data-stu-id="66a63-155">From the order line details, you can also explore the line-specific accounting distributions.</span></span>

## <a name="complete-an-action-on-the-purchase-order"></a><span data-ttu-id="66a63-156">Conclua uma ação na ordem de compra</span><span class="sxs-lookup"><span data-stu-id="66a63-156">Complete an action on the purchase order</span></span>
<span data-ttu-id="66a63-157">Depois de ver a ordem de compra que lhe foi atribuído e ler as instruções de fluxo de trabalho, você deve estar pronto para agir.</span><span class="sxs-lookup"><span data-stu-id="66a63-157">After you've viewed the purchase order that is assigned to you and read the workflow instructions, you should be ready to take action.</span></span>

1. <span data-ttu-id="66a63-158">No seu dispositivo móvel, selecione a área de trabalho **Aprovação de ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="66a63-158">On your mobile device, select the **Purchase order approval** workspace.</span></span>
2. <span data-ttu-id="66a63-159">Selecione **Ordens atribuída a mim** para exibir todas as ordens de compra para a qual foi solicitado a você tomar uma ação no fluxo de trabalho de aprovação de ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="66a63-159">Select **Orders assigned to me** to view all the purchase orders for which you've been asked to take action in the purchase order approval workflow.</span></span>
3. <span data-ttu-id="66a63-160">Selecione uma ordem, e exiba a página de detalhes.</span><span class="sxs-lookup"><span data-stu-id="66a63-160">Select an order, and view the details page.</span></span>
4. <span data-ttu-id="66a63-161">Selecione **Ações** para mostrar as ações disponíveis.</span><span class="sxs-lookup"><span data-stu-id="66a63-161">Select **Actions** to show the available actions.</span></span> <span data-ttu-id="66a63-162">As ações disponíveis dependem da tarefa que lhe foi atribuída.</span><span class="sxs-lookup"><span data-stu-id="66a63-162">The actions that are available depend on the task that has been assigned to you.</span></span>

    | <span data-ttu-id="66a63-163">Ação de tarefa</span><span class="sxs-lookup"><span data-stu-id="66a63-163">Task action</span></span>    | <span data-ttu-id="66a63-164">Ação de aprovação</span><span class="sxs-lookup"><span data-stu-id="66a63-164">Approval action</span></span>  |
    |----------------|------------------|
    | <span data-ttu-id="66a63-165">Completo</span><span class="sxs-lookup"><span data-stu-id="66a63-165">Complete</span></span>       | <span data-ttu-id="66a63-166">Aprovar</span><span class="sxs-lookup"><span data-stu-id="66a63-166">Approve</span></span>          |
    | <span data-ttu-id="66a63-167">Retornar</span><span class="sxs-lookup"><span data-stu-id="66a63-167">Return</span></span>         | <span data-ttu-id="66a63-168">Rejeitar</span><span class="sxs-lookup"><span data-stu-id="66a63-168">Reject</span></span>           |
    | <span data-ttu-id="66a63-169">Solicitar Alteração</span><span class="sxs-lookup"><span data-stu-id="66a63-169">Request change</span></span> | <span data-ttu-id="66a63-170">Solicitar Alteração</span><span class="sxs-lookup"><span data-stu-id="66a63-170">Request change</span></span>   |
    | <span data-ttu-id="66a63-171">Delegado</span><span class="sxs-lookup"><span data-stu-id="66a63-171">Delegate</span></span>       | <span data-ttu-id="66a63-172">Delegado</span><span class="sxs-lookup"><span data-stu-id="66a63-172">Delegate</span></span>         |

5. <span data-ttu-id="66a63-173">Selecione a ação adequada.</span><span class="sxs-lookup"><span data-stu-id="66a63-173">Select the appropriate action.</span></span>
6. <span data-ttu-id="66a63-174">Na página **Concluir tarefa**, insira um comentário.</span><span class="sxs-lookup"><span data-stu-id="66a63-174">On the **Complete task** page, enter a comment.</span></span> <span data-ttu-id="66a63-175">Observe que se você selecionar a ação **Delegar**, será necessário selecionar um usuário para o qual delegar a tarefa.</span><span class="sxs-lookup"><span data-stu-id="66a63-175">Note that if you select the **Delegate** action, you must select a user to delegate the task to.</span></span>
7. <span data-ttu-id="66a63-176">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="66a63-176">Select **Done**.</span></span> <span data-ttu-id="66a63-177">Depois de atualizar sua área de trabalho, a ordem de compra não estará na lista.</span><span class="sxs-lookup"><span data-stu-id="66a63-177">After you refresh your workspace, the purchase order will no longer be in your list.</span></span> 
