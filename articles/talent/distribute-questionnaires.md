---
title: "Distribuir e concluir um questionário"
description: "Este tópico explica como distribuir os questionários criados por você, de modo que sejam disponibilizados para a pessoa ou grupo de pessoas que os preencherão."
author: kherr75
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KMConnectionType, KMKnowledgeCollectorPlanningTabel, SysEmailParameters
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Core
ms.custom: 17424
ms.assetid: fd8d867a-2446-400a-b91f-ad4085427470
ms.search.region: Global
ms.author: kherr75
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 97003c6e90db1fe1335deff65efe6b5ef07ae24b
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="distribute-and-complete-a-questionnaire"></a><span data-ttu-id="f10bd-103">Distribuir e concluir um questionário</span><span class="sxs-lookup"><span data-stu-id="f10bd-103">Distribute and complete a questionnaire</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="f10bd-104">Este tópico explica como distribuir os questionários criados por você, de modo que sejam disponibilizados para a pessoa ou grupo de pessoas que os preencherão.</span><span class="sxs-lookup"><span data-stu-id="f10bd-104">This topic explains how distribute the questionnaires that you design, so that they are available to the person or group of people who will complete them.</span></span> 

<span data-ttu-id="f10bd-105">Há várias formas de distribuir um questionário:</span><span class="sxs-lookup"><span data-stu-id="f10bd-105">There are multiple ways to distribute a questionnaire:</span></span>

-   <span data-ttu-id="f10bd-106">Marcar o questionário como ativo.</span><span class="sxs-lookup"><span data-stu-id="f10bd-106">Mark the questionnaire as active.</span></span> <span data-ttu-id="f10bd-107">O questionário é disponibilizado a todos os funcionários, a menos que um grupo de questionários esteja configurado para restringir o acesso ao questionário.</span><span class="sxs-lookup"><span data-stu-id="f10bd-107">The questionnaire is then available to all employees, unless a questionnaire group is set up to restrict access to it.</span></span>
-   <span data-ttu-id="f10bd-108">Atribuir direitos a um grupo de questionários.</span><span class="sxs-lookup"><span data-stu-id="f10bd-108">Assign rights to a questionnaire group.</span></span> <span data-ttu-id="f10bd-109">O questionário ficará disponível a todos os membros do grupo selecionado.</span><span class="sxs-lookup"><span data-stu-id="f10bd-109">The questionnaire is then available to all members of the selected group.</span></span>
-   <span data-ttu-id="f10bd-110">Criar sessões de resposta planejadas.</span><span class="sxs-lookup"><span data-stu-id="f10bd-110">Create planned answer sessions.</span></span> <span data-ttu-id="f10bd-111">O questionário está disponível a apenas uma pessoa em particular.</span><span class="sxs-lookup"><span data-stu-id="f10bd-111">The questionnaire is then available only to a particular person.</span></span>
-   <span data-ttu-id="f10bd-112">Criar uma agenda.</span><span class="sxs-lookup"><span data-stu-id="f10bd-112">Create a schedule.</span></span> <span data-ttu-id="f10bd-113">O questionário poderá estar disponível para vários contatos.</span><span class="sxs-lookup"><span data-stu-id="f10bd-113">The questionnaire can then be available to multiple people.</span></span>

## <a name="marking-a-questionnaire-as-active"></a><span data-ttu-id="f10bd-114">Marcar um questionário como ativo</span><span class="sxs-lookup"><span data-stu-id="f10bd-114">Marking a questionnaire as active</span></span>
<span data-ttu-id="f10bd-115">Configurando o campo **Ativo** como **Sim** na página **Questionários**, você disponibiliza o questionário para todos os funcionários preencherem.</span><span class="sxs-lookup"><span data-stu-id="f10bd-115">By setting the **Active** field to **Yes** on the **Questionnaires** page, you make the questionnaire available for all employees to complete.</span></span> <span data-ttu-id="f10bd-116">Os respondentes poderão preencher o questionário várias vezes.</span><span class="sxs-lookup"><span data-stu-id="f10bd-116">Respondents can complete the questionnaire multiple times.</span></span> <span data-ttu-id="f10bd-117">Essa funcionalidade será útil se você quiser obter feedback contínuo durante todo o ano.</span><span class="sxs-lookup"><span data-stu-id="f10bd-117">This functionality is useful if you want to gather continual feedback throughout the year.</span></span> <span data-ttu-id="f10bd-118">Por exemplo, você pode fazer um questionário que os funcionários usam para fornecer feedback sobre o serviço de almoço no bar.</span><span class="sxs-lookup"><span data-stu-id="f10bd-118">For example, you can make a questionnaire that employees use to give feedback about the lunch service in the cafeteria.</span></span>

## <a name="questionnaire-groups"></a><span data-ttu-id="f10bd-119">Grupos de questionários</span><span class="sxs-lookup"><span data-stu-id="f10bd-119">Questionnaire groups</span></span>
<span data-ttu-id="f10bd-120">Você pode configurar grupos de questionário e incluir os participantes para os quais um questionário deve ser distribuído.</span><span class="sxs-lookup"><span data-stu-id="f10bd-120">You can set up questionnaire groups and then include the respondents that a questionnaire should be distributed to.</span></span> 

<span data-ttu-id="f10bd-121">Você pode criar grupos de questionário das seguintes páginas:</span><span class="sxs-lookup"><span data-stu-id="f10bd-121">You can create questionnaire groups from the following pages:</span></span>

-   <span data-ttu-id="f10bd-122">**Grupos de questionários**– Somente os indivíduos em um grupo de questionário podem preencher um questionário selecionado.</span><span class="sxs-lookup"><span data-stu-id="f10bd-122">**Questionnaire groups** – Only individuals in a questionnaire group can complete a selected questionnaire.</span></span> <span data-ttu-id="f10bd-123">Por exemplo, se o público-alvo é prestadores de serviço, você pode criar um grupo de questionário que é específico para esses entrevistados.</span><span class="sxs-lookup"><span data-stu-id="f10bd-123">For example, your intended audience is contractors, so you create a questionnaire group that is specific to those respondents.</span></span>
-   <span data-ttu-id="f10bd-124">**Membros do grupo de questionário** – Você pode adicionar pessoas aos grupos de questionários.</span><span class="sxs-lookup"><span data-stu-id="f10bd-124">**Questionnaire group members** – You can add people to the questionnaire groups.</span></span>

<span data-ttu-id="f10bd-125">Para atribuir um grupo de questionários a um questionário, na página **Questionário**, clique em **Direitos do usuário**.</span><span class="sxs-lookup"><span data-stu-id="f10bd-125">To assign a questionnaire group to a questionnaire, on the **Questionnaires** page, click **User rights**.</span></span> <span data-ttu-id="f10bd-126">Depois que o questionário foi salvo como ativo, os membros do grupo de questionário podem preencher o questionário.</span><span class="sxs-lookup"><span data-stu-id="f10bd-126">After the questionnaire is saved as active, the members of the questionnaire group can complete the questionnaire.</span></span> <span data-ttu-id="f10bd-127">Essa funcionalidade será útil se você quiser testar um questionário em um grupo seleto de pessoas antes de enviá-lo para um grupo maior, ou se você quiser direcionar um questionário para um público muito específico.</span><span class="sxs-lookup"><span data-stu-id="f10bd-127">This functionality is helpful if you want to test a questionnaire on a select group of people before you roll it out to a larger group, or if you want to target a questionnaire to a very specific audience.</span></span>

## <a name="planned-answer-sessions-in-a-questionnaire"></a><span data-ttu-id="f10bd-128">Sessões de respostas planejadas em um questionário</span><span class="sxs-lookup"><span data-stu-id="f10bd-128">Planned answer sessions in a questionnaire</span></span>
<span data-ttu-id="f10bd-129">As sessões de respostas planejadas são os questionários para os quais você criou e selecionou os participantes.</span><span class="sxs-lookup"><span data-stu-id="f10bd-129">Planned answer sessions are questionnaires that you've designed and selected the respondents for.</span></span> 

> <span data-ttu-id="f10bd-130">**Observação** Antes de configurar as sessões de respostas planejadas, você deverá criar um questionário.</span><span class="sxs-lookup"><span data-stu-id="f10bd-130">**Note** Before you can set up planned answer sessions, you must design a questionnaire.</span></span> 

<span data-ttu-id="f10bd-131">N página **Sessão de respostas planejadas**, é possível criar uma sessão de resposta planejada para um funcionário individual.</span><span class="sxs-lookup"><span data-stu-id="f10bd-131">On the **Planned answer session** page, you can create a planned answer session for an individual employee.</span></span> <span data-ttu-id="f10bd-132">A lista na página exibe todos os questionários planejados.</span><span class="sxs-lookup"><span data-stu-id="f10bd-132">The list on the page displays all planned questionnaires.</span></span> 

<span data-ttu-id="f10bd-133">As sessões de respostas planejadas também são usadas na página **Agendas de questionário**, onde é possível planejar questionários para diversas pessoas:</span><span class="sxs-lookup"><span data-stu-id="f10bd-133">Planned answer sessions are also used on the **Questionnaire schedules** page, where you can plan questionnaires for multiple people:</span></span>

-   <span data-ttu-id="f10bd-134">Funcionários</span><span class="sxs-lookup"><span data-stu-id="f10bd-134">Employees</span></span>
-   <span data-ttu-id="f10bd-135">Participantes do curso</span><span class="sxs-lookup"><span data-stu-id="f10bd-135">Course participants</span></span>
-   <span data-ttu-id="f10bd-136">Unidades organizacionais</span><span class="sxs-lookup"><span data-stu-id="f10bd-136">Organizational units</span></span>

<span data-ttu-id="f10bd-137">Cada pessoa pode responder ao questionário apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="f10bd-137">Each person can answer the questionnaire only one time.</span></span>

## <a name="scheduling-a-questionnaire"></a><span data-ttu-id="f10bd-138">Planejando um questionário</span><span class="sxs-lookup"><span data-stu-id="f10bd-138">Scheduling a questionnaire</span></span>
<span data-ttu-id="f10bd-139">Como opção, você pode planejar um questionário para vários participantes.</span><span class="sxs-lookup"><span data-stu-id="f10bd-139">You can optionally schedule a questionnaire for multiple respondents.</span></span>

### <a name="planning-types"></a><span data-ttu-id="f10bd-140">Tipos de planejamento</span><span class="sxs-lookup"><span data-stu-id="f10bd-140">Planning types</span></span>

<span data-ttu-id="f10bd-141">Os tipos de planejamento são necessários se você desejar agendar sessões de respostas planejadas para vários entrevistados.</span><span class="sxs-lookup"><span data-stu-id="f10bd-141">Planning types are required if you want to schedule planned answer sessions for multiple respondents.</span></span> <span data-ttu-id="f10bd-142">Os tipos de plano são usados para classificar planos de questionário.</span><span class="sxs-lookup"><span data-stu-id="f10bd-142">Planning types are used to classify questionnaire schedules.</span></span> <span data-ttu-id="f10bd-143">Por exemplo, você pode planejar questionários para as seguintes finalidades:</span><span class="sxs-lookup"><span data-stu-id="f10bd-143">For example, you can schedule questionnaires for the following purposes:</span></span>

-   <span data-ttu-id="f10bd-144">Avaliação</span><span class="sxs-lookup"><span data-stu-id="f10bd-144">Evaluation</span></span>
-   <span data-ttu-id="f10bd-145">Pesquisa</span><span class="sxs-lookup"><span data-stu-id="f10bd-145">Survey</span></span>
-   <span data-ttu-id="f10bd-146">Testando</span><span class="sxs-lookup"><span data-stu-id="f10bd-146">Testing</span></span>

<span data-ttu-id="f10bd-147">Você pode especificar tipos de plano para um plano de questionário na página **Agendas de questionário**.</span><span class="sxs-lookup"><span data-stu-id="f10bd-147">You can specify planning types for a questionnaire schedule on the **Questionnaire schedules** page.</span></span>

### <a name="reference-types-for-questionnaire"></a><span data-ttu-id="f10bd-148">Tipos de referência para o questionário</span><span class="sxs-lookup"><span data-stu-id="f10bd-148">Reference types for questionnaire</span></span>

<span data-ttu-id="f10bd-149">É possível usar tipos de referência para inserir critérios para os entrevistados que você pode selecionar ao planejar um questionário.</span><span class="sxs-lookup"><span data-stu-id="f10bd-149">You can use reference types to enter criteria for the respondents that you might select when you schedule a questionnaire.</span></span> 

<span data-ttu-id="f10bd-150">Use a página **Tipos de referência** para configurar os tipos de referência para um questionário.</span><span class="sxs-lookup"><span data-stu-id="f10bd-150">Use the **Reference types** page to set up reference types for a questionnaire.</span></span> <span data-ttu-id="f10bd-151">Cada tipo de referência corresponde a uma tabela do Microsoft Dynamics 365 Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f10bd-151">Each reference type corresponds to a table in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="f10bd-152">A o criar planos de questionários, você pode especificar os registros individuais na tabela ou um intervalo de registros ao qual o questionário será associado.</span><span class="sxs-lookup"><span data-stu-id="f10bd-152">When you create questionnaire schedules, you can specify individual records in the table or a range of records that the questionnaire will be associated with.</span></span> 

<span data-ttu-id="f10bd-153">Por exemplo, se você selecionar a tabela Cursos, poderá decidir qual curso específico para o qual será o questionário.</span><span class="sxs-lookup"><span data-stu-id="f10bd-153">For example, if you select the Courses table, you can decide which specific course the questionnaire will be for.</span></span> <span data-ttu-id="f10bd-154">Ao configurar uma referência para a tabela Cursos, alguns campos e botões na página **Cursos** se tornam disponíveis.</span><span class="sxs-lookup"><span data-stu-id="f10bd-154">When you set up a reference for the Courses table, some fields and buttons on the **Courses** page become available.</span></span>

### <a name="questionnaire-schedules"></a><span data-ttu-id="f10bd-155">Agendas de questionários</span><span class="sxs-lookup"><span data-stu-id="f10bd-155">Questionnaire schedules</span></span>

<span data-ttu-id="f10bd-156">Você pode usar agendas de questionário para gerar várias sessões de resposta planejadas para um grupo de usuários, com base em um tipo de referência.</span><span class="sxs-lookup"><span data-stu-id="f10bd-156">You can use questionnaire schedules to generate multiple planned answer sessions for a group of users, based on a reference type.</span></span> <span data-ttu-id="f10bd-157">Criar uma agenda na página **Agendas de questionários**.</span><span class="sxs-lookup"><span data-stu-id="f10bd-157">Create a schedule on the **Questionnaire schedules** page.</span></span> <span data-ttu-id="f10bd-158">Selecione o tipo de planejamento para categorizar a agenda e também selecione o tipo de referência que deve ser usado para consultar o sistema para usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="f10bd-158">Select the planning type to categorize the schedule, and also select the reference type that should be used to query the system for specific users.</span></span> <span data-ttu-id="f10bd-159">Por exemplo, se definir o tipo de referência para a tabela Cursos, você pode selecionar um curso específico no campo **Referência**.</span><span class="sxs-lookup"><span data-stu-id="f10bd-159">For example, if you set the reference type to the Courses table, you can select a specific course in the **Reference** field.</span></span> 

<span data-ttu-id="f10bd-160">Clique em **Detalhes de instalação** para selecionar o questionário e outros critérios.</span><span class="sxs-lookup"><span data-stu-id="f10bd-160">Click **Setup details** to select the questionnaire and other criteria.</span></span> <span data-ttu-id="f10bd-161">Por exemplo, especifique o nome do instrutor como um critério, se o questionário for uma avaliação do instrutor.</span><span class="sxs-lookup"><span data-stu-id="f10bd-161">For example, specify the instructor's name as a criterion if the questionnaire is an evaluation of the instructor.</span></span> <span data-ttu-id="f10bd-162">Depois que terminar de inserir os detalhes de instalação, o sistema gera sessões de respostas planejadas para os usuários incluídos na consulta.</span><span class="sxs-lookup"><span data-stu-id="f10bd-162">After you've finished entering the setup details, the system generates planned answer sessions for the users that are included in the query.</span></span> 

<span data-ttu-id="f10bd-163">Clique em **Sessões de respostas planejadas** para exibir as sessões de respostas para a agenda.</span><span class="sxs-lookup"><span data-stu-id="f10bd-163">Click **Planned answer sessions** to view the answer sessions for the schedule.</span></span> <span data-ttu-id="f10bd-164">Você poderá criar manualmente sessões de respostas planejadas adicionais ou excluir as sessões de respostas planejadas que não foram atendidas.</span><span class="sxs-lookup"><span data-stu-id="f10bd-164">You can then manually create additional planned answer sessions or delete planned answer sessions that haven't been answered.</span></span> 

<span data-ttu-id="f10bd-165">Clique em **Funções** &gt; **Início** para disponibilizar o questionário aos usuários em sessões de respostas planejadas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="f10bd-165">Click **Functions** &gt; **Start** to make the questionnaire available to the users in related planned answer sessions.</span></span> <span data-ttu-id="f10bd-166">Clique em **Respostas** para exibir as respostas concluídas do questionário.</span><span class="sxs-lookup"><span data-stu-id="f10bd-166">Click **Answers** to view the completed responses to the questionnaire.</span></span> <span data-ttu-id="f10bd-167">Como opção, você pode copiar as configurações de agenda do questionário, as sessões de respostas planejadas, e as respostas para uma nova agenda de questionário.</span><span class="sxs-lookup"><span data-stu-id="f10bd-167">You can optionally copy the questionnaire schedule settings, planned answer sessions, and answers to a new questionnaire schedule.</span></span>

## <a name="notifying-respondents-about-questionnaires-that-are-available-to-them"></a><span data-ttu-id="f10bd-168">Notificando participantes sobre os questionários que estão disponíveis para eles</span><span class="sxs-lookup"><span data-stu-id="f10bd-168">Notifying respondents about questionnaires that are available to them</span></span>
<span data-ttu-id="f10bd-169">Quando você distribuir um questionário, será necessário notificar os entrevistados que há questionários disponíveis para eles.</span><span class="sxs-lookup"><span data-stu-id="f10bd-169">When you distribute a questionnaire, you must notify respondents that questionnaires are available to them.</span></span> 

### <a name="notifying-respondents-about-a-planned-answer-session"></a><span data-ttu-id="f10bd-170">Notificando os participantes sobre uma sessão de respostas planejadas</span><span class="sxs-lookup"><span data-stu-id="f10bd-170">Notifying respondents about a planned answer session</span></span>

<span data-ttu-id="f10bd-171">Se você usar uma sessão de resposta planejadas, você deve notificar a pessoa diretamente, por telefone ou email.</span><span class="sxs-lookup"><span data-stu-id="f10bd-171">If you use a planned answer session, you must notify the person directly, such as by telephone or email.</span></span>

### <a name="notifying-respondents-about-a-scheduling"></a><span data-ttu-id="f10bd-172">Notificando participantes sobre um planejamento</span><span class="sxs-lookup"><span data-stu-id="f10bd-172">Notifying respondents about a scheduling</span></span>

<span data-ttu-id="f10bd-173">Use a página **Agendas de questionário** para preparar e enviar um email a todos os entrevistados atribuídos ao questionário.</span><span class="sxs-lookup"><span data-stu-id="f10bd-173">Use the **Questionnaire schedules** page to prepare and send email to all respondents who are assigned to the questionnaire.</span></span> <span data-ttu-id="f10bd-174">Insira o texto do email na guia **Email para o autoatendimento para funcionários**. Depois que a agenda for iniciada, clique em **Funções** &gt; **Enviar email** para gerar e enviar o email para os entrevistados.</span><span class="sxs-lookup"><span data-stu-id="f10bd-174">Enter the email text on the **E-mail for employee self service** tab. After the schedule has been started, click **Functions** &gt; **Send e-mail** to generate and send the email to the respondents.</span></span> <span data-ttu-id="f10bd-175">Os entrevistados poderão efetuar logon no site e preencher o questionário.</span><span class="sxs-lookup"><span data-stu-id="f10bd-175">Respondents can then sign in to the website and complete the questionnaire.</span></span> 

> <span data-ttu-id="f10bd-176">**Observação** Antes que você possa usar a funcionalidade de email, o administrador de TI deverá inserir as configurações de email na página **Parâmetros de email**.</span><span class="sxs-lookup"><span data-stu-id="f10bd-176">**Note** Before you can use the email functionality, your IT administrator must enter the email settings on the **E-mail parameters** page.</span></span>

## <a name="ending-a-scheduled-questionnaire"></a><span data-ttu-id="f10bd-177">Finalizando um questionário planejado</span><span class="sxs-lookup"><span data-stu-id="f10bd-177">Ending a scheduled questionnaire</span></span>
<span data-ttu-id="f10bd-178">É possível encerrar um questionário planejado depois que todos os participantes concluírem as sessões de resposta atribuídas a eles.</span><span class="sxs-lookup"><span data-stu-id="f10bd-178">You can end a scheduled questionnaire after all respondents have completed their assigned answer sessions.</span></span> <span data-ttu-id="f10bd-179">Depois que um questionário planejado for concluído, não será possível copiar as configurações para um novo agendamento.</span><span class="sxs-lookup"><span data-stu-id="f10bd-179">After a scheduled questionnaire is ended, you can't copy its settings to a new schedule.</span></span> 

> <span data-ttu-id="f10bd-180">**Observação** Caso um ou mais participantes não tenham preenchido o questionário e você ainda queira encerrar o agendamento, você deve primeiro excluir os participantes relevantes da lista na página **Sessão de respostas planejadas**.</span><span class="sxs-lookup"><span data-stu-id="f10bd-180">**Note** If one or more respondents haven't completed the questionnaire, but you still want to end the scheduling, you must first delete those respondents from the list on the **Planned answer session** page.</span></span> <span data-ttu-id="f10bd-181">Em seguida, será possível encerrar a agenda.</span><span class="sxs-lookup"><span data-stu-id="f10bd-181">You can then end the schedule.</span></span>

## <a name="completing-questionnaires"></a><span data-ttu-id="f10bd-182">Preenchendo questionários</span><span class="sxs-lookup"><span data-stu-id="f10bd-182">Completing questionnaires</span></span>
<span data-ttu-id="f10bd-183">Após criar e distribuir um questionário, este poderá ser preenchido por entrevistados selecionados.</span><span class="sxs-lookup"><span data-stu-id="f10bd-183">After you've designed and distributed a questionnaire, the questionnaire can be completed by selected respondents.</span></span> <span data-ttu-id="f10bd-184">Você pode preencher os questionários disponíveis para você em dois locais:</span><span class="sxs-lookup"><span data-stu-id="f10bd-184">You can complete the questionnaires that are available to you from two locations:</span></span>

-   <span data-ttu-id="f10bd-185">No painel de navegação, clique em **Questionários** &gt; **Distribuir** &gt; **Preencher um questionário**.</span><span class="sxs-lookup"><span data-stu-id="f10bd-185">In the navigation pane, click **Questionnaires** &gt; **Distribute** &gt; **Complete a questionnaire**.</span></span>
-   <span data-ttu-id="f10bd-186">No autoatendimento do funcionário, clique em **Questionários a serem concluídos**.</span><span class="sxs-lookup"><span data-stu-id="f10bd-186">In Employee self-service, click **Questionnaires to complete**.</span></span>

<span data-ttu-id="f10bd-187">Os questionários podem ficar disponíveis para usuários específicos, grupos de usuários ou todas as pessoas de uma rede.</span><span class="sxs-lookup"><span data-stu-id="f10bd-187">Questionnaires can made be available to specific users or groups of users, or to all users in a network.</span></span>

<a name="see-also"></a><span data-ttu-id="f10bd-188">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f10bd-188">See also</span></span>
--------

[<span data-ttu-id="f10bd-189">Projetar questionários</span><span class="sxs-lookup"><span data-stu-id="f10bd-189">Designing questionnaires</span></span>](design-questionnaires.md)

[<span data-ttu-id="f10bd-190">Usando questionários</span><span class="sxs-lookup"><span data-stu-id="f10bd-190">Using questionnaires</span></span>](questionnaires.md)

[<span data-ttu-id="f10bd-191">Exibindo e avaliando os resultados dos questionários</span><span class="sxs-lookup"><span data-stu-id="f10bd-191">Viewing and evaluating the results of questionnaires</span></span>](evaluate-questionnaire-results.md)



