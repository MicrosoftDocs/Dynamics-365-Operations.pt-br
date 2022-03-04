---
title: Não é possível criar uma linha de carga devido a dimensões de estoque inválidas
description: Ao tentar liberar uma ordem de venda de devolução para o depósito, você poderá receber um erro sobre dimensões de estoque inválidas. Remova-as da linha da ordem.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: b02408b61b07b272a7e7d52004dc2492d60ef28c
ms.sourcegitcommit: 0d14c4a1e6cf533dd20463f1a84eae8f6d88f71b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2022
ms.locfileid: "8119203"
---
# <a name="cant-create-load-line-for-return-sales-order-due-to-invalid-inventory-dimensions"></a>Não é possível criar linha de carga para Ordem de venda de devolução devido a dimensões de estoque inválidas

## <a name="symptoms"></a>Sintomas

Ao tentar liberar uma ordem de venda de devolução para o depósito, talvez você receba a seguinte mensagem de erro:

> Não é possível criar uma linha de carga para esta linha da ordem porque ela contém dimensões de estoque que são inválidas. Você não pode fazer referência às dimensões de estoque localizadas abaixo da dimensão do local na hierarquia de reserva. Remova as dimensões inválidas da linha da ordem.

## <a name="resolution"></a>Resolução

Infelizmente, o produto não oferece suporte ao processamento de carga para um processo de devolução de venda. Portanto, você não pode liberar a ordem de venda de devolução para o depósito.

Em transações de ordens de venda, você não pode fazer referência a dimensões de estoque localizadas abaixo da dimensão do **local** na hierarquia de reserva. A resolução consiste em remover as dimensões inválidas da linha da ordem.
