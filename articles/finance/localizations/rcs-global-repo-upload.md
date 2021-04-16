---
title: Criar configurações de ER no RCS e carregá-las no Repositório global
description: Este tópico explica como criar a configuração de relatório eletrônico (ER) no Microsoft Regulatory Configuration Services e carregá-lo para o Repositório global.
author: JaneA07
ms.date: 09/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: a138fd4b525077f12f6575f4b10f682728b71203
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838710"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a><span data-ttu-id="13a56-103">Criar configurações de ER no Regulatory Configuration Services (RCS) e carregá-las no Repositório global</span><span class="sxs-lookup"><span data-stu-id="13a56-103">Create ER configurations in Regulatory Configuration Services (RCS) and upload them to the Global repository</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="13a56-104">Você pode usar o Microsoft Regulatory Configuration Services (RCS) para criar configurações de relatório eletrônico (ER) e publicá-los para que possam ser usados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="13a56-104">You can use Microsoft Regulatory Configuration Services (RCS) to design Electronic reporting (ER) configurations and publish them so that they can be used in your organization.</span></span>

<span data-ttu-id="13a56-105">Os procedimentos a seguir explicam como um usuário na função de administrador do sistema ou de relatório eletrônico pode criar uma versão derivada da configuração ER que foi configurada em uma instância RCS e, em seguida, carregar a configuração derivada para o repositório global.</span><span class="sxs-lookup"><span data-stu-id="13a56-105">The following procedures explain how a user in the System Administrator or Electronic Reporting Developer role can create a derived version of an ER configuration that has been configured in an RCS instance, and then upload the derived configuration to the Global repository.</span></span> 

<span data-ttu-id="13a56-106">Antes de concluir esses procedimentos, conclua os seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="13a56-106">Before you can complete those procedures, you must complete the following prerequisites:</span></span>

- <span data-ttu-id="13a56-107">Acessar uma instância RCS.</span><span class="sxs-lookup"><span data-stu-id="13a56-107">Access an RCS instance.</span></span>
- <span data-ttu-id="13a56-108">Criar um fornecedor de configuração ativa.</span><span class="sxs-lookup"><span data-stu-id="13a56-108">Create an active configuration provider.</span></span> <span data-ttu-id="13a56-109">Para obter mais informações, consulte [Criar provedores de configuração e marcá-los como ativos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="13a56-109">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

<span data-ttu-id="13a56-110">Você também deve verificar se um ambiente RCS foi provisionado para sua empresa.</span><span class="sxs-lookup"><span data-stu-id="13a56-110">You must also make sure that an RCS environment is provisioned for your company.</span></span>

1. <span data-ttu-id="13a56-111">Em um aplicativo do Finance and Operations, acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="13a56-111">In a Finance and Operations app, go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="13a56-112">Se não tiver o ambiente do RCS provisionado para sua empresa, clique no link externo **Regulatory services – Configuração** e siga as instruções para provisionar um.</span><span class="sxs-lookup"><span data-stu-id="13a56-112">If no RCS environment is provisioned for your company, select **Regulatory services – Configuration external**, and then follow the instructions to provision one.</span></span>

<span data-ttu-id="13a56-113">Se um ambiente RCS já foi provisionado para sua empresa, use a URL da página para acessá-lo, selecionando a opção de entrada.</span><span class="sxs-lookup"><span data-stu-id="13a56-113">If an RCS environment has been already provisioned for your company, use the page URL to access it by selecting the sign-in option.</span></span>

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a><span data-ttu-id="13a56-114">Criar uma versão derivada de uma configuração no RCS</span><span class="sxs-lookup"><span data-stu-id="13a56-114">Create a derived version of a configuration in RCS</span></span>

1. <span data-ttu-id="13a56-115">No espaço de trabalho **Relatório eletrônico**, verifique se você tem um provedor de configuração ativo para sua organização.</span><span class="sxs-lookup"><span data-stu-id="13a56-115">In the **Electronic reporting** workspace, verify that you have an active configuration provider for your organization.</span></span> 
2. <span data-ttu-id="13a56-116">Selecione **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="13a56-116">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="13a56-117">Selecione a configuração da qual você deseja derivar uma nova versão.</span><span class="sxs-lookup"><span data-stu-id="13a56-117">Select the configuration that you want to derive a new version from.</span></span> <span data-ttu-id="13a56-118">Você pode usar o campo de filtro acima da árvore para restringir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="13a56-118">You can use the filter field above the tree to narrow your search.</span></span>
4. <span data-ttu-id="13a56-119">Selecione **Criar configuração** \> **Derivar de Nome**.</span><span class="sxs-lookup"><span data-stu-id="13a56-119">Select **Create configuration** \> **Derive from Name**.</span></span>
5. <span data-ttu-id="13a56-120">Insira um nome e uma descrição e selecione **Criar configuração** para criar uma nova versão derivada.</span><span class="sxs-lookup"><span data-stu-id="13a56-120">Enter a name and description, and then select **Create configuration** to create a new derived version.</span></span>
6. <span data-ttu-id="13a56-121">Selecione a configuração derivada recentemente, adicione uma descrição da versão e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="13a56-121">Select the newly derived configuration, add a description of the version, and then select **OK**.</span></span> <span data-ttu-id="13a56-122">O status da configuração a é alterado para **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="13a56-122">The status of the configuration to is changed to **Completed**.</span></span>

![Nova versão de configuração no RCS](media/RCS_CompleteConfig.JPG)

> [!NOTE]
> <span data-ttu-id="13a56-124">Quando o status da configuração for alterado, você poderá receber uma mensagem de erro de validação relacionada aos aplicativos conectados.</span><span class="sxs-lookup"><span data-stu-id="13a56-124">When the configuration status is changed, you might receive a validation error message that is related to the connected applications.</span></span> <span data-ttu-id="13a56-125">Para desativar a validação, no Painel de Ações, na guia **Configurações**, selecione **Parâmetros do usuário** e defina a opção **Ignorar validação na alteração e troca do status de configuração** para **Sim**</span><span class="sxs-lookup"><span data-stu-id="13a56-125">To turn off the validation, on the Action Pane on the **Configurations** tab, select **User parameters**, and then set the **Skip validation at configuration's status change and rebase** option to **Yes**</span></span> 

## <a name="upload-a-configuration-to-the-global-repository"></a><span data-ttu-id="13a56-126">Carregar uma configuração para o Repositório global</span><span class="sxs-lookup"><span data-stu-id="13a56-126">Upload a configuration to the Global repository</span></span>

<span data-ttu-id="13a56-127">Para compartilhar uma configuração nova ou derivada com sua organização, você pode carregá-la no Repositório global.</span><span class="sxs-lookup"><span data-stu-id="13a56-127">To share a new or derived configuration with your organization, you can upload it to the Global repository.</span></span>

1. <span data-ttu-id="13a56-128">Selecione a versão concluída da configuração e, em seguida, selecione **Carregar no repositório**.</span><span class="sxs-lookup"><span data-stu-id="13a56-128">Select the completed version of the configuration, and then select **Upload into repository**.</span></span>
2. <span data-ttu-id="13a56-129">Selecione a opção **Global (Microsoft)** e, em seguida, selecione **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="13a56-129">Select the **Global (Microsoft)** option, and then select **Upload**.</span></span>

    ![Carregar em opções de repositório](media/RCS_Upload_to_GlobalRepo_options.JPG)

3. <span data-ttu-id="13a56-131">Na caixa de mensagem de confirmação, selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="13a56-131">In the confirmation message box, select **Yes**.</span></span> 
4. <span data-ttu-id="13a56-132">Atualize a descrição da versão conforme necessário e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="13a56-132">Update the description of the version as required, and then select **OK**.</span></span> 

<span data-ttu-id="13a56-133">O status da configuração é atualizado para **Compartilhar** e a configuração é carregada no repositório global.</span><span class="sxs-lookup"><span data-stu-id="13a56-133">The status of the configuration is updated to **Share**, and the configuration is uploaded to the Global repository.</span></span> <span data-ttu-id="13a56-134">A partir daí, você pode trabalhar com ela da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="13a56-134">From there, you can work with it in the following ways:</span></span>

- <span data-ttu-id="13a56-135">Importe-o para a instância do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="13a56-135">Import it into your Dynamics 365 instance.</span></span> <span data-ttu-id="13a56-136">Para obter mais informações, consulte [Importar configurações do ER a partir de RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).</span><span class="sxs-lookup"><span data-stu-id="13a56-136">For more information, see [(ER) Import configurations from RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).</span></span>
- <span data-ttu-id="13a56-137">Compartilhar com terceiros ou com uma organização externa, consulte [Configurações de relatório eletrônico de compartilhamento RCS (ER) com organizações externas](rcs-global-repo-share-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="13a56-137">Share it with a third party or an external organization, see [RCS Share Electronic reporting (ER) configurations with external organizations](rcs-global-repo-share-configuration.md)</span></span>

    ![Versão de configuração da Contoso do Intrastat derivada no Repositório global](media/RCS_Config_upload_GlobalRepo.JPG)

## <a name="delete-a-configuration-from-the-global-repository"></a><span data-ttu-id="13a56-139">Excluir uma configuração do Repositório global</span><span class="sxs-lookup"><span data-stu-id="13a56-139">Delete a configuration from the Global repository</span></span>
<span data-ttu-id="13a56-140">Conclua as etapas a seguir para excluir uma configuração criada pela sua organização.</span><span class="sxs-lookup"><span data-stu-id="13a56-140">Complete the following steps to delete a configuration that your organization has created.</span></span>

1. <span data-ttu-id="13a56-141">No espaço de trabalho **Relatório eletrônico**, verifique se seu provedor de configuração está **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="13a56-141">In the **Electronic reporting** workspace, verify that your configuration provider is **Active**.</span></span> <span data-ttu-id="13a56-142">Para obter mais informações, consulte [Criar provedores de configuração e marcá-los como ativos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="13a56-142">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
2. <span data-ttu-id="13a56-143">No provedor de configuração ativo, selecione **repositório**.</span><span class="sxs-lookup"><span data-stu-id="13a56-143">On your active configuration provider, select **repository**.</span></span>
3. <span data-ttu-id="13a56-144">Selecione o tipo de repositório **Global** e selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="13a56-144">Select the repository type **Global**, and select **Open**.</span></span>
4. <span data-ttu-id="13a56-145">Na Guia Rápida **Filtro**, localize a configuração que deseja excluir usando a funcionalidade de **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="13a56-145">On the **Filter** FastTab, find the configuration that you want to delete by using the **Filter** functionality.</span></span>
5. <span data-ttu-id="13a56-146">Na Guia Rápida **Versão**, selecione a versão da configuração que deseja excluir e, em seguida, selecione **Excluir**:</span><span class="sxs-lookup"><span data-stu-id="13a56-146">On the **Version** FastTab, select the version of the configuration that you want to delete, and then select **Delete**:</span></span>

    ![Excluir configuração do repositório global](media/RCS_Delete_from_GlobalRepo.JPG)

6. <span data-ttu-id="13a56-148">Na caixa de mensagem de confirmação, selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="13a56-148">In the confirmation message box, select **Yes**.</span></span>

    ![Excluir mensagem de confirmação de versão de configuração](media/RCS_Delete_from_GlobalRepo_Msg.JPG)
 
<span data-ttu-id="13a56-150">A versão de configuração é excluída e a mensagem de confirmação é exibida.</span><span class="sxs-lookup"><span data-stu-id="13a56-150">The configuration version is deleted, and confirmation message is shown.</span></span> 

> [!NOTE]
> <span data-ttu-id="13a56-151">As configurações só podem ser excluídas pelo provedor de configuração que as criou.</span><span class="sxs-lookup"><span data-stu-id="13a56-151">Configurations can only be deleted by the Configuration provider that created them.</span></span> <span data-ttu-id="13a56-152">Se a configuração tiver sido compartilhada com outra organização, terá de ser descompartilhada antes de ser excluída.</span><span class="sxs-lookup"><span data-stu-id="13a56-152">If the configuration has been shared with another organization, the configuration will need to be unshared before you delete it.</span></span>
 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]