---
title: Remover um trabalho kanban da agenda
description: Esse procedimento se concentra em remover uns trabalhos kanban planejados do processo de plano revertendo o status do trabalho para Não planejado.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, SysLookupMultiSelectGrid, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: eeedfad5f294f73097fc1b6a973d63125df72209227fc06470663665961af2d4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756910"
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