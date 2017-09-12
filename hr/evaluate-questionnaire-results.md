---
title: "Exibir e avaliar os resultados de um questionário"
description: "Este tópico explica como você pode exibir e avaliar os resultados dos questionários que os entrevistados concluem."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KMCollection, KMKnowledgeCollectorCollection, KMKnowledgeCollectorUserResults
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 17444
ms.assetid: 6570206a-b2c4-4025-8715-432fe6652b78
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: b7c4a612d54f3ae8967be930c0b98e4783fd8200
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="view-and-evaluate-the-results-of-a-questionnaire"></a><span data-ttu-id="4e6be-103">Exibir e avaliar os resultados de um questionário</span><span class="sxs-lookup"><span data-stu-id="4e6be-103">View and evaluate the results of a questionnaire</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="4e6be-104">Este tópico explica como você pode exibir e avaliar os resultados dos questionários que os entrevistados concluem.</span><span class="sxs-lookup"><span data-stu-id="4e6be-104">This topic explains how you can view and evaluate the results of questionnaires that respondents complete.</span></span> 

<span data-ttu-id="4e6be-105">Depois que os entrevistados preencherem um questionário, você poderá exibir e avaliar os resultados do questionário das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="4e6be-105">After respondents complete a questionnaire, you can view and evaluate the questionnaire results in the following ways:</span></span>

-   <span data-ttu-id="4e6be-106">**Sessões de respostas concluídas** – Exiba detalhes sobre os questionários preenchidos pelos participantes e gere relatórios para resumir as respostas, e também quaisquer que sejam os pontos ganhos.</span><span class="sxs-lookup"><span data-stu-id="4e6be-106">**Completed answer sessions** – View details about the questionnaires that respondents have completed, and generate reports to summarize answers and any points that were earned.</span></span>
-   <span data-ttu-id="4e6be-107">**Grupos de resultados** – Exiba detalhes e estatísticas do grupo de resultados de questionários.</span><span class="sxs-lookup"><span data-stu-id="4e6be-107">**Result groups** – View result group details and statistics for questionnaires.</span></span> <span data-ttu-id="4e6be-108">As estatísticas do grupo de resultados podem ser geradas para uma única sessão de respostas de um questionário ou para todas as sessões de respostas.</span><span class="sxs-lookup"><span data-stu-id="4e6be-108">Result group statistics can be generated for either a single answer session  of a questionnaire or all answer sessions.</span></span>
-   <span data-ttu-id="4e6be-109">**Estatísticas do questionário** – Especifique os critérios para calcular estatísticas para um determinado grupo de entrevistados.</span><span class="sxs-lookup"><span data-stu-id="4e6be-109">**Questionnaire statistics** – Specify criteria to calculate statistics for a specific group of respondents.</span></span>

<span data-ttu-id="4e6be-110">Você também pode gerar diversos relatórios para exibir os resultados classificados por pessoa, por sessão de resposta ou por grupo de resultados.</span><span class="sxs-lookup"><span data-stu-id="4e6be-110">You can also generate various reports to view results that are sorted by person, answer session, or result group.</span></span> <span data-ttu-id="4e6be-111">Os seguintes relatórios referentes aos questionários preenchidos estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="4e6be-111">The following reports that are related to completed questionnaires are available:</span></span>

-   <span data-ttu-id="4e6be-112">Respostas</span><span class="sxs-lookup"><span data-stu-id="4e6be-112">Answers</span></span>
-   <span data-ttu-id="4e6be-113">Respostas por questionário</span><span class="sxs-lookup"><span data-stu-id="4e6be-113">Answers per questionnaire</span></span>
-   <span data-ttu-id="4e6be-114">Respostas por pessoa</span><span class="sxs-lookup"><span data-stu-id="4e6be-114">Answers per person</span></span>
-   <span data-ttu-id="4e6be-115">Análise de comentários</span><span class="sxs-lookup"><span data-stu-id="4e6be-115">Feedback analysis</span></span>

## <a name="answer-session-results"></a><span data-ttu-id="4e6be-116">Resultados da sessão de respostas</span><span class="sxs-lookup"><span data-stu-id="4e6be-116">Answer session results</span></span>
<span data-ttu-id="4e6be-117">Depois que os entrevistados preenchem o questionário, você pode exibir os resultados das sessões de respostas preenchidas.</span><span class="sxs-lookup"><span data-stu-id="4e6be-117">After respondents complete a questionnaire, you can view the results of the completed answer sessions.</span></span> <span data-ttu-id="4e6be-118">Uma sessão de resposta é a uma resposta do usuário a um questionário.</span><span class="sxs-lookup"><span data-stu-id="4e6be-118">An answer session is one user’s response to a questionnaire.</span></span> <span data-ttu-id="4e6be-119">Você pode exibir detalhes sobre as sessões de respostas preenchidas na página **Respostas**.</span><span class="sxs-lookup"><span data-stu-id="4e6be-119">You can view details about completed answer sessions on the **Answers** page.</span></span> <span data-ttu-id="4e6be-120">As sessões de respostas que estão inclusas na página **Respostas** serão filtradas de várias maneiras, dependendo de como você abrir a página:</span><span class="sxs-lookup"><span data-stu-id="4e6be-120">The answer sessions that are included on the **Answers** page are filtered in various ways, depending on how you open the page:</span></span>

-   <span data-ttu-id="4e6be-121">Todos os questionários</span><span class="sxs-lookup"><span data-stu-id="4e6be-121">All questionnaires</span></span>
-   <span data-ttu-id="4e6be-122">Um questionário específico</span><span class="sxs-lookup"><span data-stu-id="4e6be-122">A specific questionnaire</span></span>
-   <span data-ttu-id="4e6be-123">Uma pessoa específica</span><span class="sxs-lookup"><span data-stu-id="4e6be-123">A specific person</span></span>

<span data-ttu-id="4e6be-124">Na página **Respostas**, você pode exibir detalhes sobre respostas, pontos ganhos, respostas de um participante em cada grupo de resultados e a hierarquia de perguntas usadas no questionário selecionado, se uma hierarquia de perguntas tiver sido utilizada.</span><span class="sxs-lookup"><span data-stu-id="4e6be-124">From the **Answers** page, you can view details about answers, points that were earned, a respondent’s responses in each result group, and the question hierarchy that was used on the selected questionnaire, if a question hierarchy was used.</span></span> <span data-ttu-id="4e6be-125">Você também pode gerar e imprimir os seguintes relatórios:</span><span class="sxs-lookup"><span data-stu-id="4e6be-125">You can also generate and print the following reports:</span></span>

-   <span data-ttu-id="4e6be-126">**Relatório de resultados** – Este relatório mostra uma representação gráfica dos pontos obtidos por grupo de resultados para a sessão de respostas selecionada.</span><span class="sxs-lookup"><span data-stu-id="4e6be-126">**Results report** – This report shows a graphical representation of the points that were earned per result group for the selected answer session.</span></span>
-   <span data-ttu-id="4e6be-127">**Relatório de respostas** – Este relatório mostra as respostas que o participante selecionou para cada pergunta do questionário.</span><span class="sxs-lookup"><span data-stu-id="4e6be-127">**Answer report** – This report shows the answers that the respondent selected for each question on the questionnaire.</span></span>
-   <span data-ttu-id="4e6be-128">**Respostas incorretas** – Este relatório mostra informações relacionadas às respostas incorretas que o participante selecionou.</span><span class="sxs-lookup"><span data-stu-id="4e6be-128">**Incorrect answers** – This report shows information that is related to the incorrect answers that the respondent selected.</span></span>

> <span data-ttu-id="4e6be-129">**Observação**
>   O relatório **Resultados** está disponível somente se você usar grupos de resultados do questionário, e se você selecionou a **Página de resultados** na página **Questionários**.</span><span class="sxs-lookup"><span data-stu-id="4e6be-129">**Note**
  The **Results** report is available only if you use results groups on the questionnaire, and if you selected **Results page** on the **Questionnaires** page.</span></span> <span data-ttu-id="4e6be-130">O relatório de **Respostas** e o relatório de **Respostas incorretas** só estarão disponíveis se você selecionou **Relatório de respostas** na página **Questionários**.</span><span class="sxs-lookup"><span data-stu-id="4e6be-130">The **Answer** report and the **Incorrect answers** report are available only if you selected **Answer report** on the **Questionnaires** page.</span></span>

## <a name="questionnaire-statistics"></a><span data-ttu-id="4e6be-131">Estatísticas do questionário</span><span class="sxs-lookup"><span data-stu-id="4e6be-131">Questionnaire statistics</span></span>
<span data-ttu-id="4e6be-132">Você pode usar as estatísticas do questionário para analisar os resultados de um questionário preenchido, com base nos cálculos definidos por você.</span><span class="sxs-lookup"><span data-stu-id="4e6be-132">You can use questionnaire statistics to analyze the results of a completed questionnaire, based on calculations that you define.</span></span> <span data-ttu-id="4e6be-133">Para definir os cálculos, você deve concluir as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="4e6be-133">To define calculations, you must complete the following tasks:</span></span>

-   <span data-ttu-id="4e6be-134">Selecione critérios para calcular e exibir as estatísticas.</span><span class="sxs-lookup"><span data-stu-id="4e6be-134">Select criteria to calculate and display the statistics.</span></span>
    -   <span data-ttu-id="4e6be-135">Você pode exibir as estatísticas do questionário, pelas perguntas, pelas linhas de pergunta, ou os grupos de resultados.</span><span class="sxs-lookup"><span data-stu-id="4e6be-135">You can show statistics by questionnaire, questions, question rows, or results groups.</span></span>
    -   <span data-ttu-id="4e6be-136">Selecione o tipo de gráfico que será usado ao exibir os resultados.</span><span class="sxs-lookup"><span data-stu-id="4e6be-136">Select the type of chart that will be used when you view results.</span></span>
    -   <span data-ttu-id="4e6be-137">Selecione os tipos de pessoas na rede como, por exemplo, funcionários, pessoas de contato, ou candidatos, para os quais você incluirá respostas.</span><span class="sxs-lookup"><span data-stu-id="4e6be-137">Select the types of people from the network, such as employees, contact persons, or applicants, to include answers for.</span></span> <span data-ttu-id="4e6be-138">Você também pode incluir as respostas de questionários que foram preenchidos anônima.</span><span class="sxs-lookup"><span data-stu-id="4e6be-138">You can also include answers from questionnaires that were completed anonymously.</span></span>
    -   <span data-ttu-id="4e6be-139">Configurar os intervalos com base na idade ou em tempo para analisar os resultados.</span><span class="sxs-lookup"><span data-stu-id="4e6be-139">Set up intervals that are based on age or seniority to analyze results.</span></span>
-   <span data-ttu-id="4e6be-140">Selecione ou marque as configurações que refinam o assunto das estatísticas.</span><span class="sxs-lookup"><span data-stu-id="4e6be-140">Select or verify settings that refine the subject of the statistics.</span></span> <span data-ttu-id="4e6be-141">Por exemplo, ao selecionar um CEP ou código postal, você poderá analisar os resultados de todos os pesquisados dessa área geográfica específica.</span><span class="sxs-lookup"><span data-stu-id="4e6be-141">For example, by selecting a ZIP Code or postal code, you can analyze results for all respondents within a specific geographic area.</span></span>
-   <span data-ttu-id="4e6be-142">Selecione ou marque os critérios para analisar os resultados por ou características do participante do questionário.</span><span class="sxs-lookup"><span data-stu-id="4e6be-142">Select or verify criteria to analyze results by respondent or questionnaire characteristics.</span></span> <span data-ttu-id="4e6be-143">Por exemplo, selecionando o **CEP/código postal**, você poderá analisar a correção entre o local de um respondente e respostas corretas.</span><span class="sxs-lookup"><span data-stu-id="4e6be-143">For example, by selecting **ZIP/postal code**, you can analyze the correlation between a respondent’s location and correct answers.</span></span>

<span data-ttu-id="4e6be-144">As configurações que você define são salvas e podem ser usadas para recalcular resultados periodicamente.</span><span class="sxs-lookup"><span data-stu-id="4e6be-144">The settings that you define are saved and can be used to periodically recalculate results.</span></span>

<a name="see-also"></a><span data-ttu-id="4e6be-145">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4e6be-145">See also</span></span>
--------

[<span data-ttu-id="4e6be-146">Projetar questionários</span><span class="sxs-lookup"><span data-stu-id="4e6be-146">Designing questionnaires</span></span>](design-questionnaires.md)

[<span data-ttu-id="4e6be-147">Usando questionários</span><span class="sxs-lookup"><span data-stu-id="4e6be-147">Using questionnaires</span></span>](questionnaires.md)

[<span data-ttu-id="4e6be-148">Distribuindo e preenchendo questionários</span><span class="sxs-lookup"><span data-stu-id="4e6be-148">Distributing and completing questionnaires</span></span>](distribute-questionnaires.md)




