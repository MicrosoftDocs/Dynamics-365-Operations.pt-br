---
title: Não é possível criar uma linha de carga devido a dimensões de estoque inválidas
description: Ao tentar liberar uma ordem de venda de devolução para o depósito, você poderá receber um erro sobre dimensões de estoque inválidas. Remova-as da linha da ordem.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac58
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 3cb728f6a989cdac63c91d49baaea094bace59e4
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475596"
---
# <a name="cant-create-load-line-for-return-sales-order-due-to-invalid-inventory-dimensions"></a>Não é possível criar linha de carga para Ordem de venda de devolução devido a dimensões de estoque inválidas

## <a name="symptoms"></a>Sintomas

Ao tentar liberar uma ordem de venda de devolução para o depósito, talvez você receba a seguinte mensagem de erro:

> Não é possível criar uma linha de carga para esta linha da ordem porque ela contém dimensões de estoque que são inválidas. Você não pode fazer referência às dimensões de estoque localizadas abaixo da dimensão do local na hierarquia de reserva. Remova as dimensões inválidas da linha da ordem.

## <a name="resolution"></a>Resolução

Infelizmente, o produto não oferece suporte ao processamento de carga para um processo de devolução de venda. Portanto, você não pode liberar a ordem de venda de devolução para o depósito.

Em transações de ordens de venda, você não pode fazer referência a dimensões de estoque localizadas abaixo da dimensão do **local** na hierarquia de reserva. A resolução consiste em remover as dimensões inválidas da linha da ordem.
