---
title: O Human Resources não aparece nos aplicativos do Microsoft Dynamics 365
description: Este artigo explica o que fazer se o Microsoft Dynamics 365 Human Resources não estiver listado entre os aplicativos do Microsoft Dynamics 365.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2d520ac06bcc0990714929c0fdd622516eda5f30
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872229"
---
# <a name="human-resources-app-doesnt-appear-in-microsoft-dynamics-365-apps"></a>O aplicativo Human Resources não aparece no Microsoft Dynamics 365


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Problema**

O cliente não verá o Dynamics 365 Human Resources entre os aplicativos do Microsoft Dynamics 365.

**Resolução**

O usuário deve ser adicionado à função de criador de ambiente do ambiente no Microsoft Power Apps.

1. O usuário administrador com uma licença de plano de Power Apps 2 deverá abrir o [Portal de administrador do Power Apps](https://preview.admin.powerapps.com/).

2. Selecione **Ambientes** e o ambiente correto para Human Resources.

3. Na guia **Segurança**, na guia **Funções de ambiente**, selecione **Criador de ambiente**.

    ![Funções da guia de ambiente.](media/environment-roles.png)

4. Na guia **Usuários**, adicione o usuário ou a organização.

    ![Tabela de usuários.](media/environment-maker.png)

5. Selecione **Salvar**.

6. O usuário agora deve entrar no [Microsoft Dynamics 365](https://home.dynamics.com/).

7. Selecione **Sincronizar** para atualizar os aplicativos do usuário.

    ![Botão de sincronização.](media/get-more.png)

    Após a sincronização ser concluída, Human Resources aparecerá na página inicial.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
