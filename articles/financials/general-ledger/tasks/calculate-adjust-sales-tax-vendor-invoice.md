---
title: Calcular e ajustar imposto na fatura do fornecedor
description: Se o documento de origem exibir valores de imposto diferentes como calculados, você pode ajustar os valores antes do lançamento.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendInvoice, VendTableLookup, TaxTmpWorkTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 803c038d907b68a3c72a83a3e035c4e08b8a8661
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "308911"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a><span data-ttu-id="9c268-103">Calcular e ajustar imposto na fatura do fornecedor</span><span class="sxs-lookup"><span data-stu-id="9c268-103">Calculate and adjust sales tax on a vendor invoice</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9c268-104">Se o documento de origem exibir valores de imposto diferentes como calculados, você pode ajustar os valores antes do lançamento.</span><span class="sxs-lookup"><span data-stu-id="9c268-104">If the original source document displays different tax amounts as calculated, you can adjust those amounts before posting.</span></span> <span data-ttu-id="9c268-105">Esta tarefa usa a empresa de demonstração DEMF.</span><span class="sxs-lookup"><span data-stu-id="9c268-105">This task uses the DEMF demo company.</span></span>

1. <span data-ttu-id="9c268-106">Vá para Contas a pagar > Faturas > Diário de fatura.</span><span class="sxs-lookup"><span data-stu-id="9c268-106">Go to Accounts payable > Invoices > Invoice journal.</span></span>
2. <span data-ttu-id="9c268-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="9c268-107">Click New.</span></span>
3. <span data-ttu-id="9c268-108">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="9c268-108">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="9c268-109">No campo Nome, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="9c268-109">In the Name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="9c268-110">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="9c268-110">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="9c268-111">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="9c268-111">Click Lines.</span></span>
7. <span data-ttu-id="9c268-112">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="9c268-112">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="9c268-113">No campo Conta, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="9c268-113">In the Account field, specify the desired values.</span></span>
9. <span data-ttu-id="9c268-114">No campo Fatura, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9c268-114">In the Invoice field, type a value.</span></span>
10. <span data-ttu-id="9c268-115">No campo Crédito, insira um número.</span><span class="sxs-lookup"><span data-stu-id="9c268-115">In the Credit field, enter a number.</span></span>
11. <span data-ttu-id="9c268-116">No campo Contrapartida, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="9c268-116">In the Offset account field, specify the desired values.</span></span>
12. <span data-ttu-id="9c268-117">Clique em Impostos.</span><span class="sxs-lookup"><span data-stu-id="9c268-117">Click Sales tax.</span></span>
13. <span data-ttu-id="9c268-118">No campo Valor total do imposto real, insira um número.</span><span class="sxs-lookup"><span data-stu-id="9c268-118">In the Total actual sales tax amount field, enter a number.</span></span>
14. <span data-ttu-id="9c268-119">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="9c268-119">Click OK.</span></span>
15. <span data-ttu-id="9c268-120">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="9c268-120">Click Save.</span></span>
16. <span data-ttu-id="9c268-121">Clique em Impostos.</span><span class="sxs-lookup"><span data-stu-id="9c268-121">Click Sales tax.</span></span>
17. <span data-ttu-id="9c268-122">Na guia, os valores de ajuste de impostos sobre vendas podem ser ajustados por código de imposto sobre vendas.</span><span class="sxs-lookup"><span data-stu-id="9c268-122">On the Adjustment tab, the sales tax amounts can be adjusted per sales tax code.</span></span>
18. <span data-ttu-id="9c268-123">Clique em Redefinir valor real a partir de valores calculados.</span><span class="sxs-lookup"><span data-stu-id="9c268-123">Click Reset actual from calculated amounts.</span></span>
19. <span data-ttu-id="9c268-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="9c268-124">Click OK.</span></span>
20. <span data-ttu-id="9c268-125">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="9c268-125">Click Save.</span></span>

