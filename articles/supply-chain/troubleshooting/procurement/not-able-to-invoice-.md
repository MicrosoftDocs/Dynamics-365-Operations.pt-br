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
# <a name="you-cant-invoice-a-customer-facing-sales-order"></a>Você não pode faturar um pedido de vendas voltado para o cliente

Número da base de dados de conhecimento: 4611793

## <a name="symptoms"></a>Sintomas

Você não pode mais faturar o pedido de vendas original e o pedido de compra com entrega direta original após habilitar a opção **Postar fatura automaticamente** na página **Entre empresas** para um fornecedor.

## <a name="resolution"></a>Resolução

O comportamento de sincronização entre empresas e para faturas de pedidos com entrega é controlado e forçado pelos parâmetros descritos em [Configurar parâmetros para postar um pedido entre empresas](/dynamicsax-2012/appuser-itpro/set-up-parameters-to-post-an-intercompany-order).

Após definir esses parâmetros, você deve faturar o pedido de vendas entre empresas primeiro. Os pedidos de vendas e pedidos de compra originais serão sincronizados.
