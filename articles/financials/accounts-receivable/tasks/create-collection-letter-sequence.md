--- 
title: "Criar uma sequência de cartas de cobrança"
description: "Use esta guia para criar uma tarefa de sequência de cartas de cobrança."
author: mikefalkner
manager: AnnBe
ms.date: 11/10/2016
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6331c3680169b305c4bfbfada4ba106b619be092
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-collection-letter-sequence"></a><span data-ttu-id="db785-103">Criar uma sequência de cartas de cobrança</span><span class="sxs-lookup"><span data-stu-id="db785-103">Create a collection letter sequence</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="db785-104">Use esta guia para criar uma tarefa de sequência de cartas de cobrança.</span><span class="sxs-lookup"><span data-stu-id="db785-104">Use this task guide to create a collection letter sequence.</span></span> <span data-ttu-id="db785-105">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="db785-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="db785-106">Vá para Crédito e coleções > Configuração > Configurar sequência de carta de coleção.</span><span class="sxs-lookup"><span data-stu-id="db785-106">Go to Credit and collections > Setup > Set up collection letter sequence.</span></span>
2. <span data-ttu-id="db785-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="db785-107">Click New.</span></span>
3. <span data-ttu-id="db785-108">No campo de sequência de cartas de cobrança, insira uma ID de sequência que represente a sequência.</span><span class="sxs-lookup"><span data-stu-id="db785-108">In the Collection letter sequence field, enter a sequence ID that will represent the sequence.</span></span> <span data-ttu-id="db785-109">Será usada ao configurar um perfil de lançamento.</span><span class="sxs-lookup"><span data-stu-id="db785-109">It will be used when you set up a posting profile.</span></span>
4. <span data-ttu-id="db785-110">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="db785-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="db785-111">As condições de pagamento são opcionais.</span><span class="sxs-lookup"><span data-stu-id="db785-111">The terms of payment is optional.</span></span> <span data-ttu-id="db785-112">Se você inserir um valor aqui, a nota fiscal da taxa de carta de cobrança usará essas condições de pagamento em vez das condições de pagamento estocadas com o cliente.</span><span class="sxs-lookup"><span data-stu-id="db785-112">If you enter a value here, the collection letter fee invoice will use these terms of payment instead of the terms of payment stored with the customer.</span></span>  
5. <span data-ttu-id="db785-113">No campo código da carta de cobrança, selecione o código para a primeira carta de cobrança que você deseja remeter.</span><span class="sxs-lookup"><span data-stu-id="db785-113">In the collection letter code field, select the code for the first collection letter that you want to send.</span></span>
    * <span data-ttu-id="db785-114">A primeira carta de cobrança é criada de acordo com a data de vencimento na fatura, o valor inserido para o período de carência no campo Dias nessa linha e outras informações inseridas nessa linha.</span><span class="sxs-lookup"><span data-stu-id="db785-114">The first collection letter is created according to the due date on the invoice, the value that you enter for the grace period in the Days field on this line, and other information that you enter on this line.</span></span>  
6. <span data-ttu-id="db785-115">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="db785-115">In the Description field, type a value.</span></span>
    * <span data-ttu-id="db785-116">A moeda da taxa padrão para a moeda do cliente.</span><span class="sxs-lookup"><span data-stu-id="db785-116">The currency for the fee defaults to the customer currency.</span></span> <span data-ttu-id="db785-117">O código da moeda pode ser diferente da moeda da nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="db785-117">This currency code can be different than the invoice currency.</span></span>  
7. <span data-ttu-id="db785-118">Clique em Adicionar para adicionar a carta de cobrança seguinte que será enviada na sequência</span><span class="sxs-lookup"><span data-stu-id="db785-118">Click Add to add the next collection letter that will be sent in the sequence</span></span>
    * <span data-ttu-id="db785-119">Em muitos casos, a primeira carta de cobrança é apenas um aviso.</span><span class="sxs-lookup"><span data-stu-id="db785-119">In many cases, the first collection letter is just a warning.</span></span> <span data-ttu-id="db785-120">Você pode adicionar taxas, se necessário.</span><span class="sxs-lookup"><span data-stu-id="db785-120">You can add fees if needed.</span></span>  
8. <span data-ttu-id="db785-121">No campo código da carta de cobrança, selecione o próximo código que será enviado na sequência.</span><span class="sxs-lookup"><span data-stu-id="db785-121">In the collection letter code field, select the next collection letter that will be sent in the sequence.</span></span>
9. <span data-ttu-id="db785-122">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="db785-122">In the Description field, type a value.</span></span>
10. <span data-ttu-id="db785-123">No campo de conta principal, selecione a conta de receita que será usada para taxas.</span><span class="sxs-lookup"><span data-stu-id="db785-123">In the main account field, select the revenue account that will be used for fees.</span></span>
11. <span data-ttu-id="db785-124">Digite a taxa que será carregada quando esta carta de cobrança é lançada.</span><span class="sxs-lookup"><span data-stu-id="db785-124">Enter the fee that will be charged when this collection letter is posted.</span></span>
12. <span data-ttu-id="db785-125">No campo Grupo de imposto sobre vendas do item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="db785-125">In the Item sales tax group field, click the drop down button to open the lookup.</span></span>
    * <span data-ttu-id="db785-126">Selecione um grupo de impostos sobre vendas do item se o imposto sobre vendas deve ser calculado na taxa.</span><span class="sxs-lookup"><span data-stu-id="db785-126">Select an item sales tax group if sales taxes must be calculated on the fee.</span></span>  
13. <span data-ttu-id="db785-127">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="db785-127">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="db785-128">Insira o saldo atrasado mínimo necessário antes de uma carta de coleção ser enviada.</span><span class="sxs-lookup"><span data-stu-id="db785-128">Enter the minimum overdue balance required before a collection letter is sent.</span></span>
15. <span data-ttu-id="db785-129">Insira o número de dias de carência que você permitirá.</span><span class="sxs-lookup"><span data-stu-id="db785-129">Enter the number of grace days that you will allow.</span></span>
    * <span data-ttu-id="db785-130">Esse é o número de dias após a data de vencimento que uma carta de cobrança pode ser produzida.</span><span class="sxs-lookup"><span data-stu-id="db785-130">This is the number of days after the due date that a collection letter can be generated.</span></span> <span data-ttu-id="db785-131">A data de vencimento que é usada para o cálculo depende da posição da carta de cobrança na sequência de cartas de cobrança:   ⦁    O período de carência para a carta de cobrança 1 é relativo à data de vencimento da fatura.</span><span class="sxs-lookup"><span data-stu-id="db785-131">The due date that is used for the calculation depends on the position of the collection letter in the collection letter sequence:   ⦁    The grace period for collection letter 1 is relative to the due date on the invoice.</span></span>  <span data-ttu-id="db785-132">⦁ O período de carência para as cartas de cobrança 2 e posteriores estão em relação à data em que a carta de cobrança anterior é lançada ou impressa, dependendo da seleção no campo código da carta de Cobrança atualização da página Parâmetro de contas a receber.</span><span class="sxs-lookup"><span data-stu-id="db785-132">⦁ The grace period for collection letters 2 and higher is relative to the date that the previous collection letter is posted or printed, depending on the selection in the Update collection letter code field in the Accounts receivable parameters page.</span></span>  
16. <span data-ttu-id="db785-133">Clique em Adicionar para adicionar a última carta de cobrança na sequência.</span><span class="sxs-lookup"><span data-stu-id="db785-133">Click Add to add the last collection letter in the sequence.</span></span>
    * <span data-ttu-id="db785-134">Você poderá adicionar até cinco códigos de carta de cobrança para uma sequência de cartas de cobrança.</span><span class="sxs-lookup"><span data-stu-id="db785-134">You can add up to five collection letter codes for a collection letter sequence.</span></span>  
17. <span data-ttu-id="db785-135">No campo código da carta de cobrança, selecione o próximo código que será enviado na sequência.</span><span class="sxs-lookup"><span data-stu-id="db785-135">In the collection letter code field, select the next collection letter that will be sent in the sequence.</span></span>
18. <span data-ttu-id="db785-136">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="db785-136">In the Description field, type a value.</span></span>
19. <span data-ttu-id="db785-137">No campo Conta principal, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="db785-137">In the Main account field, specify the desired values.</span></span>
20. <span data-ttu-id="db785-138">No campo Taxa em moeda, insira um número.</span><span class="sxs-lookup"><span data-stu-id="db785-138">In the Fee in currency field, enter a number.</span></span>
21. <span data-ttu-id="db785-139">No campo Grupo de imposto do item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="db785-139">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="db785-140">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="db785-140">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="db785-141">No campo Saldo vencido mínimo, insira um número.</span><span class="sxs-lookup"><span data-stu-id="db785-141">In the Minimum overdue balance field, enter a number.</span></span>
24. <span data-ttu-id="db785-142">No campo Dias, insira um número.</span><span class="sxs-lookup"><span data-stu-id="db785-142">In the Days field, enter a number.</span></span>
25. <span data-ttu-id="db785-143">Marque a caixa de seleção para fazer com que o cliente pare de receber entregas e notas fiscais.</span><span class="sxs-lookup"><span data-stu-id="db785-143">Select this check box to stop the customer from additional deliveries and invoicing.</span></span>
    * <span data-ttu-id="db785-144">Para desbloquear a conta, selecione Não no campo Faturamento e entrega em espera na página Clientes.</span><span class="sxs-lookup"><span data-stu-id="db785-144">To unblock the account, select No in the Invoicing and delivery on hold field in the Customers page.</span></span>  
26. <span data-ttu-id="db785-145">Expanda guia rápida Nota.</span><span class="sxs-lookup"><span data-stu-id="db785-145">Expand the Note fasttab.</span></span>
27. <span data-ttu-id="db785-146">Digite o texto a ser exibido na carta de cobrança para o código de carta de cobrança selecionado.</span><span class="sxs-lookup"><span data-stu-id="db785-146">Enter the text to appear on the collection letter for the selected collection letter code.</span></span>
    * <span data-ttu-id="db785-147">Você pode traduzir esse texto nos vários idiomas usando o menu das traduções acima da caixa da nota.</span><span class="sxs-lookup"><span data-stu-id="db785-147">You can translate this text in to multiple languages using the Translations menu above the note box.</span></span>  


