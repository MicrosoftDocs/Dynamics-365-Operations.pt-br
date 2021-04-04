---
title: Permitir que usuários recebam mensagens de email relacionadas a fluxo de trabalho
description: Você pode configurar o sistema para enviar mensagens de email para os usuários quando ocorrerem eventos relacionados a fluxo de trabalho.
author: jasongre
manager: AnnBe
ms.date: 06/01/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9a81e01c36081ce7131ee65344f583755fa3bfd3
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564181"
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