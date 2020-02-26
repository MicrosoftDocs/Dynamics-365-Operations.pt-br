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
ms.openlocfilehash: d39e6ef4168f08f20b92979a296ed088744ad0da
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008164"
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
