--- 
title: "Estabelecer condições de pagamento de cliente"
description: "Este procedimento define uma configuração de desconto à vista e a data de vencimento."
author: aprilolson
manager: AnnBe
ms.date: 10/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ef3cad6538d9efbd1c1881f4b7d771382d9b1ba8
ms.openlocfilehash: 04b45508047d26ef7c08ede5862be75835783ef5
ms.contentlocale: pt-br
ms.lasthandoff: 10/26/2017

---
# <a name="establish-customer-payment-terms"></a><span data-ttu-id="f5881-103">Estabelecer condições de pagamento de cliente</span><span class="sxs-lookup"><span data-stu-id="f5881-103">Establish customer payment terms</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f5881-104">Este procedimento define uma configuração de desconto à vista e a data de vencimento.</span><span class="sxs-lookup"><span data-stu-id="f5881-104">This procedure defines a cash discount and due date setup.</span></span> <span data-ttu-id="f5881-105">Este guia de tarefa usa a empresa demo USMF.</span><span class="sxs-lookup"><span data-stu-id="f5881-105">This task guide uses the USMF demo company.</span></span>

1. <span data-ttu-id="f5881-106">Vá para Contas a receber > Configurar pagamentos > Dias de pagamento</span><span class="sxs-lookup"><span data-stu-id="f5881-106">Go to Accounts receivable > Payments setup > Payment days.</span></span>
    * <span data-ttu-id="f5881-107">A configuração das condições de pagamento será compartilhada para contas a receber e contas a pagar.</span><span class="sxs-lookup"><span data-stu-id="f5881-107">The setup for the Terms of payment is shared for Accounts receivable and Accounts payable.</span></span> <span data-ttu-id="f5881-108">Se você define o no módulo, estarão disponíveis em outro módulo também.</span><span class="sxs-lookup"><span data-stu-id="f5881-108">If you define it in module, it will be available in the other module also.</span></span> <span data-ttu-id="f5881-109">Para este guia de tarefa, eu configurei todos os termos de pagamento em contas a receber.</span><span class="sxs-lookup"><span data-stu-id="f5881-109">For this task guide, I set up all the terms of payment under Accounts receivable.</span></span>  
2. <span data-ttu-id="f5881-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f5881-110">Click New.</span></span>
    * <span data-ttu-id="f5881-111">Crie um dia de pagamento se as condições de pagamento exigem um determinado dia da semana (segunda-feira, terça-feira, etc.) ou uma data específica do mês (5º, 10º, etc.).</span><span class="sxs-lookup"><span data-stu-id="f5881-111">Create a payment day if your terms of payment require a specific day of the week (Monday, Tuesday, etc) or a specific date of the month (5th, 10th, etc).</span></span>  
3. <span data-ttu-id="f5881-112">No campo de dia de pagamento, digite uma ID para o dia de pagamento no campo do dia de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f5881-112">In the Payment day field, enter an ID for the Payment day in the payment day field.</span></span>
4. <span data-ttu-id="f5881-113">No campo Descrição, insira uma descrição do tipo de dia de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f5881-113">In the Description field, enter a description of the payment day.</span></span>
5. <span data-ttu-id="f5881-114">No campo da semana ou mês, selecione a semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="f5881-114">In the Week/Month field, select either Week or Month.</span></span>
    * <span data-ttu-id="f5881-115">Se você deseja inserir um dia da semana, como segunda-feira, selecione a semana.</span><span class="sxs-lookup"><span data-stu-id="f5881-115">If you want to enter a day of the week, such as Monday, select Week.</span></span> <span data-ttu-id="f5881-116">Se você deseja inserir uma data no mês, como o 10º, selecione o mês.</span><span class="sxs-lookup"><span data-stu-id="f5881-116">If you want to enter a date in the month, such as the 10th, select Month.</span></span> <span data-ttu-id="f5881-117">Selecione Mês neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="f5881-117">Select Month for this example.</span></span>  
6. <span data-ttu-id="f5881-118">No campo Dia do mês, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="f5881-118">In the Day of month field, enter a date.</span></span>
    * <span data-ttu-id="f5881-119">A data deve ser inserida como um número, como '10', e não como '10º'.</span><span class="sxs-lookup"><span data-stu-id="f5881-119">The date should be entered as a number, such as '10', and not as '10th'.</span></span>  
7. <span data-ttu-id="f5881-120">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f5881-120">Click Save.</span></span>
8. <span data-ttu-id="f5881-121">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f5881-121">Close the page.</span></span>
9. <span data-ttu-id="f5881-122">Vá para Contas a receber > Configurar pagamentos > Termos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f5881-122">Go to Accounts receivable > Payments setup > Terms of payment.</span></span>
10. <span data-ttu-id="f5881-123">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f5881-123">Click New.</span></span>
    * <span data-ttu-id="f5881-124">As condições de pagamento são usadas para definir como as datas de vencimento serão calculadas.</span><span class="sxs-lookup"><span data-stu-id="f5881-124">Terms of payment is used to define how the due dates will be calculated.</span></span> <span data-ttu-id="f5881-125">A data de desconto à vista é definida em uma página separada.</span><span class="sxs-lookup"><span data-stu-id="f5881-125">The cash discount date setup is defined in a separate page.</span></span>  
11. <span data-ttu-id="f5881-126">No campo condições de pagamento, insira uma ID de campo nas condições de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f5881-126">In the Terms of payment field, enter an ID in the Terms of payment field.</span></span>
12. <span data-ttu-id="f5881-127">No campo Descrição, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="f5881-127">In the Description field, enter a description.</span></span>
13. <span data-ttu-id="f5881-128">Selecione um método de pagamento como C.O.D., a rede, o mês atual, etc.</span><span class="sxs-lookup"><span data-stu-id="f5881-128">Select a Payment method such as COD, Net, Current month, etc.</span></span>
    * <span data-ttu-id="f5881-129">O método Pagamento é usado para definir como a data de vencimento será calculada.</span><span class="sxs-lookup"><span data-stu-id="f5881-129">The Payment method is used to define the start of how the due will be calculated.</span></span>  <span data-ttu-id="f5881-130">Por exemplo, Rede é usada se a data de vencimento for sempre um número definido de meses ou dias após a data da fatura.</span><span class="sxs-lookup"><span data-stu-id="f5881-130">For example, Net is used if the due date is always a set number of months or days after the invoice date.</span></span> <span data-ttu-id="f5881-131">C.O.D. pode ser usado para quando o pagamento é necessário na fatura, dessa forma uma data de vencimento não seria calculada.</span><span class="sxs-lookup"><span data-stu-id="f5881-131">COD can be used to when payment is required upon invoice, so a due date wouldn't be calculated.</span></span> <span data-ttu-id="f5881-132">Selecione o mês atual para esta guia de tarefa.</span><span class="sxs-lookup"><span data-stu-id="f5881-132">Select Current month for this task guide.</span></span>  
14. <span data-ttu-id="f5881-133">Selecione um dia de pagamento se um determinado dia da semana ou a data serão incluídos no cálculo.</span><span class="sxs-lookup"><span data-stu-id="f5881-133">Select a Payment day if a specific day of the  week or date are included in the calculation.</span></span>
    * <span data-ttu-id="f5881-134">Dependendo das condições de pagamento, você pode inserir uma quantidade em meses ou dias.</span><span class="sxs-lookup"><span data-stu-id="f5881-134">Depending on your terms of payment, you may enter a quantity in Months or Days.</span></span> <span data-ttu-id="f5881-135">Ou você pode usar o plano de pagamento ou o dia de pagamento 'adicionar' ao final do método de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f5881-135">Or you can use the Payment schedule or Payment day to 'add' to the end of the Payment method.</span></span> <span data-ttu-id="f5881-136">Se a data de vencimento for sempre o 10º dia do mês seguinte, selecione um dia de pagamento do 10º.</span><span class="sxs-lookup"><span data-stu-id="f5881-136">If the due date will always be the 10th of the next month, select a Payment day of the 10th.</span></span>  
15. <span data-ttu-id="f5881-137">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f5881-137">Click Save.</span></span>
16. <span data-ttu-id="f5881-138">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f5881-138">Close the page.</span></span>
17. <span data-ttu-id="f5881-139">Vá para Contas a receber > Configurar pagamentos > Descontos à vista.</span><span class="sxs-lookup"><span data-stu-id="f5881-139">Go to Accounts receivable > Payments setup > Cash discounts.</span></span>
18. <span data-ttu-id="f5881-140">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f5881-140">Click New.</span></span>
    * <span data-ttu-id="f5881-141">Essa página é usada para definir como a data de desconto à vista será calculada.</span><span class="sxs-lookup"><span data-stu-id="f5881-141">This page is used to define how the cash discount date will be calculated.</span></span>  
19. <span data-ttu-id="f5881-142">No campo desconto à vista, digite uma ID no campo desconto à vista.</span><span class="sxs-lookup"><span data-stu-id="f5881-142">In the Cash discount field, enter an ID in the Cash discount field.</span></span>
20. <span data-ttu-id="f5881-143">No campo Descrição, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="f5881-143">In the Description field, enter a description.</span></span>
21. <span data-ttu-id="f5881-144">Se um desconto à vista estratificado estiver disponível, selecione o próximo código do desconto que é relevante após esse novo desconto à vista.</span><span class="sxs-lookup"><span data-stu-id="f5881-144">If a tiered cash discount is available, select the Next discount code that is relevant after this new cash discount.</span></span>
22. <span data-ttu-id="f5881-145">Insira o número de dias usados para calcular a data do desconto à vista.</span><span class="sxs-lookup"><span data-stu-id="f5881-145">Enter the number of days used to calculate the cash discount date.</span></span>
    * <span data-ttu-id="f5881-146">Se o princípio líquido for selecionado, o número de dias será adicionado à data da nota fiscal para calcular a data do desconto à vista.</span><span class="sxs-lookup"><span data-stu-id="f5881-146">If Net principle is selected, the number of days will be added to the invoice date to calculate the cash discount date.</span></span>  
23. <span data-ttu-id="f5881-147">Inserir percentual do desconto à vista.</span><span class="sxs-lookup"><span data-stu-id="f5881-147">Enter the percentage of the cash discount.</span></span>
24. <span data-ttu-id="f5881-148">Insira a conta principal a qual o desconto à vista será lançado para as notas fiscais do cliente.</span><span class="sxs-lookup"><span data-stu-id="f5881-148">Enter the main account to which the cash discount will post for customer invoices.</span></span>
25. <span data-ttu-id="f5881-149">No campo Contas de contrapartida de desconto, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="f5881-149">In the Discount offset accounts field, select an option.</span></span>
    * <span data-ttu-id="f5881-150">Se você selecionar 'Contas nas linhas da nota fiscal', o desconto à vista será lançado na mesma conta principal do ativo/despesa nas linhas da nota fiscal do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="f5881-150">If you select 'Accounts on the invoice lines', the cash discount will post to the same asset/expense main account on the lines of the vendor invoice.</span></span> <span data-ttu-id="f5881-151">Se você selecionar 'Usar conta principal para faturas de fornecedor', o desconto à vista lançará na conta principal definida por você em 'Conta principal para faturas de fornecedor'.</span><span class="sxs-lookup"><span data-stu-id="f5881-151">If you select 'Use main account for vendor invoices', the cash discount will post to the main account you define in the 'Main account for vendor invoices'.</span></span> <span data-ttu-id="f5881-152">Neste exemplo, selecione 'Usar conta principal para faturas de fornecedor'.</span><span class="sxs-lookup"><span data-stu-id="f5881-152">For this example, select 'Use main account for vendor invoices.'</span></span>  
26. <span data-ttu-id="f5881-153">Insira a conta principal a qual o desconto à vista será lançado para as notas fiscais do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="f5881-153">Enter the main account to which the cash discount will post for vendor invoices.</span></span>
27. <span data-ttu-id="f5881-154">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f5881-154">Click Save.</span></span>


