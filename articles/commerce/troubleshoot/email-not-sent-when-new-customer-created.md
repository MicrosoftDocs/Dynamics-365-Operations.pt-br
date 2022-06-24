---
title: O email de boas-vindas não é enviado quando clientes são criados
description: Este artigo fornece orientações de solução de problemas que podem ajudar se uma notificação de email de boas-vindas não for enviada quando um novo cliente for criado no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-02-10
ms.openlocfilehash: 8e95b33d4b8a9af13c613ab89dd33de6b4934694
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853674"
---
# <a name="welcome-email-is-not-sent-when-new-customers-are-created"></a>O email de boas-vindas não é enviado quando clientes são criados

[!include [banner](../../includes/banner.md)]

Este artigo fornece orientações de solução de problemas que podem ajudar se uma notificação de email de boas-vindas não for enviada quando um novo cliente for criado no Microsoft Dynamics 365 Commerce.

## <a name="description"></a>Descrição

Quando um novo cliente é criado no Commerce headquarters, um email de boas-vindas não é enviado para o cliente, mesmo que uma notificação de email seja configurada para o tipo de notificação de email **Criado pelo cliente**.

## <a name="resolution"></a>Resolução

### <a name="set-the-correct-email-id-value-for-the-customer-created-email-notification-type"></a>Definir o valor correto da ID de email para o tipo de notificação por email criado pelo cliente

Para definir o valor **ID de email** correto para o tipo de notificação de email **Criado pelo cliente** no headquarters, siga estas etapas.

1. Acesse **Retail e Commerce \> Configuração do headquarters \> Perfil de notificação de email do Commerce**.
1. No painel de navegação esquerdo, selecione o módulo de coleta de produtos.
1. Em **Configurações de notificações de eventos do Retail**, para o tipo de notificação de email **Criado pelo cliente**, defina o campo **ID de email** como **NewCust**.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar perfil de notificação por email](../email-notification-profiles.md)
