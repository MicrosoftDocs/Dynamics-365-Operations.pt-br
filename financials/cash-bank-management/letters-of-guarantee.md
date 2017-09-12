---
title: Cartas de garantia
description: "Este artigo fornece informações sobre as cartas de garantia. Em uma carta de garantia, um banco concorda em pagar um valor específico de dinheiro a uma pessoa se um dos padrões de clientes do banco em um pagamento ou obrigação àquela pessoa."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankLGGuarantee
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 18291
ms.assetid: 5c0b5e37-d51d-4a01-bb37-1882173abb9f
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 45d28110ca93875eb534c69886ac2074ea4fe737
ms.openlocfilehash: d7144a979b98b3dbd2052661945e6d4fe22220a7
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2017

---

# <a name="letters-of-guarantee"></a><span data-ttu-id="a5272-104">Cartas de garantia</span><span class="sxs-lookup"><span data-stu-id="a5272-104">Letters of guarantee</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="a5272-105">Este artigo fornece informações sobre as cartas de garantia.</span><span class="sxs-lookup"><span data-stu-id="a5272-105">This article provides information about letters of guarantee.</span></span> <span data-ttu-id="a5272-106">Em uma carta de garantia, um banco concorda em pagar um valor específico de dinheiro a uma pessoa se um dos padrões de clientes do banco em um pagamento ou obrigação àquela pessoa.</span><span class="sxs-lookup"><span data-stu-id="a5272-106">In a letter of guarantee, a bank agrees to pay a specific amount of money to a person if one of the bank's customers defaults on a payment or obligation to that person.</span></span> 

<span data-ttu-id="a5272-107">Uma carta de garantia é um contrato de um banco (o fiador) para pagar um valor definido para outra pessoa (o credor), se o cliente do banco (o principal) não cumprir um pagamento ou uma obrigação ao beneficiário.</span><span class="sxs-lookup"><span data-stu-id="a5272-107">A letter of guarantee is an agreement by a bank (the guarantor) to pay a set amount of money to some person (the beneficiary) if a bank customer (the principal) defaults on a payment or an obligation to the beneficiary.</span></span> <span data-ttu-id="a5272-108">As notas de garantia não são transferíveis.</span><span class="sxs-lookup"><span data-stu-id="a5272-108">Letters of guarantee aren't transferable.</span></span> <span data-ttu-id="a5272-109">Só se aplicam ao beneficiário que é mencionado no contrato.</span><span class="sxs-lookup"><span data-stu-id="a5272-109">They apply only to the beneficiary who is named in the agreement.</span></span> <span data-ttu-id="a5272-110">O principal pode solicitar um aumento ou uma redução no valor de uma carta de garantia, sujeito às condições do contrato.</span><span class="sxs-lookup"><span data-stu-id="a5272-110">The principal can request an increase or decrease in the value of a letter of guarantee, subject to the terms of the agreement.</span></span> 

<span data-ttu-id="a5272-111">Para liquidar uma carta de garantia, o beneficiário deverá enviar a carta de garantia original e informar ao banco o não cumprimento do principal antes da data de vencimento.</span><span class="sxs-lookup"><span data-stu-id="a5272-111">To liquidate a letter of guarantee, the beneficiary must submit the original letter of guarantee and inform the bank of the principal’s default before the expiration date.</span></span> <span data-ttu-id="a5272-112">O banco paga o valor devido à conta do beneficiário, de acordo com os termos na carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="a5272-112">The bank then pays the amount that is due to the beneficiary's account, according to the terms in the letter of guarantee.</span></span> <span data-ttu-id="a5272-113">O banco reserva uma porcentagem de pagamento como margem.</span><span class="sxs-lookup"><span data-stu-id="a5272-113">The bank reserves a percentage of the payment as a margin.</span></span> <span data-ttu-id="a5272-114">A porcentagem é acordada e especificada nas condições do contrato.</span><span class="sxs-lookup"><span data-stu-id="a5272-114">The percentage is agreed upon and specified in the terms of the agreement.</span></span> 

<span data-ttu-id="a5272-115">Você pode criar um código para rastrear a finalidade de uma carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="a5272-115">You can create a code to track the purpose of a letter of guarantee.</span></span> <span data-ttu-id="a5272-116">Você também pode especificar os motivos que podem ser associados a uma carta de garantia quando a carta é cancelada.</span><span class="sxs-lookup"><span data-stu-id="a5272-116">You can also specify the reasons that can be associated with a letter of guarantee when the letter is canceled.</span></span> <span data-ttu-id="a5272-117">Você pode exibir os códigos de finalidade e os motivos do banco nas páginas **Códigos de finalidade do pagamento** e **Motivos do banco**.</span><span class="sxs-lookup"><span data-stu-id="a5272-117">You can view the purpose codes and bank reasons on the **Payment purpose codes** and **Bank reasons** pages.</span></span> 

<span data-ttu-id="a5272-118">Você pode usar a página **Carta de garantia** para concluir essas tarefas:</span><span class="sxs-lookup"><span data-stu-id="a5272-118">You can use the **Letter of guarantee** page to complete these tasks:</span></span>

-   <span data-ttu-id="a5272-119">Criar entradas do razão corretas e eliminar a entrada manual.</span><span class="sxs-lookup"><span data-stu-id="a5272-119">Create correct ledger entries, and eliminate manual entry.</span></span>
-   <span data-ttu-id="a5272-120">Registrar todas as transações monetárias e não monetárias e rastrear saldos de cartas de garantia.</span><span class="sxs-lookup"><span data-stu-id="a5272-120">Record all monetary and nonmonetary transactions, and track balances of letters of guarantee.</span></span>
-   <span data-ttu-id="a5272-121">Registrar e rastrear o status e o vencimento das cartas de garantia.</span><span class="sxs-lookup"><span data-stu-id="a5272-121">Record and track the status and expiration of letters of guarantee.</span></span>
-   <span data-ttu-id="a5272-122">Gerar um relatório que lista os bancos que estão mantendo cartas de garantia.</span><span class="sxs-lookup"><span data-stu-id="a5272-122">Generate a report that lists the banks that are holding letters of guarantee.</span></span>

<span data-ttu-id="a5272-123">A tabela a seguir descreve as ações que podem ser realizadas em uma carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="a5272-123">The following table describes the actions that you can perform on a letter of guarantee.</span></span>

| <span data-ttu-id="a5272-124">Ação</span><span class="sxs-lookup"><span data-stu-id="a5272-124">Action</span></span>              | <span data-ttu-id="a5272-125">Finalidade</span><span class="sxs-lookup"><span data-stu-id="a5272-125">Purpose</span></span>                                                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="a5272-126">Enviar ao banco</span><span class="sxs-lookup"><span data-stu-id="a5272-126">Submit to bank</span></span>      | <span data-ttu-id="a5272-127">Enviar a solicitação de carta de garantia para o banco.</span><span class="sxs-lookup"><span data-stu-id="a5272-127">Submit the letter of guarantee request to the bank.</span></span>                                                                       |
| <span data-ttu-id="a5272-128">Receber do banco</span><span class="sxs-lookup"><span data-stu-id="a5272-128">Receive from bank</span></span>   | <span data-ttu-id="a5272-129">Depois que o banco concordar com a solicitação enviada, cobrar a carta de garantia do banco.</span><span class="sxs-lookup"><span data-stu-id="a5272-129">After the bank agrees to the submitted request, collect the letter of guarantee from the bank.</span></span>                            |
| <span data-ttu-id="a5272-130">Dar ao beneficiário</span><span class="sxs-lookup"><span data-stu-id="a5272-130">Give to beneficiary</span></span> | <span data-ttu-id="a5272-131">Depois de receber a carta de garantia do banco, fornecê-la ao beneficiário.</span><span class="sxs-lookup"><span data-stu-id="a5272-131">After you receive the letter of guarantee from the bank, provide the letter of guarantee to the beneficiary.</span></span>              |
| <span data-ttu-id="a5272-132">Aumentar o valor</span><span class="sxs-lookup"><span data-stu-id="a5272-132">Increase value</span></span>      | <span data-ttu-id="a5272-133">Se o portador e o principal concordarem, aumentar o valor monetário.</span><span class="sxs-lookup"><span data-stu-id="a5272-133">If the beneficiary and the principal agree, increase the monetary value.</span></span>                                                  |
| <span data-ttu-id="a5272-134">Diminuir o valor</span><span class="sxs-lookup"><span data-stu-id="a5272-134">Decrease value</span></span>      | <span data-ttu-id="a5272-135">Se o portador e o principal concordarem, reduzir o valor monetário.</span><span class="sxs-lookup"><span data-stu-id="a5272-135">If the beneficiary and the principal agree, decrease the monetary value.</span></span>                                                  |
| <span data-ttu-id="a5272-136">Estender</span><span class="sxs-lookup"><span data-stu-id="a5272-136">Extend</span></span>              | <span data-ttu-id="a5272-137">Depois que você fornecer a carta de garantia ao beneficiário, aumente o período de validade, se necessário.</span><span class="sxs-lookup"><span data-stu-id="a5272-137">After you provide the letter of guarantee to the beneficiary, extend the period of validity, if an extension is required.</span></span> |
| <span data-ttu-id="a5272-138">Cancelamento</span><span class="sxs-lookup"><span data-stu-id="a5272-138">Cancel</span></span>              | <span data-ttu-id="a5272-139">Quando a finalidade para a qual a carta de garantia foi solicitada não se aplicar, cancele o contrato.</span><span class="sxs-lookup"><span data-stu-id="a5272-139">When the purpose that the letter of guarantee was requested for no longer applies, cancel the agreement.</span></span>                  |
| <span data-ttu-id="a5272-140">Liquidar</span><span class="sxs-lookup"><span data-stu-id="a5272-140">Liquidate</span></span>           | <span data-ttu-id="a5272-141">Quando o beneficiário apresentar a carta de garantia ao banco, descontá-la.</span><span class="sxs-lookup"><span data-stu-id="a5272-141">When the beneficiary presents the letter of guarantee to the bank, cash out the letter of guarantee.</span></span>                      |


<span data-ttu-id="a5272-142">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="a5272-142">For more information, see the following topics:</span></span>

[<span data-ttu-id="a5272-143">Transação da carta de garantia</span><span class="sxs-lookup"><span data-stu-id="a5272-143">Letter of guarantee transaction</span></span>](tasks/letter-guarantee-transaction.md)

[<span data-ttu-id="a5272-144">Configurar recursos bancários e perfis de lançamento para cartas de garantia</span><span class="sxs-lookup"><span data-stu-id="a5272-144">Set up bank facilities and posting profiles for letters of guarantee</span></span>](tasks/set-up-bank-facilities-posting-profiles.md)



