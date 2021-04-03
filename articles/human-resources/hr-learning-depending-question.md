---
title: Fazer uma pergunta dependente da pergunta da questão anterior
description: Perguntas condicionais permitem que você especifique qual será a próxima pergunta a ser apresentada ao entrevistado, com base na resposta dada a pergunta anterior.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMCollection, KMCollectionQuestion, KMCollectionQuestionTree, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0a76220647417b6ff69e2f0ab5b2fa5297db5c49
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467834"
---
# <a name="make-a-question-dependent-on-the-answer-of-the-previous-question"></a><span data-ttu-id="fd2dc-103">Fazer uma pergunta dependente da pergunta da questão anterior</span><span class="sxs-lookup"><span data-stu-id="fd2dc-103">Make a question dependent on the answer of the previous question</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



<span data-ttu-id="fd2dc-104">Perguntas condicionais permitem que você especifique qual será a próxima pergunta a ser apresentada ao entrevistado, com base na resposta dada a pergunta anterior.</span><span class="sxs-lookup"><span data-stu-id="fd2dc-104">Conditional questions allow you to specify what follow-up question will be presented to a respondent, based on the answer to the preceding question.</span></span> <span data-ttu-id="fd2dc-105">Por exemplo, se você perguntar "Você prefere café ou chá", a próxima pergunta pode ser determinada de maneira lógica de acordo com a escolha do entrevistado.</span><span class="sxs-lookup"><span data-stu-id="fd2dc-105">For example, if you ask "Do you prefer coffee or tea," a logical follow-up question can be determined depending on whether the respondent selects coffee or tea as their answer.</span></span> <span data-ttu-id="fd2dc-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="fd2dc-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="find-the-existing-questionnaire"></a><span data-ttu-id="fd2dc-107">Localize o questionário existente</span><span class="sxs-lookup"><span data-stu-id="fd2dc-107">Find the existing questionnaire</span></span>
1. <span data-ttu-id="fd2dc-108">Vá para Questionário > Design > Questionários.</span><span class="sxs-lookup"><span data-stu-id="fd2dc-108">Go to Questionnaire > Design > Questionnaires.</span></span>
2. <span data-ttu-id="fd2dc-109">Na lista, selecione o questionário WorkFH.</span><span class="sxs-lookup"><span data-stu-id="fd2dc-109">In the list, select the WorkFH questionnaire.</span></span>

## <a name="add-all-questions-and-sub-questions-to-the-questionnaire"></a><span data-ttu-id="fd2dc-110">Adicione todas as perguntas e subperguntas ao questionário</span><span class="sxs-lookup"><span data-stu-id="fd2dc-110">Add all questions and sub-questions to the Questionnaire</span></span>
1. <span data-ttu-id="fd2dc-111">Clique em Perguntas.</span><span class="sxs-lookup"><span data-stu-id="fd2dc-111">Click Questions.</span></span>
2. <span data-ttu-id="fd2dc-112">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="fd2dc-112">Click New.</span></span>
3. <span data-ttu-id="fd2dc-113">No campo Pergunta, selecione a pergunta número 00016.</span><span class="sxs-lookup"><span data-stu-id="fd2dc-113">In the Question field, select question number 00016.</span></span>
4. <span data-ttu-id="fd2dc-114">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="fd2dc-114">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="fd2dc-115">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="fd2dc-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="fd2dc-116">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="fd2dc-116">Click Save.</span></span>
7. <span data-ttu-id="fd2dc-117">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="fd2dc-117">Close the page.</span></span>

## <a name="set-the-questionnaire-sequence-to-conditional-and-make-the-question-dependent-on-the-appropriate-question"></a><span data-ttu-id="fd2dc-118">Defina a Sequência do Questionário para Condicional e defina a questão apropriada como dependente.</span><span class="sxs-lookup"><span data-stu-id="fd2dc-118">Set the Questionnaire Sequence to Conditional and make the question dependent on the appropriate question</span></span>
1. <span data-ttu-id="fd2dc-119">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="fd2dc-119">Click Edit.</span></span>
2. <span data-ttu-id="fd2dc-120">Expandir a seção Instalação.</span><span class="sxs-lookup"><span data-stu-id="fd2dc-120">Expand the Setup section.</span></span>
3. <span data-ttu-id="fd2dc-121">No campo Ordem das perguntas, selecione 'Condicional'.</span><span class="sxs-lookup"><span data-stu-id="fd2dc-121">In the Question order field, select 'Conditional'.</span></span>
4. <span data-ttu-id="fd2dc-122">Clique em Pergunta condicional.</span><span class="sxs-lookup"><span data-stu-id="fd2dc-122">Click Conditional question.</span></span>
5. <span data-ttu-id="fd2dc-123">Na árvore, selecione 'Perguntas\Explique o motivo da resposta fornecida à questão anterior?'.</span><span class="sxs-lookup"><span data-stu-id="fd2dc-123">In the tree, select 'Questions\Explain why you answered the previous question the way you did?'.</span></span>
6. <span data-ttu-id="fd2dc-124">No campo Pergunta principal, selecione a pergunta 00009.</span><span class="sxs-lookup"><span data-stu-id="fd2dc-124">In the Primary question field, select question 00009</span></span>
7. <span data-ttu-id="fd2dc-125">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="fd2dc-125">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="fd2dc-126">No campo Resposta, insira o ID da sequência de resposta da opção de resposta que torna a pergunta dependente dela.</span><span class="sxs-lookup"><span data-stu-id="fd2dc-126">In the Answer field, enter the answer sequence ID of the answer option you want to make the question dependent on.</span></span> <span data-ttu-id="fd2dc-127">Por exemplo, insira 1 para a primeira opção de resposta.</span><span class="sxs-lookup"><span data-stu-id="fd2dc-127">For example, enter 1 for the first answer option.</span></span>
9. <span data-ttu-id="fd2dc-128">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="fd2dc-128">Click Save.</span></span>
10. <span data-ttu-id="fd2dc-129">Na árvore, selecione 'Perguntas\Eu sou bem pago pelo trabalho que faço.'.</span><span class="sxs-lookup"><span data-stu-id="fd2dc-129">In the tree, select 'Questions\I am paid fairly for the work I do.'.</span></span>
    * <span data-ttu-id="fd2dc-130">Observe que a árvore de pergunta atualizou para mostrar a dependência.</span><span class="sxs-lookup"><span data-stu-id="fd2dc-130">Note that the question tree updated to show the dependency.</span></span>  



[!INCLUDE[footer-include](../includes/footer-banner.md)]