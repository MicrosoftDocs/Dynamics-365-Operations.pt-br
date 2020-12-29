---
title: O Human Resources não aparece nos aplicativos do Microsoft Dynamics 365
description: Este artigo explica o que fazer se o cliente não vir o aplicativo Microsoft Dynamics 365 Human Resources entre os aplicativos do Microsoft Dynamics 365.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cbf47b4673e1c97965bba7728e5669b7639c4d56
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4417262"
---
# <a name="human-resources-doesnt-appear-in-microsoft-dynamics-365-apps"></a>O Human Resources não aparece nos aplicativos do Microsoft Dynamics 365

**Emissão**

O cliente não verá o Dynamics 365 Human Resources entre os aplicativos do Microsoft Dynamics 365.

**Resolução**

O usuário deve ser adicionado à função de criador de ambiente do ambiente no Microsoft Power Apps.

1. O usuário administrador com uma licença de plano de Power Apps 2 deverá abrir o [Portal de administrador do Power Apps](https://preview.admin.powerapps.com/).

2. Selecione **Ambientes** e o ambiente correto para Human Resources.

3. Na guia **Segurança**, na guia **Funções de ambiente**, selecione **Criador de ambiente**.

    ![Funções da guia de ambiente](media/environment-roles.png)

4. Na guia **Usuários**, adicione o usuário ou a organização.

    ![Tabela de usuários](media/environment-maker.png)

5. Selecione **Salvar**.

6. O usuário agora deve entrar no [Microsoft Dynamics 365](https://home.dynamics.com/).

7. Selecione **Sincronizar** para atualizar os aplicativos do usuário.

    ![Botão de sincronização](media/get-more.png)

    Após a sincronização ser concluída, Human Resources aparecerá na página inicial.
