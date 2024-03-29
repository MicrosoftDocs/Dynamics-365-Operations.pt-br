---
title: Agendar trabalhos kanban
description: Esse procedimento se concentra em trabalhos kanban do processo de agendamento para uma célula de trabalho específica.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, KanbanPeriodCapacityPart, SysLookupMultiSelectGrid, KanbanBoardScheduleJobForward
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2cab3af0802ae6fa942460cfdd9c0819e1d31d4b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579079"
---
# <a name="schedule-kanban-jobs"></a>Agendar trabalhos kanban

[!include [banner](../../includes/banner.md)]

Esse procedimento se concentra em trabalhos kanban do processo de agendamento para uma célula de trabalho específica. O procedimento “Preparar uns trabalhos kanban de processo quando os materiais não estiverem disponíveis” é um pré-requisito para a criação deste procedimento. A empresa de dados demo usada para criar este procedimento é USMF. Esta tarefa está direcionada para o supervisor de chão de fábrica e o planejador de produção que estão trabalhando com kanbans.


## <a name="select-kanban-jobs-for-a-work-cell"></a>Selecione trabalhos kanban para uma célula de trabalho
1. Acesse Controle de produção > Kanban > Agendamento de trabalho Kanban.
2. Expandir o quadro de fatos Capacidade de período
    * Expandir o Quadro de Fatos Kanban.  
3. No campo Célula de trabalho, clique no botão suspenso para abrir a pesquisa.
4. Na lista, marque a linha selecionada.
    * Selecione a célula de trabalho 1250. Isso filtrará a exibição para exibir somente os trabalhos para a célula de trabalho 1250.  
5. Na lista, clique no link na linha selecionada.
6. Clique em Selecionar.

## <a name="schedule-a-kanban-job-in-the-first-available-period"></a>Agendar um trabalho kanban no primeiro período disponível
1. Na lista, marque a linha selecionada.
    * Selecione a primeira linha na lista que tem o Status não planejado. O ícone pontilhado no campo status do trabalho indica Não planejado.  
2. Clique em Agendar.
    * Isso agendará os trabalhos kanban no primeiro período disponível.  
    * Observe que os trabalhos kanban são movidos para o final da lista porque foram adicionados ao período que parte de hoje.  
    * Se o período que parte de hoje for registrado totalmente, os trabalhos serão movidos para o primeiro período disponível.  

## <a name="schedule-two-kanban-jobs-for-a-specific-day"></a>Agende os dois trabalhos kanban para um determinado dia
1. Na lista, selecione a linha 1.
    * Você deverá ver que a primeira linha que tiver o status não planejado no campo status do trabalho.  
2. Na lista, selecione a linha 2.
    * Você deverá ver que a segunda linha que tiver o status não planejado no campo status do trabalho. Agora você tem os dois primeiros trabalhos selecionados.  
3. Clique em Agendar da data para abrir a caixa de diálogo suspensa.
4. Marque ou desmarque a caixa de seleção Substituir reação de escassez de capacidade.
    * Esta opção permite que você substitua a reação padrão de escassez de capacidade.  
5. No campo Reação de escassez de capacidade, selecione 'Adicionar ao período solicitado'.
    * Esta opção assegurará que os trabalhos sejam adicionados à ordem, período de qualquer modo se a célula de trabalho pode ser sobrecarregada.  
6. Clique em Agendar.
    * Observe que os trabalhos são adicionados ao período desejado.  
    * Na seção Capacidade do período, você pode ver o carregamento para cada período. O campo Consumo mostra o consumo programado neste período. Se o consumo agendado for maior que a capacidade disponível neste período, o consumo selecionado será sobrecarregado.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]