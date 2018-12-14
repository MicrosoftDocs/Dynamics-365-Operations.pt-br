---
title: Incorporar Aplicativos PowerApps no Core HR
description: "Este tópico explica como resolver o problema onde o item de menu do PowerApps desapareceu do módulo de administração do sistema."
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
ms.openlocfilehash: 197b553f0b202ee29ad42274e2c0e03446ec782c
ms.contentlocale: pt-br
ms.lasthandoff: 12/04/2018

---

# <a name="embed-powerapps-apps-in-core-hr"></a>Incorporar Aplicativos PowerApps no Core HR

[!include [banner](includes/banner.md)]

**Saída**

O item de menu **PowerApps** desapareceu do módulo de **Administração do sistema**.

**Causa**

O design de interface de usuário (IU) foi alterado, e Microsoft PowerApps agora está incluído no modelo de personalização padrão.

**Resolução**

A maneira como os aplicativos do PowerApps são integrados, mudou. Os aplicativos de PowerApps agora estão adicionados por meio do modelo de personalização. Você pode adicionar aplicativos do PowerApps a quase todas as páginas no Microsoft Dynamics 365 for Talent.

Para obter informações sobre como inserir um aplicativo PowerApps no Talent, consulte [Aplicativos do PowerApps integrados](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).

Qualquer cliente do PowerApps que adicionou aplicativos antes da mudança deve ter recebido e atualizado para o novo modelo.

O botão **PowerApps** está no canto superior direito de quase todas as páginas do Talent. Você pode usar este botão para inserir um aplicativo do PowerApps.

Veja aqui um exemplo.

1. Acesse **Gerenciamento de equipe \> Links \> Trabalhadores \> Funcionários**.
2. Selecione o botão **PowerApps**, e depois selecione **Inserir um PowerApp**.

    ![Botão do PowerApps](media/png.png)

3. Preencha os campos na caixa de diálogo **Inserir um PowerApp**.

    ![Inserir uma caixa de diálogo do PowerApp](media/insert-powerapp.png)

Alternativamente, siga estas etapas.

1. No painel de ação da página, na guia **Opções**, no grupo **Personalizar**, selecione **Personalizar esse formulário**.

    ![Personalizar grupo na guia Opções](media/options.png)

    A barra de ferramentas de personalização aparece.

2. Na barra de ferramentas, selecione **Inserir \> PowerApp**.

    ![Inserir um aplicativo do PowerApps usando a barra de ferramentas de personalização](media/powerapp-bar.png)

