---
title: Expedir ordem de serviço
description: Este artigo explica como expedir uma ordem de serviço no Gerenciamento de Ativos.
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetScheduledExecution
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f78e8642715b0c3fd3d01e8072645ccd9c58d685
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016845"
---
# <a name="dispatch-work-order"></a>Expedir ordem de serviço

[!include [banner](../../includes/banner.md)]

 

Você pode agendar uma ordem de serviço ou trabalhos de ordem de serviço para um trabalhador usando a funcionalidade **Expedir**.

1. Clique em **Gerenciamento de ativos** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.

2. Selecione a ordem de serviço na lista.

3. Na guia **Geral**, clique em **Expedir**.

4. No diálogo **Agendar ordem de serviço**, selecione o trabalhador no campo **Trabalhador**.

5. No campo **Agendar horas**, é possível inserir as horas de trabalho esperadas caso estas sejam diferentes das horas previstas.

6. No campo **Início programado**, é possível editar a data e hora de início, se necessário.

7. Se o processo de agendamento respeitar as limitações de capacidade em relação aos recursos já agendados em outros trabalhos, verifique se os botões de alternância **Ativo**, **Ferramenta** e **Trabalhador** estão definidos como **Sim**. Se você quiser ver informações detalhadas sobre o processo de agendamento, selecione **Sim** no botão de alternância **Detalhado**. Isso significa que informações detalhadas sobre as pontuações calculadas na ordem de serviço são mostradas no Log de Informações.

8. Selecione **Sim** no botão de alternância **Ignorar agendamento** para ignorar os dias fechados no calendário (aplica-se a ativos, trabalhadores e ferramentas). Selecione **Sim** no botão de alternância **Ignorar execução agendada** para ignorar as limitações que podem ter sido selecionadas na ordem de serviço referente ao agendamento. 

    Para obter informações sobre a configuração da execução agendada, consulte a seção [Execução agendada](../setup-for-work-orders/scheduled-execution.md).

9. Clique em **OK**. O estado de ciclo de vida da ordem de serviço é atualizado automaticamente para o estado de ciclo de vida **Agendado** especificado em **Gerenciamento de ativos** > **Configuração** > **Ordens de serviço** > **Modelos de ciclo de vida**.

A figura abaixo mostra um exemplo de seleções de expedição na caixa de diálogo **Agendar ordens de serviço**.

![Figura 1.](media/04-work-order-scheduling.png)

[!NOTE]
Se você deseja excluir o agendamento de uma ordem de serviço, selecione a ordem de serviço em **Todas as ordens de serviço** e, em seguida, clique em **Excluir agenda** na guia **Geral**. Lembre-se de atualizar manualmente o estado de ciclo de vida da ordem de serviço se você excluir o agendamento.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]