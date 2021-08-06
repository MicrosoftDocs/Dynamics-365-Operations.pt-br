---
title: Módulo de reprodutor de vídeo
description: Este tópico abrange os módulos de exibição e descreve como adicioná-los às páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: caf45eda4ad0e7140097cb856a6ef0a65d7ecba9
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2021
ms.locfileid: "6638112"
---
# <a name="video-player-module"></a>Módulo de reprodutor de vídeo

[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de exibição e descreve como adicioná-los às páginas de site no Microsoft Dynamics 365 Commerce.

O módulo de player de vídeo é usado para dar suporte à reprodução de vídeo. Ele pode ser adicionado a qualquer página, desde que o conteúdo de vídeo seja carregado e disponibilizado no sistema de gerenciamento de conteúdo (CMS). O módulo de player de vídeo oferece suporte para o tipo de mídia. mp4.

## <a name="video-player-module"></a>Módulo de reprodutor de vídeo

O módulo de reprodução de vídeo pode ser usado para exibir vídeos em um site comercial online. Ele é compatível com todas as funcionalidades de reprodução, como reproduzir, pausar, modo tela cheia, descrições de áudio e legendas. O módulo de exibição de vídeo também oferece suporte à personalização de legendas atender aos padrões de acessibilidade da Microsoft. Por exemplo, você pode personalizar o tamanho da fonte e a cor de plano de fundo.

O módulo player de vídeo também oferece suporte a faixas de áudio secundárias. Quando um vídeo é carregado no CMS, uma trilha de áudio secundária também pode ser carregada. O módulo de reprodutor de vídeo pode reproduzir a trilha de áudio secundária se um usuário selecioná-la.

### <a name="examples-of-video-player-modules-in-e-commerce"></a>Exemplos de módulos de reprodutor de vídeo no comércio online

- Vídeos instrutivas sobre a página de detalhes de produto ou páginas de marketing
- Vídeos promocionais ou vídeos sobre políticas em qualquer página de marketing
- Vídeos de marketing que destacam recursos de produto em páginas de detalhes de produto ou páginas de marketing

A imagem a seguir mostra um exemplo de módulo de reprodutor de vídeo em uma home page.

![Exemplo de módulo de reprodutor de vídeo.](./media/ecommerce-videoplayer.PNG)

### <a name="video-player-module-properties"></a>Propriedades de módulo de reprodutor de vídeo

| Nome da propriedade         | Alíquota                               | descrição |
|-----------------------|-------------------------------------|-------------|
| Título               | Texto do cabeçalho e tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Por padrão, a tag de cabeçalho **H2** é usada, mas a tag do cabeçalho pode ser alterada para atender aos requisitos de acessibilidade. |
| Rich text             | Texto de parágrafo | O módulo oferece suporte a texto de parágrafo em formato rich text. Alguns recursos básicos de rich text são compatíveis, como negrito, sublinhado, itálico e hiperlinks. Alguns desses recursos podem ser substituídos pelo tema da página aplicado ao módulo. |
| Vincular                  | Texto do link, URL do link, rótulo ARIA (Accessible Rich Internet Applications) e seletor **Abrir link em uma nova guia** | O módulo oferece suporte a um ou mais links de "chamada à ação". Se um link for adicionado, será necessário o texto do link, uma URL e uma etiqueta ARIA. As etiquetas ARIA devem ser descritivas para atender aos requisitos de acessibilidade. Os links podem ser configurados para serem abertos em uma nova guia. |
| Subtexto              | Título, texto ou links | É possível adicionar um contexto adicional para o módulo de player de vídeo, como um autor ou nome de designer, ou links para Blogs pessoais. |
| Reprodução automática             | **Verdadeiro** ou **Falso**               | Quando o valor é definido como **Verdadeiro**, o vídeo é executado automaticamente. |
| Ativar Mudo                  | **Verdadeiro** ou **Falso**               | Quando o valor é definido como **Verdadeiro**, o áudio fica no mudo. Para esse reprodutor, o valor padrão é **Falso**. No navegador do Chrome, vídeos reproduzidos automaticamente são mudos por padrão e o áudio é reproduzido apenas se o usuário reproduzir manualmente o vídeo. |
| Loop                  | **Verdadeiro** ou **Falso**               | Quando o valor é definido como **Verdadeiro**, o vídeo é repetido em um loop. |
| Mídia                 | Caminho e nome do arquivo de vídeo | O arquivo de vídeo é reproduzido pelo reprodutor de vídeo. |
| Reproduzir em tela cheia       | **Verdadeiro** ou **Falso**               | Quando o valor é definido como **Verdadeiro**, o vídeo é exibido no modo tela cheia. |
| Disparador da pausa de reprodução    | **Verdadeiro** ou **Falso**               | Quando o valor é definido como **Verdadeiro**, o botão reproduzir/pausa será mostrado no vídeo. |
| Controles do player de vídeo | **Verdadeiro** ou **Falso**               | Quando o valor é definido como **Verdadeiro**, todos os controles do player de vídeo são exibidos. Esses controles incluem botões de reprodução e pausa, um indicador de progresso e opções de legenda. |
| Ocultar imagem do pôster     | **Verdadeiro** ou **Falso**               | Uma vídeo pode ter uma borda. Quando o valor desta propriedade é definido como **Verdadeiro**, a borda fica oculta. |
| Nível de máscara            | Um número de **0** a **100** | A máscara aplicada ao vídeo para estilo. |

> [!IMPORTANT]
> As propriedades **Cabeçalho**, **Rich Text**, **Link** e **Subtexto** estão disponíveis a partir da versão 10.0.20 do Dynamics 365 Commerce.

## <a name="add-a-video-player-module-to-a-page"></a>Adicionar um módulo de reprodutor de vídeo à página

> [!NOTE] 
> Antes de criar um módulo de player de vídeo, primeiro você deve carregar um vídeo na Biblioteca de Mídia.

Para adicionar um módulo de reprodução de vídeo a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Vá para **Modelos** e selecione **Novo** para criar um novo modelo.
1. Na caixa de diálogo **Novo Modelo**, em **Nome do modelo**, insira **Modelo de reprodutor de vídeo** e selecione **OK**.
1. No slot **Corpo**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Página Padrão** e, depois, **OK**.
1. No slot **Principal** do módulo **Página Padrão**, selecione as reticências (**...**) e, em seguida, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Contêiner** e, depois, **OK**.
1. No slot **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Reprodutor de vídeo** e, depois, **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo. 
1. Vá para **Páginas** e selecione **Novo** para criar uma nova página.
1. Na caixa de diálogo **Escolher um modelo**, selecione o modelo de reprodutor de vídeo que você criou. Em **Nome da página**, insira **Página do reprodutor de vídeo** e selecione **OK**.
1. No slot **Principal** da nova página, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Contêiner** e, depois, **OK**.
1. No slot **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Reprodutor de vídeo** e, depois, **OK**.
1. No painel de propriedades do módulo de reprodutor de vídeo, selecione **Adicionar um vídeo**.
1. Na caixa de diálogo **Seletor de Mídia**, selecione um vídeo e clique em **Carregar novo item de mídia**.
1. No explorador de arquivos, selecione um arquivo de vídeo e **Abrir**.
1. Na caixa de diálogo **Carregar item de mídia**, insira um título e outras informações, conforme necessário, e selecione **OK**.
1. Na caixa de diálogo **Seletor de Mídia**, selecione **Fechar**.
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página. Você deve ver o módulo de vídeo na página. Você pode alterar outras configurações para personalizar o comportamento do módulo.
1. Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo. 

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de banner de promoção](add-alert.md)

[Módulo do carrossel](add-carousel.md)

[Módulo de bloco de texto](add-content-rich-block.md)

[Módulo de bloco de conteúdo](add-hero-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
