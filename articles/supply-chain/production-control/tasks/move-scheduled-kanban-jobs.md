---
title: Mover trabalhos kanban agendados
description: Esse procedimento se concentra nesses trabalhos kanban de processo planejados para um período diferente.
author: ChristianRytt
manager: tfehr
ms.date: 11/07/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2769a7d519e12613796025b658db0b08cdfc4fde
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4961631"
---
# <a name="move-scheduled-kanban-jobs"></a>Mover trabalhos kanban agendados

[!include [banner](../../includes/banner.md)]

Esse procedimento se concentra nesses trabalhos kanban de processo planejados para um período diferente. A empresa de dados demo usada para criar este procedimento é USMF. Este procedimento está direcionada para o supervisor de chão de fábrica ou o planejador de produção que estão trabalhando com kanbans.

## <a name="select-scheduled-kanban-jobs"></a>Selecionar trabalhos kanban agendados. 

1. Vá para **Controle de produção > Kanban > Agendamento de trabalho Kanban**. 

2. No campo **Célula de trabalho**, clique no botão suspenso para abrir a pesquisa. 

3. Na lista, marque a linha selecionada. 
   - Selecione a célula de trabalho 1250. 
4. Clique em **Selecionar**. 

5. No campo **Exibir status do trabalho**, selecione **Programado**. Isso filtra a lista de trabalho para exibir somente os trabalhos kanban programados. 

## <a name="move-kanban-jobs-to-a-different-period"></a>Mover trabalhos kanban a um período diferente. 

1. Na lista, localize e selecione o PDV desejado. Selecione um trabalho que tenha o status de **Trabalho planejado**, por exemplo, um trabalho programado em 20 de dezembro de 2012 no campo **Período planejado**. Então mova o trabalho para o período anterior. 

2. Clique em **Período anterior**. 

3. Clique em **Finalizar** para mover o trabalho para o final da lista de trabalho como o último trabalho no período anterior. 

4. Na lista, localize e selecione o PDV desejado. Selecione um trabalho que tenha o status de **Trabalho planejado**, por exemplo, um trabalho programado em 18 de dezembro de 2012 no campo **Período planejado**. Então mova o trabalho para o próximo período. 

5. Clique em **Próximo período**. 

6. Clique em **Iniciar** para mover o trabalho para o início da lista de trabalho como o primeiro trabalho no período anterior. 

## <a name="move-a-job-within-a-period"></a>Mover um trabalho em um período. 

1. Na lista, localize e selecione o PDV desejado. Selecione um trabalho que tenha o status de Trabalho planejado, por exemplo, o segundo trabalho programado em 19 de dezembro de 2012 no campo **Período planejado**. Então mova o trabalho para o período planejado. 

2. Clique em **Encaminhar**. Observe que os trabalhos são movidos para uma linha abaixo na lista. 

3. Clique em **Recuar**. Observe que os trabalhos são movidos para uma linha acima na lista.
