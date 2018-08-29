--- 
title: "Executar formatos de relatórios eletrônicos (ER) para contagem e soma"
description: "As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para fazer a contagem e soma com base nos dados já gerados do texto de saída."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: c6d309416a3a0c4da07a76c90246f492585deef5
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---
# <a name="run-electronic-reporting-er-formats-to-do-counting-and-summing"></a><span data-ttu-id="67fc1-103">Executar formatos de relatórios eletrônicos (ER) para contagem e soma</span><span class="sxs-lookup"><span data-stu-id="67fc1-103">Run Electronic reporting (ER) formats to do counting and summing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="67fc1-104">As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para fazer a contagem e soma com base nos dados já gerados do texto de saída.</span><span class="sxs-lookup"><span data-stu-id="67fc1-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="67fc1-105">Essas etapas podem ser executadas na empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="67fc1-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="67fc1-106">Para concluir estas etapas, primeiramente você deve concluir as etapas no procedimento "ER Configurar o formato para fazer a contagem e soma (Parte 3: usar cálculos para criar a saída)".</span><span class="sxs-lookup"><span data-stu-id="67fc1-106">To complete these steps, you must first complete the steps in the “ER Configure format to do counting and summing (Part 3: Use computations to make the output)” procedure.</span></span>

<span data-ttu-id="67fc1-107">Este procedimento é para um recurso que foi adicionado à versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="67fc1-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="test-this-configuration-for-generation-of-the-intrastat-reports"></a><span data-ttu-id="67fc1-108">Testar esta configuração para a geração de relatórios intrastat</span><span class="sxs-lookup"><span data-stu-id="67fc1-108">Test this configuration for generation of the Intrastat reports</span></span>
1. <span data-ttu-id="67fc1-109">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="67fc1-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="67fc1-110">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="67fc1-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="67fc1-111">Na árvore, expanda 'Modelo intrastat'.</span><span class="sxs-lookup"><span data-stu-id="67fc1-111">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="67fc1-112">Na árvore, expanda 'Modelo intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="67fc1-112">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="67fc1-113">Na árvore, selecione "Modelo intrastat\Intrastat (DE)\Intrastat (DE) com contagem e soma".</span><span class="sxs-lookup"><span data-stu-id="67fc1-113">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="67fc1-114">No Painel de Ação, clique em Configurações.</span><span class="sxs-lookup"><span data-stu-id="67fc1-114">On the Action Pane, click Configurations.</span></span>
7. <span data-ttu-id="67fc1-115">Clique em Parâmetros de usuário.</span><span class="sxs-lookup"><span data-stu-id="67fc1-115">Click User parameters.</span></span>
8. <span data-ttu-id="67fc1-116">Selecione Sim no campo Executar configurações.</span><span class="sxs-lookup"><span data-stu-id="67fc1-116">Select Yes in the Run settings field.</span></span>
9. <span data-ttu-id="67fc1-117">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="67fc1-117">Click OK.</span></span>
10. <span data-ttu-id="67fc1-118">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="67fc1-118">Click Edit.</span></span>
11. <span data-ttu-id="67fc1-119">Selecione Sim no campo Executar Rascunho.</span><span class="sxs-lookup"><span data-stu-id="67fc1-119">Select Yes in the Run Draft field.</span></span>
12. <span data-ttu-id="67fc1-120">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="67fc1-120">Click Save.</span></span>
13. <span data-ttu-id="67fc1-121">Vá para Imposto > Configuração > Comércio exterior > Parâmetros de comércio exterior.</span><span class="sxs-lookup"><span data-stu-id="67fc1-121">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
14. <span data-ttu-id="67fc1-122">Expanda a seção Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="67fc1-122">Expand the Electronic reporting section.</span></span>
15. <span data-ttu-id="67fc1-123">Selecione a configuração "Intrastat (DE) com contagem e soma".</span><span class="sxs-lookup"><span data-stu-id="67fc1-123">Select the “Intrastat (DE) with counting & summing” configuration.</span></span>
16. <span data-ttu-id="67fc1-124">Selecione a configuração "Intrastat (DE) com contagem e soma".</span><span class="sxs-lookup"><span data-stu-id="67fc1-124">Select the “Intrastat (DE) with counting & summing” configuration.</span></span>
17. <span data-ttu-id="67fc1-125">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="67fc1-125">Click Save.</span></span>
18. <span data-ttu-id="67fc1-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="67fc1-126">Close the page.</span></span>
19. <span data-ttu-id="67fc1-127">Vá para Imposto > Declarações > Comércio exterior > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="67fc1-127">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
20. <span data-ttu-id="67fc1-128">Clique em Saída.</span><span class="sxs-lookup"><span data-stu-id="67fc1-128">Click Output.</span></span>
21. <span data-ttu-id="67fc1-129">Clique em Relatório.</span><span class="sxs-lookup"><span data-stu-id="67fc1-129">Click Report.</span></span>
    * <span data-ttu-id="67fc1-130">Execute o processo de geração de relatórios intrastat.</span><span class="sxs-lookup"><span data-stu-id="67fc1-130">Run the Intrastat report generation process.</span></span>  
22. <span data-ttu-id="67fc1-131">No campo Data inicial, defina a data como '01-01-2000'.</span><span class="sxs-lookup"><span data-stu-id="67fc1-131">In the From date field, set the date to '2000-01-01'.</span></span>
    * <span data-ttu-id="67fc1-132">Defina as datas inicial e final para o período do relatório que incluam a existente nas transações do formulário.</span><span class="sxs-lookup"><span data-stu-id="67fc1-132">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
23. <span data-ttu-id="67fc1-133">No campo Data final, defina a data como '31-12-2022'.</span><span class="sxs-lookup"><span data-stu-id="67fc1-133">In the To date field, set the date to '2022-12-31'.</span></span>
    * <span data-ttu-id="67fc1-134">Defina as datas inicial e final para o período do relatório que incluam a existente nas transações do formulário.</span><span class="sxs-lookup"><span data-stu-id="67fc1-134">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
24. <span data-ttu-id="67fc1-135">No campo Direção, selecione 'Entradas'.</span><span class="sxs-lookup"><span data-stu-id="67fc1-135">In the Direction field, select 'Arrivals'.</span></span>
25. <span data-ttu-id="67fc1-136">Selecione Sim no campo Gerar arquivo.</span><span class="sxs-lookup"><span data-stu-id="67fc1-136">Select Yes in the Generate file field.</span></span>
26. <span data-ttu-id="67fc1-137">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="67fc1-137">Click OK.</span></span>
    * <span data-ttu-id="67fc1-138">Examine as saídas criadas com as linhas de resumo no final.</span><span class="sxs-lookup"><span data-stu-id="67fc1-138">Review the created output with the summary lines in the end.</span></span>  
27. <span data-ttu-id="67fc1-139">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="67fc1-139">Click New.</span></span>
28. <span data-ttu-id="67fc1-140">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="67fc1-140">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="67fc1-141">No campo Direção, selecione 'Expedições'.</span><span class="sxs-lookup"><span data-stu-id="67fc1-141">In the Direction field, select 'Dispatches'.</span></span>
30. <span data-ttu-id="67fc1-142">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="67fc1-142">In the Item number field, enter or select a value.</span></span>
31. <span data-ttu-id="67fc1-143">No campo Mercadoria, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="67fc1-143">In the Commodity field, enter or select a value.</span></span>
32. <span data-ttu-id="67fc1-144">Defina o peso como '10'.</span><span class="sxs-lookup"><span data-stu-id="67fc1-144">Set Weight to '10'.</span></span>
33. <span data-ttu-id="67fc1-145">Defina o valor da fatura como '10000'.</span><span class="sxs-lookup"><span data-stu-id="67fc1-145">Set Invoice amount to '10000'.</span></span>
34. <span data-ttu-id="67fc1-146">Defina o valor estatístico como '10000'.</span><span class="sxs-lookup"><span data-stu-id="67fc1-146">Set Statistical amount to '10000'.</span></span>
35. <span data-ttu-id="67fc1-147">Clique em Saída.</span><span class="sxs-lookup"><span data-stu-id="67fc1-147">Click Output.</span></span>
36. <span data-ttu-id="67fc1-148">Clique em Relatório.</span><span class="sxs-lookup"><span data-stu-id="67fc1-148">Click Report.</span></span>
37. <span data-ttu-id="67fc1-149">No campo Direção, selecione 'Expedições'.</span><span class="sxs-lookup"><span data-stu-id="67fc1-149">In the Direction field, select 'Dispatches'.</span></span>
38. <span data-ttu-id="67fc1-150">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="67fc1-150">Click OK.</span></span>
    * <span data-ttu-id="67fc1-151">Examine as saídas criadas com as linhas de resumo no final.</span><span class="sxs-lookup"><span data-stu-id="67fc1-151">Review the created output with the summary lines in the end.</span></span> <span data-ttu-id="67fc1-152">Observe que elas foram modificadas em comparação com a primeira execução.</span><span class="sxs-lookup"><span data-stu-id="67fc1-152">Note that it has been changed in comparison to the first run.</span></span>  

## <a name="run-this-configuration-in-debug-mode-to-review-the-collected-counting--summing-data"></a><span data-ttu-id="67fc1-153">Execute esta configuração no modo de depuração para analisar os dados de contagem e soma coletados</span><span class="sxs-lookup"><span data-stu-id="67fc1-153">Run this configuration in debug mode to review the collected counting & summing data</span></span>
1. <span data-ttu-id="67fc1-154">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="67fc1-154">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="67fc1-155">Na árvore, expanda 'Modelo intrastat'.</span><span class="sxs-lookup"><span data-stu-id="67fc1-155">In the tree, expand 'Intrastat model'.</span></span>
3. <span data-ttu-id="67fc1-156">Na árvore, expanda 'Modelo intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="67fc1-156">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
4. <span data-ttu-id="67fc1-157">Na árvore, selecione "Modelo intrastat\Intrastat (DE)\Intrastat (DE) com contagem e soma".</span><span class="sxs-lookup"><span data-stu-id="67fc1-157">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
5. <span data-ttu-id="67fc1-158">No Painel de Ação, clique em Configurações.</span><span class="sxs-lookup"><span data-stu-id="67fc1-158">On the Action Pane, click Configurations.</span></span>
6. <span data-ttu-id="67fc1-159">Clique em Parâmetros de usuário.</span><span class="sxs-lookup"><span data-stu-id="67fc1-159">Click User parameters.</span></span>
7. <span data-ttu-id="67fc1-160">Selecione Sim no campo Executar em modo de depuração.</span><span class="sxs-lookup"><span data-stu-id="67fc1-160">Select Yes in the Run in debug mode field.</span></span>
8. <span data-ttu-id="67fc1-161">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="67fc1-161">Click OK.</span></span>
9. <span data-ttu-id="67fc1-162">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="67fc1-162">Close the page.</span></span>
10. <span data-ttu-id="67fc1-163">Vá para Imposto > Declarações > Comércio exterior > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="67fc1-163">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
11. <span data-ttu-id="67fc1-164">Clique em Saída.</span><span class="sxs-lookup"><span data-stu-id="67fc1-164">Click Output.</span></span>
12. <span data-ttu-id="67fc1-165">Clique em Relatório.</span><span class="sxs-lookup"><span data-stu-id="67fc1-165">Click Report.</span></span>
13. <span data-ttu-id="67fc1-166">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="67fc1-166">Click OK.</span></span>
14. <span data-ttu-id="67fc1-167">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="67fc1-167">Close the page.</span></span>
15. <span data-ttu-id="67fc1-168">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="67fc1-168">Go to Organization administration > Electronic reporting > Configurations.</span></span>
16. <span data-ttu-id="67fc1-169">Na árvore, expanda 'Modelo intrastat'.</span><span class="sxs-lookup"><span data-stu-id="67fc1-169">In the tree, expand 'Intrastat model'.</span></span>
17. <span data-ttu-id="67fc1-170">Na árvore, expanda 'Modelo intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="67fc1-170">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
18. <span data-ttu-id="67fc1-171">Na árvore, selecione "Modelo intrastat\Intrastat (DE)\Intrastat (DE) com contagem e soma".</span><span class="sxs-lookup"><span data-stu-id="67fc1-171">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
19. <span data-ttu-id="67fc1-172">Clique em Logs de depuração.</span><span class="sxs-lookup"><span data-stu-id="67fc1-172">Click Debug logs.</span></span>
    * <span data-ttu-id="67fc1-173">Observe que um registro de log de depuração foi criado para o processo de execução da configuração selecionada.</span><span class="sxs-lookup"><span data-stu-id="67fc1-173">Note that a debug log record has been created for the execution process of the selected configuration.</span></span>  
20. <span data-ttu-id="67fc1-174">Clique em Anexar.</span><span class="sxs-lookup"><span data-stu-id="67fc1-174">Click Attach.</span></span>
21. <span data-ttu-id="67fc1-175">Clique em Abrir.</span><span class="sxs-lookup"><span data-stu-id="67fc1-175">Click Open.</span></span>
    * <span data-ttu-id="67fc1-176">Examine o arquivo XML criado que contém os detalhes da contagem e soma que foram coletados durante a execução da configuração selecionada.</span><span class="sxs-lookup"><span data-stu-id="67fc1-176">Review the created XML file that contains counting and summing details that were collected during the execution of the selected configuration.</span></span>  


