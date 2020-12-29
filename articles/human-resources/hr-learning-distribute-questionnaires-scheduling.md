---
title: Distribuir questionários usando agendamento
description: A programação do questionário permite que você planeje e distribua questionários para vários participantes.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMKnowledgeCollectorPlanningTable, KMKnowledgeCollectorPlanningMulti, SysQueryForm, HcmPersonLookup, KMKnowledgeCollectorPlanning, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d233938fe553dbd7da7fcc5477097fd885665102
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4417346"
---
# <a name="distribute-questionnaires-using-scheduling"></a><span data-ttu-id="4e96d-103">Distribuir questionários usando agendamento</span><span class="sxs-lookup"><span data-stu-id="4e96d-103">Distribute questionnaires using scheduling</span></span>

<span data-ttu-id="4e96d-104">A programação do questionário permite que você planeje e distribua questionários para vários participantes.</span><span class="sxs-lookup"><span data-stu-id="4e96d-104">Questionnaire scheduling allows you to plan and distribute questionnaires to multiple respondents.</span></span> <span data-ttu-id="4e96d-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="4e96d-105">The demo data company used to create this procedure is USMF.</span></span>

## <a name="create-a-questionnaire-schedule"></a><span data-ttu-id="4e96d-106">Criar uma agenda de questionário</span><span class="sxs-lookup"><span data-stu-id="4e96d-106">Create a questionnaire schedule</span></span>

1. <span data-ttu-id="4e96d-107">Vá para Questionário > Distribuir > Agendas de questionário.</span><span class="sxs-lookup"><span data-stu-id="4e96d-107">Go to Questionnaire > Distribute > Questionnaire schedules.</span></span>

2. <span data-ttu-id="4e96d-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="4e96d-108">Click New.</span></span>

3. <span data-ttu-id="4e96d-109">No campo Agendamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="4e96d-109">In the Scheduling field, type a value.</span></span>

4. <span data-ttu-id="4e96d-110">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="4e96d-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="4e96d-111">Defina a agenda para Anônima se as respostas precisarem ser registradas sem nomes associados à resposta.</span><span class="sxs-lookup"><span data-stu-id="4e96d-111">Set the schedule to Anonymous if the responses should be recorded without names associated to the response.</span></span>  
    * <span data-ttu-id="4e96d-112">Permitir resultados anônimos deve estar configurado primeiro nos parâmetros de RH.</span><span class="sxs-lookup"><span data-stu-id="4e96d-112">Allowing anonymous results must be set up in the HR parameters first.</span></span>  

5. <span data-ttu-id="4e96d-113">No campo Tipo, selecione o tipo de planejamento.</span><span class="sxs-lookup"><span data-stu-id="4e96d-113">In the Type field, select the planning type.</span></span>  <span data-ttu-id="4e96d-114">Neste exemplo, usaremos o tipo Satisfação.</span><span class="sxs-lookup"><span data-stu-id="4e96d-114">In this example we will use the Satisfaction type.</span></span>

6. <span data-ttu-id="4e96d-115">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="4e96d-115">In the list, find and select the desired record.</span></span>

7. <span data-ttu-id="4e96d-116">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="4e96d-116">In the list, click the link in the selected row.</span></span>

8. <span data-ttu-id="4e96d-117">No campo Data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="4e96d-117">In the Date field, enter a date.</span></span>

9. <span data-ttu-id="4e96d-118">Expanda a seção Email para autoatendimento de funcionários.</span><span class="sxs-lookup"><span data-stu-id="4e96d-118">Expand the Email for employee self service section.</span></span>

10. <span data-ttu-id="4e96d-119">No campo Assunto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="4e96d-119">In the Subject field, type a value.</span></span>

    * <span data-ttu-id="4e96d-120">Exemplo: questionário disponível</span><span class="sxs-lookup"><span data-stu-id="4e96d-120">Example: Questionnaire available</span></span>  

11. <span data-ttu-id="4e96d-121">No campo Texto, digite o corpo da mensagem do seu email.</span><span class="sxs-lookup"><span data-stu-id="4e96d-121">In the Text field, type the body of your email message.</span></span> <span data-ttu-id="4e96d-122">Observe que a variável pode ser usada para substituir valores no sistema.</span><span class="sxs-lookup"><span data-stu-id="4e96d-122">Note, the variable can be used to substitue values in the system.</span></span>

    * <span data-ttu-id="4e96d-123">Exemplo: Prezado(a) %P%, faça logon no Autoatendimento para funcionários para concluir o questionário sobre saúde da força de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4e96d-123">Example: Dear %P%, Please log in to Employee Self Service to complete the Workforce Health questionnaire.</span></span>  <span data-ttu-id="4e96d-124">Contoso</span><span class="sxs-lookup"><span data-stu-id="4e96d-124">Contoso</span></span>  

12. <span data-ttu-id="4e96d-125">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="4e96d-125">Click Save.</span></span>

## <a name="use-the-setup-details-to-select-the-questionnaires-to-be-answered-as-well-as-any-queries-to-use-to-select-respondents"></a><span data-ttu-id="4e96d-126">Use os detalhes de configuração para selecionar os questionários a serem respondidos assim como algumas consultas a serem usadas para selecionar participantes.</span><span class="sxs-lookup"><span data-stu-id="4e96d-126">Use the Setup details to select the questionnaire(s) to be answered as well as any queries to use to select respondents.</span></span>

1. <span data-ttu-id="4e96d-127">Clique em Detalhes da configuração.</span><span class="sxs-lookup"><span data-stu-id="4e96d-127">Click Setup details.</span></span>

2. <span data-ttu-id="4e96d-128">Na lista, selecione uma consulta que será usada para encontrar participantes para o questionário no sistema.</span><span class="sxs-lookup"><span data-stu-id="4e96d-128">In the list, select a query to use to search the system for respondents for the questionnaire.</span></span>

    * <span data-ttu-id="4e96d-129">Example: trabalhadores</span><span class="sxs-lookup"><span data-stu-id="4e96d-129">Example: Workers</span></span>  

3. <span data-ttu-id="4e96d-130">Clique em Exibir ou modificar consulta para selecionar pessoas específicas ou ajustar a consulta para encontrar pessoas que atendem aos critérios específicos.</span><span class="sxs-lookup"><span data-stu-id="4e96d-130">Click View or modify query to select specific people or adjust the query to find people who match specific criteria.</span></span>

    * <span data-ttu-id="4e96d-131">Observe que todos os participantes devem ser usuários do sistema.</span><span class="sxs-lookup"><span data-stu-id="4e96d-131">Note that all respondents must also be users in the system.</span></span>  

4. <span data-ttu-id="4e96d-132">Na lista, marque a linha para pessoa.</span><span class="sxs-lookup"><span data-stu-id="4e96d-132">In the list, mark the row for Person</span></span>

5. <span data-ttu-id="4e96d-133">No campo Critérios, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="4e96d-133">In the Criteria field, enter or select a value.</span></span>

    * <span data-ttu-id="4e96d-134">Selecione Julia Funderburk</span><span class="sxs-lookup"><span data-stu-id="4e96d-134">Select Julia Funderburk</span></span>  

6. <span data-ttu-id="4e96d-135">Na lista, selecione Julia Funderburk</span><span class="sxs-lookup"><span data-stu-id="4e96d-135">In the list, select Julia Funderburk</span></span>

7. <span data-ttu-id="4e96d-136">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4e96d-136">Click OK.</span></span>

8. <span data-ttu-id="4e96d-137">Clique na guia Questionários.</span><span class="sxs-lookup"><span data-stu-id="4e96d-137">Click the Questionnaires tab.</span></span>

9. <span data-ttu-id="4e96d-138">Na árvore, expanda "o nó da pesquisa de satisfação do tipo de questionário".</span><span class="sxs-lookup"><span data-stu-id="4e96d-138">In the tree, expand 'the node for the questionnaire type Satisfaction Survey'.</span></span>

10. <span data-ttu-id="4e96d-139">Na árvore, verifique "Avaliação da saúde da força de trabalho".</span><span class="sxs-lookup"><span data-stu-id="4e96d-139">In the tree, check 'Workforce Health Assessment'.</span></span>

11. <span data-ttu-id="4e96d-140">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4e96d-140">Click OK.</span></span>

12. <span data-ttu-id="4e96d-141">Clique em Sessão de respostas planejadas.</span><span class="sxs-lookup"><span data-stu-id="4e96d-141">Click Planned answer session.</span></span>

    * <span data-ttu-id="4e96d-142">Observe que as sessões de respostas planejadas são criadas para cada usuário selecionado/consultado.</span><span class="sxs-lookup"><span data-stu-id="4e96d-142">Note that Planned answer sessions have been created for each selected/queried user.</span></span>  

13. <span data-ttu-id="4e96d-143">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4e96d-143">Close the page.</span></span>

## <a name="start-the-questionnaire-schedule-in-order-to-make-the-questionnaire-available-for-respondents-to-complete"></a><span data-ttu-id="4e96d-144">Inicie a agenda de questionário para disponibilizar o questionário para que os participantes o concluam.</span><span class="sxs-lookup"><span data-stu-id="4e96d-144">Start the questionnaire schedule in order to make the questionnaire available for respondents to complete.</span></span>

1. <span data-ttu-id="4e96d-145">Clique em Funções.</span><span class="sxs-lookup"><span data-stu-id="4e96d-145">Click Functions.</span></span>

2. <span data-ttu-id="4e96d-146">Clique em Iniciar.</span><span class="sxs-lookup"><span data-stu-id="4e96d-146">Click Start.</span></span>

3. <span data-ttu-id="4e96d-147">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4e96d-147">Click OK.</span></span>

## <a name="send-the-email-to-inform-respondents-of-the-available-questionnaire"></a><span data-ttu-id="4e96d-148">Envie email para informar os participantes sobre o questionário disponível.</span><span class="sxs-lookup"><span data-stu-id="4e96d-148">Send the email to inform respondents of the available questionnaire.</span></span>

1. <span data-ttu-id="4e96d-149">Clique em Funções.</span><span class="sxs-lookup"><span data-stu-id="4e96d-149">Click Functions.</span></span>

2. <span data-ttu-id="4e96d-150">Clique em Enviar email.</span><span class="sxs-lookup"><span data-stu-id="4e96d-150">Click Send email.</span></span>

3. <span data-ttu-id="4e96d-151">Clique em Cancelar.</span><span class="sxs-lookup"><span data-stu-id="4e96d-151">Click Cancel.</span></span>

## <a name="use-planned-answer-sessions-to-monitor-who-needs-to-complete-the-questionnaire"></a><span data-ttu-id="4e96d-152">Use sessões de respostas planejadas para monitorar quem precisa preencher o questionário.</span><span class="sxs-lookup"><span data-stu-id="4e96d-152">Use Planned answer sessions to monitor who needs to complete the questionnaire.</span></span>

1. <span data-ttu-id="4e96d-153">Clique em Sessão de respostas planejadas.</span><span class="sxs-lookup"><span data-stu-id="4e96d-153">Click Planned answer session.</span></span>

    * <span data-ttu-id="4e96d-154">Excluir todas as sessões de respostas planejadas pendentes quando estiver pronto para encerrar a sessão planejada.</span><span class="sxs-lookup"><span data-stu-id="4e96d-154">Delete any remaining planned answer session when you're ready to end the scheduled session.</span></span>  

2. <span data-ttu-id="4e96d-155">Clique em Excluir.</span><span class="sxs-lookup"><span data-stu-id="4e96d-155">Click Delete.</span></span>

3. <span data-ttu-id="4e96d-156">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="4e96d-156">Click Yes.</span></span>

4. <span data-ttu-id="4e96d-157">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4e96d-157">Close the page.</span></span>

## <a name="end-the-schedule-when-all-respondents-have-completed-the-questionnaire-andor-all-remaining-planned-answer-sessions-have-been-deleted"></a><span data-ttu-id="4e96d-158">Encerre a agenda quando todos os entrevistados tiverem concluído o questionário e/ou todas as sessões de respostas planejadas restantes tiverem sido excluídas.</span><span class="sxs-lookup"><span data-stu-id="4e96d-158">End the schedule when all respondents have completed the questionnaire and/or all remaining Planned answer sessions have been deleted.</span></span>

1. <span data-ttu-id="4e96d-159">Clique em Funções.</span><span class="sxs-lookup"><span data-stu-id="4e96d-159">Click Functions.</span></span>
2. <span data-ttu-id="4e96d-160">Clique em Finalizar.</span><span class="sxs-lookup"><span data-stu-id="4e96d-160">Click End.</span></span>
3. <span data-ttu-id="4e96d-161">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4e96d-161">Click OK.</span></span>

