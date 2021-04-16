---
title: Depositar pagamentos de cliente
description: Depositar pagamentos de cliente.
author: ShivamPandey-msft
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransCustPaym, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7bf44570a0eaceab94765b100bdd8b4d507a0f54
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822362"
---
# <a name="deposit-customer-payments"></a><span data-ttu-id="9a4e9-103">Depositar pagamentos de cliente</span><span class="sxs-lookup"><span data-stu-id="9a4e9-103">Deposit customer payments</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9a4e9-104">Depositar pagamentos de cliente.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-104">Deposit customer payments.</span></span> <span data-ttu-id="9a4e9-105">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="9a4e9-106">Vá para **Painel de Navegação > Módulos > Contas a receber > Pagamentos > Diário de pagamentos**.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-106">Go to **Navigation pane > Modules > Accounts receivable > Payments > Payment journal**.</span></span>
2. <span data-ttu-id="9a4e9-107">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-107">Select **New**.</span></span>
3. <span data-ttu-id="9a4e9-108">No campo **Nome**, selecione **CustPay** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-108">In the **Name** field, select **CustPay** in the drop-down menu.</span></span>
4. <span data-ttu-id="9a4e9-109">Selecione **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-109">Select **Lines**.</span></span>
5. <span data-ttu-id="9a4e9-110">No campo **Conta**, selecione o cliente para o qual você está registrando o pagamento.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-110">In the **Account** field, select the customer for whom you are recording the payment.</span></span>
6. <span data-ttu-id="9a4e9-111">No campo **Crédito**, insira o valor do pagamento.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-111">In the **Credit** field, enter the amount of the payment.</span></span> <span data-ttu-id="9a4e9-112">Você pode optar por manter o valor em branco, e fazer com que o sistema o calcule selecionando as faturas que foram pagas.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-112">You can choose to leave the amount blank, and have the system calculate it by selecting the invoices which were paid.</span></span>  
7. <span data-ttu-id="9a4e9-113">No campo **Referência de pagamento**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-113">In the **Payment reference** field, type a value.</span></span> <span data-ttu-id="9a4e9-114">A referência de pagamento pode ser o número do cheque para pagamento que você está inserindo.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-114">The payment reference could be the check number for the payment you are entering.</span></span> <span data-ttu-id="9a4e9-115">A referência do pagamento é necessária para incluir o pagamento em um comprovante de pagamento.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-115">The payment reference is required in order to include the payment on a deposit slip.</span></span>  
8. <span data-ttu-id="9a4e9-116">Marque a caixa Usar uma guia de depósito.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-116">Mark the box Use a deposit slip.</span></span> <span data-ttu-id="9a4e9-117">Se o pagamento for incluído no depósito, altere essa configuração para Sim.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-117">If the payment should be included in the deposit, change this setting to Yes.</span></span>  
9. <span data-ttu-id="9a4e9-118">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-118">Select **New**.</span></span>
10. <span data-ttu-id="9a4e9-119">No campo **Conta**, selecione o cliente para o próximo pagamento.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-119">In the **Account** field, select the customer for the next payment.</span></span>
11. <span data-ttu-id="9a4e9-120">No campo **Crédito**, insira o valor do pagamento.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-120">In the **Credit** field, enter the payment amount.</span></span>
12. <span data-ttu-id="9a4e9-121">No campo **Referência de pagamento**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-121">In the **Payment reference** field, type a value.</span></span>
13. <span data-ttu-id="9a4e9-122">Marque a caixa **Usar uma guia de depósito**.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-122">Mark the box **Use a deposit slip**.</span></span>
14. <span data-ttu-id="9a4e9-123">Selecione **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-123">Select **Post**.</span></span> <span data-ttu-id="9a4e9-124">Os pagamentos devem ser lançados antes que a guia de depósito possa ser gerada.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-124">Payments must be posted before the deposit slip can be generated.</span></span> <span data-ttu-id="9a4e9-125">Isso garante que os pagamentos não se alterem depois que a guia de depósito for gerada.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-125">This is to ensure that the payments don't change after the deposit slip is generated.</span></span>  
15. <span data-ttu-id="9a4e9-126">Selecione **Funções**.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-126">Select **Functions**.</span></span>
16. <span data-ttu-id="9a4e9-127">Selecione **Guia de depósito**.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-127">Select **Deposit slip**.</span></span>
17. <span data-ttu-id="9a4e9-128">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-128">Select **OK**.</span></span> <span data-ttu-id="9a4e9-129">A primeira página é usada para criar a guia de depósito.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-129">The first page is used to create the deposit slip.</span></span>  
18. <span data-ttu-id="9a4e9-130">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-130">Select **OK**.</span></span> <span data-ttu-id="9a4e9-131">A segunda etapa é imprimir a guia de depósito, mas essa etapa não é necessária.</span><span class="sxs-lookup"><span data-stu-id="9a4e9-131">The second step is to print the deposit slip, but this step is not required.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]