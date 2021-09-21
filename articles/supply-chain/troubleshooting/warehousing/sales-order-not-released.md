---
title: A ordem de venda não pôde ser liberada com operações de depósito de saída
description: Há vários motivos pelos quais você pode receber uma mensagem de erro informando que uma ordem de venda não pôde ser liberada. Esta página explica por que e como corrigir o problema.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: fca5ee1bc97545ea4de56d940fdedd320a6cfe84
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475595"
---
# <a name="sales-order-could-not-be-released-with-outbound-warehouse-operations"></a>A ordem de venda não pôde ser liberada com operações de depósito de saída

## <a name="symptoms"></a>Sintomas

Ao trabalhar com operações de depósito de saída, talvez seja exibida a seguinte mensagem de erro:

> Não foi possível liberar a ordem de venda.

## <a name="cause"></a>Causa

Esse problema pode ocorrer por vários motivos. Por exemplo, a ordem está em espera de gerenciamento de crédito e nenhuma remessa pode ser criada até que um endereço postal válido seja inserido para todas as linhas de vendas associadas a uma ordem. Como alternativa, há um bloqueio de ordem que deve ser resolvido antes que a ordem possa ser liberada para o depósito. Esse bloqueio pode ser específico da ordem ou pode ocorrer na conta do cliente.

## <a name="resolution"></a>Resolução

Adicione ou atualize o endereço na ordem de venda e nas linhas de ordem e, depois, libere a ordem para o depósito. As ordens podem ser liberadas para o depósito somente se elas tiverem um endereço de entrega válido (de acordo com a configuração do formato de endereço no módulo **Administração da organização**).

Investigue o bloqueio da ordem e resolva os problemas. Depois, remova o bloqueio da ordem ou do cliente e libere a ordem no depósito.
