--- 
title: Remover um trabalho kanban da agenda
description: "Esse procedimento se concentra em remover uns trabalhos kanban planejados do processo de plano revertendo o status do trabalho para Não planejado."
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: b1232fd4039c8021d9a4cd64d8b7c0f66a4f8f9f
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="remove-a-kanban-job-from-the-schedule"></a>Remover um trabalho kanban da agenda

[!include[task guide banner](../../includes/task-guide-banner.md)]

Esse procedimento se concentra em remover uns trabalhos kanban planejados do processo de plano revertendo o status do trabalho para Não planejado. A empresa de dados demo usada para criar este procedimento é USMF. Este procedimento está direcionada para o supervisor de chão de fábrica ou o planejador de produção.


## <a name="find-a-planned-kanban-job"></a>Escolha um trabalho kanban planejado
1. Vá para Controle de produção > Kanban > Agendamento de trabalho Kanban.
2. No campo Célula de trabalho, clique no botão suspenso para abrir a pesquisa.
3. Na lista, clique no link na linha selecionada.
    * Selecione a célula de trabalho 1250.  
4. Clique em Selecionar.
5. No campo Exibir status do trabalho, selecione 'Programado'.

## <a name="remove-the-planned-kanban-job-from-the-schedule"></a>Remover o trabalho kanban planejado da agenda
1. Na lista, localize e selecione o PDV desejado.
    * Selecione um trabalho que tenha o Status planejado, por exemplo, um trabalho de 19 de dezembro de 2012.  
2. No Painel de Ação, clique em Plano.
3. Clique em Reverter status de trabalho.
4. Clique em OK.
    * Isso reverterá o status do trabalho atual 'Planejado' para 'Não planejado' e remove-o da diretoria do processo.   


