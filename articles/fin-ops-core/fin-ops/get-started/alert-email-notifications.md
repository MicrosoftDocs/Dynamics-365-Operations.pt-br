---
title: Notificações de alerta do cliente por email
description: Este artigo fornece informações sobre como configurar regras que enviarão notificações por email se ocorrerem eventos predefinidos.
author: RichdiMSFT
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: richdi
ms.search.validFrom: 2019-1-29
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 469c7fdda40780d6e559819103d73d7a4e7132a1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878268"
---
# <a name="client-alert-notifications-by-email"></a>Notificações de alerta do cliente por email

[!include [banner](../includes/banner.md)]

Você pode definir regras de alerta personalizadas que monitoram exibições filtradas de dados e enviam notificações por email automaticamente quando ocorrerem eventos predefinidos. A opção para enviar notificações por email está disponível para todos os tipos de alerta com suporte e você também pode ativá-la para regras de alertas existentes.

Você pode usar controles internos para criar regras de alerta que monitoram as exibições filtradas de trabalhos em lotes do sistema. Monitorando o valor do campo **Status**, você também pode configurar regras de alerta que enviam email quando há falha em um trabalho em lotes. Depois de criar essas regras de alerta, você não precisará verificar os relatórios de alterações nos dados comerciais. Em vez disso, deixe que o serviço de detecção inteligente de alterações faça o monitoramento por você.

Os alertas de cliente dependem do subsistema de email fornecido por meio da integração com o Microsoft Office. É recomendável usar o provedor de protocolo SMTP (Simple Mail Transfer Protocol), para que a distribuição de email que não tenha que depender de um cliente de email local.

Para enviar notificações por email, os clientes devem configurar serviços de email integrado. As notificações por email são enviadas aos destinatários em nome dos proprietários dos alertas.

Para obter mais informações sobre como configurar o email, consulte [Configurar e enviar email](../organization-administration/configure-email.md).

A imagem a seguir mostra a caixa de diálogo **Criar regra de alerta**, que agora inclui uma opção **Enviar email**.

[![Criar a caixa de diálogo da regra de alerta em que a opção Enviar email esteja definida como Sim.](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)

> [!NOTE]
> Quando a opção **Enviar email** estiver definida como **Sim**, as notificações de alerta continuarão a ser enviadas da Central de Ações.

## <a name="alert-notification-email-templates"></a>Modelos de email de notificação de alerta

O serviço envia notificações por email usando modelos predefinidos de email que fornecem os detalhes básicos da notificação de alerta.

A imagem a seguir mostra a estrutura das notificações de alerta quando elas são recebidas por email.

[![Notificações de alerta baseadas em modelo para a criação de registros, alterações de campo e exclusão de modelos.](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]