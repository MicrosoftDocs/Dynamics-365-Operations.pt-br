---
title: Regulatory Configuration Service (RCS) — Recursos de globalização
description: Este tópico explica como usar o Microsoft Regulatory Configuration Services (RCS) e o Repositório global para criar e usar Recursos de globalização.
author: JaneA07
ms.date: 06/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, RCSWorkspace, e-Invoicing service
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: cbb1d9a53a7a09ab525532f08553898c4e40223a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822772"
---
# <a name="regulatory-configuration-services-rcs---globalization-features"></a><span data-ttu-id="23371-103">Regulatory Configuration Service (RCS) — Recursos de globalização</span><span class="sxs-lookup"><span data-stu-id="23371-103">Regulatory Configuration Services (RCS) - Globalization features</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="23371-104">Você pode usar o Microsoft Regulatory Configuration Services (RCS) para criar um Recurso de globalização que pode ser usado nos Serviços de globalização, como um serviço de faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="23371-104">You can use Microsoft Regulatory Configuration Services (RCS) to create a Globalization feature that can be used in Globalization services, such as an e-invoicing service.</span></span> <span data-ttu-id="23371-105">O RCS permite executar estas tarefas:</span><span class="sxs-lookup"><span data-stu-id="23371-105">RCS lets you perform these tasks:</span></span>

- <span data-ttu-id="23371-106">Definir componentes relacionados de um recurso.</span><span class="sxs-lookup"><span data-stu-id="23371-106">Define related components of a feature.</span></span>
- <span data-ttu-id="23371-107">Gerenciar o ciclo de vida do recurso por meio do status de um recurso.</span><span class="sxs-lookup"><span data-stu-id="23371-107">Manage the feature lifecycle through a feature's status.</span></span>
- <span data-ttu-id="23371-108">Disponibilizar um recurso para ambientes definidos.</span><span class="sxs-lookup"><span data-stu-id="23371-108">Make a feature available for defined environments.</span></span>
- <span data-ttu-id="23371-109">Compartilhar um recurso com outras organizações.</span><span class="sxs-lookup"><span data-stu-id="23371-109">Share a feature with other organizations.</span></span>

<span data-ttu-id="23371-110">Os procedimentos a seguir explicam como um usuário no RCS pode adicionar um recurso de globalização e componentes relacionados, atualizar o status do recurso e disponibilizar o recurso para que possa ser usado nos serviços de globalização.</span><span class="sxs-lookup"><span data-stu-id="23371-110">The following procedures explain how a user in RCS can add a Globalization feature and related components, update the feature's status, and make the feature available so that it can be used in Globalization services.</span></span>

<span data-ttu-id="23371-111">Antes de concluir os procedimentos, você deverá concluir as etapas relacionadas às seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="23371-111">Before you complete the procedures, you must complete the steps that are related to the following tasks:</span></span>

- <span data-ttu-id="23371-112">Acessar uma instância RCS.</span><span class="sxs-lookup"><span data-stu-id="23371-112">Accessing an RCS instance.</span></span>
- <span data-ttu-id="23371-113">Criar e ativar um provedor de configuração.</span><span class="sxs-lookup"><span data-stu-id="23371-113">Creating and activating a configuration provider.</span></span> <span data-ttu-id="23371-114">Para obter mais informações, consulte [Criar provedores de configuração e marcá-los como ativos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="23371-114">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

<span data-ttu-id="23371-115">Na sua instância de aplicativos do Finance and Operations, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="23371-115">In your Finance and Operations apps instance, follow these steps.</span></span>

1. <span data-ttu-id="23371-116">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="23371-116">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="23371-117">Se não tiver o ambiente do RCS provisionado para sua empresa, selecione **Regulatory services – Configuração** e siga as instruções para provisionar um.</span><span class="sxs-lookup"><span data-stu-id="23371-117">If no RCS environment is provisioned for your company, select **Regulatory services – Configuration**, and follow the instructions to provision one.</span></span>

> [!NOTE]
> <span data-ttu-id="23371-118">Se um ambiente RCS já tiver sido provisionado para sua empresa, use a URL da página para acessá-lo selecionando a opção de entrada.</span><span class="sxs-lookup"><span data-stu-id="23371-118">If an RCS environment has already been provisioned for your company, use the page URL to access the environment by selecting the sign-in option.</span></span>

## <a name="turn-on-the-globalization-features"></a><span data-ttu-id="23371-119">Ativar os Recursos de globalização</span><span class="sxs-lookup"><span data-stu-id="23371-119">Turn on the Globalization features</span></span>

1. <span data-ttu-id="23371-120">Na instância RCS, selecione o bloco **Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="23371-120">In your RCS instance, select the **Feature management** tile.</span></span>
2. <span data-ttu-id="23371-121">No espaço de trabalho **Gerenciamento de recursos** , selecione **Recursos de globalização** na lista e, em seguida, selecione **Habilitar agora**.</span><span class="sxs-lookup"><span data-stu-id="23371-121">In the **Feature management** workspace, select **Globalization features** in the list, and then select **Enable now**.</span></span>

    ![Recursos de globalização no Gerenciamento de recursos](./media/RCS_GlobalF_1%20Feature%20mgmt.JPG)

## <a name="globalization-features"></a><span data-ttu-id="23371-123">Recursos de globalização</span><span class="sxs-lookup"><span data-stu-id="23371-123">Globalization features</span></span>

<span data-ttu-id="23371-124">Para usar um Recurso de globalização, primeiro você deverá importá-lo do Repositório global e criar sua própria versão.</span><span class="sxs-lookup"><span data-stu-id="23371-124">To use a Globalization feature, you must first import it from the the Global repository and create your own version of it.</span></span> <span data-ttu-id="23371-125">Há duas maneiras de adicionar Recursos de globalização:</span><span class="sxs-lookup"><span data-stu-id="23371-125">There are two ways to add Globalization features:</span></span>

- <span data-ttu-id="23371-126">Adicione um recurso derivado que se baseia em um recurso existente que foi publicado ou compartilhado.</span><span class="sxs-lookup"><span data-stu-id="23371-126">Add a derived feature that is based on an existing feature that has been published or shared.</span></span>
- <span data-ttu-id="23371-127">Adicione um novo recurso criado do zero.</span><span class="sxs-lookup"><span data-stu-id="23371-127">Add a new feature that you've created from scratch.</span></span>

## <a name="access-globalization-features"></a><span data-ttu-id="23371-128">Acessar Recursos de globalização</span><span class="sxs-lookup"><span data-stu-id="23371-128">Access Globalization features</span></span>

1. <span data-ttu-id="23371-129">Verifique se o recurso **Recursos de globalização** está ativado no Gerenciamento de recursos conforme descrito anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="23371-129">Make sure that the **Globalization features** feature is turned on in Feature management, as described earlier in this topic.</span></span>
2. <span data-ttu-id="23371-130">Abra o novo espaço de trabalho **Recursos de Globalização** e, em seguida, em **Recursos**, selecione o bloco **Faturamento eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="23371-130">Open the new **Globalization Features** workspace, and then, under **Features**, select the **e-Invoicing** tile.</span></span>

    ![Espaço de trabalho Recursos Globais](./media/RCS_GlobalF_2%20Feature%20wrkspace.JPG)

    <span data-ttu-id="23371-132">A página **Recursos de faturamento eletrônico** é aberta.</span><span class="sxs-lookup"><span data-stu-id="23371-132">The **e-Invoicing Features** page is opened.</span></span>

    ![Página Recursos de faturamento eletrônico](./media/RCS_GlobalF_3%20Feature%20form.JPG)

## <a name="add-a-derived-globalization-feature"></a><span data-ttu-id="23371-134">Adicionar um Recurso de globalização derivado</span><span class="sxs-lookup"><span data-stu-id="23371-134">Add a derived Globalization feature</span></span>

<span data-ttu-id="23371-135">Você pode adicionar um novo Recurso de globalização derivando-o de um recurso existente que foi publicado ou compartilhado.</span><span class="sxs-lookup"><span data-stu-id="23371-135">You can add a new Globalization feature by deriving it from an existing feature that has been published or shared.</span></span>

1. <span data-ttu-id="23371-136">Selecione **Importar** para abrir a página **Importar recurso do Repositório global**.</span><span class="sxs-lookup"><span data-stu-id="23371-136">Select **Import** to open the **Import feature from Global repository** page.</span></span>

    ![Página Importar recurso do Repositório global](./media/RCS_GlobalF_4%20Feature%20import%20form%20GR.JPG)

2. <span data-ttu-id="23371-138">Selecione **Sincronizar** para obter os recursos mais recentes.</span><span class="sxs-lookup"><span data-stu-id="23371-138">Select **Synchronize** to get the latest features.</span></span>

    <span data-ttu-id="23371-139">A lista sincronizada inclui recursos que estão disponíveis para você porque foram publicados pela Microsoft ou porque foram compartilhados com você por outro provedor de configuração.</span><span class="sxs-lookup"><span data-stu-id="23371-139">The synced list includes features that are available to you either because they were published by Microsoft or because they were shared with you by another configuration provider.</span></span>

    ![Lista de recursos sincronizados](./media/RCS_GlobalF_5%20Feature%20GR%20sync.JPG)

3. <span data-ttu-id="23371-141">Na lista, selecione os recursos a serem importados e, em seguida, selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="23371-141">In the list, select the features to import, and then select **Import**.</span></span> <span data-ttu-id="23371-142">Você receberá uma mensagem quando os recursos selecionados tiverem sido importados com êxito.</span><span class="sxs-lookup"><span data-stu-id="23371-142">You receive a message when the selected features have been successfully imported.</span></span>

    ![Mensagem de importação bem-sucedida](./media/RCS_GlobalF_6%20Feature%20GR%20import%20success.JPG)

4. <span data-ttu-id="23371-144">Selecione **Adicionar** e , na caixa de diálogo suspensa, selecione a opção **Com base na versão existente**.</span><span class="sxs-lookup"><span data-stu-id="23371-144">Select **Add**, and then, in the drop-down dialog box, select the **Based on existing version** option.</span></span>
5. <span data-ttu-id="23371-145">Digite um nome e uma descrição para o recurso.</span><span class="sxs-lookup"><span data-stu-id="23371-145">Enter a name and description for the feature.</span></span>
6. <span data-ttu-id="23371-146">Na lista de recursos disponíveis, selecione a versão base do recurso e selecione **Criar recurso**.</span><span class="sxs-lookup"><span data-stu-id="23371-146">In the list of available features, select the base version of the feature, and then select **Create feature**.</span></span>

    ![Adição de um recurso derivado](./media/RCS_GlobalF_7%20Feature%20create%20derived.JPG)

    <span data-ttu-id="23371-148">O recurso adicionado é criado e tem um status **Rascunho**.</span><span class="sxs-lookup"><span data-stu-id="23371-148">The feature that you added is created and has a status of **Draft**.</span></span>

    ![Recurso derivado com status Rascunho](./media/RCS_GlobalF_8%20Feature%20draft%20create.JPG)

7. <span data-ttu-id="23371-150">Revise os componentes do recurso para determinar se as atualizações são necessárias:</span><span class="sxs-lookup"><span data-stu-id="23371-150">Review the feature components to determine whether updates are required:</span></span>

    - <span data-ttu-id="23371-151">Revise as configurações, caso precise personalizar os formatos de Relatório eletrônico (ER) e sua associação com mapeamentos de formato para a versão do recurso.</span><span class="sxs-lookup"><span data-stu-id="23371-151">Review the configurations, in case you need to customize the Electronic reporting (ER) formats and their binding with format mappings for the feature version.</span></span>
    - <span data-ttu-id="23371-152">Revise a configuração caso precise personalizar a guia **Ações**, **Regras de aplicabilidade** ou a guia **Variáveis** para a versão do recurso.</span><span class="sxs-lookup"><span data-stu-id="23371-152">Review the setup, in case you need to customize the **Actions** tab, **Applicability rules** tab, or **Variables** tab for the feature version.</span></span>

8. <span data-ttu-id="23371-153">Na guia **Versões**, selecione uma data **Início da vigência** e digite uma descrição se o campo **Descrição** estiver em branco.</span><span class="sxs-lookup"><span data-stu-id="23371-153">On the **Versions** tab, select an **Effective from** date, and enter a description if the **Description** field is blank.</span></span>
9. <span data-ttu-id="23371-154">Selecione **Alterar status** para concluir o recurso.</span><span class="sxs-lookup"><span data-stu-id="23371-154">Select **Change status** to complete the feature.</span></span> <span data-ttu-id="23371-155">Os recursos completos podem ser disponibilizados para um ambiente específico, de forma que possam ser usados nos serviços de globalização ou podem ser publicados no Repositório global.</span><span class="sxs-lookup"><span data-stu-id="23371-155">Completed features can be made available for a specific environment so that they can be used in Globalization services, or they can be published to the Global repository.</span></span>

> [!NOTE]
> <span data-ttu-id="23371-156">Os recursos com um **Status de versão do recurso** **Publicado** podem ser compartilhados com organizações externas.</span><span class="sxs-lookup"><span data-stu-id="23371-156">Features that have a **Feature version status** value of **Published** can be shared with external organizations.</span></span>

## <a name="add-a-new-globalization-feature"></a><span data-ttu-id="23371-157">Adicionar um novo Recurso de globalização</span><span class="sxs-lookup"><span data-stu-id="23371-157">Add a new Globalization feature</span></span>

<span data-ttu-id="23371-158">Você pode adicionar um novo Recurso de globalização, criando-o do zero.</span><span class="sxs-lookup"><span data-stu-id="23371-158">You can add a new Globalization feature by creating it from scratch.</span></span>

1. <span data-ttu-id="23371-159">Na página **Importar recurso do Repositório global** , selecione **Adicionar** e, na caixa de diálogo suspensa, selecione a opção **Novo recurso**.</span><span class="sxs-lookup"><span data-stu-id="23371-159">On the **Import feature from Global repository** page, select **Add**, and then, in the drop-down dialog box, select the **New feature** option.</span></span>
2. <span data-ttu-id="23371-160">Digite um nome e uma descrição para o recurso.</span><span class="sxs-lookup"><span data-stu-id="23371-160">Enter a name and description for the feature.</span></span>
3. <span data-ttu-id="23371-161">Selecione **Criar recurso**.</span><span class="sxs-lookup"><span data-stu-id="23371-161">Select **Create feature**.</span></span>

    ![Adição de um novo recurso](./media/RCS_GlobalF_9%20Feature%20create%20new.JPG)

4. <span data-ttu-id="23371-163">Na guia **Versões**, selecione uma data **Início da vigência** e, em seguida, selecione **Alterar status** para concluir o recurso.</span><span class="sxs-lookup"><span data-stu-id="23371-163">On the **Versions** tab, select an **Effective from** date, and then select **Change status** to complete the feature.</span></span> <span data-ttu-id="23371-164">Os recursos completos podem ser disponibilizados para um ambiente específico, de forma que possam ser usados nos serviços de globalização ou podem ser publicados no Repositório global.</span><span class="sxs-lookup"><span data-stu-id="23371-164">Completed features can be made available for a specific environment so that they can be used in Globalization services, or they can be published to the Global repository.</span></span>

> [!NOTE]
> <span data-ttu-id="23371-165">Os recursos com um **Status de versão do recurso** **Publicado** podem ser compartilhados com organizações externas.</span><span class="sxs-lookup"><span data-stu-id="23371-165">Features that have a **Feature version status** value of **Published** can be shared with external organizations.</span></span>

## <a name="feature-component-overview"></a><span data-ttu-id="23371-166">Visão geral do componente de recurso</span><span class="sxs-lookup"><span data-stu-id="23371-166">Feature component overview</span></span>

<span data-ttu-id="23371-167">Os recursos de globalização têm vários componentes:</span><span class="sxs-lookup"><span data-stu-id="23371-167">Globalization features have several components:</span></span>

- <span data-ttu-id="23371-168">**Versão** – esse componente oferece suporte ao gerenciamento de ciclo de vida de recursos e permite que os usuários gerenciem o status de versões diferentes do recurso.</span><span class="sxs-lookup"><span data-stu-id="23371-168">**Version** – This component supports feature lifecycle management and lets users manage the status for different versions of the feature.</span></span>
- <span data-ttu-id="23371-169">**Configurações** – esse componente permite que os usuários gerenciem, exibam e editem formatos de ER e mapeamentos de formato relacionados.</span><span class="sxs-lookup"><span data-stu-id="23371-169">**Configurations** – This component lets users manage, view, and edit related ER formats and format mappings.</span></span>
- <span data-ttu-id="23371-170">**Configurações** – esse componente permite que os usuários dos Serviços de globalização, como um serviço de faturamento eletrônica, gerenciem a configuração da versão do recurso relacionado.</span><span class="sxs-lookup"><span data-stu-id="23371-170">**Setups** – This component lets users of Globalization services, such as an e-invoicing service, manage the setup of the related feature version.</span></span> <span data-ttu-id="23371-171">Portanto, ele oferece suporte à construção flexível de regras de comunicação e respostas.</span><span class="sxs-lookup"><span data-stu-id="23371-171">Therefore, it supports the flexible construction of communication and responses rules.</span></span>
- <span data-ttu-id="23371-172">**Ambiente** – esse componente permite que os usuários dos serviços de globalização, como um serviço de faturamento eletrônico, gerenciem o ambiente no qual a configuração da versão do recurso é usada e conceda autorização aos usuários que terão acesso a ele.</span><span class="sxs-lookup"><span data-stu-id="23371-172">**Environment** – This component lets users of Globalization services, such as an e-invoicing service, manage the environment where the feature version setup is used and grant authorization to the users who will have access to it.</span></span>
- <span data-ttu-id="23371-173">**Organizações** – esse componente permite que os usuários compartilhem o recurso com organizações externas.</span><span class="sxs-lookup"><span data-stu-id="23371-173">**Organizations** – This component lets users to share the feature with external organizations.</span></span>

## <a name="configuring-feature-components"></a><span data-ttu-id="23371-174">Como configurar componentes de recursos</span><span class="sxs-lookup"><span data-stu-id="23371-174">Configuring feature components</span></span>

### <a name="version-and-status"></a><span data-ttu-id="23371-175">Versão e status</span><span class="sxs-lookup"><span data-stu-id="23371-175">Version and status</span></span>

<span data-ttu-id="23371-176">A versão é usada para gerenciar o ciclo de vida do Recurso de globalização.</span><span class="sxs-lookup"><span data-stu-id="23371-176">The version is used to manage the Globalization feature lifecycle.</span></span>

<span data-ttu-id="23371-177">O status pode ser alterado no campo **Status** na guia **Versão**. Os seguintes status estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="23371-177">The status can be changed in the **Status** field on the **Version** tab. The following statuses are available:</span></span>

- <span data-ttu-id="23371-178">**Rascunho** – o recurso só poderá ser editado quando estiver com esse status.</span><span class="sxs-lookup"><span data-stu-id="23371-178">**Draft** – The feature can be edited only when it's in this status.</span></span>
- <span data-ttu-id="23371-179">**Concluído** – o recurso e todos os componentes relacionados foram finalizados (concluídos) e não podem ser editados.</span><span class="sxs-lookup"><span data-stu-id="23371-179">**Complete** – The feature and all related components have been finalized (completed) and can't be edited.</span></span>
- <span data-ttu-id="23371-180">**Publicado** – o recurso e todos os componentes relacionados foram publicados no Repositório global.</span><span class="sxs-lookup"><span data-stu-id="23371-180">**Published** – The feature and all related components have been published to the Global repository.</span></span>
- <span data-ttu-id="23371-181">**Compartilhado** – o recurso e todos os componentes relacionados foram compartilhados com organizações externas.</span><span class="sxs-lookup"><span data-stu-id="23371-181">**Shared** – The feature and all related components have been shared with external organizations.</span></span>
- <span data-ttu-id="23371-182">**Habilitado** – o recurso e todos os componentes relacionados foram habilitados para uso em um Serviço de globalização, por exemplo, um serviço de faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="23371-182">**Enabled** – The feature and all related components have been enabled for use in a Globalization service, such as an e-invoicing service.</span></span>

> [!NOTE]
> <span data-ttu-id="23371-183">Os recursos devem ser movidos sequencialmente por alguns desses status.</span><span class="sxs-lookup"><span data-stu-id="23371-183">Features must move sequentially through some of these statuses.</span></span> <span data-ttu-id="23371-184">Portanto, nem todo status pode estar disponível em todos os estágios do ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="23371-184">Therefore, not every status might be available at every lifecycle stage.</span></span>

### <a name="configurations"></a><span data-ttu-id="23371-185">Configurações</span><span class="sxs-lookup"><span data-stu-id="23371-185">Configurations</span></span>

<span data-ttu-id="23371-186">As ações a seguir estão disponíveis para configurações:</span><span class="sxs-lookup"><span data-stu-id="23371-186">The following actions are available for configurations:</span></span>

- <span data-ttu-id="23371-187">**Exibir** – exiba as configurações de recursos subjacentes que não exigem atualização.</span><span class="sxs-lookup"><span data-stu-id="23371-187">**View** – View the underlying feature configurations that don't require any update.</span></span>
- <span data-ttu-id="23371-188">**Editar** – cria uma versão de rascunho de uma configuração selecionada para que você possa editar o formato ou o mapeamento de formato no Designer de formatação.</span><span class="sxs-lookup"><span data-stu-id="23371-188">**Edit** – Create a draft version of a selected configuration so that you can edit the format or format mapping in the Format designer.</span></span>
- <span data-ttu-id="23371-189">**Excluir** – exclui uma configuração selecionada do recurso.</span><span class="sxs-lookup"><span data-stu-id="23371-189">**Delete** – Delete a selected configuration from the feature.</span></span>
- <span data-ttu-id="23371-190">**Alterar base** – baseie o recurso novamente.</span><span class="sxs-lookup"><span data-stu-id="23371-190">**Rebase** – Rebase the feature.</span></span> <span data-ttu-id="23371-191">Para obter mais informações, consulte a seção [Trocar base de Recursos de globalização derivados](#rebase) posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="23371-191">For more information, see the [Rebase derived Globalization features](#rebase) section later in this topic.</span></span>

### <a name="setups"></a><span data-ttu-id="23371-192">Configurações</span><span class="sxs-lookup"><span data-stu-id="23371-192">Setups</span></span>

<span data-ttu-id="23371-193">As ações a seguir estão disponíveis para configurações de recurso:</span><span class="sxs-lookup"><span data-stu-id="23371-193">The following actions are available for feature setups:</span></span>

- <span data-ttu-id="23371-194">**Adicionar** – crie uma nova configuração de recurso.</span><span class="sxs-lookup"><span data-stu-id="23371-194">**Add** – Create a new feature setup.</span></span> <span data-ttu-id="23371-195">Essa configuração de recurso pode ser derivada de uma configuração de recurso existente ou criada do zero.</span><span class="sxs-lookup"><span data-stu-id="23371-195">This feature setup can be derived from an existing feature setup or created from scratch.</span></span>
- <span data-ttu-id="23371-196">**Excluir** – exclui uma configuração de recurso selecionada.</span><span class="sxs-lookup"><span data-stu-id="23371-196">**Delete** – Delete a selected feature setup.</span></span>
- <span data-ttu-id="23371-197">**Exibir** – exibe uma configuração de recurso subjacente que não exige alterações.</span><span class="sxs-lookup"><span data-stu-id="23371-197">**View** – View an underlying feature setup that doesn't require any changes.</span></span>
- <span data-ttu-id="23371-198">**Editar** – crie, exclua ou modifique os atributos dos três componentes principais de uma configuração de recurso:</span><span class="sxs-lookup"><span data-stu-id="23371-198">**Edit** – Create, delete, or modify the attributes of the three main components of a feature setup:</span></span>

    - <span data-ttu-id="23371-199">Ações e seus parâmetros</span><span class="sxs-lookup"><span data-stu-id="23371-199">Actions and their parameters</span></span>
    - <span data-ttu-id="23371-200">Regras de aplicabilidade</span><span class="sxs-lookup"><span data-stu-id="23371-200">Applicability rules</span></span>
    - <span data-ttu-id="23371-201">Variáveis</span><span class="sxs-lookup"><span data-stu-id="23371-201">Variables</span></span>

![Página Configuração da versão do recurso](./media/RCS_GlobalF_10%20Feature%20set%20up.JPG)

### <a name="environments"></a><span data-ttu-id="23371-203">Ambientes</span><span class="sxs-lookup"><span data-stu-id="23371-203">Environments</span></span>

<span data-ttu-id="23371-204">As ações a seguir estão disponíveis para ambientes:</span><span class="sxs-lookup"><span data-stu-id="23371-204">The following actions are available for environments:</span></span>

- <span data-ttu-id="23371-205">**Habilitar** – para uma versão do recurso selecionada, selecione um ambiente publicado e selecione uma data **Início da vigência** quando ela deverá estar disponível.</span><span class="sxs-lookup"><span data-stu-id="23371-205">**Enable** – For a selected feature version, select a published environment, and select an **Effective from** date when it should be available.</span></span> <span data-ttu-id="23371-206">Para obter mais informações, consulte a seção [Configurar ambientes para habilitação](#configureenvironment) posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="23371-206">For more information, see the [Configure environments for enablement](#configureenvironment) section later in this topic.</span></span>
- <span data-ttu-id="23371-207">**Cancelar** – remova um ambiente para uma configuração de recurso.</span><span class="sxs-lookup"><span data-stu-id="23371-207">**Cancel** – Remove an environment for a feature setup.</span></span>

### <a name="organizations"></a><span data-ttu-id="23371-208">Organizações</span><span class="sxs-lookup"><span data-stu-id="23371-208">Organizations</span></span>

<span data-ttu-id="23371-209">Siga estas etapas para compartilhar um Recurso de globalização com uma organização externa.</span><span class="sxs-lookup"><span data-stu-id="23371-209">Follow these steps to share a Globalization feature with an external organization.</span></span>

1. <span data-ttu-id="23371-210">Na página **Recursos de faturamento eletrônico**, selecione o recurso e a versão do recurso a serem compartilhados.</span><span class="sxs-lookup"><span data-stu-id="23371-210">On the **e-Invoicing features** page, select the feature and the feature version to share.</span></span>
2. <span data-ttu-id="23371-211">Na guia **Organizações**, selecione **Compartilhar com** e, na caixa de diálogo suspensa, insira o nome de domínio da organização.</span><span class="sxs-lookup"><span data-stu-id="23371-211">On the **Organizations** tab, select **Share with**, and then, in the drop-down dialog box, enter the organization's domain name.</span></span>
3. <span data-ttu-id="23371-212">Selecione **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="23371-212">Select **Share**.</span></span>

    ![Compartilhamento de um recurso com uma organização](./media/RCS_GlobalF_20%20Feature%20orgn_share%20with.JPG)

<span data-ttu-id="23371-214">O recurso é compartilhado com a organização selecionada e está disponível para essa organização no Repositório global.</span><span class="sxs-lookup"><span data-stu-id="23371-214">The feature is shared with the selected organization and is available for that organization in the Global repository.</span></span> <span data-ttu-id="23371-215">A partir daí, o recurso pode ser importado para a instância da organização do RCS ou do Dynamics 365 Finance para que possa ser usado.</span><span class="sxs-lookup"><span data-stu-id="23371-215">From there, the feature can be imported into the organization's instance of RCS or Dynamics 365 Finance so that it can be used.</span></span>

## <a name="rebase-derived-globalization-features"></a><a name="rebase"></a><span data-ttu-id="23371-216">Trocar base de Recursos de globalização derivados</span><span class="sxs-lookup"><span data-stu-id="23371-216">Rebase derived Globalization features</span></span>

<span data-ttu-id="23371-217">Você pode alterar a base de um Recurso de globalização derivado para a versão do recurso base nova ou atualizada.</span><span class="sxs-lookup"><span data-stu-id="23371-217">You can rebase a derived Globalization feature to the new or updated base feature version.</span></span> <span data-ttu-id="23371-218">Dessa forma, as alterações ocorridas na versão base podem ser atualizadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="23371-218">In this way, changes that have occurred in the base version can be automatically updated.</span></span> <span data-ttu-id="23371-219">A versão do recurso base atualizada é criada pelo provedor de configuração original e, em seguida, é publicada ou compartilhada.</span><span class="sxs-lookup"><span data-stu-id="23371-219">The updated base feature version is created by the originating configuration provider, and it's then published or shared.</span></span>

![Versão do recurso de base atualizada](./media/RCS_GlobalF_12%20Feature%20new%20version.JPG)

<span data-ttu-id="23371-221">Por exemplo, se desejar alterar a base da versão derivada de um recurso criado, você primeiro obterá a versão mais recente do recurso importando-a do repositório global.</span><span class="sxs-lookup"><span data-stu-id="23371-221">For example, if you want to rebase the derived version of a feature that you created, you first get the latest version of the feature by importing it from the Global repository.</span></span>

1. <span data-ttu-id="23371-222">Na página **Recursos de faturamento eletrônico**, selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="23371-222">On the **e-Invoicing features** page, select **Import**.</span></span>
2. <span data-ttu-id="23371-223">Selecione **Sincronizar** para obter os recursos mais recentes.</span><span class="sxs-lookup"><span data-stu-id="23371-223">Select **Synchronize** to get the latest features.</span></span>
3. <span data-ttu-id="23371-224">Na lista de recursos, selecione os recursos a serem importados e, em seguida, selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="23371-224">In the list of features, select the features to import, and then select **Import**.</span></span>

    ![Importação da versão mais recente de um recurso](./media/RCS_GlobalF_13%20Feature%20new%20version%20import.JPG)

4. <span data-ttu-id="23371-226">Na lista de recursos, selecione o recurso a ter a base trocada.</span><span class="sxs-lookup"><span data-stu-id="23371-226">In the list of features, select the feature to rebase.</span></span>
5. <span data-ttu-id="23371-227">Na guia **Versão**, selecione **Nova** para criar uma versão de rascunho.</span><span class="sxs-lookup"><span data-stu-id="23371-227">On the **Version** tab, select **New** to create a draft version.</span></span>

    ![Nova versão de rascunho criada](./media/RCS_GlobalF_14%20Feature%20new%20base%20version.JPG)

6. <span data-ttu-id="23371-229">Selecione **Trocar base**.</span><span class="sxs-lookup"><span data-stu-id="23371-229">Select **Rebase**.</span></span>
7. <span data-ttu-id="23371-230">Na caixa de diálogo **Trocar base**, selecione a última versão do recurso para o qual a base será trocada.</span><span class="sxs-lookup"><span data-stu-id="23371-230">In the **Rebase** dialog box, select the latest version of the feature to rebase to.</span></span>

    ![Caixa de diálogo Trocar base](./media/RCS_GlobalF_15%20Feature%20rebase%20version.JPG)

8. <span data-ttu-id="23371-232">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="23371-232">Select **OK**.</span></span>
9. <span data-ttu-id="23371-233">Revise os componentes do recurso e faça as alterações necessárias.</span><span class="sxs-lookup"><span data-stu-id="23371-233">Review the feature components, and make any changes that are required.</span></span>
10. <span data-ttu-id="23371-234">Selecione **Alterar status** para concluir o recurso com a base trocada.</span><span class="sxs-lookup"><span data-stu-id="23371-234">Select **Change status** to complete the rebased feature.</span></span> <span data-ttu-id="23371-235">Quando a troca de base é concluída, você pode executar ações adicionais.</span><span class="sxs-lookup"><span data-stu-id="23371-235">When the rebase is completed, you can perform additional actions.</span></span> <span data-ttu-id="23371-236">Por exemplo, você pode publicar o recurso e torná-lo disponível para uso nos Serviços de globalização.</span><span class="sxs-lookup"><span data-stu-id="23371-236">For example, you can publish the feature and make it available for use in Globalization services.</span></span>

    ![Status do recurso atualizado para Concluído](./media/RCS_GlobalF_16%20Feature%20rebase%20version%20complete.JPG)

## <a name="configure-environments-for-globalization-features"></a><a name="configureenvironment"></a><span data-ttu-id="23371-238">Configurar ambientes para Recursos de globalização</span><span class="sxs-lookup"><span data-stu-id="23371-238">Configure environments for Globalization features</span></span>

<span data-ttu-id="23371-239">Os usuários dos Serviços de globalização podem gerenciar o ambiente para configurar um Recurso de globalização e conceder autorização a outros usuários que terão acesso a ele.</span><span class="sxs-lookup"><span data-stu-id="23371-239">Users of Globalization services can manage the environment to set up a Globalization feature and grant authorization to other users who will have access to it.</span></span>

1. <span data-ttu-id="23371-240">No espaço de trabalho **Recursos de Globalização** e, em seguida, em **Ambientes**, selecione o bloco **Faturamento eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="23371-240">In the **Globalization Features** workspace, under **Environments**, select the **e-Invoicing** tile.</span></span>

    ![Espaço de trabalho Recursos de Globalização](./media/RCS_GlobalF_17%20Feature%20environment.JPG)

2. <span data-ttu-id="23371-242">Selecione **Parâmetros de de Key Vault** e, em seguida, selecione **Novo** para criar um segredo do Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="23371-242">Select **Key Vault parameters**, and then select **New** to create an Azure Key Vault secret.</span></span>
3. <span data-ttu-id="23371-243">Insira um nome e uma descrição para o key vault e, em seguida, no campo **URI do Key Vault**, insira a URL que identifica o recurso Key Vault no Azure.</span><span class="sxs-lookup"><span data-stu-id="23371-243">Enter a name and description for the key vault, and then, in the **Key Vault URI** field, enter the URL that identifies the Key Vault resource in Azure.</span></span>
4. <span data-ttu-id="23371-244">Na Guia Rápida **Certificados**, selecione **Adicionar** para adicionar o certificado e insira um nome e uma descrição para cada certificado.</span><span class="sxs-lookup"><span data-stu-id="23371-244">On the **Certificates** FastTab, select **Add** to add the certificate, and enter a name and description for each certificate.</span></span>

    ![Certificado adicionado](./media/RCS_GlobalF_18%20Feature%20envn%20key%20vault%20parameter.JPG)

5. <span data-ttu-id="23371-246">Selecione **Novo** para criar um novo ambiente.</span><span class="sxs-lookup"><span data-stu-id="23371-246">Select **New** to create a new environment.</span></span>
6. <span data-ttu-id="23371-247">Digite um nome, uma descrição e o segredo do token de assinatura de acesso compartilhado necessário para o armazenamento.</span><span class="sxs-lookup"><span data-stu-id="23371-247">Enter a name, a description, and the shared access signature token secret required for the storage.</span></span>
7. <span data-ttu-id="23371-248">Na Guia Rápida **Usuários**, selecione **Novo** para adicionar um usuário que terá permissão para acessar esse ambiente.</span><span class="sxs-lookup"><span data-stu-id="23371-248">On the **Users** FastTab, select **New** to add a user who will have permission to access this environment.</span></span>
8. <span data-ttu-id="23371-249">Insira a ID de usuário e o endereço de email do usuário.</span><span class="sxs-lookup"><span data-stu-id="23371-249">Enter the user's user ID and email address.</span></span>
9. <span data-ttu-id="23371-250">Repita as etapas 7 e 8 para adicionar mais usuários.</span><span class="sxs-lookup"><span data-stu-id="23371-250">Repeat steps 7 and 8 to add more users.</span></span>
10. <span data-ttu-id="23371-251">Selecione **Publicar** para publicar o ambiente.</span><span class="sxs-lookup"><span data-stu-id="23371-251">Select **Publish** to publish the environment.</span></span>

    ![Ambiente publicado](./media/RCS_GlobalF_19%20Feature%20envn%20publishing.JPG)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]