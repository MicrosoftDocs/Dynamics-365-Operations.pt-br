--- 
title: Criar um modelo de fatura de texto livre
description: "Este registro usa a empresa de dados de demonstração USMF."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: e9c9811b348d81cd735c5b75ca48e0a56a8d52be
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-free-text-invoice-template"></a><span data-ttu-id="ee654-103">Criar um modelo de fatura de texto livre</span><span class="sxs-lookup"><span data-stu-id="ee654-103">Create a free text invoice template</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ee654-104">Este registro usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="ee654-104">This recording uses the USMF demo company.</span></span> <span data-ttu-id="ee654-105">O registro é direcionado para o usuário responsável por gerenciar e processar faturas A/R.</span><span class="sxs-lookup"><span data-stu-id="ee654-105">The recording is intended for the user who is responsible for managing and processing A/R invoices.</span></span>

1. <span data-ttu-id="ee654-106">Vá para Contas a receber > Faturas > Faturas recorrentes > Modelos de fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="ee654-106">Go to Accounts receivable > Invoices > Recurring invoices > Free text invoice templates.</span></span>
    * <span data-ttu-id="ee654-107">Use este formulário para criar modelos de fatura de texto livre que podem incluir linhas da fatura, encargos, um modelo de distribuição contábil e informações da conta contábil.</span><span class="sxs-lookup"><span data-stu-id="ee654-107">Use this form to create free text invoice templates that can include invoice lines, charges, an accounting distribution template, and ledger account information.</span></span>  
2. <span data-ttu-id="ee654-108">Clique em 'Novo' para criar um novo modelo de fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="ee654-108">Click 'New' to create a new free text invoice template.</span></span>
3. <span data-ttu-id="ee654-109">No campo Nome de modelo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ee654-109">In the Template name field, type a value.</span></span>
    * <span data-ttu-id="ee654-110">Especialmente 'Nome do modelo' identifica um modelo de fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="ee654-110">‘Template name’ uniquely identifies a free text invoice template.</span></span> <span data-ttu-id="ee654-111">Nenhum do dois modelos pode ter o mesmo 'Nome do modelo'.</span><span class="sxs-lookup"><span data-stu-id="ee654-111">No two templates can have the same ‘Template name’.</span></span>  
4. <span data-ttu-id="ee654-112">No campo Descrição, insira uma descrição do modelo.</span><span class="sxs-lookup"><span data-stu-id="ee654-112">In the Description field, enter a description of the template.</span></span>
5. <span data-ttu-id="ee654-113">Expanda a guia nas linhas da nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="ee654-113">Expand the Invoice lines tab.</span></span>
6. <span data-ttu-id="ee654-114">No campo Descrição, insira uma descrição da linha de fatura.</span><span class="sxs-lookup"><span data-stu-id="ee654-114">In the Description field, enter a description of the invoice line.</span></span>
7. <span data-ttu-id="ee654-115">No campo Conta principal, selecione uma conta de receita.</span><span class="sxs-lookup"><span data-stu-id="ee654-115">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="ee654-116">Você pode selecionar a conta da transação de contrapartida de um crédito de cliente para o valor total da fatura na página Perfis de lançamento de cliente.</span><span class="sxs-lookup"><span data-stu-id="ee654-116">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
8. <span data-ttu-id="ee654-117">No campo Grupo de imposto, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ee654-117">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ee654-118">O grupo de impostos para a linha da fatura atual, que é o grupo de impostos padrão para a conta do cliente.</span><span class="sxs-lookup"><span data-stu-id="ee654-118">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
9. <span data-ttu-id="ee654-119">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ee654-119">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="ee654-120">No campo Grupo de taxa de item, selecione o grupo de impostos de item para a linha de fatura atual.</span><span class="sxs-lookup"><span data-stu-id="ee654-120">In the Item tax group field, select the item sales tax group for the current invoice line.</span></span>
11. <span data-ttu-id="ee654-121">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ee654-121">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="ee654-122">No campo Preço de unidade, insira ou exiba o preço por unidade para a linha de fatura</span><span class="sxs-lookup"><span data-stu-id="ee654-122">In the Unit price field, enter or view the price per unit for the invoice line</span></span>
    * <span data-ttu-id="ee654-123">Esse valor é multiplicado pelo campo Quantidade para determinar o valor da linha da fatura.</span><span class="sxs-lookup"><span data-stu-id="ee654-123">This amount is multiplied by the Quantity field to determine the invoice line amount.</span></span>  
13. <span data-ttu-id="ee654-124">Adicione uma nova linha ao modelo de fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="ee654-124">Add a new line to free text invoice template.</span></span>
14. <span data-ttu-id="ee654-125">No campo Descrição, insira uma descrição da linha de fatura.</span><span class="sxs-lookup"><span data-stu-id="ee654-125">In the Description field, enter a description of the invoice line.</span></span>
15. <span data-ttu-id="ee654-126">No campo Conta principal, selecione uma conta de receita.</span><span class="sxs-lookup"><span data-stu-id="ee654-126">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="ee654-127">Você pode selecionar a conta da transação de contrapartida de um crédito de cliente para o valor total da fatura na página Perfis de lançamento de cliente.</span><span class="sxs-lookup"><span data-stu-id="ee654-127">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
16. <span data-ttu-id="ee654-128">No campo Grupo de imposto, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ee654-128">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ee654-129">O grupo de impostos para a linha da fatura atual, que é o grupo de impostos padrão para a conta do cliente.</span><span class="sxs-lookup"><span data-stu-id="ee654-129">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
17. <span data-ttu-id="ee654-130">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ee654-130">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="ee654-131">No campo Grupo de imposto do item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ee654-131">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ee654-132">O grupo de impostos do item para a linha de fatura atual.</span><span class="sxs-lookup"><span data-stu-id="ee654-132">The item sales tax group for the current invoice line.</span></span>  
19. <span data-ttu-id="ee654-133">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ee654-133">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="ee654-134">Insira ou exiba o número de unidades da linha da fatura</span><span class="sxs-lookup"><span data-stu-id="ee654-134">Enter or view the number of units for the invoice line</span></span>
    * <span data-ttu-id="ee654-135">Esse número é multiplicado pelo valor no campo Preço unitário para determinar o valor da linha da fatura.</span><span class="sxs-lookup"><span data-stu-id="ee654-135">This number is multiplied by the value in the Unit price field to determine the invoice line amount.</span></span>  
21. <span data-ttu-id="ee654-136">Insira ou exiba o preço unitário para a linha de fatura.</span><span class="sxs-lookup"><span data-stu-id="ee654-136">Enter or view the price per unit for the invoice line.</span></span> 
    * <span data-ttu-id="ee654-137">Esse valor é multiplicado pelo valor no campo Quantidade para determinar o valor da linha da fatura.</span><span class="sxs-lookup"><span data-stu-id="ee654-137">This amount is multiplied by the value in the Quantity field to determine the invoice line amount.</span></span>  
22. <span data-ttu-id="ee654-138">Exiba e modifique as distribuições contábeis para uma linha individual e todas as linhas descendentes.</span><span class="sxs-lookup"><span data-stu-id="ee654-138">View and modify the accounting distributions for an individual line and any child lines.</span></span>
    * <span data-ttu-id="ee654-139">As distribuições contábeis definem como um valor será contabilizado, assim como a receita, os impostos ou os encargos serão contabilizados em uma fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="ee654-139">Accounting distributions define how an amount will be accounted for, such as how the revenue, tax, or charges will be accounted for on a free text invoice.</span></span>  
23. <span data-ttu-id="ee654-140">Atualizar as distribuições contábeis para a linha de fatura selecionada.</span><span class="sxs-lookup"><span data-stu-id="ee654-140">Update the accounting distributions for the selected invoice line.</span></span>
24. <span data-ttu-id="ee654-141">Clique em Fechar.</span><span class="sxs-lookup"><span data-stu-id="ee654-141">Click Close.</span></span>


