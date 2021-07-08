---
title: Introdução à Contabilidade de estoque global
description: Este tópico descreve como começar com a Contabilidade de estoque global.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 59f9db309312bbbc88b4fa47c12c4c02f09e7c6d
ms.sourcegitcommit: cbbb35c71ab4ff1ae08fa4f7cc97019b207246be
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301689"
---
# <a name="get-started-with-global-inventory-accounting"></a><span data-ttu-id="f63ea-103">Introdução à Contabilidade de estoque global</span><span class="sxs-lookup"><span data-stu-id="f63ea-103">Get started with Global Inventory Accounting</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="f63ea-104">A Contabilidade de estoque global de custos permite realizar múltiplas contabilidades de inventário nos razões da Contabilidade de estoque global.</span><span class="sxs-lookup"><span data-stu-id="f63ea-104">Global Inventory Accounting lets you do multiple inventory accountings in the Global Inventory Accounting ledgers that you've set up.</span></span> <span data-ttu-id="f63ea-105">É necessário associar cada razão da Contabilidade de estoque global a uma *convenção*.</span><span class="sxs-lookup"><span data-stu-id="f63ea-105">You must associate each Global Inventory Accounting ledger with a *convention*.</span></span> <span data-ttu-id="f63ea-106">Uma convenção é uma coleção dos seguintes tipos de políticas de contabilidade:</span><span class="sxs-lookup"><span data-stu-id="f63ea-106">A convention is a collection of the following types of accounting policies:</span></span>

- <span data-ttu-id="f63ea-107">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="f63ea-107">Cost object</span></span>
- <span data-ttu-id="f63ea-108">Base de medida de entrada</span><span class="sxs-lookup"><span data-stu-id="f63ea-108">Input measurement basis</span></span>
- <span data-ttu-id="f63ea-109">Suposição de fluxo de custos</span><span class="sxs-lookup"><span data-stu-id="f63ea-109">Cost flow assumption</span></span>
- <span data-ttu-id="f63ea-110">Elemento de custo</span><span class="sxs-lookup"><span data-stu-id="f63ea-110">Cost element</span></span>

> [!NOTE]
> <span data-ttu-id="f63ea-111">Mesmo depois de ativar a Contabilidade de estoque global, ainda é possível realizar a contabilidade de estoque no Microsoft Dynamics 365 Supply Chain Management, como de costume.</span><span class="sxs-lookup"><span data-stu-id="f63ea-111">Even after you turn on Global Inventory Accounting, you can still do inventory accounting in Microsoft Dynamics 365 Supply Chain Management in the usual way.</span></span>

<span data-ttu-id="f63ea-112">A Contabilidade de estoque global é um suplemento.</span><span class="sxs-lookup"><span data-stu-id="f63ea-112">Global Inventory Accounting is an add-in.</span></span> <span data-ttu-id="f63ea-113">Para disponibilizar os recursos, é necessário instalá-lo a partir do Lifecycle Services (LCS) Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="f63ea-113">To make its features available, you must install it from Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="f63ea-114">É possível optar por avaliá-lo em um ambiente de teste antes de ativá-lo para ambientes de produção.</span><span class="sxs-lookup"><span data-stu-id="f63ea-114">You can choose to evaluate it in a test environment before you turn it on for production environments.</span></span>

<span data-ttu-id="f63ea-115">No momento, a Contabilidade de estoque global não permite todos os recursos de gerenciamento de custos que são incorporados ao Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f63ea-115">Global Inventory Accounting doesn't currently support all the cost management features that are built into Supply Chain Management.</span></span> <span data-ttu-id="f63ea-116">Portanto, é importante que você avalie se o conjunto de recursos disponível no momento atenderá aos seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="f63ea-116">Therefore, it's important that you evaluate whether the set of features that is currently available will meet your requirements.</span></span>

## <a name="how-to-get-the-global-inventory-accounting-public-preview"></a><a name="sign-up"></a><span data-ttu-id="f63ea-117">Como obter a versão preliminar pública da Contabilidade de estoque global</span><span class="sxs-lookup"><span data-stu-id="f63ea-117">How to get the Global Inventory Accounting public preview</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f63ea-118">Para usar a Contabilidade de estoque global, você deve ter um ambiente de alta disponibilidade habilitado para LCS (não um ambiente OneBox).</span><span class="sxs-lookup"><span data-stu-id="f63ea-118">To use Global Inventory Accounting, you must have an LCS-enabled high-availability environment (not a OneBox environment).</span></span> <span data-ttu-id="f63ea-119">Além disso, você deve estar executando a versão 10.0.19 ou posterior do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f63ea-119">Additionally, you must be running Supply Chain Management version 10.0.19 or later.</span></span>

<span data-ttu-id="f63ea-120">Para se inscrever na versão preliminar pública da Contabilidade de estoque global, envie seu ID de ambiente LCS por email para a [Equipe da Contabilidade de estoque global](mailto:GlobalInventoryAccounting@service.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="f63ea-120">To sign up for the Global Inventory Accounting public preview, send your LCS environment ID by email to the [Global Inventory Accounting team](mailto:GlobalInventoryAccounting@service.microsoft.com).</span></span> <span data-ttu-id="f63ea-121">Depois que você for aprovado para o programa, a equipe enviará um email de acompanhamento que contém uma chave beta da Contabilidade de estoque global e seus pontos de extremidade de serviço.</span><span class="sxs-lookup"><span data-stu-id="f63ea-121">After you're approved for the program, the team will send you a follow-up email that contains a Global Inventory Accounting beta key and your service endpoints.</span></span> <span data-ttu-id="f63ea-122">Depois de receber a chave beta, você pode [instalar o suplemento](#install).</span><span class="sxs-lookup"><span data-stu-id="f63ea-122">After you receive the beta key, you can [install the add-in](#install).</span></span>

## <a name="licensing"></a><span data-ttu-id="f63ea-123">Licenciamento</span><span class="sxs-lookup"><span data-stu-id="f63ea-123">Licensing</span></span>

<span data-ttu-id="f63ea-124">A Contabilidade de estoque global é licenciada com os recursos padrão de contabilidade de estoque que estão disponíveis para o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f63ea-124">Global Inventory Accounting is licensed together with the standard features of inventory accounting that are available for Supply Chain Management.</span></span> <span data-ttu-id="f63ea-125">Não é necessário comprar uma licença adicional para usar a Contabilidade de Estoque Global.</span><span class="sxs-lookup"><span data-stu-id="f63ea-125">You don't have to purchase an additional license to use Global Inventory Accounting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f63ea-126">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f63ea-126">Prerequisites</span></span>

### <a name="set-up-microsoft-power-platform-integration"></a><span data-ttu-id="f63ea-127">Configurar integração do Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="f63ea-127">Set up Microsoft Power Platform integration</span></span>

<span data-ttu-id="f63ea-128">Antes de habilitar a funcionalidade de suplemento, você deve se integrar ao Microsoft Power Platform seguindo essas etapas.</span><span class="sxs-lookup"><span data-stu-id="f63ea-128">Before you can enable add-in functionality, you must integrate with Microsoft Power Platform by following these steps.</span></span>

1. <span data-ttu-id="f63ea-129">Abra o ambiente LCS ao qual deseja adicionar o serviço.</span><span class="sxs-lookup"><span data-stu-id="f63ea-129">Open the LCS environment where you want to add the service.</span></span>
1. <span data-ttu-id="f63ea-130">Vá para **Detalhes completos**.</span><span class="sxs-lookup"><span data-stu-id="f63ea-130">Go to **Full details**.</span></span>
1. <span data-ttu-id="f63ea-131">Na seção **Integração do Power Platform**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="f63ea-131">In the **Power Platform Integration** section, select **Setup**.</span></span>
1. <span data-ttu-id="f63ea-132">Na caixa de diálogo **Configuração do ambiente do Power Platform**, marque a caixa de seleção e selecione **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="f63ea-132">In the **Power platform environment setup** dialog box, select the checkbox, and then select **Setup**.</span></span> <span data-ttu-id="f63ea-133">Normalmente, a configuração leva entre 60 e 90 minutos.</span><span class="sxs-lookup"><span data-stu-id="f63ea-133">Typically, setup takes between 60 and 90 minutes.</span></span>
1. <span data-ttu-id="f63ea-134">Após a configuração do ambiente do Microsoft Power Platform ser concluída, a página mostra o nome do seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="f63ea-134">After setup of the Microsoft Power Platform environment is completed, the page shows the name of your environment.</span></span> <span data-ttu-id="f63ea-135">Além disso, a seção **Integração do Power Platform** mostra a afirmação: "A configuração de ambiente do Power Platform foi concluída."</span><span class="sxs-lookup"><span data-stu-id="f63ea-135">Additionally, the **Power Platform Integration** section shows the statement, "Power Platform environment setup is complete."</span></span> <span data-ttu-id="f63ea-136">A Contabilidade de estoque global não requer um aplicativo de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="f63ea-136">Global Inventory Accounting doesn't require a dual-write application.</span></span>

<span data-ttu-id="f63ea-137">Para obter mais informações, consulte [Configuração após a implantação do ambiente](../../fin-ops-core/dev-itpro/power-platform/overview.md#set-up-after-environment-deployment).</span><span class="sxs-lookup"><span data-stu-id="f63ea-137">For more information, see [Set up after environment deployment](../../fin-ops-core/dev-itpro/power-platform/overview.md#set-up-after-environment-deployment).</span></span>

### <a name="set-up-dataverse"></a><span data-ttu-id="f63ea-138">Configurar o Dataverse</span><span class="sxs-lookup"><span data-stu-id="f63ea-138">Set up Dataverse</span></span>

<span data-ttu-id="f63ea-139">Antes de configurar o Dataverse, adicione os princípios do Contabilidade de estoque global ao seu locatário seguindo essas etapas.</span><span class="sxs-lookup"><span data-stu-id="f63ea-139">Before you set up Dataverse, add the Global Inventory Accounting service principles to your tenant by following these steps.</span></span>

1. <span data-ttu-id="f63ea-140">Instale o módulo Azure AD para Windows PowerShell v2, conforme descrito em [Instalar o Azure Active Directory PowerShell para o Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="f63ea-140">Install Azure AD Module for Windows PowerShell v2 as described in [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>
1. <span data-ttu-id="f63ea-141">Execute o comando do PowerShell a seguir.</span><span class="sxs-lookup"><span data-stu-id="f63ea-141">Run the following PowerShell command.</span></span>

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)

    New-AzureADServicePrincipal -AppId "7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9" -DisplayName "d365-scm-costaccountingservice"

    New-AzureADServicePrincipal -AppId "5f58fc56-0202-49a8-ac9e-0946b049718b" -DisplayName "d365-scm-operationdataservice"
    ```

<span data-ttu-id="f63ea-142">Em seguida, crie usuários de aplicativos para a Contabilidade de estoque global do Dataverse seguindo essas etapas.</span><span class="sxs-lookup"><span data-stu-id="f63ea-142">Next, create application users for Global Inventory Accounting in Dataverse by following these steps.</span></span>

1. <span data-ttu-id="f63ea-143">Abra a URL do ambiente do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="f63ea-143">Open the URL of your Dataverse environment.</span></span>
1. <span data-ttu-id="f63ea-144">Acesse **Configuração Avançada \> Sistema \> Segurança \> Usuários** e crie um usuário de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f63ea-144">Go to **Advanced Setting \> System \> Security \> Users**, and create an application user.</span></span> <span data-ttu-id="f63ea-145">Use o campo **Visualizar** para alterar a exibição de página para *Usuários do Aplicativo*.</span><span class="sxs-lookup"><span data-stu-id="f63ea-145">Use the **View** field to change the page view to *Application users*.</span></span>
1. <span data-ttu-id="f63ea-146">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="f63ea-146">Select **New**.</span></span>
1. <span data-ttu-id="f63ea-147">Defina o campo **ID do Aplicativo** como *7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9*.</span><span class="sxs-lookup"><span data-stu-id="f63ea-147">Set the **Application ID** field to *7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9*.</span></span>
1. <span data-ttu-id="f63ea-148">Selecione **Atribuir Função** e, depois, selecione *Administrador do Sistema*.</span><span class="sxs-lookup"><span data-stu-id="f63ea-148">Select **Assign Role**, and then select *System Administrator*.</span></span> <span data-ttu-id="f63ea-149">Se houver uma função denominada *Usuário do Common Data Service*, selecione-a.</span><span class="sxs-lookup"><span data-stu-id="f63ea-149">If there is a role that is named *Common Data Service User*, select it too.</span></span>
1. <span data-ttu-id="f63ea-150">Repita as etapas anteriores, mas defina o campo **ID do aplicativo** para *5f58fc56-0202-49a8-ac9e-0946b049718b*.</span><span class="sxs-lookup"><span data-stu-id="f63ea-150">Repeat the preceding steps, but set the **Application ID** field to *5f58fc56-0202-49a8-ac9e-0946b049718b*.</span></span>

<span data-ttu-id="f63ea-151">Para obter mais informações, consulte [Criar um usuário de aplicativo](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span><span class="sxs-lookup"><span data-stu-id="f63ea-151">For more information, see [Create an application user](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span></span>

<span data-ttu-id="f63ea-152">Se o idioma padrão da sua instalação do Dataverse não for inglês, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f63ea-152">If the default language of your Dataverse installation isn't English, follow these steps.</span></span>

1. <span data-ttu-id="f63ea-153">Acesse **Configurações avançadas \> Administração \> Idiomas**.</span><span class="sxs-lookup"><span data-stu-id="f63ea-153">Go to **Advanced Setting \> Administration \> Languages**.</span></span>
1. <span data-ttu-id="f63ea-154">Selecione *Inglês* (*LanguageCode = 1033*) e selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="f63ea-154">Select *English* (*LanguageCode=1033*), and then select **Apply**.</span></span>

## <a name="install-the-add-in"></a><a name="install"></a><span data-ttu-id="f63ea-155">Instalar o suplemento</span><span class="sxs-lookup"><span data-stu-id="f63ea-155">Install the add-in</span></span>

<span data-ttu-id="f63ea-156">Siga estas etapas para instalar o suplemento para que você possa usar a Contabilidade de estoque global.</span><span class="sxs-lookup"><span data-stu-id="f63ea-156">Follow these steps to install the add-in so that you can use Global Inventory Accounting.</span></span>

1. <span data-ttu-id="f63ea-157">[Inscreva-se](#sign-up) na versão preliminar pública da Contabilidade de estoque global.</span><span class="sxs-lookup"><span data-stu-id="f63ea-157">[Sign up](#sign-up) for the Global Inventory Accounting public preview.</span></span>
1. <span data-ttu-id="f63ea-158">Entre no [LCS](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="f63ea-158">Sign in to [LCS](https://lcs.dynamics.com/Logon/Index).</span></span>
1. <span data-ttu-id="f63ea-159">Vá para **Gerenciamento da versão prévia do recurso**.</span><span class="sxs-lookup"><span data-stu-id="f63ea-159">Go to **Preview feature management**.</span></span>
1. <span data-ttu-id="f63ea-160">Selecione o sinal de mais (**+**).</span><span class="sxs-lookup"><span data-stu-id="f63ea-160">Select the plus sign (**+**).</span></span>
1. <span data-ttu-id="f63ea-161">No campo **Código**, insira a chave beta do complemento da Contabilidade de estoque global.</span><span class="sxs-lookup"><span data-stu-id="f63ea-161">In the **Code** field, enter your add-in beta key for Global Inventory Accounting.</span></span> <span data-ttu-id="f63ea-162">(Você deve ter recebido sua chave beta por email quando se inscreveu.)</span><span class="sxs-lookup"><span data-stu-id="f63ea-162">(You should have received your beta key by email when you signed up.)</span></span>
1. <span data-ttu-id="f63ea-163">Selecione **Desbloquear**.</span><span class="sxs-lookup"><span data-stu-id="f63ea-163">Select **Unblock**.</span></span>
1. <span data-ttu-id="f63ea-164">Abra o ambiente LCS ao qual deseja adicionar o serviço.</span><span class="sxs-lookup"><span data-stu-id="f63ea-164">Open the LCS environment where you want to add the service.</span></span>
1. <span data-ttu-id="f63ea-165">Vá para **Detalhes completos**.</span><span class="sxs-lookup"><span data-stu-id="f63ea-165">Go to **Full details**.</span></span>
1. <span data-ttu-id="f63ea-166">Vá para **Integração do Power Platform** e selecione **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="f63ea-166">Go to **Power Platform Integration**, and select **Setup**.</span></span>
1. <span data-ttu-id="f63ea-167">Na caixa de diálogo **Configuração do ambiente do Power Platform**, marque a caixa de seleção e selecione **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="f63ea-167">In the **Power platform environment setup** dialog box, select the checkbox, and then select **Setup**.</span></span> <span data-ttu-id="f63ea-168">Normalmente, a configuração leva entre 60 e 90 minutos.</span><span class="sxs-lookup"><span data-stu-id="f63ea-168">Typically, setup takes between 60 and 90 minutes.</span></span>
1. <span data-ttu-id="f63ea-169">Após a configuração do ambiente do Microsoft Power Platform ser concluída, na FastTab **Suplementos do ambiente**, selecione **Instalar um novo suplemento**.</span><span class="sxs-lookup"><span data-stu-id="f63ea-169">After setup of the Microsoft Power Platform environment is completed, on the **Environment add-ins** FastTab, select **Install a new add-in**.</span></span>
1. <span data-ttu-id="f63ea-170">Selecione **Contabilidade de estoque global**.</span><span class="sxs-lookup"><span data-stu-id="f63ea-170">Select **Global inventory accounting**.</span></span>
1. <span data-ttu-id="f63ea-171">Acompanhe o guia de instalação e concorde com os termos e condições.</span><span class="sxs-lookup"><span data-stu-id="f63ea-171">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="f63ea-172">Selecione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="f63ea-172">Select **Install**.</span></span>
1. <span data-ttu-id="f63ea-173">Na FastTab **Suplementos do ambiente**, você verá que o Contabilidade de estoque global está sendo instalado.</span><span class="sxs-lookup"><span data-stu-id="f63ea-173">On the **Environment add-ins** FastTab, you should see that Global Inventory Accounting is being installed.</span></span> <span data-ttu-id="f63ea-174">Após alguns minutos, o status deve mudar de *Instalando* para *Instalado*.</span><span class="sxs-lookup"><span data-stu-id="f63ea-174">After a few minutes, the status should change from *Installing* to *Installed*.</span></span> <span data-ttu-id="f63ea-175">(Talvez seja necessário atualizar a página para ver essa alteração.) Nesse momento, a Contabilidade de estoque global já está pronto para uso.</span><span class="sxs-lookup"><span data-stu-id="f63ea-175">(You might have to refresh the page to see this change.) At that point, Global Inventory Accounting is ready to use.</span></span>

## <a name="set-up-the-integration"></a><span data-ttu-id="f63ea-176">Configurar a integração</span><span class="sxs-lookup"><span data-stu-id="f63ea-176">Set up the integration</span></span>

<span data-ttu-id="f63ea-177">Siga essas etapas para configurar a integração entre a Contabilidade de estoque global e o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f63ea-177">Follow these steps to set up the integration between Global Inventory Accounting and Supply Chain Management.</span></span>

1. <span data-ttu-id="f63ea-178">Entre no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f63ea-178">Sign in to Supply Chain Management.</span></span>
1. <span data-ttu-id="f63ea-179">Vá para **Administração do sistema \> Gerenciamento de Recursos**.</span><span class="sxs-lookup"><span data-stu-id="f63ea-179">Go to **System administration \> Feature Management**.</span></span>
1. <span data-ttu-id="f63ea-180">Selecione **Verificar se há atualizações**.</span><span class="sxs-lookup"><span data-stu-id="f63ea-180">Select **Check for updates**.</span></span>
1. <span data-ttu-id="f63ea-181">Na guia **Tudo**, pesquise o recurso que se chama *Contabilidade de estoque global*.</span><span class="sxs-lookup"><span data-stu-id="f63ea-181">On the **All** tab, search for the feature that is named *Global inventory accounting*.</span></span>
1. <span data-ttu-id="f63ea-182">Selecione **Habilitar agora**.</span><span class="sxs-lookup"><span data-stu-id="f63ea-182">Select **Enable now**.</span></span>
1. <span data-ttu-id="f63ea-183">Vá para **Contabilidade de estoque global \> Configuração \> Parâmetros contábeis \> Integrações de parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="f63ea-183">Go to **Global inventory accounting \> Setup \> Global inventory accounting parameters \> Integrations parameters**.</span></span>
1. <span data-ttu-id="f63ea-184">Nos campos **Dados do ponto de extremidade de serviço** e **Ponto de extremidade da Contabilidade de estoque global**, insira os URLs com base no email que a equipe da Contabilidade de estoque global enviou quando você se inscreveu na versão preliminar.</span><span class="sxs-lookup"><span data-stu-id="f63ea-184">In the **Data service endpoint** and **Global inventory accounting endpoint** fields, enter the URLs from the email that the Global Inventory Accounting team sent when you signed up for the preview.</span></span>

<span data-ttu-id="f63ea-185">A Contabilidade de estoque global está pronta para uso.</span><span class="sxs-lookup"><span data-stu-id="f63ea-185">Global Inventory Accounting is now ready to use.</span></span>
