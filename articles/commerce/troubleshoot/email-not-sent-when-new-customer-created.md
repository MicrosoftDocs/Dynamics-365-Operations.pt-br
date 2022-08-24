---
title: O email de boas-vindas não é enviado quando clientes são criados
description: Este artigo fornece orientações de solução de problemas que podem ajudar se uma notificação de email de boas-vindas não for enviada quando um novo cliente for criado no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 08/01/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-02-10
ms.openlocfilehash: 5aa7d864555f96194500989e2d7ad200d8892121
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2022
ms.locfileid: "9219395"
---
# <a name="welcome-email-isnt-sent-when-new-customers-are-created"></a>O email de boas-vindas não é enviado quando são criados novos clientes

[!include [banner](../../includes/banner.md)]

Este artigo fornece orientações de solução de problemas que podem ajudar se uma notificação de email de boas-vindas não for enviada quando um novo cliente for criado no Microsoft Dynamics 365 Commerce.

## <a name="description"></a>Descrição

Quando um novo cliente é criado no Commerce headquarters, um email de boas-vindas não é enviado para o cliente, mesmo que uma notificação de email seja configurada para o tipo de notificação de email **Criado pelo cliente**.

## <a name="resolution"></a>Resolução

### <a name="associate-an-email-notification-profile-under-commerce-parameters"></a>Associe um perfil de notificação por email a parâmetros do Commerce

1. No headquarters, acesse **Retail e Commerce \> Configuração do headquarters \> Parâmetros \> Parâmetros do Commerce \> Geral**.
2. Na lista suspensa **Perfil de notificação por e-mail**, selecione o perfil de notificação por email que contém um mapeamento entre o tipo de notificação criado pelo cliente e um modelo de email criado pelo cliente.  

> [!NOTE] 
> Ao habilitar notificações criadas pelo cliente, os clientes criados em todos os canais da entidade legal receberão um cliente criado por email. No momento, as notificações criadas pelo cliente não podem ser limitadas a um único canal.

Para obter mais informações, consulte [Criar modelos de email para eventos transacionais](../email-templates-transactions.md). 

## <a name="additional-resources"></a>Recursos adicionais

[Configurar perfil de notificação por email](../email-notification-profiles.md)
