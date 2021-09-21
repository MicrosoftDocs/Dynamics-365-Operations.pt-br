---
title: Erro no cálculo de custos de fluxo inverso durante o fechamento do estoque
description: Em versões anteriores, talvez você tenha recebido um erro de cálculo de custos de fluxo inverso durante o fechamento do estoque. Esse problema foi corrigido.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ae92b7121998d6b1ba2f08ea5736c55637867fbf
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475565"
---
# <a name="backflush-costing-calculation-error-during-inventory-closing"></a>Erro no cálculo de custos de fluxo inverso durante o fechamento do estoque

## <a name="symptoms"></a>Sintomas

Em versões anteriores à versão 10.0.13, se você não estiver usando o fluxo de custo de produção de lean receberá a seguinte mensagem de aviso incorreta durante o fechamento de estoque:

> Você está prestes a executar um fechamento de estoque com uma data %1. Nenhuma execução de custos de fluxo inverso com uma data %1 que corresponde ao fim do período foi registrada. Lembre-se de executar um cálculo de custos de fluxo inverso com uma data de %1 que corresponda ao final do período. A avaliação de estoques, custo dos produtos vendidos e variações pode não estar correta no Razão auxiliar ou na Contabilidade até que isso seja executado.

## <a name="resolution"></a>Resolução

Esse problema foi corrigido na versão 10.0.13 ou posterior. Para obter mais informações, consulte [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296).
