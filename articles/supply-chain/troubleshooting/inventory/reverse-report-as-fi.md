---
title: Reversão de relatório como finalizado cria uma transação em aberto inesperada
description: A reversão do relatório como finalizado que tem uma marcação cria uma transação em aberto em que a quantidade revertida tem as mesmas dimensões de inventário que a transação revertida.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ea9044a9008e766c7fc92f98e27cfb91076f5b44
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026281"
---
# <a name="reversal-of-reporting-as-finished-creates-an-unexpected-open-transaction"></a><span data-ttu-id="662c5-103">Reversão de relatório como finalizado cria uma transação em aberto inesperada</span><span class="sxs-lookup"><span data-stu-id="662c5-103">Reversal of reporting as finished creates an unexpected open transaction</span></span>

<span data-ttu-id="662c5-104">Número da base de dados de conhecimento: 4612469</span><span class="sxs-lookup"><span data-stu-id="662c5-104">KB number: 4612469</span></span>

## <a name="symptoms"></a><span data-ttu-id="662c5-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="662c5-105">Symptoms</span></span>

<span data-ttu-id="662c5-106">Se você reverter o relatório como finalizado que tem uma marcação, o sistema criará uma transação em aberto em que a quantidade revertida tem as mesmas dimensões de inventário que a transação que foi revertida.</span><span class="sxs-lookup"><span data-stu-id="662c5-106">If you reverse reporting as finished that has marking, the system creates an open transaction where the reversed quantity has the same inventory dimensions as the transaction that was reversed.</span></span>

## <a name="resolution"></a><span data-ttu-id="662c5-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="662c5-107">Resolution</span></span>

<span data-ttu-id="662c5-108">Quando você reverter uma operação relatar-como-finalizado, a dimensão do inventário é inicializada no diário de produção.</span><span class="sxs-lookup"><span data-stu-id="662c5-108">When you reverse a report-as-finished operation, the inventory dimension is initialized from the production journal.</span></span> <span data-ttu-id="662c5-109">Portanto, ela obtém o número do lote.</span><span class="sxs-lookup"><span data-stu-id="662c5-109">Therefore, it gets the batch number.</span></span> <span data-ttu-id="662c5-110">Por conta da marcação, as transações de pedido de venda herdará o número de lote.</span><span class="sxs-lookup"><span data-stu-id="662c5-110">Because of marking, the sales order transactions will inherit the batch number.</span></span>

<span data-ttu-id="662c5-111">A dimensão pode ser redefinida quando o relatório como finalizado é postado.</span><span class="sxs-lookup"><span data-stu-id="662c5-111">The dimension can be reset when the reporting as finished is posted.</span></span>
