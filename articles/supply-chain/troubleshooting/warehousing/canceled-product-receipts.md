---
title: Os recibos de produtos cancelados não atualizam o status da transação para Registrado
description: Depois de cancelar os recibos do produto em uma carga de entrada, o sistema atualiza automaticamente o status da transação de estoque de Recebido para Encomendado.
author: GalynaFedorova
ms.date: 06/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 9c86457d50a7a9ac2a699a0e0a9c7bdf4cd7c67b
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294009"
---
# <a name="canceled-product-receipts-dont-update-transaction-status-to-registered"></a><span data-ttu-id="288c7-103">Os recibos de produtos cancelados não atualizam o status da transação para Registrado</span><span class="sxs-lookup"><span data-stu-id="288c7-103">Canceled product receipts don't update transaction status to Registered</span></span>

## <a name="symptoms"></a><span data-ttu-id="288c7-104">Sintomas</span><span class="sxs-lookup"><span data-stu-id="288c7-104">Symptoms</span></span>

<span data-ttu-id="288c7-105">Depois de executar a ação **Cancelar recibos do produto** em uma carga de entrada, o sistema atualiza automaticamente o status das transações de estoque de *Recebido* para *Encomendado*.</span><span class="sxs-lookup"><span data-stu-id="288c7-105">After you run the **Cancel product receipts** action on an inbound load, the system automatically updates the status of inventory transactions from *Received* to *Ordered*.</span></span>

## <a name="resolution"></a><span data-ttu-id="288c7-106">Resolução</span><span class="sxs-lookup"><span data-stu-id="288c7-106">Resolution</span></span>

<span data-ttu-id="288c7-107">Quando as guias de remessa são cancelados para cargas de saída, o status das transações de estoque permanece *Separado*.</span><span class="sxs-lookup"><span data-stu-id="288c7-107">When packing slips are canceled for outbound loads, the status of inventory transactions remains *Picked*.</span></span> <span data-ttu-id="288c7-108">No entanto, quando os recibos do produto de uma carga de entrada são cancelados, o status das transações de estoque não é restaurado para *Registrado*.</span><span class="sxs-lookup"><span data-stu-id="288c7-108">However, when product receipts from an inbound load are canceled, the status of inventory transactions isn't restored to *Registered*.</span></span> <span data-ttu-id="288c7-109">Portanto, depois que um recibo do produto de uma carga de entrada for cancelado, o funcionário do depósito deve recadastrar as quantidades de itens para as cargas.</span><span class="sxs-lookup"><span data-stu-id="288c7-109">Therefore, after a product receipt from an inbound load is canceled, the warehouse worker must re-register item quantities for the loads.</span></span>

<span data-ttu-id="288c7-110">Para obter mais informações, consulte [Registrar quantidades de itens que chegam em uma carga de entrada](/dynamics365/supply-chain/warehousing/inbound-load-handling#register-item-quantities-arriving).</span><span class="sxs-lookup"><span data-stu-id="288c7-110">For more information, see [Register item quantities that arrive on an inbound load](/dynamics365/supply-chain/warehousing/inbound-load-handling#register-item-quantities-arriving).</span></span>
