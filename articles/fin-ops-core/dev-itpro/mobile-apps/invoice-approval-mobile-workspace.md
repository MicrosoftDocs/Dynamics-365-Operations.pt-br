---
title: Espaço de trabalho móvel para aprovações de fatura
description: Este tópico fornece informações sobre a área de trabalho móvel de aprovações de fatura. Este espaço de trabalho fornece uma lista de faturas que foram atribuídas a você por meio do processo de fluxo de trabalho do cabeçalho da fatura de fornecedor.
author: abruer
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: d4ea1d81b0e4f92974ceb7d46386c9d9f6e48979
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248994"
---
# <a name="invoice-approvals-mobile-workspace"></a><span data-ttu-id="f2154-104">Espaço de trabalho móvel para aprovações de fatura</span><span class="sxs-lookup"><span data-stu-id="f2154-104">Invoice approvals mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f2154-105">Este tópico fornece informações sobre a área de trabalho móvel de **Aprovações de fatura**.</span><span class="sxs-lookup"><span data-stu-id="f2154-105">This topic provides information about the **Invoice approvals** mobile workspace.</span></span> <span data-ttu-id="f2154-106">Este espaço de trabalho fornece uma lista de faturas que foram atribuídas a você por meio do processo de fluxo de trabalho do cabeçalho da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="f2154-106">This workspace provides a list of invoices that have been assigned to you through the vendor invoice header workflow process.</span></span> 

<span data-ttu-id="f2154-107">Esse espaço de trabalho móvel deve ser usado com o aplicativo móvel Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f2154-107">This mobile workspace is intended to be used with the Finance and Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="f2154-108">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="f2154-108">Overview</span></span>

<span data-ttu-id="f2154-109">O espaço de trabalho móvel **Aprovações de fatura** permite que auxiliares e gerentes de contas a pagar visualizem faturas que lhes foram atribuídas como parte do processo de fluxo de trabalho do cabeçalho da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="f2154-109">The **Invoice approvals** mobile workspace lets Accounts payable clerks and managers view invoices that have been assigned to them as part of the vendor invoice header workflow process.</span></span> <span data-ttu-id="f2154-110">Você pode visualizar informações de fatura e mesmo detalhes de linhas e de distribuição para ajudá-lo a tomar decisões acertadas de aprovação.</span><span class="sxs-lookup"><span data-stu-id="f2154-110">You can view the invoice information, and even the line and distribution details, to help you make informed approval decisions.</span></span> <span data-ttu-id="f2154-111">A partir do espaço de trabalho, você pode tomar medidas para mover a fatura no processo de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f2154-111">From the workspace, you can take action to move the invoice through the workflow process.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="f2154-112">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f2154-112">Prerequisites</span></span>

<span data-ttu-id="f2154-113">Antes de usar este espaço de trabalho móvel, os seguintes pré-requisitos devem ser atendidos.</span><span class="sxs-lookup"><span data-stu-id="f2154-113">Before you can use this mobile workspace, the following prerequisites must be met.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="f2154-114">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="f2154-114">Prerequisite</span></span></th>
<th><span data-ttu-id="f2154-115">Função</span><span class="sxs-lookup"><span data-stu-id="f2154-115">Role</span></span></th>
<th><span data-ttu-id="f2154-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="f2154-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f2154-117">O Microsoft Dynamics 365 Finance deve ser implantado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f2154-117">Microsoft Dynamics 365 Finance must be deployed in your organization.</span></span></td>
<td><span data-ttu-id="f2154-118">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="f2154-118">System administrator</span></span></td>
<td><span data-ttu-id="f2154-119">Consulte <a href="../deployment/deploy-demo-environment.md">Implantar um ambiente de demonstração</a>.</span><span class="sxs-lookup"><span data-stu-id="f2154-119">See <a href="../deployment/deploy-demo-environment.md">Deploy a demo environment</a>.</span></span>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="f2154-120">A área de trabalho móvel <strong>Aprovações de fatura</strong> deve ser publicada.</span><span class="sxs-lookup"><span data-stu-id="f2154-120">The <strong>Invoice approvals</strong> mobile workspace must be published.</span></span></td>
<td><span data-ttu-id="f2154-121">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="f2154-121">System administrator</span></span></td>
<td><span data-ttu-id="f2154-122">Consulte <a href="publish-mobile-workspace.md">Publicar um espaço de trabalho móvel</a>.</span><span class="sxs-lookup"><span data-stu-id="f2154-122">See <a href="publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="f2154-123">Baixa e instala o aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="f2154-123">Download and install the mobile app</span></span>

<span data-ttu-id="f2154-124">Baixe e instale o aplicativo móvel Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="f2154-124">Download and install the Finance and Operations mobile app:</span></span>

-   [<span data-ttu-id="f2154-125">Para telefones Android</span><span class="sxs-lookup"><span data-stu-id="f2154-125">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="f2154-126">Para iPhones</span><span class="sxs-lookup"><span data-stu-id="f2154-126">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="f2154-127">Entrar no aplicativo móvel</span><span class="sxs-lookup"><span data-stu-id="f2154-127">Sign in to the mobile app</span></span>

1.  <span data-ttu-id="f2154-128">Inicie o aplicativo móvel no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f2154-128">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="f2154-129">Insira a URL do Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="f2154-129">Enter your Microsoft Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="f2154-130">Na primeira vez que você iniciar a sessão, será solicitado o nome de usuário e a senha.</span><span class="sxs-lookup"><span data-stu-id="f2154-130">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="f2154-131">Insira suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="f2154-131">Enter your credentials.</span></span>
4.  <span data-ttu-id="f2154-132">Depois de entrar, serão exibidos os espaços de trabalho disponíveis da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="f2154-132">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="f2154-133">Observe que se o seu administrador de sistema publica um novo espaço de de trabalho depois, você terá que atualizar a lista dos espaços de trabalho móveis.</span><span class="sxs-lookup"><span data-stu-id="f2154-133">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

    <span data-ttu-id="f2154-134">[![Efetue pull para atualizar](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="f2154-134">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="approve-invoices-by-using-the-invoice-approvals-mobile-workspace"></a><span data-ttu-id="f2154-135">Aprovar faturas usando o espaço de trabalho móvel para aprovações de fatura</span><span class="sxs-lookup"><span data-stu-id="f2154-135">Approve invoices by using the Invoice approvals mobile workspace</span></span>
1.  <span data-ttu-id="f2154-136">No seu dispositivo móvel, selecione o espaço de trabalho **Aprovações de fatura**.</span><span class="sxs-lookup"><span data-stu-id="f2154-136">On your mobile device, select the **Invoice approvals** workspace.</span></span>
2.  <span data-ttu-id="f2154-137">Selecione a fatura que foi atribuída a você pelo processo de fluxo de trabalho do cabeçalho da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="f2154-137">Select the invoice that has been assigned to you by the vendor invoice header workflow process.</span></span>
3.  <span data-ttu-id="f2154-138">Na página **Detalhes da fatura**, reveja as informações de cabeçalho da fatura, como informações de fornecedor e data.</span><span class="sxs-lookup"><span data-stu-id="f2154-138">On the **Invoice details** page, review the invoice header information, such as the vendor and date information.</span></span>
4.  <span data-ttu-id="f2154-139">Selecione uma linha da fatura para exibir informações mais detalhadas sobre ela na exibição **Detalhes de linha de fatura**.</span><span class="sxs-lookup"><span data-stu-id="f2154-139">Select a line on the invoice to view more detailed information about it in the **Invoice line details** view.</span></span>
5.  <span data-ttu-id="f2154-140">Na exibição **Detalhes de linha de fatura**, selecione **Distribuições** para exibir as distribuições de linha.</span><span class="sxs-lookup"><span data-stu-id="f2154-140">In the **Invoice line details** view, select **Distributions** to show the line distributions.</span></span> <span data-ttu-id="f2154-141">Aqui você pode visualizar a contabilidade para a linha de fatura.</span><span class="sxs-lookup"><span data-stu-id="f2154-141">Here, you can view the accounting for the invoice line.</span></span> <span data-ttu-id="f2154-142">As informações apresentadas incluem as dimensões financeiras e a conta principal.</span><span class="sxs-lookup"><span data-stu-id="f2154-142">The information that is shown includes the financial dimensions and the main account.</span></span>
6.  <span data-ttu-id="f2154-143">Na página **Detalhes da fatura**, selecione **Distribuições** para exibir todas as distribuições.</span><span class="sxs-lookup"><span data-stu-id="f2154-143">On the **Invoice details** page, select **Distributions** to show all distributions.</span></span> <span data-ttu-id="f2154-144">Aqui você pode visualizar a contabilidade para a fatura inteira.</span><span class="sxs-lookup"><span data-stu-id="f2154-144">Here, you can view the accounting for the whole invoice.</span></span> <span data-ttu-id="f2154-145">As informações apresentadas incluem as dimensões financeiras e as contas principais.</span><span class="sxs-lookup"><span data-stu-id="f2154-145">The information that is shown includes the financial dimensions and the main accounts.</span></span> 
7.  <span data-ttu-id="f2154-146">Selecione **Anexos** para exibir quaisquer notas ou arquivos anexados à fatura.</span><span class="sxs-lookup"><span data-stu-id="f2154-146">Select **Attachments** to view any notes or files that are attached to the invoice.</span></span>
8.  <span data-ttu-id="f2154-147">Na página **Detalhes da fatura**, selecione a ação de fluxo de trabalho apropriada para concluir o seu processo de revisão.</span><span class="sxs-lookup"><span data-stu-id="f2154-147">On the **Invoice details** page, select the appropriate workflow action to complete your review process.</span></span>
9.  <span data-ttu-id="f2154-148">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="f2154-148">Select **Done**.</span></span>