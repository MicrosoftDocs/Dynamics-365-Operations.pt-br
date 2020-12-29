---
title: Criar uma pergunta fechada
description: As perguntas fechadas permitem que você forneça opções para que o entrevistado escolha.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMAnswerCollection, KMAnswer, KMQuestion, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a2eb53290d39fef0bf439a199dfd774138823ec2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4417348"
---
# <a name="create-a-closed-ended-question"></a><span data-ttu-id="ebe25-103">Criar uma pergunta fechada</span><span class="sxs-lookup"><span data-stu-id="ebe25-103">Create a closed ended question</span></span>



<span data-ttu-id="ebe25-104">As perguntas fechadas permitem que você forneça opções para que o entrevistado escolha.</span><span class="sxs-lookup"><span data-stu-id="ebe25-104">Closed-ended questions allow you to provide options for the respondent to choose from.</span></span> <span data-ttu-id="ebe25-105">Primeiro, você precisa criar o Grupo de resposta com as respostas, então criar a pergunta que irá utilizar o grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="ebe25-105">First, you need to create the Answer group with the answers, then create the question that will use the answer group.</span></span> <span data-ttu-id="ebe25-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="ebe25-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-an-answer-group"></a><span data-ttu-id="ebe25-107">Crie um grupo de reposta</span><span class="sxs-lookup"><span data-stu-id="ebe25-107">Create an answer group</span></span>
1. <span data-ttu-id="ebe25-108">Vá para Questionário > Design > Grupos de respostas.</span><span class="sxs-lookup"><span data-stu-id="ebe25-108">Go to Questionnaire > Design > Answer groups.</span></span>
2. <span data-ttu-id="ebe25-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="ebe25-109">Click New.</span></span>
3. <span data-ttu-id="ebe25-110">No campo Grupo de resposta, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ebe25-110">In the Answer group field, type a value.</span></span>
4. <span data-ttu-id="ebe25-111">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ebe25-111">In the Description field, type a value.</span></span>
    * <span data-ttu-id="ebe25-112">Use a funcionalidade Randomizar para colocar as respostas numa ordem aleatória diferente toda vez que o grupo de repostas for usado para uma questão.</span><span class="sxs-lookup"><span data-stu-id="ebe25-112">Use the Randomize functionality to randomly place the answers in a different order each time the answer group is used for a question.</span></span>  
5. <span data-ttu-id="ebe25-113">Clique em Resposta.</span><span class="sxs-lookup"><span data-stu-id="ebe25-113">Click Answer.</span></span>
6. <span data-ttu-id="ebe25-114">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="ebe25-114">Click New.</span></span>
    * <span data-ttu-id="ebe25-115">Número de sequência controla a ordem em que as respostas são exibidas, a menos que Randomizar seja selecionada para o Grupo de respostas.</span><span class="sxs-lookup"><span data-stu-id="ebe25-115">Sequence number controls the order in which the answers are displayed, unless Randomize is selected for the Answer group.</span></span>  
    * <span data-ttu-id="ebe25-116">Pontos podem ser concedidos pelas respostas para uso na pontuação do questionário.</span><span class="sxs-lookup"><span data-stu-id="ebe25-116">Points can be awarded to answers for use in scoring the questionnaire.</span></span>  
7. <span data-ttu-id="ebe25-117">No campo Pontos, insira um número.</span><span class="sxs-lookup"><span data-stu-id="ebe25-117">In the Points field, enter a number.</span></span>
    * <span data-ttu-id="ebe25-118">A resposta correta pode ser marcada para indicar que a resposta selecionada é a correta.</span><span class="sxs-lookup"><span data-stu-id="ebe25-118">The correct answer can be marked to indicate that the selected answer is the correct one.</span></span> <span data-ttu-id="ebe25-119">Isso pode ser usado na pontuação do questionário.</span><span class="sxs-lookup"><span data-stu-id="ebe25-119">This can be used for scoring the questionnaire.</span></span>  
8. <span data-ttu-id="ebe25-120">No campo Resposta, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ebe25-120">In the Answer field, type a value.</span></span>
    * <span data-ttu-id="ebe25-121">Continue a criar opções de seleção de resposta para o grupo de respostas.</span><span class="sxs-lookup"><span data-stu-id="ebe25-121">Continue to create answer selection options for the answer group.</span></span>  
9. <span data-ttu-id="ebe25-122">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="ebe25-122">Click New.</span></span>
10. <span data-ttu-id="ebe25-123">No campo Pontos, insira um número.</span><span class="sxs-lookup"><span data-stu-id="ebe25-123">In the Points field, enter a number.</span></span>
11. <span data-ttu-id="ebe25-124">No campo Resposta, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ebe25-124">In the Answer field, type a value.</span></span>
12. <span data-ttu-id="ebe25-125">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="ebe25-125">Click New.</span></span>
13. <span data-ttu-id="ebe25-126">No campo Pontos, insira um número.</span><span class="sxs-lookup"><span data-stu-id="ebe25-126">In the Points field, enter a number.</span></span>
14. <span data-ttu-id="ebe25-127">No campo Resposta, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ebe25-127">In the Answer field, type a value.</span></span>
15. <span data-ttu-id="ebe25-128">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="ebe25-128">Click New.</span></span>
16. <span data-ttu-id="ebe25-129">No campo Pontos, insira um número.</span><span class="sxs-lookup"><span data-stu-id="ebe25-129">In the Points field, enter a number.</span></span>
17. <span data-ttu-id="ebe25-130">No campo Resposta, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ebe25-130">In the Answer field, type a value.</span></span>
18. <span data-ttu-id="ebe25-131">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="ebe25-131">Click New.</span></span>
19. <span data-ttu-id="ebe25-132">No campo Pontos, insira um número.</span><span class="sxs-lookup"><span data-stu-id="ebe25-132">In the Points field, enter a number.</span></span>
20. <span data-ttu-id="ebe25-133">No campo Resposta, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ebe25-133">In the Answer field, type a value.</span></span>
21. <span data-ttu-id="ebe25-134">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ebe25-134">Close the page.</span></span>
22. <span data-ttu-id="ebe25-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ebe25-135">Close the page.</span></span>

## <a name="create-the-question"></a><span data-ttu-id="ebe25-136">Crie a pergunta</span><span class="sxs-lookup"><span data-stu-id="ebe25-136">Create the question</span></span>
1. <span data-ttu-id="ebe25-137">Vá para Questionário > Design > Perguntas.</span><span class="sxs-lookup"><span data-stu-id="ebe25-137">Go to Questionnaire > Design > Questions.</span></span>
2. <span data-ttu-id="ebe25-138">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="ebe25-138">Click New.</span></span>
3. <span data-ttu-id="ebe25-139">Use o campo Tipo para agrupar perguntas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="ebe25-139">Use the Type field to group related questions together.</span></span>
    * <span data-ttu-id="ebe25-140">Você pode usar os tipos de entrada de Caixa de seleção, Botão Alternativo, ou Caixa de combinação para perguntas fechadas.</span><span class="sxs-lookup"><span data-stu-id="ebe25-140">You can use input types of Check box, Alternative button, or Combo box for closed-ended questions.</span></span>  
4. <span data-ttu-id="ebe25-141">No campo Tipo de entrada, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="ebe25-141">In the Input type field, select an option.</span></span>
5. <span data-ttu-id="ebe25-142">No campo Responder grupo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ebe25-142">In the Answer group field, enter or select a value.</span></span>
6. <span data-ttu-id="ebe25-143">No campo Texto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ebe25-143">In the Text field, type a value.</span></span>

