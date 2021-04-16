---
title: Registrar e lançar um cheque pré-datado para um fornecedor
description: Você pode registrar os detalhes de um cheque pós-datado antes de emitir o cheque para um fornecedor usando o comprovante de diário.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cb7f9935b20d042551b0ce77fd6bdbf55e9f9669
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834659"
---
# <a name="register-and-post-a-postdated-check-for-a-vendor"></a><span data-ttu-id="f841a-103">Registrar e lançar um cheque pré-datado para um fornecedor</span><span class="sxs-lookup"><span data-stu-id="f841a-103">Register and post a postdated check for a vendor</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f841a-104">Você pode registrar os detalhes de um cheque pós-datado antes de emitir o cheque para um fornecedor usando o comprovante de diário.</span><span class="sxs-lookup"><span data-stu-id="f841a-104">You can register the details of a postdated check before you issue the check to a vendor by using the journal voucher.</span></span> <span data-ttu-id="f841a-105">Você também pode lançar o cheque pré-datado e gerar transações financeiras.</span><span class="sxs-lookup"><span data-stu-id="f841a-105">You can also post the postdated check and generate financial transactions.</span></span> <span data-ttu-id="f841a-106">Antes de registrar e lançar um cheque pré-datado de um fornecedor, conclua a seguinte tarefa:</span><span class="sxs-lookup"><span data-stu-id="f841a-106">Before you register and post a postdated check from a vendor, complete the following task:</span></span> 

<span data-ttu-id="f841a-107">Configurar cheques pós-datado na página Gerenciamento de caixa e banco.</span><span class="sxs-lookup"><span data-stu-id="f841a-107">Set up postdated checks in the Cash and bank management page.</span></span> 



<span data-ttu-id="f841a-108">A função desta guias de tarefas é Tesoureiro.</span><span class="sxs-lookup"><span data-stu-id="f841a-108">The role of this task guides is Treasurer.</span></span> <span data-ttu-id="f841a-109">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="f841a-109">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="f841a-110">Vá para Contas a pagar > Pagamentos > Diário de pagamentos</span><span class="sxs-lookup"><span data-stu-id="f841a-110">Go to Acounts payable > Payments > Payment journal</span></span>
2. <span data-ttu-id="f841a-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f841a-111">Click New.</span></span>
3. <span data-ttu-id="f841a-112">No campo Nome, digite 'VendPay'.</span><span class="sxs-lookup"><span data-stu-id="f841a-112">In the Name field, type 'VendPay'.</span></span>
4. <span data-ttu-id="f841a-113">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="f841a-113">Click Lines.</span></span>
5. <span data-ttu-id="f841a-114">No campo Conta, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="f841a-114">In the Account field, specify the desired values.</span></span>
6. <span data-ttu-id="f841a-115">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f841a-115">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="f841a-116">No campo Débito, insira um número.</span><span class="sxs-lookup"><span data-stu-id="f841a-116">In the Debit field, enter a number.</span></span>
8. <span data-ttu-id="f841a-117">No campo Método de pagamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f841a-117">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="f841a-118">Selecione o método de pagamento para o cheque pré-datado</span><span class="sxs-lookup"><span data-stu-id="f841a-118">Select the method of payment for the postdated check</span></span>  
9. <span data-ttu-id="f841a-119">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="f841a-119">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="f841a-120">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f841a-120">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="f841a-121">Clique na aba Cheques pré-datados.</span><span class="sxs-lookup"><span data-stu-id="f841a-121">Click the Postdated checks tab.</span></span>
12. <span data-ttu-id="f841a-122">No campo Número do cheque, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f841a-122">In the Check number field, type a value.</span></span>
    * <span data-ttu-id="f841a-123">Insira ou modifique o número do cheque pós-datado.</span><span class="sxs-lookup"><span data-stu-id="f841a-123">Enter or modify the number of the postdated check.</span></span>  
13. <span data-ttu-id="f841a-124">No campo Nome do banco emissor, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f841a-124">In the Issuing bank name field, type a value.</span></span>
    * <span data-ttu-id="f841a-125">insira os detalhes do banco para o banco emissor.</span><span class="sxs-lookup"><span data-stu-id="f841a-125">enter the bank details for the issuing bank.</span></span>  
14. <span data-ttu-id="f841a-126">Clique na guia Listar.</span><span class="sxs-lookup"><span data-stu-id="f841a-126">Click the List tab.</span></span>
15. <span data-ttu-id="f841a-127">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="f841a-127">Click Post.</span></span>
16. <span data-ttu-id="f841a-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f841a-128">Close the page.</span></span>
17. <span data-ttu-id="f841a-129">Clique na aba Cheques pré-datados.</span><span class="sxs-lookup"><span data-stu-id="f841a-129">Click the Postdated checks tab.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]