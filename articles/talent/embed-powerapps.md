---
title: Inserir aplicativos PowerApps no Dynamics 365 - Core HR
description: Este tópico explica como resolver o problema quando o item do menu PowerApps desapareceu do módulo de administração do sistema.
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
ms.openlocfilehash: 4fbc24c5ceb73389b84b125eb942ac31757928aa
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008421"
---
# <a name="embed-powerapps-apps-in-core-hr"></a>Inserir aplicativos PowerApps no Core HR

[!include [banner](includes/banner.md)]

**Emissão**

O item de menu **PowerApps** desapareceu do módulo de **Administração do sistema**.

**Causa**

O design de interface de usuário (IU) foi alterado, e agora o Microsoft PowerApps está incluído no modelo de personalização padrão.

**Resolução**

A maneira como os aplicativos PowerApps são inseridos mudou. Os aplicativos PowerApps agora são adicionados por meio do modelo de personalização. Você pode adicionar aplicativos PowerApps a quase todas as páginas do Microsoft Dynamics 365 Talent.

Para obter informações sobre como inserir aplicativos PowerApps no Talent, consulte [Inserir aplicativos PowerApps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).

Qualquer cliente do PowerApps que inseriu aplicativos antes da mudança deve ter sido atualizado para o novo modelo.

O botão **PowerApps** fica no canto superior direito de quase todas as páginas do Talent. Você pode usar esse botão para inserir um aplicativo PowerApps.

Veja aqui um exemplo.

1. Acesse **Gerenciamento de equipe \> Links \> Trabalhadores \> Funcionários**.
2. Selecione o botão **PowerApps** e selecione **Inserir um PowerApp**.

    ![Botão PowerApps](media/png.png)

3. Preencha os campos na caixa de diálogo **Inserir um PowerApp**.

    ![Inserir uma caixa de diálogo do PowerApp](media/insert-powerapp.png)

Alternativamente, siga estas etapas.

1. No painel de ação da página, na guia **Opções**, no grupo **Personalizar**, selecione **Personalizar esse formulário**.

    ![Personalizar grupo na guia Opções](media/options.png)

    A barra de ferramentas de personalização aparece.

2. Na barra de ferramentas, selecione **Inserir \> PowerApp**.

    ![Inserir um aplicativo PowerApps usando a barra de ferramentas de personalização](media/powerapp-bar.png)
