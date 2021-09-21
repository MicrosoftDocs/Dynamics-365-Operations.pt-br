---
title: A tarefa de atualização de recebimento de produtos confirma ordens não confirmadas
description: Depois de executar Atualizar recebimentos de produtos, o sistema confirma ordens não confirmadas com o status Registrado. Saiba mais sobre o recurso que corrige esse problema.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 171a978efc6b55b92f429381e72036cb1b3296c6
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475545"
---
# <a name="unconfirmed-purchase-orders-are-confirmed-after-running-update-product-receipts"></a>As ordens de compra não confirmadas são confirmadas após a execução de Atualizar recebimentos de produtos

## <a name="symptoms"></a>Sintomas

Depois de executar a tarefa periódica *Atualizar recebimentos de produtos*, o sistema confirma automaticamente as ordens de compra não confirmadas com status de transação de estoque *Registrado*.

## <a name="resolution"></a>Resolução

Um novo recurso de processamento de cargas de entrada, *Recebimento a mais de quantidade de carga*, corrige esse problema. Para ativar esse recurso, acesse o espaço de trabalho [Gerenciamento de recursos](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview) e ative os seguintes recursos na ordem em que estão listados:

1. Associar transações de estoque da ordem de compra com carga
2. Recebimento a mais de quantidade de carga

Para obter mais informações, consulte [Lançar quantidades de produtos registrados nas ordens de compra](/dynamics365/supply-chain/warehousing/inbound-load-handling).
