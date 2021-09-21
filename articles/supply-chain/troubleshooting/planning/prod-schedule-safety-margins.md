---
title: O agendamento de produção não considera as margens de segurança
description: A programação da produção não considera as margens de segurança definidas na cobertura do item para fornecimento vinculado
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
ms.openlocfilehash: 738296b7570ded0a4ee806e4445204a68e6a08c8
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475559"
---
# <a name="production-scheduling-doesnt-consider-the-safety-margins"></a>O agendamento de produção não considera as margens de segurança

## <a name="symptoms"></a>Sintomas

O planejamento mestre considera as margens de segurança. Contudo, as margens de segurança são ignoradas quando as ordens de produção planejadas são programadas.

## <a name="resolution"></a>Resolução

As margens são consideradas somente durante o planejamento mestre, não durante a programação manual. As margens são projetadas para atuar como um buffer durante a fase de planejamento, para dar alguma "margem" para o processo real.

Para obter o resultado desejado, você pode remover a margem. A rota deve ser atualizada para incluir o tempo desejado (por exemplo, como tempo de fila). O planejamento mestre e a programação manual devem produzir o mesmo resultado.
