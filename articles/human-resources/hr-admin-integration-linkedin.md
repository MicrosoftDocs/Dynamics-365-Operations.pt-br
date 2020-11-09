---
title: Integrar com o LinkedIn Talent Hub
description: Este tópico explica como configurar a integração entre o Microsoft Dynamics 365 Human Resources e o LinkedIn Talent Hub.
author: jaredha
manager: tfehr
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e82b79858060f31a6310cc5abdb2faf87db2d6c2
ms.sourcegitcommit: 765056b5dc1d0a8c27e56ff2cbd310ad3349ff09
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2020
ms.locfileid: "4056088"
---
# <a name="integrate-with-linkedin-talent-hub"></a><span data-ttu-id="318c9-103">Integrar com o LinkedIn Talent Hub</span><span class="sxs-lookup"><span data-stu-id="318c9-103">Integrate with LinkedIn Talent Hub</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="318c9-104">[LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub) é uma plataforma do sistema de acompanhamento de candidatos (ATS).</span><span class="sxs-lookup"><span data-stu-id="318c9-104">[LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub) is an applicant tracking system (ATS) platform.</span></span> <span data-ttu-id="318c9-105">Ele permite que você forneça, gerencie e contrate funcionários em um único local.</span><span class="sxs-lookup"><span data-stu-id="318c9-105">It lets you source, manage, and hire employees all in one place.</span></span> <span data-ttu-id="318c9-106">Ao integrar o Microsoft Dynamics 365 Human Resources ao LinkedIn Talent Hub, você pode criar registros de funcionários com facilidade no Human Resources para candidatos que foram contratados para uma posição.</span><span class="sxs-lookup"><span data-stu-id="318c9-106">By integrating Microsoft Dynamics 365 Human Resources with LinkedIn Talent Hub, you can easily create employee records in Human Resources for applicants who have been hired for a position.</span></span>

## <a name="setup"></a><span data-ttu-id="318c9-107">Configurar</span><span class="sxs-lookup"><span data-stu-id="318c9-107">Setup</span></span>

<span data-ttu-id="318c9-108">Um administrador do sistema deve concluir as tarefas de configuração para habilitar a integração com o LinkedIn Talent Hub.</span><span class="sxs-lookup"><span data-stu-id="318c9-108">A system administrator must complete setup tasks to enable integration with LinkedIn Talent Hub.</span></span> <span data-ttu-id="318c9-109">Primeiro, no ambiente do Power Apps, você deve configurar um usuário e uma função de segurança para conceder as permissões apropriadas ao LinkedIn Talent Hub para gravar dados no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="318c9-109">First, in the Power Apps environment, you must set up a user and security role to grant LinkedIn Talent Hub the appropriate permissions to write data into Human Resources.</span></span>

### <a name="link-your-environment-to-linkedin-talent-hub"></a><span data-ttu-id="318c9-110">Vincular seu ambiente ao LinkedIn Talent Hub</span><span class="sxs-lookup"><span data-stu-id="318c9-110">Link your environment to LinkedIn Talent Hub</span></span>

1. <span data-ttu-id="318c9-111">Abra o [LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub).</span><span class="sxs-lookup"><span data-stu-id="318c9-111">Open [LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub).</span></span>

2. <span data-ttu-id="318c9-112">No menu suspenso do usuário, selecione **Configurações do Produto**.</span><span class="sxs-lookup"><span data-stu-id="318c9-112">On the user drop-down menu, select **Product Settings**.</span></span>

3. <span data-ttu-id="318c9-113">No painel de navegação esquerdo, na seção **Avançado** , selecione **Integrações**.</span><span class="sxs-lookup"><span data-stu-id="318c9-113">In the left navigation pane, in the **Advanced** section, select **Integrations**.</span></span>

4. <span data-ttu-id="318c9-114">Selecione **Autorizar** para a integração do Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="318c9-114">Select **Authorize** for the Microsoft Dynamics 365 Human Resources integration.</span></span>

5. <span data-ttu-id="318c9-115">Na página **Dynamics 365 Human Resources** , selecione o ambiente ao qual vincular o LinkedIn Talent Hub e, em seguida, selecione **Vincular**.</span><span class="sxs-lookup"><span data-stu-id="318c9-115">On the **Dynamics 365 Human Resources** page, select the environment to link LinkedIn Talent Hub to, and then select **Link**.</span></span>

    ![Integração do LinkedIn Talent Hub](./media/hr-admin-integration-talent-hub-onboarding.jpg)

    > [!NOTE]
    > <span data-ttu-id="318c9-117">Você pode vincular somente a ambientes nos quais sua conta de usuário tenha acesso de administrador ao ambiente do Human Resources e ao ambiente do Power Apps associado.</span><span class="sxs-lookup"><span data-stu-id="318c9-117">You can link only to environments where your user account has administrator access to both the Human Resources environment and the associated Power Apps environment.</span></span> <span data-ttu-id="318c9-118">Se nenhum ambiente estiver listado na página Link do Human Resources, verifique se você tem ambientes licenciados do Human Resources no locatário e se o usuário que entrou na página de vinculação tem permissões de administrador para o ambiente do Human Resources e o ambiente do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="318c9-118">If no environments are listed on the Human Resources link page, make sure that you have licensed Human Resources environments on the tenant, and that the user that you signed in to the link page as has administrator permissions to both the Human Resources environment and the Power Apps environment.</span></span>

### <a name="create-a-power-apps-security-role"></a><span data-ttu-id="318c9-119">Criar uma função de segurança do Power Apps</span><span class="sxs-lookup"><span data-stu-id="318c9-119">Create a Power Apps security role</span></span>

1. <span data-ttu-id="318c9-120">Abra o [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="318c9-120">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="318c9-121">Na lista de **Ambientes** , selecione o ambiente associado ao ambiente do Human Resources ao qual você deseja vincular sua instância do LinkedIn Talent Hub.</span><span class="sxs-lookup"><span data-stu-id="318c9-121">In the **Environments** list, select the environment that is associated with the Human Resources environment that you want to link your instance of LinkedIn Talent Hub to.</span></span>

3. <span data-ttu-id="318c9-122">Selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="318c9-122">Select **Settings**.</span></span>

4. <span data-ttu-id="318c9-123">Expanda o nó **Usuários + Permissões** e selecione **Funções de Segurança**.</span><span class="sxs-lookup"><span data-stu-id="318c9-123">Expand the **Users + Permissions** node, and select **Security Roles**.</span></span>

5. <span data-ttu-id="318c9-124">Na página **Funções de Segurança** , na barra de ferramentas, selecione **Nova função**.</span><span class="sxs-lookup"><span data-stu-id="318c9-124">On the **Security Roles** page, on the toolbar, select **New role**.</span></span>

6. <span data-ttu-id="318c9-125">Na guia **Detalhes** , insira um nome para a função, como **Integração LinkedIn Talent Hub HRIS**.</span><span class="sxs-lookup"><span data-stu-id="318c9-125">On the **Details** tab, enter a name for the role, such as **LinkedIn Talent Hub HRIS Integration**.</span></span>

7. <span data-ttu-id="318c9-126">Na guia **Personalização** , selecione a permissão **Leitura** no nível da organização para as seguintes entidades:</span><span class="sxs-lookup"><span data-stu-id="318c9-126">On the **Customization** tab, select organization-level **Read** permission for the following entities:</span></span>

    - <span data-ttu-id="318c9-127">Entidade</span><span class="sxs-lookup"><span data-stu-id="318c9-127">Entity</span></span>
    - <span data-ttu-id="318c9-128">Campo</span><span class="sxs-lookup"><span data-stu-id="318c9-128">Field</span></span>
    - <span data-ttu-id="318c9-129">Relacionamento</span><span class="sxs-lookup"><span data-stu-id="318c9-129">Relationship</span></span>

8. <span data-ttu-id="318c9-130">Salve e feche a função de segurança.</span><span class="sxs-lookup"><span data-stu-id="318c9-130">Save and close the security role.</span></span>

### <a name="create-a-power-apps-application-user"></a><span data-ttu-id="318c9-131">Criar um usuário de aplicativo do Power Apps</span><span class="sxs-lookup"><span data-stu-id="318c9-131">Create a Power Apps application user</span></span>

<span data-ttu-id="318c9-132">Um usuário de aplicativo deve ser criado para o adaptador do LinkedIn Talent Hub a fim de conceder permissões ao adaptador para gravar registros de candidato no ambiente do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="318c9-132">An application user must be created for the LinkedIn Talent Hub adapter to grant permissions to the adapter to write candidate records into the Power Apps environment.</span></span>

1. <span data-ttu-id="318c9-133">Abra o [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="318c9-133">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="318c9-134">Na lista de **Ambientes** , selecione o ambiente associado ao ambiente do Human Resources ao qual você deseja vincular sua instância do LinkedIn Talent Hub.</span><span class="sxs-lookup"><span data-stu-id="318c9-134">In the **Environments** list, select the environment that is associated with the Human Resources environment that you want to link your instance of LinkedIn Talent Hub to.</span></span>

3. <span data-ttu-id="318c9-135">Selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="318c9-135">Select **Settings**.</span></span>

4. <span data-ttu-id="318c9-136">Expanda o nó **Usuários + Permissões** e selecione **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="318c9-136">Expand the **Users + Permissions** node, and select **Users**.</span></span>

5. <span data-ttu-id="318c9-137">Selecione **Gerenciar usuários no Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="318c9-137">Select **Manage users in Dynamics 365**.</span></span>

6. <span data-ttu-id="318c9-138">Use o menu suspenso acima da lista para alterar a exibição do padrão **Usuários Habilitados** para **Usuários do Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="318c9-138">Use the drop-down menu above the list to change the view from the default **Enabled Users** view to **Application Users**.</span></span>

    ![Exibição Usuários do Aplicativo](./media/hr-admin-integration-power-apps-application-users.jpg)

7. <span data-ttu-id="318c9-140">Na barra de ferramentas, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="318c9-140">On the toolbar, select **New**.</span></span>

8. <span data-ttu-id="318c9-141">Na página **Novo usuário** , siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="318c9-141">On the **New user** page, follow these steps:</span></span>

    1. <span data-ttu-id="318c9-142">Altere o valor do campo **Tipo de usuário** para **Usuário de Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="318c9-142">Change the value of the **User type** field to **Application User**.</span></span>
    2. <span data-ttu-id="318c9-143">Defina o campo **Nome do Usuário** como **Integração Dynamics365 HR LinkedIn HRIS**.</span><span class="sxs-lookup"><span data-stu-id="318c9-143">Set the **User Name** field to **Dynamics365 HR LinkedIn HRIS Integration**.</span></span>
    3. <span data-ttu-id="318c9-144">Defina o campo **ID do Aplicativo** como **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span><span class="sxs-lookup"><span data-stu-id="318c9-144">Set the **Application ID** field to **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span></span>
    4. <span data-ttu-id="318c9-145">Insira qualquer valor nos campos **Nome** , **Sobrenome** e **Email Principal**.</span><span class="sxs-lookup"><span data-stu-id="318c9-145">Enter any value in the **First Name** , **Last Name** , and **Primary Email** fields.</span></span>
    5. <span data-ttu-id="318c9-146">Na barra de ferramentas, selecione **Salvar \& Fechar**.</span><span class="sxs-lookup"><span data-stu-id="318c9-146">On the toolbar, select **Save \& Close**.</span></span>

### <a name="assign-a-security-role-to-the-new-user"></a><span data-ttu-id="318c9-147">Atribuir uma função de segurança a um usuário novo</span><span class="sxs-lookup"><span data-stu-id="318c9-147">Assign a security role to the new user</span></span>

<span data-ttu-id="318c9-148">Depois de salvar e fechar o novo usuário do aplicativo na seção anterior, você voltará para a página **Lista de usuários**.</span><span class="sxs-lookup"><span data-stu-id="318c9-148">After you save and close the new application user in the previous section, you're returned to the **Users list** page.</span></span>

1. <span data-ttu-id="318c9-149">Na página **Lista de usuários** , altere a exibição para **Usuários do Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="318c9-149">On the **Users list** page, change the view to **Application Users**.</span></span>

2. <span data-ttu-id="318c9-150">Selecione o usuário do aplicativo criado na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="318c9-150">Select the application user that you created in the previous section.</span></span>

3. <span data-ttu-id="318c9-151">Na barra de ferramentas, selecione **Gerenciar Funções**.</span><span class="sxs-lookup"><span data-stu-id="318c9-151">On the toolbar, select **Manage Roles**.</span></span>

4. <span data-ttu-id="318c9-152">Selecione a função de segurança criada anteriormente para a integração.</span><span class="sxs-lookup"><span data-stu-id="318c9-152">Select the security role that you created earlier for the integration.</span></span>

5. <span data-ttu-id="318c9-153">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="318c9-153">Select **OK**.</span></span>

### <a name="add-an-azure-active-directory-app-in-human-resources"></a><span data-ttu-id="318c9-154">Adicionar um aplicativo do Azure Active Directory ao Human Resources</span><span class="sxs-lookup"><span data-stu-id="318c9-154">Add an Azure Active Directory app in Human Resources</span></span>

1. <span data-ttu-id="318c9-155">No Dynamics 365 Human Resources, abra a página **Aplicativos do Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="318c9-155">In Dynamics 365 Human Resources, open the **Azure Active Directory applications** page.</span></span>
2. <span data-ttu-id="318c9-156">Adicione um novo registro à lista e defina os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="318c9-156">Add a new record to the list, and set the following fields:</span></span>

    - <span data-ttu-id="318c9-157">**ID do Cliente** : insira **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span><span class="sxs-lookup"><span data-stu-id="318c9-157">**Client ID** : Enter **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span></span>
    - <span data-ttu-id="318c9-158">**Nome** : insira o nome da função de segurança do Power Apps que você criou anteriormente, como **Integração LinkedIn Talent Hub HRIS**.</span><span class="sxs-lookup"><span data-stu-id="318c9-158">**Name** : Enter the name of the Power Apps security role that you created earlier, such as **LinkedIn Talent Hub HRIS Integration**.</span></span>
    - <span data-ttu-id="318c9-159">**ID do Usuário** : selecione um usuário que tenha permissões para gravar dados no Gerenciamento de Pessoal.</span><span class="sxs-lookup"><span data-stu-id="318c9-159">**User ID** : Select a user who has permissions to write data in Personnel Management.</span></span>

### <a name="create-the-entity-in-common-data-service"></a><span data-ttu-id="318c9-160">Criar a entidade no Common Data Service</span><span class="sxs-lookup"><span data-stu-id="318c9-160">Create the entity in Common Data Service</span></span>

> [!IMPORTANT]
> <span data-ttu-id="318c9-161">A integração com o LinkedIn Talent Hub depende de entidades virtuais no Common Data Service para Human Resources.</span><span class="sxs-lookup"><span data-stu-id="318c9-161">The integration with LinkedIn Talent Hub depends on virtual entities in Common Data Service for Human Resources.</span></span> <span data-ttu-id="318c9-162">Como um pré-requisito para essa etapa na configuração, você deve configurar as entidades virtuais.</span><span class="sxs-lookup"><span data-stu-id="318c9-162">As a prerequisite for this step in the setup, you must configure virtual entities.</span></span> <span data-ttu-id="318c9-163">Para obter informações sobre como configurar entidades virtuais, consulte [Configurar entidades virtuais do Common Data Service](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).</span><span class="sxs-lookup"><span data-stu-id="318c9-163">For information about how to configure virtual entities, see [Configure Common Data Service virtual entities](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).</span></span>

1. <span data-ttu-id="318c9-164">No Human Resources, abra a página **Integração do Common Data Service (CDS)**.</span><span class="sxs-lookup"><span data-stu-id="318c9-164">In Human Resources, open the **Common Data Service (CDS) integration** page.</span></span>

2. <span data-ttu-id="318c9-165">Selecione a guia **Entidades virtuais**.</span><span class="sxs-lookup"><span data-stu-id="318c9-165">Select the **Virtual entities** tab.</span></span>

3. <span data-ttu-id="318c9-166">Filtre a lista de entidades por etiqueta de entidade para localizar **Candidato exportado do LinkedIn**.</span><span class="sxs-lookup"><span data-stu-id="318c9-166">Filter the entity list by entity label to find **LinkedIn exported candidate**.</span></span>

4. <span data-ttu-id="318c9-167">Selecione a entidade e selecione **Gerar/atualizar**.</span><span class="sxs-lookup"><span data-stu-id="318c9-167">Select the entity, and then select **Generate/refresh**.</span></span>

## <a name="exporting-candidate-records"></a><span data-ttu-id="318c9-168">Exportação de registros de candidato</span><span class="sxs-lookup"><span data-stu-id="318c9-168">Exporting candidate records</span></span>

<span data-ttu-id="318c9-169">Após a conclusão da configuração, os profissionais de recrutamento e recursos humanos (RH) poderão usar a função **Exportar para HRIS** no LinkedIn Talent Hub para exportar registros de candidatos contratados do LinkedIn Talent Hub para o Human Resources.</span><span class="sxs-lookup"><span data-stu-id="318c9-169">After the setup is completed, recruiters and Human resources (HR) professionals can use the **Export to HRIS** function in LinkedIn Talent Hub to export hired candidate records from LinkedIn Talent Hub to Human Resources.</span></span>

### <a name="export-records-from-linkedin-talent-hub"></a><span data-ttu-id="318c9-170">Exportar registros do LinkedIn Talent Hub</span><span class="sxs-lookup"><span data-stu-id="318c9-170">Export records from LinkedIn Talent Hub</span></span>

<span data-ttu-id="318c9-171">Depois que um candidato passar pelo processo de recrutamento e tiver sido contratado, você poderá exportar o registro do candidato do LinkedIn Talent Hub para o Human Resources.</span><span class="sxs-lookup"><span data-stu-id="318c9-171">After a candidate has moved through the recruiting process and has been hired, you can export the candidate record from LinkedIn Talent Hub to Human Resources.</span></span>

1. <span data-ttu-id="318c9-172">No LinkedIn Talent Hub, abra o projeto para o qual você contratou o novo funcionário.</span><span class="sxs-lookup"><span data-stu-id="318c9-172">In LinkedIn Talent Hub, open the project that you hired the new employee for.</span></span>

2. <span data-ttu-id="318c9-173">Selecione um registro de candidato.</span><span class="sxs-lookup"><span data-stu-id="318c9-173">Select a candidate record.</span></span>

3. <span data-ttu-id="318c9-174">Selecione **Alterar estágio** e selecione **Contratado**.</span><span class="sxs-lookup"><span data-stu-id="318c9-174">Select **Change stage** , and then select **Hired**.</span></span>

4. <span data-ttu-id="318c9-175">No menu de reticências ( **...** ) para o candidato, selecione **Exportar para HRIS**.</span><span class="sxs-lookup"><span data-stu-id="318c9-175">On the ellipsis menu ( **...** ) for the candidate, select **Export to HRIS**.</span></span>

5. <span data-ttu-id="318c9-176">No painel **Exportar para HRIS** , insira as informações que devem ser exportadas:</span><span class="sxs-lookup"><span data-stu-id="318c9-176">In the **Export to HRIS** pane, enter the information that must be exported:</span></span>

    - <span data-ttu-id="318c9-177">No campo **Provedor de HRIS** , selecione **Microsoft Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="318c9-177">In the **HRIS provider** field, select **Microsoft Dynamics 365 Human Resources**.</span></span>
    - <span data-ttu-id="318c9-178">No campo **Data de início** , selecione um valor para o novo funcionário.</span><span class="sxs-lookup"><span data-stu-id="318c9-178">In the **Start date** field, select a value for the new employee.</span></span>
    - <span data-ttu-id="318c9-179">No campo **Cargo** , insira um cargo para o trabalho do novo funcionário.</span><span class="sxs-lookup"><span data-stu-id="318c9-179">In the **Job title** field, enter a job title for the new employee's job.</span></span>
    - <span data-ttu-id="318c9-180">No campo **Local** , insira o local em que será a base do funcionário.</span><span class="sxs-lookup"><span data-stu-id="318c9-180">In the **Location** field, enter the location where the employee will be based.</span></span>
    - <span data-ttu-id="318c9-181">Insira ou verifique o endereço de email do funcionário.</span><span class="sxs-lookup"><span data-stu-id="318c9-181">Enter or verify the employee's email address.</span></span>

![Exportar para o painel HRIS no LinkedIn Talent Hub](./media/hr-admin-integration-linkedin-talent-hub-export.jpg)

## <a name="complete-onboarding-in-human-resources"></a><span data-ttu-id="318c9-183">Concluir a integração no Human Resources</span><span class="sxs-lookup"><span data-stu-id="318c9-183">Complete onboarding in Human Resources</span></span>

<span data-ttu-id="318c9-184">Os registros de candidato exportados do LinkedIn Talent Hub para o Human Resources são exibidos na seção **Candidatos a contratar** da página **Gerenciamento de pessoal**.</span><span class="sxs-lookup"><span data-stu-id="318c9-184">Candidate records that are exported from LinkedIn Talent Hub to Human Resources appear in the **Candidates to hire** section of the **Personnel management** page.</span></span>

1. <span data-ttu-id="318c9-185">No Human Resources, abra a página **Gerenciamento de pessoal**.</span><span class="sxs-lookup"><span data-stu-id="318c9-185">In Human Resources, open the **Personnel management** page.</span></span>

2. <span data-ttu-id="318c9-186">Na seção **Candidatos a contratar** , selecione **Contratar** para o candidato selecionado.</span><span class="sxs-lookup"><span data-stu-id="318c9-186">In the **Candidates to hire** section, select **Hire** for the selected candidate.</span></span>

3. <span data-ttu-id="318c9-187">Na caixa de diálogo **Contratar novo trabalhador** , revise o registro e adicione as informações necessárias.</span><span class="sxs-lookup"><span data-stu-id="318c9-187">In the **Hire new worker** dialog box, review the record, and add any required information.</span></span> <span data-ttu-id="318c9-188">Você também pode selecionar o número da posição para a qual o candidato foi contratado.</span><span class="sxs-lookup"><span data-stu-id="318c9-188">You can also select the position number that the candidate has been hired for.</span></span>

<span data-ttu-id="318c9-189">Depois que as informações necessárias tiverem sido inseridas, você poderá continuar com os processos padrão para criar registros de funcionário e integrar os funcionários.</span><span class="sxs-lookup"><span data-stu-id="318c9-189">After the required information has been entered, you can continue with your standard processes for creating employee records and onboarding employees.</span></span>

<span data-ttu-id="318c9-190">Os seguintes detalhes são importados e incluídos no novo registro de funcionário:</span><span class="sxs-lookup"><span data-stu-id="318c9-190">The following details are imported and included on the new employee record:</span></span>

- <span data-ttu-id="318c9-191">Nome</span><span class="sxs-lookup"><span data-stu-id="318c9-191">First name</span></span>
- <span data-ttu-id="318c9-192">Sobrenome</span><span class="sxs-lookup"><span data-stu-id="318c9-192">Last name</span></span>
- <span data-ttu-id="318c9-193">Data de início do emprego</span><span class="sxs-lookup"><span data-stu-id="318c9-193">Employment start date</span></span>
- <span data-ttu-id="318c9-194">Endereço de email</span><span class="sxs-lookup"><span data-stu-id="318c9-194">Email address</span></span>
- <span data-ttu-id="318c9-195">Número de telefone</span><span class="sxs-lookup"><span data-stu-id="318c9-195">Phone number</span></span>

## <a name="see-also"></a><span data-ttu-id="318c9-196">Consulte também</span><span class="sxs-lookup"><span data-stu-id="318c9-196">See also</span></span>

[<span data-ttu-id="318c9-197">Configurar entidades virtuais do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="318c9-197">Configure Common Data Service virtual entities</span></span>](./hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="318c9-198">O que é o Common Data Service?</span><span class="sxs-lookup"><span data-stu-id="318c9-198">What is Common Data Service?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
