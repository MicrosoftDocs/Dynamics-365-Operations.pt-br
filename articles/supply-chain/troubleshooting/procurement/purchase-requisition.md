---
title: Não é possível adicionar uma linha a uma requisição de compra após solicitar uma alteração
description: O sistema não permite a você adicionar uma linha a uma requisição de compra após solicitar uma alteração.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PurchReqTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: jeyao
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 5dbb55a6a352a7acf16729c1cfe1afdac2e2eef8
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026274"
---
# <a name="you-cant-add-a-line-to-a-purchase-requisition-after-you-request-a-change"></a><span data-ttu-id="1e896-103">Não é possível adicionar uma linha a uma requisição de compra após solicitar uma alteração</span><span class="sxs-lookup"><span data-stu-id="1e896-103">You can't add a line to a purchase requisition after you request a change</span></span>

<span data-ttu-id="1e896-104">Número da base de dados de conhecimento: 4611211</span><span class="sxs-lookup"><span data-stu-id="1e896-104">KB number: 4611211</span></span>

## <a name="symptoms"></a><span data-ttu-id="1e896-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="1e896-105">Symptoms</span></span>

<span data-ttu-id="1e896-106">O sistema não permite a você adicionar uma linha a uma requisição de compra após solicitar uma alteração.</span><span class="sxs-lookup"><span data-stu-id="1e896-106">The system doesn't allow you to add a line to a purchase requisition after you request a change.</span></span>

## <a name="resolution"></a><span data-ttu-id="1e896-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="1e896-107">Resolution</span></span>

<span data-ttu-id="1e896-108">Você deve chamar o fluxo de trabalho novamente.</span><span class="sxs-lookup"><span data-stu-id="1e896-108">You must recall the workflow.</span></span> <span data-ttu-id="1e896-109">Quando a requisição de compra estiver no status *Rascunho*, você pode continuar editando ou adicionar uma linha a ela.</span><span class="sxs-lookup"><span data-stu-id="1e896-109">After the purchase requisition is in *Draft* status, you can continue to edit it or add a line to it.</span></span>
