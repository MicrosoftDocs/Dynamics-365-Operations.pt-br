---
title: Configurar perfil de notificação por email
description: Este tópico descreve como criar um perfil de notificação de email no Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 320f21916a5f451ebf4f21e0075017a121ba6d6a
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057605"
---
# <a name="set-up-an-email-notification-profile"></a>Configurar perfil de notificação por email


[!include [banner](includes/banner.md)]

Este tópico descreve como criar um perfil de notificação de email no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Antes de criar canais, configure um perfil para garantir que as notificações de email possam ser enviadas para vários eventos, como criação da ordem, status da remessa da ordem e falha do pagamento.

Para obter informações adicionais sobre como configurar o email, consulte [Configurar e enviar email](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-email).

## <a name="create-an-email-notification-profile"></a>Criar perfil de notificação por email

Para criar um perfil de notificação por email, siga estas etapas.

1. No painel de navegação, vá para **Módulos \> Retail e Commerce \> Configuração do Headquarters \> Perfil de notificação por email do Commerce**.
1. No painel de ações, clique em **Novo**.
1. No campo **Perfil de notificação por email**, insira um nome para identificar o perfil.
1. No campo **Descrição**, insira uma descrição relevante.
1. Defina a alternância **Ativo** como **Sim**.

### <a name="create-an-email-template"></a>Criar um modelo de email

Antes que uma notificação por email possa ser criada, é necessário criar um modelo de email da organização contendo as informações de email dos remetentes e o modelo de email.

Para criar um modelo de email, siga estas etapas.

1. No painel de navegação, vá para **Módulos \> Retail e Commerce \> Configuração do Headquarters \> Parâmetros \> Modelos de email da organização**.
1. No painel de ação, selecione **Novo**.
1. No campo **ID do email**, insira uma ID para ajudar a identificar este modelo.
1. No campo **Nome do remetente**, digite o nome do remetente.
1. No campo **Descrição do Email**, insira uma descrição significativa.
1. No campo **Email do remetente**, insira o endereço de email do remetente.
1. Na seção **Geral**, preencha todas as informações opcionais necessárias (como a prioridade de email).
1. Expanda a seção **Conteúdo da mensagem de email** e selecione **Novo** para criar o conteúdo do modelo. Para cada item de conteúdo, selecione o idioma e forneça a linha de assunto do email. Se o email tiver um corpo, certifique-se de que a caixa **Tem corpo** esteja selecionada.
1. No painel de ações, selecione **Mensagem do email** para fornecer um modelo de corpo de email.

A imagem a seguir mostra alguns exemplos de configurações de modelo de email.

![Configurações de modelo de email](media/email-template.png)

### <a name="create-an-email-event"></a>Criar um evento de email

Para criar um evento de email, siga estas etapas.

1. No painel de navegação, vá para **Módulos \> Retail e Commerce \> Configuração do Headquarters \> Perfil de notificação por email do Commerce**.
1. Na lista, localize e selecione o registro desejado. 
1. Selecione o modelo de email na lista suspensa **ID do Email**.
1. Selecione o **Tipo de notificação por email** apropriado na lista suspensa.
1. Marque a caixa de seleção **Ativo**.
1. No painel de ação, selecione **Salvar**.

A imagem a seguir mostra alguns exemplos de configurações de notificação de evento.

![Configurações de notificação de evento](media/email-notification-profile.png)

## <a name="additional-resources"></a>Recursos adicionais

[Configurar e enviar email](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-email)

[Visão geral de canais](channels-overview.md)

[Pré-requisitos de configuração de canal](channels-prerequisites.md)

[Visão geral de organizações e hierarquias organizacionais](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
