---
title: Quantidade em estoque não atualizada devido a transações insuficientes
description: A quantidade em estoque -1% não pode ser atualizada porque não há transações de estoque suficientes do item %2 com as dimensões especificadas.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 88130a969039dd741c8ea4fbaabe81acf0e6fb6a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475531"
---
# <a name="system-cant-update-inventory-quantity-because-of-insufficient-transactions"></a>O sistema não pode atualizar a quantidade em estoque devido a transações insuficientes

## <a name="symptoms"></a>Sintomas

Esse problema pode ocorrer se o sistema não puder atualizar uma quantidade de estoque porque não há transações de estoque suficientes com as dimensões especificadas. Você poderá receber a seguinte mensagem de erro:

> A quantidade de estoque -%1 não pôde ser atualizada em razão de transações de estoque insuficientes para o item %2 com dimensões de Tamanho = %3, Cor = %4, Adições = %5, Local = %6, Depósito = %7, Local = %8, Status do estoque = Disponível, Placa de licença = %9, Número do lote = %10 para a ID de referência %11 na ID de lote %12.

## <a name="resolution"></a>Resolução

Certifique-se de que nenhuma transação de estoque esteja reservando fisicamente a quantidade. Por exemplo, essas transações podem abrir ordens de qualidade, registros de bloqueio de estoque ou ordens de saída.
