---
title: O depósito no diário de listas de separação não atualiza em uma linha da BOM.
description: O depósito no diário de listas de separação atualiza em uma linha da lista de materiais (BOM).
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdJournalTransBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 5d24c0b8538f3894fd1d2a3edb3a6ed8633c9609
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026260"
---
# <a name="the-warehouse-in-the-picking-list-journal-isnt-updated-on-a-bom-line"></a><span data-ttu-id="97e8e-103">O depósito no diário de listas de separação atualiza em uma linha da BOM</span><span class="sxs-lookup"><span data-stu-id="97e8e-103">The warehouse in the picking list journal isn't updated on a BOM line</span></span>

<span data-ttu-id="97e8e-104">Número de KB: 4614848</span><span class="sxs-lookup"><span data-stu-id="97e8e-104">KB number: 4614848</span></span>

## <a name="symptoms"></a><span data-ttu-id="97e8e-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="97e8e-105">Symptoms</span></span>

<span data-ttu-id="97e8e-106">O depósito no diário de listas de separação atualiza em uma linha da lista de materiais (BOM).</span><span class="sxs-lookup"><span data-stu-id="97e8e-106">The warehouse in the picking list journal isn't updated on a bill of materials (BOM) line.</span></span>

## <a name="resolution"></a><span data-ttu-id="97e8e-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="97e8e-107">Resolution</span></span>

<span data-ttu-id="97e8e-108">O sistema está agindo como esperado.</span><span class="sxs-lookup"><span data-stu-id="97e8e-108">The system is behaving as designed.</span></span> <span data-ttu-id="97e8e-109">Se uma linha do diário de listas de separação for criada com uma referência (por meio do ID do lote) para uma linha da BOM de produção, o depósito na linha de produção da BOM não será atualizado se a dimensão do depósito na linha de produção do diário da lista de separação for alterada posteriormente.</span><span class="sxs-lookup"><span data-stu-id="97e8e-109">If a picking list journal line is created that has a reference (via the lot ID) to a production BOM line, the warehouse on the production BOM line won't be updated if the warehouse dimension on the production picking list journal line is changed later.</span></span>
