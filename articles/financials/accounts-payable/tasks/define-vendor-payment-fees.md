--- 
title: Definir taxas de pagamento de fornecedor
description: Configure taxas de pagamento de fornecedor.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendPaymFee, VendPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 399291a98ddc6b01fb08f7a5c629ec7a6f8acfbf
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="define-vendor-payment-fees"></a><span data-ttu-id="cb13b-103">Definir taxas de pagamento de fornecedor</span><span class="sxs-lookup"><span data-stu-id="cb13b-103">Define vendor payment fees</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cb13b-104">Configure taxas de pagamento de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="cb13b-104">Set up vendor payment fees.</span></span> <span data-ttu-id="cb13b-105">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="cb13b-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="cb13b-106">Vá para Contas a pagar > Configurar pagamento > Taxa de pagamento.</span><span class="sxs-lookup"><span data-stu-id="cb13b-106">Go to Accounts payable > Payment setup > Payment fee.</span></span>
2. <span data-ttu-id="cb13b-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="cb13b-107">Click New.</span></span>
3. <span data-ttu-id="cb13b-108">No campo ID da taxa, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="cb13b-108">In the Fee ID field, type a value.</span></span>
    * <span data-ttu-id="cb13b-109">A ID de taxa deve descrever quando essa taxa será usada, como "EFT_Fee".</span><span class="sxs-lookup"><span data-stu-id="cb13b-109">The Fee ID should describe when this fee will be used, such as "EFT_Fee".</span></span>  
4. <span data-ttu-id="cb13b-110">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="cb13b-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="cb13b-111">No campo Descrição de taxa, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="cb13b-111">In the Fee description field, type a value.</span></span>
    * <span data-ttu-id="cb13b-112">Adicione uma descrição para fornecer mais detalhes sobre quando a taxa será cobrada.</span><span class="sxs-lookup"><span data-stu-id="cb13b-112">Add a description to provide more detail on when the fee is assessed.</span></span>  
6. <span data-ttu-id="cb13b-113">No campo Encargo, selecione Fornecedor ou Razão.</span><span class="sxs-lookup"><span data-stu-id="cb13b-113">In the Charge field, select either Vendor or Ledger.</span></span>
    * <span data-ttu-id="cb13b-114">A razão é usada quando a taxa será cobrada por sua organização.</span><span class="sxs-lookup"><span data-stu-id="cb13b-114">Ledger is used when the fee will be expensed to your organization.</span></span>  <span data-ttu-id="cb13b-115">O fornecedor é usado quando a taxa for avaliada ao fornecedor.</span><span class="sxs-lookup"><span data-stu-id="cb13b-115">Vendor is used when the fee will be assessed to the vendor.</span></span>  
7. <span data-ttu-id="cb13b-116">Insira uma conta principal onde a taxa será cobrada.</span><span class="sxs-lookup"><span data-stu-id="cb13b-116">Enter a main account for where the fee will be expensed.</span></span>
    * <span data-ttu-id="cb13b-117">Esta opção está disponível apenas quando selecionar a opção Razão como Encargo.</span><span class="sxs-lookup"><span data-stu-id="cb13b-117">This option is only available when selecting Ledger as the Charge option.</span></span>  
8. <span data-ttu-id="cb13b-118">Selecione o diário em que a taxa pode ser usada.</span><span class="sxs-lookup"><span data-stu-id="cb13b-118">Select the journal on which this fee can be used.</span></span> 
    * <span data-ttu-id="cb13b-119">Para uma taxa de pagamento de fornecedor, você selecionaria o diário de 'Pagamento fornecedor'.</span><span class="sxs-lookup"><span data-stu-id="cb13b-119">For a vendor payment fee, you would select the journal 'Vendor disbursement.'</span></span>  
9. <span data-ttu-id="cb13b-120">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="cb13b-120">Click Save.</span></span>
10. <span data-ttu-id="cb13b-121">Clique em Configuração de taxa de pagamento.</span><span class="sxs-lookup"><span data-stu-id="cb13b-121">Click Payment fee setup.</span></span>
    * <span data-ttu-id="cb13b-122">Continue com a configuração da taxa de pagamento para definir quando a taxa deverá ser padronizada no diário selecionado.</span><span class="sxs-lookup"><span data-stu-id="cb13b-122">Continue to the Payment fee setup to define when the fee should default onto the journal you selected.</span></span>  
11. <span data-ttu-id="cb13b-123">Selecione Tabela, Grupo ou Tudo.</span><span class="sxs-lookup"><span data-stu-id="cb13b-123">Select either Table, Group or All.</span></span>
    * <span data-ttu-id="cb13b-124">Ela é usada para selecionar uma única conta bancária, Grupo é usado para selecionar um grupo bancário, e Tudo é usado como configuração de taxa para todas as contas bancárias</span><span class="sxs-lookup"><span data-stu-id="cb13b-124">Table is used to select a single bank account, Group is used to select a bank group, and All is to use this fee setup for all bank accounts</span></span>  
12. <span data-ttu-id="cb13b-125">Selecione um grupo de bancos ou uma conta bancária.</span><span class="sxs-lookup"><span data-stu-id="cb13b-125">Select either a bank group or a bank account.</span></span>
    * <span data-ttu-id="cb13b-126">A consulta mostrará o grupo de bancos se você selecionou Grupo, contas bancárias e mostrará se você selecionou Tabela.</span><span class="sxs-lookup"><span data-stu-id="cb13b-126">The lookup will show bank group if you selected Group, and will show bank accounts if you selected Table.</span></span>  
13. <span data-ttu-id="cb13b-127">Selecione o método de pagamento a ser usado por essa taxa.</span><span class="sxs-lookup"><span data-stu-id="cb13b-127">Select the method of payment for when this fee will be assessed.</span></span>
14. <span data-ttu-id="cb13b-128">Selecionar a especificação de pagamento para o método de pagamento selecionado.</span><span class="sxs-lookup"><span data-stu-id="cb13b-128">Select the Payment specification for the selected method of payment.</span></span>
    * <span data-ttu-id="cb13b-129">A especificação de pagamento é usada com métodos de transferência de fundo eletrônico de pagamento.</span><span class="sxs-lookup"><span data-stu-id="cb13b-129">The Payment specification is used with electronic fund transfer methods of payment.</span></span>  
15. <span data-ttu-id="cb13b-130">Selecione se a taxa é uma porcentagem, um valor ou um intervalo.</span><span class="sxs-lookup"><span data-stu-id="cb13b-130">Select whether the fee is a percentage, amount or interval.</span></span>
16. <span data-ttu-id="cb13b-131">Inserir o percentual do valor da taxa.</span><span class="sxs-lookup"><span data-stu-id="cb13b-131">Enter the percentage or amount of the fee.</span></span>
    * <span data-ttu-id="cb13b-132">Se a taxa for uma porcentagem, insira a porcentagem.</span><span class="sxs-lookup"><span data-stu-id="cb13b-132">If the Fee is a percentage, enter the percentage.</span></span> <span data-ttu-id="cb13b-133">Se a taxa for um valor, insira o valor da taxa.</span><span class="sxs-lookup"><span data-stu-id="cb13b-133">If the Fee is an amount, enter the amount of the fee.</span></span> <span data-ttu-id="cb13b-134">Se a taxa for um intervalo, use a guia Intervalo definida como as taxas estratificadas.</span><span class="sxs-lookup"><span data-stu-id="cb13b-134">If the Fee is an interval, use the Interval tab to defined the tiered fees.</span></span>  
17. <span data-ttu-id="cb13b-135">No campo Moeda da taxa, selecione a moeda na qual a taxa será avaliada.</span><span class="sxs-lookup"><span data-stu-id="cb13b-135">In the Fee currency field, select the currency in which the fee will be assessed.</span></span>
    * <span data-ttu-id="cb13b-136">Esta moeda é para a taxa.</span><span class="sxs-lookup"><span data-stu-id="cb13b-136">This currency is for the fee.</span></span> <span data-ttu-id="cb13b-137">A moeda do pagamento é usada para definir quando a regra de taxa deverá ser cobrada com base na moeda do pagamento.</span><span class="sxs-lookup"><span data-stu-id="cb13b-137">The payment currency is used to define when the fee rule should be assessed based on the payment's currency.</span></span> <span data-ttu-id="cb13b-138">Por exemplo, seu banco pode cobrar uma taxa quando um pagamento é efetuado em Euro, mas todos pagamentos restantes não são avaliados por uma taxa.</span><span class="sxs-lookup"><span data-stu-id="cb13b-138">For example, your bank may charge a fee when a payment is made in EUR, but all other payments aren't assessed a fee.</span></span>  
18. <span data-ttu-id="cb13b-139">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="cb13b-139">Click Save.</span></span>


