---
title: Somente um rótulo é impresso para vários cabeçalhos de trabalho em um único recibo
description: Somente um rótulo é impresso para vários cabeçalhos de trabalho em um único recibo.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8e11dc918eb3c9085018d15b43819522cc8bebe3
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026268"
---
# <a name="only-one-label-is-printed-for-multiple-work-headers-on-a-single-receipt"></a><span data-ttu-id="b591f-103">Somente um rótulo é impresso para vários cabeçalhos de trabalho em um único recibo</span><span class="sxs-lookup"><span data-stu-id="b591f-103">Only one label is printed for multiple work headers on a single receipt</span></span>

<span data-ttu-id="b591f-104">Número de KB: 4614667</span><span class="sxs-lookup"><span data-stu-id="b591f-104">KB number: 4614667</span></span>

## <a name="symptoms"></a><span data-ttu-id="b591f-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="b591f-105">Symptoms</span></span>

<span data-ttu-id="b591f-106">Vários cabeçalhos de trabalho são criados para a mesma placa de licença de destino que parte de um único aplicativo de depósito.</span><span class="sxs-lookup"><span data-stu-id="b591f-106">Multiple work headers are created for the same target license plate as part of a single warehouse app receiving event.</span></span> <span data-ttu-id="b591f-107">No entanto, apenas uma etiqueta da placa de licença é impressa quando o produto é recebido.</span><span class="sxs-lookup"><span data-stu-id="b591f-107">However, only one license plate label is printed when the product is received.</span></span>

## <a name="resolution"></a><span data-ttu-id="b591f-108">Resolução</span><span class="sxs-lookup"><span data-stu-id="b591f-108">Resolution</span></span>

<span data-ttu-id="b591f-109">O sistema está agindo como esperado.</span><span class="sxs-lookup"><span data-stu-id="b591f-109">The system is behaving as designed.</span></span>

<span data-ttu-id="b591f-110">No design atual, uma etiqueta da placa de licença é sempre gerada, independentemente do número de combinações de cabeçalho de trabalho e de linha de trabalho existentes.</span><span class="sxs-lookup"><span data-stu-id="b591f-110">In the current design, a single license plate label is always generated, regardless of the number of work header and work line combinations that exist.</span></span> <span data-ttu-id="b591f-111">A etiqueta gerada inclui as informações para apenas uma combinação.</span><span class="sxs-lookup"><span data-stu-id="b591f-111">The generated label includes the information for only one combination.</span></span>

<span data-ttu-id="b591f-112">Para resolver esse problema, certifique-se de que a criação do cabeçalho de trabalho seja sempre mapeada para apenas uma placa de licença de destino.</span><span class="sxs-lookup"><span data-stu-id="b591f-112">To work around this issue, make sure that work header creation is always mapped to just one target license plate.</span></span>
