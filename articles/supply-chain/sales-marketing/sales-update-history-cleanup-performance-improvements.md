---
title: Melhorias no desempenho de limpeza do histórico de vendas
description: Este tópico descreve o recurso de aperfeiçoamentos de desempenho da limpeza de vendas e como habilitá-lo.
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
ms.openlocfilehash: 1b2de9d6a7b1b7793b6bb753dd580d052d3c2841
ms.sourcegitcommit: 96515ddbe2f65905140b16088ba62e9b258863fa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2021
ms.locfileid: "7891759"
---
# <a name="saleshistorycleanupperformanceimprovements"></a>Melhorias no desempenho de limpeza do histórico de vendas

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.24 -->

O trabalho em lote periódico **Limpeza do histórico de vendas** pode demorar muito se for executada com pouca frequência em ambientes com um alto volume de atualizações de vendas. Nessas situações, o recurso *Aperfeiçoamentos de desempenho da limpeza de vendas* pode ajudar a reduzir a duração da execução e melhorar a confiabilidade.

O recurso melhora o trabalho de limpeza atual das seguintes maneiras:

- Ele divide a limpeza em lotes (você pode alterar o tamanho do lote por meio das personalizações).
- Ela será executada por um máximo de 2 horas (você pode alterar a duração por meio das personalizações).
- Sempre que possível, a limpeza utiliza os recursos do banco de dados para minimizar o bloqueio e evitar a junção de tabelas transacionais durante a limpeza.

Depois de habilitar o recurso, o trabalho em lotes **Limpeza do histórico de atualizações de vendas** (**Vendas e marketing \> Tarefas periódicas de \> Limpeza \> Limpeza do histórico de atualizações de vendas**) será executado como de costume, mas com melhor desempenho e por um máximo de 2 horas. Isso significa que talvez seja necessário executar várias vezes para limpar todos os dados de um período de retenção específico.

## <a name="turn-on-the-saleshistorycleanupperformanceimprovements-feature"></a>Ativar o recurso de melhorias no desempenho de limpeza do histórico de vendas

Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Vendas e marketing*
- **Nome do recurso:** *melhorias no desempenho de limpeza do histórico de vendas*
