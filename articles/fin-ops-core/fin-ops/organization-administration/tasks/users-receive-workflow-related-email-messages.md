---
title: Permitir que usuários recebam mensagens de email relacionadas a fluxo de trabalho
description: Você pode configurar o sistema para enviar mensagens de email para os usuários quando ocorrerem eventos relacionados a fluxo de trabalho.
author: jasongre
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5e08f95ef6d263ee0f8c0a94b258c8a2795786bc
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189835"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a>Permitir que usuários recebam mensagens de email relacionadas a fluxo de trabalho

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

