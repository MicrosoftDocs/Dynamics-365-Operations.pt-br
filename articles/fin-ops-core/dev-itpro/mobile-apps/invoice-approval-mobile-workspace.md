---
title: Espaço de trabalho móvel para aprovações de fatura
description: Este tópico fornece informações sobre a área de trabalho móvel de aprovações de fatura.
author: abruer
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 1a7aa1a03791b8ccb7050389097d1272f5930a49
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127560"
---
# <a name="invoice-approvals-mobile-workspace"></a><span data-ttu-id="15b44-103">Espaço de trabalho móvel para aprovações de fatura</span><span class="sxs-lookup"><span data-stu-id="15b44-103">Invoice approvals mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="15b44-104">Este tópico fornece informações sobre a área de trabalho móvel de **Aprovações de fatura**.</span><span class="sxs-lookup"><span data-stu-id="15b44-104">This topic provides information about the **Invoice approvals** mobile workspace.</span></span> <span data-ttu-id="15b44-105">Este espaço de trabalho fornece uma lista de faturas que foram atribuídas a você por meio do processo de fluxo de trabalho do cabeçalho da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="15b44-105">This workspace provides a list of invoices that have been assigned to you through the vendor invoice header workflow process.</span></span> 

<span data-ttu-id="15b44-106">Esse espaço de trabalho móvel deve ser usado com o aplicativo móvel Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="15b44-106">This mobile workspace is intended to be used with the Finance and Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="15b44-107">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="15b44-107">Overview</span></span>

<span data-ttu-id="15b44-108">O espaço de trabalho móvel **Aprovações de fatura** permite que auxiliares e gerentes de contas a pagar visualizem faturas que lhes foram atribuídas como parte do processo de fluxo de trabalho do cabeçalho da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="15b44-108">The **Invoice approvals** mobile workspace lets Accounts payable clerks and managers view invoices that have been assigned to them as part of the vendor invoice header workflow process.</span></span> <span data-ttu-id="15b44-109">Você pode visualizar informações de fatura e mesmo detalhes de linhas e de distribuição para ajudá-lo a tomar decisões acertadas de aprovação.</span><span class="sxs-lookup"><span data-stu-id="15b44-109">You can view the invoice information, and even the line and distribution details, to help you make informed approval decisions.</span></span> <span data-ttu-id="15b44-110">A partir do espaço de trabalho, você pode tomar medidas para mover a fatura no processo de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="15b44-110">From the workspace, you can take action to move the invoice through the workflow process.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="15b44-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="15b44-111">Prerequisites</span></span>

<span data-ttu-id="15b44-112">Antes de usar este espaço de trabalho móvel, os seguintes pré-requisitos devem ser atendidos.</span><span class="sxs-lookup"><span data-stu-id="15b44-112">Before you can use this mobile workspace, the following prerequisites must be met.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="15b44-113">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="15b44-113">Prerequisite</span></span></th>
<th><span data-ttu-id="15b44-114">Função</span><span class="sxs-lookup"><span data-stu-id="15b44-114">Role</span></span></th>
<th><span data-ttu-id="15b44-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="15b44-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="15b44-116">O Microsoft Dynamics 365 Finance deve ser implantado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="15b44-116">Microsoft Dynamics 365 Finance must be deployed in your organization.</span></span></td>
<td><span data-ttu-id="15b44-117">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="15b44-117">System administrator</span></span></td>
<td><span data-ttu-id="15b44-118">Consulte <a href="../deployment/deploy-demo-environment.md">Implantar um ambiente de demonstração</a>.</span><span class="sxs-lookup"><span data-stu-id="15b44-118">See <a href="../deployment/deploy-demo-environment.md">Deploy a demo environment</a>.</span></span>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="15b44-119">A área de trabalho móvel <strong>Aprovações de fatura</strong> deve ser publicada.</span><span class="sxs-lookup"><span data-stu-id="15b44-119">The <strong>Invoice approvals</strong> mobile workspace must be published.</span></span></td>
<td><span data-ttu-id="15b44-120">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="15b44-120">System administrator</span></span></td>
<td><span data-ttu-id="15b44-121">Consulte <a href="publish-mobile-workspace.md">Publicar um espaço de trabalho móvel</a>.</span><span class="sxs-lookup"><span data-stu-id="15b44-121">See <a href="publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="15b44-122">Baixa e instala o aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="15b44-122">Download and install the mobile app</span></span>

<span data-ttu-id="15b44-123">Baixe e instale o aplicativo móvel Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="15b44-123">Download and install the Finance and Operations mobile app:</span></span>

-   [<span data-ttu-id="15b44-124">Para telefones Android</span><span class="sxs-lookup"><span data-stu-id="15b44-124">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="15b44-125">Para iPhones</span><span class="sxs-lookup"><span data-stu-id="15b44-125">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="15b44-126">Entrar no aplicativo móvel</span><span class="sxs-lookup"><span data-stu-id="15b44-126">Sign in to the mobile app</span></span>

1.  <span data-ttu-id="15b44-127">Inicie o aplicativo móvel no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15b44-127">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="15b44-128">Insira a URL do Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="15b44-128">Enter your Microsoft Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="15b44-129">Na primeira vez que você iniciar a sessão, será solicitado o nome de usuário e a senha.</span><span class="sxs-lookup"><span data-stu-id="15b44-129">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="15b44-130">Insira suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="15b44-130">Enter your credentials.</span></span>
4.  <span data-ttu-id="15b44-131">Depois de entrar, serão exibidos os espaços de trabalho disponíveis da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="15b44-131">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="15b44-132">Observe que se o seu administrador de sistema publica um novo espaço de de trabalho depois, você terá que atualizar a lista dos espaços de trabalho móveis.</span><span class="sxs-lookup"><span data-stu-id="15b44-132">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

    <span data-ttu-id="15b44-133">[![Efetue pull para atualizar](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="15b44-133">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="approve-invoices-by-using-the-invoice-approvals-mobile-workspace"></a><span data-ttu-id="15b44-134">Aprovar faturas usando o espaço de trabalho móvel para aprovações de fatura</span><span class="sxs-lookup"><span data-stu-id="15b44-134">Approve invoices by using the Invoice approvals mobile workspace</span></span>
1.  <span data-ttu-id="15b44-135">No seu dispositivo móvel, selecione o espaço de trabalho **Aprovações de fatura**.</span><span class="sxs-lookup"><span data-stu-id="15b44-135">On your mobile device, select the **Invoice approvals** workspace.</span></span>
2.  <span data-ttu-id="15b44-136">Selecione a fatura que foi atribuída a você pelo processo de fluxo de trabalho do cabeçalho da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="15b44-136">Select the invoice that has been assigned to you by the vendor invoice header workflow process.</span></span>
3.  <span data-ttu-id="15b44-137">Na página **Detalhes da fatura**, reveja as informações de cabeçalho da fatura, como informações de fornecedor e data.</span><span class="sxs-lookup"><span data-stu-id="15b44-137">On the **Invoice details** page, review the invoice header information, such as the vendor and date information.</span></span>
4.  <span data-ttu-id="15b44-138">Selecione uma linha da fatura para exibir informações mais detalhadas sobre ela na exibição **Detalhes de linha de fatura**.</span><span class="sxs-lookup"><span data-stu-id="15b44-138">Select a line on the invoice to view more detailed information about it in the **Invoice line details** view.</span></span>
5.  <span data-ttu-id="15b44-139">Na exibição **Detalhes de linha de fatura**, selecione **Distribuições** para exibir as distribuições de linha.</span><span class="sxs-lookup"><span data-stu-id="15b44-139">In the **Invoice line details** view, select **Distributions** to show the line distributions.</span></span> <span data-ttu-id="15b44-140">Aqui você pode visualizar a contabilidade para a linha de fatura.</span><span class="sxs-lookup"><span data-stu-id="15b44-140">Here, you can view the accounting for the invoice line.</span></span> <span data-ttu-id="15b44-141">As informações apresentadas incluem as dimensões financeiras e a conta principal.</span><span class="sxs-lookup"><span data-stu-id="15b44-141">The information that is shown includes the financial dimensions and the main account.</span></span>
6.  <span data-ttu-id="15b44-142">Na página **Detalhes da fatura**, selecione **Distribuições** para exibir todas as distribuições.</span><span class="sxs-lookup"><span data-stu-id="15b44-142">On the **Invoice details** page, select **Distributions** to show all distributions.</span></span> <span data-ttu-id="15b44-143">Aqui você pode visualizar a contabilidade para a fatura inteira.</span><span class="sxs-lookup"><span data-stu-id="15b44-143">Here, you can view the accounting for the whole invoice.</span></span> <span data-ttu-id="15b44-144">As informações apresentadas incluem as dimensões financeiras e as contas principais.</span><span class="sxs-lookup"><span data-stu-id="15b44-144">The information that is shown includes the financial dimensions and the main accounts.</span></span> 
7.  <span data-ttu-id="15b44-145">Selecione **Anexos** para exibir quaisquer notas ou arquivos anexados à fatura.</span><span class="sxs-lookup"><span data-stu-id="15b44-145">Select **Attachments** to view any notes or files that are attached to the invoice.</span></span>
8.  <span data-ttu-id="15b44-146">Na página **Detalhes da fatura**, selecione a ação de fluxo de trabalho apropriada para concluir o seu processo de revisão.</span><span class="sxs-lookup"><span data-stu-id="15b44-146">On the **Invoice details** page, select the appropriate workflow action to complete your review process.</span></span>
9.  <span data-ttu-id="15b44-147">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="15b44-147">Select **Done**.</span></span>
