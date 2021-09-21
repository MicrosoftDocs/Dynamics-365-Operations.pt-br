---
title: As ordens planejadas demoram muito para serem atualizadas
description: Ao atualizar a quantidade necessária e/ou data de entrega em uma ordem planejada, normalmente leva pelo menos 30 segundos por ordem para salvar a atualização
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: ccf3305cc18ea0ccf2ac3e9ca0dd507fd12a9da7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475593"
---
# <a name="planned-orders-take-a-long-time-to-update"></a>As ordens planejadas demoram muito para serem atualizadas

## <a name="symptoms"></a>Sintomas

Ao atualizar a quantidade necessária e/ou data de entrega em uma ordem planejada, normalmente leva pelo menos 30 segundos por ordem para salvar a atualização.

## <a name="resolution"></a>Resolução

Esse é um problema conhecido com o mecanismo de planejamento mestre integrado. Ele é causado pela explosão automática subjacente por meio da estrutura da BOM durante as edições. Esse problema é abordado na Otimização de Planejamento, onde um planejador pode atualizar e aprovar os pedidos relevantes e, quando desejado, acionar uma execução de planejamento para atualizar as ordens planejadas para a estrutura de BOM subjacente.

Uma maneira de melhorar o desempenho com o mecanismo de planejamento mestre integrado é realizar as seguintes etapas:

1. Acesse **Planejamento mestre \> Configuração \> Planos \> Planos mestres**.
1. Selecione um plano.
1. Expanda a FastTab **Limite de tempo em dias**.
1. Defina **Detalhamento** como *Sim* e defina o campo abaixo dessa configuração como 0 (zero).

> [!NOTE]
> Isso limitará o período de detalhamentos realizados desse plano mestre a um único dia.
