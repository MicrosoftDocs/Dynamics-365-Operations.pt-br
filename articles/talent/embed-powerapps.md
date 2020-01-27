---
title: Inserir aplicativos Power Apps no Dynamics 365 - Core HR
description: Este tópico explica como resolver o problema quando o item do menu Microsoft Power Apps desapareceu do módulo de administração do sistema.
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
ms.openlocfilehash: b1dd1756be349d85af8e6d7159623a2a95e75526
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898703"
---
# <a name="embed-power-apps-apps-in-dynamics-365---core-hr"></a>Inserir aplicativos Power Apps no Dynamics 365 - Core HR

**Emissão**

O item de menu **Power Apps** desapareceu do módulo de **Administração do sistema**.

**Causa**

O design de interface de usuário (IU) foi alterado, e agora o Microsoft Power Apps está incluído no modelo de personalização padrão.

**Resolução**

A maneira como os Power Apps são inseridos mudou. Agora os Power Apps são adicionados por meio do modelo de personalização. Você pode adicionar Power Apps a quase todas as páginas do Microsoft Dynamics 365 Talent.

Para obter informações sobre como inserir Power Apps no Talent, consulte [Inserir o Microsoft Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).

Qualquer cliente do Power Apps que inseriu aplicativos antes da mudança deve ter sido atualizado para o novo modelo.

O botão **Power Apps** fica no canto superior direito de quase todas as páginas do Talent. Você pode usar esse botão para inserir Power Apps.

Veja aqui um exemplo.

1. Acesse **Gerenciamento de equipe \> Links \> Trabalhadores \> Funcionários**.
2. Selecione o botão **Power Apps** e selecione **Inserir um PowerApp**.

    ![Botão Power Apps](media/png.png)

3. Preencha os campos na caixa de diálogo **Inserir um PowerApp**.

    ![Inserir uma caixa de diálogo do PowerApp](media/insert-powerapp.png)

Alternativamente, siga estas etapas.

1. No painel de ação da página, na guia **Opções**, no grupo **Personalizar**, selecione **Personalizar esse formulário**.

    ![Personalizar grupo na guia Opções](media/options.png)

    A barra de ferramentas de personalização aparece.

2. Na barra de ferramentas, selecione **Inserir \> PowerApp**.

    ![Inserir um aplicativo Power Apps usando a barra de ferramentas de personalização](media/powerapp-bar.png)
