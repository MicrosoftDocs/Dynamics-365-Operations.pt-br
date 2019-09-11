---
title: Expedir ordem de serviço
description: Este tópico explica como expedir uma ordem de serviço no Gerenciamento de Ativo.
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
ms.openlocfilehash: 3b1621cf0f1e47d7bd5fe2fa0b41fbcd61f14def
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887196"
---
# <a name="dispatch-work-order"></a>Expedir ordem de serviço

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Você pode agendar uma ordem de serviço ou trabalhos de ordem de serviço para um trabalhador usando a funcionalidade **Expedir**.

1. Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.

2. Selecione a ordem de serviço na lista.

3. Na guia **Geral**, clique em **Expedir**.

4. Na caixa de diálogo **Agendar ordem de serviço**, selecione o trabalhador no campo **Trabalhador**.

5. No campo **Agendar horas**, é possível inserir as horas de trabalho esperadas caso estas sejam diferentes das horas previstas.

6. No campo **Início programado**, é possível editar a data e hora de início, se necessário.

7. Se o processo de agendamento respeitar as limitações de capacidade em relação aos recursos já agendados em outros trabalhos, verifique se os botões de alternância **Ativo**, **Ferramenta** e **Trabalhador** estão definidos como "Sim". Se você quiser ver informações detalhadas sobre o processo de agendamento, selecione "Sim" no botão de alternância **Detalhado**. Isso significa que informações detalhadas sobre as pontuações calculadas na ordem de serviço são mostradas no Log de Informações.

8. Selecione "Sim" no botão de alternância **Ignorar agendamento** para ignorar os dias fechados no calendário (aplica-se a ativos, trabalhadores e ferramentas). Selecione "Sim" no botão de alternância **Ignorar execução agendada** para ignorar as limitações que podem ter sido selecionadas na ordem de serviço referente ao agendamento. Consulte a seção [Execução agendada](../setup-for-work-orders/scheduled-execution.md) para obter informações sobre a configuração da execução agendada.

9. Clique em **OK**. O estado de ciclo de vida da ordem de serviço é atualizado automaticamente para o estado de ciclo de vida "Agendado" especificado em **Gerenciamento de ativos** > **Configuração** > **Ordens de serviço** > **Modelos de ciclo de vida**.

A figura abaixo mostra um exemplo de seleções de expedição na caixa de diálogo **Agendar ordens de serviço**.

![Figura 1](media/04-work-order-scheduling.png)

>[!NOTE]
>Se você deseja excluir o agendamento de uma ordem de serviço, isso é feito selecionando a ordem de serviço em **Todas as ordens de serviço** e clicando em **Excluir agenda** na guia **Geral**. Lembre-se de atualizar manualmente o estado de ciclo de vida da ordem de serviço se você excluir o agendamento.

