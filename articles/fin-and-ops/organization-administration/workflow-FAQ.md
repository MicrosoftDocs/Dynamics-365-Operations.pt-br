---
title: Perguntas frequentes sobre fluxo de trabalho
description: Esse tópico responde perguntas frequentes sobre o sistema de fluxo de trabalho no Microsoft Dynamics 365 for Finance and Operations.
author: ChrisGarty
manager: AnnBe
ms.date: 05/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f6240b1b5136937aa47f455547fed6f0c7c08e2c
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509282"
---
# <a name="workflow-system"></a>Sistema do fluxo de trabalho

[!include [banner](../includes/banner.md)]

Esse tópico responde perguntas frequentes sobre o sistema de fluxo de trabalho no Microsoft Dynamics 365 for Finance and Operations.

## <a name="notifications"></a>Notificações

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>Por que várias notificações são recebidas quando um item de trabalho é rejeitado?
Quando um item de trabalho é rejeitado, esse item de trabalho é concluído como anulado. Outro item de trabalho é criado e atribuído ao originador. Isso significa que há uma notificação para o originador do item de trabalho rejeitado, e uma notificação separada para o usuário atribuído ao novo item de trabalho com "alteração solicitada". 

Cada notificação é para um item de trabalho diferente, mas a similaridade pode causar confusão. Sempre estamos de olho em formas para aprimorar isso em uma versão futura.

### <a name="why-are-my-workflow-exports-failing"></a>Por que minhas exportações de fluxo de trabalho estão falhando?
Atualmente, existe uma limitação no recurso de exportação de fluxo de trabalho para prevenir que nomes de fluxo de trabalho excedam 48 caracteres. Usar um nome maior que 48 caracteres pode resultar em um erro de "Falha do servidor ao autenticar a solicitação" e/ou prevenir que um arquivo seja exportado sem um tipo de arquivo. A postagem de blog a seguir fornece mais detalhes [Solução de problemas na exportação do fluxo de trabalho](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).
