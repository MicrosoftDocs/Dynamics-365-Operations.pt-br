---
title: O campo "Data do último teste" não atualiza quando várias ordens de qualidade são criadas
description: O campo "Data do último teste" não atualiza quando várias ordens de qualidade são criadas.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventBatch
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6f796bdaa88d32b1c58dd8a4bca19f0ce4f3943d
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026280"
---
# <a name="the-last-tested-date-field-isnt-updated-when-multiple-quality-orders-are-created"></a><span data-ttu-id="0692a-103">O campo "Data do último teste" não atualiza quando várias ordens de qualidade são criadas</span><span class="sxs-lookup"><span data-stu-id="0692a-103">The Last tested date field isn't updated when multiple quality orders are created</span></span>

<span data-ttu-id="0692a-104">Número de KB: 4612803</span><span class="sxs-lookup"><span data-stu-id="0692a-104">KB number: 4612803</span></span>

## <a name="symptoms"></a><span data-ttu-id="0692a-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="0692a-105">Symptoms</span></span>

<span data-ttu-id="0692a-106">O campo **Data do último teste** não atualiza quando várias ordens de qualidade são criadas.</span><span class="sxs-lookup"><span data-stu-id="0692a-106">The **Last tested date** field isn't updated when multiple quality orders are created.</span></span>

## <a name="resolution"></a><span data-ttu-id="0692a-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="0692a-107">Resolution</span></span>

<span data-ttu-id="0692a-108">O sistema está agindo como esperado.</span><span class="sxs-lookup"><span data-stu-id="0692a-108">The system is behaving as designed.</span></span> <span data-ttu-id="0692a-109">A data do último teste não está relacionada a ordens de qualidade.</span><span class="sxs-lookup"><span data-stu-id="0692a-109">The last tested date isn't related to quality orders.</span></span> <span data-ttu-id="0692a-110">Ela guarda a data em que os bens acabados foram comprados ou fabricados pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="0692a-110">It stores the date when the finished goods were first purchased or manufactured.</span></span> <span data-ttu-id="0692a-111">Esta data é usada para calcular a data de aviso de validade.</span><span class="sxs-lookup"><span data-stu-id="0692a-111">This date is used to calculate the shelf life advice date.</span></span>
