---
title: O email de boas-vindas não é enviado quando clientes são criados
description: Este tópico fornece orientações de solução de problemas que podem ajudar se uma notificação de email de boas-vindas não for enviada quando um novo cliente for criado no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-02-10
ms.openlocfilehash: 1a4faf6cd189f69232e7f9ab8d0e79b320cfe2d9
ms.sourcegitcommit: d2e5d38ed1550287b12c90331fc4136ed546b14c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8349940"
---
# <a name="welcome-email-is-not-sent-when-new-customers-are-created"></a>O email de boas-vindas não é enviado quando clientes são criados

[!include [banner](../../includes/banner.md)]

Este tópico fornece orientações de solução de problemas que podem ajudar se uma notificação de email de boas-vindas não for enviada quando um novo cliente for criado no Microsoft Dynamics 365 Commerce.

## <a name="description"></a>Descrição

Quando um novo cliente é criado na sede do Commerce, um email de boas-vindas não é enviado para o cliente, mesmo que uma notificação de email seja configurada para o tipo de notificação de email **Criado pelo cliente**.

## <a name="resolution"></a>Resolução

### <a name="set-the-correct-email-id-value-for-the-customer-created-email-notification-type"></a>Definir o valor correto da ID de email para o tipo de notificação por email criado pelo cliente

Para definir o valor **ID de email** correto para o tipo de notificação de email **Criado pelo cliente** na sede, siga estas etapas.

1. Acesse **Retail e Commerce \> Configuração do Headquarters \> Perfil de notificação de email do Commerce**.
1. No painel de navegação esquerdo, selecione o módulo de coleta de produtos.
1. Em **Configurações de notificações de eventos do Retail**, para o tipo de notificação de email **Criado pelo cliente**, defina o campo **ID de email** como **NewCust**.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar perfil de notificação por email](../email-notification-profiles.md)
