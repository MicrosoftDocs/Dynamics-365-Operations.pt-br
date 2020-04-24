---
title: Criar um método de avaliação para RFQs
description: Este procedimento mostra como criar um método de avaliação.
author: mkirknel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQScoringMethod
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd8657098519391ee488025e175e1499c58a55ce
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204645"
---
# <a name="create-a-scoring-method-for-rfqs"></a><span data-ttu-id="9c82d-103">Criar um método de avaliação para RFQs</span><span class="sxs-lookup"><span data-stu-id="9c82d-103">Create a scoring method for RFQs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9c82d-104">Este procedimento mostra como criar um método de avaliação.</span><span class="sxs-lookup"><span data-stu-id="9c82d-104">This procedure shows you how to create a scoring method.</span></span> <span data-ttu-id="9c82d-105">Um método de avaliação é um grupo de critérios que pode ser usado para comparar as ofertas que são enviadas em resposta a um pedido para a cotação (RFQ).</span><span class="sxs-lookup"><span data-stu-id="9c82d-105">A scoring method is a set of criteria that can be used to compare bids that are sent in reply to a request for quotation (RFQ).</span></span> <span data-ttu-id="9c82d-106">Por exemplo, talvez você queira classificar o desempenho passado de um fornecedor, ou avaliar se a empresa é ambientalmente correta ou uma boa parceira, ou você pode querer comparar lances com base em preços.</span><span class="sxs-lookup"><span data-stu-id="9c82d-106">For example, you might want to rate a vendor on past performance, or rate whether the company is environmentally friendly or a good collaborator, or you might want to compare bids based on price.</span></span> <span data-ttu-id="9c82d-107">Se um método de pontuação estiver associado ao tipo de solicitação, esse será o método de pontuação padrão para a RFQs que você estiver criando.</span><span class="sxs-lookup"><span data-stu-id="9c82d-107">The scoring method can be associated with a solicitation type as the default scoring method for RFQs of that type.</span></span> <span data-ttu-id="9c82d-108">Essas tarefas são normalmente realizadas por um Gerente de compras.</span><span class="sxs-lookup"><span data-stu-id="9c82d-108">These tasks would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="9c82d-109">Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou nos seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="9c82d-109">You can use this procedure in demo data company USMF or on your own data.</span></span>

1. <span data-ttu-id="9c82d-110">Vá para Compras > Configuração > Solicitação de cotação > Método de pontuação.</span><span class="sxs-lookup"><span data-stu-id="9c82d-110">Go to Procurement and sourcing > Setup > Request for quotation > Scoring method.</span></span>
2. <span data-ttu-id="9c82d-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="9c82d-111">Click New.</span></span>
3. <span data-ttu-id="9c82d-112">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9c82d-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="9c82d-113">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9c82d-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="9c82d-114">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="9c82d-114">Click Save.</span></span>
6. <span data-ttu-id="9c82d-115">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="9c82d-115">Click New.</span></span>
7. <span data-ttu-id="9c82d-116">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9c82d-116">In the Name field, type a value.</span></span>
8. <span data-ttu-id="9c82d-117">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9c82d-117">In the Description field, type a value.</span></span>
    * <span data-ttu-id="9c82d-118">Esta descrição é exibida junto com o nome do método de avaliação quando um método de avaliação é selecionado para um RFQ.</span><span class="sxs-lookup"><span data-stu-id="9c82d-118">This description is shown along with the scoring method name when a scoring method is selected for an RFQ.</span></span>  
9. <span data-ttu-id="9c82d-119">No campo Variar de, insira um número.</span><span class="sxs-lookup"><span data-stu-id="9c82d-119">In the Range from field, enter a number.</span></span>
    * <span data-ttu-id="9c82d-120">A variação limita o que o profissional de obtenção pode inserir como avaliação.</span><span class="sxs-lookup"><span data-stu-id="9c82d-120">The range limits what the procurement professional can enter as a score.</span></span> <span data-ttu-id="9c82d-121">Quando há um múltiplo que marca critérios em um RFQ, as contagens que foram incorporadas são adicionadas entre si e a soma feita está disponível para permitir que as ofertas sejam comparadas.</span><span class="sxs-lookup"><span data-stu-id="9c82d-121">When there are multiple scoring criteria on an RFQ, the scores that have been entered are added to each other and the sum is made available to allow the bids to be compared.</span></span>  
10. <span data-ttu-id="9c82d-122">No campo Variar a, insira um número.</span><span class="sxs-lookup"><span data-stu-id="9c82d-122">In the Range to field, enter a number.</span></span>
11. <span data-ttu-id="9c82d-123">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="9c82d-123">Click New.</span></span>
12. <span data-ttu-id="9c82d-124">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9c82d-124">In the Name field, type a value.</span></span>
13. <span data-ttu-id="9c82d-125">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9c82d-125">In the Description field, type a value.</span></span>
14. <span data-ttu-id="9c82d-126">No campo Variar de, insira um número.</span><span class="sxs-lookup"><span data-stu-id="9c82d-126">In the Range from field, enter a number.</span></span>
15. <span data-ttu-id="9c82d-127">No campo Variar a, insira um número.</span><span class="sxs-lookup"><span data-stu-id="9c82d-127">In the Range to field, enter a number.</span></span>

