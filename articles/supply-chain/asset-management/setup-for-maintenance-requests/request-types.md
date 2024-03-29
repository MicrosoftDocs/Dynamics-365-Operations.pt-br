---
title: Tipos de solicitação de manutenção
description: Este artigo explica como configurar uma solicitação de manutenção no Gerenciamento de Ativos.
author: johanhoffmann
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0a2d707cc9c0aa4863968651a8434883cc1322eb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8888691"
---
# <a name="maintenance-request-types"></a>Tipos de solicitação de manutenção

[!include [banner](../../includes/banner.md)]

 

Os tipos de solicitação de manutenção são usados para categorizar solicitações de manutenção. Por exemplo, você pode ter os tipos de solicitação de manutenção relacionados à manutenção preventiva e manutenção corretiva. Ou pode ter um tipo especial de solicitação de manutenção que é usado para gerenciar o reparo de ativos (reparo de depósito).

Um tipo do solicitação de manutenção define a afiliação ao grupo de estados de ciclo de vida da solicitação de manutenção (modelo do ciclo de vida de manutenção). Os modelos de ciclo de vida de solicitação de manutenção definem os estados de ciclo de vida que podem ser definidos para uma solicitação de manutenção. (Os exemplos dos estados de ciclo de vida de solicitação de manutenção incluem **Criado**, **Ativo** e **Concluído**).

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Solicitações de manutenção** \> **Tipos de solicitação de manutenção**.
2. Selecione **Novo** para criar um tipo de solicitação de manutenção.
3. No campo **Tipo de solicitação de manutenção** , insira uma ID para o tipo de solicitação de manutenção.
4. No campo **Nome**, insira um nome.
5. Na Guia Rápida **Geral**, no campo **Modelo de ciclo de vida de solicitação de manutenção** , selecione um modelo de ciclo de vida de solicitação de manutenção.
6. No campo **Tipo de ordem de serviço**, selecione um tipo de ordem de serviço. Quando uma solicitação de manutenção é convertida em uma ordem de serviço, a ordem de serviço obtém automaticamente o tipo de ordem de serviço relacionado ao tipo de solicitação de manutenção.

A ilustração a seguir mostra um exemplo da página **Tipos de solicitação de manutenção**.

![Página de tipos de solicitação de manutenção.](media/07-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]