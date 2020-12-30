---
title: ER Configurar o formato para fazer contagem e soma (Parte 4 - Executar formato)
description: As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para fazer a contagem e soma com base nos dados já gerados do texto de saída.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, IntrastatParameters, Intrastat, InventItemIdLookupSimple, IntrastatCommodityLookup, ERFormatMappingRunLogTable, DocuView
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8f37fc3c611e9c5328f4d99be8c7c63ab59b2f08
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684634"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-4---run-format"></a><span data-ttu-id="73310-103">ER Configurar o formato para fazer contagem e soma (Parte 4 - Executar formato)</span><span class="sxs-lookup"><span data-stu-id="73310-103">ER Configure format to do counting and summing (Part 4 - Run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="73310-104">As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para fazer a contagem e soma com base nos dados já gerados do texto de saída.</span><span class="sxs-lookup"><span data-stu-id="73310-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="73310-105">Essas etapas podem ser executadas na empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="73310-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="73310-106">Para concluir estas etapas, primeiramente conclua as etapas no procedimento "ER Configurar o formato para contagem e soma (Parte 3: usar cálculos para obter o resultado)".</span><span class="sxs-lookup"><span data-stu-id="73310-106">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 3: Use computations to make the output)" procedure.</span></span>

<span data-ttu-id="73310-107">Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="73310-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="test-this-configuration-for-generation-of-the-intrastat-reports"></a><span data-ttu-id="73310-108">Testar esta configuração para a geração de relatórios intrastat</span><span class="sxs-lookup"><span data-stu-id="73310-108">Test this configuration for generation of the Intrastat reports</span></span>
1. <span data-ttu-id="73310-109">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="73310-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="73310-110">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="73310-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="73310-111">Na árvore, expanda 'Modelo intrastat'.</span><span class="sxs-lookup"><span data-stu-id="73310-111">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="73310-112">Na árvore, expanda 'Modelo intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="73310-112">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="73310-113">Na árvore, selecione "Modelo intrastat\Intrastat (DE)\Intrastat (DE) com contagem e soma".</span><span class="sxs-lookup"><span data-stu-id="73310-113">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="73310-114">No Painel de Ação, clique em Configurações.</span><span class="sxs-lookup"><span data-stu-id="73310-114">On the Action Pane, click Configurations.</span></span>
7. <span data-ttu-id="73310-115">Clique em Parâmetros de usuário.</span><span class="sxs-lookup"><span data-stu-id="73310-115">Click User parameters.</span></span>
8. <span data-ttu-id="73310-116">Selecione Sim no campo Executar configurações.</span><span class="sxs-lookup"><span data-stu-id="73310-116">Select Yes in the Run settings field.</span></span>
9. <span data-ttu-id="73310-117">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="73310-117">Click OK.</span></span>
10. <span data-ttu-id="73310-118">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="73310-118">Click Edit.</span></span>
11. <span data-ttu-id="73310-119">Selecione Sim no campo Executar Rascunho.</span><span class="sxs-lookup"><span data-stu-id="73310-119">Select Yes in the Run Draft field.</span></span>
12. <span data-ttu-id="73310-120">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="73310-120">Click Save.</span></span>
13. <span data-ttu-id="73310-121">Vá para Imposto > Configuração > Comércio exterior > Parâmetros de comércio exterior.</span><span class="sxs-lookup"><span data-stu-id="73310-121">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
14. <span data-ttu-id="73310-122">Expanda a seção Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="73310-122">Expand the Electronic reporting section.</span></span>
15. <span data-ttu-id="73310-123">Selecione a configuração "Intrastat (DE) com contagem e soma".</span><span class="sxs-lookup"><span data-stu-id="73310-123">Select the "Intrastat (DE) with counting & summing" configuration.</span></span>
16. <span data-ttu-id="73310-124">Selecione a configuração "Intrastat (DE) com contagem e soma".</span><span class="sxs-lookup"><span data-stu-id="73310-124">Select the "Intrastat (DE) with counting & summing" configuration.</span></span>
17. <span data-ttu-id="73310-125">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="73310-125">Click Save.</span></span>
18. <span data-ttu-id="73310-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="73310-126">Close the page.</span></span>
19. <span data-ttu-id="73310-127">Vá para Imposto > Declarações > Comércio exterior > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="73310-127">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
20. <span data-ttu-id="73310-128">Clique em Saída.</span><span class="sxs-lookup"><span data-stu-id="73310-128">Click Output.</span></span>
21. <span data-ttu-id="73310-129">Clique em Relatório.</span><span class="sxs-lookup"><span data-stu-id="73310-129">Click Report.</span></span>
    * <span data-ttu-id="73310-130">Execute o processo de geração de relatórios intrastat.</span><span class="sxs-lookup"><span data-stu-id="73310-130">Run the Intrastat report generation process.</span></span>  
22. <span data-ttu-id="73310-131">No campo Data inicial, defina a data como '01-01-2000'.</span><span class="sxs-lookup"><span data-stu-id="73310-131">In the From date field, set the date to '2000-01-01'.</span></span>
    * <span data-ttu-id="73310-132">Defina as datas inicial e final para o período do relatório que incluam a existente nas transações do formulário.</span><span class="sxs-lookup"><span data-stu-id="73310-132">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
23. <span data-ttu-id="73310-133">No campo Data final, defina a data como '31-12-2022'.</span><span class="sxs-lookup"><span data-stu-id="73310-133">In the To date field, set the date to '2022-12-31'.</span></span>
    * <span data-ttu-id="73310-134">Defina as datas inicial e final para o período do relatório que incluam a existente nas transações do formulário.</span><span class="sxs-lookup"><span data-stu-id="73310-134">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
24. <span data-ttu-id="73310-135">No campo Direção, selecione 'Entradas'.</span><span class="sxs-lookup"><span data-stu-id="73310-135">In the Direction field, select 'Arrivals'.</span></span>
25. <span data-ttu-id="73310-136">Selecione Sim no campo Gerar arquivo.</span><span class="sxs-lookup"><span data-stu-id="73310-136">Select Yes in the Generate file field.</span></span>
26. <span data-ttu-id="73310-137">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="73310-137">Click OK.</span></span>
    * <span data-ttu-id="73310-138">Examine as saídas criadas com as linhas de resumo no final.</span><span class="sxs-lookup"><span data-stu-id="73310-138">Review the created output with the summary lines in the end.</span></span>  
27. <span data-ttu-id="73310-139">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="73310-139">Click New.</span></span>
28. <span data-ttu-id="73310-140">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="73310-140">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="73310-141">No campo Direção, selecione 'Expedições'.</span><span class="sxs-lookup"><span data-stu-id="73310-141">In the Direction field, select 'Dispatches'.</span></span>
30. <span data-ttu-id="73310-142">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="73310-142">In the Item number field, enter or select a value.</span></span>
31. <span data-ttu-id="73310-143">No campo Mercadoria, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="73310-143">In the Commodity field, enter or select a value.</span></span>
32. <span data-ttu-id="73310-144">Defina o peso como '10'.</span><span class="sxs-lookup"><span data-stu-id="73310-144">Set Weight to '10'.</span></span>
33. <span data-ttu-id="73310-145">Defina o valor da fatura como '10000'.</span><span class="sxs-lookup"><span data-stu-id="73310-145">Set Invoice amount to '10000'.</span></span>
34. <span data-ttu-id="73310-146">Defina o valor estatístico como '10000'.</span><span class="sxs-lookup"><span data-stu-id="73310-146">Set Statistical amount to '10000'.</span></span>
35. <span data-ttu-id="73310-147">Clique em Saída.</span><span class="sxs-lookup"><span data-stu-id="73310-147">Click Output.</span></span>
36. <span data-ttu-id="73310-148">Clique em Relatório.</span><span class="sxs-lookup"><span data-stu-id="73310-148">Click Report.</span></span>
37. <span data-ttu-id="73310-149">No campo Direção, selecione 'Expedições'.</span><span class="sxs-lookup"><span data-stu-id="73310-149">In the Direction field, select 'Dispatches'.</span></span>
38. <span data-ttu-id="73310-150">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="73310-150">Click OK.</span></span>
    * <span data-ttu-id="73310-151">Examine as saídas criadas com as linhas de resumo no final.</span><span class="sxs-lookup"><span data-stu-id="73310-151">Review the created output with the summary lines in the end.</span></span> <span data-ttu-id="73310-152">Observe que elas foram modificadas em comparação com a primeira execução.</span><span class="sxs-lookup"><span data-stu-id="73310-152">Note that it has been changed in comparison to the first run.</span></span>  

## <a name="run-this-configuration-in-debug-mode-to-review-the-collected-counting--summing-data"></a><span data-ttu-id="73310-153">Execute esta configuração no modo de depuração para analisar os dados de contagem e soma coletados</span><span class="sxs-lookup"><span data-stu-id="73310-153">Run this configuration in debug mode to review the collected counting & summing data</span></span>
1. <span data-ttu-id="73310-154">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="73310-154">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="73310-155">Na árvore, expanda 'Modelo intrastat'.</span><span class="sxs-lookup"><span data-stu-id="73310-155">In the tree, expand 'Intrastat model'.</span></span>
3. <span data-ttu-id="73310-156">Na árvore, expanda 'Modelo intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="73310-156">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
4. <span data-ttu-id="73310-157">Na árvore, selecione "Modelo intrastat\Intrastat (DE)\Intrastat (DE) com contagem e soma".</span><span class="sxs-lookup"><span data-stu-id="73310-157">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
5. <span data-ttu-id="73310-158">No Painel de Ação, clique em Configurações.</span><span class="sxs-lookup"><span data-stu-id="73310-158">On the Action Pane, click Configurations.</span></span>
6. <span data-ttu-id="73310-159">Clique em Parâmetros de usuário.</span><span class="sxs-lookup"><span data-stu-id="73310-159">Click User parameters.</span></span>
7. <span data-ttu-id="73310-160">Selecione Sim no campo Executar em modo de depuração.</span><span class="sxs-lookup"><span data-stu-id="73310-160">Select Yes in the Run in debug mode field.</span></span>
8. <span data-ttu-id="73310-161">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="73310-161">Click OK.</span></span>
9. <span data-ttu-id="73310-162">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="73310-162">Close the page.</span></span>
10. <span data-ttu-id="73310-163">Vá para Imposto > Declarações > Comércio exterior > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="73310-163">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
11. <span data-ttu-id="73310-164">Clique em Saída.</span><span class="sxs-lookup"><span data-stu-id="73310-164">Click Output.</span></span>
12. <span data-ttu-id="73310-165">Clique em Relatório.</span><span class="sxs-lookup"><span data-stu-id="73310-165">Click Report.</span></span>
13. <span data-ttu-id="73310-166">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="73310-166">Click OK.</span></span>
14. <span data-ttu-id="73310-167">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="73310-167">Close the page.</span></span>
15. <span data-ttu-id="73310-168">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="73310-168">Go to Organization administration > Electronic reporting > Configurations.</span></span>
16. <span data-ttu-id="73310-169">Na árvore, expanda 'Modelo intrastat'.</span><span class="sxs-lookup"><span data-stu-id="73310-169">In the tree, expand 'Intrastat model'.</span></span>
17. <span data-ttu-id="73310-170">Na árvore, expanda 'Modelo intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="73310-170">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
18. <span data-ttu-id="73310-171">Na árvore, selecione "Modelo intrastat\Intrastat (DE)\Intrastat (DE) com contagem e soma".</span><span class="sxs-lookup"><span data-stu-id="73310-171">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
19. <span data-ttu-id="73310-172">Clique em Logs de depuração.</span><span class="sxs-lookup"><span data-stu-id="73310-172">Click Debug logs.</span></span>
    * <span data-ttu-id="73310-173">Observe que um registro de log de depuração foi criado para o processo de execução da configuração selecionada.</span><span class="sxs-lookup"><span data-stu-id="73310-173">Note that a debug log record has been created for the execution process of the selected configuration.</span></span>  
20. <span data-ttu-id="73310-174">Clique em Anexar.</span><span class="sxs-lookup"><span data-stu-id="73310-174">Click Attach.</span></span>
21. <span data-ttu-id="73310-175">Clique em Abrir.</span><span class="sxs-lookup"><span data-stu-id="73310-175">Click Open.</span></span>
    * <span data-ttu-id="73310-176">Examine o arquivo XML criado que contém os detalhes da contagem e soma que foram coletados durante a execução da configuração selecionada.</span><span class="sxs-lookup"><span data-stu-id="73310-176">Review the created XML file that contains counting and summing details that were collected during the execution of the selected configuration.</span></span>  

