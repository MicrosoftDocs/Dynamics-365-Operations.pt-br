---
title: Solucionar problemas de liberações e remessas parciais
description: Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com liberações parciais e remessas parciais no Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1c9246376505e163a4a41bf141a98deed0fd511f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263219"
---
# <a name="troubleshoot-partial-releases-and-partial-shipments"></a><span data-ttu-id="7eb8d-103">Solucionar problemas de liberações e remessas parciais</span><span class="sxs-lookup"><span data-stu-id="7eb8d-103">Troubleshoot partial releases and partial shipments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7eb8d-104">Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com liberações parciais e remessas parciais no Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7eb8d-104">This topic describes how to fix common issues that you might encounter while you work with partial releases and partial shipments in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="the-release-status-of-a-sales-order-remains-partially-released-even-after-the-sales-order-is-invoiced"></a><span data-ttu-id="7eb8d-105">O status de liberação de uma ordem de venda permanece Parcialmente liberada, mesmo depois que a ordem de venda é faturada.</span><span class="sxs-lookup"><span data-stu-id="7eb8d-105">The release status of a sales order remains Partially released even after the sales order is invoiced.</span></span>

### <a name="issue-description"></a><span data-ttu-id="7eb8d-106">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="7eb8d-106">Issue description</span></span>

<span data-ttu-id="7eb8d-107">Uma ordem de venda é uma ordem de entrega, mas um ou mais itens contidos nela possuem um modo de entrega diferente.</span><span class="sxs-lookup"><span data-stu-id="7eb8d-107">A sales order is a delivery order, but one or more items on it have a different mode of delivery.</span></span> <span data-ttu-id="7eb8d-108">Depois que a ordem é faturada, ela ainda tem um status de liberação de *Parcialmente liberada*.</span><span class="sxs-lookup"><span data-stu-id="7eb8d-108">After the order is invoiced, it still has a release status of *Partially released*.</span></span>

<span data-ttu-id="7eb8d-109">Por exemplo, uma ordem de venda tem dois itens: um para entrega e outro para retirada.</span><span class="sxs-lookup"><span data-stu-id="7eb8d-109">For example, a sales order has two items: one for delivery and one for pickup.</span></span> <span data-ttu-id="7eb8d-110">A entrega e a retirada foram realizadas.</span><span class="sxs-lookup"><span data-stu-id="7eb8d-110">Both the delivery and the pickup have been done.</span></span> <span data-ttu-id="7eb8d-111">Portanto, ambas as linhas foram faturadas.</span><span class="sxs-lookup"><span data-stu-id="7eb8d-111">Therefore, both lines have been invoiced.</span></span> <span data-ttu-id="7eb8d-112">No entanto, o status de liberação ainda é mostrado como *Parcialmente liberada*, o que é enganoso.</span><span class="sxs-lookup"><span data-stu-id="7eb8d-112">However, the release status is still shown as *Partially released*, which is misleading.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="7eb8d-113">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="7eb8d-113">Issue resolution</span></span>

<span data-ttu-id="7eb8d-114">O status de liberação se aplica apenas a linhas de ordem em que os itens estão habilitados para gerenciamento de depósito.</span><span class="sxs-lookup"><span data-stu-id="7eb8d-114">The release status applies only to order lines where the items are enabled for warehouse management.</span></span> <span data-ttu-id="7eb8d-115">Portanto, o status de liberação permanece *Parcialmente liberada* neste cenário.</span><span class="sxs-lookup"><span data-stu-id="7eb8d-115">Therefore, the release status remains *Partially released* in this scenario.</span></span> <span data-ttu-id="7eb8d-116">A Microsoft avaliou esse problema e determinou que é uma limitação de recurso.</span><span class="sxs-lookup"><span data-stu-id="7eb8d-116">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="7eb8d-117">Uma extensão pode ser adicionada como parte da guia de remessa e do processo de faturamento para atualizar o status de liberação.</span><span class="sxs-lookup"><span data-stu-id="7eb8d-117">An extension could be added as part of the packing slip and invoicing process to update the release status.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]