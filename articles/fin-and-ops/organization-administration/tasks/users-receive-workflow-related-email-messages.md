--- 
title: "Configurar o sistema para enviar aos usuários email relacionado ao fluxo de trabalho"
description: "Você pode configurar o sistema para enviar mensagens de email para os usuários quando ocorrerem eventos relacionados a fluxo de trabalho."
author: jasongre
manager: AnnBe
ms.date: 02/21/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 04d90c9ded1ba7fb1ceac4ff1d54f54f6c43f9e9
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---
# <a name="configure-the-system-to-send-workflow-related-email-to-users"></a>Configurar o sistema para enviar aos usuários email relacionado ao fluxo de trabalho

[!include [task guide banner](../../includes/task-guide-banner.md)]

Você pode configurar o sistema para enviar mensagens de email para os usuários quando ocorrerem eventos relacionados a fluxo de trabalho. Por exemplo, as mensagens de email poderão ser enviadas aos usuários quando documentos forem atribuídos a eles para aprovação. A empresa de dados demo usada para criar este procedimento é USMF.

1. Vá para Administração do sistema > Usuários > Usuários.
2. Na lista, localize e selecione o PDV desejado.
3. Clique em Opções do usuário.
4. Clique na guia Fluxo de trabalho.
    * Certifique-se de que a seção Notificações está expandida.     Na seção Notificações, você pode especificar como deseja que o usuário seja notificado sobre eventos relacionados a fluxo de trabalho.  
5. No campo Tipo de notificação de fluxo de trabalho de item de linha, selecione uma opção.
    * Agrupado – As notificações para itens de linha são agrupadas em uma única mensagem de email.    Individual – Uma mensagem de email é enviada para cada item de linha.  
    * Se quiser que o usuário receba notificações no cliente, marque a caixa de seleção Enviar notificações no email.  
6. Clique em Salvar.
7. Feche a página.


