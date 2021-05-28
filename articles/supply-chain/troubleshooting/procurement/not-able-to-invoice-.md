---
title: Você não pode faturar um pedido de vendas voltado para o cliente
description: Você não pode mais faturar o pedido de vendas original e o pedido de compra com entrega direta original após habilitar a opção Postar fatura automaticamente.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: SalesEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ab18a2a1dec4b70c55a55637b087c6b11023aa40
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026265"
---
# <a name="you-cant-invoice-a-customer-facing-sales-order"></a><span data-ttu-id="b0db1-103">Você não pode faturar um pedido de vendas voltado para o cliente</span><span class="sxs-lookup"><span data-stu-id="b0db1-103">You can't invoice a customer-facing sales order</span></span>

<span data-ttu-id="b0db1-104">Número da base de dados de conhecimento: 4611793</span><span class="sxs-lookup"><span data-stu-id="b0db1-104">KB number: 4611793</span></span>

## <a name="symptoms"></a><span data-ttu-id="b0db1-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="b0db1-105">Symptoms</span></span>

<span data-ttu-id="b0db1-106">Você não pode mais faturar o pedido de vendas original e o pedido de compra com entrega direta original após habilitar a opção **Postar fatura automaticamente** na página **Entre empresas** para um fornecedor.</span><span class="sxs-lookup"><span data-stu-id="b0db1-106">You can no longer invoice the original sales order and the original direct delivery purchase order after you enable the **Post invoice automatically** option on the **Intercompany** page for a vendor.</span></span>

## <a name="resolution"></a><span data-ttu-id="b0db1-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="b0db1-107">Resolution</span></span>

<span data-ttu-id="b0db1-108">O comportamento de sincronização entre empresas e para faturas de pedidos com entrega é controlado e forçado pelos parâmetros descritos em [Configurar parâmetros para postar um pedido entre empresas](/dynamicsax-2012/appuser-itpro/set-up-parameters-to-post-an-intercompany-order).</span><span class="sxs-lookup"><span data-stu-id="b0db1-108">The synchronization behavior for intercompany and direct delivery order invoices is controlled and forced by the parameters that are described in [Set up parameters to post an intercompany order](/dynamicsax-2012/appuser-itpro/set-up-parameters-to-post-an-intercompany-order).</span></span>

<span data-ttu-id="b0db1-109">Após definir esses parâmetros, você deve faturar o pedido de vendas entre empresas primeiro.</span><span class="sxs-lookup"><span data-stu-id="b0db1-109">After you set those parameters, you must invoice the intercompany sales order first.</span></span> <span data-ttu-id="b0db1-110">Os pedidos de vendas e pedidos de compra originais serão sincronizados.</span><span class="sxs-lookup"><span data-stu-id="b0db1-110">The original sales orders and purchase orders will then be synchronized.</span></span>
