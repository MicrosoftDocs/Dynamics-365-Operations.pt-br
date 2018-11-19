---
title: Fornecimento com o LinkedIn Recruiter
description: "Este tópico fornece informações sobre o uso de machine learning para obter recomendações de trabalho e recomendações de candidatos ao trabalho."
author: josaw
manager: AnnBe
ms.date: 10/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: 
ms.author: josaw
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: 2fc6bf25d303d7d8de8002a923a080b90dcfbeab
ms.openlocfilehash: 106103e2c3d8f3d89aac5140174e5794da22536f
ms.contentlocale: pt-br
ms.lasthandoff: 10/24/2018

---

# <a name="sourcing-with-linkedin-recruiter"></a><span data-ttu-id="42ccd-103">Fornecimento com o LinkedIn Recruiter</span><span class="sxs-lookup"><span data-stu-id="42ccd-103">Sourcing with LinkedIn Recruiter</span></span>
[!include[banner](../includes/banner.md)]

<span data-ttu-id="42ccd-104">O LinkedIn é o maior banco de dados de talentos do mundo e geralmente o principal sistema que os recrutadores usam para encontrar, se comunicar e fornecer candidatos para os trabalhos que os recrutadores buscam preencher.</span><span class="sxs-lookup"><span data-stu-id="42ccd-104">LinkedIn is the world’s largest talent database and often the primary system that recruiters use to find, communicate with, and source candidates for the jobs that recruiters are looking to fill.</span></span> <span data-ttu-id="42ccd-105">A integração do LinkedIn Recruiter com Dynamics 365 for Talent: Attract facilita para os usuários fazerem contratações e manterem os dados sincronizados entre os dois sistemas.</span><span class="sxs-lookup"><span data-stu-id="42ccd-105">LinkedIn Recruiter integration with Dynamics 365 for Talent: Attract makes it easier for users to hire, and to keep the data in sync between the two systems.</span></span>

> [!NOTE]
> <span data-ttu-id="42ccd-106">Você precisa do complemento de Contratação abrangente e de estações do LinkedIn Recruiter para poder usar a integração do LinkedIn Recruiter com o Attract.</span><span class="sxs-lookup"><span data-stu-id="42ccd-106">You need the Comprehensive hiring add-on and LinkedIn Recruiter seats to be able to use LinkedIn Recruiter integration with Attract.</span></span>

## <a name="set-up-linkedin-recruiter-with-attract"></a><span data-ttu-id="42ccd-107">Configurar o LinkedIn Recruiter com o Attract</span><span class="sxs-lookup"><span data-stu-id="42ccd-107">Set up LinkedIn Recruiter with Attract</span></span> 

<span data-ttu-id="42ccd-108">Para poder usar os recursos do LinkedIn Recruiter, você deve configurar o acesso no nível de contrato ou o acesso no nível da empresa com sua instância do Attract.</span><span class="sxs-lookup"><span data-stu-id="42ccd-108">Before you can use the LinkedIn Recruiter capabilities, you must configure contract-level or company-level access with your Attract instance.</span></span> <span data-ttu-id="42ccd-109">Para concluir o processo de configuração, é necessário trabalhar com o usuário que seja um Administrador no contrato do LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="42ccd-109">To complete the configuration process, you must work with the user who is an Admin on your LinkedIn Recruiter contract.</span></span> <span data-ttu-id="42ccd-110">Conclua as etapas abaixo para configurar o LinkedIn Recruiter com o Attract.</span><span class="sxs-lookup"><span data-stu-id="42ccd-110">Complete the following steps to configure LinkedIn Recruiter with Attract.</span></span>

1.  <span data-ttu-id="42ccd-111">Entre no Attract como Administrador e acesse **Configurações de Administração**.</span><span class="sxs-lookup"><span data-stu-id="42ccd-111">Sign in to Attract as an Admin and go to **Admin Settings**.</span></span>

2.  <span data-ttu-id="42ccd-112">No painel esquerdo, clique na guia **Integração com o LinkedIn**.</span><span class="sxs-lookup"><span data-stu-id="42ccd-112">On the left pane, click the **LinkedIn Integration** tab.</span></span>

<span data-ttu-id="42ccd-113">[![Exibição do administrador no Attract para iniciar a integração com o LinkedIn Recruiter](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)</span><span class="sxs-lookup"><span data-stu-id="42ccd-113">[![Attract Admin view to start LinkedIn Recruiter integration](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)</span></span>

3.  <span data-ttu-id="42ccd-114">Clique em **Conectar** para iniciar a configuração e ser guiado no processo de logon do LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="42ccd-114">Click **Connect** to start the setup and be guided through the LinkedIn sign-in process.</span></span>

4.  <span data-ttu-id="42ccd-115">Se você tiver estações em vários contratos do LinkedIn, selecione o contrato ao qual você deseja conectar o sistema Attract.</span><span class="sxs-lookup"><span data-stu-id="42ccd-115">If you have seats on multiple LinkedIn contracts, select the contract that you would like to connect to the Attract system.</span></span> <span data-ttu-id="42ccd-116">Se você tiver uma estação em apenas um contrato do LinkedIn, essa etapa não será necessária.</span><span class="sxs-lookup"><span data-stu-id="42ccd-116">If you have a seat on only one LinkedIn contract, this step will not be needed.</span></span>

5.  <span data-ttu-id="42ccd-117">O widget do LinkedIn agora carregará suas configurações de administração com a lista de integrações exibidas.</span><span class="sxs-lookup"><span data-stu-id="42ccd-117">The LinkedIn widget will now load in your Admin settings with the list of integrations shown.</span></span> <span data-ttu-id="42ccd-118">Em **Recruiter System Connect**, clique em **Solicitar**.</span><span class="sxs-lookup"><span data-stu-id="42ccd-118">Under **Recruiter System connect**, click **Request**.</span></span>

<span data-ttu-id="42ccd-119">[![Exibição do administrador no Attract para solicitar a integração com o LinkedIn Recruiter](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)</span><span class="sxs-lookup"><span data-stu-id="42ccd-119">[![Attract Admin view to Request LinkedIn Recruiter integration](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)</span></span>

6.  <span data-ttu-id="42ccd-120">Depois que a integração for solicitada no Attract, ele será exibido como **Parceiro pronto** e estará pronto para ser ativado em **Configurações de administração do Recruiter**.</span><span class="sxs-lookup"><span data-stu-id="42ccd-120">After the integration is requested from Attract, it will show as **Partner ready** and is ready to be turned on from **Recruiter Admin settings**.</span></span> <span data-ttu-id="42ccd-121">Se você vir a mensagem **Notificar o parceiro** nesta página, aguarde alguns segundos, clique em **Notificar o parceiro**e atualize a página.</span><span class="sxs-lookup"><span data-stu-id="42ccd-121">If you see **Notify partner** on this page, wait a few seconds, click **Notify partner**, and then refresh the page.</span></span> <span data-ttu-id="42ccd-122">Ele agora deverá ser exibido como **Parceiro pronto**.</span><span class="sxs-lookup"><span data-stu-id="42ccd-122">It should now show as **Partner ready**.</span></span>

<span data-ttu-id="42ccd-123">[![Exibição do administrador no Attract para indicar o lado do Attract das solicitações que foram concluídas](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)</span><span class="sxs-lookup"><span data-stu-id="42ccd-123">[![Attract Admin view to indicate Attract side of requests have been completed](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)</span></span>

<span data-ttu-id="42ccd-124">Para concluir a etapa seguinte, você precisará ter um privilégio de administrador no contrato do LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="42ccd-124">To complete the next step, you need to have an Admin privilege on your LinkedIn Recruiter Contract.</span></span>

7.  <span data-ttu-id="42ccd-125">Entre no LinkedIn usando a conta de administrador e acesse o LinkedIn Recruiter na parte superior direita.</span><span class="sxs-lookup"><span data-stu-id="42ccd-125">Sign in to LinkedIn using the Admin account and go to LinkedIn Recruiter on the top right.</span></span> 

8. <span data-ttu-id="42ccd-126">No menu **Mais**, na parte superior da tela, clique em **Configurações de Administração** e na guia **ATS** .</span><span class="sxs-lookup"><span data-stu-id="42ccd-126">On the **More** menu at the top of the screen, click **Admin Settings**, and then click the **ATS** Tab.</span></span>

<span data-ttu-id="42ccd-127">O sistema Attract será listado com algumas opções que poderão ser ativadas.</span><span class="sxs-lookup"><span data-stu-id="42ccd-127">The Attract system will be listed with a couple of options that can be turned on.</span></span>

9. <span data-ttu-id="42ccd-128">Se quiser habilitar somente a exportação em um clique para o **Indicador em ATS** e para o **Widget de perfil em ATS**, selecione **Acesso no nível da empresa**.</span><span class="sxs-lookup"><span data-stu-id="42ccd-128">If you want to enable only 1-Click export for the **In-ATS indicator** and the **In-ATS Profile Widget**, select **Company-level access**.</span></span> <span data-ttu-id="42ccd-129">Se você deseja habilitar todos os recursos de acesso no nível da empresa além do histórico do InMail, histórico de Observações e o acesso a perfil do comprovante do InMail, selecione **Acesso no nível de contrato**.</span><span class="sxs-lookup"><span data-stu-id="42ccd-129">If you want to enable all of Company-level access features plus InMail history, Notes history, and the InMail stub profile access, select **Contract-level access**.</span></span>

10. <span data-ttu-id="42ccd-130">Ative o nível de acesso desejado nas configurações **Admin-ATS** do LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="42ccd-130">Turn on the desired access level from your LinkedIn Recruiter **Admin-ATS** settings.</span></span>

<span data-ttu-id="42ccd-131">[![Ativar a integração com o Attract a partir da Exibição do administrador do LinkedIn Recruiter](./media/EnableRSC.png)](./media/EnableRSC.png)</span><span class="sxs-lookup"><span data-stu-id="42ccd-131">[![Turn on Attract integration from LinkedIn Recruiter Admin view](./media/EnableRSC.png)](./media/EnableRSC.png)</span></span>

12. <span data-ttu-id="42ccd-132">Volte às Configurações de Administração do Attract como administrador do Attract e selecione a guia **Integração com o LinkedIn** . Agora você deverá ver o widget do LinkedIn carregado mostrando **Habilitado** com o nível de acesso selecionado ativado.</span><span class="sxs-lookup"><span data-stu-id="42ccd-132">Go back to Attract Admin Settings as an AttractAdmin and select the **LinkedIn integration** tab. You should now see the LinkedIn widget load showing **Enabled** with the selected access level turned on.</span></span>

<span data-ttu-id="42ccd-133">[![Integração com o LinkedIn Recruiter concluída](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)</span><span class="sxs-lookup"><span data-stu-id="42ccd-133">[![LinkedIn Recruiter integration complete](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)</span></span>

## <a name="using-linkedin-recruiter-capabilities"></a><span data-ttu-id="42ccd-134">Usando os recursos do LinkedIn Recruiter</span><span class="sxs-lookup"><span data-stu-id="42ccd-134">Using LinkedIn Recruiter capabilities</span></span>

<span data-ttu-id="42ccd-135">Depois que os recursos do LinkedIn Recruiter forem habilitados pelo administrador do Attract, eles estarão disponíveis para o acesso pelos gerentes de contratação e recrutadores.</span><span class="sxs-lookup"><span data-stu-id="42ccd-135">After LinkedIn Recruiter capabilities has been enabled by the Attract Admin it is available for hiring managers and recruiters to access.</span></span> <span data-ttu-id="42ccd-136">Para usar esses recursos, conecte sua conta do LinkedIn em **Configurações do usuário**.</span><span class="sxs-lookup"><span data-stu-id="42ccd-136">To use these capabilities, connect your LinkedIn account under **User Settings**.</span></span> <span data-ttu-id="42ccd-137">Vários recursos estarão disponíveis depois que as configurações do administrador e do usuário forem conectadas.</span><span class="sxs-lookup"><span data-stu-id="42ccd-137">Several capabilities will be available after both the Admin and User settings have been connected.</span></span>

### <a name="in-ats-profile-widget"></a><span data-ttu-id="42ccd-138">Widget de perfil em ATS</span><span class="sxs-lookup"><span data-stu-id="42ccd-138">In-ATS profile widget</span></span>

<span data-ttu-id="42ccd-139">Você pode exibir o perfil do LinkedIn do candidato no Attract.</span><span class="sxs-lookup"><span data-stu-id="42ccd-139">You can view the candidate’s LinkedIn profile in Attract.</span></span> <span data-ttu-id="42ccd-140">O widget do LinkedIn exibirá o perfil do candidato quando as informações de ATS corresponderem com as informações do LinkedIn de seus usuários.</span><span class="sxs-lookup"><span data-stu-id="42ccd-140">The LinkedIn widget will display the candidate profile when the ATS information matches the LinkedIn information of its users.</span></span>

<span data-ttu-id="42ccd-141">Para exibir um perfil, acesse o perfil do candidato a partir de um trabalho ou de um grupo de talentos.</span><span class="sxs-lookup"><span data-stu-id="42ccd-141">To view a profile, go the candidate profile either from a job or talent pool.</span></span> <span data-ttu-id="42ccd-142">No perfil do candidato, selecione a guia **LinkedIn** e o widget de perfil será carregado.</span><span class="sxs-lookup"><span data-stu-id="42ccd-142">In the candidate profile, select the **LinkedIn** tab and the profile widget will load.</span></span> <span data-ttu-id="42ccd-143">Usando o widget de perfil, indique se esta é a correspondência correta.</span><span class="sxs-lookup"><span data-stu-id="42ccd-143">Using the profile widget, indicate if this is the correct match.</span></span> <span data-ttu-id="42ccd-144">Caso contrário, encontre a pessoa correta.</span><span class="sxs-lookup"><span data-stu-id="42ccd-144">If it is not, find the correct person.</span></span> <span data-ttu-id="42ccd-145">Você também pode salvar o candidato em seus projetos do LinkedIn Recruiter a nessa página.</span><span class="sxs-lookup"><span data-stu-id="42ccd-145">You can also save the candidate to your LinkedIn Recruiter projects from this page.</span></span>

### <a name="1-click-export"></a><span data-ttu-id="42ccd-146">Exportação em um clique</span><span class="sxs-lookup"><span data-stu-id="42ccd-146">1-click export</span></span> 

<span data-ttu-id="42ccd-147">Ao fornecer candidatos no LinkedIn, é possível fazer a exportação em um clique do candidato para os trabalhos que você tiver em aberto o momento.</span><span class="sxs-lookup"><span data-stu-id="42ccd-147">While sourcing candidates in LinkedIn, you can 1-click export the candidate to the jobs that you currently have open.</span></span> <span data-ttu-id="42ccd-148">Conclua as etapas a seguir para fazer uma exportação em um clique.</span><span class="sxs-lookup"><span data-stu-id="42ccd-148">Complete the following steps for a 1-click export.</span></span> <span data-ttu-id="42ccd-149">Antes de concluir essas etapas, verifique se você está atribuído à função de Gerente de contratação ou Recrutador para o trabalho e se o trabalho tem um estágio **Cliente potencial**.</span><span class="sxs-lookup"><span data-stu-id="42ccd-149">Before you complete these steps, verify that you are a assigned the role of Hiring manager or Recruiter for the job and that the job has a **Prospect** stage.</span></span>

1.  <span data-ttu-id="42ccd-150">Crie o trabalho, atribua as funções adequadas e ative o trabalho.</span><span class="sxs-lookup"><span data-stu-id="42ccd-150">Create the job, assign the appropriate roles, and activate the job.</span></span>

2.  <span data-ttu-id="42ccd-151">Quando o trabalho for ativado, navegue até o LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="42ccd-151">When the job is activated, navigate to LinkedIn Recruiter.</span></span>

3.  <span data-ttu-id="42ccd-152">Encontre o candidato que você está procurando e acesse seu perfil.</span><span class="sxs-lookup"><span data-stu-id="42ccd-152">Find the candidate that you are looking for and go to their profile.</span></span>

4.  <span data-ttu-id="42ccd-153">Usando a caixa de pesquisa de trabalhos no cartão de contato, encontre o trabalho usando o título ou a ID do trabalho que foi ativado no Attract.</span><span class="sxs-lookup"><span data-stu-id="42ccd-153">Using the job search box in the contact card, find the job using the title or the Job ID that was activated in Attract.</span></span> <span data-ttu-id="42ccd-154">Se você não encontrar o trabalho, clique em **Alterar ATS** para encontrar a instância correta do Attract.</span><span class="sxs-lookup"><span data-stu-id="42ccd-154">If you don’t find the job, click **Change ATS** to find the correct Attract instance.</span></span>

5. <span data-ttu-id="42ccd-155">Depois que o trabalho for selecionado, clique em **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="42ccd-155">After the job is selected, click **Export**.</span></span> <span data-ttu-id="42ccd-156">O candidato agora será obtido pelo Attract.</span><span class="sxs-lookup"><span data-stu-id="42ccd-156">The candidate is now fetched by Attract.</span></span>

6.  <span data-ttu-id="42ccd-157">Acesse o Attract e abra o respectivo trabalho.</span><span class="sxs-lookup"><span data-stu-id="42ccd-157">Go to Attract and open the respective job.</span></span> <span data-ttu-id="42ccd-158">Você encontrará o candidato que acabou de exportar no estágio **Candidato ao trabalho** do trabalho.</span><span class="sxs-lookup"><span data-stu-id="42ccd-158">You will find the candidate that you just exported in the **Prospect** stage of the job.</span></span>

### <a name="in-ats-indicator"></a><span data-ttu-id="42ccd-159">Indicador em ATS</span><span class="sxs-lookup"><span data-stu-id="42ccd-159">In-ATS indicator</span></span> 

<span data-ttu-id="42ccd-160">Usando o LinkedIn Recruiter, você poderá rastrear se um candidato se candidatou a outros trabalhos em sua organização, acompanhar em que parte está em estágios diferentes de solicitações de emprego e exibir os comentários do Attract no LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="42ccd-160">Using LinkedIn recruiter, you can track whether a candidate has applied to other jobs in your organization, look at where they are in different stages of job applications, and view the feedback and comments from Attract in LinkedIn Recruiter.</span></span>

1.  <span data-ttu-id="42ccd-161">Abra o LinkedIn Recruiter e localize o perfil do candidato que você está procurando.</span><span class="sxs-lookup"><span data-stu-id="42ccd-161">Open LinkedIn Recruiter and locate the candidate profile that you are looking for.</span></span>

2.  <span data-ttu-id="42ccd-162">Role para baixo para exibir a seção **Em ATS** no perfil do candidato.</span><span class="sxs-lookup"><span data-stu-id="42ccd-162">Scroll down to view the **In-ATS** section on the candidate’s profile.</span></span>

3.  <span data-ttu-id="42ccd-163">Você pode usar este widget para exibir todas as informações sobre o candidato que estejam presentes no Attract na exibição do LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="42ccd-163">You can use this widget to view all of the information about the candidate that’s present in Attract from within the LinkedIn Recruiter view.</span></span>

4.  <span data-ttu-id="42ccd-164">Selecione a guia **Trabalhos e status** para ver quais trabalhos fazem parte, o status mais recente e como eles vêm mudando em relação a cada trabalho.</span><span class="sxs-lookup"><span data-stu-id="42ccd-164">Select the **Jobs & Statuses** tab to see jobs they are part of, the latest status, and how they have been moving against each job.</span></span>

5.  <span data-ttu-id="42ccd-165">Selecione a guia **Comentários da entrevista** para ver os comentários que os entrevistadores enviaram no Attract.</span><span class="sxs-lookup"><span data-stu-id="42ccd-165">Select the **Interview Feedback** tab to see feedback that the interviewers have submitted in Attract.</span></span>

6.  <span data-ttu-id="42ccd-166">Selecione a guia **Observações** para consultar as observações que foram feitas sobre o candidato no Attract.</span><span class="sxs-lookup"><span data-stu-id="42ccd-166">Select the **Notes** tab to see notes that have been captured for this applicant in Attract.</span></span>

### <a name="inmail-history"></a><span data-ttu-id="42ccd-167">Histórico do InMail</span><span class="sxs-lookup"><span data-stu-id="42ccd-167">InMail history</span></span>

<span data-ttu-id="42ccd-168">O histórico do LinkedIn InMail está disponível com o acesso no nível de contrato do LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="42ccd-168">The LinkedIn InMail history is available with contract-level access with LinkedIn Recruiter.</span></span> <span data-ttu-id="42ccd-169">Quando habilitado, você poderá exibir o histórico completo do InMail com o candidato.</span><span class="sxs-lookup"><span data-stu-id="42ccd-169">When it is enabled, you can view your entire InMail history with the candidate.</span></span> <span data-ttu-id="42ccd-170">Você também poderá consultar quem mais em sua organização trocou InMails com o candidato, no entanto, você não poderá exibir as mensagens entre eles.</span><span class="sxs-lookup"><span data-stu-id="42ccd-170">You can also see who else from your organization has exchanged InMail with the candidate, however you can't view the messages between them.</span></span>

<span data-ttu-id="42ccd-171">Para exibir o histórico do InMail, acesse o perfil de um candidato, acesse a guia **LinkedIn** e role para a parte inferior da página para exibir o histórico.</span><span class="sxs-lookup"><span data-stu-id="42ccd-171">To view InMail history, go to a candidate’s profile, go to the **LinkedIn** tab and scroll to the bottom of the page to view the history.</span></span> <span data-ttu-id="42ccd-172">Você poderá exibir o histórico do InMail somente se o candidato tiver respondido à sua solicitação e optado por compartilhar o perfil com você no LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="42ccd-172">You can view the InMail history only if the candidate has responded to your request and chosen to share their profile with you in LinkedIn.</span></span> <span data-ttu-id="42ccd-173">As mensagens do InMail sincronizam com o Attract a cada duas horas.</span><span class="sxs-lookup"><span data-stu-id="42ccd-173">The messages from InMail sync with Attract every couple of hours.</span></span>

### <a name="notes-history"></a><span data-ttu-id="42ccd-174">Histórico de observações</span><span class="sxs-lookup"><span data-stu-id="42ccd-174">Notes history</span></span> 

<span data-ttu-id="42ccd-175">O histórico de observações do LinkedIn está disponível com o acesso no nível de contrato do LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="42ccd-175">The LinkedIn notes history is available with contract-level access with LinkedIn Recruiter.</span></span> <span data-ttu-id="42ccd-176">Quando habilitado, você poderá exibir as observações que foram feitas sobre o candidato por diferentes recrutadores de sua organização.</span><span class="sxs-lookup"><span data-stu-id="42ccd-176">When it is enabled, you can view the notes that have been captured about the candidate by different recruiters from your organization.</span></span>

<span data-ttu-id="42ccd-177">Para exibir o histórico de observações, acesse o perfil de um candidato, acesse a guia **LinkedIn** e role para a parte inferior da página para exibir o histórico.</span><span class="sxs-lookup"><span data-stu-id="42ccd-177">To view Notes history, go to a candidate’s profile, go to the **LinkedIn** tab and scroll to the bottom of the page to view the history.</span></span> <span data-ttu-id="42ccd-178">Você poderá exibir as observações sobre o candidato no LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="42ccd-178">You can view all the notes about the candidate from LinkedIn Recruiter.</span></span>

### <a name="inmail-stub-profile"></a><span data-ttu-id="42ccd-179">Perfil do comprovante do InMail</span><span class="sxs-lookup"><span data-stu-id="42ccd-179">InMail stub profile</span></span>

<span data-ttu-id="42ccd-180">O perfil do comprovante do está disponível com o acesso no nível de contrato do LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="42ccd-180">The InMail stub profile is available with contract-level access with LinkedIn Recruiter.</span></span> <span data-ttu-id="42ccd-181">Se os candidatos concordarem em compartilhar seus perfis do LinkedIn com qualquer usuário em sua organização, você poderá rastrear os candidatos no Attract e um novo registro de candidato será criado para cada um.</span><span class="sxs-lookup"><span data-stu-id="42ccd-181">If candidates agree to share their LinkedIn profiles with any user in your organization, you can track the candidates in Attract and a new candidate record will be created for each candidate.</span></span>

<span data-ttu-id="42ccd-182">Para exibir a lista de candidatos, acesse **Grupos de talentos** para exibir um grupo de talentos do LinkedIn criado pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="42ccd-182">To view the list of candidates, go to **Talent pools** to see a system-created LinkedIn talent pool.</span></span> <span data-ttu-id="42ccd-183">Esse grupo de talentos contém a lista de candidatos e seus perfis do comprovante conforme recebidos do LinkedIn, mostrando o nome e sobrenome do candidato.</span><span class="sxs-lookup"><span data-stu-id="42ccd-183">This talent pool contains the list candidates and their stub profiles as received from LinkedIn, showing the candidate's first name and last name.</span></span> <span data-ttu-id="42ccd-184">A ID do email do candidato será exibida se o candidato tiver optado por compartilhar o endereço de email.</span><span class="sxs-lookup"><span data-stu-id="42ccd-184">The candidate’s email ID will be displayed if the candidate had chosen to share their email address.</span></span>

