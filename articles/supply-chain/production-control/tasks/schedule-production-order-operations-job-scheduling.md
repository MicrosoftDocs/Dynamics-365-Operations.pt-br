---
title: Agendar uma ordem de produção com operações e agendamento de trabalho
description: Este tópico se concentra em agendar uma ordem de produção com o agendamento de operações e planejamento de trabalho.
author: ChristianRytt
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 883a68af78a9d91df089d30d8f1b3d7ba498d577
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841374"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a>Agendar uma ordem de produção com operações e agendamento de trabalho

[!include [banner](../../includes/banner.md)]

Este tópico se concentra em agendar uma ordem de produção com o agendamento de operações e planejamento de trabalho. Nenhum trabalho é criado com o agendamento de operações, mas sim no planejamento de trabalho. A empresa de dados demo usada para criar esta tarefa é USMF. Este procedimento destina-se ao gerente de produção, ao planejador de produção, ou supervisor de chão de fábrica que trabalha em um ambiente de manufatura discreto.


## <a name="create-a-production-order"></a>Criar uma ordem de produção
1. No painel de navegação, acesse **Módulos > Controle de produção > Ordens de produção > Todas as ordens de produção**.
2. Selecione **Nova ordem de produção**.
3. No campo **Número do item**, insira ou selecione um valor. Selecione o Número de item **D0001**.  
4. Selecione **Criar**.

## <a name="schedule-operations-for-the-production-order"></a>Agendar operações para a ordem de produção
1. Marque a linha que acabou de ser criada.      
2. No Painel de Ação, selecione **Agendar**.
3. Selecione **Agendar operações**.
4. No campo **Direção do agendamento**, selecione **A partir da data de agendamento**.
5. No campo **Data de planejamento**, insira uma data. Selecione uma data futura, por exemplo, hoje mais uma semana. Com a Direção de agendamento selecionada, a ordem de produção será agendada a partir dessa data.  
6. Selecione **OK**.
7. Na lista, marque a linha selecionada. Observe que o status foi alterado para **Agendado**. 
8. Selecione **Todos os trabalhos**. Observe que nenhum trabalho é criado com o agendamento de operações.  
9. Feche a página.

## <a name="schedule-jobs-for-the-production-order"></a>Agendar trabalhos para a ordem de produção
1. No Painel de Ação, selecione **Agendar**.
2. Selecione **Agendar trabalhos**.
3. No campo **Direção do agendamento**, selecione **A partir da data de agendamento**.
4. No campo **Data de planejamento**, insira uma data. Selecione uma data futura, por exemplo, hoje mais uma semana. Com a Direção de agendamento selecionada, a ordem de produção será agendada a partir dessa data.  
5. Selecione **OK**.
6. No Painel de Ação, selecione **Ordem de produção**.
7. Selecione **Todos os trabalhos**. Observe que, com base no roteiro ativo, 5 trabalhos são criados com o agendamento do trabalho.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]