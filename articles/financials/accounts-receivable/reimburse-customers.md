---
title: Reembolsar clientes
description: "Este artigo explica como criar transações de reembolso para um grupo de clientes. Se um cliente tiver um saldo de crédito, é possível reembolsar o cliente para o valor do saldo."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 36e7e684e207e13baffa7eefd13e8e4a29d99914
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---

# <a name="reimburse-customers"></a><span data-ttu-id="30ebd-104">Reembolsar clientes</span><span class="sxs-lookup"><span data-stu-id="30ebd-104">Reimburse customers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="30ebd-105">Este artigo explica como criar transações de reembolso para um grupo de clientes.</span><span class="sxs-lookup"><span data-stu-id="30ebd-105">This article explains how to create reimbursement transactions for a group of customers.</span></span> <span data-ttu-id="30ebd-106">Se um cliente tiver um saldo de crédito, é possível reembolsar o cliente para o valor do saldo.</span><span class="sxs-lookup"><span data-stu-id="30ebd-106">If a customer has a credit balance, you can reimburse the customer for the amount of the balance.</span></span> 

<span data-ttu-id="30ebd-107">A tabela a seguir mostra os pré-requisitos que devem estar funcionando antes de começar.</span><span class="sxs-lookup"><span data-stu-id="30ebd-107">The following table shows the prerequisites that must be in place before you start.</span></span>

| <span data-ttu-id="30ebd-108">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="30ebd-108">Prerequisite</span></span>                                                            | <span data-ttu-id="30ebd-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="30ebd-109">Description</span></span>                                                                                                                                                                                 |
|-------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="30ebd-110">Especificar o valor mínimo de reembolso para a entidade legal.</span><span class="sxs-lookup"><span data-stu-id="30ebd-110">Specify the minimum reimbursement amount for the legal entity.</span></span>          | <span data-ttu-id="30ebd-111">Na página **Parâmetros de contas a receber**, na área **Geral** no campo **Reembolso mínimo**, insira o valor mínimo que pode ser reembolsado para pagamentos do cliente.</span><span class="sxs-lookup"><span data-stu-id="30ebd-111">On the **Accounts receivable parameters** page, in the **General** area, in the **Minimum reimbursement** field, enter the minimum amount that can be reimbursed for customer overpayments.</span></span> |
| <span data-ttu-id="30ebd-112">Opcional: Adicionar uma conta de fornecedor para cada cliente que pode ser reembolsado.</span><span class="sxs-lookup"><span data-stu-id="30ebd-112">Optional: Add a vendor account to each customer that can be reimbursed.</span></span> | <span data-ttu-id="30ebd-113">Na página **Clientes**, na Guia Rápida **Detalhes diversos**, no campo **Conta do fornecedor**, selecione a conta do fornecedor para o cliente.</span><span class="sxs-lookup"><span data-stu-id="30ebd-113">On the **Customers** page, on the **Miscellaneous details** FastTab, in the **Vendor account** field, select the vendor account for the customer.</span></span>                                           |

<span data-ttu-id="30ebd-114">Ao criar transações de reembolso, uma fatura de fornecedor é criada para o valor do saldo de crédito.</span><span class="sxs-lookup"><span data-stu-id="30ebd-114">When you create reimbursement transactions, a vendor invoice is created for the amount of the credit balance.</span></span> <span data-ttu-id="30ebd-115">O processo de reembolso remove o saldo de crédito para a conta de cliente e cria um saldo devedor para a conta do fornecedor que corresponde ao cliente.</span><span class="sxs-lookup"><span data-stu-id="30ebd-115">The reimbursement process removes the credit balance for the customer account and creates a balance due for the vendor account that corresponds to the customer.</span></span>

1.  <span data-ttu-id="30ebd-116">Em Contas a receber, execute o processo **Reembolso**.</span><span class="sxs-lookup"><span data-stu-id="30ebd-116">In Accounts receivable, run the **Reimbursement** process.</span></span>
2.  <span data-ttu-id="30ebd-117">Siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="30ebd-117">Follow one of these steps:</span></span>
    -   <span data-ttu-id="30ebd-118">Para reembolsar contas específicas de clientes, clique em **Selecionar** e especifique as contas do cliente na consulta.</span><span class="sxs-lookup"><span data-stu-id="30ebd-118">To reimburse specific customer accounts, click **Select**, and specify the customer accounts in the query.</span></span>
    -   <span data-ttu-id="30ebd-119">Para reembolsar todas as contas de clientes, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="30ebd-119">To reimburse all customer accounts, click **OK**.</span></span>

    <span data-ttu-id="30ebd-120">Os valores de crédito são transferidos para as contas de fornecedor dos clientes e processados como pagamentos normais.</span><span class="sxs-lookup"><span data-stu-id="30ebd-120">The credit amounts are transferred to the vendor accounts of the customers and are processed as ordinary payments.</span></span> <span data-ttu-id="30ebd-121">Se um cliente não tiver uma conta de fornecedor, uma conta de fornecedor ocasional será criada automaticamente para o cliente.</span><span class="sxs-lookup"><span data-stu-id="30ebd-121">If a customer doesn't have a vendor account, a one-time vendor account is automatically created for the customer.</span></span>
3.  <span data-ttu-id="30ebd-122">Para visualizar as transações do reembolso que foram criados, use a página **Reembolso**.</span><span class="sxs-lookup"><span data-stu-id="30ebd-122">To view the reimbursement transactions that were created, use the **Reimbursement** page.</span></span>
4.  <span data-ttu-id="30ebd-123">Em Contas a pagar, crie um pagamento para as faturas de fornecedor que foram criadas pelo processo de reembolso.</span><span class="sxs-lookup"><span data-stu-id="30ebd-123">In Accounts payable, create a payment for the vendor invoices that were created by the reimbursement process.</span></span>





