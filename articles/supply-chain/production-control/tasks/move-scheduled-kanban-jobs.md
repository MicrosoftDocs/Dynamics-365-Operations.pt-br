--- 
title: Mover trabalhos kanban agendados
description: "Esse procedimento se concentra nesses trabalhos kanban de processo planejados para um período diferente."
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2a12a6859a3a436706822873bc6fdd781e0ef032
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="move-scheduled-kanban-jobs"></a>Mover trabalhos kanban agendados

[!include[task guide banner](../../includes/task-guide-banner.md)]

Esse procedimento se concentra nesses trabalhos kanban de processo planejados para um período diferente. A empresa de dados demo usada para criar este procedimento é USMF. Este procedimento está direcionada para o supervisor de chão de fábrica ou o planejador de produção que estão trabalhando com kanbans.


## <a name="select-scheduled-kanban-jobs"></a>Selecionar trabalhos kanban agendados
1. Gå til Produktionsstyring > Kanban > Tidsplanlægning af kanban-job.
2. !MtCMR!No campo Célula de trabalho, clique no botão suspenso para abrir a busca. áçêìõý!
3. Markér den valgte række på listen.
    * Selecione a célula de trabalho 1250.  
4. Klik på Select.
5. Vælg 'Planlagt' i feltet Display job status.
    * Isso filtra a lista de trabalho para exibir somente os trabalhos kanban programados.  

## <a name="move-kanban-jobs-to-a-different-period"></a>Mover trabalhos kanban a um período diferente
1. Find og vælg den ønskede post på listen.
    * Selecione um trabalho que tenha o status de Trabalho planejado, por exemplo, um trabalho programado em 20 de dezembro de 2012 no campo Período planejado. Então mova o trabalho para o período anterior.  
2. Klik på Previous period.
3. Klik på End.
    * Isso moverá o trabalho para o final da lista de trabalho como o último trabalho no período anterior.  
4. Find og vælg den ønskede post på listen.
    * Selecione um trabalho que tenha o status de Trabalho planejado, por exemplo, um trabalho programado em 18 de dezembro de 2012 no campo Período planejado. Então mova o trabalho para o próximo período.  
5. Klik på Next period.
6. Klik på Start.
    * Isso moverá o trabalho para o início da lista de trabalho como o primeiro trabalho no período anterior.  

## <a name="task-move-a-job-within-a-period"></a>Tarefas: Mover um trabalho em um período
1. Find og vælg den ønskede post på listen.
    * Selecione um trabalho que tenha o status de Trabalho planejado, por exemplo, o segundo trabalho programado em 19 de dezembro de 2012 no campo Período planejado. Então mova o trabalho para o período planejado.  
2. Klik på Forward.
    * Observe que os trabalhos são movidos para uma linha abaixo na lista.  
3. Klik på Backward.
    * Observe que os trabalhos são movidos para uma linha acima na lista.  


