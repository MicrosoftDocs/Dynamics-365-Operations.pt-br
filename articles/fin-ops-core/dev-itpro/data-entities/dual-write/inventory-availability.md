---
title: Disponibilidade de estoque em gravação dupla
description: Este tópico fornece informações sobre a disponibilidade de verificação de estoque em gravação dupla.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: dd0995eb8c70ed06cdc3c0f6a28b13b117297533
ms.sourcegitcommit: be7e4378c8122c6e7cfc4e7991efbdffee45e006
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2020
ms.locfileid: "3426973"
---
# <a name="inventory-availability"></a><span data-ttu-id="306b9-103">Disponibilidade de estoque</span><span class="sxs-lookup"><span data-stu-id="306b9-103">Inventory availability</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="306b9-104">Usando a disponibilidade de estoque, você pode verificar seu estoque antes de adicionar um produto aos formulários **Cotações**, **Ordens** ou **Faturas** em aplicativos baseados em modelo no Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="306b9-104">Using inventory availability, you can check your inventory before you add a product into the **Quotes**, **Orders**, or **Invoices** forms in model-driven apps in Dynamics 365.</span></span> <span data-ttu-id="306b9-105">Por exemplo, a verificação de estoque e a determinação de uma data de atendimento é uma tarefa fundamental no [processo de pagamento à vista](dual-write-prospect-to-cash.md).</span><span class="sxs-lookup"><span data-stu-id="306b9-105">For example, checking inventory and determining a fulfullment date is a key task in the [prospect-to-cash](dual-write-prospect-to-cash.md) process.</span></span> <span data-ttu-id="306b9-106">Se não tiver estoque suficiente, você poderá estimar uma data de entrega com base em recebimentos e saídas de estoque projetado.</span><span class="sxs-lookup"><span data-stu-id="306b9-106">If you don't have enough inventory, you can estimate a delivery date based on projected inventory receipts and issues.</span></span> <span data-ttu-id="306b9-107">Você também pode verificar as informações de disponível para promessa (ATP), em que é possível encontrar a quantidade ATP no limite de tempo predefinido.</span><span class="sxs-lookup"><span data-stu-id="306b9-107">You can also check the product's available-to-promise (ATP) information, where you can find the ATP quantity in the pre-defined time fence.</span></span>

## <a name="on-hand-inventory"></a><span data-ttu-id="306b9-108">Estoque disponível</span><span class="sxs-lookup"><span data-stu-id="306b9-108">On-hand Inventory</span></span> 

<span data-ttu-id="306b9-109">No cabeçalho dos formulários **Cotações**, **Ordens** ou **Faturas** no Dynamics 365 Sales, foi adicionado um novo botão **Estoque disponível**.</span><span class="sxs-lookup"><span data-stu-id="306b9-109">In the header of the **Quotes**, **Orders**, or **Invoices** forms in Dynamics 365 Sales, a new button **On-hand Inventory** is added.</span></span> <span data-ttu-id="306b9-110">Quando você clica no botão, uma caixa de diálogo é exibida e você pode especificar a empresa e o produto para o qual deseja verificar o estoque disponível.</span><span class="sxs-lookup"><span data-stu-id="306b9-110">When you click the button, a dialog box appears and you can specify the company and the product for which you want to check the on-hand inventory.</span></span> <span data-ttu-id="306b9-111">Ele retorna as informações de estoque do Dynamics 365 Supply Chain Management e mostra as mesmas informações do [Estoque disponível](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span><span class="sxs-lookup"><span data-stu-id="306b9-111">It returns the inventory information from Dynamics 365 Supply Chain Management, and shows the same information as [On-hand inventory](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span></span> <span data-ttu-id="306b9-112">As informações incluem estas quantidades:</span><span class="sxs-lookup"><span data-stu-id="306b9-112">The information includes these quantities:</span></span>

- <span data-ttu-id="306b9-113">**Quantidade Disponível**</span><span class="sxs-lookup"><span data-stu-id="306b9-113">**On-hand Quantity**</span></span>
- <span data-ttu-id="306b9-114">**Quantidade Disponível Reservada**</span><span class="sxs-lookup"><span data-stu-id="306b9-114">**Reserved On-hand Quantity**</span></span>
- <span data-ttu-id="306b9-115">**Quantidade Disponível**</span><span class="sxs-lookup"><span data-stu-id="306b9-115">**Available On-hand Quantity**</span></span>
- <span data-ttu-id="306b9-116">**Quantidade da Ordem**</span><span class="sxs-lookup"><span data-stu-id="306b9-116">**Orderd Quantity**</span></span>
- <span data-ttu-id="306b9-117">**Quantidade na Ordem**</span><span class="sxs-lookup"><span data-stu-id="306b9-117">**On-order Quantity**</span></span>
- <span data-ttu-id="306b9-118">**Quantidade Encomendada Reservada**</span><span class="sxs-lookup"><span data-stu-id="306b9-118">**Reserved Ordered Quantity**</span></span>
- <span data-ttu-id="306b9-119">**Quantidade Disponível Total**</span><span class="sxs-lookup"><span data-stu-id="306b9-119">**Total Available Quantity**</span></span>

## <a name="atp-information"></a><span data-ttu-id="306b9-120">Informações sobre ATP</span><span class="sxs-lookup"><span data-stu-id="306b9-120">ATP information</span></span>

<span data-ttu-id="306b9-121">Em itens de linha dos formulários **Cotações**, **Ordens** ou **Faturas** no Dynamics 365 Sales, foi adicionado um novo botão **Informações ATP**.</span><span class="sxs-lookup"><span data-stu-id="306b9-121">On line items of the **Quotes**, **Orders**, or **Invoices** forms in Dynamics 365 Sales, a new button **ATP Information** is added.</span></span> <span data-ttu-id="306b9-122">Quando você clica no botão, uma caixa de diálogo é exibida e você pode especificar a empresa, produto, site do estoque, depósito de estoque e quantidade da ordem.</span><span class="sxs-lookup"><span data-stu-id="306b9-122">When you click the button, a dialog box appears and you can specify the company, product, inventory Site, inventory warehouse, and order quantity.</span></span> <span data-ttu-id="306b9-123">Ele retorna as **informações ATP** do Supply Chain Management e mostra as configurações descritas em [Promessa de ordem](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span><span class="sxs-lookup"><span data-stu-id="306b9-123">It returns the **ATP Information** from Supply Chain Management and shows the settings descrbed in [Order promising](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span></span> <span data-ttu-id="306b9-124">As informações incluem a **Quantidade ATP**, a **Quantidade de recebimento**, **Quantidade de saída** e **Quantidade disponível**.</span><span class="sxs-lookup"><span data-stu-id="306b9-124">The information includes **ATP quantity**, **Receipt quantity**, **Issue quantity**, and **On-hand quantity**.</span></span>
