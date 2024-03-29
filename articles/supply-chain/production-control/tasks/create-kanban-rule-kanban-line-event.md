---
title: Criar uma regra kanban usando um evento de linha de kanban
description: Este procedimento cria uma regra kanban usando a linha kanban de evento que ajusta-se para provocar a tração de uma atividade do processo.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b7aaf959db0f0a136fc615f9a57ec787ef6cf2ad
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579151"
---
# <a name="create-a-kanban-rule-using-a-kanban-line-event"></a>Criar uma regra kanban usando um evento de linha de kanban

[!include [banner](../../includes/banner.md)]

Este procedimento cria uma regra kanban usando a linha kanban de evento que ajusta-se para provocar a tração de uma atividade do processo. A regra kanban é provocada por uma atividade kanban do processo, com uma quantidade igual ou maior que 25 cada. A empresa de dados demo usada para criar esta tarefa é USMF. Esta tarefa destina-se ao Engenheiro do processo ou Gerente de fluxo de valor, pois eles preparam a produção de um produto novo ou modificado em um ambiente de lean.


## <a name="create-a-kanban-rule"></a>Criar uma regra kanban
1. Acesse Gerenciamento de informações dos produtos > Lean manufacturing > Regras kanban.
2. Clique em Novo.
3. No campo Estratégia de reabastecimento, selecione 'Evento'.
    * Isto gera kanbans diretamente na procura. É usado para estabelecer as regras que definem uma encenação por encomenda.  
4. No campo Primeira atividade do plano, insira ou selecione um valor.
    * Insira ou selecione SpeakerAssemblyAndPolish. A primeira atividade de uma regra kanban de fabricação é uma atividade de processo no fluxo de produto. Quando você seleciona a atividade, as datas de validade da atividade são copiadas para as datas de validade da regra kanban.  
5. Expanda a seção Detalhes.
6. No campo Produto, digite 'L0001'.
7. Expanda a seção Eventos.
8. No campo Evento de linha Kanban, selecione 'Automático'.
    * Isto gera os kanbans do evento por encomenda.  Este campo é usado para definir regras kanban que reabastecem o material necessário para uma atividade de processo downstream. Quando você seleciona automático, os kanbans do evento são criados com a procura. Este ajuste é recomendado se você espera executar no mesmo dia a produção.  
9. Defina Quantidade mínima de eventos como '25'.
    * Os kanbans de evento são gerados quando a quantidade da demanda é igual ou maior do que este campo. Isto é útil se você quer produzir uma quantidade da ordem menor do que este campo em uma máquina e maior do que este campo em uma outra máquina.  
10. Clique em Salvar.

## <a name="create-sales-order-and-trigger-kanban-chain"></a>Crie a corrente kanban da ordem e do disparador de vendas
1. Acesse Vendas e marketing > Ordens de venda > Todas as ordens de venda.
2. Clique em Novo.
3. No campo Conta de cliente, insira ou selecione um valor.
    * Selecione a conta de Cliente US-003, Forest Wholesales.  
4. Clique em OK.
5. No campo Número do item, digite 'L0001'.
    * L0001 é o item para o qual você criou a regra kanban.  
6. Defina a quantidade como '27'.
    * Como 27 é mais alto do que a quantidade mínima de 25 na regra kanban, este provocará um evento kanban.  
7. No campo Site, digite '1'.
8. No campo Depósito, insira ou selecione um valor.
    * Selecione depósito 13.  
9. Clique em Salvar.

## <a name="view-the-kanban-generated-by-the-kanban-rule"></a>Veja o kanban gerado pela regra kanban
1. Acesse Gerenciamento de informações dos produtos > Lean manufacturing > Regras kanban.
2. Na lista, localize e selecione o PDV desejado.
3. Expanda a seção kanbans.
    * Observe que um kanban de 27 foi criado para processar a atividade baseada na regra kanban criada.  
    * Esta é a última etapa.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]