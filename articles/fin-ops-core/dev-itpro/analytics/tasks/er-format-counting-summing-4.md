---
title: ER Configurar o formato para fazer contagem e soma (Parte 4 - Executar formato)
description: Este tópico descreve como configurar um formato de relatório eletrônico para contar e somar com base nos dados da saída de texto já gerada. (Parte 4)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, IntrastatParameters, Intrastat, InventItemIdLookupSimple, IntrastatCommodityLookup, ERFormatMappingRunLogTable, DocuView
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2ca8449581edc06016b6e387880aad91087b67f1
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565408"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-4---run-format"></a><span data-ttu-id="14a04-104">ER Configurar o formato para fazer contagem e soma (Parte 4 - Executar formato)</span><span class="sxs-lookup"><span data-stu-id="14a04-104">ER Configure format to do counting and summing (Part 4 - Run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="14a04-105">As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para fazer a contagem e soma com base nos dados já gerados do texto de saída.</span><span class="sxs-lookup"><span data-stu-id="14a04-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="14a04-106">Essas etapas podem ser executadas na empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="14a04-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="14a04-107">Para concluir estas etapas, primeiramente conclua as etapas no procedimento "ER Configurar o formato para contagem e soma (Parte 3: usar cálculos para obter o resultado)".</span><span class="sxs-lookup"><span data-stu-id="14a04-107">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 3: Use computations to make the output)" procedure.</span></span>

<span data-ttu-id="14a04-108">Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="14a04-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="test-this-configuration-for-generation-of-the-intrastat-reports"></a><span data-ttu-id="14a04-109">Testar esta configuração para a geração de relatórios intrastat</span><span class="sxs-lookup"><span data-stu-id="14a04-109">Test this configuration for generation of the Intrastat reports</span></span>
1. <span data-ttu-id="14a04-110">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="14a04-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="14a04-111">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="14a04-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="14a04-112">Na árvore, expanda 'Modelo intrastat'.</span><span class="sxs-lookup"><span data-stu-id="14a04-112">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="14a04-113">Na árvore, expanda 'Modelo intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="14a04-113">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="14a04-114">Na árvore, selecione "Modelo intrastat\Intrastat (DE)\Intrastat (DE) com contagem e soma".</span><span class="sxs-lookup"><span data-stu-id="14a04-114">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="14a04-115">No Painel de Ação, clique em Configurações.</span><span class="sxs-lookup"><span data-stu-id="14a04-115">On the Action Pane, click Configurations.</span></span>
7. <span data-ttu-id="14a04-116">Clique em Parâmetros de usuário.</span><span class="sxs-lookup"><span data-stu-id="14a04-116">Click User parameters.</span></span>
8. <span data-ttu-id="14a04-117">Selecione Sim no campo Executar configurações.</span><span class="sxs-lookup"><span data-stu-id="14a04-117">Select Yes in the Run settings field.</span></span>
9. <span data-ttu-id="14a04-118">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="14a04-118">Click OK.</span></span>
10. <span data-ttu-id="14a04-119">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="14a04-119">Click Edit.</span></span>
11. <span data-ttu-id="14a04-120">Selecione Sim no campo Executar Rascunho.</span><span class="sxs-lookup"><span data-stu-id="14a04-120">Select Yes in the Run Draft field.</span></span>
12. <span data-ttu-id="14a04-121">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="14a04-121">Click Save.</span></span>
13. <span data-ttu-id="14a04-122">Vá para Imposto > Configuração > Comércio exterior > Parâmetros de comércio exterior.</span><span class="sxs-lookup"><span data-stu-id="14a04-122">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
14. <span data-ttu-id="14a04-123">Expanda a seção Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="14a04-123">Expand the Electronic reporting section.</span></span>
15. <span data-ttu-id="14a04-124">Selecione a configuração "Intrastat (DE) com contagem e soma".</span><span class="sxs-lookup"><span data-stu-id="14a04-124">Select the "Intrastat (DE) with counting & summing" configuration.</span></span>
16. <span data-ttu-id="14a04-125">Selecione a configuração "Intrastat (DE) com contagem e soma".</span><span class="sxs-lookup"><span data-stu-id="14a04-125">Select the "Intrastat (DE) with counting & summing" configuration.</span></span>
17. <span data-ttu-id="14a04-126">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="14a04-126">Click Save.</span></span>
18. <span data-ttu-id="14a04-127">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="14a04-127">Close the page.</span></span>
19. <span data-ttu-id="14a04-128">Vá para Imposto > Declarações > Comércio exterior > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="14a04-128">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
20. <span data-ttu-id="14a04-129">Clique em Saída.</span><span class="sxs-lookup"><span data-stu-id="14a04-129">Click Output.</span></span>
21. <span data-ttu-id="14a04-130">Clique em Relatório.</span><span class="sxs-lookup"><span data-stu-id="14a04-130">Click Report.</span></span>
    * <span data-ttu-id="14a04-131">Execute o processo de geração de relatórios intrastat.</span><span class="sxs-lookup"><span data-stu-id="14a04-131">Run the Intrastat report generation process.</span></span>  
22. <span data-ttu-id="14a04-132">No campo Data inicial, defina a data como '01-01-2000'.</span><span class="sxs-lookup"><span data-stu-id="14a04-132">In the From date field, set the date to '2000-01-01'.</span></span>
    * <span data-ttu-id="14a04-133">Defina as datas inicial e final para o período do relatório que incluam a existente nas transações do formulário.</span><span class="sxs-lookup"><span data-stu-id="14a04-133">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
23. <span data-ttu-id="14a04-134">No campo Data final, defina a data como '31-12-2022'.</span><span class="sxs-lookup"><span data-stu-id="14a04-134">In the To date field, set the date to '2022-12-31'.</span></span>
    * <span data-ttu-id="14a04-135">Defina as datas inicial e final para o período do relatório que incluam a existente nas transações do formulário.</span><span class="sxs-lookup"><span data-stu-id="14a04-135">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
24. <span data-ttu-id="14a04-136">No campo Direção, selecione 'Entradas'.</span><span class="sxs-lookup"><span data-stu-id="14a04-136">In the Direction field, select 'Arrivals'.</span></span>
25. <span data-ttu-id="14a04-137">Selecione Sim no campo Gerar arquivo.</span><span class="sxs-lookup"><span data-stu-id="14a04-137">Select Yes in the Generate file field.</span></span>
26. <span data-ttu-id="14a04-138">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="14a04-138">Click OK.</span></span>
    * <span data-ttu-id="14a04-139">Examine as saídas criadas com as linhas de resumo no final.</span><span class="sxs-lookup"><span data-stu-id="14a04-139">Review the created output with the summary lines in the end.</span></span>  
27. <span data-ttu-id="14a04-140">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="14a04-140">Click New.</span></span>
28. <span data-ttu-id="14a04-141">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="14a04-141">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="14a04-142">No campo Direção, selecione 'Expedições'.</span><span class="sxs-lookup"><span data-stu-id="14a04-142">In the Direction field, select 'Dispatches'.</span></span>
30. <span data-ttu-id="14a04-143">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="14a04-143">In the Item number field, enter or select a value.</span></span>
31. <span data-ttu-id="14a04-144">No campo Mercadoria, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="14a04-144">In the Commodity field, enter or select a value.</span></span>
32. <span data-ttu-id="14a04-145">Defina o peso como '10'.</span><span class="sxs-lookup"><span data-stu-id="14a04-145">Set Weight to '10'.</span></span>
33. <span data-ttu-id="14a04-146">Defina o valor da fatura como '10000'.</span><span class="sxs-lookup"><span data-stu-id="14a04-146">Set Invoice amount to '10000'.</span></span>
34. <span data-ttu-id="14a04-147">Defina o valor estatístico como '10000'.</span><span class="sxs-lookup"><span data-stu-id="14a04-147">Set Statistical amount to '10000'.</span></span>
35. <span data-ttu-id="14a04-148">Clique em Saída.</span><span class="sxs-lookup"><span data-stu-id="14a04-148">Click Output.</span></span>
36. <span data-ttu-id="14a04-149">Clique em Relatório.</span><span class="sxs-lookup"><span data-stu-id="14a04-149">Click Report.</span></span>
37. <span data-ttu-id="14a04-150">No campo Direção, selecione 'Expedições'.</span><span class="sxs-lookup"><span data-stu-id="14a04-150">In the Direction field, select 'Dispatches'.</span></span>
38. <span data-ttu-id="14a04-151">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="14a04-151">Click OK.</span></span>
    * <span data-ttu-id="14a04-152">Examine as saídas criadas com as linhas de resumo no final.</span><span class="sxs-lookup"><span data-stu-id="14a04-152">Review the created output with the summary lines in the end.</span></span> <span data-ttu-id="14a04-153">Observe que elas foram modificadas em comparação com a primeira execução.</span><span class="sxs-lookup"><span data-stu-id="14a04-153">Note that it has been changed in comparison to the first run.</span></span>  

## <a name="run-this-configuration-in-debug-mode-to-review-the-collected-counting--summing-data"></a><span data-ttu-id="14a04-154">Execute esta configuração no modo de depuração para analisar os dados de contagem e soma coletados</span><span class="sxs-lookup"><span data-stu-id="14a04-154">Run this configuration in debug mode to review the collected counting & summing data</span></span>
1. <span data-ttu-id="14a04-155">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="14a04-155">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="14a04-156">Na árvore, expanda 'Modelo intrastat'.</span><span class="sxs-lookup"><span data-stu-id="14a04-156">In the tree, expand 'Intrastat model'.</span></span>
3. <span data-ttu-id="14a04-157">Na árvore, expanda 'Modelo intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="14a04-157">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
4. <span data-ttu-id="14a04-158">Na árvore, selecione "Modelo intrastat\Intrastat (DE)\Intrastat (DE) com contagem e soma".</span><span class="sxs-lookup"><span data-stu-id="14a04-158">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
5. <span data-ttu-id="14a04-159">No Painel de Ação, clique em Configurações.</span><span class="sxs-lookup"><span data-stu-id="14a04-159">On the Action Pane, click Configurations.</span></span>
6. <span data-ttu-id="14a04-160">Clique em Parâmetros de usuário.</span><span class="sxs-lookup"><span data-stu-id="14a04-160">Click User parameters.</span></span>
7. <span data-ttu-id="14a04-161">Selecione Sim no campo Executar em modo de depuração.</span><span class="sxs-lookup"><span data-stu-id="14a04-161">Select Yes in the Run in debug mode field.</span></span>
8. <span data-ttu-id="14a04-162">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="14a04-162">Click OK.</span></span>
9. <span data-ttu-id="14a04-163">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="14a04-163">Close the page.</span></span>
10. <span data-ttu-id="14a04-164">Vá para Imposto > Declarações > Comércio exterior > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="14a04-164">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
11. <span data-ttu-id="14a04-165">Clique em Saída.</span><span class="sxs-lookup"><span data-stu-id="14a04-165">Click Output.</span></span>
12. <span data-ttu-id="14a04-166">Clique em Relatório.</span><span class="sxs-lookup"><span data-stu-id="14a04-166">Click Report.</span></span>
13. <span data-ttu-id="14a04-167">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="14a04-167">Click OK.</span></span>
14. <span data-ttu-id="14a04-168">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="14a04-168">Close the page.</span></span>
15. <span data-ttu-id="14a04-169">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="14a04-169">Go to Organization administration > Electronic reporting > Configurations.</span></span>
16. <span data-ttu-id="14a04-170">Na árvore, expanda 'Modelo intrastat'.</span><span class="sxs-lookup"><span data-stu-id="14a04-170">In the tree, expand 'Intrastat model'.</span></span>
17. <span data-ttu-id="14a04-171">Na árvore, expanda 'Modelo intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="14a04-171">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
18. <span data-ttu-id="14a04-172">Na árvore, selecione "Modelo intrastat\Intrastat (DE)\Intrastat (DE) com contagem e soma".</span><span class="sxs-lookup"><span data-stu-id="14a04-172">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
19. <span data-ttu-id="14a04-173">Clique em Logs de depuração.</span><span class="sxs-lookup"><span data-stu-id="14a04-173">Click Debug logs.</span></span>
    * <span data-ttu-id="14a04-174">Observe que um registro de log de depuração foi criado para o processo de execução da configuração selecionada.</span><span class="sxs-lookup"><span data-stu-id="14a04-174">Note that a debug log record has been created for the execution process of the selected configuration.</span></span>  
20. <span data-ttu-id="14a04-175">Clique em Anexar.</span><span class="sxs-lookup"><span data-stu-id="14a04-175">Click Attach.</span></span>
21. <span data-ttu-id="14a04-176">Clique em Abrir.</span><span class="sxs-lookup"><span data-stu-id="14a04-176">Click Open.</span></span>
    * <span data-ttu-id="14a04-177">Examine o arquivo XML criado que contém os detalhes da contagem e soma que foram coletados durante a execução da configuração selecionada.</span><span class="sxs-lookup"><span data-stu-id="14a04-177">Review the created XML file that contains counting and summing details that were collected during the execution of the selected configuration.</span></span>  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]