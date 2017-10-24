--- 
title: Criar uma fatura de texto livre
description: "Essa guia da tarefa demonstra a criação de uma nota fiscal de texto livre."
author: mikefalkner
manager: AnnBe
ms.date: 10/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 33324a9b95026600bcc6facb9c22a04fd2e323c8
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-free-text-invoice"></a><span data-ttu-id="18e86-103">Criar uma fatura de texto livre</span><span class="sxs-lookup"><span data-stu-id="18e86-103">Create a free text invoice</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="18e86-104">Essa guia da tarefa demonstra a criação de uma nota fiscal de texto livre.</span><span class="sxs-lookup"><span data-stu-id="18e86-104">This task guide demonstrates creating a free text invoice.</span></span> <span data-ttu-id="18e86-105">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="18e86-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="18e86-106">Vá para Contas recebíveis > Faturas > Todas faturas de texto livre.</span><span class="sxs-lookup"><span data-stu-id="18e86-106">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="18e86-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="18e86-107">Click New.</span></span>
3. <span data-ttu-id="18e86-108">No campo Conta de cliente, selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="18e86-108">In the Customer account field, select a value.</span></span>
    * <span data-ttu-id="18e86-109">A conta de fatura usará como padrão a mesma conta usada para a conta do cliente.</span><span class="sxs-lookup"><span data-stu-id="18e86-109">The invoice account will default to the same account used for the customer account.</span></span>   
    * <span data-ttu-id="18e86-110">O status contábil inicia com Em processo se a fatura não for lançada.</span><span class="sxs-lookup"><span data-stu-id="18e86-110">The accounting status starts with In process if the invoice is not posted.</span></span>   
    * <span data-ttu-id="18e86-111">O número da fatura será atribuído quando ela for lançada.</span><span class="sxs-lookup"><span data-stu-id="18e86-111">The invoice number will be assigned when the invoice is posted.</span></span>  
    * <span data-ttu-id="18e86-112">Se você estiver usando cartas de ordem de SEPA, a carta da ordem de débito direto será preenchida automaticamente com uma carta da ordem quando você selecionar a conta do cliente.</span><span class="sxs-lookup"><span data-stu-id="18e86-112">If you are using SEPA mandates, the direct debit mandate will be automatically populated with a mandate when you select the customer account.</span></span>  
4. <span data-ttu-id="18e86-113">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="18e86-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="18e86-114">No campo de conta principal, especifique um número de conta sem dimensões.</span><span class="sxs-lookup"><span data-stu-id="18e86-114">In the Main account field, specify an account number without dimensions.</span></span>
    * <span data-ttu-id="18e86-115">Você também pode inserir um ou mais caracteres para a conta principal e usar a pesquisa para localizar a conta.</span><span class="sxs-lookup"><span data-stu-id="18e86-115">You can also enter one or more characters for the main account and use the lookup to find your account.</span></span> <span data-ttu-id="18e86-116">Insira dimensões posteriormente neste guia.</span><span class="sxs-lookup"><span data-stu-id="18e86-116">You will enter dimensions later on in this guide.</span></span>  
6. <span data-ttu-id="18e86-117">Expanda a guia rápida Detalhes da linha para poder adicionar dimensões à sua conta principal.</span><span class="sxs-lookup"><span data-stu-id="18e86-117">Expand the Line details fasttab so you can add dimensions to your main account.</span></span>
7. <span data-ttu-id="18e86-118">Clique na guia Linha de dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="18e86-118">Click the Financial dimensions line tab.</span></span>
    * <span data-ttu-id="18e86-119">As dimensões são somente para a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="18e86-119">The dimensions are for the selected line only.</span></span>    
    * <span data-ttu-id="18e86-120">O grupo de impostos sobre vendas é preenchido pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="18e86-120">The sales tax group is populated from the customer.</span></span> <span data-ttu-id="18e86-121">Se o cliente não tiver um grupo de impostos sobre vendas, o grupo de impostos sobre vendas da conta principal será usado.</span><span class="sxs-lookup"><span data-stu-id="18e86-121">If the customer does not have a sales tax group, the sales tax group from the main account is used.</span></span>  
    * <span data-ttu-id="18e86-122">O grupo de impostos dos itens é preenchido pela conta principal.</span><span class="sxs-lookup"><span data-stu-id="18e86-122">The items sales tax group is populated from the main account.</span></span> <span data-ttu-id="18e86-123">Se a conta principal não tiver um grupo de impostos do item, será usado o grupo de impostos do item nos parâmetros de impostos da Contabilidade.</span><span class="sxs-lookup"><span data-stu-id="18e86-123">If the main account does not have a item sales tax group, then the item sales tax group in the General ledger sales tax parameters is used.</span></span>    
8. <span data-ttu-id="18e86-124">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="18e86-124">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="18e86-125">A quantidade é opcional.</span><span class="sxs-lookup"><span data-stu-id="18e86-125">The quantity is optional.</span></span>  
9. <span data-ttu-id="18e86-126">No campo Preço unitário, insira um número.</span><span class="sxs-lookup"><span data-stu-id="18e86-126">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="18e86-127">O preço unitário é opcional.</span><span class="sxs-lookup"><span data-stu-id="18e86-127">The unit price is optional.</span></span>  
    * <span data-ttu-id="18e86-128">O valor é calculado como a quantidade vezes o preço unitário.</span><span class="sxs-lookup"><span data-stu-id="18e86-128">The amount is calculated as the quantity times the unit price.</span></span> <span data-ttu-id="18e86-129">No entanto, você pode substituir o cálculo e inserir um valor.</span><span class="sxs-lookup"><span data-stu-id="18e86-129">However, you can override that calculation and enter an amount.</span></span>  
10. <span data-ttu-id="18e86-130">Clique em Imposto para ver os impostos calculados para sua fatura.</span><span class="sxs-lookup"><span data-stu-id="18e86-130">Click on Sales tax to view the sales tax calculated for your invoice.</span></span>
    * <span data-ttu-id="18e86-131">Exiba os valores dos impostos nesta página ou substitua os valores na guia Ajuste.</span><span class="sxs-lookup"><span data-stu-id="18e86-131">View the sales tax amounts in this page or you can override the amounts on the Adjustment tab.</span></span>  
11. <span data-ttu-id="18e86-132">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="18e86-132">Click OK.</span></span>
12. <span data-ttu-id="18e86-133">Clique em Encargos para adicionar um encargo a sua fatura.</span><span class="sxs-lookup"><span data-stu-id="18e86-133">Click Charges to add a charge to your invoice.</span></span> 
13. <span data-ttu-id="18e86-134">No campo Código de encargo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="18e86-134">In the Charges code field, type a value.</span></span>
14. <span data-ttu-id="18e86-135">No campo Valor de encargo, insira um número.</span><span class="sxs-lookup"><span data-stu-id="18e86-135">In the Charges value field, enter a number.</span></span>
15. <span data-ttu-id="18e86-136">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="18e86-136">Close the page.</span></span>
16. <span data-ttu-id="18e86-137">Clique em Totais para ver o resumo dos detalhes da fatura e os totais.</span><span class="sxs-lookup"><span data-stu-id="18e86-137">Click Totals to view the summary invoice details and totals.</span></span>
17. <span data-ttu-id="18e86-138">Clique em Fechar.</span><span class="sxs-lookup"><span data-stu-id="18e86-138">Click Close.</span></span>
18. <span data-ttu-id="18e86-139">Clique em Lançar para lançar a fatura.</span><span class="sxs-lookup"><span data-stu-id="18e86-139">Click Post to post the invoice.</span></span> <span data-ttu-id="18e86-140">É possível cancelar antes de lançar.</span><span class="sxs-lookup"><span data-stu-id="18e86-140">You will be able to cancel before you post.</span></span>
    * <span data-ttu-id="18e86-141">Para alterar o cronograma de impressão de faturas: selecione Atual para imprimir cada fatura conforme elas são atualizadas ou selecione Depois para imprimir depois de todas as faturas serem atualizadas.</span><span class="sxs-lookup"><span data-stu-id="18e86-141">To change the timing of your invoice printing:  Select Current to print each invoice as it is updated   or  Select After to print after all invoices have been updated.</span></span>  
    * <span data-ttu-id="18e86-142">Se desejar alterar como o limite de crédito do cliente será verificado antes de lançar, altere o tipo de limite de crédito.</span><span class="sxs-lookup"><span data-stu-id="18e86-142">If you want to change how the customer's credit limit is checked before posting, change the Credit limit type.</span></span>  
    * <span data-ttu-id="18e86-143">Se desejar imprimir a fatura, selecione Sim.</span><span class="sxs-lookup"><span data-stu-id="18e86-143">If you want to print the invoice, select Yes.</span></span>  
    * <span data-ttu-id="18e86-144">Se desejar lançar a fatura, selecione Sim.</span><span class="sxs-lookup"><span data-stu-id="18e86-144">If you want to post the invoice, select Yes.</span></span> <span data-ttu-id="18e86-145">Você pode imprimir a nota fiscal sem lançá-las.</span><span class="sxs-lookup"><span data-stu-id="18e86-145">You can print the invoice without posting.</span></span>  
19. <span data-ttu-id="18e86-146">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="18e86-146">Click OK.</span></span>


