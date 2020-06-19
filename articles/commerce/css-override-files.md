---
title: Trabalhar com arquivos de substituição CSS
description: Este tópico descreve porque, quando e como usar Folhas de Estilos em Cascata (CSS) substituem arquivos no Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-12-12
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 3ec43b16b1df07400cffe597378ad4035e4d07e0
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411238"
---
# <a name="work-with-css-override-files"></a>Trabalhar com arquivos de substituição CSS


[!include [banner](includes/banner.md)]

Este tópico descreve porque, quando e como usar Folhas de Estilos em Cascata (CSS) substituem arquivos no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Normalmente, os estilos de site permanentes devem ser manipulados por meio do tema de um site. Os temas fornecem as configurações base de CSS e estilo para os módulos em qualquer página do seu site. Os temas são criados usando o kit de desenvolvimento de software Dynamics 365 Commerce online (SDK) e são implantados em seus sites por meio do Lifecycle Services (LCS) do Microsoft Dynamics. Recursos de depuração de tema e configurações de interface de módulo nos desenvolvedores de site da ajuda do SDK criam pacotes de design de site personalizáveis e coesos. Quando esses pacotes de design são implantados em um site, os autores do site podem se concentrar na criação, na edição e na publicação de conteúdo, e não no desenvolvimento do site.

Devido ao ciclo de vida normal de um tema, a dependência dos desenvolvedores de fazer alterações de estilo por meio do pipeline de implantação do SDK e do LCS pode ser proibitiva em alguns cenários. Os protótipos de site ou hotfixes podem parecer complicados se o SDK não estiver configurado ou se você não tiver tempo para esperar por uma implantação do LCS.

Nessas situações, arquivos de substituição do CSS podem ajudar. Nas ferramentas de criação do Commerce, os usuários autenticados podem carregar um arquivo CSS, visualizá-lo e depois ativá-lo para substituir o tema de um site. A sobrecarga da implantação do SDK ou LCS não é necessária. As substituições especificadas em um arquivo de substituição do CSS podem ser tão pequenas quanto uma alteração em um único estilo de texto ou como uma revisão de marca completa.

Antes de usar os arquivos de substituição CSS, esteja ciente das seguintes limitações:

- Somente um arquivo de substituição CSS pode estar ativo em um site de cada vez. Portanto, todas as substituições ativas devem estar presentes em um único arquivo de substituição.
- Embora seja possível visualizar as substituições nas ferramentas de criação do Commerce, não há recursos de depuração dedicados para ajudar a identificar os bugs introduzidos por essas substituições. Em outras palavras, ao usar os arquivos de substituição CSS, você não tem o mesmo conjunto de ferramentas que o SDK oferece para validação de módulo e criação de páginas.

No entanto, os arquivos de substituição CSS fornecem uma maneira rápida de criar um protótipo de um projeto ou implementar um hotfix antes que uma atualização de tema completa seja desenvolvida e implantada.

## <a name="create-a-css-override-file"></a>Criar um arquivo de substituição do CSS

Para criar um arquivo de substituição CSS, você pode usar qualquer ambiente de desenvolvimento integrado (IDE), editor de texto ou editor de código fonte. Uma abordagem típica é usar os depuradores da Web padrão no seu navegador para identificar seletores de estilo, propriedades e valores no site existente. A maioria dos navegadores permite que você altere valores e visualize-os no depurador. Depois de identificar as alterações que deseja fazer, você pode salvá-las no seu próprio arquivo CSS.

## <a name="upload-a-css-override-file"></a>Carregar um arquivo de substituição CSS

Para carregar um arquivo CSS em seu site no Commerce, siga estas etapas.

1. Nas ferramentas de criação, vá para nosso site.
1. No painel de navegação à esquerda, selecione **Design**.

    > [!NOTE]
    > Dependendo da versão das ferramentas de criação do Commerce que você está usando, talvez você precise expandir **Configurações** no painel de navegação antes de poder selecionar **Design**.

1. Na parte superior do painel de design principal, selecione a guia **Substituir CSS**, caso ainda não esteja selecionada.
1. Under **Substituição de CSS disponível**, selecione **Carregar arquivo CSS**. Uma janela do explorador de arquivos é exibida.
1. No explorador de arquivos, procure e selecione um arquivo CSS e depois selecione **Abrir**. O arquivo carregado CSS agora aparece em **Substituição de CSS disponível**.

## <a name="preview-a-css-override-file"></a>Visualizar um arquivo de substituição CSS

Para visualizar um arquivo de substituição CSS antes de torná-lo ativo no seu site ao vivo, siga estas etapas.

1. No painel de navegação à esquerda, selecione **Design**, e depois, na guia **Substituição de CSS**, em **Substituição de CSS disponível**, encontra o arquivo CSS que deseja visualizar.
1. Ao lado do nome do arquivo do CSS, selecione **Visualizar site**.
1. Na caixa de seleção **Selecionar uma URL**, selecione a URL do site no qual você deseja que a substituição seja aplicada, e selecione **OK**.
1. Se houver várias grades para a URL selecionada, selecione a grade desejada na caixa de diálogo **Visualizar grades** exibida.

Uma nova guia ou janela do navegador é aberta, na qual você pode validar suas substituições de estilo no site. Em seguida, você poderá compartilhar a URL com outros usuários autenticados do Commerce para revisão e comentários.

## <a name="activate-a-css-override-file-on-your-live-site"></a>Ativar um arquivo de substituição CSS no site ao vivo

Depois de exibir e aprovar o arquivo de substituição CSS, você poderá ativá-lo no seu site.

> [!NOTE]
> Somente um arquivo de substituição CSS pode estar ativo em seu site de cada vez. Se você ativar um novo arquivo de substituição, o arquivo de substituição anterior será desativado. Portanto, verifique se todas as substituições necessárias estão presentes em um único arquivo de substituição CSS.

Para ativar um arquivo de substituição CSS, siga estas etapas.

1. No painel de navegação à esquerda, selecione **Design**, e depois, na guia **Substituição de CSS**, em **Substituição de CSS disponível**, encontra o arquivo CSS que deseja ativar.
1. No nome do arquivo CSS, selecione **Ativar**. O arquivo de substituição se tornará imediatamente ativo no seu site ao vivo.

## <a name="deactivate-a-css-override-file-on-your-live-site"></a>Desativar um arquivo de substituição CSS no site ao vivo

Para desativar um arquivo de substituição CSS no site, siga estas etapas.

1. No painel de navegação à esquerda, selecione **Design**, e depois, na guia **Substituição de CSS**, em **Substituição de CSS disponível**, encontra o arquivo CSS que deseja desativar.
1. No nome do arquivo CSS, selecione **Desativar**. O arquivo de substituição se tornará imediatamente inativo no seu site ao vivo.

> [!TIP]
> Para acessar opções adicionais para arquivos de substituição CSS, selecione as reticências (**...**) ao lado do nome do arquivo CSS. As opções **Baixar**, **Renomear** e **Substituir** são úteis para mudanças rápidas a um arquivo de substituição CSS existente.

## <a name="additional-resources"></a>Recursos adicionais

[Adicionar um logotipo](add-logo.md)

[Selecionar um tema de site](select-site-theme.md)

[Trabalhar com estilos predefinidos](style-presets.md)

[Adicionar um favicon](add-favicon.md)

[Adicionar uma mensagem de boas-vindas](add-welcome-message.md)

[Adicionar um aviso de direitos autorais](add-copyright-notice.md)

[Adicionar idiomas ao seu site](add-languages-to-site.md)

[Adicionar o código de script a páginas do site para oferecer suporte à telemetria](add-telemetry.md)
