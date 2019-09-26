---
title: Agendar ordem de serviço em data e hora específicas
description: Este tópico explica como programar uma ordem de trabalho em uma data e hora específicas em Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0f818c4c3b669cc94e37cba1e3571c57b5c0dd1b
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887356"
---
# <a name="schedule-work-order-on-specific-date-and-time"></a>Agendar ordem de serviço em data e hora específicas

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Se uma ordem de trabalho tiver de ser agenda em uma data *e* hora específicas, você pode substituir o processo de agendamento padrão no Gerenciamento de ativo e criar um agendamento específico para uma ordem de serviço.

1. Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.

2. Na lista de trabalho, clique na ID da ordem de trabalho na coluna **Ordem de trabalho**.

3. Clique em **Editar**.

4. Na Guia Rápida **Cabeçalho da ordem de serviço**, insira as datas e horas e início e término nos campos **Início esperado** e **Término esperado**.

![Figura 1](media/05-work-order-scheduling.png)

5. Na guia **Geral**, clique em **Agendar** para usar o processo de agendamento padrão, ou clique em **Expedir** se quiser agendar a ordem de serviço para um trabalhador específico.

6. Para substituir quaisquer reservas de capacidade existentes para garantir que a ordem de serviço está agendada no período esperado, realize as seleções como exibido na figura abaixo na seção da caixa de diálogo **Agendar ordem de serviço** > **Capacidade finita**. Isso significa que o processo de agendamento ignorará as reservas de capacidade existentes porque a ordem de serviço deve iniciar na hora de início esperada.

![Figura 2](media/06-work-order-scheduling.png)

7. Clique em **OK** para iniciar o agendamento.

8. Se o processo de agendamento resultar em duplas reservas, você verá uma mensagem na tela e poderá ajudar as ordens de serviço relacionadas.

>[!NOTE]
>Para agendar um funcionário de manutenção para a ordem de serviço, o funcionário de manutenção deve estar disponível na data e hora de início esperada. A disponibilidade do trabalhador é configurada em [calendário do trabalhador](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md). 
