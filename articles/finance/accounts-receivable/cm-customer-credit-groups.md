---
title: Grupos de crédito de cliente
description: Este tópico fornece informações sobre grupos de crédito de cliente.
author: JodiChristiansen
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 0815aa41b034d8ba5c9b09f4003ff3df7311190a
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735482"
---
# <a name="customer-credit-groups"></a>Grupos de crédito de cliente

[!include [banner](../includes/banner.md)]

Você pode definir grupos de clientes que têm um limite de crédito compartilhado. O limite de crédito individual definido na conta de fatura de cliente também é considerado.

É possível selecionar membros de um grupo de crédito de cliente de diferentes entidades legais. Quando você adiciona um cliente à lista de clientes no grupo de crédito de cliente, a data de vencimento do limite de crédito de cada cliente é alterada para a data de vencimento atribuída ao grupo.

Você pode configurar grupos de crédito de cliente na página **Grupos de crédito de cliente** (**Gerenciamento de crédito \> Grupos de crédito de cliente \> Grupos de crédito de cliente**).

1. Nos campos **Número do grupo** e **Descrição**, insira um identificador e uma descrição para o grupo.
2. Nos campos **Limite de crédito** e **Moeda**, insira o limite de crédito e a moeda que deverão ser usados quando o sistema verificar o limite de crédito de qualquer membro do grupo.
3. No campo **Limite de crédito até a data**, insira a data em que vence o limite de crédito. Os grupos de crédito de cliente devem ter uma data de vencimento.

Depois de concluir a configuração de um grupo de crédito de cliente, você poderá adicionar clientes especificando a entidade legal e a ID de conta de cliente deles. Ao adicionar um novo cliente a um grupo de crédito de cliente, o sistema procura a mesma conta de cliente em todas as entidades legais e solicita que você a adicione ao grupo de crédito de cliente.

Use o menu **Saldos antigos** para ver os detalhes do saldo antigo de todos os clientes da fatura em um grupo de crédito de cliente. A página **Saldo antigo** mostra um resumo dos saldos antigos das contas de cliente da fatura.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
