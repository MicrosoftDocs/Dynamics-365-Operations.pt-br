---
title: Registrar uma fatura de fornecedor no diário de faturas
description: Este guia de tarefa mostrará como registrar as notas fiscais de fornecedor que não estão associadas às ordens de compra.
author: abruer
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5277081d9f7adcc43c30d30208d13c7e39d76118
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140366"
---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a><span data-ttu-id="fd3d9-103">Registrar uma fatura de fornecedor no diário de faturas</span><span class="sxs-lookup"><span data-stu-id="fd3d9-103">Record a vendor invoice in the invoice journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fd3d9-104">Este guia de tarefa mostrará como registrar as notas fiscais de fornecedor que não estão associadas às ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="fd3d9-104">This task guide will show how to record vendor invoices that are not associated with purchase orders.</span></span> <span data-ttu-id="fd3d9-105">Exemplos deste tipo de nota fiscal incluem despesas de fornecimentos ou serviços.</span><span class="sxs-lookup"><span data-stu-id="fd3d9-105">Examples of this type of invoice include expenses for supplies or services.</span></span>  <span data-ttu-id="fd3d9-106">Este registro usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="fd3d9-106">This recording uses the USMF demo company.</span></span>

1. <span data-ttu-id="fd3d9-107">Vá para **Painel de navegação > Módulos > Contas a pagar > Espaços de trabalho > Entrada de fatura de fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="fd3d9-107">Go to **Navigation pane > Modules > Accounts payable > Workspaces > Vendor invoice entry**.</span></span>
2. <span data-ttu-id="fd3d9-108">No **Painel de ação**, clique em **Diário de nova fatura**.</span><span class="sxs-lookup"><span data-stu-id="fd3d9-108">On the **Action pane**, click **New invoice journal**.</span></span>
3. <span data-ttu-id="fd3d9-109">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="fd3d9-109">Click **New**.</span></span>
4. <span data-ttu-id="fd3d9-110">No campo **Nome**, insira o nome do diário ou clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fd3d9-110">In the **Name** field, enter the journal name or click the drop down button to open the lookup.</span></span>
5. <span data-ttu-id="fd3d9-111">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="fd3d9-111">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="fd3d9-112">No **Painel de ação**, clique em **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="fd3d9-112">On the **Action pane**, click **Lines**.</span></span> <span data-ttu-id="fd3d9-113">No campo **Data**, insira a data de lançamento que atualizará a Contabilidade.</span><span class="sxs-lookup"><span data-stu-id="fd3d9-113">In the **Date** field, enter the posting date that will update General Ledger.</span></span>  
7. <span data-ttu-id="fd3d9-114">No campo **Conta**, especifique a **Conta do fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="fd3d9-114">In the **Account** field, specify the **Vendor account**.</span></span>
8. <span data-ttu-id="fd3d9-115">No campo **Fatura**, insira o número da fatura.</span><span class="sxs-lookup"><span data-stu-id="fd3d9-115">In the **Invoice** field, enter the invoice number.</span></span>
9. <span data-ttu-id="fd3d9-116">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="fd3d9-116">In the **Description** field, type a value.</span></span>
10. <span data-ttu-id="fd3d9-117">No campo **Crédito**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="fd3d9-117">In the **Credit** field, enter a number.</span></span>
11. <span data-ttu-id="fd3d9-118">No campo **Contrapartida**, insira o número da conta ou clique no botão suspenso para abrir a pesquisa</span><span class="sxs-lookup"><span data-stu-id="fd3d9-118">In the **Offset account** field, enter the account number or click the drop down button to open the lookup</span></span>
    * <span data-ttu-id="fd3d9-119">O **Grupo de impostos** terá o padrão retirado da conta do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="fd3d9-119">The **Sales tax group** will be default from the vendor account.</span></span>  
    * <span data-ttu-id="fd3d9-120">O **Grupo de impostos do item** terá o padrão retirado da conta principal especificada no campo **Contrapartida**.</span><span class="sxs-lookup"><span data-stu-id="fd3d9-120">The **Item sales tax group** will be default from the main account specified in the **Offset account** field.</span></span>  
    * <span data-ttu-id="fd3d9-121">A **Data de vencimento** será calculada com base nos Termos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="fd3d9-121">The **Due date** will be calculated based on the Terms of payment.</span></span>  
    * <span data-ttu-id="fd3d9-122">O **Desconto à vista** terá o padrão retirado da Conta do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="fd3d9-122">The **Cash discount** will default from the Vendor account.</span></span>  
12. <span data-ttu-id="fd3d9-123">Clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="fd3d9-123">Click **Post**.</span></span>
13. <span data-ttu-id="fd3d9-124">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="fd3d9-124">Close the page.</span></span>

