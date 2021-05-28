---
title: O relatório Custos indiretos no processo inclui pedidos de produção excluídos
description: O relatório Custos indiretos no processo apresenta informações sobre pedidos de produção que foram processados parcialmente e depois excluídos.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdIndirectCostInProgress
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 707fa9bb30129c3656e10c6756dee770a7712e65
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026270"
---
# <a name="the-indirect-costs-in-process-report-includes-deleted-production-orders"></a><span data-ttu-id="fb8ac-103">O relatório Custos indiretos no processo inclui pedidos de produção excluídos</span><span class="sxs-lookup"><span data-stu-id="fb8ac-103">The Indirect costs in process report includes deleted production orders</span></span>

<span data-ttu-id="fb8ac-104">Número da base de dados de conhecimento: 4612748</span><span class="sxs-lookup"><span data-stu-id="fb8ac-104">KB number: 4612748</span></span>

## <a name="symptoms"></a><span data-ttu-id="fb8ac-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="fb8ac-105">Symptoms</span></span>

<span data-ttu-id="fb8ac-106">O relatório **Custos indiretos no processo** apresenta informações sobre pedidos de produção que foram processados parcialmente e depois excluídos.</span><span class="sxs-lookup"><span data-stu-id="fb8ac-106">The **Indirect costs in process** report presents information about production orders that were partially processed and later deleted.</span></span>

## <a name="resolution"></a><span data-ttu-id="fb8ac-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="fb8ac-107">Resolution</span></span>

<span data-ttu-id="fb8ac-108">Quando você reverte um pedido de produção, você também reverte todas as transações desse pedido de produção.</span><span class="sxs-lookup"><span data-stu-id="fb8ac-108">When you reverse a production order, you also reverse all the transactions of that production order.</span></span> <span data-ttu-id="fb8ac-109">Ao excluir o pedido de produção, as tabelas do razão auxiliar e do razão geral persistem em todas as transações relacionadas a ele.</span><span class="sxs-lookup"><span data-stu-id="fb8ac-109">When you delete the production order, the subledger tables and general ledger persist all transactions that are related to it.</span></span> <span data-ttu-id="fb8ac-110">Os relatórios mostrarão as transações nas tabelas do razão auxiliar.</span><span class="sxs-lookup"><span data-stu-id="fb8ac-110">The reports will show the transactions in the subledger tables.</span></span> <span data-ttu-id="fb8ac-111">Para o pedido de produção específico, o valor líquido deve ser 0,00.</span><span class="sxs-lookup"><span data-stu-id="fb8ac-111">For the specific production order, the net value should be 0.00.</span></span>
