--- 
title: "Monitorar uma execução do planejamento mestre"
description: "O planejador de produção deseja ver se uma execução do planejamento mestre está em andamento."
author: YuyuScheller
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 8eb19ac9ded4dc2a091ff733f2f43cb6cafa1b43
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="monitor-a-master-planning-run"></a>Monitorar uma execução do planejamento mestre

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


