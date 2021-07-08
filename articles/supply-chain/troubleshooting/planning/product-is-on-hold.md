---
title: O produto está em espera para transações
description: Depois de firmar ordens de planejamento, você recebe uma mensagem de erro que afirma que um item está em espera para transações.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6654e6437a088218db116b955631be4c7e62de5f
ms.sourcegitcommit: f9b145ef4a81cec81f420871b4130b05db4f4500
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301270"
---
# <a name="product-is-on-hold-for-transactions"></a>O produto está em espera para transações

Código de erro: SYS13295

## <a name="symptoms"></a>Sintomas

Depois de firmar ordens planejadas, você recebe a seguinte mensagem de erro:

> O item %1 está retido para transações em %2.

## <a name="cause"></a>Causa

Ao descrever os itens bloqueados, o sistema usa os termos *bloqueados*, *interrompidos* e *em espera* de forma alternada. Esse erro significa que o item está definido como **Interrompido** em suas configurações de ordem padrão.

Se um item estiver bloqueado e você o adicionar a uma linha de ordem de compra ou de venda, você receberá uma mensagem de aviso. Quando o item está bloqueado, não é possível modificar as transações de estoque que estão relacionadas à linha da ordem de compra ou de venda, por exemplo, quando você lança uma guia de remessa ou uma fatura. Você pode bloquear um item comprado e, ao mesmo tempo, vendê-lo. Nesse caso, a caixa de seleção **Interrompido** marcada em uma ordem de compra, mas o item não é bloqueado no estoque ou em uma ordem de venda.

Aqui estão algumas das condições que podem fazer com que um número de item seja impedido de ser vendido:

- O item ainda está em desenvolvimento ou fabricação. Portanto, você não quer que ele seja vendido ou reservado.
- Você recebeu muitos itens defeituosos, e os defeitos devem ser corrigidos antes que o item possa ser vendido.

Em casos assim, você pode bloquear o item até que o problema seja resolvido.

Se um item estiver bloqueado e você criar uma linha de ordem de devolução, você receberá uma mensagem. Não é possível bloquear uma série ou um lote do item. Se partes do item tiverem de ser bloqueadas, você poderá bloqueá-las movendo o estoque ou bloqueando o estoque inteiro do item durante aquele período.

## <a name="resolution"></a>Resolução

- Abra a página **Configurações de ordem padrão** para o item e desmarque a caixa de seleção **Interrompido**.
