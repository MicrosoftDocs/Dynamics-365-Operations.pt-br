---
title: O trabalho de limpeza do histórico de atualização de vendas falha ou tem problemas de desempenho
description: O trabalho em lotes Limpeza do histórico de vendas poderá falhar ou levar muito tempo se houver uma grande quantidade de dados de atualização de vendas.
author: myvakalo
ms.date: 10/05/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-09-29
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: c02273adf90afc67b7c0ae1b82c19d489bfbd3b1
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920065"
---
# <a name="sales-update-history-cleanup-job-fails-or-has-performance-issues"></a>O trabalho de limpeza do histórico de atualização de vendas falha ou tem problemas de desempenho

## <a name="symptoms"></a>Sintomas

O trabalho em lote **Limpeza do histórico de atualização de vendas** falha ou tem problemas de desempenho.  

## <a name="cause"></a>Causa

Isso pode ocorrer quando o sistema inclui um grande número de atualizações de vendas, o que pode resultar em uma grande quantidade de dados de atualização de vendas. O trabalho de limpeza tenta limpar todos os dados em uma transação. Como resultado, o trabalho pode levar muito tempo para ser executado ou até mesmo falhar.

## <a name="resolution"></a>Resolução

Uma nova versão do trabalho em lote **Limpeza do histórico de atualização de vendas** está disponível para o Supply Chain Management versão 10.0.19 e posterior. Este recurso não está habilitado por padrão. Para obter detalhes sobre como ele funciona e como habilitá-lo no gerenciamento de recursos, consulte [Melhorias no desempenho da limpeza do histórico de vendas](../../sales-marketing/sales-update-history-cleanup-performance-improvements.md).

