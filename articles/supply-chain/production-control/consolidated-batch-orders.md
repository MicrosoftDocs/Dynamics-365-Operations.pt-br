---
title: Ordens de lote consolidadas
description: Este artigo descreve o conceito das ordens de lotes consolidados.
author: ShylaThompson
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PmfAddToConsOrder, PmfBulkItemConv, PmfBulkPackOnHand, PmfConsOrderListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19291
ms.assetid: e97f1d3d-1306-4c42-b2bc-d1755fe574d5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2098cb458821146f6d1bf029591493ac745626f1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966446"
---
# <a name="consolidated-batch-orders"></a><span data-ttu-id="16f80-103">Ordens de lote consolidadas</span><span class="sxs-lookup"><span data-stu-id="16f80-103">Consolidated batch orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="16f80-104">Este artigo descreve o conceito das ordens de lotes consolidados.</span><span class="sxs-lookup"><span data-stu-id="16f80-104">This article describes the concept of consolidated batch orders.</span></span>

<span data-ttu-id="16f80-105">Um item a granel produzido é considerado um item principal, enquanto um item embalado é considerado um item secundário.</span><span class="sxs-lookup"><span data-stu-id="16f80-105">A bulk item that is produced is considered a parent item, whereas a packed item is considered a child item.</span></span> <span data-ttu-id="16f80-106">A relação entre o item a granel e o item embalado é expressa em uma conversão do item a granel.</span><span class="sxs-lookup"><span data-stu-id="16f80-106">The relation between the bulk item and the packed item is expressed in a bulk item conversion.</span></span> <span data-ttu-id="16f80-107">Essa conversão do item a granel é definida no próprio item a granel.</span><span class="sxs-lookup"><span data-stu-id="16f80-107">This bulk item conversion is defined on the bulk item itself.</span></span>  

<span data-ttu-id="16f80-108">Os itens embalados podem ser embalados em contêineres de um único tamanho ou de vários tamanhos considerados como uma unidade.</span><span class="sxs-lookup"><span data-stu-id="16f80-108">Packed items can be packaged into containers of either a single size or multiple sizes that are considered one unit.</span></span> <span data-ttu-id="16f80-109">Ao consolidar as ordens para um item a granel, você poderá ver todas as ordens do lote relacionadas em uma única exibição, que pode ajudar a determinar qualquer trabalho restante que tenha de ser concluído.</span><span class="sxs-lookup"><span data-stu-id="16f80-109">By consolidating the orders for a bulk item, you can see all the related batch orders in a single view that can help you determine any remaining work that must be completed.</span></span>  

<span data-ttu-id="16f80-110">Uma ordem de lote consolidada pode conter qualquer combinação das seguintes ordens:</span><span class="sxs-lookup"><span data-stu-id="16f80-110">A consolidated batch order can contain any combination of the following orders:</span></span>

-   <span data-ttu-id="16f80-111">Uma única ordem a granel e várias ordens embaladas</span><span class="sxs-lookup"><span data-stu-id="16f80-111">A single bulk order and multiple packed orders</span></span>
-   <span data-ttu-id="16f80-112">Várias ordens a granel e várias ordens embaladas</span><span class="sxs-lookup"><span data-stu-id="16f80-112">Multiple bulk orders and multiple packed orders</span></span>
-   <span data-ttu-id="16f80-113">Várias ordens a granel e uma única ordem embalada</span><span class="sxs-lookup"><span data-stu-id="16f80-113">Multiple bulk orders and a single packed order</span></span>
-   <span data-ttu-id="16f80-114">Somente ordens embaladas</span><span class="sxs-lookup"><span data-stu-id="16f80-114">Only packed orders</span></span>




