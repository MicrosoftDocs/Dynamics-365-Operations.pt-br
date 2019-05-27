---
title: Criar uma regra kanban de evento da linha BOM
description: Essa tarefa se concentra na configuração necessária para criar uma regra kanban de evento e garantir a fonte para linhas BOM de produção em um ambiente de produção lean e clássico misturado.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdTable, ProdBOM, ProdParmCostEstimation
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 82a4252548fd030f2a044436ff607da5125d2854
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1551920"
---
# <a name="create-a-bom-line-event-kanban-rule"></a>Criar uma regra kanban de evento da linha BOM

[!include [task guide banner](../../includes/task-guide-banner.md)]

Essa tarefa se concentra na configuração necessária para criar uma regra kanban de evento e garantir a fonte para linhas BOM de produção em um ambiente de produção lean e clássico misturado. A empresa de dados demo usada para criar esta tarefa é USMF. Esta tarefa destina-se ao Engenheiro do processo ou Gerente de fluxo de valor, pois eles preparam a produção de um produto novo ou modificado.


## <a name="create-a-new-kanban-rule"></a>Criar uma nova regra kanban
1. Vá para Controle de produção > Tarefas periódicas > Cálculo da quantidade kanban > Regras kanban.
2. Clique em Novo.
3. No campo Tipo, selecione "Retirada".
    * O tipo de retirada é usado para criar kanbans de transferência.  
4. No campo Estratégia de reabastecimento, selecione 'Evento'.
    * A Estratégia de evento está selecionada para criar a transferência de kanbans com base em um evento. Posteriormente na guia da tarefa, o dispararemos estimando uma ordem de produção.  
5. No campo Primeira atividade do plano, insira ou selecione um valor.
    * Insira ou selecione ReplenishSpeakerComponents. Essa atividade de transferência tem o depósito de recebimento (saída) e o local 12, o que significa que o material será movido para a localização 12 no depósito 12.  
6. Expanda a seção Detalhes.
7. No campo Produto, insira ou selecione M0001.
8. Expanda a seção Eventos.
9. No campo Evento de linha BOM, selecione 'Automático'.
    * No campo do evento da linha BOM definido como automático, o kanban será criado para atender às necessidades de material de embalagem para linhas BOM da ordem de produção.  
10. Feche a página.

## <a name="create-and-modify-a-new-production-order"></a>Criar e modificar uma nova ordem de produção
1. Vá para Controle de produção > Ordens de produção > Todas as ordens de produção.
2. Clique em Nova ordem de produção.
3. No campo Número do item, insira ou selecione um valor.
    * Insira ou selecione 'L0001'. Nós usamos o item L0001 porque o item M0001 é incluído na BOM para o item L0001.  
4. Clique em Criar.
5. Na lista, clique no link na linha de L0001.
6. Clicar em BOM.
7. Na lista, clique no link na linha selecionada.
8. Clique em Editar.
9. No campo Tipo de linha, selecione "Fornecimento vinculado".
    * O Fornecimento vinculado está selecionado para disparar a criação de fornecimento de um kanban.  
10. Selecione Não no campo Consumo de recurso.
    * Desmarcar a caixa de seleção de consumo de recurso permite trocar o depósito.  
11. Expanda a seção Dimensões de estoque.
12. No campo Depósito, digite '12'.
    * O depósito é definido como 12 porque esse é o depósito de saída para a atividade de saída.  
13. No campo Local, digite '12'.
    * O local é definido como 12 porque esse é o local de saída para a atividade de saída.  
14. Feche a página.
15. Feche a página.

## <a name="estimate-the-production-order-and-view-the-kanban-created"></a>Estimar a ordem de produção e exibir o kanban criado
1. Clique em Estimar.
    * Para estimar a ordem de produção dispararemos a criação do kanban associada para fornecer o item M0001.  
2. Clique em OK.
3. Feche a página.
4. Feche a página.
5. Vá para Gerenciamento de informações dos produtos > Lean manufacturing > Regras kanban.
6. Na lista, clique no link na linha selecionada.
    * Selecione a regra kanban de evento criada para o item M0001.  
7. Expanda a seção kanbans.
8. Na lista, marque a linha selecionada.
    * Observe o kanban criado para fornecer M0001 para a ordem de produção prevista.  
    * Esta é a última etapa!  

