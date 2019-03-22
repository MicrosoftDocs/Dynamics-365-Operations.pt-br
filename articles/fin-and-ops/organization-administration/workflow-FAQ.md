---
title: Perguntas frequentes sobre fluxo de trabalho
description: Esse tópico responde perguntas frequentes sobre o sistema de fluxo de trabalho no Microsoft Dynamics 365 for Finance and Operations.
author: ChrisGarty
manager: AnnBe
ms.date: 02/28/2019
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
ms.openlocfilehash: f058a450eb18e688efbc5306a42b4efef6aa91e7
ms.sourcegitcommit: 9a723737565ac78c884e40f7129d0f5aad747524
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/01/2019
ms.locfileid: "773195"
---
# <a name="workflow-system"></a>Sistema do fluxo de trabalho

[!include [banner](../includes/banner.md)]

Esse tópico responde perguntas frequentes sobre o sistema de fluxo de trabalho no Microsoft Dynamics 365 for Finance and Operations.

## <a name="notifications"></a>Notificações

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>Por que várias notificações são recebidas quando um item de trabalho é rejeitado?
Quando um item de trabalho é rejeitado, esse item de trabalho é concluído como anulado. Outro item de trabalho é criado e atribuído ao originador. Isso significa que há uma notificação para o originador do item de trabalho rejeitado, e uma notificação separada para o usuário atribuído ao novo item de trabalho com "alteração solicitada". 

Cada notificação é para um item de trabalho diferente, mas a similaridade pode causar confusão. Sempre estamos de olho em formas para aprimorar isso em uma versão futura.
