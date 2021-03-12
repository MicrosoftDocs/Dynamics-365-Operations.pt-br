---
title: Remover um trabalho kanban da agenda
description: Esse procedimento se concentra em remover uns trabalhos kanban planejados do processo de plano revertendo o status do trabalho para Não planejado.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, SysLookupMultiSelectGrid, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fcd9247e24323ba606377d7e51bd4447ab51c905
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4961606"
---
# <a name="remove-a-kanban-job-from-the-schedule"></a>Remover um trabalho kanban da agenda

[!include [banner](../../includes/banner.md)]

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

