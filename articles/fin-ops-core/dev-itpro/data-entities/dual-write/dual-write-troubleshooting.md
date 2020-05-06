---
title: Solução de problemas gerais
description: Este tópico fornece informações gerais de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: d5d9dbce0c74d32107db6bbae033b921e4201693
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275641"
---
# <a name="general-troubleshooting"></a><span data-ttu-id="4e05e-103">Solução de problemas gerais</span><span class="sxs-lookup"><span data-stu-id="4e05e-103">General troubleshooting</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="4e05e-104">Este tópico fornece informações gerais de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="4e05e-104">This topic provides general troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e05e-105">Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="4e05e-105">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="4e05e-106">A seção para cada problema explica se uma função ou credenciais específicas são necessárias.</span><span class="sxs-lookup"><span data-stu-id="4e05e-106">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="when-you-try-to-install-the-dual-write-package-by-using-the-package-deployer-tool-no-available-solutions-are-shown"></a><span data-ttu-id="4e05e-107">Ao tentar instalar o pacote de gravação dupla usando a ferramenta Package Deployer, nenhuma solução disponível é mostrada</span><span class="sxs-lookup"><span data-stu-id="4e05e-107">When you try to install the dual-write package by using the package deployer tool, no available solutions are shown</span></span>

<span data-ttu-id="4e05e-108">Algumas versões da ferramenta Package Deployer são incompatíveis com o pacote de solução de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="4e05e-108">Some versions of the package deployer tool are incompatible with the dual-write solution package.</span></span> <span data-ttu-id="4e05e-109">Para instalar o pacote com êxito, certifique-se de usar a [versão 9.1.0.20](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf/9.1.0.20) ou posterior da ferramenta Package Deployer.</span><span class="sxs-lookup"><span data-stu-id="4e05e-109">To successfully install the package, be sure to use [version 9.1.0.20](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf/9.1.0.20) or later of the package deployer tool.</span></span>

<span data-ttu-id="4e05e-110">Depois de instalar a ferramenta do Package Deployer, instale o pacote de solução seguindo essas etapas.</span><span class="sxs-lookup"><span data-stu-id="4e05e-110">After you install the package deployer tool, install the solution package by following these steps.</span></span>

1. <span data-ttu-id="4e05e-111">Baixe o arquivo de pacote de solução mais recente de Yammer.com.</span><span class="sxs-lookup"><span data-stu-id="4e05e-111">Download the latest solution package file from Yammer.com.</span></span> <span data-ttu-id="4e05e-112">Depois que o arquivo zip do pacote for baixado, clique nele com o botão direito do mouse e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4e05e-112">After the package zip file is downloaded, right-click it, and select **Properties**.</span></span> <span data-ttu-id="4e05e-113">Marque caixa de seleção **Desbloquear** e selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="4e05e-113">Select the **Unblock** check box, and then select **Apply**.</span></span> <span data-ttu-id="4e05e-114">Se você não vir a caixa de seleção **Desbloquear**, o arquivo zip já está desbloqueado e você pode ignorar essa etapa.</span><span class="sxs-lookup"><span data-stu-id="4e05e-114">If you don't see the **Unblock** check box, the zip file is already unblocked, and you can skip this step.</span></span>

    ![Caixa de diálogo de propriedades](media/unblock_option.png)

2. <span data-ttu-id="4e05e-116">Extraia o arquivo compactado no pacote e copie todos os arquivos na pasta **Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438**.</span><span class="sxs-lookup"><span data-stu-id="4e05e-116">Extract the package zip file, and copy all the files in the **Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438** folder.</span></span>

    ![Conteúdo da pasta Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438](media/extract_package.png)

3. <span data-ttu-id="4e05e-118">Cole todos os arquivos copiados na pasta **Ferramentas** da ferramenta Package Deployer.</span><span class="sxs-lookup"><span data-stu-id="4e05e-118">Paste all the copied files into the **Tools** folder of the package deployer tool.</span></span> 
4. <span data-ttu-id="4e05e-119">Execute **PackageDeployer.exe** para selecionar o ambiente Common Data Service e instale as soluções.</span><span class="sxs-lookup"><span data-stu-id="4e05e-119">Run **PackageDeployer.exe** to select the Common Data Service environment and install the solutions.</span></span>

    ![Conteúdo da pasta Ferramentas](media/paste_copied_files.png)

## <a name="enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details"></a><span data-ttu-id="4e05e-121">Habilite e exiba o log de rastreamento de plug-in no Common Data Service para exibir detalhes do erro</span><span class="sxs-lookup"><span data-stu-id="4e05e-121">Enable and view the plug-in trace log in Common Data Service to view error details</span></span>

<span data-ttu-id="4e05e-122">**Função necessária para ativar o log de rastreamento e erros de exibição**: administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="4e05e-122">**Required role to turn on the trace log and view errors:** System admin</span></span>

<span data-ttu-id="4e05e-123">Para ativar o log de rastreamento, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4e05e-123">To turn on the trace log, follow these steps.</span></span>

1. <span data-ttu-id="4e05e-124">Efetue login no aplicativo Finance and Operations, abra a página **Configurações** e, em **Sistema**, selecione **Administração**.</span><span class="sxs-lookup"><span data-stu-id="4e05e-124">Sign in to the Finance and Operations app, open the **Settings** page, and then, under **System**, select **Administration**.</span></span>
2. <span data-ttu-id="4e05e-125">Na página **Administração**, selecione **Configuração do sistema**.</span><span class="sxs-lookup"><span data-stu-id="4e05e-125">On the **Administration** page, select **System Settings**.</span></span>
3. <span data-ttu-id="4e05e-126">Na guia **Personalização**, no campo **Rastreamento de atividade de fluxo de trabalho e plug-in**, selecione **Todos** para habilitar o log de rastreamento de plug-in.</span><span class="sxs-lookup"><span data-stu-id="4e05e-126">On the **Customization** tab, in the **Plug-in and custom workflow activity tracing** field, select **All** to enable the plug-in trace log.</span></span> <span data-ttu-id="4e05e-127">Se você deseja registrar logs de rastreamento somente quando ocorrerem exceções, em vez disso, você pode selecionar **Exceção**.</span><span class="sxs-lookup"><span data-stu-id="4e05e-127">If you want to log trace logs only when exceptions occur, you can select **Exception** instead.</span></span>


<span data-ttu-id="4e05e-128">Para exibir o log de rastreamento, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4e05e-128">To view the trace log, follow these steps.</span></span>

1. <span data-ttu-id="4e05e-129">Efetue login no aplicativo Finance and Operations, abra a página **Configurações** e, em **Personalização**, selecione **Log de rastreamento de plug-in**.</span><span class="sxs-lookup"><span data-stu-id="4e05e-129">Sign in to the Finance and Operations app, open the **Settings** page, and then, under **Customization**, select **Plug-in Trace Log**.</span></span>
2. <span data-ttu-id="4e05e-130">Encontre os logs de rastreamento em que o campo **Nome do Tipo** esteja definido como **Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PreCommmitPlugin**.</span><span class="sxs-lookup"><span data-stu-id="4e05e-130">Find the trace logs where the **Type Name** field is set to **Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PreCommmitPlugin**.</span></span>
3. <span data-ttu-id="4e05e-131">Clique duas vezes em um item para exibir o log completo e, em seguida, na Guia Rápida **Execução** revise o texto do **Bloco de mensagens**.</span><span class="sxs-lookup"><span data-stu-id="4e05e-131">Double-click an item to view the full log, and then, on the **Execution** FastTab, review the **Message Block** text.</span></span>

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a><span data-ttu-id="4e05e-132">Habilitar modo de depuração para solucionar problemas de sincronização dinâmica em aplicativos Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4e05e-132">Enable debug mode to troubleshoot live synchronization issues in Finance and Operations apps</span></span>

<span data-ttu-id="4e05e-133">**Função necessária para exibir os erros:** erros de gravação dupla do administrador do sistema que se originam no Common Data Service e podem ser exibidos no aplicativo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4e05e-133">**Required role to view the errors:** System admin Dual-write errors that originate in Common Data Service can appear in the Finance and Operations app.</span></span> <span data-ttu-id="4e05e-134">Em alguns casos, o texto completo da mensagem de erro não está disponível porque a mensagem é muito longa ou contém informações de identificação pessoal (PII).</span><span class="sxs-lookup"><span data-stu-id="4e05e-134">In some cases, the full text of the error message isn't available because the message is too long or contains personally identifying information (PII).</span></span> <span data-ttu-id="4e05e-135">Você pode ativar o registro detalhado de erros ao seguir estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4e05e-135">You can turn on verbose logging for errors by following these steps.</span></span>

1. <span data-ttu-id="4e05e-136">Todas as configurações de projeto nos aplicativos Finance and Operations têm uma propriedade **IsDebugMode** na entidade **DualWriteProjectConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="4e05e-136">All project configurations in Finance and Operations apps have an **IsDebugMode** property in the **DualWriteProjectConfiguration** entity.</span></span> <span data-ttu-id="4e05e-137">Abra a entidade **DualWriteProjectConfiguration** usando um suplemento do Excel.</span><span class="sxs-lookup"><span data-stu-id="4e05e-137">Open the **DualWriteProjectConfiguration** entity by using the Excel add-in.</span></span>

    > [!TIP]
    > <span data-ttu-id="4e05e-138">Uma forma simples de abrir a entidade é ativar o modo **Design** no suplemento do Excel e adicionar **DualWriteProjectConfigurationEntity** à planilha.</span><span class="sxs-lookup"><span data-stu-id="4e05e-138">An easy way to open the entity is to turn on **Design** mode in the Excel add-in and then add **DualWriteProjectConfigurationEntity** to the worksheet.</span></span> <span data-ttu-id="4e05e-139">Para obter mais informações, consulte [Abrir os dados da entidade no Excel e atualizá-los usando o suplemento do Excel](../../office-integration/use-excel-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="4e05e-139">For more information, see [Open entity data in Excel and update it by using the Excel add-in](../../office-integration/use-excel-add-in.md).</span></span>

2. <span data-ttu-id="4e05e-140">Defina a propriedade **IsDebugMode** como **Sim** para o projeto.</span><span class="sxs-lookup"><span data-stu-id="4e05e-140">Set the **IsDebugMode** property to **Yes** for the project.</span></span>
3. <span data-ttu-id="4e05e-141">Execute o cenário que está gerando erros.</span><span class="sxs-lookup"><span data-stu-id="4e05e-141">Run the scenario that is generating errors.</span></span>
4. <span data-ttu-id="4e05e-142">Os logs detalhados estão disponíveis na tabela DualWriteErrorLog.</span><span class="sxs-lookup"><span data-stu-id="4e05e-142">The verbose logs are available in the DualWriteErrorLog table.</span></span> <span data-ttu-id="4e05e-143">Para pesquisar dados no navegador da tabela, use a seguinte URL (substitua **XXX**, conforme apropriado):</span><span class="sxs-lookup"><span data-stu-id="4e05e-143">To look up data in the table browser, use the following URL (replace **XXX** as appropriate):</span></span>

    `https://XXXaos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=>DualWriteErrorLog`

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a><span data-ttu-id="4e05e-144">Verificar erros de sincronização na máquina virtual para o aplicativo Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4e05e-144">Check synchronization errors on the virtual machine for the Finance and Operations app</span></span>

<span data-ttu-id="4e05e-145">**Função necessária para exibir os erros:** administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="4e05e-145">**Required role to view the errors:** System administrator</span></span>

1. <span data-ttu-id="4e05e-146">Entre Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="4e05e-146">Sign in to Microsoft Dynamics Lifecycle Services (LCS).</span></span>
2. <span data-ttu-id="4e05e-147">Abra o projeto LCS escolhido para realizar testes de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="4e05e-147">Open the LCS project that you chose to do the dual-write testing for.</span></span>
3. <span data-ttu-id="4e05e-148">Selecione o bloco **Ambientes hospedados na nuvem**.</span><span class="sxs-lookup"><span data-stu-id="4e05e-148">Select the **Cloud-hosted environments** tile.</span></span>
4. <span data-ttu-id="4e05e-149">Use área de trabalho remota para fazer login na máquina virtual (VM) do aplicativo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4e05e-149">Use Remote Desktop to sign in to the virtual machine (VM) for the Finance and Operations app.</span></span> <span data-ttu-id="4e05e-150">Use a conta local que é mostrada em LCS.</span><span class="sxs-lookup"><span data-stu-id="4e05e-150">Use the local account that is shown in LCS.</span></span>
5. <span data-ttu-id="4e05e-151">Abra o Visualizador de Eventos.</span><span class="sxs-lookup"><span data-stu-id="4e05e-151">Open Event viewer.</span></span>
6. <span data-ttu-id="4e05e-152">Selecione **Registros de aplicativos e serviços \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operacional**.</span><span class="sxs-lookup"><span data-stu-id="4e05e-152">Select **Applications and Services Logs \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operational**.</span></span>
7. <span data-ttu-id="4e05e-153">Revise a lista de erros recentes.</span><span class="sxs-lookup"><span data-stu-id="4e05e-153">Review the list of recent errors.</span></span>

## <a name="unlink-and-link-another-common-data-service-environment-from-a-finance-and-operations-app"></a><span data-ttu-id="4e05e-154">Desvincular e vincular outro ambiente do Common Data Service de um aplicativo Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4e05e-154">Unlink and link another Common Data Service environment from a Finance and Operations app</span></span>

<span data-ttu-id="4e05e-155">**Função necessária para desvincular o ambiente:** administrador do sistema para os aplicativos Finance and Operations ou Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="4e05e-155">**Required role to unlink the environment:** System administrator for either Finance and Operations app or Common Data Service.</span></span>

1. <span data-ttu-id="4e05e-156">Entrar no aplicativo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4e05e-156">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="4e05e-157">Vá para **Espaços de trabalho \> Gerenciamento de dados** e selecione o bloco **Gravação dupla**.</span><span class="sxs-lookup"><span data-stu-id="4e05e-157">Go to **Workspaces \> Data management**, and select the **Dual Write** tile.</span></span>
3. <span data-ttu-id="4e05e-158">Selecione todos os mapeamentos em execução e selecione **Parar**.</span><span class="sxs-lookup"><span data-stu-id="4e05e-158">Select all running mappings, and then select **Stop**.</span></span>
4. <span data-ttu-id="4e05e-159">Selecione **Desvincular ambiente**.</span><span class="sxs-lookup"><span data-stu-id="4e05e-159">Select **Unlink environment**.</span></span>
5. <span data-ttu-id="4e05e-160">Selecione **Sim** para confirmar a operação.</span><span class="sxs-lookup"><span data-stu-id="4e05e-160">Select **Yes** to confirm the operation.</span></span>

<span data-ttu-id="4e05e-161">Agora você pode vincular um novo ambiente.</span><span class="sxs-lookup"><span data-stu-id="4e05e-161">You can now link a new environment.</span></span>

## <a name="unable-to-view-the-sales-order-line-information-form"></a><span data-ttu-id="4e05e-162">Não é possível exibir o formulário de informações da linha da ordem de venda</span><span class="sxs-lookup"><span data-stu-id="4e05e-162">Unable to view the sales order line Information form</span></span> 

<span data-ttu-id="4e05e-163">Quando você cria uma ordem de venda no Dynamics 365 Sales, clicar em **Adicionar produtos** talvez redirecione você para o formulário da linha de ordem do Dynamics 365 Project Operations.</span><span class="sxs-lookup"><span data-stu-id="4e05e-163">When you create a sales order in Dynamics 365 Sales, clicking on **+ Add products** might redirect you to the Dynamics 365 Project Operations order line form.</span></span> <span data-ttu-id="4e05e-164">Não há nenhuma maneira de esse formulário exibir o formulário de **Informações** da linha da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="4e05e-164">There is no way from that form to view the sales order line **Information** form.</span></span> <span data-ttu-id="4e05e-165">A opção de **Informações** não aparece na lista suspensa **Nova Linha da Ordem** abaixo.</span><span class="sxs-lookup"><span data-stu-id="4e05e-165">The option for **Information** does not appear in the dropdown below **New Order Line**.</span></span> <span data-ttu-id="4e05e-166">Isso ocorre porque o Project Operations foi instalado em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="4e05e-166">This happens because Project Operations has been installed in your environment.</span></span>

<span data-ttu-id="4e05e-167">Para habilitar novamente a opção de formulário de **Informações**, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="4e05e-167">To re-enable the **Information** form option, follow these steps:</span></span>
1. <span data-ttu-id="4e05e-168">Navegue até a entidade **Linha da Ordem**.</span><span class="sxs-lookup"><span data-stu-id="4e05e-168">Navigate to the **Order Line** entity.</span></span>
2. <span data-ttu-id="4e05e-169">Encontre o formulário de **Informações** no nó de formulários.</span><span class="sxs-lookup"><span data-stu-id="4e05e-169">Find the **Information** form under the forms node.</span></span> 
3. <span data-ttu-id="4e05e-170">Selecione o formulário de **Informações** e clique em **Habilitar funções de segurança**.</span><span class="sxs-lookup"><span data-stu-id="4e05e-170">Select the **Information** form and click **Enable security roles**.</span></span> 
4. <span data-ttu-id="4e05e-171">Altere a configuração de segurança para **Exibir para todos**.</span><span class="sxs-lookup"><span data-stu-id="4e05e-171">Change the security setting to **Display to everyone**.</span></span>
