---
title: "Talent não aparece entre os aplicativos do Microsoft Dynamics 365 (CDS1.0)"
description: "Este tópico explica o que fazer se o cliente não vir o aplicativo Microsoft Dynamics 365 for Talent entre os aplicativos do Microsoft Dynamics 365."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 32ae0ab807e953bd811a557e6878b9bee79d293c
ms.contentlocale: pt-br
ms.lasthandoff: 12/04/2018

---

# <a name="talent-doesnt-appear-among-the-microsoft-dynamics-365-apps-cds10"></a>Talent não aparece entre os aplicativos do Microsoft Dynamics 365 (CDS1.0)

[!include [banner](includes/banner.md)]

**Saída**

O cliente não vir o aplicativo Microsoft Dynamics 365 for Talent entre os aplicativos do Microsoft Dynamics 365.

**Resolução**

O usuário deve ser adicionado à função de criador de ambiente do ambiente no Microsoft PowerApps.

1. O usuário admin com uma licença de plano de PowerApps 2 deverá abrir [Portal de admin do PowerApps](https://preview.admin.powerapps.com/).
2. Selecione **Ambientes**, e selecione o ambiente atual de Talent.
3. Na guia **Segurança**, na guia **Funções de ambiente**, selecione **Criador de ambiente**.

    ![Funções da guia de ambiente](media/environment-roles.png)

4. Na guia **Usuários**, adicione o usuário ou a organização.

    ![Tabela de usuários](media/environment-maker.png)

5. Selecione **Salvar**.
6. O usuário agora deve se conectar ao [Microsoft Dynamics 365](https://home.dynamics.com/).
7. Selecione **Sincronizar** para atualizar os aplicativos do usuário.

    ![Botão de sincronização](media/get-more.png)

    Após a sincronização ser concluída, Talent aparecerá na página inicial.

