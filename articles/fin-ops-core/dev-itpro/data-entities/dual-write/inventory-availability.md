---
title: Disponibilidade de estoque em gravação dupla
description: Este tópico fornece informações sobre como verificar a disponibilidade de estoque em gravação dupla.
author: yijialuan
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: 4d1022eec633bf0a9edb4d5b26982853cec836d7
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997883"
---
# <a name="inventory-availability-in-dual-write"></a><span data-ttu-id="dc83a-103">Disponibilidade de estoque em gravação dupla</span><span class="sxs-lookup"><span data-stu-id="dc83a-103">Inventory availability in dual-write</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dc83a-104">Usando a disponibilidade de estoque, você pode verificar seu estoque antes de adicionar um produto à página **Cotações** , **Ordens** ou **Faturas** no Microsoft Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="dc83a-104">By using inventory availability, you can check your inventory before you add a product to the **Quotations** , **Orders** , or **Invoices** page in Microsoft Dynamics 365 Sales.</span></span> <span data-ttu-id="dc83a-105">Por exemplo, você verifica o estoque e determina uma data de atendimento como uma tarefa fundamental no processo de [pagamento à vista](dual-write-prospect-to-cash.md).</span><span class="sxs-lookup"><span data-stu-id="dc83a-105">For example, you check inventory and determine a fulfillment date as one key task in the [prospect-to-cash](dual-write-prospect-to-cash.md) process.</span></span>

<span data-ttu-id="dc83a-106">Se não tiver estoque suficiente, você poderá estimar uma data de entrega com base em recebimentos e saídas de estoque projetado.</span><span class="sxs-lookup"><span data-stu-id="dc83a-106">If you don't have enough inventory, you can estimate a delivery date, based on projected inventory receipts and issues.</span></span> <span data-ttu-id="dc83a-107">Você também pode verificar as informações de disponível para promessa (ATP), em que é possível encontrar a quantidade ATP no limite de tempo predefinido.</span><span class="sxs-lookup"><span data-stu-id="dc83a-107">You can also check the product's available-to-promise (ATP) information, where you can find the ATP quantity in the predefined time fence.</span></span>

## <a name="on-hand-inventory"></a><span data-ttu-id="dc83a-108">Estoque Disponível</span><span class="sxs-lookup"><span data-stu-id="dc83a-108">On-hand inventory</span></span>

<span data-ttu-id="dc83a-109">No Dynamics 365 Sales, um novo botão **Estoque disponível** foi adicionado ao cabeçalho das páginas **Cotações** , **Ordens** e **Faturas**.</span><span class="sxs-lookup"><span data-stu-id="dc83a-109">In Dynamics 365 Sales, a new **On-hand Inventory** button has been added to the header of the **Quotes** , **Orders** , and **Invoices** pages.</span></span> <span data-ttu-id="dc83a-110">Quando você seleciona esse botão, uma caixa de diálogo é exibida e você pode especificar a empresa e o produto para o qual deseja verificar o estoque disponível.</span><span class="sxs-lookup"><span data-stu-id="dc83a-110">When you select this button, a dialog box appears, where you can specify the company and the product that you want to check the on-hand inventory for.</span></span> <span data-ttu-id="dc83a-111">Essa caixa de diálogo mostra as mesmas informações do que o [Estoque disponível](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span><span class="sxs-lookup"><span data-stu-id="dc83a-111">This dialog box shows the same information as [On-hand inventory](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span></span>

<span data-ttu-id="dc83a-112">A caixa de diálogo retorna as informações de estoque do Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="dc83a-112">The dialog box returns the inventory information from Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="dc83a-113">Essas informações incluem as seguintes quantidades:</span><span class="sxs-lookup"><span data-stu-id="dc83a-113">This information includes the following quantities:</span></span>

- <span data-ttu-id="dc83a-114">Quantidade disponível</span><span class="sxs-lookup"><span data-stu-id="dc83a-114">On-hand quantity</span></span>
- <span data-ttu-id="dc83a-115">Quantidade disponível reservada</span><span class="sxs-lookup"><span data-stu-id="dc83a-115">Reserved on-hand quantity</span></span>
- <span data-ttu-id="dc83a-116">Quantidade disponível</span><span class="sxs-lookup"><span data-stu-id="dc83a-116">Available on-hand quantity</span></span>
- <span data-ttu-id="dc83a-117">Quantidade encomendada</span><span class="sxs-lookup"><span data-stu-id="dc83a-117">Ordered quantity</span></span>
- <span data-ttu-id="dc83a-118">Quantidade na ordem</span><span class="sxs-lookup"><span data-stu-id="dc83a-118">On-order quantity</span></span>
- <span data-ttu-id="dc83a-119">Quantidade encomendada reservada</span><span class="sxs-lookup"><span data-stu-id="dc83a-119">Reserved ordered quantity</span></span>
- <span data-ttu-id="dc83a-120">Quantidade disponível total</span><span class="sxs-lookup"><span data-stu-id="dc83a-120">Total available quantity</span></span>

## <a name="atp-information"></a><span data-ttu-id="dc83a-121">Informações sobre ATP</span><span class="sxs-lookup"><span data-stu-id="dc83a-121">ATP information</span></span>

<span data-ttu-id="dc83a-122">No Sales, um novo botão **Informações sobre ATP** foi adicionado aos itens de linha nas páginas **Cotações** , **Ordens** e **Faturas**.</span><span class="sxs-lookup"><span data-stu-id="dc83a-122">In Sales, a new **ATP Information** button has been added to line items on the **Quotes** , **Orders** , and **Invoices** pages.</span></span> <span data-ttu-id="dc83a-123">Quando você selecione essa botão, uma caixa de diálogo é exibida e você pode especificar empresa, produto, site do estoque, depósito de estoque e quantidade da ordem.</span><span class="sxs-lookup"><span data-stu-id="dc83a-123">When you select this button, a dialog box appears, where you can specify the company, product, inventory site, inventory warehouse, and order quantity.</span></span> <span data-ttu-id="dc83a-124">Essa caixa de diálogo tem as mesmas configurações descritas em [Promessa de ordem](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span><span class="sxs-lookup"><span data-stu-id="dc83a-124">This dialog box has the same settings that are described in [Order promising](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span></span>

<span data-ttu-id="dc83a-125">A caixa de diálogo retorna as informações sobre ATP do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="dc83a-125">The dialog box returns the ATP information from Supply Chain Management.</span></span> <span data-ttu-id="dc83a-126">Essas informações incluem as seguintes quantidades:</span><span class="sxs-lookup"><span data-stu-id="dc83a-126">This information includes the following quantities:</span></span>

- <span data-ttu-id="dc83a-127">Quantidade ATP</span><span class="sxs-lookup"><span data-stu-id="dc83a-127">ATP quantity</span></span>
- <span data-ttu-id="dc83a-128">Quantidade recebida</span><span class="sxs-lookup"><span data-stu-id="dc83a-128">Receipt quantity</span></span>
- <span data-ttu-id="dc83a-129">Quantidade emitida</span><span class="sxs-lookup"><span data-stu-id="dc83a-129">Issue quantity</span></span>
- <span data-ttu-id="dc83a-130">Quantidade disponível</span><span class="sxs-lookup"><span data-stu-id="dc83a-130">On-hand quantity</span></span>
