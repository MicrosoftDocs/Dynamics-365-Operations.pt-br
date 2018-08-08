--- 
title: "Configurar cheques pré-datados"
description: "Este tópico explica como especificar se deseja lançar entradas de diário para cheques pré-datados e quais diários de lançamento a serem usados para limpar as entradas e os pagamentos de fornecedores."
author: kweekley
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 5b1988ee50dae686ae860305cd785deacae94a72
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---
# <a name="set-up-postdated-checks"></a><span data-ttu-id="397f5-103">Configurar cheques pré-datados</span><span class="sxs-lookup"><span data-stu-id="397f5-103">Set up postdated checks</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="397f5-104">Este tópico explica como especificar se deseja lançar entradas de diário para cheques pré-datados e quais diários de lançamento a serem usados para limpar as entradas e os pagamentos de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="397f5-104">This topic explains how to specify whether to post journal entries for postdated checks and which posting journals to use for clearing entries and vendor payments.</span></span> <span data-ttu-id="397f5-105">Também é possível especificar as contas de compensação para cheques emitidos, cheques recebidos, e a retenção de imposto.</span><span class="sxs-lookup"><span data-stu-id="397f5-105">You can also specify clearing accounts for issued checks, received checks, and withholding tax.</span></span> <span data-ttu-id="397f5-106">Cheques pré-datados que são emitidos com a finalidade de realizar e receber pagamentos em uma data futura.</span><span class="sxs-lookup"><span data-stu-id="397f5-106">Postdated checks that are issued to make and receive payments on a future date.</span></span> <span data-ttu-id="397f5-107">É possível especificar se o cheque deve ser refletido nos registros de contabilidade antes da data de vencimento.</span><span class="sxs-lookup"><span data-stu-id="397f5-107">You can specify whether the check must be reflected in the accounting books before its maturity date.</span></span>



<span data-ttu-id="397f5-108">A função deste procedimento é Tesoureiro.</span><span class="sxs-lookup"><span data-stu-id="397f5-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="397f5-109">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="397f5-109">This procedure uses the USMF demo company.</span></span>


## <a name="set-up-postdated-checks"></a><span data-ttu-id="397f5-110">Configurar cheques pré-datados</span><span class="sxs-lookup"><span data-stu-id="397f5-110">Set up postdated checks</span></span>
1. <span data-ttu-id="397f5-111">Vá para Gerenciamento de dinheiro e banco > Configuração > Parâmetros do gerenciamento de dinheiro e banco.</span><span class="sxs-lookup"><span data-stu-id="397f5-111">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="397f5-112">Clique na aba Cheques pré-datados.</span><span class="sxs-lookup"><span data-stu-id="397f5-112">Click the Postdated checks tab.</span></span>
3. <span data-ttu-id="397f5-113">Marque ou desmarque a caixa de seleção Habilitar cheques pré-datados.</span><span class="sxs-lookup"><span data-stu-id="397f5-113">Select or clear the Enable postdated checks check box.</span></span>
4. <span data-ttu-id="397f5-114">Marque ou desmarque a caixa de seleção Lançar entradas de diário para cheques pré-datados.</span><span class="sxs-lookup"><span data-stu-id="397f5-114">Select or clear the Post journal entries for postdated checks check box.</span></span>
5. <span data-ttu-id="397f5-115">No campo Conta de compensação para cheques emitidos, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="397f5-115">In the Clearing account for issued checks field, specify the desired values.</span></span>
6. <span data-ttu-id="397f5-116">No campo Conta de compensação para cheques recebidos, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="397f5-116">In the Clearing account for received checks field, specify the desired values.</span></span>
7. <span data-ttu-id="397f5-117">No campo Diário geral para entradas de compensação, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="397f5-117">In the General journal for clearing entries field, type a value.</span></span>
8. <span data-ttu-id="397f5-118">No campo Transferir cheques pré-datados para este diário de pagamento de fornecedor, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="397f5-118">In the Transfer postdated checks to this vendor payment journal field, type a value.</span></span>
9. <span data-ttu-id="397f5-119">No campo Conta de compensação de imposto retido na fonte, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="397f5-119">In the Withholding tax clearing account field, specify the desired values.</span></span>
10. <span data-ttu-id="397f5-120">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="397f5-120">Click Save.</span></span>
11. <span data-ttu-id="397f5-121">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="397f5-121">Close the page.</span></span>
12. <span data-ttu-id="397f5-122">Vá para Contas a pagar > Configurar pagamento > Métodos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="397f5-122">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
13. <span data-ttu-id="397f5-123">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="397f5-123">Click New.</span></span>
14. <span data-ttu-id="397f5-124">No campo Método de pagamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="397f5-124">In the Method of payment field, type a value.</span></span>
15. <span data-ttu-id="397f5-125">Selecione a opção de lançamento Compensação de cheque pré-datado para indicar que o valor do cheque está lançado em uma conta de compensação.</span><span class="sxs-lookup"><span data-stu-id="397f5-125">Select the Postdated check clearing posting option to indicate that the check amount is posted to a clearing account.</span></span>
16. <span data-ttu-id="397f5-126">No campo Tipo de conta, selecione 'Banco'.</span><span class="sxs-lookup"><span data-stu-id="397f5-126">In the Account type field, select 'Bank'.</span></span>
    * <span data-ttu-id="397f5-127">A conta de contrapartida do método de pagamento será um banco.</span><span class="sxs-lookup"><span data-stu-id="397f5-127">The offset account of the payment method will be a bank.</span></span>  
17. <span data-ttu-id="397f5-128">No campo Conta de pagamento, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="397f5-128">In the Payment account field, specify the desired values.</span></span>
    * <span data-ttu-id="397f5-129">Selecione a conta bancária utilizada para deduzir o valor da fatura.</span><span class="sxs-lookup"><span data-stu-id="397f5-129">Select the bank account that is used to deduct the invoice amount.</span></span>  
18. <span data-ttu-id="397f5-130">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="397f5-130">Close the page.</span></span>
19. <span data-ttu-id="397f5-131">Vá para Contas a receber > Configurar pagamentos > Métodos de pagamento</span><span class="sxs-lookup"><span data-stu-id="397f5-131">Go to Accounts receivable > Payment setup > Methods of payment</span></span>
20. <span data-ttu-id="397f5-132">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="397f5-132">Click New.</span></span>
21. <span data-ttu-id="397f5-133">No campo Método de pagamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="397f5-133">In the Method of payment field, type a value.</span></span>
22. <span data-ttu-id="397f5-134">Selecione a opção de lançamento Compensação de cheque pré-datado para indicar que o valor do cheque está lançado em uma conta de compensação.</span><span class="sxs-lookup"><span data-stu-id="397f5-134">Select the Postdated check clearing posting option to indicate that the check amount is posted to a clearing account.</span></span>
23. <span data-ttu-id="397f5-135">No campo Tipo de conta, selecione 'Banco'.</span><span class="sxs-lookup"><span data-stu-id="397f5-135">In the Account type field, select 'Bank'.</span></span>
    * <span data-ttu-id="397f5-136">A conta de contrapartida do método de pagamento será um banco.</span><span class="sxs-lookup"><span data-stu-id="397f5-136">The offset account of the payment method will be a bank.</span></span>  
24. <span data-ttu-id="397f5-137">No campo Conta de pagamento, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="397f5-137">In the Payment account field, specify the desired values.</span></span>
    * <span data-ttu-id="397f5-138">Selecione a conta bancária utilizada para deduzir o valor da fatura.</span><span class="sxs-lookup"><span data-stu-id="397f5-138">Select the bank account that is used to deduct the invoice amount.</span></span>  
25. <span data-ttu-id="397f5-139">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="397f5-139">Close the page.</span></span>


