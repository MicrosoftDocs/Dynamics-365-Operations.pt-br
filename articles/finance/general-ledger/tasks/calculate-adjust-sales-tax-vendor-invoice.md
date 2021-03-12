---
title: Calcular e ajustar imposto na fatura de fornecedor
description: Este tópico explica como ajustar impostos em uma fatura de fornecedor no Dynamics 365 Finance.
author: twheeloc
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendInvoice, VendTableLookup, TaxTmpWorkTrans
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2536e87953267eae13cf3b42c2bd5476fc647c22
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994706"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a><span data-ttu-id="b0c77-103">Calcular e ajustar imposto na fatura de fornecedor</span><span class="sxs-lookup"><span data-stu-id="b0c77-103">Calculate and adjust sales tax on a vendor invoice</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b0c77-104">Este tópico explica como ajustar impostos em uma fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="b0c77-104">This topic explains how to adjust sales tax on a vendor invoice.</span></span> <span data-ttu-id="b0c77-105">Se o documento de origem exibir valores de imposto diferentes como calculados, você pode ajustar os valores antes do lançamento.</span><span class="sxs-lookup"><span data-stu-id="b0c77-105">If the original source document displays different tax amounts as calculated, you can adjust those amounts before posting.</span></span> <span data-ttu-id="b0c77-106">Esta tarefa usa a empresa de demonstração DEMF.</span><span class="sxs-lookup"><span data-stu-id="b0c77-106">This task uses the DEMF demo company.</span></span>

1. <span data-ttu-id="b0c77-107">No painel de navegação, vá para **Módulos > Contas a pagar > Faturas > Diário de faturas**.</span><span class="sxs-lookup"><span data-stu-id="b0c77-107">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice journal**.</span></span>
2. <span data-ttu-id="b0c77-108">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="b0c77-108">Select **New**.</span></span>
3. <span data-ttu-id="b0c77-109">No campo **Nome** da nova linha, selecione uma opção no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="b0c77-109">In the **Name** field of the new row, select an option in the drop-down menu.</span></span>
4. <span data-ttu-id="b0c77-110">No Painel de Ações, selecione **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="b0c77-110">In the Action Pane, select **Lines**.</span></span>
5. <span data-ttu-id="b0c77-111">No campo **Conta**, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="b0c77-111">In the **Account** field, specify the desired values.</span></span>
6. <span data-ttu-id="b0c77-112">No campo **Fatura**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b0c77-112">In the **Invoice** field, type a value.</span></span>
7. <span data-ttu-id="b0c77-113">No campo **Crédito**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b0c77-113">In the **Credit** field, enter a number.</span></span>
8. <span data-ttu-id="b0c77-114">No campo **Contrapartida**, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="b0c77-114">In the **Offset account** field, specify the desired values.</span></span>
9. <span data-ttu-id="b0c77-115">Selecione **Imposto**.</span><span class="sxs-lookup"><span data-stu-id="b0c77-115">Select **Sales tax**.</span></span>
10. <span data-ttu-id="b0c77-116">No campo **Valor total do imposto real**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b0c77-116">In the **Total actual sales tax amount** field, enter a number.</span></span>
11. <span data-ttu-id="b0c77-117">Na guia **Ajuste**, os valores de impostos podem ser ajustados por código de imposto.</span><span class="sxs-lookup"><span data-stu-id="b0c77-117">On the **Adjustment** tab, the sales tax amounts can be adjusted per sales tax code.</span></span>
12. <span data-ttu-id="b0c77-118">Selecione **Redefinir valor real a partir de valores calculados**.</span><span class="sxs-lookup"><span data-stu-id="b0c77-118">Select **Reset actual from calculated amounts**.</span></span>
13. <span data-ttu-id="b0c77-119">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0c77-119">Select **OK**.</span></span>
14. <span data-ttu-id="b0c77-120">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b0c77-120">Select **Save**.</span></span>

