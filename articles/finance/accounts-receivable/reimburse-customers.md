---
title: Reembolsar clientes
description: Este artigo explica como criar transações de reembolso para um grupo de clientes. Se um cliente tiver um saldo de crédito, é possível reembolsar o cliente para o valor do saldo.
author: JodiChristiansen
manager: AnnBe
ms.date: 09/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 65ee884fb22c1a38e2d3022085fed7e3e6077d1f
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644528"
---
# <a name="reimburse-customers"></a><span data-ttu-id="6af78-104">Reembolsar clientes</span><span class="sxs-lookup"><span data-stu-id="6af78-104">Reimburse customers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6af78-105">Este artigo explica como criar transações de reembolso para um grupo de clientes.</span><span class="sxs-lookup"><span data-stu-id="6af78-105">This article explains how to create reimbursement transactions for a group of customers.</span></span> <span data-ttu-id="6af78-106">Se um cliente tiver um saldo de crédito, é possível reembolsar o cliente para o valor do saldo.</span><span class="sxs-lookup"><span data-stu-id="6af78-106">If a customer has a credit balance, you can reimburse the customer for the amount of the balance.</span></span> 

<span data-ttu-id="6af78-107">A tabela a seguir mostra os pré-requisitos que devem estar funcionando antes de começar.</span><span class="sxs-lookup"><span data-stu-id="6af78-107">The following table shows the prerequisites that must be in place before you start.</span></span>

| <span data-ttu-id="6af78-108">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="6af78-108">Prerequisite</span></span>                                                            | <span data-ttu-id="6af78-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="6af78-109">Description</span></span> |
|-------------------------------------------------------------------------|-------------|
| <span data-ttu-id="6af78-110">Especificar o valor mínimo de reembolso para a entidade legal.</span><span class="sxs-lookup"><span data-stu-id="6af78-110">Specify the minimum reimbursement amount for the legal entity.</span></span>          | <span data-ttu-id="6af78-111">Na página **Parâmetros de contas a receber**, na área **Geral** no campo **Reembolso mínimo**, insira o valor mínimo que pode ser reembolsado para pagamentos do cliente.</span><span class="sxs-lookup"><span data-stu-id="6af78-111">On the **Accounts receivable parameters** page, in the **General** area, in the **Minimum reimbursement** field, enter the minimum amount that can be reimbursed for customer overpayments.</span></span> |
| <span data-ttu-id="6af78-112">Opcional: Adicionar uma conta de fornecedor para cada cliente que pode ser reembolsado.</span><span class="sxs-lookup"><span data-stu-id="6af78-112">Optional: Add a vendor account to each customer that can be reimbursed.</span></span> | <span data-ttu-id="6af78-113">Na página **Clientes**, na Guia Rápida **Detalhes diversos**, no campo **Conta do fornecedor**, selecione a conta do fornecedor para o cliente.</span><span class="sxs-lookup"><span data-stu-id="6af78-113">On the **Customers** page, on the **Miscellaneous details** FastTab, in the **Vendor account** field, select the vendor account for the customer.</span></span> |

<span data-ttu-id="6af78-114">Ao criar transações de reembolso, uma fatura de fornecedor é criada para o valor do saldo de crédito.</span><span class="sxs-lookup"><span data-stu-id="6af78-114">When you create reimbursement transactions, a vendor invoice is created for the amount of the credit balance.</span></span> <span data-ttu-id="6af78-115">O processo de reembolso remove o saldo de crédito para a conta de cliente e cria um saldo devedor para a conta do fornecedor que corresponde ao cliente.</span><span class="sxs-lookup"><span data-stu-id="6af78-115">The reimbursement process removes the credit balance for the customer account and creates a balance due for the vendor account that corresponds to the customer.</span></span>

1. <span data-ttu-id="6af78-116">Em Contas a receber, execute o processo de **Reembolso** (**Contas a receber \> Tarefas periódicas \> Reembolso**).</span><span class="sxs-lookup"><span data-stu-id="6af78-116">In Accounts receivable, run the **Reimbursement** process (**Accounts receivable \> Periodic tasks \> Reimbursement**).</span></span>
2. <span data-ttu-id="6af78-117">Para agrupar todas as transações, independentemente das dimensões do razão, defina a opção **Resumir cliente** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="6af78-117">To group all transactions, regardless of ledger dimensions, set the **Summarize customer** option to **Yes**.</span></span> <span data-ttu-id="6af78-118">Para agrupar somente transações que tenham dimensões contábeis semelhantes, defina a opção como **Não**.</span><span class="sxs-lookup"><span data-stu-id="6af78-118">To group only transactions that have similar ledger dimensions, set the option to **No**.</span></span>
3. <span data-ttu-id="6af78-119">Selecione **Incluir clientes com transações de débito pendentes** para selecionar clientes que tenham valores de débito não liquidados.</span><span class="sxs-lookup"><span data-stu-id="6af78-119">Select **Include customers with outstanding debit transactions** to select customers who have unsettled debit amounts.</span></span>
4. <span data-ttu-id="6af78-120">Para reembolsar contas de cliente específicas, na Guia Rápida **Registros a incluir**, selecione **Filtrar** e especifique as contas de cliente na consulta.</span><span class="sxs-lookup"><span data-stu-id="6af78-120">To reimburse specific customer accounts, on the **Records to include** FastTab, select **Filter**, and then specify the customer accounts in the query.</span></span>

    <span data-ttu-id="6af78-121">Os valores de crédito são transferidos para as contas de fornecedor dos clientes e processados como pagamentos normais.</span><span class="sxs-lookup"><span data-stu-id="6af78-121">The credit amounts are transferred to the vendor accounts of the customers and are processed as ordinary payments.</span></span> <span data-ttu-id="6af78-122">Se um cliente não tiver uma conta de fornecedor, uma conta de fornecedor ocasional será criada automaticamente para o cliente.</span><span class="sxs-lookup"><span data-stu-id="6af78-122">If a customer doesn't have a vendor account, a one-time vendor account is automatically created for the customer.</span></span>

5. <span data-ttu-id="6af78-123">Para exibir as transações de reembolso criadas, use o relatório **Reembolso** (**Contas a Receber \> Consultas e relatórios \> relatório Reembolso**).</span><span class="sxs-lookup"><span data-stu-id="6af78-123">To view the reimbursement transactions that were created, use the **Reimbursement** report (**Accounts Receivable \> Inquiries and reports \> Reimbursement report**).</span></span>
6. <span data-ttu-id="6af78-124">Em Contas a pagar, crie um pagamento para as faturas de fornecedor que foram criadas pelo processo de reembolso.</span><span class="sxs-lookup"><span data-stu-id="6af78-124">In Accounts payable, create a payment for the vendor invoices that were created by the reimbursement process.</span></span> <span data-ttu-id="6af78-125">Para obter informações sobre como pagar fornecedores, consulte [Visão geral de pagamentos do fornecedor](../accounts-payable/Vendor-payments-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="6af78-125">For information about how to pay vendors, see [Vendor payment overview](../accounts-payable/Vendor-payments-workspace.md).</span></span>
