---
title: Uma das linhas já está em uma carga
description: Esta página explica porque você pode ter recebido o erro "Uma das linhas já está em uma carga. Não foi possível liberar para o depósito" e como resolver o problema.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0bdfaed005b9c58f7bd5f87dd6dffe648de47261
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475630"
---
# <a name="one-of-the-lines-is-already-on-a-load"></a>Uma das linhas já está em uma carga

## <a name="symptoms"></a>Sintomas

Ao trabalhar com a criação de carga e remessas, você pode receber a seguinte mensagem de erro:

> Uma das linhas já está em uma carga. Não foi possível liberar para o depósito.

Se você criar cargas manualmente ou configurar o processo de forma que as cargas já sejam criadas antes que a entrada da linha da ordem de vendas ocorra, a suposição é que a liberação subsequente será feita manualmente e que a rota e a classificação da carga serão usadas.

Em outro cenário possível, você está tentando fazer uma liberação automática para o depósito, mas houve falha no processo de ciclo durante a criação do trabalho. Portanto, uma remessa ou carga aberta ainda será criada. Essa remessa ou carga aberta bloqueia as tentativas subsequentes de liberar automaticamente a ordem até que você exclua a remessa ou carga aberta ou reprocesse manualmente o ciclo.

## <a name="resolution"></a>Resolução

É possível liberar na página de ordem de venda, ou uma liberação automática pode ser feita na página de liberação de ordem de venda, somente se não houver carga antes da liberação para o depósito. A carga será criada automaticamente após o processamento da onda.
