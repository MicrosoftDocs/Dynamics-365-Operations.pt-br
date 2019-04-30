---
title: O Talent não aparece entre os aplicativos do Microsoft Dynamics 365 (Common Data Service 1.0)
description: Este tópico explica o que fazer se o cliente não vir o aplicativo Microsoft Dynamics 365 for Talent entre os aplicativos do Microsoft Dynamics 365.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: ad5add2b572ccb6bff175806b965f63b53986152
ms.sourcegitcommit: 45b79d1e587e03f5cde2766cdec4eaa7a2a897a3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2019
ms.locfileid: "949773"
---
# <a name="talent-doesnt-appear-among-the-microsoft-dynamics-365-apps-common-data-service-10"></a>O Talent não aparece entre os aplicativos do Microsoft Dynamics 365 (Common Data Service 1.0)

[!include [banner](includes/banner.md)]

**Saída**

O cliente não encontrar o aplicativo Microsoft Dynamics 365 for Talent entre os aplicativos do Microsoft Dynamics 365.

**Resolução**

O usuário deve ser adicionado à função de criador de ambiente do ambiente no Microsoft PowerApps.

1. O usuário admin com uma licença de plano de PowerApps 2 deverá abrir [Portal de admin do PowerApps](https://preview.admin.powerapps.com/).
2. Selecione **Ambientes**, e selecione o ambiente atual de Talent.
3. Na guia **Segurança**, na guia **Funções de ambiente**, selecione **Criador de ambiente**.

    ![Funções da guia de ambiente](media/environment-roles.png)

4. Na guia **Usuários**, adicione o usuário ou a organização.

    ![Tabela de usuários](media/environment-maker.png)

5. Selecione **Salvar**.
6. O usuário agora deve entrar no [Microsoft Dynamics 365](https://home.dynamics.com/).
7. Selecione **Sincronizar** para atualizar os aplicativos do usuário.

    ![Botão de sincronização](media/get-more.png)

    Após a sincronização ser concluída, Talent aparecerá na página inicial.
