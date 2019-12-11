---
title: Adicionar um aviso de direitos autorais
description: Este tópico descreve como adicionar um aviso de direitos autorais ao seu site de comércio eletrônico.
author: psimolin
manager: AnnBe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 39135a2eca25336097ee9eddf06dc6709c102571
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2696936"
---
# <a name="add-a-copyright-notice"></a>Adicionar um aviso de direitos autorais

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico descreve como adicionar um aviso de direitos autorais ao seu site de comércio eletrônico.

## <a name="prerequisites"></a>Pré-requisitos

Antes de adicionar um aviso de direitos autorais ao seu site, você deve ter os seguintes itens:

- Um modelo que inclui um fragmento de rodapé compartilhado.
- Uma página que usa esse modelo.

## <a name="add-a-copyright-notice"></a>Adicionar um aviso de direitos autorais

Para adicionar um aviso de direitos autorais na parte inferior de cada página que usa um modelo específico, siga as etapas a seguir.

1. Vá para **Fragmentos** e selecione **Novo Fragmento de Página**.
1. Na caixa de diálogo, selecione o módulo **Rodapé** e nomeie o fragmento. Por exemplo, insira **Footer-Copyright**.
1. Selecione **OK**.
1. No painel de navegação, selecione o botão de reticências (**...**) ao lado de **Rodapé** e depois **Adicionar módulo**.
1. Na caixa de diálogo, selecione **Categoria de rodapé** e depois **OK**.
1. No painel de navegação, selecione o botão de reticências ao lado de **Categoria de rodapé** e depois **Adicionar módulo**.
1. Na caixa de diálogo, selecione **Item de bloco de conteúdo sofisticado** e depois **OK**.
1. No painel de navegação, selecione **Item de bloco de conteúdo sofisticado**.
1. No painel de propriedades à direita, no campo **Parágrafo**, adicione sua mensagem de direitos autorais. Por exemplo, insira **(C) Fabrikam 2019**.
1. Selecione **Save**, **Fazer Check-in** e depois **Publicar**.
1. Vá para **Modelos**, selecione o modelo e depois **Fazer Check-out**.
1. Em **Estrutura de Tópicos da Página**, expanda **Corpo** e depois **Página Padrão**.
1. Selecione o botão de reticências ao lado de **Slot de rodapé** e depois escolha **Adicionar fragmento**.
1. Selecione o fragmento que você criou antes e escolha **Selecionar**.
1. Faça check-in do modelo e publique-o.

O rodapé que contém o aviso de direitos autorais aparece automaticamente na parte inferior de todas as páginas que usam o modelo selecionado.

## <a name="additional-resources"></a>Recursos adicionais

[Adicionar um logotipo](add-logo.md)

[Selecionar um tema de site](select-site-theme.md)

[Adicionar um favicon](add-favicon.md)

[Adicionar uma mensagem de boas-vindas](add-welcome-message.md)

[Adicionar idiomas ao seu site](add-languages-to-site.md)

[Adicionar o código de script a páginas do site para oferecer suporte à telemetria](add-telemetry.md)

