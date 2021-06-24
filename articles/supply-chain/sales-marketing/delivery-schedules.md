---
title: Agendas de entrega
description: As agendas de entrega permitem que você rastreie a quantidade da linha da ordem quando estiver usando várias entregas para uma única ordem de venda, cotação de venda ou ordem de compra.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchDeliverySchedule, SalesDeliverySchedule, SalesQuotationDeliverySchedule, SalesQuotationDeliverySchedule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 213984
ms.assetid: 44cac104-c36c-4371-a992-9178b3fd65e9
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3dbd66d499b5d5f9f8ef21c0ce3752031a5f4672
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193773"
---
# <a name="delivery-schedules"></a><span data-ttu-id="81dc1-103">Agendas de entrega</span><span class="sxs-lookup"><span data-stu-id="81dc1-103">Delivery schedules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="81dc1-104">As agendas de entrega permitem que você rastreie a quantidade da linha da ordem quando estiver usando várias entregas para uma única ordem de venda, cotação de venda ou ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="81dc1-104">Delivery schedules allow you to track order line quantity when you are using multiple deliveries for a single sales order, sales quotation, or purchase order.</span></span>

<span data-ttu-id="81dc1-105">Use um plano de entrega quando a quantidade total em uma linha de ordem ou cotação tiver que ser entregue em várias remessas.</span><span class="sxs-lookup"><span data-stu-id="81dc1-105">Use a delivery schedule when the total quantity on an order or quotation line must be delivered in multiple shipments.</span></span> <span data-ttu-id="81dc1-106">Remessas individuais são representadas por linhas de entrega.</span><span class="sxs-lookup"><span data-stu-id="81dc1-106">Individual shipments are represented by delivery lines.</span></span> <span data-ttu-id="81dc1-107">Duas ou mais linhas de entrega compõem uma agenda de entrega.</span><span class="sxs-lookup"><span data-stu-id="81dc1-107">Two or more delivery lines make up one delivery schedule.</span></span> <span data-ttu-id="81dc1-108">As linhas de entrega podem ter datas de entrega diferentes, quantidades, modos de entrega e dimensões de armazenamento, como o site e o depósito.</span><span class="sxs-lookup"><span data-stu-id="81dc1-108">The delivery lines can have different delivery dates, quantities, modes of delivery, and storage dimensions, such as site and warehouse.</span></span>  

<span data-ttu-id="81dc1-109">**Exemplo de uma agenda de entrega**</span><span class="sxs-lookup"><span data-stu-id="81dc1-109">**Example of a delivery schedule**</span></span>

| <span data-ttu-id="81dc1-110">Item </span><span class="sxs-lookup"><span data-stu-id="81dc1-110">Item</span></span>                              | <span data-ttu-id="81dc1-111">Alíquota</span><span class="sxs-lookup"><span data-stu-id="81dc1-111">Value</span></span>                                    |
|-----------------------------------|------------------------------------------|
| <span data-ttu-id="81dc1-112">Ordem total (linha da ordem original)</span><span class="sxs-lookup"><span data-stu-id="81dc1-112">Total order (original order line)</span></span> | <span data-ttu-id="81dc1-113">600 cadeiras</span><span class="sxs-lookup"><span data-stu-id="81dc1-113">600 chairs</span></span>                               |
| <span data-ttu-id="81dc1-114">Agenda de entrega solicitada</span><span class="sxs-lookup"><span data-stu-id="81dc1-114">Requested delivery schedule</span></span>       | <span data-ttu-id="81dc1-115">100 cadeiras por mês</span><span class="sxs-lookup"><span data-stu-id="81dc1-115">100 chairs per month</span></span>                     |
| <span data-ttu-id="81dc1-116">Período solicitado para entrega</span><span class="sxs-lookup"><span data-stu-id="81dc1-116">Requested time frame for delivery</span></span> | <span data-ttu-id="81dc1-117">6 meses, no primeiro dia de cada mês</span><span class="sxs-lookup"><span data-stu-id="81dc1-117">6 months, on the first day of each month</span></span> |

<span data-ttu-id="81dc1-118">Neste cenário, o cliente solicita uma entrega de 600 cadeiras em lotes de 100 cadeiras durante um período de seis meses.</span><span class="sxs-lookup"><span data-stu-id="81dc1-118">In this scenario, the customer requests delivery of 600 chairs in batches of 100 chairs over a period of six months.</span></span> <span data-ttu-id="81dc1-119">Para controlar os requisitos de entrega, você cria uma agenda de entrega.</span><span class="sxs-lookup"><span data-stu-id="81dc1-119">To keep track of the delivery requirements, you create a delivery schedule.</span></span> <span data-ttu-id="81dc1-120">Na página da agenda de entrega, você cria seis linhas de entrega separadas.</span><span class="sxs-lookup"><span data-stu-id="81dc1-120">On the delivery schedule page, you create six separate delivery lines.</span></span> <span data-ttu-id="81dc1-121">Cada linha de entrega contem 100 cadeiras e indica a data de entrega para essas 100 cadeiras.</span><span class="sxs-lookup"><span data-stu-id="81dc1-121">Each delivery line contains 100 chairs and indicates the delivery date for those 100 chairs.</span></span> <span data-ttu-id="81dc1-122">Neste caso, cada linha é compensada no primeiro dia do mês, por seis meses consecutivos.</span><span class="sxs-lookup"><span data-stu-id="81dc1-122">In this case, each line is offset on the first of the month for six consecutive months.</span></span>  

<span data-ttu-id="81dc1-123">Quando você cria uma agenda de entrega, o tipo da linha da ordem original será alterado automaticamente para **Linha da ordem com várias entregas**.</span><span class="sxs-lookup"><span data-stu-id="81dc1-123">When you create a delivery schedule, the type of the original order line is automatically changed to **Order line with multiple deliveries**.</span></span> <span data-ttu-id="81dc1-124">Uma linha deste tipo é mencionada como uma linha comercial e é marcada por um ícone.</span><span class="sxs-lookup"><span data-stu-id="81dc1-124">A line of this type is referred to as a commercial line and is marked by an icon.</span></span> <span data-ttu-id="81dc1-125">A linha de entrega é marcada por um ícone diferente.</span><span class="sxs-lookup"><span data-stu-id="81dc1-125">The delivery line is marked by a different icon.</span></span> <span data-ttu-id="81dc1-126">Se você alterar uma quantidade em uma linha de entrega, a linha comercial é atualizada para a quantidade total da agenda de entrega.</span><span class="sxs-lookup"><span data-stu-id="81dc1-126">If you change a quantity on a delivery line, the commercial line is updated to the total quantity of the delivery schedule.</span></span> <span data-ttu-id="81dc1-127">Se um contrato comercial tiver um desconto total definido para a ordem, a agenda de entrega garantirá que a ordem seja qualificada para o desconto total da ordem, mesmo quando ordem for dividida em entregas separadas.</span><span class="sxs-lookup"><span data-stu-id="81dc1-127">If a trade agreement has defined a total discount for the order, the delivery schedule ensures that your order is eligible for the total order discount, even when the order is split into separate deliveries.</span></span>  

<span data-ttu-id="81dc1-128">Ordens que tenham uma agenda de entrega são processadas em relação às linhas de entrega.</span><span class="sxs-lookup"><span data-stu-id="81dc1-128">Orders that have a delivery schedule are processed against the delivery lines.</span></span> <span data-ttu-id="81dc1-129">O processamento inclui o lançamento de guias de remessa, recebimentos de produtos e faturamento.</span><span class="sxs-lookup"><span data-stu-id="81dc1-129">Processing includes the posting of packing slips, product receipts, and invoicing.</span></span>  

<span data-ttu-id="81dc1-130">Impressões de documento de ordens e cotações que têm uma agenda de entrega mostram apenas as linhas de entrega.</span><span class="sxs-lookup"><span data-stu-id="81dc1-130">Document printouts of orders and quotations that have a delivery schedule show only the delivery lines.</span></span> <span data-ttu-id="81dc1-131">Não mostram as linhas originais (linhas comerciais).</span><span class="sxs-lookup"><span data-stu-id="81dc1-131">They don't show the original lines (commercial lines).</span></span> <span data-ttu-id="81dc1-132">**Observação:** Além disso, apenas as linhas de entrega serão exibidas quando você executar estas ações:</span><span class="sxs-lookup"><span data-stu-id="81dc1-132">**Note:** In addition, only the delivery lines are shown when you perform these actions:</span></span>

-   <span data-ttu-id="81dc1-133">Lançar</span><span class="sxs-lookup"><span data-stu-id="81dc1-133">Post</span></span>
-   <span data-ttu-id="81dc1-134">Copiar páginas</span><span class="sxs-lookup"><span data-stu-id="81dc1-134">Copy pages</span></span>
-   <span data-ttu-id="81dc1-135">Procurar páginas de lista e relatórios</span><span class="sxs-lookup"><span data-stu-id="81dc1-135">Browse list pages and reports</span></span>

<span data-ttu-id="81dc1-136">Quando você confirmar as cotações de venda, as ordens de venda resultantes mostrarão a agenda de entrega completa, até mesmo as linhas de ordem que têm várias entregas.</span><span class="sxs-lookup"><span data-stu-id="81dc1-136">When you confirm sales quotations, the resulting sales orders show the whole delivery schedule, even the order lines that have multiple deliveries.</span></span> <span data-ttu-id="81dc1-137">Além disso, a agenda de entrega inteira é exibida em todas as páginas principais, como ordens de venda, cotações de venda e ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="81dc1-137">In addition, the whole delivery schedule is shown on all the major pages, such as sales orders, sales quotations, and purchase orders.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]