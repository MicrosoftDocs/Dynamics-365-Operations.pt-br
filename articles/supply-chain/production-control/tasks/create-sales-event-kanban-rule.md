--- 
title: Criar uma regra kanban de evento de vendas
description: "Este procedimento tem como foco a configuração necessária para criar uma regra kanban que é necessária durante a criação da ordem de vendas."
author: ChristianRytt
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: f1f66157b2e74ad1b490e10112cbc121ac9826fb
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-sales-event-kanban-rule"></a>Criar uma regra kanban de evento de vendas

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento tem como foco a configuração necessária para criar uma regra kanban que é necessária durante a criação da ordem de vendas. A regra kanban de evento reabastece requisitos que têm origem nas linhas de ordem de vendas. A empresa de dados demo usada para criar este procedimento é USMF. Destina-se ao engenheiro do processo ou gerente de fluxo de valor, pois eles preparam a produção de um produto novo ou modificado.




## <a name="create-a-new-kanban-rule"></a>Criar uma nova regra kanban
1. Vá para Regras kanban.
2. Clique em Novo.
3. No campo Estratégia de reabastecimento, selecione 'Evento'.
    * Selecionar Evento significa que a regra kanban é ativada por um evento, como a criação de uma linha da ordem de venda.   Isso é aplicado a áreas nas quais cada kanban deve cobrir uma demanda específica.  
4. No campo Primeira atividade do plano, insira ou selecione um valor.
    * Selecione Montagem final.  
5. Expanda a seção Detalhes.
6. No campo Produto, insira ou selecione um valor.
    * Selecione L0050.  

## <a name="define-an-event"></a>Definir um evento
1. Expanda a seção Eventos.
2. No campo Evento de vendas, selecione 'Automático'.
    * Selecionando o evento de vendas Automático, a regra kanban será acionada automaticamente quando uma linha de vendas corresponder ao produto e local de recebimento. Neste procedimento, é o produto L0050 no depósito 13.  
3. Defina Quantidade mínima de eventos como '50'.
    * Com uma quantidade mínima de eventos de 50, a regra kanban será acionada somente por eventos com uma quantidade de 50 ou mais.  
4. Expanda a seção Fluxo de produção.
    * Observe que o local de recebimento é o depósito 13. Isso significa que essa regra kanban será acionada quanto a esse local.  
    * Neste exemplo, uma linha de vendas do produto L0050, com uma quantidade de 50 ou mais, no depósito 13, acionará a regra kanban.  

## <a name="create-sales-line-to-trigger-event-kanban-rule"></a>Criar linha de vendas para acionar regra kanban de evento
1. Ir para Todas as ordens de venda.
    * Um aviso é exibido quando a regra kanban é salva, o que significa que kanbans serão criados em tempo real durante a produção de ordens de vendas.  
2. Clique em Novo.
3. No campo Conta de cliente, insira ou selecione um valor.
    * Por exemplo, selecione US-003.  
4. Clique em OK.
5. No campo Número do item, digite 'L0050'.
6. No campo Site, digite '1'.
    * Selecione Site 1, pois o depósito 13 está no site 1.  
7. No campo Depósito, insira ou selecione um valor.
    * Defina Depósito como 13.  
8. Defina a quantidade como '75'.
    * Insira uma quantidade de 50 ou mais, para acionar a regra kanban criada.  

## <a name="verify-that-kanban-is-created"></a>Verifique se o kanban foi criado.
1. Clique em Produtos e fornecimento.
2. Clique em Exibir árvore de vinculação.
    * Note que um kanban com a mesma quantidade como a linha de vendas é criado. Você também pode ver as questões materiais necessárias para produzir L0050. Esta é a última etapa do procedimento.  


