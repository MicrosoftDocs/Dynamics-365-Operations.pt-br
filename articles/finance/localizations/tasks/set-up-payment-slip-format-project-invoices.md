---
title: Configurar um formato da guia de pagamento para faturas de projeto
description: Geralmente, as empresas anexam guias de pagamento impressas a faturas para ajudar os clientes e fornecer uma referência de pagamento para lançamento e liquidação.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OMLegalEntity, CustFormletterParameters
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4671e1df3bc86361736b5882d67e6b160b4c5644
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174758"
---
# <a name="set-up-payment-slip-format-for-project-invoices"></a><span data-ttu-id="f0634-103">Configurar um formato da guia de pagamento para faturas de projeto</span><span class="sxs-lookup"><span data-stu-id="f0634-103">Set up payment slip format for project invoices</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f0634-104">Geralmente, as empresas anexam guias de pagamento impressas a faturas para ajudar os clientes e fornecer uma referência de pagamento para lançamento e liquidação.</span><span class="sxs-lookup"><span data-stu-id="f0634-104">Businesses commonly attach printed payment slips to invoices to assist customers and provide a payment reference for posting and settlement.</span></span> <span data-ttu-id="f0634-105">A guia de pagamento pode ser usada para faturas de projeto ou serviço, cartas de cobrança, notas de juros e demonstrativos de conta, além das faturas de venda e faturas de texto livre.</span><span class="sxs-lookup"><span data-stu-id="f0634-105">The payment slip can be used for project or service invoices, collection letters, interest notes, and account statements, in addition to sales invoices and free text invoices.</span></span> <span data-ttu-id="f0634-106">Para processar guias de pagamento, primeiro configure os formatos de número de identificação do credor e de anexo de guia de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f0634-106">To process payment slips, first set up your creditor identification number and payment slip attachment formats.</span></span>

<span data-ttu-id="f0634-107">Este procedimento usa a empresa de dados de demonstração DEMF.</span><span class="sxs-lookup"><span data-stu-id="f0634-107">This procedure uses the DEMF demo company.</span></span> 

<span data-ttu-id="f0634-108">Esta funcionalidade está disponível para entidades legais cujo endereço principal seja na Dinamarca.</span><span class="sxs-lookup"><span data-stu-id="f0634-108">This functionality is available for legal entities whose primary address is in Denmark.</span></span>


## <a name="set-up-a-creditor-id-number"></a><span data-ttu-id="f0634-109">Configurar um número de identificação do credor</span><span class="sxs-lookup"><span data-stu-id="f0634-109">Set up a creditor ID number</span></span>
1. <span data-ttu-id="f0634-110">Vá para Administração da organização > Organizações > Entidades legais.</span><span class="sxs-lookup"><span data-stu-id="f0634-110">Go to Organization administration > Organizations > Legal entities.</span></span>
2. <span data-ttu-id="f0634-111">Expandir ou recolher a seção Informações de conta bancária.</span><span class="sxs-lookup"><span data-stu-id="f0634-111">Expand or collapse the Bank account information section.</span></span>
3. <span data-ttu-id="f0634-112">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="f0634-112">Click Edit.</span></span>
4. <span data-ttu-id="f0634-113">No campo ID do FI-Credor, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f0634-113">In the FI-Creditor ID field, type a value.</span></span>
5. <span data-ttu-id="f0634-114">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f0634-114">Click Save.</span></span>
6. <span data-ttu-id="f0634-115">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f0634-115">Close the page.</span></span>

## <a name="set-up-a-payment-slip-format-for-invoices-notes-letters-and-statements"></a><span data-ttu-id="f0634-116">Configurar um formato da guia de pagamento para faturas, notas, letras e demonstrativos</span><span class="sxs-lookup"><span data-stu-id="f0634-116">Set up a payment slip format for invoices, notes, letters, and statements</span></span>
1. <span data-ttu-id="f0634-117">Vá para Contas a receber > Configuração > Formulários > Configuração de formulário.</span><span class="sxs-lookup"><span data-stu-id="f0634-117">Go to Accounts receivable > Setup > Forms > Form setup.</span></span>
2. <span data-ttu-id="f0634-118">Clique na guia Fatura.</span><span class="sxs-lookup"><span data-stu-id="f0634-118">Click the Invoice tab.</span></span>
3. <span data-ttu-id="f0634-119">No campo Anexo do pagamento associado na fatura de cliente, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="f0634-119">In the Associated payment attachment on customer invoice field, select an option.</span></span>
    * <span data-ttu-id="f0634-120">Nenhum – Não imprime uma guia de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f0634-120">None – Do not print a payment slip.</span></span> <span data-ttu-id="f0634-121">Escolha esta opção se o valor do pagamento estiver em uma moeda diferente da coroa dinamarquesa (DKK).</span><span class="sxs-lookup"><span data-stu-id="f0634-121">Choose this option if the payment amount is in a currency other than Danish kroner (DKK).</span></span>   <span data-ttu-id="f0634-122">FIK 751 – Imprima uma guia de pagamento FIK 751, se você pretende gravar manualmente o valor de pagamento e a data de vencimento na guia de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f0634-122">FIK 751 – Print an FIK 751 payment slip if you intend to manually write the payment amount and due date on the payment slip.</span></span>   <span data-ttu-id="f0634-123">FIK 752 – imprime uma guia de pagamento FIK 752, se você pretende usar uma guia de pagamento gerada pelo computador com um valor de pagamento e uma data de vencimento pré-impressos.</span><span class="sxs-lookup"><span data-stu-id="f0634-123">FIK 752 – Print an FIK 752 payment slip if you intend to use a computer-generated payment slip with a preprinted payment amount and due date.</span></span>  
4. <span data-ttu-id="f0634-124">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f0634-124">Click Save.</span></span>
5. <span data-ttu-id="f0634-125">Clique na guia Fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="f0634-125">Click the Free text invoice tab.</span></span>
6. <span data-ttu-id="f0634-126">No campo Anexo de pagamento associado na fatura de texto livre, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="f0634-126">In the Associated payment attachment on free text invoice field, select an option.</span></span>
    * <span data-ttu-id="f0634-127">Nenhum – Não imprime uma guia de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f0634-127">None – Do not print a payment slip.</span></span> <span data-ttu-id="f0634-128">Escolha esta opção se o valor do pagamento estiver em uma moeda diferente da coroa dinamarquesa (DKK).</span><span class="sxs-lookup"><span data-stu-id="f0634-128">Choose this option if the payment amount is in a currency other than Danish kroner (DKK).</span></span>   <span data-ttu-id="f0634-129">FIK 751 – Imprime uma guia de pagamento FIK 751, se você pretende gravar o valor de pagamento e a data de vencimento na guia de pagamento manualmente.</span><span class="sxs-lookup"><span data-stu-id="f0634-129">FIK 751 – Print an FIK 751 payment slip if you intend to write the payment amount and due date on the payment slip manually.</span></span>   <span data-ttu-id="f0634-130">FIK 752 – imprime uma guia de pagamento FIK 752, se você pretende usar uma guia de pagamento gerada pelo computador com um valor de pagamento e uma data de vencimento pré-impressos.</span><span class="sxs-lookup"><span data-stu-id="f0634-130">FIK 752 – Print an FIK 752 payment slip if you intend to use a computer-generated payment slip with a preprinted payment amount and due date.</span></span>  
7. <span data-ttu-id="f0634-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f0634-131">Click Save.</span></span>
8. <span data-ttu-id="f0634-132">Clique na guia Nota de juros.</span><span class="sxs-lookup"><span data-stu-id="f0634-132">Click the Interest note tab.</span></span>
9. <span data-ttu-id="f0634-133">No campo Anexo do pagamento associado na nota de juros, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="f0634-133">In the Associated payment attachment on interest note field, select an option.</span></span>
    * <span data-ttu-id="f0634-134">Nenhum – Não imprime uma guia de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f0634-134">None – Do not print a payment slip.</span></span> <span data-ttu-id="f0634-135">Escolha esta opção se o valor do pagamento estiver em uma moeda diferente da coroa dinamarquesa (DKK).</span><span class="sxs-lookup"><span data-stu-id="f0634-135">Choose this option if the payment amount is in a currency other than Danish kroner (DKK).</span></span>   <span data-ttu-id="f0634-136">FIK 751 – Imprime uma guia de pagamento FIK 751, se você pretende gravar o valor de pagamento e a data de vencimento na guia de pagamento manualmente.</span><span class="sxs-lookup"><span data-stu-id="f0634-136">FIK 751 – Print an FIK 751 payment slip if you intend to write the payment amount and due date on the payment slip manually.</span></span>   <span data-ttu-id="f0634-137">FIK 752 – imprime uma guia de pagamento FIK 752, se você pretende usar uma guia de pagamento gerada pelo computador com um valor de pagamento e uma data de vencimento pré-impressos.</span><span class="sxs-lookup"><span data-stu-id="f0634-137">FIK 752 – Print an FIK 752 payment slip if you intend to use a computer-generated payment slip with a preprinted payment amount and due date.</span></span>  
10. <span data-ttu-id="f0634-138">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f0634-138">Click Save.</span></span>
11. <span data-ttu-id="f0634-139">Clique na guia Carta de cobrança.</span><span class="sxs-lookup"><span data-stu-id="f0634-139">Click the Collection letter tab.</span></span>
12. <span data-ttu-id="f0634-140">No campo Anexo de pagamento associado na carta de cobrança, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="f0634-140">In the Associated payment attachment on collection letter field, select an option.</span></span>
    * <span data-ttu-id="f0634-141">Nenhum – Não imprime uma guia de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f0634-141">None – Do not print a payment slip.</span></span> <span data-ttu-id="f0634-142">Escolha esta opção se o valor do pagamento estiver em uma moeda diferente da coroa dinamarquesa (DKK).</span><span class="sxs-lookup"><span data-stu-id="f0634-142">Choose this option if the payment amount is in a currency other than Danish kroner (DKK).</span></span>   <span data-ttu-id="f0634-143">FIK 751 – Imprime uma guia de pagamento FIK 751, se você pretende gravar o valor de pagamento e a data de vencimento na guia de pagamento manualmente.</span><span class="sxs-lookup"><span data-stu-id="f0634-143">FIK 751 – Print an FIK 751 payment slip if you intend to write the payment amount and due date on the payment slip manually.</span></span>   <span data-ttu-id="f0634-144">FIK 752 – imprime uma guia de pagamento FIK 752, se você pretende usar uma guia de pagamento gerada pelo computador com um valor de pagamento e uma data de vencimento pré-impressos.</span><span class="sxs-lookup"><span data-stu-id="f0634-144">FIK 752 – Print an FIK 752 payment slip if you intend to use a computer-generated payment slip with a preprinted payment amount and due date.</span></span>  
13. <span data-ttu-id="f0634-145">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f0634-145">Click Save.</span></span>
14. <span data-ttu-id="f0634-146">Clique na guia Demonstrativo da conta.</span><span class="sxs-lookup"><span data-stu-id="f0634-146">Click the Account statement tab.</span></span>
15. <span data-ttu-id="f0634-147">No campo Anexo de pagamento associado no demonstrativo da conta, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="f0634-147">In the Associated payment attachment on account statement field, select an option.</span></span>
    * <span data-ttu-id="f0634-148">Nenhum – Não imprime uma guia de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f0634-148">None – Do not print a payment slip.</span></span> <span data-ttu-id="f0634-149">Escolha esta opção se o valor do pagamento estiver em uma moeda diferente da coroa dinamarquesa (DKK).</span><span class="sxs-lookup"><span data-stu-id="f0634-149">Choose this option if the payment amount is in a currency other than Danish kroner (DKK).</span></span>   <span data-ttu-id="f0634-150">FIK 751 – Imprime uma guia de pagamento FIK 751, se você pretende gravar o valor de pagamento e a data de vencimento na guia de pagamento manualmente.</span><span class="sxs-lookup"><span data-stu-id="f0634-150">FIK 751 – Print an FIK 751 payment slip if you intend to write the payment amount and due date on the payment slip manually.</span></span>   <span data-ttu-id="f0634-151">FIK 752 – imprime uma guia de pagamento FIK 752, se você pretende usar uma guia de pagamento gerada pelo computador com um valor de pagamento e uma data de vencimento pré-impressos.</span><span class="sxs-lookup"><span data-stu-id="f0634-151">FIK 752 – Print an FIK 752 payment slip if you intend to use a computer-generated payment slip with a preprinted payment amount and due date.</span></span>  
16. <span data-ttu-id="f0634-152">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f0634-152">Click Save.</span></span>
17. <span data-ttu-id="f0634-153">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f0634-153">Close the page.</span></span>
