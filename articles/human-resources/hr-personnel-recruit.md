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
ms.openlocfilehash: 6aca285133495dfe023dfd18bdeb050aabcafee6
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478275"
---
# <a name="recruit-job-candidates"></a><span data-ttu-id="ad12b-103">Recrutar candidatos ao trabalho</span><span class="sxs-lookup"><span data-stu-id="ad12b-103">Recruit job candidates</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="ad12b-104">O Dynamics 365 Human Resources ajuda a gerenciar solicitações de recrutamento.</span><span class="sxs-lookup"><span data-stu-id="ad12b-104">Dynamics 365 Human Resources helps you to manage recruiting requests.</span></span> <span data-ttu-id="ad12b-105">Ele também ajuda você a fazer a transição completa de candidatos ao trabalho para funcionários.</span><span class="sxs-lookup"><span data-stu-id="ad12b-105">It also helps you seamlessly transition job candidates to employees.</span></span> <span data-ttu-id="ad12b-106">Se a sua organização usar um aplicativo de recrutamento separado, o processo de recrutamento poderá incluir as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="ad12b-106">If your organization uses a separate recruiting application, your recruiting process might include the following steps:</span></span>

- <span data-ttu-id="ad12b-107">Insira sua solicitação de recrutamento no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="ad12b-107">Enter your recruiting request in Human Resources.</span></span>
- <span data-ttu-id="ad12b-108">Receba indicações de candidatos no Human Resources do aplicativo de recrutamento.</span><span class="sxs-lookup"><span data-stu-id="ad12b-108">Receive candidate referrals in Human Resources from the recruiting application.</span></span>
- <span data-ttu-id="ad12b-109">Conclua o processo de aprovação de candidatos no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="ad12b-109">Complete the candidate approval process in Human Resources.</span></span>

<span data-ttu-id="ad12b-110">Se não estiver usando um aplicativo de recrutamento separado, você também poderá gerenciar candidatos manualmente no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="ad12b-110">If you aren't using a separate recruiting application, you can also manually manage candidates in Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="ad12b-111">Se você for um administrador ou desenvolvedor e quiser integrar o Human Resources com um aplicativo de recrutamento de terceiros, consulte [Configurar integração do Dataverse](hr-admin-integration-common-data-service.md) e [Configurar tabelas virtuais do Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)</span><span class="sxs-lookup"><span data-stu-id="ad12b-111">If you're an admin or developer and want to integrate Human Resources with a third-party recruiting application, see [Configure Dataverse integration](hr-admin-integration-common-data-service.md) and [Configure Dataverse virtual tables](hr-admin-integration-common-data-service-virtual-entities.md)</span></span>
>
> <span data-ttu-id="ad12b-112">Também é possível encontrar aplicativos de integração de recrutamento no [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics).</span><span class="sxs-lookup"><span data-stu-id="ad12b-112">You can also find recruiting integration apps on [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics).</span></span>
>
> <span data-ttu-id="ad12b-113">Para testar a versão prévia do recurso para integração com o LinkedIn Talent Hub, consulte [Integrar com o LinkedIn Talent Hub](hr-admin-integration-linkedin.md).</span><span class="sxs-lookup"><span data-stu-id="ad12b-113">To try out our preview feature for integrating with LinkedIn Talent Hub, see [Integrate with LinkedIn Talent Hub](hr-admin-integration-linkedin.md).</span></span>

## <a name="enable-recruiting-requests"></a><span data-ttu-id="ad12b-114">Habilitar solicitações de recrutamento</span><span class="sxs-lookup"><span data-stu-id="ad12b-114">Enable recruiting requests</span></span>

<span data-ttu-id="ad12b-115">Se você deseja enviar solicitações de recrutamento no Human Resources, primeiro habilite a funcionalidade em **Parâmetros compartilhados de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-115">If you want to submit recruiting requests in Human Resources, you must first enable the functionality in **Human resources shared parameters**.</span></span>

1. <span data-ttu-id="ad12b-116">No espaço de trabalho **Gerenciamento de pessoal**, selecione **Links**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-116">In the **Personnel management** workspace, select **Links**.</span></span>

2. <span data-ttu-id="ad12b-117">Em **Configuração**, selecione **Parâmetros compartilhados de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-117">Under **Setup**, select **Human resources shared parameters**.</span></span>

3. <span data-ttu-id="ad12b-118">Na guia **Recrutamento**, em **RECRUTAMENTO**, defina **Habilitar solicitações de recrutamento** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-118">On the **Recruitment** tab, under **RECRUITING**, set **Enable recruiting requests** to **Yes**.</span></span>

## <a name="add-a-recruiting-request-location"></a><span data-ttu-id="ad12b-119">Adicionar um local de solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="ad12b-119">Add a recruiting request location</span></span>

<span data-ttu-id="ad12b-120">Se a sua organização tiver vários locais, você poderá adicioná-los de forma que os solicitantes possam selecionar um local no qual o novo recrutamento funcionará.</span><span class="sxs-lookup"><span data-stu-id="ad12b-120">If your organization has multiple locations, you can add them so requestors can select a location where the new recruit will be working.</span></span> <span data-ttu-id="ad12b-121">O local será incluído no lançamento do trabalho.</span><span class="sxs-lookup"><span data-stu-id="ad12b-121">The location will be included in the job posting.</span></span>

1. <span data-ttu-id="ad12b-122">Na barra de pesquisa, insira o **local da solicitação de recrutamento**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-122">In the search bar, enter **recruiting request location**.</span></span>

2. <span data-ttu-id="ad12b-123">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-123">Select **New**.</span></span>

3. <span data-ttu-id="ad12b-124">No campo **Local da solicitação de recrutamento**, insira o nome do local.</span><span class="sxs-lookup"><span data-stu-id="ad12b-124">In the **Recruiting request location** field, enter the location name.</span></span>

   ![Adicionar um local de solicitação de recrutamento](./media/hr-recruit-0a-add-location.png)

4. <span data-ttu-id="ad12b-126">No campo **Descrição**, insira uma descrição do local.</span><span class="sxs-lookup"><span data-stu-id="ad12b-126">In the **Description**, enter a description for the location.</span></span>

5. <span data-ttu-id="ad12b-127">Em **Local**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-127">Under **Location**, select **Add**.</span></span> <span data-ttu-id="ad12b-128">Se o popout **Novo endereço** aparecer, insira o endereço do local.</span><span class="sxs-lookup"><span data-stu-id="ad12b-128">If the **New address** popout appears, enter the address for the location.</span></span>

   ![Inserir endereço](./media/hr-recruit-0b-address.png)

6. <span data-ttu-id="ad12b-130">Em **Informações de contato**, insira as informações do contato do local.</span><span class="sxs-lookup"><span data-stu-id="ad12b-130">Under **Contact information**, enter the information for the location's contact.</span></span>

7. <span data-ttu-id="ad12b-131">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-131">Select **Save**.</span></span>

## <a name="add-a-recruiting-request"></a><span data-ttu-id="ad12b-132">Adicionar uma solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="ad12b-132">Add a recruiting request</span></span>

<span data-ttu-id="ad12b-133">Os gerentes podem enviar solicitações de recrutamento no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="ad12b-133">Managers can submit recruiting requests in Human Resources.</span></span> <span data-ttu-id="ad12b-134">Se você usar um aplicativo de recrutamento separado, ao concluir essas etapas, uma solicitação de recrutamento será enviada e o processo de recrutamento iniciará nesse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ad12b-134">If you use a separate recruiting application, completing these steps will send a recruiting request and start the recruiting process in that application.</span></span> <span data-ttu-id="ad12b-135">Caso contrário, conclua esse procedimento para iniciar o fluxo de trabalho para seu próprio processo de recrutamento interno.</span><span class="sxs-lookup"><span data-stu-id="ad12b-135">Otherwise, complete this procedure to begin the workflow for your own internal recruiting process.</span></span>

1. <span data-ttu-id="ad12b-136">Selecione **Autoatendimento para funcionários**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-136">Select **Employee self service**.</span></span>

2. <span data-ttu-id="ad12b-137">Selecione a guia **Minha equipe**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-137">Select the **My team** tab.</span></span>

3. <span data-ttu-id="ad12b-138">Selecione **Solucionar recrutamento**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-138">Select  **Request to recruit**.</span></span>

   ![Iniciar uma solicitação de recrutamento](./media/hr-recruit-1-request-to-recruit.png)

4. <span data-ttu-id="ad12b-140">Preencha os campos **Descrição**, **Trabalho** e **Data de início estimada**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-140">Complete the **Description**, **Job**, and **Estimated start date** fields.</span></span>

   ![Concluir a solicitação de recrutamento](./media/hr-recruit-2-request-to-recruit.png)

5. <span data-ttu-id="ad12b-142">Selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-142">Select **Continue**.</span></span> <span data-ttu-id="ad12b-143">A solicitação de recrutamento do seu cargo é exibida.</span><span class="sxs-lookup"><span data-stu-id="ad12b-143">The recruiting request for your position appears.</span></span>

6. <span data-ttu-id="ad12b-144">Em **Geral**, selecione um recrutador na lista suspensa **Recrutador** e selecione um local no menu suspenso **Localização da solicitação de recrutamento**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-144">Under **General**, select a recruiter from the **Recruiter** dropdown, and then select a location from the **Recruiting request location** dropdown.</span></span>

7. <span data-ttu-id="ad12b-145">Em **Trabalho**, altere as informações conforme necessário e selecione **Criar detalhes do trabalho**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-145">Under **Job**, change any information as needed, and then select **Create details from job**.</span></span>

   ![Criar detalhes do trabalho](./media/hr-recruit-3-create-details-from-job.png)

   <span data-ttu-id="ad12b-147">O restante da solicitação de recrutamento será preenchido com as informações padrão para o trabalho inserido.</span><span class="sxs-lookup"><span data-stu-id="ad12b-147">The rest of the recruiting request will populate with the default information for the job you entered.</span></span>

8. <span data-ttu-id="ad12b-148">Em **Descrição externa**, insira uma descrição de trabalho externa.</span><span class="sxs-lookup"><span data-stu-id="ad12b-148">Under **External description**, enter an external-facing job description.</span></span>

9. <span data-ttu-id="ad12b-149">Em **Posições**, selecione **Adicionar** e selecione um cargo para essa solicitação de recrutamento.</span><span class="sxs-lookup"><span data-stu-id="ad12b-149">Under **Positions**, select **Add**, and then select a position for this recruiting request.</span></span>

   ![Adicionar uma posição](./media/hr-recruit-4-select-position.png)

10. <span data-ttu-id="ad12b-151">Em **Habilidades**, selecione **Adicionar** e, depois, uma habilidade.</span><span class="sxs-lookup"><span data-stu-id="ad12b-151">Under **Skills**, select **Add**, and then select a skill.</span></span>

11. <span data-ttu-id="ad12b-152">Em **Requisitos de formação educacional**, selecione **Adicionar** e, depois, selecione os valores das **Educação** e **Nível de formação educacional**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-152">Under **Educational requirements**, select **Add**, and then select values from the **Education** and **Level of education** dropdowns.</span></span>

   ![Adicionar requisitos educacionais](./media/hr-recruit-5-select-educational-requirements.png)

12. <span data-ttu-id="ad12b-154">Em **Comentário**, adicione comentários, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ad12b-154">Under **Comment**, add comments as necessary.</span></span>

13. <span data-ttu-id="ad12b-155">Em **Remuneração**, selecione um nível no menu suspenso **Nível** e ajuste **Limite baixo**, **Ponto de controle** e **Limite alto**, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ad12b-155">Under **Compensation**, select a level from the **Level** dropdown, and then adjust **Low threshold**, **Control point**, and **High threshold** as necessary.</span></span>

14. <span data-ttu-id="ad12b-156">Quando sua solicitação de recrutamento for concluída e você estiver pronto para iniciar o processo de recrutamento, selecione **Ativar** na barra de menus.</span><span class="sxs-lookup"><span data-stu-id="ad12b-156">When your recruiting request is complete and you're ready to start the recruiting process, select **Activate** in the menu bar.</span></span>

   ![Ativar solicitação de recrutamento](./media/hr-recruit-6-activate-recruit-request.png)

15. <span data-ttu-id="ad12b-158">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-158">Select **Save**.</span></span>

## <a name="view-and-edit-your-recruiting-requests"></a><span data-ttu-id="ad12b-159">Exibir e editar solicitações de recrutamento</span><span class="sxs-lookup"><span data-stu-id="ad12b-159">View and edit your recruiting requests</span></span>

<span data-ttu-id="ad12b-160">Se você for um gerente e desejar exibir suas próprias solicitações:</span><span class="sxs-lookup"><span data-stu-id="ad12b-160">If you're a manager and want to view your own requests:</span></span>

1. <span data-ttu-id="ad12b-161">Selecione **Autoatendimento para funcionários**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-161">Select **Employee self service**.</span></span>

2. <span data-ttu-id="ad12b-162">Selecione a guia **Minha equipe**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-162">Select the **My team** tab.</span></span>

3. <span data-ttu-id="ad12b-163">Em **Informações da minha equipe**, selecione a guia **Solicitações de recrutamento**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-163">Under **My team information**, select the **Recruiting requests** tab.</span></span>

   ![Selecionar a guia Solicitações de recrutamento](./media/hr-recruit-7-recruiting-requests.png)

4. <span data-ttu-id="ad12b-165">Para exibir ou editar uma solicitação de recrutamento, selecione-a na grade.</span><span class="sxs-lookup"><span data-stu-id="ad12b-165">To view or edit a recruiting request, select it in the grid.</span></span>

<span data-ttu-id="ad12b-166">Se você for um profissional de RH e quiser exibir todas as solicitações de recrutamento:</span><span class="sxs-lookup"><span data-stu-id="ad12b-166">If you're an HR pro and want to view all recruiting requests:</span></span>

1. <span data-ttu-id="ad12b-167">Selecione **Gerenciamento de pessoal**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-167">Select **Personnel management**.</span></span>

2. <span data-ttu-id="ad12b-168">Selecione **Solicitações de recrutamento**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-168">Select **Recruiting requests**.</span></span>

   ![Exibir solicitações de recrutamento no Gerenciamento de pessoal](./media/hr-recruit-8-recruiting-requests-personnel-management.png)

3. <span data-ttu-id="ad12b-170">Para exibir ou editar uma solicitação de recrutamento, selecione-a na grade.</span><span class="sxs-lookup"><span data-stu-id="ad12b-170">To view or edit a recruiting request, select it in the grid.</span></span>

## <a name="add-or-edit-a-candidate-profile"></a><span data-ttu-id="ad12b-171">Adicionar ou editar um perfil de candidato</span><span class="sxs-lookup"><span data-stu-id="ad12b-171">Add or edit a candidate profile</span></span>

<span data-ttu-id="ad12b-172">Se a sua organização se integrou a outro aplicativo para gerenciar solicitações de recrutamento, as solicitações de recrutamento serão encaminhadas para esse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ad12b-172">If your organization has integrated with another application to manage recruiting requests, recruiting requests are forwarded to that application.</span></span> <span data-ttu-id="ad12b-173">O aplicativo de recrutamento reenvia informações sobre candidatos para o Human Resources.</span><span class="sxs-lookup"><span data-stu-id="ad12b-173">The recruiting application then sends candidate information back to Human Resources.</span></span> <span data-ttu-id="ad12b-174">Caso contrário, você poderá seguir seus próprios processos internos de recrutamento e inserir informações sobre os candidatos manualmente.</span><span class="sxs-lookup"><span data-stu-id="ad12b-174">Otherwise, you can follow your own internal recruiting processes and enter candidate information manually.</span></span>

1. <span data-ttu-id="ad12b-175">Selecione **Gerenciamento de pessoal**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-175">Select **Personnel management**.</span></span>

2. <span data-ttu-id="ad12b-176">Selecione **Links**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-176">Select **Links**.</span></span>

3. <span data-ttu-id="ad12b-177">Em **Recrutamento**, selecione **Candidatos**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-177">Under **Recruiting**, select **Candidates**.</span></span>

   ![Exibir candidatos](./media/hr-recruit-9-candidates.png)

4. <span data-ttu-id="ad12b-179">Para adicionar um candidato, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-179">To add a candidate, select **New**.</span></span> <span data-ttu-id="ad12b-180">Para editar um candidato existente, selecione o candidato na lista e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-180">To edit an existing candidate, select the candidate from the list and then select **Edit**.</span></span> <span data-ttu-id="ad12b-181">O perfil do candidato aparece.</span><span class="sxs-lookup"><span data-stu-id="ad12b-181">The candidate profile appears.</span></span>

5. <span data-ttu-id="ad12b-182">Em **Resumo de candidatos**, insira ou edite as informações do candidato conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ad12b-182">Under **Candidate summary**, enter or edit the candidate information as necessary.</span></span>

6. <span data-ttu-id="ad12b-183">Em **Solicitação de recrutamento**, selecione uma solicitação de recrutamento para vincular o candidato.</span><span class="sxs-lookup"><span data-stu-id="ad12b-183">Under **Recruiting request**, select a recruiting request to link the candidate to.</span></span> <span data-ttu-id="ad12b-184">Em seguida, preencha os campos **Data de início estimada**, **Gerente de contratação** e **Cargo** e **Descrição**, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="ad12b-184">Then complete the **Estimated start date**, **Hiring manager**, **Position**, and **Description fields** as appropriate.</span></span>

   ![Vincular à solicitação de recrutamento](./media/hr-recruit-10-link-to-recruiting-request.png)

7. <span data-ttu-id="ad12b-186">Preencha todas as informações nas seguintes áreas a serem incluídas no registro do candidato:</span><span class="sxs-lookup"><span data-stu-id="ad12b-186">Complete all the information in the following areas that you want to include in the candidate's record:</span></span>
   - <span data-ttu-id="ad12b-187">**Comentários**</span><span class="sxs-lookup"><span data-stu-id="ad12b-187">**Comments**</span></span>
   - <span data-ttu-id="ad12b-188">**Experiência Profissional**</span><span class="sxs-lookup"><span data-stu-id="ad12b-188">**Professional experience**</span></span>
   - <span data-ttu-id="ad12b-189">**Informações do contato**</span><span class="sxs-lookup"><span data-stu-id="ad12b-189">**Contact information**</span></span>
   - <span data-ttu-id="ad12b-190">**Formação**</span><span class="sxs-lookup"><span data-stu-id="ad12b-190">**Education**</span></span>
   - <span data-ttu-id="ad12b-191">**Habilidades**</span><span class="sxs-lookup"><span data-stu-id="ad12b-191">**Skills**</span></span>
   - <span data-ttu-id="ad12b-192">**Certificados**</span><span class="sxs-lookup"><span data-stu-id="ad12b-192">**Certificates**</span></span>
   - <span data-ttu-id="ad12b-193">**Triagens**</span><span class="sxs-lookup"><span data-stu-id="ad12b-193">**Screenings**</span></span>

8. <span data-ttu-id="ad12b-194">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-194">Select **Save**.</span></span>

## <a name="hire-a-candidate"></a><span data-ttu-id="ad12b-195">Contratar um candidato</span><span class="sxs-lookup"><span data-stu-id="ad12b-195">Hire a candidate</span></span>

<span data-ttu-id="ad12b-196">Quando estiver pronto para contratar um candidato, siga este procedimento para fazer a transição do candidato para um funcionário.</span><span class="sxs-lookup"><span data-stu-id="ad12b-196">When you're ready to hire a candidate, follow this procedure to transition the candidate to an employee.</span></span>

1. <span data-ttu-id="ad12b-197">No formulário do candidato, selecione **Contratar**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-197">On the candidate form, select **Hire**.</span></span>

   ![Contratar um candidato](./media/hr-recruit-11-hire.png)

2. <span data-ttu-id="ad12b-199">No formulário **Contratar novo trabalhador**, em **Detalhes**, preencha todos os campos.</span><span class="sxs-lookup"><span data-stu-id="ad12b-199">On the **Hire new worker** form, under **Details**, complete all the fields.</span></span>

   ![Inserir detalhes de novos contratados](./media/hr-recruit-12-hire-new-worker.png)

3. <span data-ttu-id="ad12b-201">Em **Detalhes do cargo**, verifique e altere as informações conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ad12b-201">Under **Position details**, verify and change information as necessary.</span></span>

4. <span data-ttu-id="ad12b-202">Em **Listas de verificação de integração**, selecione as listas de verificação de integração relevantes para este funcionário.</span><span class="sxs-lookup"><span data-stu-id="ad12b-202">Under **Onboarding checklists**, select the relevant onboarding checklists for this employee.</span></span>

5. <span data-ttu-id="ad12b-203">Selecione **Continuar** para criar o registro de funcionário.</span><span class="sxs-lookup"><span data-stu-id="ad12b-203">Select **Continue** to create the employee record.</span></span>

   >[!NOTE]
   ><span data-ttu-id="ad12b-204">Dependendo dos fluxos de trabalho da organização, o registro de candidatos pode passar por etapas de aprovação adicionais antes de se tornar um registro de funcionário.</span><span class="sxs-lookup"><span data-stu-id="ad12b-204">Depending on your organization's workflows, the candidate record may go through additional approval steps before becoming an employee record.</span></span>

## <a name="decide-not-to-hire-a-candidate"></a><span data-ttu-id="ad12b-205">Decidir não contratar um candidato</span><span class="sxs-lookup"><span data-stu-id="ad12b-205">Decide not to hire a candidate</span></span>

<span data-ttu-id="ad12b-206">Se você optar por não contratar um candidato, siga este procedimento para removê-lo do processo de habilitação.</span><span class="sxs-lookup"><span data-stu-id="ad12b-206">If you decide not to hire a candidate, follow this procedure to remove them from the vetting process.</span></span> 

1. <span data-ttu-id="ad12b-207">No formulário do candidato, selecione **Não contratar**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-207">On the candidate form, select **Do not hire**.</span></span>

   ![Não contratar candidato](./media/hr-recruit-13-do-not-hire.png)

2. <span data-ttu-id="ad12b-209">Selecione um **Código de motivo** e inclua comentários.</span><span class="sxs-lookup"><span data-stu-id="ad12b-209">Select a **Reason code** and include any comments.</span></span>

3. <span data-ttu-id="ad12b-210">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-210">Select **OK**.</span></span>

## <a name="dismiss-a-candidate"></a><span data-ttu-id="ad12b-211">Ignorar um candidato</span><span class="sxs-lookup"><span data-stu-id="ad12b-211">Dismiss a candidate</span></span>

<span data-ttu-id="ad12b-212">Se necessário, você poderá ignorar um candidato após contratá-lo.</span><span class="sxs-lookup"><span data-stu-id="ad12b-212">If needed, you can dismiss a candidate after hiring them.</span></span> <span data-ttu-id="ad12b-213">Por exemplo, um candidato pode rejeitar sua oferta ou não aparecer no primeiro dia.</span><span class="sxs-lookup"><span data-stu-id="ad12b-213">For example, a candidate might reject your offer or not show up on their first day.</span></span>

- <span data-ttu-id="ad12b-214">No formulário do candidato, selecione **Ignorar candidato**.</span><span class="sxs-lookup"><span data-stu-id="ad12b-214">On the candidate form, select **Dismiss candidate**.</span></span>

  ![Ignorar o candidato](./media/hr-recruit-14-dismiss-candidate.png)

## <a name="see-also"></a><span data-ttu-id="ad12b-216">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ad12b-216">See also</span></span>

[<span data-ttu-id="ad12b-217">Configurar tabelas virtuais do Dataverse</span><span class="sxs-lookup"><span data-stu-id="ad12b-217">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="ad12b-218">Organizar sua força de trabalho</span><span class="sxs-lookup"><span data-stu-id="ad12b-218">Organize your workforce</span></span>](hr-personnel-departments-jobs-positions.md)<br>
[<span data-ttu-id="ad12b-219">Configurar os componentes de um trabalho</span><span class="sxs-lookup"><span data-stu-id="ad12b-219">Set up the components of a job</span></span>](hr-personnel-jobs.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
