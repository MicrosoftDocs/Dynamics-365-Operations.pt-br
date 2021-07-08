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
# <a name="canceled-product-receipts-dont-update-transaction-status-to-registered"></a>Os recibos de produtos cancelados não atualizam o status da transação para Registrado

## <a name="symptoms"></a>Sintomas

Depois de executar a ação **Cancelar recibos do produto** em uma carga de entrada, o sistema atualiza automaticamente o status das transações de estoque de *Recebido* para *Encomendado*.

## <a name="resolution"></a>Resolução

Quando as guias de remessa são cancelados para cargas de saída, o status das transações de estoque permanece *Separado*. No entanto, quando os recibos do produto de uma carga de entrada são cancelados, o status das transações de estoque não é restaurado para *Registrado*. Portanto, depois que um recibo do produto de uma carga de entrada for cancelado, o funcionário do depósito deve recadastrar as quantidades de itens para as cargas.

Para obter mais informações, consulte [Registrar quantidades de itens que chegam em uma carga de entrada](/dynamics365/supply-chain/warehousing/inbound-load-handling#register-item-quantities-arriving).
