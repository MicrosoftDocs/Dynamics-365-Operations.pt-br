---
title: Monitorar uma execução do planejamento mestre
description: O planejador de produção deseja ver se uma execução do planejamento mestre está em andamento.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7c2e158d8cbad1f5d4f377f6a8eb43487b34ffdc
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "367492"
---
# <a name="monitor-a-master-planning-run"></a>Monitorar uma execução do planejamento mestre

[!include [task guide banner](../../includes/task-guide-banner.md)]

O planejador de produção deseja ver se uma execução do planejamento mestre está em andamento. Use empresa de dados demo USMF para completar este procedimento.


## <a name="run-master-planning"></a>Executar planejamento mestre
1. Clique em Planejamento mestre.
    * Você encontrará isso no painel padrão.  
2. No campo Plano, insira ou selecione um valor.
    * Exemplo: StaticPlan  
3. Clique em Executar.
4. Selecione Sim no campo Rastrear tempo de processamento.
    * Se o campo já estiver selecionado, pule esta etapa.  
5. No campo Número de threads, insira um número.
6. Expanda os Registros para incluir a seção.
7. Clique em Filtro.
8. Na lista, marque a linha selecionada.
    * Marque a linha onde Campo = Número de item.  
9. No campo Critérios, insira ou selecione um valor.
    * Exemplo: T0001  
10. Clique em OK.
11. Clique em OK.

## <a name="monitor-the-master-planning-run"></a>Monitore a execução do planejamento mestre
1. Clique em Histórico.
2. Clique em Consultas.
3. Clique em Processar duração da tarefa.
4. Na lista, localize e selecione o PDV desejado.
    * Para cada item é possível obter uma visão geral do período necessária para preencher cada etapa de planejamento.  

