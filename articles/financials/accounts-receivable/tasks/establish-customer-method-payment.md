--- 
title: "Estabelecer método de pagamento de clientes"
description: "Criar um método de pagamento para pagamentos de clientes."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPaymMode, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 4dd61e24f882292a8bf6aec96037845ecbf7f1e8
ms.contentlocale: pt-br
ms.lasthandoff: 09/11/2018

---
# <a name="establish-customer-method-of-payment"></a><span data-ttu-id="3bd62-103">Estabelecer método de pagamento de clientes</span><span class="sxs-lookup"><span data-stu-id="3bd62-103">Establish customer method of payment</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3bd62-104">Criar um método de pagamento para pagamentos de clientes.</span><span class="sxs-lookup"><span data-stu-id="3bd62-104">Create a method of payment for customer payments.</span></span> <span data-ttu-id="3bd62-105">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="3bd62-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="3bd62-106">Vá para Contas a receber > Configurar pagamentos > Métodos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="3bd62-106">Go to Accounts receivable > Payments setup > Methods of payment.</span></span>
2. <span data-ttu-id="3bd62-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="3bd62-107">Click New.</span></span>
3. <span data-ttu-id="3bd62-108">No campo Método de pagamento, insira um ID para o método de pagamento.</span><span class="sxs-lookup"><span data-stu-id="3bd62-108">In the Method of payment field, enter an ID for the method of payment.</span></span>
    * <span data-ttu-id="3bd62-109">O método da ID de pagamento é mostrado nas notas fiscais e pagamentos, para que o torne descritivo suficiente para compreender o tipo de pagamento que está sendo registrado, e para a conta bancária.</span><span class="sxs-lookup"><span data-stu-id="3bd62-109">The Method of payment ID is shown on invoices and payments, so make it descriptive enough to understand what type of payment is being recorded, and for what bank account.</span></span>  
4. <span data-ttu-id="3bd62-110">No campo Descrição, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="3bd62-110">In the Description field, enter a description.</span></span>
5. <span data-ttu-id="3bd62-111">Selecionar o status de pagamento é necessário para que os pagamentos sejam lançados.</span><span class="sxs-lookup"><span data-stu-id="3bd62-111">Select what payment status is required in order for payments to be posted.</span></span>
    * <span data-ttu-id="3bd62-112">Ao criar um pagamento de cliente, ele só pode ser lançado quando o status do pagamento corresponde ao status do pagamento definido aqui.</span><span class="sxs-lookup"><span data-stu-id="3bd62-112">When creating a customer payment, it can only be posted when the payment status matches the payment status you define here.</span></span>  
6. <span data-ttu-id="3bd62-113">Selecione como os pagamentos de clientes devem ser criados para notas fiscais.</span><span class="sxs-lookup"><span data-stu-id="3bd62-113">Select how customers payments should be created for invoices.</span></span>
    * <span data-ttu-id="3bd62-114">Esta opção é usada apenas para executar uma proposta de pagamento.</span><span class="sxs-lookup"><span data-stu-id="3bd62-114">This option is only used when running a payment proposal.</span></span> <span data-ttu-id="3bd62-115">Uma proposta de pagamento pode ser usada para pagamentos de cliente ao fazer os débitos diretos, e o recebimento dos fundos das contas bancárias dos clientes.</span><span class="sxs-lookup"><span data-stu-id="3bd62-115">A payment proposal could be used for customer payments when doing direct debits, and pulling the funds from the customers' bank accounts.</span></span>  
7. <span data-ttu-id="3bd62-116">Selecionar o tipo de pagamento.</span><span class="sxs-lookup"><span data-stu-id="3bd62-116">Select the type of payment.</span></span>
    * <span data-ttu-id="3bd62-117">O tipo de pagamento ajudará a determinar se qualquer validação ocorre ou não no pagamento.</span><span class="sxs-lookup"><span data-stu-id="3bd62-117">The payment type will help determine whether some validation will occur or not on the payment.</span></span>  
8. <span data-ttu-id="3bd62-118">Selecione quais tipos de pagamentos de conta serão lançados.</span><span class="sxs-lookup"><span data-stu-id="3bd62-118">Select what account type payments will post to.</span></span>
    * <span data-ttu-id="3bd62-119">Normalmente, o banco deve ser selecionado para essa opção.</span><span class="sxs-lookup"><span data-stu-id="3bd62-119">Typically, Bank would be selected for this option.</span></span>  
9. <span data-ttu-id="3bd62-120">Selecione a conta bancária na qual o pagamento será registrado.</span><span class="sxs-lookup"><span data-stu-id="3bd62-120">Select the bank account into which this payment will be recorded.</span></span>
10. <span data-ttu-id="3bd62-121">Insira o tipo de transação bancária para identificar o tipo de pagamento usado pelo banco.</span><span class="sxs-lookup"><span data-stu-id="3bd62-121">Enter the Bank transaction type to identify the type of payment used by your bank.</span></span>
    * <span data-ttu-id="3bd62-122">O tipo de transação bancária será usado durante o processo de reconciliação do banco, e pode facilitar a reconciliação.</span><span class="sxs-lookup"><span data-stu-id="3bd62-122">The bank transaction type is used during the bank reconciliation process, and can make reconciliation easier.</span></span>  
11. <span data-ttu-id="3bd62-123">Selecione se o pagamento será lançado temporariamente em uma conta de transição.</span><span class="sxs-lookup"><span data-stu-id="3bd62-123">Select whether this payment will temporarily post to a bridging account.</span></span>
    * <span data-ttu-id="3bd62-124">Se desejar testar o tempo de flutuação para que um pagamento desmarque o banco, use a funcionalidade de construção de transição.</span><span class="sxs-lookup"><span data-stu-id="3bd62-124">If you want to try the float time for a payment to clear the bank, use the Bridging functionality.</span></span> <span data-ttu-id="3bd62-125">O pagamento será lançado temporariamente em uma conta contábil até que o banco a desmarque quando o pagamento se moverá à conta bancária como definido aqui.</span><span class="sxs-lookup"><span data-stu-id="3bd62-125">The payment will temporarily post to a Ledger account until it clears the bank, at which time the payment will move to the bank account you defined here.</span></span>  
12. <span data-ttu-id="3bd62-126">Insira a conta principal usada para lançar o lançamento de transição.</span><span class="sxs-lookup"><span data-stu-id="3bd62-126">Enter the main account used for the bridging posting.</span></span>
    * <span data-ttu-id="3bd62-127">Esta é a conta principal a qual o pagamento será lançado se temporariamente usar a construção de transição.</span><span class="sxs-lookup"><span data-stu-id="3bd62-127">This is the main account to which the payment will temporarily post if using bridging.</span></span>  
13. <span data-ttu-id="3bd62-128">Use a guia do formato de arquivo para definir a configuração de pagamentos eletrônicos.</span><span class="sxs-lookup"><span data-stu-id="3bd62-128">Use the File format tab to define setting for electronic payments.</span></span>
14. <span data-ttu-id="3bd62-129">Use a guia do controle de pagamento para definir os campos que são obrigatórias.</span><span class="sxs-lookup"><span data-stu-id="3bd62-129">Use the Payment control tab to define fields that are mandatory.</span></span>
    * <span data-ttu-id="3bd62-130">Por exemplo, caso você precise de todos os pagamentos com este método de pagamento a serem depositados, você pode escolher essa opção nesta guia.</span><span class="sxs-lookup"><span data-stu-id="3bd62-130">For example, if you require all payments with this method of payment to be deposited, you can choose that option on this tab.</span></span>  
15. <span data-ttu-id="3bd62-131">Use a guia Atributos de pagamento para definir os atributos de pagamento que deseja usar para o método de pagamento.</span><span class="sxs-lookup"><span data-stu-id="3bd62-131">Use the Payment atrributes tab to define which payment attributes you want to use for this method of payment.</span></span>
16. <span data-ttu-id="3bd62-132">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="3bd62-132">Click Save.</span></span>


