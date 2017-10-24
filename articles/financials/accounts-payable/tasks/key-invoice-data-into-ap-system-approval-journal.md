--- 
title: "Dados-chave de fatura em contas a pagar usando um diário de aprovações"
description: "Este guia de tarefa mostrará como usar o registro de nota fiscal para criar notas fiscais e usar no diário de aprovações para atualizar as contas de despesas."
author: abruer
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 604345d357e5019e334017b2b6d0413f40818acc
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a><span data-ttu-id="b6018-103">Dados-chave de fatura em contas a pagar usando um diário de aprovações</span><span class="sxs-lookup"><span data-stu-id="b6018-103">Key invoice data into accounts payable using an approval journal</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b6018-104">Este guia de tarefa mostrará como usar o registro de nota fiscal para criar notas fiscais e usar no diário de aprovações para atualizar as contas de despesas.</span><span class="sxs-lookup"><span data-stu-id="b6018-104">This task guide will show you how to use the invoice register to create invoices and then use the approval journal to update the expense accounts.</span></span>


## <a name="create-and-post-and-invoice"></a><span data-ttu-id="b6018-105">Criar e lançar e faturar</span><span class="sxs-lookup"><span data-stu-id="b6018-105">Create and post and invoice</span></span>
1. <span data-ttu-id="b6018-106">Ir para Contas a pagar > Faturas > Registro de fatura.</span><span class="sxs-lookup"><span data-stu-id="b6018-106">Go to Accounts payable > Invoices > Invoice register.</span></span>
2. <span data-ttu-id="b6018-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b6018-107">Click New.</span></span>
3. <span data-ttu-id="b6018-108">Selecione o nome do registro de fatura que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="b6018-108">Select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="b6018-109">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b6018-109">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="b6018-110">Clique em em Linhas para abrir o registro e para inserir linhas de despesa.</span><span class="sxs-lookup"><span data-stu-id="b6018-110">Click on Lines to open the register and enter expense lines.</span></span>
6. <span data-ttu-id="b6018-111">Selecione um fornecedor.</span><span class="sxs-lookup"><span data-stu-id="b6018-111">Select a vendor.</span></span> <span data-ttu-id="b6018-112">Por exemplo, digite ou selecione US-104</span><span class="sxs-lookup"><span data-stu-id="b6018-112">For example, enter or select US-104</span></span>
7. <span data-ttu-id="b6018-113">No campo Fatura, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b6018-113">In the Invoice field, type a value.</span></span>
8. <span data-ttu-id="b6018-114">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b6018-114">In the Description field, type a value.</span></span>
9. <span data-ttu-id="b6018-115">No campo Crédito, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b6018-115">In the Credit field, enter a number.</span></span>
10. <span data-ttu-id="b6018-116">No campo Aprovado por, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b6018-116">In the Approved by field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="b6018-117">Realce um aprovador e clique em selecionar para selecionar o aprovador.</span><span class="sxs-lookup"><span data-stu-id="b6018-117">Highlight an approver and click Select to select that approver.</span></span>
12. <span data-ttu-id="b6018-118">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="b6018-118">Click Post.</span></span>
13. <span data-ttu-id="b6018-119">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b6018-119">Close the page.</span></span>
14. <span data-ttu-id="b6018-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b6018-120">Close the page.</span></span>

## <a name="approve-an-invoice"></a><span data-ttu-id="b6018-121">Aprovar uma fatura</span><span class="sxs-lookup"><span data-stu-id="b6018-121">Approve an invoice</span></span>
1. <span data-ttu-id="b6018-122">Ir para Contas a pagar > Faturas > Aprovação de fatura.</span><span class="sxs-lookup"><span data-stu-id="b6018-122">Go to Accounts payable > Invoices > Invoice approval.</span></span>
2. <span data-ttu-id="b6018-123">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b6018-123">Click New.</span></span>
3. <span data-ttu-id="b6018-124">Selecione o nome do diário de aprovação de fatura que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="b6018-124">Select the name of the invoice approval journal that you want to use.</span></span>
4. <span data-ttu-id="b6018-125">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b6018-125">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="b6018-126">Clique em Linhas para exibir uma página na qual você possa selecionar as notas fiscais que deseja aprovar.</span><span class="sxs-lookup"><span data-stu-id="b6018-126">Click lines to display a page where you will be able to select the invoices that you want to approve.</span></span>
6. <span data-ttu-id="b6018-127">Selecione comprovantes de localização para exibir todas as notas fiscais que estão prontas para aprovação.</span><span class="sxs-lookup"><span data-stu-id="b6018-127">Select Find Vouchers to display all of the invoices that are ready for approval.</span></span>
7. <span data-ttu-id="b6018-128">Marque a nota fiscal que você criou.</span><span class="sxs-lookup"><span data-stu-id="b6018-128">Mark the invoice that you created.</span></span>
8. <span data-ttu-id="b6018-129">Clique em Selecionar.</span><span class="sxs-lookup"><span data-stu-id="b6018-129">Click Select.</span></span>
    * <span data-ttu-id="b6018-130">Os comprovantes que tiver selecionado acima são movidos para esta lista depois que você os seleciona.</span><span class="sxs-lookup"><span data-stu-id="b6018-130">The vouchers that you selected above are moved to this list after you select them.</span></span>  
9. <span data-ttu-id="b6018-131">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b6018-131">Click OK.</span></span>
10. <span data-ttu-id="b6018-132">Clique no campo do número de conta para adicionar uma conta de despesas na nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="b6018-132">Click on the account number field to add an expense account to the invoice.</span></span>
11. <span data-ttu-id="b6018-133">Insira um número de conta e desmarque o campo.</span><span class="sxs-lookup"><span data-stu-id="b6018-133">Enter an account number and tab off of the field.</span></span> <span data-ttu-id="b6018-134">Por exemplo, insira 600120.</span><span class="sxs-lookup"><span data-stu-id="b6018-134">For example, enter 600120.</span></span>
12. <span data-ttu-id="b6018-135">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="b6018-135">Click Post.</span></span>
13. <span data-ttu-id="b6018-136">Clique no comprovante para exibir as entradas que foram lançadas.</span><span class="sxs-lookup"><span data-stu-id="b6018-136">Click Voucher to view the entries that were posted.</span></span>
    * <span data-ttu-id="b6018-137">A nota fiscal durante a conta de aprovação é revertida e substituída pela conta de despesa real.</span><span class="sxs-lookup"><span data-stu-id="b6018-137">The Invoice Pending Approval account is reversed and replaced with the actual expense account.</span></span>  


