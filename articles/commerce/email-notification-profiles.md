---
title: Configurar perfil de notificação por email
description: Este tópico descreve como criar um perfil de notificação de email no Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 03/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: ac58ea4f1dfd8208c1c2f78e36d82d1375475413
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6349511"
---
# <a name="set-up-an-email-notification-profile"></a>Configurar perfil de notificação por email

[!include [banner](includes/banner.md)]

Este tópico descreve como criar um perfil de notificação de email no Microsoft Dynamics 365 Commerce.

Ao criar canais, você pode configurar um perfil de notificação por email. Dessa forma, os emails podem ser enviados para os clientes por vários eventos transacionais, como a criação da ordem, o status de remessa da ordem e a falha de pagamento.

Para obter informações adicionais sobre como configurar o email, consulte [Configurar e enviar email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).

## <a name="create-an-email-notification-profile"></a>Criar perfil de notificação por email

Para criar um perfil de notificação por email, siga estas etapas.

1. No painel de navegação, vá para **Módulos \> Retail e Commerce \> Configuração do Headquarters \> Perfil de notificação por email do Commerce**.
1. No painel de ações, clique em **Novo**.
1. No campo **Perfil de notificação por email**, insira um nome para identificar o perfil.
1. No campo **Descrição**, insira uma descrição relevante.
1. Defina a alternância **Ativo** como **Sim**.

### <a name="create-an-email-template"></a>Criar um modelo de email

Antes que um tipo de notificação por email possa ser habilitado, você deve criar um modelo de email de organização no Commerce Headquarters. Este modelo define o assunto do email, o remetente, o idioma padrão e o corpo do email para cada idioma para o qual você deseja oferecer suporte.

Para criar um modelo de email, siga estas etapas.

1. No painel de navegação, vá para **Módulos \> Retail e Commerce \> Configuração do Headquarters \> Parâmetros \> Modelos de email da organização**.
1. No painel de ação, selecione **Novo**.
1. No campo **ID do email**, insira uma ID para ajudar a identificar este modelo.
1. No campo **Nome do remetente**, digite o nome do remetente.
1. No campo **Descrição do Email**, insira uma descrição significativa.
1. No campo **Email do remetente**, insira o endereço de email do remetente.
1. Na seção **Geral**, selecione um idioma padrão para o modelo de email. O idioma padrão será usado quando não existir nenhum modelo localizado para o idioma especificado.
1. Expanda a seção **Conteúdo da mensagem de email** e selecione **Novo** para criar o conteúdo do modelo. Para cada item de conteúdo, selecione o idioma e forneça a linha de assunto do email. Se o email tiver um corpo, certifique-se de que a caixa **Tem corpo** esteja selecionada.
1. No painel de ações, selecione **Mensagem do email** para fornecer um modelo de corpo de email.

A imagem a seguir mostra alguns exemplos de configurações de modelo de email.

![Configurações de modelo de email.](media/email-template.png)

### <a name="create-an-email-event"></a>Criar um evento de email

Para criar um evento de email, siga estas etapas.

1. No painel de navegação, vá para **Módulos \> Retail e Commerce \> Configuração do Headquarters \> Perfil de notificação por email do Commerce**.
1. Na lista, localize e selecione o registro desejado. 
1. Selecione o modelo de email na lista suspensa **ID do Email**.
1. Selecione o **Tipo de notificação por email** apropriado na lista suspensa.
1. Marque a caixa de seleção **Ativo**.
1. No painel de ação, selecione **Salvar**.

A imagem a seguir mostra alguns exemplos de configurações de notificação de evento.

![Configurações de notificação de evento.](media/email-notification-profile.png)

### <a name="next-steps"></a>Próximas etapas

Para poder enviar emails, você deve configurar seu serviço de email de saída e configurar um trabalho em lotes. Para obter mais informações, consulte [Configurar e enviar email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).


## <a name="additional-resources"></a>Recursos adicionais

[Configurar e enviar email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[Visão geral de canais](channels-overview.md)

[Pré-requisitos de configuração de canal](channels-prerequisites.md)

[Visão geral de organizações e hierarquias organizacionais](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
