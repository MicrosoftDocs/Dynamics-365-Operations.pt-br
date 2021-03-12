---
title: Solucionar problemas de fabricação de processo
description: Este tópico descreve como corrigir problemas que podem ocorrer durante o trabalho com fabricação de processos.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d999c91aa1cc14f29ebfa6be8e456e45ef0d3fa4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966171"
---
# <a name="troubleshoot-process-manufacturing"></a>Solucionar problemas de fabricação de processo

Este tópico descreve como corrigir problemas que podem ocorrer durante o trabalho com fabricação de processos.

## <a name="when-i-use-the-job-card-device-to-report-a-partial-quantity-on-the-last-job-in-a-production-order-all-the-previous-jobs-on-that-order-that-have-a-status-of-in-progress-are-automatically-ended"></a>Quando eu uso o dispositivo de ficha de trabalho para relatar uma quantidade parcial do último trabalho em uma ordem de produção, todos os trabalhos anteriores nessa ordem com status Em andamento são encerrados automaticamente.

Esse comportamento é por design. Na página **Padrões de ordem de produção**, na guia **Relatar como concluído**, há uma opção chamada **Marcar fim de roteiro**. Se este tópico for definido como *Sim*, um diário de cartão de rota será lançado quando um trabalhador usar o dispositivo de cartão de trabalho ou terminal de cartão de trabalho para relatar a operação mais recente. Esse diário marca todas as operações como concluídas e encerra todos os trabalhos de produção. Quando a opção **Marcar fim de roteiro** é definida como *Sim*, o sistema não considera o status do trabalho que o trabalhador selecionou quando relatou a operação mais recente. O sistema também não considera se o trabalhador está relatando uma quantidade total ou parcial.

## <a name="when-i-attempt-a-stock-closing-i-receive-the-following-warning-message-no-execution-of-backflush-costing-calculation-with-a-date-1-matching-period-end-has-been-registered"></a>Quando tento um fechamento de estoque, recebo a seguinte mensagem de aviso: "Nenhuma execução de cálculo de custos de fluxo inverso com uma data %1 que corresponde ao final do período foi registrada."

Em versões anteriores à versão 10.0.13, se você não estiver usando o fluxo de custo de produção de lean receberá a seguinte mensagem de aviso incorreta durante o fechamento de estoque:

> Você está prestes a executar um fechamento de estoque com uma data %1. Nenhuma execução de custos de fluxo inverso com uma data %1 que corresponde ao fim do período foi registrada. Lembre-se de executar um cálculo de custos de fluxo inverso com uma data de %1 que corresponda ao final do período. A avaliação de estoques, custo dos produtos vendidos e variações podem não estar corretos no razão auxiliar ou na contabilidade até que seja executado.

Esse problema foi corrigido na versão 10.0.13 ou posterior. Para obter mais informações, consulte [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296).
