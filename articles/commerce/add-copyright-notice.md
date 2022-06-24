---
title: Adicionar um aviso de direitos autorais
description: Este artigo descreve como adicionar um aviso de direitos autorais ao seu site de comércio eletrônico.
author: psimolin
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a1e394b9a582b48c44bbec26ef42a90d50918f87
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851180"
---
# <a name="add-a-copyright-notice"></a>Adicionar um aviso de direitos autorais

[!include [banner](includes/banner.md)]

Este artigo descreve como adicionar um aviso de direitos autorais ao seu site de comércio eletrônico.

## <a name="prerequisites"></a>Pré-requisitos

Antes de adicionar um aviso de direitos autorais ao seu site, você deve ter os seguintes itens:

- Um modelo que inclui um fragmento de rodapé compartilhado.
- Uma página que usa esse modelo.

## <a name="add-a-copyright-notice"></a>Adicionar um aviso de direitos autorais

Para adicionar um aviso de direitos autorais na parte inferior de cada página que usa um modelo específico, siga as etapas a seguir.

1. Acesse **Fragmentos** e selecione **Novo**.
1. Na caixa de diálogo **Novo fragmento**, selecione o módulo **Rodapé** e nomeie o fragmento. Por exemplo, insira **Footer-Copyright**.
1. Selecione **OK**.
1. No painel de navegação, selecione o botão de reticências (**...**) ao lado de **Rodapé** e depois **Adicionar módulo**.
1. Na caixa de diálogo, selecione **Categoria de rodapé** e depois **OK**.
1. No painel de navegação, selecione o botão de reticências ao lado de **Categoria de rodapé** e depois **Adicionar módulo**.
1. Na caixa de diálogo, selecione **Bloco de texto** e depois **OK**.
1. No painel de navegação, selecione **Bloco de texto**.
1. No painel de propriedades à direita, no campo **Parágrafo**, adicione sua mensagem de direitos autorais. Por exemplo, insira **(C) Fabrikam 2019**.
1. Selecione **Salvar**, **Concluir a edição** e depois **Publicar**.
1. Acesse **Modelos**, selecione o modelo e depois **Editar**.
1. Em **Estrutura de Tópicos da Página**, expanda **Corpo** e depois **Página Padrão**.
1. Selecione o botão de reticências ao lado de **Slot de rodapé** e depois escolha **Adicionar fragmento**.
1. Selecione o fragmento que você criou antes e escolha **Selecionar**.
1. Selecione **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.

O rodapé que contém o aviso de direitos autorais aparece automaticamente na parte inferior de todas as páginas que usam o modelo selecionado.

## <a name="additional-resources"></a>Recursos adicionais

[Adicionar um logotipo](add-logo.md)

[Selecionar um tema de site](select-site-theme.md)

[Trabalhar com arquivos de substituição CSS](css-override-files.md)

[Adicionar um favicon](add-favicon.md)

[Adicionar idiomas ao seu site](add-languages-to-site.md)

[Adicionar o código de script a páginas do site para oferecer suporte à telemetria](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
