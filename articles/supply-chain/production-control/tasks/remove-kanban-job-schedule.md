---
title: Remover um trabalho kanban da agenda
description: Esse procedimento se concentra em remover uns trabalhos kanban planejados do processo de plano revertendo o status do trabalho para Não planejado.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, SysLookupMultiSelectGrid, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 838270189e08065f791c9e58888351025e0a6df8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573624"
---
# <a name="remove-a-kanban-job-from-the-schedule"></a>Remover um trabalho kanban da agenda

[!include [banner](../../includes/banner.md)]

Esse procedimento se concentra em remover uns trabalhos kanban planejados do processo de plano revertendo o status do trabalho para Não planejado. A empresa de dados demo usada para criar este procedimento é USMF. Este procedimento está direcionada para o supervisor de chão de fábrica ou o planejador de produção.


## <a name="find-a-planned-kanban-job"></a>Escolha um trabalho kanban planejado
1. Acesse Controle de produção > Kanban > Agendamento de trabalho Kanban.
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]