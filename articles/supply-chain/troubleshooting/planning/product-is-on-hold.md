---
title: O produto está em espera para transações
description: Depois de firmar ordens de planejamento, você recebe uma mensagem de erro que afirma que um item está em espera para transações.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6654e6437a088218db116b955631be4c7e62de5f
ms.sourcegitcommit: f9b145ef4a81cec81f420871b4130b05db4f4500
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301270"
---
# <a name="product-is-on-hold-for-transactions"></a><span data-ttu-id="660eb-103">O produto está em espera para transações</span><span class="sxs-lookup"><span data-stu-id="660eb-103">Product is on hold for transactions</span></span>

<span data-ttu-id="660eb-104">Código de erro: SYS13295</span><span class="sxs-lookup"><span data-stu-id="660eb-104">Error code: SYS13295</span></span>

## <a name="symptoms"></a><span data-ttu-id="660eb-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="660eb-105">Symptoms</span></span>

<span data-ttu-id="660eb-106">Depois de firmar ordens planejadas, você recebe a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="660eb-106">After you firm planned orders, you receive the following error message:</span></span>

> <span data-ttu-id="660eb-107">O item %1 está retido para transações em %2.</span><span class="sxs-lookup"><span data-stu-id="660eb-107">Item %1 is on hold for transactions in %2.</span></span>

## <a name="cause"></a><span data-ttu-id="660eb-108">Causa</span><span class="sxs-lookup"><span data-stu-id="660eb-108">Cause</span></span>

<span data-ttu-id="660eb-109">Ao descrever os itens bloqueados, o sistema usa os termos *bloqueados*, *interrompidos* e *em espera* de forma alternada.</span><span class="sxs-lookup"><span data-stu-id="660eb-109">When describing blocked items, system uses the terms *blocked*, *stopped*, and *on hold* interchangeably.</span></span> <span data-ttu-id="660eb-110">Esse erro significa que o item está definido como **Interrompido** em suas configurações de ordem padrão.</span><span class="sxs-lookup"><span data-stu-id="660eb-110">This error means that the item is set as **Stopped** in its default order settings.</span></span>

<span data-ttu-id="660eb-111">Se um item estiver bloqueado e você o adicionar a uma linha de ordem de compra ou de venda, você receberá uma mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="660eb-111">If an item is blocked, and you add it to a purchase order or sales order line, you receive a warning message.</span></span> <span data-ttu-id="660eb-112">Quando o item está bloqueado, não é possível modificar as transações de estoque que estão relacionadas à linha da ordem de compra ou de venda, por exemplo, quando você lança uma guia de remessa ou uma fatura.</span><span class="sxs-lookup"><span data-stu-id="660eb-112">When an item is blocked, inventory transactions that are related to the purchase order or sales order line can't be modified (for example, when you post a packing slip or an invoice).</span></span> <span data-ttu-id="660eb-113">Você pode bloquear um item comprado e, ao mesmo tempo, vendê-lo.</span><span class="sxs-lookup"><span data-stu-id="660eb-113">You can block a purchased item, and, at the same time, sell the item.</span></span> <span data-ttu-id="660eb-114">Nesse caso, a caixa de seleção **Interrompido** marcada em uma ordem de compra, mas o item não é bloqueado no estoque ou em uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="660eb-114">In this case, the **Stopped** check box is selected on a purchase order, but the item isn't blocked in inventory or on a sales order.</span></span>

<span data-ttu-id="660eb-115">Aqui estão algumas das condições que podem fazer com que um número de item seja impedido de ser vendido:</span><span class="sxs-lookup"><span data-stu-id="660eb-115">Here are some of the conditions that can cause an item number to be blocked from being sold:</span></span>

- <span data-ttu-id="660eb-116">O item ainda está em desenvolvimento ou fabricação.</span><span class="sxs-lookup"><span data-stu-id="660eb-116">The item is still under development or manufacture.</span></span> <span data-ttu-id="660eb-117">Portanto, você não quer que ele seja vendido ou reservado.</span><span class="sxs-lookup"><span data-stu-id="660eb-117">Therefore, you don't want it to be sold or reserved.</span></span>
- <span data-ttu-id="660eb-118">Você recebeu muitos itens defeituosos, e os defeitos devem ser corrigidos antes que o item possa ser vendido.</span><span class="sxs-lookup"><span data-stu-id="660eb-118">You've received many defective items, and the defects must be corrected before the item can be sold.</span></span>

<span data-ttu-id="660eb-119">Em casos assim, você pode bloquear o item até que o problema seja resolvido.</span><span class="sxs-lookup"><span data-stu-id="660eb-119">In cases of this type, you can block the item until the issue is resolved.</span></span>

<span data-ttu-id="660eb-120">Se um item estiver bloqueado e você criar uma linha de ordem de devolução, você receberá uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="660eb-120">If an item is blocked, and you create a return order line, you receive a message.</span></span> <span data-ttu-id="660eb-121">Não é possível bloquear uma série ou um lote do item.</span><span class="sxs-lookup"><span data-stu-id="660eb-121">You can't block a series or a lot of an item.</span></span> <span data-ttu-id="660eb-122">Se partes do item tiverem de ser bloqueadas, você poderá bloqueá-las movendo o estoque ou bloqueando o estoque inteiro do item durante aquele período.</span><span class="sxs-lookup"><span data-stu-id="660eb-122">If parts of an item must be blocked, you can block them by moving inventory or by blocking the full stock of the item for that period.</span></span>

## <a name="resolution"></a><span data-ttu-id="660eb-123">Resolução</span><span class="sxs-lookup"><span data-stu-id="660eb-123">Resolution</span></span>

- <span data-ttu-id="660eb-124">Abra a página **Configurações de ordem padrão** para o item e desmarque a caixa de seleção **Interrompido**.</span><span class="sxs-lookup"><span data-stu-id="660eb-124">Open the **Default order settings** page for the item, and clear the **Stopped** checkbox.</span></span>
