---
title: Recrutar candidatos ao trabalho
description: Este tópico mostra como recrutar candidatos no Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 12/03/2020
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
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9a35abcb8a2f6aa8031c8d84a44c2a8ad93883ac
ms.sourcegitcommit: 0354ca7e566fbd2eb0aabdd40000d4ac5c44ea78
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2020
ms.locfileid: "4669153"
---
# <a name="recruit-job-candidates"></a><span data-ttu-id="cc714-103">Recrutar candidatos ao trabalho</span><span class="sxs-lookup"><span data-stu-id="cc714-103">Recruit job candidates</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="cc714-104">O Dynamics 365 Human Resources ajuda a gerenciar solicitações de recrutamento.</span><span class="sxs-lookup"><span data-stu-id="cc714-104">Dynamics 365 Human Resources helps you to manage recruiting requests.</span></span> <span data-ttu-id="cc714-105">Ele também ajuda você a fazer a transição completa de candidatos ao trabalho para funcionários.</span><span class="sxs-lookup"><span data-stu-id="cc714-105">It also helps you seamlessly transition job candidates to employees.</span></span> <span data-ttu-id="cc714-106">Se a sua organização usar um aplicativo de recrutamento separado, o processo de recrutamento poderá incluir as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="cc714-106">If your organization uses a separate recruiting application, your recruiting process might include the following steps:</span></span>

- <span data-ttu-id="cc714-107">Insira sua solicitação de recrutamento no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="cc714-107">Enter your recruiting request in Human Resources.</span></span>
- <span data-ttu-id="cc714-108">Receba indicações de candidatos no Human Resources do aplicativo de recrutamento.</span><span class="sxs-lookup"><span data-stu-id="cc714-108">Receive candidate referrals in Human Resources from the recruiting application.</span></span>
- <span data-ttu-id="cc714-109">Conclua o processo de aprovação de candidatos no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="cc714-109">Complete the candidate approval process in Human Resources.</span></span>

<span data-ttu-id="cc714-110">Se não estiver usando um aplicativo de recrutamento separado, você também poderá gerenciar candidatos manualmente no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="cc714-110">If you aren't using a separate recruiting application, you can also manually manage candidates in Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="cc714-111">Se você for um administrador ou desenvolvedor e quiser integrar o Human Resources com um aplicativo de recrutamento de terceiros, consulte [Configurar integração do Common Data Service](hr-admin-integration-common-data-service.md) e [Configurar entidades virtuais do Common Data Service](hr-admin-integration-common-data-service-virtual-entities.md)</span><span class="sxs-lookup"><span data-stu-id="cc714-111">If you're an admin or developer and want to integrate Human Resources with a third-party recruiting application, see [Configure Common Data Service integration](hr-admin-integration-common-data-service.md) and [Configure Common Data Service virtual entities](hr-admin-integration-common-data-service-virtual-entities.md)</span></span>
>
> <span data-ttu-id="cc714-112">Também é possível encontrar aplicativos de integração de recrutamento no [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics).</span><span class="sxs-lookup"><span data-stu-id="cc714-112">You can also find recruiting integration apps on [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics).</span></span>
>
> <span data-ttu-id="cc714-113">Para testar a versão prévia do recurso para integração com o LinkedIn Talent Hub, consulte [Integrar com o LinkedIn Talent Hub](hr-admin-integration-linkedin.md).</span><span class="sxs-lookup"><span data-stu-id="cc714-113">To try out our preview feature for integrating with LinkedIn Talent Hub, see [Integrate with LinkedIn Talent Hub](hr-admin-integration-linkedin.md).</span></span>

## <a name="enable-recruiting-requests"></a><span data-ttu-id="cc714-114">Habilitar solicitações de recrutamento</span><span class="sxs-lookup"><span data-stu-id="cc714-114">Enable recruiting requests</span></span>

<span data-ttu-id="cc714-115">Se você deseja enviar solicitações de recrutamento no Human Resources, primeiro habilite a funcionalidade em **Parâmetros de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="cc714-115">If you want to submit recruiting requests in Human Resources, you must first enable the functionality in **Human resources parameters**.</span></span>

1. <span data-ttu-id="cc714-116">No espaço de trabalho **Gerenciamento de pessoal**, selecione **Links**.</span><span class="sxs-lookup"><span data-stu-id="cc714-116">In the **Personnel management** workspace, select **Links**.</span></span>

2. <span data-ttu-id="cc714-117">Em **Configuração**, selecione **Parâmetros de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="cc714-117">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="cc714-118">Na guia **Geral**, em **RECRUTAMENTO**, defina **Habilitar solicitações de recrutamento** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="cc714-118">On the **General** tab, under **RECRUITING**, set **Enable recruiting requests** to **Yes**.</span></span>

   ![Habilitar solicitações de recrutamento](./media/hr-recruit-0-enable-requests.png)

## <a name="add-a-recruiting-request-location"></a><span data-ttu-id="cc714-120">Adicionar um local de solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="cc714-120">Add a recruiting request location</span></span>

<span data-ttu-id="cc714-121">Se a sua organização tiver vários locais, você poderá adicioná-los de forma que os solicitantes possam selecionar um local no qual o novo recrutamento funcionará.</span><span class="sxs-lookup"><span data-stu-id="cc714-121">If your organization has multiple locations, you can add them so requestors can select a location where the new recruit will be working.</span></span> <span data-ttu-id="cc714-122">O local será incluído no lançamento do trabalho.</span><span class="sxs-lookup"><span data-stu-id="cc714-122">The location will be included in the job posting.</span></span>

1. <span data-ttu-id="cc714-123">Na barra de pesquisa, insira o **local da solicitação de recrutamento**.</span><span class="sxs-lookup"><span data-stu-id="cc714-123">In the search bar, enter **recruiting request location**.</span></span>

2. <span data-ttu-id="cc714-124">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="cc714-124">Select **New**.</span></span>

3. <span data-ttu-id="cc714-125">No campo **Local da solicitação de recrutamento**, insira o nome do local.</span><span class="sxs-lookup"><span data-stu-id="cc714-125">In the **Recruiting request location** field, enter the location name.</span></span>

   ![Adicionar um local de solicitação de recrutamento](./media/hr-recruit-0a-add-location.png)

4. <span data-ttu-id="cc714-127">No campo **Descrição**, insira uma descrição do local.</span><span class="sxs-lookup"><span data-stu-id="cc714-127">In the **Description**, enter a description for the location.</span></span>

5. <span data-ttu-id="cc714-128">Em **Local**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="cc714-128">Under **Location**, select **Add**.</span></span> <span data-ttu-id="cc714-129">Se o popout **Novo endereço** aparecer, insira o endereço do local.</span><span class="sxs-lookup"><span data-stu-id="cc714-129">If the **New address** popout appears, enter the address for the location.</span></span>

   ![Inserir endereço](./media/hr-recruit-0b-address.png)

6. <span data-ttu-id="cc714-131">Em **Informações de contato**, insira as informações do contato do local.</span><span class="sxs-lookup"><span data-stu-id="cc714-131">Under **Contact information**, enter the information for the location's contact.</span></span>

7. <span data-ttu-id="cc714-132">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cc714-132">Select **Save**.</span></span>

## <a name="add-a-recruiting-request"></a><span data-ttu-id="cc714-133">Adicionar uma solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="cc714-133">Add a recruiting request</span></span>

<span data-ttu-id="cc714-134">Os gerentes podem enviar solicitações de recrutamento no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="cc714-134">Managers can submit recruiting requests in Human Resources.</span></span> <span data-ttu-id="cc714-135">Se você usar um aplicativo de recrutamento separado, ao concluir essas etapas, uma solicitação de recrutamento será enviada e o processo de recrutamento iniciará nesse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="cc714-135">If you use a separate recruiting application, completing these steps will send a recruiting request and start the recruiting process in that application.</span></span> <span data-ttu-id="cc714-136">Caso contrário, conclua esse procedimento para iniciar o fluxo de trabalho para seu próprio processo de recrutamento interno.</span><span class="sxs-lookup"><span data-stu-id="cc714-136">Otherwise, complete this procedure to begin the workflow for your own internal recruiting process.</span></span>

1. <span data-ttu-id="cc714-137">Selecione **Autoatendimento para funcionários**.</span><span class="sxs-lookup"><span data-stu-id="cc714-137">Select **Employee self service**.</span></span>

2. <span data-ttu-id="cc714-138">Selecione a guia **Minha equipe**.</span><span class="sxs-lookup"><span data-stu-id="cc714-138">Select the **My team** tab.</span></span>

3. <span data-ttu-id="cc714-139">Selecione **Solucionar recrutamento**.</span><span class="sxs-lookup"><span data-stu-id="cc714-139">Select  **Request to recruit**.</span></span>

   ![Iniciar uma solicitação de recrutamento](./media/hr-recruit-1-request-to-recruit.png)

4. <span data-ttu-id="cc714-141">Preencha os campos **Descrição**, **Trabalho** e **Data de início estimada**.</span><span class="sxs-lookup"><span data-stu-id="cc714-141">Complete the **Description**, **Job**, and **Estimated start date** fields.</span></span>

   ![Concluir a solicitação de recrutamento](./media/hr-recruit-2-request-to-recruit.png)

5. <span data-ttu-id="cc714-143">Selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="cc714-143">Select **Continue**.</span></span> <span data-ttu-id="cc714-144">A solicitação de recrutamento do seu cargo é exibida.</span><span class="sxs-lookup"><span data-stu-id="cc714-144">The recruiting request for your position appears.</span></span>

6. <span data-ttu-id="cc714-145">Em **Geral**, selecione um recrutador na lista suspensa **Recrutador** e selecione um local no menu suspenso **Localização da solicitação de recrutamento**.</span><span class="sxs-lookup"><span data-stu-id="cc714-145">Under **General**, select a recruiter from the **Recruiter** dropdown, and then select a location from the **Recruiting request location** dropdown.</span></span>

7. <span data-ttu-id="cc714-146">Em **Trabalho**, altere as informações conforme necessário e selecione **Criar detalhes do trabalho**.</span><span class="sxs-lookup"><span data-stu-id="cc714-146">Under **Job**, change any information as needed, and then select **Create details from job**.</span></span>

   ![Criar detalhes do trabalho](./media/hr-recruit-3-create-details-from-job.png)

   <span data-ttu-id="cc714-148">O restante da solicitação de recrutamento será preenchido com as informações padrão para o trabalho inserido.</span><span class="sxs-lookup"><span data-stu-id="cc714-148">The rest of the recruiting request will populate with the default information for the job you entered.</span></span>

8. <span data-ttu-id="cc714-149">Em **Descrição externa**, insira uma descrição de trabalho externa.</span><span class="sxs-lookup"><span data-stu-id="cc714-149">Under **External description**, enter an external-facing job description.</span></span>

9. <span data-ttu-id="cc714-150">Em **Posições**, selecione **Adicionar** e selecione um cargo para essa solicitação de recrutamento.</span><span class="sxs-lookup"><span data-stu-id="cc714-150">Under **Positions**, select **Add**, and then select a position for this recruiting request.</span></span>

   ![Adicionar uma posição](./media/hr-recruit-4-select-position.png)

10. <span data-ttu-id="cc714-152">Em **Habilidades**, selecione **Adicionar** e, depois, uma habilidade.</span><span class="sxs-lookup"><span data-stu-id="cc714-152">Under **Skills**, select **Add**, and then select a skill.</span></span>

11. <span data-ttu-id="cc714-153">Em **Requisitos de formação educacional**, selecione **Adicionar** e, depois, selecione os valores das **Educação** e **Nível de formação educacional**.</span><span class="sxs-lookup"><span data-stu-id="cc714-153">Under **Educational requirements**, select **Add**, and then select values from the **Education** and **Level of education** dropdowns.</span></span>

   ![Adicionar requisitos educacionais](./media/hr-recruit-5-select-educational-requirements.png)

12. <span data-ttu-id="cc714-155">Em **Comentário**, adicione comentários, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="cc714-155">Under **Comment**, add comments as necessary.</span></span>

13. <span data-ttu-id="cc714-156">Em **Remuneração**, selecione um nível no menu suspenso **Nível** e ajuste **Limite baixo**, **Ponto de controle** e **Limite alto**, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="cc714-156">Under **Compensation**, select a level from the **Level** dropdown, and then adjust **Low threshold**, **Control point**, and **High threshold** as necessary.</span></span>

14. <span data-ttu-id="cc714-157">Quando sua solicitação de recrutamento for concluída e você estiver pronto para iniciar o processo de recrutamento, selecione **Ativar** na barra de menus.</span><span class="sxs-lookup"><span data-stu-id="cc714-157">When your recruiting request is complete and you're ready to start the recruiting process, select **Activate** in the menu bar.</span></span>

   ![Ativar solicitação de recrutamento](./media/hr-recruit-6-activate-recruit-request.png)

15. <span data-ttu-id="cc714-159">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cc714-159">Select **Save**.</span></span>

## <a name="view-and-edit-your-recruiting-requests"></a><span data-ttu-id="cc714-160">Exibir e editar solicitações de recrutamento</span><span class="sxs-lookup"><span data-stu-id="cc714-160">View and edit your recruiting requests</span></span>

<span data-ttu-id="cc714-161">Se você for um gerente e desejar exibir suas próprias solicitações:</span><span class="sxs-lookup"><span data-stu-id="cc714-161">If you're a manager and want to view your own requests:</span></span>

1. <span data-ttu-id="cc714-162">Selecione **Autoatendimento para funcionários**.</span><span class="sxs-lookup"><span data-stu-id="cc714-162">Select **Employee self service**.</span></span>

2. <span data-ttu-id="cc714-163">Selecione a guia **Minha equipe**.</span><span class="sxs-lookup"><span data-stu-id="cc714-163">Select the **My team** tab.</span></span>

3. <span data-ttu-id="cc714-164">Em **Informações da minha equipe**, selecione a guia **Solicitações de recrutamento**.</span><span class="sxs-lookup"><span data-stu-id="cc714-164">Under **My team information**, select the **Recruiting requests** tab.</span></span>

   ![Selecionar a guia Solicitações de recrutamento](./media/hr-recruit-7-recruiting-requests.png)

4. <span data-ttu-id="cc714-166">Para exibir ou editar uma solicitação de recrutamento, selecione-a na grade.</span><span class="sxs-lookup"><span data-stu-id="cc714-166">To view or edit a recruiting request, select it in the grid.</span></span>

<span data-ttu-id="cc714-167">Se você for um profissional de RH e quiser exibir todas as solicitações de recrutamento:</span><span class="sxs-lookup"><span data-stu-id="cc714-167">If you're an HR pro and want to view all recruiting requests:</span></span>

1. <span data-ttu-id="cc714-168">Selecione **Gerenciamento de pessoal**.</span><span class="sxs-lookup"><span data-stu-id="cc714-168">Select **Personnel management**.</span></span>

2. <span data-ttu-id="cc714-169">Selecione **Solicitações de recrutamento**.</span><span class="sxs-lookup"><span data-stu-id="cc714-169">Select **Recruiting requests**.</span></span>

   ![Exibir solicitações de recrutamento no Gerenciamento de pessoal](./media/hr-recruit-8-recruiting-requests-personnel-management.png)

3. <span data-ttu-id="cc714-171">Para exibir ou editar uma solicitação de recrutamento, selecione-a na grade.</span><span class="sxs-lookup"><span data-stu-id="cc714-171">To view or edit a recruiting request, select it in the grid.</span></span>

## <a name="add-or-edit-a-candidate-profile"></a><span data-ttu-id="cc714-172">Adicionar ou editar um perfil de candidato</span><span class="sxs-lookup"><span data-stu-id="cc714-172">Add or edit a candidate profile</span></span>

<span data-ttu-id="cc714-173">Se a sua organização se integrou a outro aplicativo para gerenciar solicitações de recrutamento, as solicitações de recrutamento serão encaminhadas para esse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="cc714-173">If your organization has integrated with another application to manage recruiting requests, recruiting requests are forwarded to that application.</span></span> <span data-ttu-id="cc714-174">O aplicativo de recrutamento reenvia informações sobre candidatos para o Human Resources.</span><span class="sxs-lookup"><span data-stu-id="cc714-174">The recruiting application then sends candidate information back to Human Resources.</span></span> <span data-ttu-id="cc714-175">Caso contrário, você poderá seguir seus próprios processos internos de recrutamento e inserir informações sobre os candidatos manualmente.</span><span class="sxs-lookup"><span data-stu-id="cc714-175">Otherwise, you can follow your own internal recruiting processes and enter candidate information manually.</span></span>

1. <span data-ttu-id="cc714-176">Selecione **Gerenciamento de pessoal**.</span><span class="sxs-lookup"><span data-stu-id="cc714-176">Select **Personnel management**.</span></span>

2. <span data-ttu-id="cc714-177">Selecione **Links**.</span><span class="sxs-lookup"><span data-stu-id="cc714-177">Select **Links**.</span></span>

3. <span data-ttu-id="cc714-178">Em **Recrutamento**, selecione **Candidatos**.</span><span class="sxs-lookup"><span data-stu-id="cc714-178">Under **Recruiting**, select **Candidates**.</span></span>

   ![Exibir candidatos](./media/hr-recruit-9-candidates.png)

4. <span data-ttu-id="cc714-180">Para adicionar um candidato, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="cc714-180">To add a candidate, select **New**.</span></span> <span data-ttu-id="cc714-181">Para editar um candidato existente, selecione o candidato na lista e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="cc714-181">To edit an existing candidate, select the candidate from the list and then select **Edit**.</span></span> <span data-ttu-id="cc714-182">O perfil do candidato aparece.</span><span class="sxs-lookup"><span data-stu-id="cc714-182">The candidate profile appears.</span></span>

5. <span data-ttu-id="cc714-183">Em **Resumo de candidatos**, insira ou edite as informações do candidato conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="cc714-183">Under **Candidate summary**, enter or edit the candidate information as necessary.</span></span>

6. <span data-ttu-id="cc714-184">Em **Solicitação de recrutamento**, selecione uma solicitação de recrutamento para vincular o candidato.</span><span class="sxs-lookup"><span data-stu-id="cc714-184">Under **Recruiting request**, select a recruiting request to link the candidate to.</span></span> <span data-ttu-id="cc714-185">Em seguida, preencha os campos **Data de início estimada**, **Gerente de contratação** e **Cargo** e **Descrição**, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="cc714-185">Then complete the **Estimated start date**, **Hiring manager**, **Position**, and **Description fields** as appropriate.</span></span>

   ![Vincular à solicitação de recrutamento](./media/hr-recruit-10-link-to-recruiting-request.png)

7. <span data-ttu-id="cc714-187">Preencha todas as informações nas seguintes áreas a serem incluídas no registro do candidato:</span><span class="sxs-lookup"><span data-stu-id="cc714-187">Complete all the information in the following areas that you want to include in the candidate's record:</span></span>
   - <span data-ttu-id="cc714-188">**Comentários**</span><span class="sxs-lookup"><span data-stu-id="cc714-188">**Comments**</span></span>
   - <span data-ttu-id="cc714-189">**Experiência Profissional**</span><span class="sxs-lookup"><span data-stu-id="cc714-189">**Professional experience**</span></span>
   - <span data-ttu-id="cc714-190">**Informações do contato**</span><span class="sxs-lookup"><span data-stu-id="cc714-190">**Contact information**</span></span>
   - <span data-ttu-id="cc714-191">**Formação**</span><span class="sxs-lookup"><span data-stu-id="cc714-191">**Education**</span></span>
   - <span data-ttu-id="cc714-192">**Habilidades**</span><span class="sxs-lookup"><span data-stu-id="cc714-192">**Skills**</span></span>
   - <span data-ttu-id="cc714-193">**Certificados**</span><span class="sxs-lookup"><span data-stu-id="cc714-193">**Certificates**</span></span>
   - <span data-ttu-id="cc714-194">**Triagens**</span><span class="sxs-lookup"><span data-stu-id="cc714-194">**Screenings**</span></span>

8. <span data-ttu-id="cc714-195">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cc714-195">Select **Save**.</span></span>

## <a name="hire-a-candidate"></a><span data-ttu-id="cc714-196">Contratar um candidato</span><span class="sxs-lookup"><span data-stu-id="cc714-196">Hire a candidate</span></span>

<span data-ttu-id="cc714-197">Quando estiver pronto para contratar um candidato, siga este procedimento para fazer a transição do candidato para um funcionário.</span><span class="sxs-lookup"><span data-stu-id="cc714-197">When you're ready to hire a candidate, follow this procedure to transition the candidate to an employee.</span></span>

1. <span data-ttu-id="cc714-198">No formulário do candidato, selecione **Contratar**.</span><span class="sxs-lookup"><span data-stu-id="cc714-198">On the candidate form, select **Hire**.</span></span>

   ![Contratar um candidato](./media/hr-recruit-11-hire.png)

2. <span data-ttu-id="cc714-200">No formulário **Contratar novo trabalhador**, em **Detalhes**, preencha todos os campos.</span><span class="sxs-lookup"><span data-stu-id="cc714-200">On the **Hire new worker** form, under **Details**, complete all the fields.</span></span>

   ![Inserir detalhes de novos contratados](./media/hr-recruit-12-hire-new-worker.png)

3. <span data-ttu-id="cc714-202">Em **Detalhes do cargo**, verifique e altere as informações conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="cc714-202">Under **Position details**, verify and change information as necessary.</span></span>

4. <span data-ttu-id="cc714-203">Em **Listas de verificação de integração**, selecione as listas de verificação de integração relevantes para este funcionário.</span><span class="sxs-lookup"><span data-stu-id="cc714-203">Under **Onboarding checklists**, select the relevant onboarding checklists for this employee.</span></span>

5. <span data-ttu-id="cc714-204">Selecione **Continuar** para criar o registro de funcionário.</span><span class="sxs-lookup"><span data-stu-id="cc714-204">Select **Continue** to create the employee record.</span></span>

   >[!NOTE]
   ><span data-ttu-id="cc714-205">Dependendo dos fluxos de trabalho da organização, o registro de candidatos pode passar por etapas de aprovação adicionais antes de se tornar um registro de funcionário.</span><span class="sxs-lookup"><span data-stu-id="cc714-205">Depending on your organization's workflows, the candidate record may go through additional approval steps before becoming an employee record.</span></span>

## <a name="decide-not-to-hire-a-candidate"></a><span data-ttu-id="cc714-206">Decidir não contratar um candidato</span><span class="sxs-lookup"><span data-stu-id="cc714-206">Decide not to hire a candidate</span></span>

<span data-ttu-id="cc714-207">Se você optar por não contratar um candidato, siga este procedimento para removê-lo do processo de habilitação.</span><span class="sxs-lookup"><span data-stu-id="cc714-207">If you decide not to hire a candidate, follow this procedure to remove them from the vetting process.</span></span> 

1. <span data-ttu-id="cc714-208">No formulário do candidato, selecione **Não contratar**.</span><span class="sxs-lookup"><span data-stu-id="cc714-208">On the candidate form, select **Do not hire**.</span></span>

   ![Não contratar candidato](./media/hr-recruit-13-do-not-hire.png)

2. <span data-ttu-id="cc714-210">Selecione um **Código de motivo** e inclua comentários.</span><span class="sxs-lookup"><span data-stu-id="cc714-210">Select a **Reason code** and include any comments.</span></span>

3. <span data-ttu-id="cc714-211">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="cc714-211">Select **OK**.</span></span>

## <a name="dismiss-a-candidate"></a><span data-ttu-id="cc714-212">Ignorar um candidato</span><span class="sxs-lookup"><span data-stu-id="cc714-212">Dismiss a candidate</span></span>

<span data-ttu-id="cc714-213">Se necessário, você poderá ignorar um candidato após contratá-lo.</span><span class="sxs-lookup"><span data-stu-id="cc714-213">If needed, you can dismiss a candidate after hiring them.</span></span> <span data-ttu-id="cc714-214">Por exemplo, um candidato pode rejeitar sua oferta ou não aparecer no primeiro dia.</span><span class="sxs-lookup"><span data-stu-id="cc714-214">For example, a candidate might reject your offer or not show up on their first day.</span></span>

- <span data-ttu-id="cc714-215">No formulário do candidato, selecione **Ignorar candidato**.</span><span class="sxs-lookup"><span data-stu-id="cc714-215">On the candidate form, select **Dismiss candidate**.</span></span>

  ![Ignorar candidato](./media/hr-recruit-14-dismiss-candidate.png)

## <a name="see-also"></a><span data-ttu-id="cc714-217">Consulte também</span><span class="sxs-lookup"><span data-stu-id="cc714-217">See also</span></span>

[<span data-ttu-id="cc714-218">Configurar entidades virtuais do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="cc714-218">Configure Common Data Service virtual entities</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="cc714-219">Organizar sua força de trabalho</span><span class="sxs-lookup"><span data-stu-id="cc714-219">Organize your workforce</span></span>](hr-personnel-departments-jobs-positions.md)<br>
[<span data-ttu-id="cc714-220">Configurar os componentes de um trabalho</span><span class="sxs-lookup"><span data-stu-id="cc714-220">Set up the components of a job</span></span>](hr-personnel-jobs.md)