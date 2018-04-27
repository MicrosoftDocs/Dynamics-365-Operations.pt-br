--- 
title: Criar uma pergunta fechada
description: "As perguntas fechadas permitem que você forneça opções para que o entrevistado escolha."
author: kherr75
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: fdfac92b80774adb8376d5c2e945d063173188c8
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-closed-ended-question"></a><span data-ttu-id="6a67d-103">Criar uma pergunta fechada</span><span class="sxs-lookup"><span data-stu-id="6a67d-103">Create a closed ended question</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6a67d-104">As perguntas fechadas permitem que você forneça opções para que o entrevistado escolha.</span><span class="sxs-lookup"><span data-stu-id="6a67d-104">Closed-ended questions allow you to provide options for the respondent to choose from.</span></span> <span data-ttu-id="6a67d-105">Primeiro, você precisa criar o Grupo de resposta com as respostas, então criar a pergunta que irá utilizar o grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="6a67d-105">First, you need to create the Answer group with the answers, then create the question that will use the answer group.</span></span> <span data-ttu-id="6a67d-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="6a67d-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-an-answer-group"></a><span data-ttu-id="6a67d-107">Crie um grupo de reposta</span><span class="sxs-lookup"><span data-stu-id="6a67d-107">Create an answer group</span></span>
1. <span data-ttu-id="6a67d-108">Vá para Questionário > Design > Grupos de respostas.</span><span class="sxs-lookup"><span data-stu-id="6a67d-108">Go to Questionnaire > Design > Answer groups.</span></span>
2. <span data-ttu-id="6a67d-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="6a67d-109">Click New.</span></span>
3. <span data-ttu-id="6a67d-110">No campo Grupo de resposta, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6a67d-110">In the Answer group field, type a value.</span></span>
4. <span data-ttu-id="6a67d-111">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6a67d-111">In the Description field, type a value.</span></span>
    * <span data-ttu-id="6a67d-112">Use a funcionalidade Randomizar para colocar as respostas numa ordem aleatória diferente toda vez que o grupo de repostas for usado para uma questão.</span><span class="sxs-lookup"><span data-stu-id="6a67d-112">Use the Randomize functionality to randomly place the answers in a different order each time the answer group is used for a question.</span></span>  
5. <span data-ttu-id="6a67d-113">Clique em Resposta.</span><span class="sxs-lookup"><span data-stu-id="6a67d-113">Click Answer.</span></span>
6. <span data-ttu-id="6a67d-114">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="6a67d-114">Click New.</span></span>
    * <span data-ttu-id="6a67d-115">Número de sequência controla a ordem em que as respostas são exibidas, a menos que Randomizar seja selecionada para o Grupo de respostas.</span><span class="sxs-lookup"><span data-stu-id="6a67d-115">Sequence number controls the order in which the answers are displayed, unless Randomize is selected for the Answer group.</span></span>  
    * <span data-ttu-id="6a67d-116">Pontos podem ser concedidos pelas respostas para uso na pontuação do questionário.</span><span class="sxs-lookup"><span data-stu-id="6a67d-116">Points can be awarded to answers for use in scoring the questionnaire.</span></span>  
7. <span data-ttu-id="6a67d-117">No campo Pontos, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6a67d-117">In the Points field, enter a number.</span></span>
    * <span data-ttu-id="6a67d-118">A resposta correta pode ser marcada para indicar que a resposta selecionada é a correta.</span><span class="sxs-lookup"><span data-stu-id="6a67d-118">The correct answer can be marked to indicate that the selected answer is the correct one.</span></span> <span data-ttu-id="6a67d-119">Isso pode ser usado na pontuação do questionário.</span><span class="sxs-lookup"><span data-stu-id="6a67d-119">This can be used for scoring the questionnaire.</span></span>  
8. <span data-ttu-id="6a67d-120">No campo Resposta, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6a67d-120">In the Answer field, type a value.</span></span>
    * <span data-ttu-id="6a67d-121">Continue a criar opções de seleção de resposta para o grupo de respostas.</span><span class="sxs-lookup"><span data-stu-id="6a67d-121">Continue to create answer selection options for the answer group.</span></span>  
9. <span data-ttu-id="6a67d-122">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="6a67d-122">Click New.</span></span>
10. <span data-ttu-id="6a67d-123">No campo Pontos, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6a67d-123">In the Points field, enter a number.</span></span>
11. <span data-ttu-id="6a67d-124">No campo Resposta, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6a67d-124">In the Answer field, type a value.</span></span>
12. <span data-ttu-id="6a67d-125">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="6a67d-125">Click New.</span></span>
13. <span data-ttu-id="6a67d-126">No campo Pontos, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6a67d-126">In the Points field, enter a number.</span></span>
14. <span data-ttu-id="6a67d-127">No campo Resposta, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6a67d-127">In the Answer field, type a value.</span></span>
15. <span data-ttu-id="6a67d-128">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="6a67d-128">Click New.</span></span>
16. <span data-ttu-id="6a67d-129">No campo Pontos, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6a67d-129">In the Points field, enter a number.</span></span>
17. <span data-ttu-id="6a67d-130">No campo Resposta, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6a67d-130">In the Answer field, type a value.</span></span>
18. <span data-ttu-id="6a67d-131">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="6a67d-131">Click New.</span></span>
19. <span data-ttu-id="6a67d-132">No campo Pontos, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6a67d-132">In the Points field, enter a number.</span></span>
20. <span data-ttu-id="6a67d-133">No campo Resposta, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6a67d-133">In the Answer field, type a value.</span></span>
21. <span data-ttu-id="6a67d-134">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6a67d-134">Close the page.</span></span>
22. <span data-ttu-id="6a67d-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6a67d-135">Close the page.</span></span>

## <a name="create-the-question"></a><span data-ttu-id="6a67d-136">Crie a pergunta</span><span class="sxs-lookup"><span data-stu-id="6a67d-136">Create the question</span></span>
1. <span data-ttu-id="6a67d-137">Vá para Questionário > Design > Perguntas.</span><span class="sxs-lookup"><span data-stu-id="6a67d-137">Go to Questionnaire > Design > Questions.</span></span>
2. <span data-ttu-id="6a67d-138">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="6a67d-138">Click New.</span></span>
3. <span data-ttu-id="6a67d-139">Use o campo Tipo para agrupar perguntas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="6a67d-139">Use the Type field to group related questions together.</span></span>
    * <span data-ttu-id="6a67d-140">Você pode usar os tipos de entrada de Caixa de seleção, Botão Alternativo, ou Caixa de combinação para perguntas fechadas.</span><span class="sxs-lookup"><span data-stu-id="6a67d-140">You can use input types of Check box, Alternative button, or Combo box for closed-ended questions.</span></span>  
4. <span data-ttu-id="6a67d-141">No campo Tipo de entrada, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="6a67d-141">In the Input type field, select an option.</span></span>
5. <span data-ttu-id="6a67d-142">No campo Responder grupo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="6a67d-142">In the Answer group field, enter or select a value.</span></span>
6. <span data-ttu-id="6a67d-143">No campo Texto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6a67d-143">In the Text field, type a value.</span></span>


