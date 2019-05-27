---
title: Agendar uma ordem de produção com operações e agendamento de trabalho
description: Este procedimento se concentra em agendar uma ordem de produção com o agendamento de operações e planejamento de trabalho.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 00698e9cd2ed0481e5fed301c8a8c2e98690a5db
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562129"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a>Agendar uma ordem de produção com operações e agendamento de trabalho

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento se concentra em agendar uma ordem de produção com o agendamento de operações e planejamento de trabalho. Nenhum trabalho é criado com o agendamento de operações, mas sim no planejamento de trabalho. A empresa de dados demo usada para criar esta tarefa é USMF. Este procedimento destina-se ao gerente de produção, ao planejador de produção, ou supervisor de chão de fábrica que trabalha em um ambiente de manufatura discreto.


## <a name="create-a-production-order"></a>Criar uma ordem de produção
1. Vá para Controle de produção > Ordens de produção > Todas as ordens de produção.
2. Clique em Nova ordem de produção.
3. No campo Número do item, insira ou selecione um valor.
    * Selecione o Número de item D0001.  
4. Clique em Criar.

## <a name="schedule-operations-for-the-production-order"></a>Agendar operações para a ordem de produção
1. Na lista, marque a linha selecionada.
    * Selecione a ordem de produção que você acabou de criar. Ela deve estar na parte superior da lista.      
2. No Painel de Ação, clique em Agenda.
3. Clique em Agendar operações.
4. No campo Direção do agendamento, selecione 'A partir da data de agendamento'.
5. No campo Data de planejamento, insira uma data.
    * Selecione uma data futura, por exemplo, hoje mais uma semana. Com a Direção de agendamento selecionada, a ordem de produção será agendada a partir dessa data.  
6. Clique em OK.
7. Na lista, marque a linha selecionada.
    * Observe que o status foi alterado para Agendado.  
8. Na lista, clique no link na linha selecionada.
9. Clique em Todos os trabalhos.
    * Observe que nenhum trabalho é criado com o agendamento de operações.  
10. Feche a página.

## <a name="schedule-jobs-for-the-production-order"></a>Agendar trabalhos para a ordem de produção
1. No Painel de Ação, clique em Agenda.
2. Clique em Agendar trabalhos.
3. No campo Direção do agendamento, selecione 'A partir da data de agendamento'.
4. No campo Data de planejamento, insira uma data.
    * Selecione uma data futura, por exemplo, hoje mais uma semana. Com a Direção de agendamento selecionada, a ordem de produção será agendada a partir dessa data.  
5. Clique em OK.
6. No Painel de Ação, clique em Ordem de produção.
7. Clique em Todos os trabalhos.
    * Observe que, com base no roteiro ativo, 5 trabalhos são criados com o agendamento do trabalho.  

