--- 
title: "Criar um método de avaliação para RFQs"
description: "Este procedimento mostra como criar um método de avaliação."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6d72678db60254801c6c899f4d405f1c59de8d65
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-scoring-method-for-rfqs"></a><span data-ttu-id="46ca5-103">Criar um método de avaliação para RFQs</span><span class="sxs-lookup"><span data-stu-id="46ca5-103">Create a scoring method for RFQs</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="46ca5-104">Este procedimento mostra como criar um método de avaliação.</span><span class="sxs-lookup"><span data-stu-id="46ca5-104">This procedure shows you how to create a scoring method.</span></span> <span data-ttu-id="46ca5-105">Um método de avaliação é um grupo de critérios que pode ser usado para comparar as ofertas que são enviadas em resposta a um pedido para a cotação (RFQ).</span><span class="sxs-lookup"><span data-stu-id="46ca5-105">A scoring method is a set of criteria that can be used to compare bids that are sent in reply to a request for quotation (RFQ).</span></span> <span data-ttu-id="46ca5-106">Por exemplo, talvez você queira classificar o desempenho passado de um fornecedor, ou avaliar se a empresa é ambientalmente correta ou uma boa parceira, ou você pode querer comparar lances com base em preços.</span><span class="sxs-lookup"><span data-stu-id="46ca5-106">For example, you might want to rate a vendor on past performance, or rate whether the company is environmentally friendly or a good collaborator, or you might want to compare bids based on price.</span></span> <span data-ttu-id="46ca5-107">Se um método de pontuação estiver associado ao tipo de solicitação, esse será o método de pontuação padrão para a RFQs que você estiver criando.</span><span class="sxs-lookup"><span data-stu-id="46ca5-107">The scoring method can be associated with a solicitation type as the default scoring method for RFQs of that type.</span></span> <span data-ttu-id="46ca5-108">Essas tarefas são normalmente realizadas por um Gerente de compras.</span><span class="sxs-lookup"><span data-stu-id="46ca5-108">These tasks would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="46ca5-109">Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou nos seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="46ca5-109">You can use this procedure in demo data company USMF or on your own data.</span></span>

1. <span data-ttu-id="46ca5-110">Vá para Compras > Configuração > Solicitação de cotação > Método de pontuação.</span><span class="sxs-lookup"><span data-stu-id="46ca5-110">Go to Procurement and sourcing > Setup > Request for quotation > Scoring method.</span></span>
2. <span data-ttu-id="46ca5-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="46ca5-111">Click New.</span></span>
3. <span data-ttu-id="46ca5-112">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="46ca5-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="46ca5-113">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="46ca5-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="46ca5-114">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="46ca5-114">Click Save.</span></span>
6. <span data-ttu-id="46ca5-115">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="46ca5-115">Click New.</span></span>
7. <span data-ttu-id="46ca5-116">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="46ca5-116">In the Name field, type a value.</span></span>
8. <span data-ttu-id="46ca5-117">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="46ca5-117">In the Description field, type a value.</span></span>
    * <span data-ttu-id="46ca5-118">Esta descrição é exibida junto com o nome do método de avaliação quando um método de avaliação é selecionado para um RFQ.</span><span class="sxs-lookup"><span data-stu-id="46ca5-118">This description is shown along with the scoring method name when a scoring method is selected for an RFQ.</span></span>  
9. <span data-ttu-id="46ca5-119">No campo Variar de, insira um número.</span><span class="sxs-lookup"><span data-stu-id="46ca5-119">In the Range from field, enter a number.</span></span>
    * <span data-ttu-id="46ca5-120">A variação limita o que o profissional de obtenção pode inserir como avaliação.</span><span class="sxs-lookup"><span data-stu-id="46ca5-120">The range limits what the procurement professional can enter as a score.</span></span> <span data-ttu-id="46ca5-121">Quando há um múltiplo que marca critérios em um RFQ, as contagens que foram incorporadas são adicionadas entre si e a soma feita está disponível para permitir que as ofertas sejam comparadas.</span><span class="sxs-lookup"><span data-stu-id="46ca5-121">When there are multiple scoring criteria on an RFQ, the scores that have been entered are added to each other and the sum is made available to allow the bids to be compared.</span></span>  
10. <span data-ttu-id="46ca5-122">No campo Variar a, insira um número.</span><span class="sxs-lookup"><span data-stu-id="46ca5-122">In the Range to field, enter a number.</span></span>
11. <span data-ttu-id="46ca5-123">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="46ca5-123">Click New.</span></span>
12. <span data-ttu-id="46ca5-124">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="46ca5-124">In the Name field, type a value.</span></span>
13. <span data-ttu-id="46ca5-125">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="46ca5-125">In the Description field, type a value.</span></span>
14. <span data-ttu-id="46ca5-126">No campo Variar de, insira um número.</span><span class="sxs-lookup"><span data-stu-id="46ca5-126">In the Range from field, enter a number.</span></span>
15. <span data-ttu-id="46ca5-127">No campo Variar a, insira um número.</span><span class="sxs-lookup"><span data-stu-id="46ca5-127">In the Range to field, enter a number.</span></span>


