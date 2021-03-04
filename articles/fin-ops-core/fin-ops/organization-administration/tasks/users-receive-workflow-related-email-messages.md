---
title: Permitir que usuários recebam mensagens de email relacionadas a fluxo de trabalho
description: Você pode configurar o sistema para enviar mensagens de email para os usuários quando ocorrerem eventos relacionados a fluxo de trabalho.
author: jasongre
manager: AnnBe
ms.date: 06/01/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5b7a953ea54286a7e48b392728d2cc9bb2902072
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "4692809"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a>Permitir que usuários recebam mensagens de email relacionadas a fluxo de trabalho

[!include [banner](../../includes/banner.md)]

Você pode configurar o sistema para enviar mensagens de email para os usuários quando ocorrerem eventos relacionados a fluxo de trabalho. Por exemplo, as mensagens de email poderão ser enviadas aos usuários quando documentos forem atribuídos a eles para aprovação. A empresa de dados demo usada para criar este procedimento é USMF.

1. Vá para **Painel de navegação > Módulos > Administração do sistema > Usuários > Usuários**.
2. Na lista, localize e selecione o registro desejado.
3. No **Painel de ação**, clique em **Opções de usuário**.
4. Clique na guia **Fluxo de trabalho**. Verifique se a seção **Notificações** está expandida. Na seção **Notificações**, você pode especificar como deseja que o usuário seja notificado sobre eventos relacionados a fluxo de trabalho.  
5. No campo **Tipo de notificação de fluxo de trabalho de item de linha**, selecione uma opção.
    - Agrupado – As notificações para itens de linha são agrupadas em uma única mensagem de email.
    - Individual – Uma mensagem de email é enviada para cada item de linha.  
    - Se quiser que o usuário receba notificações no cliente, marque a caixa de seleção **Enviar notificações no email**.  
6. Clique em **Salvar**.
7. Feche a página.

> [!NOTE]
> Os modelos de email do fluxo de trabalho serão originados de modelos de email do sistema ou modelos de email da organização, dependendo de o fluxo de trabalho ser um fluxo de trabalho no nível do sistema (não específico da empresa) ou no nível organizacional (específico da empresa).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]