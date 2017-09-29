--- 
title: "Registrar uma fatura de fornecedor no diário de faturas"
description: "Este guia de tarefa mostrará como registrar as notas fiscais de fornecedor que não estão associadas às ordens de compra."
author: abruer
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 42f93e6d8fcf62babc3e3244bc1fe76d1efd9d13
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a><span data-ttu-id="8f6c5-103">Registrar uma fatura de fornecedor no diário de faturas</span><span class="sxs-lookup"><span data-stu-id="8f6c5-103">Record a vendor invoice in the invoice journal</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8f6c5-104">Este guia de tarefa mostrará como registrar as notas fiscais de fornecedor que não estão associadas às ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="8f6c5-104">This task guide will show how to record vendor invoices that are not associated with purchase orders.</span></span> <span data-ttu-id="8f6c5-105">Exemplos deste tipo de nota fiscal incluem despesas de fornecimentos ou serviços.</span><span class="sxs-lookup"><span data-stu-id="8f6c5-105">Examples of this type of invoice include expenses for supplies or services.</span></span>  <span data-ttu-id="8f6c5-106">Este registro usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="8f6c5-106">This recording uses the USMF demo company.</span></span>

1. <span data-ttu-id="8f6c5-107">Vá para Contas a pagar > Espaços de trabalho > Entrada de fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="8f6c5-107">Go to Accounts payable > Workspaces > Vendor invoice entry.</span></span>
2. <span data-ttu-id="8f6c5-108">Clique em Novo diário de faturas.</span><span class="sxs-lookup"><span data-stu-id="8f6c5-108">Click New invoice journal.</span></span>
3. <span data-ttu-id="8f6c5-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="8f6c5-109">Click New.</span></span>
4. <span data-ttu-id="8f6c5-110">No campo Nome, insira o nome do diário ou clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8f6c5-110">In the Name field, enter the journal name or click the drop down button to open the lookup.</span></span>
5. <span data-ttu-id="8f6c5-111">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8f6c5-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="8f6c5-112">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="8f6c5-112">Click Lines.</span></span>
    * <span data-ttu-id="8f6c5-113">No campo data, insira a data de lançamento que atualizará a contabilidade.</span><span class="sxs-lookup"><span data-stu-id="8f6c5-113">In the Date field, enter the posting date that will update General Ledger.</span></span>  
7. <span data-ttu-id="8f6c5-114">No campo Conta, especifique a Conta do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="8f6c5-114">In the Account field, specify the Vendor account.</span></span>
8. <span data-ttu-id="8f6c5-115">No campo Fatura, insira o número da fatura.</span><span class="sxs-lookup"><span data-stu-id="8f6c5-115">In the Invoice field, enter the invoice number.</span></span>
9. <span data-ttu-id="8f6c5-116">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8f6c5-116">In the Description field, type a value.</span></span>
10. <span data-ttu-id="8f6c5-117">No campo Crédito, insira um número.</span><span class="sxs-lookup"><span data-stu-id="8f6c5-117">In the Credit field, enter a number.</span></span>
11. <span data-ttu-id="8f6c5-118">No campo Contrapartida, insira o número da conta ou clique no botão suspenso para abrir a pesquisa</span><span class="sxs-lookup"><span data-stu-id="8f6c5-118">In the Offset account field, enter the account number or click the drop down button to open the lookup</span></span>
    * <span data-ttu-id="8f6c5-119">O grupo de imposto será padrão da conta do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="8f6c5-119">The Sales tax group will default from the vendor account.</span></span>  
    * <span data-ttu-id="8f6c5-120">O grupo de imposto será padrão da conta principal especificada no campo Contrapartida.</span><span class="sxs-lookup"><span data-stu-id="8f6c5-120">The Item sales tax group will default from the main account specified in the Offset account field.</span></span>  
    * <span data-ttu-id="8f6c5-121">A data de vencimento será calculada com base nos Termos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="8f6c5-121">The Due date will be calculated based on the Terms of payment.</span></span>  
    * <span data-ttu-id="8f6c5-122">O desconto à vista será padrão da Conta do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="8f6c5-122">The Cash discount will default from the Vendor account.</span></span>  
12. <span data-ttu-id="8f6c5-123">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="8f6c5-123">Click Post.</span></span>
13. <span data-ttu-id="8f6c5-124">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8f6c5-124">Close the page.</span></span>


