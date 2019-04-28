---
title: Analisar resultados de questionário
description: As estatísticas do questionário podem ser usadas para calcular média, totais e porcentagens, com base em um conjunto de dados demográficos.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMQuestionnaireStatistics, KMQuestionnaireStatisticsLine
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2d8f9c2fcf0be117f8fcde5113c0d42f11786679
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "858574"
---
# <a name="analyzing-questionnaire-results"></a><span data-ttu-id="049ef-103">Analisar resultados de questionário</span><span class="sxs-lookup"><span data-stu-id="049ef-103">Analyzing questionnaire results</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="049ef-104">As estatísticas do questionário podem ser usadas para calcular média, totais e porcentagens, com base em um conjunto de dados demográficos.</span><span class="sxs-lookup"><span data-stu-id="049ef-104">Questionnaire statistics can be used to calculate averages, totals, and percentages based on a set of demographic data.</span></span> <span data-ttu-id="049ef-105">Para iniciar este procedimento, vá para Questionário > Exibir e analisar resultados > Estatísticas de questionário.</span><span class="sxs-lookup"><span data-stu-id="049ef-105">To begin this procedure, go to Questionnaire > View and analyze results > Questionnaire statistics.</span></span> <span data-ttu-id="049ef-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="049ef-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-questionnaire-statistics-record"></a><span data-ttu-id="049ef-107">Criar um registro de estatísticas de questionário</span><span class="sxs-lookup"><span data-stu-id="049ef-107">Create a Questionnaire statistics record</span></span>
1. <span data-ttu-id="049ef-108">Vá para Estatísticas do questionário.</span><span class="sxs-lookup"><span data-stu-id="049ef-108">Go to Questionnaire statistics.</span></span>
2. <span data-ttu-id="049ef-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="049ef-109">Click New.</span></span>
3. <span data-ttu-id="049ef-110">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="049ef-110">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="049ef-111">No campo Estatísticas, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="049ef-111">In the Statistics field, type a value.</span></span>
5. <span data-ttu-id="049ef-112">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="049ef-112">In the Description field, type a value.</span></span>
6. <span data-ttu-id="049ef-113">No campo Questionário, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="049ef-113">In the Questionnaire field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="049ef-114">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="049ef-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="049ef-115">Clique na guia Geral.</span><span class="sxs-lookup"><span data-stu-id="049ef-115">Click the General tab.</span></span>
    * <span data-ttu-id="049ef-116">Selecione se deseja incluir resultados anônimos ou resultados de trabalhadores, contatos e candidatos.</span><span class="sxs-lookup"><span data-stu-id="049ef-116">Select if you want to include anonymous results or results from workers, contacts, and applicants.</span></span>  
9. <span data-ttu-id="049ef-117">Marque ou desmarque a caixa de seleção Trabalhador.</span><span class="sxs-lookup"><span data-stu-id="049ef-117">Select or clear the Worker check box.</span></span>
    * <span data-ttu-id="049ef-118">Se você deseja exibir os resultados por tempo de serviço ou por idade, especifique os intervalos que você gostaria de usar para agrupar os resultados.</span><span class="sxs-lookup"><span data-stu-id="049ef-118">If you will be viewing the results by seniority or age, specify the intervals that you would like to use for grouping the results.</span></span>  
    * <span data-ttu-id="049ef-119">Inserindo um 5 para o intervalo de idade o agrupará com base nos resultados em intervalos de cinco anos de idade.</span><span class="sxs-lookup"><span data-stu-id="049ef-119">Entering a 5 for the age interval will group the results based on five-year age intervals.</span></span>  
10. <span data-ttu-id="049ef-120">No campo Idade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="049ef-120">In the Age field, enter a number.</span></span>
    * <span data-ttu-id="049ef-121">Selecione se você deseja executar o cálculo inteiro, em relação ao questionário para cada grupo de resultados, para cada pergunta ou para cada linha de pergunta.</span><span class="sxs-lookup"><span data-stu-id="049ef-121">Select if you want to run the calculation against the entire questionnaire, for each result group, for each question, or for each question row.</span></span>  
    * <span data-ttu-id="049ef-122">Selecione como gostaria de agrupas os resultados.</span><span class="sxs-lookup"><span data-stu-id="049ef-122">Select how you would like to group the results.</span></span>  
    * <span data-ttu-id="049ef-123">Por exemplo, se você calcular os pontos médios por pergunta, você pode desejar ver as perguntas agrupadas por grupo de resultados.</span><span class="sxs-lookup"><span data-stu-id="049ef-123">For example, if you calculate the average points per question, you may want to see the questions grouped by Result group.</span></span>  
    * <span data-ttu-id="049ef-124">Selecione os dados no qual basear o cálculo.</span><span class="sxs-lookup"><span data-stu-id="049ef-124">Select the data to base the calculation on.</span></span>  
    * <span data-ttu-id="049ef-125">Por exemplo, se você desejar ver a porcentagem média recebida no questionário por meio dos funcionários em relação ao número médio de pontos obtido por meio dos funcionários.</span><span class="sxs-lookup"><span data-stu-id="049ef-125">For example, if you want to see the average percent received on the questionnaire across your workers versus the average number of points achieved across your workers.</span></span>  
11. <span data-ttu-id="049ef-126">Clique na guia Variação.</span><span class="sxs-lookup"><span data-stu-id="049ef-126">Click the Range tab.</span></span>
    * <span data-ttu-id="049ef-127">Use intervalos para limitar o conjunto de resultados somente se essas atendem aos critérios do intervalo.</span><span class="sxs-lookup"><span data-stu-id="049ef-127">Use ranges to limit your result set to only those meeting the Range criteria.</span></span>  
12. <span data-ttu-id="049ef-128">Clique no Agrupamento por guia.</span><span class="sxs-lookup"><span data-stu-id="049ef-128">Click the Grouping by tab.</span></span>
    * <span data-ttu-id="049ef-129">Use grupos para determinar como os resultados serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="049ef-129">Use Groupings to determine how the results should be displayed.</span></span>  
    * <span data-ttu-id="049ef-130">Por exemplo, agrupar os resultados primeiro por gênero, então por idade.</span><span class="sxs-lookup"><span data-stu-id="049ef-130">For example, group the results first by gender, then by age.</span></span>  
13. <span data-ttu-id="049ef-131">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="049ef-131">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="049ef-132">Mova os agrupamentos no lado Selecionado e posicione-os na ordem desejada.</span><span class="sxs-lookup"><span data-stu-id="049ef-132">Move the groupings into the Selected side and place them in the desired order.</span></span>  

## <a name="execute-the-statistics-calculation"></a><span data-ttu-id="049ef-133">Executa o cálculo das estatísticas</span><span class="sxs-lookup"><span data-stu-id="049ef-133">Execute the statistics calculation</span></span>
1. <span data-ttu-id="049ef-134">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="049ef-134">Click Execute.</span></span>
    * <span data-ttu-id="049ef-135">Selecione a função de cálculo que você gostaria de executar nos resultados.</span><span class="sxs-lookup"><span data-stu-id="049ef-135">Select which calculation function you would like to perform on the results.</span></span>  
    * <span data-ttu-id="049ef-136">Por exemplo, calcule as porcentagens médio por meio do questionário para os agrupamentos selecionados ou o total de pontos por meio de grupos de resultados dos agrupamentos selecionados.</span><span class="sxs-lookup"><span data-stu-id="049ef-136">For example, calculate the average percentages across the questionnaire for the selected groupings or total the points across the result groups for the selected groupings.</span></span>  
2. <span data-ttu-id="049ef-137">Selecione ou limpe as caixas de seleção Excluir buscas anteriores.</span><span class="sxs-lookup"><span data-stu-id="049ef-137">Select or clear the Delete previous searches check box.</span></span>
3. <span data-ttu-id="049ef-138">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="049ef-138">Click OK.</span></span>

## <a name="view-the-results-of-the-questionnaire-statistics-run"></a><span data-ttu-id="049ef-139">Exiba os resultados da execução de estatísticas do questionário.</span><span class="sxs-lookup"><span data-stu-id="049ef-139">View the results of the questionnaire statistics run.</span></span>
1. <span data-ttu-id="049ef-140">Clique em Resultado.</span><span class="sxs-lookup"><span data-stu-id="049ef-140">Click Result.</span></span>
2. <span data-ttu-id="049ef-141">Clique em Resultado.</span><span class="sxs-lookup"><span data-stu-id="049ef-141">Click Result.</span></span>
3. <span data-ttu-id="049ef-142">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="049ef-142">Close the page.</span></span>

