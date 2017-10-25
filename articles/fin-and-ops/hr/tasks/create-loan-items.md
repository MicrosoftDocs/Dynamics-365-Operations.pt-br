--- 
title: "Criar itens de empréstimo"
description: "Os itens de empréstimo são registros que ajudam a manter o controle dos itens físicos, como telefones ou computadores, que sua empresa empresta aos trabalhadores."
author: kherr75
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: cef1f9b2e3d202d7eea3a967fa8a6c371c6ac3a5
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-loan-items"></a><span data-ttu-id="595bb-103">Criar itens de empréstimo</span><span class="sxs-lookup"><span data-stu-id="595bb-103">Create loan items</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="595bb-104">Os itens de empréstimo são registros que ajudam a manter o controle dos itens físicos, como telefones ou computadores, que sua empresa empresta aos trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="595bb-104">Loan items are records that help you track physical items, such as phones or computers, that your company lends to workers.</span></span> <span data-ttu-id="595bb-105">Cada item físico deve ter um item de empréstimo correspondente.</span><span class="sxs-lookup"><span data-stu-id="595bb-105">Each physical item must have a corresponding loan item.</span></span> <span data-ttu-id="595bb-106">Cada registro de item de empréstimo deve descrever o que está sendo emprestado, quem é a pessoa responsável pelo empréstimo e o número de dias que o item poderá ficar emprestado.</span><span class="sxs-lookup"><span data-stu-id="595bb-106">Each loan item record should describe what is being loaned, who is responsible for the loan, and the number of days the item can be on loan.</span></span> <span data-ttu-id="595bb-107">Você pode criar vários itens de empréstimo, como chaves, cartões de acesso ou uniformes, ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="595bb-107">You can create multiple loan items, such as keys, access cards, or uniforms, at the same time.</span></span> <span data-ttu-id="595bb-108">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="595bb-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-loan-types"></a><span data-ttu-id="595bb-109">Criar Tipos de empréstimo</span><span class="sxs-lookup"><span data-stu-id="595bb-109">Create Loan types</span></span>
1. <span data-ttu-id="595bb-110">Vá para Recursos humanos > Trabalhadores > Itens de empréstimo > Tipos de empréstimo.</span><span class="sxs-lookup"><span data-stu-id="595bb-110">Go to Human resources > Workers > Loan items > Loan types.</span></span>
2. <span data-ttu-id="595bb-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="595bb-111">Click New.</span></span>
3. <span data-ttu-id="595bb-112">No campo Tipo de empréstimo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="595bb-112">In the Loan type field, type a value.</span></span>
4. <span data-ttu-id="595bb-113">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="595bb-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="595bb-114">Insira o número de dias de atraso permitidos para os itens atribuídos a este tipo de empréstimo.</span><span class="sxs-lookup"><span data-stu-id="595bb-114">Enter the number of days that items assigned to this loan type can be overdue.</span></span> 
6. <span data-ttu-id="595bb-115">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="595bb-115">Click Save.</span></span>
7. <span data-ttu-id="595bb-116">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="595bb-116">Close the page.</span></span>
8. <span data-ttu-id="595bb-117">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="595bb-117">Refresh the page.</span></span>

## <a name="create-loan-items"></a><span data-ttu-id="595bb-118">Criar Itens de empréstimo</span><span class="sxs-lookup"><span data-stu-id="595bb-118">Create Loan items</span></span>
1. <span data-ttu-id="595bb-119">Vá para Recursos humanos > Trabalhadores > Itens de empréstimo > Itens de empréstimo.</span><span class="sxs-lookup"><span data-stu-id="595bb-119">Go to Human resources > Workers > Loan items > Loan items.</span></span>
2. <span data-ttu-id="595bb-120">Clique em Criar itens de empréstimo.</span><span class="sxs-lookup"><span data-stu-id="595bb-120">Click Create loan items.</span></span>
3. <span data-ttu-id="595bb-121">Em Quantidade. insira um número.</span><span class="sxs-lookup"><span data-stu-id="595bb-121">In the Qty. field, enter a number.</span></span>
4. <span data-ttu-id="595bb-122">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="595bb-122">In the Description field, type a value.</span></span>
5. <span data-ttu-id="595bb-123">No campo Tipo de empréstimo, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="595bb-123">In the Loan type field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="595bb-124">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="595bb-124">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="595bb-125">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="595bb-125">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="595bb-126">Insira o número de dias pelos quais o item pode ser emprestado.</span><span class="sxs-lookup"><span data-stu-id="595bb-126">Enter the number of days the item can be on loan.</span></span>
    * <span data-ttu-id="595bb-127">O valor padrão do campo Devolução planejada na página de Equipamento emprestado é calculado como a data atual mais esse número.</span><span class="sxs-lookup"><span data-stu-id="595bb-127">The default value for the Planned return field on the Loaned equipment page is calculated as the current date plus this number.</span></span>  
9. <span data-ttu-id="595bb-128">No campo Pessoa responsável, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="595bb-128">In the Person in charge field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="595bb-129">Clique em Selecionar.</span><span class="sxs-lookup"><span data-stu-id="595bb-129">Click Select.</span></span>
11. <span data-ttu-id="595bb-130">No campo Valor inicial, insira um número.</span><span class="sxs-lookup"><span data-stu-id="595bb-130">In the Starting value field, enter a number.</span></span>
12. <span data-ttu-id="595bb-131">No campo Intervalo, insira um número.</span><span class="sxs-lookup"><span data-stu-id="595bb-131">In the Interval field, enter a number.</span></span>
13. <span data-ttu-id="595bb-132">No campo Formato, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="595bb-132">In the Format field, type a value.</span></span>
    * <span data-ttu-id="595bb-133">Por exemplo, se o número de início por um item de empréstimo 10, insira dois símbolos de números no campo Formato.</span><span class="sxs-lookup"><span data-stu-id="595bb-133">For example, if the starting number for a loan item is 10, enter two number symbols symbols in the Format field.</span></span>  
14. <span data-ttu-id="595bb-134">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="595bb-134">Click OK.</span></span>
15. <span data-ttu-id="595bb-135">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="595bb-135">Refresh the page.</span></span>

