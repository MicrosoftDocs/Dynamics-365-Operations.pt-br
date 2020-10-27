---
title: Estágios de ordem de serviço
description: Definindo fases de uma ordem de serviço e as atribuindo aos trabalhadores, você controla o fluxo de uma ordem de serviço por meio de tarefas que várias pessoas executam na organização de serviço.
author: ShylaThompson
manager: tfehr
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAStageTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 52bcb72e8222b378198fcd044428fa1a4a0e8944
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3978426"
---
# <a name="service-order-stages"></a>Estágios de ordem de serviço   

[!include [banner](../includes/banner.md)]


Você pode configurar fases de uma ordem de serviço para definir as tarefas que devem ser concluídas, a ordem em que são concluídas e os trabalhadores responsáveis pela conclusão delas. Definindo fases de uma ordem de serviço e as atribuindo aos trabalhadores, você poderá controlar o fluxo de uma ordem de serviço por meio de tarefas que várias pessoas executam na organização de serviço. A sequência de fases deve incluir uma fase inicial.

Você também pode definir as ações que são permitidas em cada fase. Por exemplo, se você desmarcar a caixa de seleção **Lançar** para todas as fases, exceto a fase final, você impedirá que as ordens de serviço sejam lançadas antes de terem percorrido toda a sequência completa de fases.

## <a name="branching-in-service-order-stages"></a>Ramificação nas fases da ordem de serviço

Ao configurar uma fase de serviço, você poderá criar várias opções ou ramificações, a serem selecionadas para a próxima fase de serviço. Todas as ramificações que você criar estarão disponíveis para seleção, quando a fase inicial for concluída. Por exemplo, você configura **Planejamento** como uma fase inicial. Você cria duas fases denominadas **Em andamento** e **Cancelar** e, em seguida, seleciona **Planejar** como pai delas. Você atribui a fase de **Planejamento** à ordem de venda. Quando a fase de planejamento da ordem de venda for concluída, você poderá selecionar a fase **Em andamento** se a ordem de venda estiver pronta ou poderá selecionar a fase **Cancelar** se a ordem de venda for cancelada.

## <a name="see-also"></a>Consulte também

[Configurar estágios da ordem de serviço](set-up-service-order-stages.md)

[Alterar a fase da ordem de serviço](change-service-order-stage.md)

  


