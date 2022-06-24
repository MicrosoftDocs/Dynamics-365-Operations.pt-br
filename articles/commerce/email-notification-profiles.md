---
title: Configurar perfil de notificação por email
description: Este artigo descreve como criar um perfil de notificação de email no Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 02/11/2022
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
ms.openlocfilehash: 109adcc4e8b49c665bd14ecab2b7cc56cebd2291
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878477"
---
# <a name="set-up-an-email-notification-profile"></a>Configurar perfil de notificação por email

[!include [banner](includes/banner.md)]

Este artigo descreve como criar um perfil de notificação de email no Microsoft Dynamics 365 Commerce.

Ao criar canais, você pode configurar um perfil de notificação por email. O perfil de notificação por email define os eventos de uma transação de venda (como ordem criada, pacote de ordens e eventos faturados de ordem) para os quais você enviará notificações aos clientes. 

Para obter informações adicionais sobre como configurar o email, consulte [Configurar e enviar email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).

## <a name="create-an-email-notification-profile"></a>Criar perfil de notificação por email

Para criar um perfil de notificação por email, siga estas etapas.

1. No painel de navegação, Acesse **Módulos \> Retail e Commerce \> Configuração do headquarters \> Perfil de notificação por email do Commerce**.
1. No painel de ações, clique em **Novo**.
1. No campo **Perfil de notificação por email**, insira um nome para identificar o perfil.
1. No campo **Descrição**, insira uma descrição relevante.
1. Defina a alternância **Ativo** como **Sim**.

### <a name="create-an-email-template"></a>Criar um modelo de email

Antes que um tipo de notificação por email possa ser habilitado, você deve criar um modelo de email de organização no Commerce headquarters. Este modelo define o assunto do email, o remetente, o idioma padrão e o corpo do email para cada idioma com suporte.

Para criar um modelo de email, siga estas etapas.

1. No painel de navegação, Acesse **Módulos \> Retail e Commerce \> Configuração do headquarters \> Parâmetros \> Modelos de email da organização**.
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

Para obter mais informações sobre como criar modelos de email, consulte [Criar modelos de email para eventos transacionais](email-templates-transactions.md). 

### <a name="create-an-email-event"></a>Criar um evento de email

Para criar um evento de email, siga estas etapas.

1. No painel de navegação, Acesse **Módulos \> Retail e Commerce \> Configuração do headquarters \> Perfil de notificação por email do Commerce**.
1. Na lista, localize e selecione o registro desejado. 
1. Selecione o modelo de email na lista suspensa **ID do Email**.
1. Selecione o **Tipo de notificação por email** apropriado na lista suspensa.
1. Marque a caixa de seleção **Ativo**.
1. No painel de ação, selecione **Salvar**.

A imagem a seguir mostra alguns exemplos de configurações de notificação de evento.

![Configurações de notificação de evento.](media/email-notification-profile.png)

> [!NOTE]
> O tipo de notificação criado pelo cliente exige uma personalização a ser implementada para que uma notificação por email possa ser enviada.

### <a name="schedule-a-recurring-email-notification-process-job"></a>Agendar um trabalho de processo de notificação por email recorrente

Para enviar notificações por email, o trabalho **Processar notificação por email da ordem de varejo** deve estar em execução.

Para configurar o trabalho **Processar notificação por email da ordem de varejo** no Commerce headquarters, se ainda não fez isso, siga estas etapas.

1. Acesse **Varejo e Comércio \> TI de Varejo e Comércio \> Email e notificações \> Enviar notificação por email**.
1. Na caixa de diálogo **Processar notificação por email da ordem de varejo**, selecione **Recorrência**.
1. Na caixa de diálogo **Definir recorrência**, selecione **Sem data de término**.
1. Em **Padrão de recorrência**, selecione **Minutos** e defina o campo **Contagem** como **1**. Essas configurações garantirão que as notificações por email serão processadas o mais rápido possível.
1. Selecione **OK** para voltar à caixa de diálogo **Processar notificação por email da ordem de varejo**.
1. Selecione **OK** para concluir a configuração do trabalho.

### <a name="next-steps"></a>Próximas etapas

Para poder enviar emails, você deve configurar seu serviço de email de saída e configurar um trabalho em lotes. Para obter mais informações, consulte [Configurar e enviar email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).

## <a name="additional-resources"></a>Recursos adicionais

[Configurar e enviar email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[Visão geral de canais](channels-overview.md)

[Pré-requisitos de configuração de canal](channels-prerequisites.md)

[Visão geral de organizações e hierarquias organizacionais](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
