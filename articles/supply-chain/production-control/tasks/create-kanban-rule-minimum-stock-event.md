---
title: Criar uma regra kanban usando um evento de estoque mínimo
description: Este procedimento é centrado sobre a instalação necessária para criar uma regra kanban usando um evento do estoque mínimo para assegurar-se de que um produto específico esteja sempre disponível em um lugar específico.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable, InventLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6ca5a2e2180235e51ef569fd93ad06867c3dddae
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149311"
---
# <a name="create-a-kanban-rule-using-a-minimum-stock-event"></a>Criar uma regra kanban usando um evento de estoque mínimo

[!include [banner](../../includes/banner.md)]

Este procedimento é centrado sobre a instalação necessária para criar uma regra kanban usando um evento do estoque mínimo para assegurar-se de que um produto específico esteja sempre disponível em um lugar específico. Uma regra kanban é criada para transferir o material ao lugar quando o nível de estoque cai abaixo de 200 partes. Ao executar o processamento do evento de vinculação, os kanbans necessários são criados. A empresa de dados demo usada para criar esta tarefa é USMF. Esta tarefa destina-se ao Engenheiro do processo ou Gerente de fluxo de valor, pois eles preparam a produção de um produto novo ou modificado em um ambiente de lean.


## <a name="create-a-new-kanban-rule"></a>Criar uma nova regra kanban
1. Vá para Gerenciamento de informações dos produtos > Lean manufacturing > Regras kanban.
2. Clique em Novo.
3. No campo Tipo, selecione "Retirada".
    * Este tipo é usado para criar kanbans de transferência.  
4. No campo Estratégia de reabastecimento, selecione 'Evento'.
    * A Estratégia de evento é usada para criar a transferência de kanbans com base em um evento. Mais tarde no procedimento, você provocará kanbans de transferência usando o reabastecimento conservado em estoque.  
5. No campo Primeira atividade do plano, insira ou selecione um valor.
    * Insira ou selecione ReplenishSpeakerComponents. Essa atividade de transferência tem o depósito de recebimento (saída) e o local 12, o que significa que o material será movido para a localização 12 no depósito 12.  
6. Expanda a seção Detalhes.
7. No campo Produto, insira ou selecione um valor.
    * Selecione M0007.  
8. Expanda a seção Eventos.
9. No campo Evento de reabastecimento de estoque, selecione "Lote".
    * Isto cria kanbans para cumprir necessidades materiais no lugar relacionado durante o processamento do evento de vinculação.  

## <a name="set-the-minimum-quantity-for-the-item"></a>Defina a quantidade mínima para o item
1. Clique para seguir o link no campo Produto.
2. Clique para seguir o link no campo Número de item.
3. Expanda a imagem do produto FactBox.
4. No Painel de Ação, clique em Plano.
5. Clique em Cobertura de item.
6. Clique em Novo.
7. Na lista, marque a linha selecionada.
8. No campo Depósito, insira ou selecione um valor.
    * Defina Depósito como 12.  
9. Ajuste o mínimo para “200".

## <a name="run-the-batch-event-creation-job"></a>Execute o trabalho de criação de evento em lotes
1. Vá para Controle de produção > Tarefas periódicas > Processamento em lote de trabalhos kanban > Processamento de evento de vinculação.
2. Clique em OK.
3. Vá para Gerenciamento de informações dos produtos > Lean manufacturing > Regras kanban.
4. Na lista, clique no link na linha selecionada.
    * Selecione a regra kanban que você criou anteriormente.  
5. Expanda a seção kanbans.
    * Observe que um kanban foi criado para transferir o material necessário para o depósito 12.  

