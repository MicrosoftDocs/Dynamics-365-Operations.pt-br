---
title: Visão geral de Lean manufacturing
description: Este artigo fornece uma visão geral e uma descrição dos recursos de lean manufacturing no Dynamics 365 Supply Chain Management.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardTransferJob, KanbanBoardWorkCell, KanbanJobSchedulingListPage, LeanProductionFlow, Kanban, KanbanQuantityOverview, KanbanAssignCard, KanbanCirculatingCards, KanbanRules, WHSKanbanWaveTableManagePickingListPool
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "19371"
- intro-internal
ms.assetid: 026c5605-6be7-4fdb-a6f2-8e37a806796c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9c58d00d04c1e34e179d0a94485a86779f7f686e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579367"
---
# <a name="lean-manufacturing-overview"></a>​Visão geral de lean manufacturing​

[!include [banner](../includes/banner.md)]

Este artigo fornece uma visão geral e uma descrição dos recursos de lean manufacturing no Dynamics 365 Supply Chain Management.

O lean manufacturing oferece ferramentas que você pode usar para modelar as operações lean. Essas ferramentas dão suporte e promovem os conceitos e atividades de negócio a seguir:
-   Criar um fundamento te lean manufacturing modelando a fabricação e os processos logísticos de acordo com o fluxo da produção.
-   Implementar um sistema lean de remessa usando kanban para sinalizar requisitos de demanda.
-   Monitore e mantenha trabalhos kanban.

A arquitetura de lean manufacturing consiste em fluxos de produção, atividades e regras kanban. Essas estruturas são totalmente integradas aos processos do Supply Chain Management. Você pode usar o lean manufacturing em um ambiente de fabricação de modo misto que combina várias estratégias de fontes, produção e de fornecimento. Essas estratégias incluem ordens de produção, ordens de lote para indústrias de processamento, ordens de compra e de transferência.

| **Importante**                                                                                                                                                                                                                                                                |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Você pode usar o Supply Chain Management para oferecer suporte à implementação de lean manufacturing com kanbans. No entanto uma implementação bem sucedida de princípios Lean dependem dos processos internos de negócios que você usa, além do ambiente e das condições reais de produção. |

## <a name="modeling-manufacturing-and-logistics-processes-as-production-flows"></a>Modelar processos de fabricação e de logística de acordo com o fluxo de produção
Para criar um fundamento de lean manufacturing, modele o processo de fabricação e de logística de acordo com o fluxo de produção. Essa atividade consiste nas seguintes tarefas:
1.  Identifique os processos para os quais você deseja implementar uma estratégia de reabastecimento de lean e o em seguida modelar esses processamentos de acordo com o fluxo de produção. Você poderá analisar e simplificar os processos. Uma das metas de uma implementação de lean é reduzir o desperdício aumentando o fluxo de material e de informações.
2.  Definir um fluxo de produção como uma sequência de atividades que descreve o fluxo de material. Uma atividade de transferência define o movimento de um produto ou de produtos de um local para outro. Uma atividade de processamento define uma operação de valor agregado que se aplica a um produto.
3.  Criar uma versão do fluxo de produção que define os requisitos por takt time. Esses requisitos são usados para calcular o tempo do ciclo de cada atividade no fluxo de produção. Você pode criar várias versões dos fluxos de produção e depois usar essas versões para melhorar processos.

## <a name="using-kanbans-to-signal-demand-requirements"></a>Usando kanban para sinalizar requisitos de demanda
Um sistema de recebimento gera bens somente quando eles são necessários. Esta prática reduz o tempo de entrega e o estoque em excesso. Você pode usar kanban para planejar, rastrear e processar os requisitos baseados em fluxos de produção. Para criar uma estrutura de kanban, crie as regras kanban que são definidas com a criação do kanban e como os requisitos são preenchidos. Você pode criar dois tipos de regras kanban. As regras de fabricação criam trabalhos kanban de processamento e as regras kanban de retirada criam trabalhos kanban de transferência. Você pode configurar as estratégias de reabastecimento a seguir:
-   **Quantidade fixa** as regras kanban estão relacionadas a um número fixo de unidades de manuseio, o que significa que os números de kanban ativos são constantes. Sempre que todos os produtos de um kanban são consumidos e as unidades de manuseio de material são esvaziadas manualmente, um novo kanban do mesmo tipo é criado. Ao criar regras de kanban de quantidade fixa, é possível calcular as quantidades de kanban ideais e as quantidades de produto que são usadas. O cálculo só levará em conta a previsão, a demanda real de ordens em aberto, o prazo de entrega para reabastecer itens e as demandas históricas.
-   As regras kanban **agendadas** reabastecem os requisitos calculados pelo planejamento mestre. O planejamento mestre gera os kanbans planejados que podem ser confirmados para kanbans.
-   As regras kanban de **evento** reabastecem os requisitos originados das linhas da ordem de venda, das linhas da BOM de produção, das linhas de kanban ou das configurações de estoque mínimo. Quando os kanban de evento são gerados, eles serão vinculados à requisição da origem.

Quando os kanban são criados, um ou vários trabalhos kanban são gerados com base nas atividades do fluxo kanban definidas nas regras kanban.

## <a name="monitoring-and-maintaining-kanban-jobs"></a>Monitoramento e manutenção de trabalhos kanban
O lean manufacturing oferece visibilidade no status atual das atividades de fabricação e logística que são governadas por regras kanban. Como resultado, você pode planejar e priorizar as seguintes tarefas:

-   Obtenha uma visão geral da programação atual de trabalhos kanban.
-   Planejar e reprogramar trabalhos kanban.
-   Controle e registre o status de trabalhos kanban.

A lista a seguir descreve os quadros kanban especializados:
-   Agendamento de trabalho kanban – fornece uma visão geral dos trabalhos kanban. O quadro exibe trabalhos kanban e o status deles para uma ou várias células de trabalho. Os trabalhos são listados de acordo com os períodos de planejamento (dias ou semanas) definidos pelo modelo de fluxo de produção. O quadro também exibe o consumo da capacidade de cada período de planejamento, para que você possa monitorar a carga programada. Você pode alterar o status do trabalho kanban, reprogramar trabalho kanban para períodos de planejamento diferentes e executar outras tarefas.
-   Quadro kanban para trabalhos de transferência – Este quadro fornece uma visão geral dos trabalhos de transferência atuais. Você pode atualizar e registrar as listas de separação, iniciar e completar os trabalhos de transferência e executar outras tarefas.
-   Quadro kanban para processar trabalhos – esse quadro foi projetado para dar suporte ao fluxo de produção normal e oferecer uma visão geral da situação atual em uma ou mais células de trabalho. Nesse quadro, os Kanbans podem ser priorizados, separados ou fabricados. O quadro também foi projetado para dar suporte à digitalização de código de barras para os relatórios de Kanbans.

## <a name="kanban-jobs-and-integration-with-supply-chain-management-processes"></a>Trabalhos kanban e integração aos processos do Supply Chain Management
Os trabalhos kanban são totalmente integrados aos processos atuais para transações de estoque no Supply Chain Management.
-   Você pode executar atividades de separação para reabastecer o material usado para atender aos requisitos dos trabalhos kanban.
-   Você pode imprimir cartões kanban, colocar cartões kanban em circulação e separar listas para oferecer suporte para o uso de kanbans. Esses documentos são usados para representar, acompanhar e registrar os trabalhos kanban no depósito e no chão de fábrica.
-   Você pode registrar a separação e as atividades de transferência no estoque digitalizando códigos de barra.

Além de isso, o lean manufacturing oferece suporte para os processos de compra e de faturamento para serviços que são referidos como atividades subcontratadas.
-   Você pode atribuir linhas e serviços do contrato de compra para atividades subcontratadas.
-   Você pode criar ordens de compra e avisos de recebimento periódicos para dar suporte a compra e ao faturamento de serviços.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]