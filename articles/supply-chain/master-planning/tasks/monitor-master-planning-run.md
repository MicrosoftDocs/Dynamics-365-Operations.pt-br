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
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b923b215528ecceaed9b5057ddb736ec959f1d65
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845104"
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

