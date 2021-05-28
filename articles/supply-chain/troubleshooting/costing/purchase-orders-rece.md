---
title: Os pedidos de compra recebidos fisicamente não aparecem no relatório de fechamento de inventário
description: Os pedidos de compra recebidos fisicamente não aparecem no relatório de fechamento de inventário Verificar quantidades em aberto.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventOpenQtyCritical
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 9508d6d75d8ebee7ca10140ed4c4215d7ad1dda7
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026269"
---
# <a name="physically-received-purchase-orders-dont-appear-on-the-inventory-closing-report"></a><span data-ttu-id="9f67a-103">Os pedidos de compra recebidos fisicamente não aparecem no relatório de fechamento de inventário</span><span class="sxs-lookup"><span data-stu-id="9f67a-103">Physically received purchase orders don't appear on the inventory closing report</span></span>

<span data-ttu-id="9f67a-104">Número da base de dados de conhecimento: 4612595</span><span class="sxs-lookup"><span data-stu-id="9f67a-104">KB number: 4612595</span></span>

## <a name="symptoms"></a><span data-ttu-id="9f67a-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="9f67a-105">Symptoms</span></span>

<span data-ttu-id="9f67a-106">Os pedidos de compra recebidos fisicamente não aparecem no relatório de fechamento de inventário **Verificar quantidades em aberto**.</span><span class="sxs-lookup"><span data-stu-id="9f67a-106">Physically received purchase orders don't appear on the **Check open quantities** inventory closing report.</span></span>

## <a name="resolution"></a><span data-ttu-id="9f67a-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="9f67a-107">Resolution</span></span>

<span data-ttu-id="9f67a-108">O relatório **Verificar quantidades em aberto** mostra transações emitidas que não podem ser liquidadas com base nos recebimentos de inventário atualizados financeiramente a partir da data de fechamento selecionada.</span><span class="sxs-lookup"><span data-stu-id="9f67a-108">The **Check open quantities** report shows issue transactions that can't be settled against financially updated inventory receipts as of the selected closing date.</span></span> <span data-ttu-id="9f67a-109">Você pode incluir recibos físicos no relatório.</span><span class="sxs-lookup"><span data-stu-id="9f67a-109">You can choose to include physical receipts on the report.</span></span> <span data-ttu-id="9f67a-110">Nesse caso, os recibos físicos serão mostrados se puderem cobrir as transações emitidas que não podem ser liquidadas.</span><span class="sxs-lookup"><span data-stu-id="9f67a-110">In that case, physical receipts will be shown if they can cover the issue transactions that can't be settled.</span></span> <span data-ttu-id="9f67a-111">Para mais informações, consulte [Preparar para realizar fechamento de inventário](/dynamicsax-2012/appuser-itpro/preparing-to-run-inventory-close).</span><span class="sxs-lookup"><span data-stu-id="9f67a-111">For more information, see [Preparing to run inventory close](/dynamicsax-2012/appuser-itpro/preparing-to-run-inventory-close).</span></span>
