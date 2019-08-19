---
title: Estabelecer taxas de pagamento de clientes
description: Criar taxas de pagamento para pagamentos de clientes.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymFee, CustPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f18b88cfdeef2e66003cd4411ace4b4c49e42f6f
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834430"
---
# <a name="establish-customer-payment-fees"></a><span data-ttu-id="80210-103">Estabelecer taxas de pagamento de clientes</span><span class="sxs-lookup"><span data-stu-id="80210-103">Establish customer payment fees</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="80210-104">Criar taxas de pagamento para pagamentos de clientes.</span><span class="sxs-lookup"><span data-stu-id="80210-104">Create payment fees for customer payments.</span></span>

<span data-ttu-id="80210-105">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="80210-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="80210-106">Vá para Contas a receber > Configurar pagamentos > Taxa de pagamento</span><span class="sxs-lookup"><span data-stu-id="80210-106">Go to Accounts receivable > Payments setup > Payment fee.</span></span>
2. <span data-ttu-id="80210-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="80210-107">Click New.</span></span>
3. <span data-ttu-id="80210-108">No campo ID de taxa, insira um ID de taxa.</span><span class="sxs-lookup"><span data-stu-id="80210-108">In the Fee ID field, enter a Fee ID.</span></span>
    * <span data-ttu-id="80210-109">Exibe a ID de taxa em diários de pagamentos, o que o tornam descritivo para compreender a taxa que será avaliada.</span><span class="sxs-lookup"><span data-stu-id="80210-109">The Fee ID displays on payment journals, so make it descriptive to understand what fee is being assessed.</span></span>  
4. <span data-ttu-id="80210-110">No campo Nome, insira um Nome de taxa.</span><span class="sxs-lookup"><span data-stu-id="80210-110">In the Name field, enter a fee Name.</span></span>
5. <span data-ttu-id="80210-111">No campo Descrição de taxa, insira uma descrição para a taxa.</span><span class="sxs-lookup"><span data-stu-id="80210-111">In the Fee description field, enter a description for the fee.</span></span>
6. <span data-ttu-id="80210-112">Selecione se a taxa será cobrada do cliente ou em uma conta contábil.</span><span class="sxs-lookup"><span data-stu-id="80210-112">Select whether the fee will be charged to the Customer or a Ledger account.</span></span>
    * <span data-ttu-id="80210-113">Se o cliente for avaliado pela taxa, selecione Cliente.</span><span class="sxs-lookup"><span data-stu-id="80210-113">If the customer is assessed the fee, select Customer.</span></span> <span data-ttu-id="80210-114">Se a taxa for avaliada por sua organização como uma despesa, selecione o Razão.</span><span class="sxs-lookup"><span data-stu-id="80210-114">If the fee will be assess to your organization as an expense, select Ledger.</span></span> <span data-ttu-id="80210-115">Para essa tarefa, selecione Cliente.</span><span class="sxs-lookup"><span data-stu-id="80210-115">For this task, select Customer.</span></span>  
7. <span data-ttu-id="80210-116">Selecione o tipo de diário que pode usar a taxa de pagamento.</span><span class="sxs-lookup"><span data-stu-id="80210-116">Select the type of  journal that can use this payment fee.</span></span>
    * <span data-ttu-id="80210-117">Se essas taxas são usadas para pagamentos de cliente, o tipo de diário será provavelmente Pagamento de cliente.</span><span class="sxs-lookup"><span data-stu-id="80210-117">If these fees are used for customer payments, the journal type will likely be Customer payment.</span></span>  
8. <span data-ttu-id="80210-118">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="80210-118">Click Save.</span></span>
9. <span data-ttu-id="80210-119">Clique em Configuração de taxa de pagamento.</span><span class="sxs-lookup"><span data-stu-id="80210-119">Click Payment fee setup.</span></span>
    * <span data-ttu-id="80210-120">A configuração da taxa de pagamento é usada para definir os critérios para a taxa de pagamento que será avaliada.</span><span class="sxs-lookup"><span data-stu-id="80210-120">The Payment fee setup is used to define the criteria for when the payment fee will be assessed.</span></span>  <span data-ttu-id="80210-121">Por exemplo, você pode definir que a taxa será calculada se a conta bancária for USMF OPER, e o método de pagamento é cheque.</span><span class="sxs-lookup"><span data-stu-id="80210-121">For example, you can define that the fee will be calculated if the bank account is USMF OPER, and the method of payment is check.</span></span>  
10. <span data-ttu-id="80210-122">Selecione Tabela, Grupo ou Tudo para definir contas bancárias que serão avaliadas por essa taxa.</span><span class="sxs-lookup"><span data-stu-id="80210-122">Select either Table, Group or All to define which bank accounts will be assessed this fee.</span></span>
    * <span data-ttu-id="80210-123">Se você selecionar Tudo, todas as contas bancárias podem ser avaliadas por essa taxa.</span><span class="sxs-lookup"><span data-stu-id="80210-123">If you select All, all bank accounts could be assessed this fee.</span></span>  <span data-ttu-id="80210-124">Se você selecionar Tabela, apenas a conta bancária que você seleciona pode ser cobrada por essa taxa.</span><span class="sxs-lookup"><span data-stu-id="80210-124">If you select Table, only the bank account you select could be assessed this fee.</span></span> <span data-ttu-id="80210-125">Se você selecionar Grupo, somente as contas bancárias no grupo de bancos selecionado podem ser avaliadas por essa taxa.</span><span class="sxs-lookup"><span data-stu-id="80210-125">If you select Group, only the bank accounts in the selected bank group could be assessed this fee.</span></span>  
11. <span data-ttu-id="80210-126">Selecione um grupo de bancos ou uma conta bancária.</span><span class="sxs-lookup"><span data-stu-id="80210-126">Select either a bank group or a bank account.</span></span>
    * <span data-ttu-id="80210-127">Se você selecionou Tabela, a pesquisa exibirá contas bancárias.</span><span class="sxs-lookup"><span data-stu-id="80210-127">If you selected Table, the lookup will display bank accounts.</span></span> <span data-ttu-id="80210-128">Se você selecionou Grupo, a pesquisa exibirá grupos bancários.</span><span class="sxs-lookup"><span data-stu-id="80210-128">If you selected Group, the lookup will display bank groups.</span></span>  
12. <span data-ttu-id="80210-129">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="80210-129">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="80210-130">Selecione o Método de pagamento a ser usado por essa taxa.</span><span class="sxs-lookup"><span data-stu-id="80210-130">Select the Method of payment for which this fee will be assessed.</span></span>
    * <span data-ttu-id="80210-131">Por exemplo, você pode classificar uma taxa para os clientes se enviar pagamentos como um cheque, em vez de como um pagamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="80210-131">For example, you may assess a fee to your customers if they send payments as a check, rather than as an electronic payment.</span></span>  
14. <span data-ttu-id="80210-132">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="80210-132">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="80210-133">Se relevante, insira uma moeda do pagamento.</span><span class="sxs-lookup"><span data-stu-id="80210-133">If relevant, enter a payment currency.</span></span>
    * <span data-ttu-id="80210-134">A moeda de pagamento é usada como critérios adicionais para se a taxa que será avaliada.</span><span class="sxs-lookup"><span data-stu-id="80210-134">The payment currency is used as an additional criteria for whether the fee will be assessed.</span></span>  <span data-ttu-id="80210-135">Por exemplo, seu banco pode cobrar uma taxa adicional para pagamentos recebidos na moeda USD, desde que transacionem normalmente somente na moeda de Euro.</span><span class="sxs-lookup"><span data-stu-id="80210-135">For example, your bank may charge an extra fee for payments received in USD currency, since they normally only transact in EUR currency.</span></span>  
16. <span data-ttu-id="80210-136">Selecione se a taxa será uma porcentagem, um valor ou um intervalo.</span><span class="sxs-lookup"><span data-stu-id="80210-136">Select whether the fee will be a percent, amount or interval.</span></span>
17. <span data-ttu-id="80210-137">Insira a porcentagem ou o valor da taxa.</span><span class="sxs-lookup"><span data-stu-id="80210-137">Enter either percentage or amount of the fee.</span></span>
    * <span data-ttu-id="80210-138">Se o campo Porcentagem/Valor for porcentagem, o valor fornecido aqui será uma porcentagem.</span><span class="sxs-lookup"><span data-stu-id="80210-138">If the Percentage/Amount field is Percent, then the value enter here will be a percentage.</span></span> <span data-ttu-id="80210-139">Se o campo Porcentagem/Valor for Valor, o valor fornecido aqui será um valor.</span><span class="sxs-lookup"><span data-stu-id="80210-139">If the Percentage/Amount field is Amount, then the value you enter here will be an amount.</span></span> <span data-ttu-id="80210-140">Se o campo Porcentagem/Valor for intervalo, use a guia Intervalo para definir as camadas.</span><span class="sxs-lookup"><span data-stu-id="80210-140">If the Percentage/Amount field is Interval, use the Interval tab to define the tiers.</span></span>  
18. <span data-ttu-id="80210-141">No campo Moeda da taxa, selecione a moeda da taxa.</span><span class="sxs-lookup"><span data-stu-id="80210-141">In the Fee currency field, select the currency of the fee.</span></span>
    * <span data-ttu-id="80210-142">Esta é a moeda na qual a taxa será criada.</span><span class="sxs-lookup"><span data-stu-id="80210-142">This is the currency in which the fee will be created.</span></span>  
19. <span data-ttu-id="80210-143">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="80210-143">Click Save.</span></span>

