---
title: Grupos de crédito de cliente
description: Este tópico fornece informações sobre grupos de crédito de cliente.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: f7121b78f3318bae9f82b2f0f951bc7bfe6c4358
ms.sourcegitcommit: 6a70f9ac296158edd065d52a12703b3ce85ce5ee
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3015116"
---
# <a name="customer-credit-groups"></a>Grupos de crédito de cliente

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Você pode definir grupos de clientes que têm o mesmo limite de crédito. O limite de crédito individual definido na conta de fatura de cliente também é considerado.

É possível selecionar membros de um grupo de crédito de cliente de diferentes entidades legais. Quando você adiciona um cliente à lista de clientes no grupo de crédito de cliente, a data de vencimento do limite de crédito de cada cliente é alterada para a data de vencimento atribuída ao grupo.

Você pode configurar grupos de crédito de cliente na página **Grupos de crédito de cliente** (**Gerenciamento de crédito \> Grupos de crédito de cliente \> Grupos de crédito de cliente**).

1. Nos campos **Número do grupo** e **Descrição**, insira um identificador e uma descrição para o grupo.
2. Nos campos **Limite de crédito** e **Moeda**, insira o limite de crédito e a moeda que deverão ser usados quando o sistema verificar o limite de crédito de qualquer membro do grupo.
3. No campo **Limite de crédito até a data**, insira a data em que vence o limite de crédito. Os grupos de crédito de cliente devem ter uma data de vencimento.

Depois de concluir a configuração de um grupo de crédito de cliente, você poderá adicionar clientes especificando a entidade legal e a ID de conta de cliente deles. Ao adicionar um novo cliente a um grupo de crédito de cliente, o sistema procura a mesma conta de cliente em todas as entidades legais e solicita que você a adicione ao grupo de crédito de cliente.

Use o menu **Saldos antigos** para ver os detalhes do saldo antigo de todos os clientes da fatura em um grupo de crédito de cliente. A página **Saldo antigo** mostra um resumo dos saldos antigos das contas de cliente da fatura.
