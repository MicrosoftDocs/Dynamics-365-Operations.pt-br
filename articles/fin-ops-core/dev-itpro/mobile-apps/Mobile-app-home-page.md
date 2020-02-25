---
title: Home page de Aplicativo móvel
description: Este tópico descreve o aplicativo móvel Finance and Operations (Dynamics 365) e fornece links para recursos que podem ajudá-lo a implementá-lo em sua organização.
author: sericks007
manager: AnnBe
ms.date: 01/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 272853
ms.assetid: c99f818f-27b3-4e45-92b4-74272dad0e17
ms.search.region: Global
ms.author: sericks
ms.dyn365.ops.version: Platform update 4
ms.search.validFrom: 2017-02-28
ms.openlocfilehash: 012b51b66c831a66a54c7c868735e310f05eb8c1
ms.sourcegitcommit: f939bc6292840e29bc0f498efc8f4641dfe8f994
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2020
ms.locfileid: "2975188"
---
# <a name="mobile-app-home-page"></a><span data-ttu-id="bd10c-103">Home page de Aplicativo móvel</span><span class="sxs-lookup"><span data-stu-id="bd10c-103">Mobile app home page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bd10c-104">Este tópico descreve o aplicativo móvel **Finance and Operations (Dynamics 365)** e fornece links para recursos que podem ajudá-lo a implementá-lo em sua organização.</span><span class="sxs-lookup"><span data-stu-id="bd10c-104">This topic describes the **Finance and Operations (Dynamics 365)** mobile app and provides links to resources that can help you implement it in your organization.</span></span>

<a name="overview"></a><span data-ttu-id="bd10c-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="bd10c-105">Overview</span></span>
--------

<span data-ttu-id="bd10c-106">O aplicativo móvel permite que sua organização disponibilize os processos empresariais nos dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="bd10c-106">The mobile app enables your organization to make its business processes available on mobile devices.</span></span> <span data-ttu-id="bd10c-107">Depois que seu administrador de TI habilitar os espaços de trabalho de sua organização, os usuários podem entrar no aplicativo e começar imediatamente a executar os processos comerciais de seus dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="bd10c-107">After your IT admin enables the mobile workspaces for your organization, users can sign in to the app and immediately begin to run business processes from their mobile devices.</span></span> <span data-ttu-id="bd10c-108">O aplicativo móvel inclui os seguintes recursos que podem ajudar a aumentar a produtividade:</span><span class="sxs-lookup"><span data-stu-id="bd10c-108">The mobile app includes the following features that can help increase productivity:</span></span>

- <span data-ttu-id="bd10c-109">Os usuários podem exibir, editar e atuar nos dados corporativos, mesmo se eles tiverem conectividade de rede intermitente ou seus dispositivos móveis estiverem completamente offline.</span><span class="sxs-lookup"><span data-stu-id="bd10c-109">Users can view, edit, and act on business data, even if they have intermittent network connectivity or their mobile devices are completely offline.</span></span> <span data-ttu-id="bd10c-110">Quando um dispositivo restabelece uma conexão de rede, as operações de dados offline são sincronizadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="bd10c-110">When a device reestablishes a network connection, offline data operations are automatically synchronized.</span></span>
- <span data-ttu-id="bd10c-111">Os administradores de TI ou desenvolvedores podem criar e publicar espaços de trabalho móveis que foram personalizados para sua organização.</span><span class="sxs-lookup"><span data-stu-id="bd10c-111">IT admins or developers can build and publish mobile workspaces that have been tailored to their organization.</span></span> <span data-ttu-id="bd10c-112">O aplicativo usa seu código de ativos existente.</span><span class="sxs-lookup"><span data-stu-id="bd10c-112">The app uses your existing code assets.</span></span> <span data-ttu-id="bd10c-113">Portanto, não é necessário reimplementar os procedimentos de validação, lógica de negócio ou configuração de segurança.</span><span class="sxs-lookup"><span data-stu-id="bd10c-113">Therefore, you don't have to re-implement your validation procedures, business logic, or security configuration.</span></span>
- <span data-ttu-id="bd10c-114">Os desenvolvedores ou administradores de TI podem facilmente criar espaços de trabalho móveis usando o criador de espaço de trabalho de apontar e clicar que é incluído no cliente da Web.</span><span class="sxs-lookup"><span data-stu-id="bd10c-114">IT admins or developers can easily design mobile workspaces by using the point-and-click workspace designer that is included with the web client.</span></span>
- <span data-ttu-id="bd10c-115">Os administradores de TI ou desenvolvedores podem, como opção, otimizar os recursos offline dos espaços de trabalho, usando a estrutura de extensibilidade da lógica de negócios.</span><span class="sxs-lookup"><span data-stu-id="bd10c-115">IT admins or developers can optionally optimize the offline capabilities of workspaces by using the Business logic extensibility framework.</span></span> <span data-ttu-id="bd10c-116">Como os dados continuam sendo processados quando um dispositivo está offline, seu cenário móvel permanece avançado e fluido, mesmo se os dispositivos não tiverem conectividade de rede constante.</span><span class="sxs-lookup"><span data-stu-id="bd10c-116">Because data continues to be processed while a device is offline, your mobile scenarios remain rich and fluid, even if devices don't have constant network connectivity.</span></span>

## <a name="elements-of-the-mobile-app"></a><span data-ttu-id="bd10c-117">Elementos do aplicativo móvel</span><span class="sxs-lookup"><span data-stu-id="bd10c-117">Elements of the mobile app</span></span>
<span data-ttu-id="bd10c-118">A navegação no aplicativo móvel consiste em quatro conceitos básicos: o painel, os espaços de trabalho, as páginas e as ações.</span><span class="sxs-lookup"><span data-stu-id="bd10c-118">Navigation in the mobile app consists of four basic concepts: the dashboard, workspaces, pages, and actions.</span></span> 

<span data-ttu-id="bd10c-119">[![Conceitos de navegação no aplicativo móvel](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)</span><span class="sxs-lookup"><span data-stu-id="bd10c-119">[![Navigation concepts in the mobile app](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)</span></span>

1. <span data-ttu-id="bd10c-120">Quando você inicia o aplicativo, você vai para o **painel**.</span><span class="sxs-lookup"><span data-stu-id="bd10c-120">When you start the app, you go to the **dashboard**.</span></span>
2. <span data-ttu-id="bd10c-121">No painel, você pode ver uma lista de **espaços de trabalho** que foi publicada.</span><span class="sxs-lookup"><span data-stu-id="bd10c-121">On the dashboard, you can see a list of **workspaces** that have been published.</span></span>
3. <span data-ttu-id="bd10c-122">Em cada espaço de trabalho, você pode ver uma lista de **páginas** disponíveis para esse espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="bd10c-122">In each workspace, you can see a list of **pages** that are available for that workspace.</span></span>
4. <span data-ttu-id="bd10c-123">Estando em uma página, você pode executar várias ações.</span><span class="sxs-lookup"><span data-stu-id="bd10c-123">After you're on a page, you can perform several actions.</span></span> <span data-ttu-id="bd10c-124">Eis alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="bd10c-124">Here are some examples:</span></span>

    - <span data-ttu-id="bd10c-125">Exibir dados detalhados.</span><span class="sxs-lookup"><span data-stu-id="bd10c-125">View detailed data.</span></span>
    - <span data-ttu-id="bd10c-126">Navegue em outras páginas para obter dados relacionados, como detalhes da entidade ou linhas.</span><span class="sxs-lookup"><span data-stu-id="bd10c-126">Navigate to other pages for related data, such as entity details or lines.</span></span>
    - <span data-ttu-id="bd10c-127">Consultar uma lista de **ações** disponíveis para essa página.</span><span class="sxs-lookup"><span data-stu-id="bd10c-127">See a list of **actions** that are available for that page.</span></span> <span data-ttu-id="bd10c-128">As ações permitem que você crie ou edite os dados existentes.</span><span class="sxs-lookup"><span data-stu-id="bd10c-128">Actions let you create or edit existing data.</span></span>

## <a name="implementation-process"></a><span data-ttu-id="bd10c-129">Processo de implementação</span><span class="sxs-lookup"><span data-stu-id="bd10c-129">Implementation process</span></span>
<span data-ttu-id="bd10c-130">A ilustração a seguir mostra o processo de implementação dos espaços de trabalho móveis fornecidos pela Microsoft e dos espaços de trabalho móveis personalizados.</span><span class="sxs-lookup"><span data-stu-id="bd10c-130">The following illustration shows the process for implementing both mobile workspaces that are provided by Microsoft and custom mobile workspaces.</span></span> 

<span data-ttu-id="bd10c-131">[![Processo de implementação de aplicativos móveis](./media/Mobile-implementation-process-5.png)](./media/Mobile-implementation-process-5.png)</span><span class="sxs-lookup"><span data-stu-id="bd10c-131">[![Mobile apps implementation process](./media/Mobile-implementation-process-5.png)](./media/Mobile-implementation-process-5.png)</span></span>

<span data-ttu-id="bd10c-132">A tabela a seguir inclui links para recursos que podem ajudá-lo a implementar os espaços de trabalho móveis fornecidos pela Microsoft e os espaços de trabalho móveis personalizados.</span><span class="sxs-lookup"><span data-stu-id="bd10c-132">The following table includes links to resources that can help you implement both mobile workspaces that are provided by Microsoft and custom mobile workspaces.</span></span> <span data-ttu-id="bd10c-133">Os números na primeira coluna correspondem às etapas numeradas na ilustração anterior.</span><span class="sxs-lookup"><span data-stu-id="bd10c-133">The numbers in the first column correspond to the numbered steps in the previous illustration.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd10c-134">Etapa</span><span class="sxs-lookup"><span data-stu-id="bd10c-134">Step</span></span></th>
<th><span data-ttu-id="bd10c-135">Função</span><span class="sxs-lookup"><span data-stu-id="bd10c-135">Role</span></span></th>
<th><span data-ttu-id="bd10c-136">Ação</span><span class="sxs-lookup"><span data-stu-id="bd10c-136">Action</span></span></th>
<th><span data-ttu-id="bd10c-137">Recursos para ajudá-lo a concluir a ação</span><span class="sxs-lookup"><span data-stu-id="bd10c-137">Resources to help you complete the action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="bd10c-138">1</span><span class="sxs-lookup"><span data-stu-id="bd10c-138">1</span></span></td>
<td><span data-ttu-id="bd10c-139">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="bd10c-139">System administrator</span></span></td>
<td><span data-ttu-id="bd10c-140">Implementar o aplicativo Finance and Operations na sua organização.</span><span class="sxs-lookup"><span data-stu-id="bd10c-140">Implement the Finance and Operations app in your organization.</span></span></td>
<td><ul><li><span data-ttu-id="bd10c-141">Caso ainda não tenha implantado uma versão do Microsoft Dynamics 365, consulte <a href="../deployment/deploy-demo-environment.md">Implantar um ambiente de demonstração</a>.</span><span class="sxs-lookup"><span data-stu-id="bd10c-141">If you haven&#39;t yet deployed a version of Microsoft Dynamics 365, see <a href="../deployment/deploy-demo-environment.md">Deploy a demo environment</a>.</span></span></li><li><span data-ttu-id="bd10c-142">Para ver uma lista dos espaços de trabalho móveis que podem ser usados, consulte <a href="mobile-workspaces-released.md">Espaços de trabalho móveis lançados recentemente</a>.</span><span class="sxs-lookup"><span data-stu-id="bd10c-142">To see a list of mobile workspaces that can be used, see <a href="mobile-workspaces-released.md">Mobile workspaces recently released</a>.</span></span></li></ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bd10c-143">2</span><span class="sxs-lookup"><span data-stu-id="bd10c-143">2</span></span></td>
<td><span data-ttu-id="bd10c-144">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="bd10c-144">System administrator</span></span></td>
<td><span data-ttu-id="bd10c-145"><strong>Se estiver usando o Microsoft Dynamics 365 for Operations versão 1611:</strong> Baixe e instale os KBs que habilitam os espaços de trabalho móveis que são fornecidos pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bd10c-145"><strong>If you&#39;re using Microsoft Dynamics 365 for Operations version 1611:</strong> Download and install KBs that enable the mobile workspaces that are provided by Microsoft.</span></span></td>
<td><span data-ttu-id="bd10c-146">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="bd10c-146">See the following topics for more information:</span></span>
<ul>

<li><span data-ttu-id="bd10c-147"><a href="../../../finance/cost-accounting/cost-controlling-mobile-workspace.md">Espaços de trabalho móveis de controle de custo</a></span><span class="sxs-lookup"><span data-stu-id="bd10c-147"><a href="../../../finance/cost-accounting/cost-controlling-mobile-workspace.md">Cost controlling mobile workspaces</a></span></span></li>
<li><span data-ttu-id="bd10c-148"><a href="../../../supply-chain/inventory/inventory-on-hand-mobile-workspace.md">Espaço de trabalho móvel de estoque disponível</a></span><span class="sxs-lookup"><span data-stu-id="bd10c-148"><a href="../../../supply-chain/inventory/inventory-on-hand-mobile-workspace.md">Inventory on-hand mobile workspace</a></span></span></li>
<li><span data-ttu-id="bd10c-149"><a href="../../../supply-chain/sales-marketing/sales-orders-mobile-workspace.md">Espaços de trabalho móveis das ordens de venda</a></span><span class="sxs-lookup"><span data-stu-id="bd10c-149"><a href="../../../supply-chain/sales-marketing/sales-orders-mobile-workspace.md">Sales orders mobile workspaces</a></span></span></li>
<li><span data-ttu-id="bd10c-150"><a href="../../../supply-chain/procurement/vendor-collaboration-mobile-workspace.md">Espaço de trabalho móvel de colaboração de fornecedores</a></span><span class="sxs-lookup"><span data-stu-id="bd10c-150"><a href="../../../supply-chain/procurement/vendor-collaboration-mobile-workspace.md">Vendor collaboration mobile workspace</a></span></span></li>
<li><span data-ttu-id="bd10c-151"><a href="../../../finance/project-management/project-time-entry-mobile-workspace.md">Espaço de trabalho móvel de entrada de tempo do projeto</a></span><span class="sxs-lookup"><span data-stu-id="bd10c-151"><a href="../../../finance/project-management/project-time-entry-mobile-workspace.md">Project time entry mobile workspace</a></span></span></li>
<li><span data-ttu-id="bd10c-152"><a href="../../../finance/expense-management/expense-management-mobile-workspace.md">Espaço de trabalho móvel de gerenciamento de despesas</a></span><span class="sxs-lookup"><span data-stu-id="bd10c-152"><a href="../../../finance/expense-management/expense-management-mobile-workspace.md">Expense management mobile workspace</a></span></span></li>

</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bd10c-153">3</span><span class="sxs-lookup"><span data-stu-id="bd10c-153">3</span></span></td>
<td><span data-ttu-id="bd10c-154">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="bd10c-154">System administrator</span></span></td>
<td><span data-ttu-id="bd10c-155">Publique os espaços de trabalho móveis fornecidos pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bd10c-155">Publish the mobile workspaces that are provided by Microsoft.</span></span></td>
<td><span data-ttu-id="bd10c-156"><a href="publish-mobile-workspace.md">Publicar um espaço de trabalho móvel</a>
</span><span class="sxs-lookup"><span data-stu-id="bd10c-156"><a href="publish-mobile-workspace.md">Publish a mobile workspace</a>
</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bd10c-157">4</span><span class="sxs-lookup"><span data-stu-id="bd10c-157">4</span></span></td>
<td><span data-ttu-id="bd10c-158">Desenvolvedor ou fornecedor de software independente (ISV)</span><span class="sxs-lookup"><span data-stu-id="bd10c-158">Developer or independent software vendor (ISV)</span></span></td>
<td><span data-ttu-id="bd10c-159">Use a plataforma móvel para criar espaços de trabalho móveis personalizados.</span><span class="sxs-lookup"><span data-stu-id="bd10c-159">Use the mobile platform to create custom mobile workspaces.</span></span></td>
<td><span data-ttu-id="bd10c-160"><a href="platform/mobile-platform-home-page.md">Plataforma móvel</a></span><span class="sxs-lookup"><span data-stu-id="bd10c-160"><a href="platform/mobile-platform-home-page.md">Mobile platform</a></span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bd10c-161">5</span><span class="sxs-lookup"><span data-stu-id="bd10c-161">5</span></span></td>
<td><span data-ttu-id="bd10c-162">ISV</span><span class="sxs-lookup"><span data-stu-id="bd10c-162">ISV</span></span></td>
<td><span data-ttu-id="bd10c-163">Cria um pacote implantável que contém os espaços de trabalho móveis personalizados e carrega o pacote no Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="bd10c-163">Create a deployable package that contains custom mobile workspaces, and upload the package to Microsoft Dynamics Lifecycle Services (LCS).</span></span></td>
<td><span data-ttu-id="bd10c-164"><a href="../deployment/create-apply-deployable-package.md">Criar um pacote implantável</a></span><span class="sxs-lookup"><span data-stu-id="bd10c-164"><a href="../deployment/create-apply-deployable-package.md">Create a deployable package</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bd10c-165">6</span><span class="sxs-lookup"><span data-stu-id="bd10c-165">6</span></span></td>
<td><span data-ttu-id="bd10c-166">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="bd10c-166">System administrator</span></span></td>
<td><span data-ttu-id="bd10c-167">Aplica o pacote implantável que contém os espaços de trabalho personalizados que são fornecidos pelo ISV (Fornecedor Independente de Software).</span><span class="sxs-lookup"><span data-stu-id="bd10c-167">Apply the deployable package that contains the custom workspaces that are provided by the independent software vendor (ISV).</span></span></td>
<td><span data-ttu-id="bd10c-168"><a href="../deployment/apply-deployable-package-system.md">Aplicar um pacote implantável</a></span><span class="sxs-lookup"><span data-stu-id="bd10c-168"><a href="../deployment/apply-deployable-package-system.md">Apply a deployable package</a></span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bd10c-169">7</span><span class="sxs-lookup"><span data-stu-id="bd10c-169">7</span></span></td>
<td><span data-ttu-id="bd10c-170">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="bd10c-170">System administrator</span></span></td>
<td><span data-ttu-id="bd10c-171">Publica os espaços de trabalho móveis personalizados que são fornecidos pelo ISV.</span><span class="sxs-lookup"><span data-stu-id="bd10c-171">Publish the custom mobile workspaces that are provided by the ISV.</span></span></td>
<td><span data-ttu-id="bd10c-172"><a href="publish-mobile-workspace.md">Publicar um espaço de trabalho móvel</a></span><span class="sxs-lookup"><span data-stu-id="bd10c-172"><a href="publish-mobile-workspace.md">Publish a mobile workspace</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bd10c-173">8</span><span class="sxs-lookup"><span data-stu-id="bd10c-173">8</span></span></td>
<td><span data-ttu-id="bd10c-174">Usuário</span><span class="sxs-lookup"><span data-stu-id="bd10c-174">User</span></span></td>
<td><span data-ttu-id="bd10c-175">Baixe e instale o aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="bd10c-175">Download and install the mobile app.</span></span></td>
<td><span data-ttu-id="bd10c-176">
<a href="https://go.microsoft.com/fwlink/?linkid=850662">Aplicativo Finance and Operations para Android</a></span><span class="sxs-lookup"><span data-stu-id="bd10c-176">
<a href="https://go.microsoft.com/fwlink/?linkid=850662">Finance and Operations app for Android</a></span></span><BR/><span data-ttu-id="bd10c-177">
<a href="https://go.microsoft.com/fwlink/?linkid=850663">Aplicativo Finance and Operations para iOS</a></span><span class="sxs-lookup"><span data-stu-id="bd10c-177">
<a href="https://go.microsoft.com/fwlink/?linkid=850663">Finance and Operations app for iOS</a></span></span><BR/>
<span data-ttu-id="bd10c-178">(Windows Phone não tem suporte)</span><span class="sxs-lookup"><span data-stu-id="bd10c-178">(Windows Phone unsupported)</span></span>
</td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bd10c-179">9</span><span class="sxs-lookup"><span data-stu-id="bd10c-179">9</span></span></td>
<td><span data-ttu-id="bd10c-180">Usuário</span><span class="sxs-lookup"><span data-stu-id="bd10c-180">User</span></span></td>
<td><span data-ttu-id="bd10c-181">Entrar e usar o aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="bd10c-181">Sign in, and use the mobile app.</span></span> <span data-ttu-id="bd10c-182">O aplicativo inclui os espaços de trabalho móveis que foram publicados pelo administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="bd10c-182">The app includes the mobile workspaces that have been published by the system administrator.</span></span></td>
<td><span data-ttu-id="bd10c-183">Para ver uma lista dos espaços de trabalho móveis que são fornecidos pela Microsoft, consulte <a href="mobile-workspaces-released.md">Espaços de trabalho móveis lançados recentemente</a>.</span><span class="sxs-lookup"><span data-stu-id="bd10c-183">To see a list of mobile workspaces that are provided by Microsoft, see <a href="mobile-workspaces-released.md">Mobile workspaces recently released</a>.</span></span>
</td>
</tr>
</tbody>
</table>

## <a name="troubleshooting"></a><span data-ttu-id="bd10c-184">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="bd10c-184">Troubleshooting</span></span>
[<span data-ttu-id="bd10c-185">Recursos da plataforma móvel</span><span class="sxs-lookup"><span data-stu-id="bd10c-185">Mobile platform resources</span></span>](platform/mobile-platform-home-page.md#troubleshooting-the-app)
