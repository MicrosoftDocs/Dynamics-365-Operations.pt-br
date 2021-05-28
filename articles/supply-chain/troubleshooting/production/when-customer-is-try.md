---
title: O número do lote é apagado quando um novo ID do lote é selecionado
description: Quando estiver analisando uma linha do diário da lista de separação, o valor no campo "Número de lote" será apagado se você selecionar um novo valor no campo "ID do lote".
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdJournalTransBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: datra
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 71977a04adb066a8b51c9bf7b8c5a4e752ca902e
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026254"
---
# <a name="batch-number-is-cleared-when-a-new-lot-id-is-selected"></a><span data-ttu-id="b4d85-103">O número do lote é apagado quando um novo ID do lote é selecionado</span><span class="sxs-lookup"><span data-stu-id="b4d85-103">Batch number is cleared when a new lot ID is selected</span></span>

<span data-ttu-id="b4d85-104">Número de KB: 4613107</span><span class="sxs-lookup"><span data-stu-id="b4d85-104">KB number: 4613107</span></span>

## <a name="symptoms"></a><span data-ttu-id="b4d85-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="b4d85-105">Symptoms</span></span>

<span data-ttu-id="b4d85-106">Quando estiver analisando uma linha do diário da lista de separação, o valor no campo **Número de lote** será apagado se você selecionar um novo valor no campo **ID do lote**.</span><span class="sxs-lookup"><span data-stu-id="b4d85-106">When you're reviewing a picking list journal line, the value in the **Batch number** field is cleared if you select a new value in the **Lot ID** field.</span></span>

## <a name="resolution"></a><span data-ttu-id="b4d85-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="b4d85-107">Resolution</span></span>

<span data-ttu-id="b4d85-108">O sistema está agindo como esperado.</span><span class="sxs-lookup"><span data-stu-id="b4d85-108">The system is behaving as designed.</span></span> <span data-ttu-id="b4d85-109">Se você alterar o ID do lote, altere o contexto do item.</span><span class="sxs-lookup"><span data-stu-id="b4d85-109">If you change the lot ID, you change the item context.</span></span> <span data-ttu-id="b4d85-110">Assim, o número do lote será redefinido.</span><span class="sxs-lookup"><span data-stu-id="b4d85-110">Therefore, the batch number is reset.</span></span>

<span data-ttu-id="b4d85-111">Para associar o número de lote a um ID do lote, você deve definir primeiro o ID do lote.</span><span class="sxs-lookup"><span data-stu-id="b4d85-111">To associate the batch number with a lot ID, you must set the lot ID first.</span></span>
