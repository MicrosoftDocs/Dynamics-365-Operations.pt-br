---
title: Manter informações de ferimentos e doenças de funcionários
description: É recomendável concluir a primeira guia de tarefas 'Configuração de lesões e doenças', pois algumas informações de configuração são usadas aqui.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMInjuryIncident, HcmWorkerLookUp
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4059a862ab38820c3b7b35dea5a55ac5c87791ca
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190318"
---
# <a name="maintain-employee-injury-and-illness-information"></a><span data-ttu-id="906b2-103">Manter informações de ferimentos e doenças de funcionários</span><span class="sxs-lookup"><span data-stu-id="906b2-103">Maintain employee injury and illness information</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="906b2-104">É recomendável concluir a primeira guia de tarefas 'Configuração de lesões e doenças', pois algumas informações de configuração são usadas aqui.</span><span class="sxs-lookup"><span data-stu-id="906b2-104">It is recommended to complete the 'Setup injury and illness' task guide first, as some of the setup information is used here.</span></span> 



<span data-ttu-id="906b2-105">Essa gravação de tarefa abrange as etapas básicas para criar um caso de ferimento ou de doença.</span><span class="sxs-lookup"><span data-stu-id="906b2-105">This task recording covers the basic steps to creating an injury or illness case.</span></span> <span data-ttu-id="906b2-106">Além de controlar os detalhes de ferimento ou de doença, há um status do caso que é rastreado também.</span><span class="sxs-lookup"><span data-stu-id="906b2-106">Besides tracking the details of the injury or illness, there is a case status that is tracked as well.</span></span>  <span data-ttu-id="906b2-107">Os padrões do caso com um status 'em aberto'.</span><span class="sxs-lookup"><span data-stu-id="906b2-107">The case defaults with an 'open' status.</span></span>  <span data-ttu-id="906b2-108">Os status podem ser gerenciados do item de menu "Status do caso" na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="906b2-108">The statuses can be managed from the 'Case status' menu item at the top of the page.</span></span>

1. <span data-ttu-id="906b2-109">Vá para Recursos humanos > Trabalhadores > Lesão e doença > Incidentes de lesão ou doença.</span><span class="sxs-lookup"><span data-stu-id="906b2-109">Go to Human resources > Workers > Injury and illness > Injury or illness incidents.</span></span>
2. <span data-ttu-id="906b2-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="906b2-110">Click New.</span></span>
3. <span data-ttu-id="906b2-111">No campo Descrição do caso, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="906b2-111">In the Case description field, type a value.</span></span>
    * <span data-ttu-id="906b2-112">Exemplo: Ferimento de pulso</span><span class="sxs-lookup"><span data-stu-id="906b2-112">Example:  Wrist injury</span></span>  
4. <span data-ttu-id="906b2-113">No campo Trabalhador, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="906b2-113">In the Worker field, enter or select a value.</span></span>
    * <span data-ttu-id="906b2-114">Exemplo: Ahmed Barnett</span><span class="sxs-lookup"><span data-stu-id="906b2-114">Example: Ahmed Barnett</span></span>  
5. <span data-ttu-id="906b2-115">No campo Data e hora do incidente, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="906b2-115">In the Date and time of incident field, enter a date and time.</span></span>
    * <span data-ttu-id="906b2-116">Exemplo: 20/01/2016 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="906b2-116">Example:  1/20/2016 10:00 AM</span></span>  
6. <span data-ttu-id="906b2-117">No campo do tipo de ferimento ou doença, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="906b2-117">In the Injury or illness type field, enter or select a value.</span></span>
    * <span data-ttu-id="906b2-118">Exemplo: Fratura</span><span class="sxs-lookup"><span data-stu-id="906b2-118">Example:  Fracture</span></span>  
7. <span data-ttu-id="906b2-119">No campo Parte do corpo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="906b2-119">In the Body part field, enter or select a value.</span></span>
    * <span data-ttu-id="906b2-120">Exemplo: Pulso</span><span class="sxs-lookup"><span data-stu-id="906b2-120">Example:  Wrist</span></span>  
8. <span data-ttu-id="906b2-121">No campo Tipo de resultado, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="906b2-121">In the Outcome type field, enter or select a value.</span></span>
    * <span data-ttu-id="906b2-122">Exemplo: Terapia</span><span class="sxs-lookup"><span data-stu-id="906b2-122">Example:  Therapy</span></span>  
9. <span data-ttu-id="906b2-123">No campo Data e hora relatadas, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="906b2-123">In the Date and time reported field, enter a date and time.</span></span>
    * <span data-ttu-id="906b2-124">A data e a hora reportadas devem ser posteriores à data e à hora do incidente.</span><span class="sxs-lookup"><span data-stu-id="906b2-124">The date and time reported must be later than the date and time of incident.</span></span>  
10. <span data-ttu-id="906b2-125">No campo Pessoa que relatou o caso, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="906b2-125">In the Person who reported case field, enter or select a value.</span></span>
    * <span data-ttu-id="906b2-126">Pode ser o funcionário ou outra testemunha do incidente.</span><span class="sxs-lookup"><span data-stu-id="906b2-126">This could be the employee or another witness to the incident.</span></span>  <span data-ttu-id="906b2-127">Exemplo: Ahmed Barnett</span><span class="sxs-lookup"><span data-stu-id="906b2-127">Example: Ahmed Barnett</span></span>  
11. <span data-ttu-id="906b2-128">Expanda a seção Incidente.</span><span class="sxs-lookup"><span data-stu-id="906b2-128">Expand the Incident section.</span></span>
12. <span data-ttu-id="906b2-129">No campo Onde o incidente ocorreu, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="906b2-129">In the Where incident occurred field, type a value.</span></span>
    * <span data-ttu-id="906b2-130">Exemplo: Depósito</span><span class="sxs-lookup"><span data-stu-id="906b2-130">Example:  Warehouse</span></span>  
13. <span data-ttu-id="906b2-131">Selecione Sim no campo Em locais de trabalho.</span><span class="sxs-lookup"><span data-stu-id="906b2-131">Select Yes in the On work premises field.</span></span>
    * <span data-ttu-id="906b2-132">Se o incidente ocorreu nos locais de trabalho, selecione Sim.</span><span class="sxs-lookup"><span data-stu-id="906b2-132">If the incident occurred on work premises, select yes.</span></span>  
14. <span data-ttu-id="906b2-133">No campo A data e hora de início do trabalho, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="906b2-133">In the Date and time began work field, enter a date and time.</span></span>
    * <span data-ttu-id="906b2-134">Insira a data e a hora em que a pessoa afetada começou a trabalhar, antes de ocorrer o incidente.</span><span class="sxs-lookup"><span data-stu-id="906b2-134">Enter the date and time that affected individual started working, prior to the incident occurring.</span></span>  
15. <span data-ttu-id="906b2-135">No campo Trabalho ou tarefa do funcionário, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="906b2-135">In the Employee job or task field, type a value.</span></span>
    * <span data-ttu-id="906b2-136">Informe o trabalho ou a tarefa que o trabalhador estava executando quando ocorreu o incidente.</span><span class="sxs-lookup"><span data-stu-id="906b2-136">Enter the job or task the worker was performing when the incident occurred.</span></span>  <span data-ttu-id="906b2-137">Exemplo: Caixas de carga</span><span class="sxs-lookup"><span data-stu-id="906b2-137">Example:  Loading boxes</span></span>  
16. <span data-ttu-id="906b2-138">No campo Causa do incidente, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="906b2-138">In the Cause of incident field, type a value.</span></span>
    * <span data-ttu-id="906b2-139">Insira a causa do incidente.</span><span class="sxs-lookup"><span data-stu-id="906b2-139">Enter the cause of the incident.</span></span>  <span data-ttu-id="906b2-140">Exemplo: Deslizou no chão molhado</span><span class="sxs-lookup"><span data-stu-id="906b2-140">Example:  Slipped on wet floor</span></span>  
17. <span data-ttu-id="906b2-141">No campo Nível de gravidade, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="906b2-141">In the Severity level field, enter or select a value.</span></span>
18. <span data-ttu-id="906b2-142">No campo Ação a ser tomada, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="906b2-142">In the Action to be taken field, type a value.</span></span>
    * <span data-ttu-id="906b2-143">Exemplo: Limpar derramamentos prontamente</span><span class="sxs-lookup"><span data-stu-id="906b2-143">Example:  Clean up spills promptly</span></span>  
19. <span data-ttu-id="906b2-144">No campo Dias esperados longe de trabalho, insira um número.</span><span class="sxs-lookup"><span data-stu-id="906b2-144">In the Expected days away from work field, enter a number.</span></span>
    * <span data-ttu-id="906b2-145">Insira o número de dias que era esperado que a pessoas ficasse fora do trabalho.</span><span class="sxs-lookup"><span data-stu-id="906b2-145">Enter the number of days that the individual is expected to be away from work.</span></span>  <span data-ttu-id="906b2-146">Depois que a pessoa retornar ao trabalho, atualize o campo 'Dias de afastamento do trabalho' com o número real de dias de afastamento.</span><span class="sxs-lookup"><span data-stu-id="906b2-146">Once the individual returns to work, update the 'Days away from work' field with the actual number of days away.</span></span>  
20. <span data-ttu-id="906b2-147">Expanda a seção Custos de lesões ou doenças.</span><span class="sxs-lookup"><span data-stu-id="906b2-147">Expand the Injury or illness costs section.</span></span>
21. <span data-ttu-id="906b2-148">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="906b2-148">Click Add.</span></span>
22. <span data-ttu-id="906b2-149">No campo Data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="906b2-149">In the Date field, enter a date.</span></span>
23. <span data-ttu-id="906b2-150">No campo Tipo de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="906b2-150">In the Cost type field, enter or select a value.</span></span>
    * <span data-ttu-id="906b2-151">Exemplo: Terapia. Você também pode inserir a um valor e anexar toda a documentação de suporte, como faturas e notas do médico ao custo.</span><span class="sxs-lookup"><span data-stu-id="906b2-151">Example:  Therapy    You can also enter in an amount, and attach any supporting documentation such as invoices or doctor's notes to the cost.</span></span>  
24. <span data-ttu-id="906b2-152">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="906b2-152">Click Add.</span></span>
25. <span data-ttu-id="906b2-153">No campo Data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="906b2-153">In the Date field, enter a date.</span></span>
26. <span data-ttu-id="906b2-154">No campo Tipo de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="906b2-154">In the Cost type field, enter or select a value.</span></span>
    * <span data-ttu-id="906b2-155">Por exemplo: Médico</span><span class="sxs-lookup"><span data-stu-id="906b2-155">Example: Doctor</span></span>  
27. <span data-ttu-id="906b2-156">Expanda a seção Tratamentos de lesões ou doenças.</span><span class="sxs-lookup"><span data-stu-id="906b2-156">Expand the Injury or illness treatments section.</span></span>
28. <span data-ttu-id="906b2-157">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="906b2-157">Click Add.</span></span>
29. <span data-ttu-id="906b2-158">No campo Data de tratamento, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="906b2-158">In the Treatment date field, enter a date and time.</span></span>
30. <span data-ttu-id="906b2-159">No campo Tipo de tratamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="906b2-159">In the Treatment type field, enter or select a value.</span></span>
    * <span data-ttu-id="906b2-160">Exemplo: Tala</span><span class="sxs-lookup"><span data-stu-id="906b2-160">Example:  Splint</span></span>  
31. <span data-ttu-id="906b2-161">Como opção, defina a seção Visita à sala de emergência do hospital como Sim.</span><span class="sxs-lookup"><span data-stu-id="906b2-161">Optionally, set the emergency room hospital visit section to Yes.</span></span>
32. <span data-ttu-id="906b2-162">No campo Comentários sobre o tratamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="906b2-162">In the Treatment comments field, type a value.</span></span>
    * <span data-ttu-id="906b2-163">Exemplo: Tala por 2 semanas</span><span class="sxs-lookup"><span data-stu-id="906b2-163">Example:  Splint for 2 weeks</span></span>  
33. <span data-ttu-id="906b2-164">No campo Nome do médico, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="906b2-164">In the Physician name field, type a value.</span></span>
    * <span data-ttu-id="906b2-165">Exemplo: Dr. Anderson</span><span class="sxs-lookup"><span data-stu-id="906b2-165">Example:  Dr. Anderson</span></span>  
34. <span data-ttu-id="906b2-166">No campo Instalação e localização de tratamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="906b2-166">In the Treatment facility and location field, type a value.</span></span>
    * <span data-ttu-id="906b2-167">Exemplo: Elm St. Emergência</span><span class="sxs-lookup"><span data-stu-id="906b2-167">Example:  Elm St. Emergency</span></span>  
35. <span data-ttu-id="906b2-168">No campo Detalhes do tratamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="906b2-168">In the Treatment details field, type a value.</span></span>
    * <span data-ttu-id="906b2-169">Exemplo: O raio X confirma a fratura, usar tala</span><span class="sxs-lookup"><span data-stu-id="906b2-169">Example:  Xray confirms fracture, wear splint</span></span>  
36. <span data-ttu-id="906b2-170">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="906b2-170">Click Save.</span></span>
    * <span data-ttu-id="906b2-171">O status do caso pode ser atualizado a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="906b2-171">The case status can be updated at any time.</span></span>  <span data-ttu-id="906b2-172">Defina o caso para em andamento, se o processamento do ferimento ou da doença estiver em andamento.</span><span class="sxs-lookup"><span data-stu-id="906b2-172">Set the case to in process, if the processing of the injury or illness is in process.</span></span>  <span data-ttu-id="906b2-173">Depois que fechar o incidente, você só poderá adicionar ou remover custos, tratamentos ou arquivamentos relacionados ao incidente.</span><span class="sxs-lookup"><span data-stu-id="906b2-173">Once you close the incident you can only add or remove costs, treatments or filings related to the incident.</span></span>  <span data-ttu-id="906b2-174">Para alterar outras informações, reabra o caso.</span><span class="sxs-lookup"><span data-stu-id="906b2-174">To modify other information, reopen the case.</span></span>  
