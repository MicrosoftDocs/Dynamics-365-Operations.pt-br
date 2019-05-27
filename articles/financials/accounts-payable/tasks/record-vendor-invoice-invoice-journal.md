---
title: Registrar uma fatura de fornecedor no diário de faturas
description: Este guia de tarefa mostrará como registrar as notas fiscais de fornecedor que não estão associadas às ordens de compra.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 775f3764d34cecbfc071ff7420d32c7832b42308
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556316"
---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a><span data-ttu-id="422b1-103">Registrar uma fatura de fornecedor no diário de faturas</span><span class="sxs-lookup"><span data-stu-id="422b1-103">Record a vendor invoice in the invoice journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="422b1-104">Este guia de tarefa mostrará como registrar as notas fiscais de fornecedor que não estão associadas às ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="422b1-104">This task guide will show how to record vendor invoices that are not associated with purchase orders.</span></span> <span data-ttu-id="422b1-105">Exemplos deste tipo de nota fiscal incluem despesas de fornecimentos ou serviços.</span><span class="sxs-lookup"><span data-stu-id="422b1-105">Examples of this type of invoice include expenses for supplies or services.</span></span>  <span data-ttu-id="422b1-106">Este registro usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="422b1-106">This recording uses the USMF demo company.</span></span>

1. <span data-ttu-id="422b1-107">Vá para Contas a pagar > Espaços de trabalho > Entrada de fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="422b1-107">Go to Accounts payable > Workspaces > Vendor invoice entry.</span></span>
2. <span data-ttu-id="422b1-108">Clique em Novo diário de faturas.</span><span class="sxs-lookup"><span data-stu-id="422b1-108">Click New invoice journal.</span></span>
3. <span data-ttu-id="422b1-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="422b1-109">Click New.</span></span>
4. <span data-ttu-id="422b1-110">No campo Nome, insira o nome do diário ou clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="422b1-110">In the Name field, enter the journal name or click the drop down button to open the lookup.</span></span>
5. <span data-ttu-id="422b1-111">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="422b1-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="422b1-112">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="422b1-112">Click Lines.</span></span>
    * <span data-ttu-id="422b1-113">No campo data, insira a data de lançamento que atualizará a contabilidade.</span><span class="sxs-lookup"><span data-stu-id="422b1-113">In the Date field, enter the posting date that will update General Ledger.</span></span>  
7. <span data-ttu-id="422b1-114">No campo Conta, especifique a Conta do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="422b1-114">In the Account field, specify the Vendor account.</span></span>
8. <span data-ttu-id="422b1-115">No campo Fatura, insira o número da fatura.</span><span class="sxs-lookup"><span data-stu-id="422b1-115">In the Invoice field, enter the invoice number.</span></span>
9. <span data-ttu-id="422b1-116">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="422b1-116">In the Description field, type a value.</span></span>
10. <span data-ttu-id="422b1-117">No campo Crédito, insira um número.</span><span class="sxs-lookup"><span data-stu-id="422b1-117">In the Credit field, enter a number.</span></span>
11. <span data-ttu-id="422b1-118">No campo Contrapartida, insira o número da conta ou clique no botão suspenso para abrir a pesquisa</span><span class="sxs-lookup"><span data-stu-id="422b1-118">In the Offset account field, enter the account number or click the drop down button to open the lookup</span></span>
    * <span data-ttu-id="422b1-119">O grupo de imposto será padrão da conta do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="422b1-119">The Sales tax group will default from the vendor account.</span></span>  
    * <span data-ttu-id="422b1-120">O grupo de imposto será padrão da conta principal especificada no campo Contrapartida.</span><span class="sxs-lookup"><span data-stu-id="422b1-120">The Item sales tax group will default from the main account specified in the Offset account field.</span></span>  
    * <span data-ttu-id="422b1-121">A data de vencimento será calculada com base nos Termos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="422b1-121">The Due date will be calculated based on the Terms of payment.</span></span>  
    * <span data-ttu-id="422b1-122">O desconto à vista será padrão da Conta do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="422b1-122">The Cash discount will default from the Vendor account.</span></span>  
12. <span data-ttu-id="422b1-123">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="422b1-123">Click Post.</span></span>
13. <span data-ttu-id="422b1-124">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="422b1-124">Close the page.</span></span>

