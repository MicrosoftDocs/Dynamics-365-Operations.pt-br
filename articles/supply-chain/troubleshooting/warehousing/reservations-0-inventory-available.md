---
title: Não é possível fazer reservas de estoque porque há 0,00 disponível
description: Você recebe um erro dizendo que o sistema não pode fazer reservas porque há somente 0,00 disponível no estoque. Esse problema é provavelmente causado por um trabalho aberto.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 75d72f7ee1bdecca5a087b75b1de9907b9d244ab
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475611"
---
# <a name="system-cant-make-reservations-because-000-are-available-in-the-inventory"></a>O sistema não pode fazer reservas porque a disponibilidade de estoque é 0,00

## <a name="symptoms"></a>Sintomas

Esse problema pode ocorrer se o sistema não puder atualizar uma quantidade de estoque porque não há transações de estoque suficientes com as dimensões especificadas. Você poderá receber a seguinte mensagem de erro:

> Físico disponível Local = %1, Depósito = %2, Status do estoque = Disponível, Nº do lote = %3, Proprietário = %4: %5 não pode ser reservado porque somente 0,00 está disponível no estoque.

## <a name="resolution"></a>Resolução

Esse problema é provavelmente causado por um trabalho aberto. Conclua a obra ou receba sem criação de trabalho. Certifique-se de que nenhuma transação de estoque esteja reservando fisicamente a quantidade. Por exemplo, essas transações podem abrir ordens de qualidade, registros de bloqueio de estoque ou ordens de saída.
