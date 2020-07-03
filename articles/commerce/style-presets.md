---
title: Trabalhar com estilos predefinidos
description: Este tópico descreve como trabalhar com layouts predefinidos de site no Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b972c1de9f110ffb1ee1a52d9a9a1e3fa3fd9513
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411505"
---
# <a name="work-with-style-presets"></a>Trabalhar com estilos predefinidos

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico descreve como trabalhar com layouts predefinidos de site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

Uma predefinição de estilo é um conjunto armazenado de todos os valores de estilo que pode ser criado no tema de um site. Ele pode ser usado para alterar imediatamente a aparência de um site do construtor de sites. As predefinições de estilo permitem que o criador de sites do Commerce altere, visualize e ative rapidamente um conjunto de valores de estilo no site sem a necessidade de usar folhas de estilo em cascata (CSS) ou implantar temas. Estilos de fonte, estilos de botão e cores de site são exemplos típicos de variáveis de estilo que podem ser gerenciadas por meio de predefinições de estilo.

O conjunto de variáveis de estilo que está disponível em um site é determinado pelo tema e pela biblioteca de módulos que é implantado para o locatário de um site. O kit de desenvolvimento de software (SDK) online do Dynamics 365 Commerce permite que os desenvolvedores implementem o máximo (ou o mínimo) de variáveis de estilo que podem ser criadas quanto forem necessárias para um determinado tema. Ao habilitar mais variáveis de estilo, um desenvolvedor de temas poderá colocar as escolhas finais sobre os estilos de site nas mãos dos autores do construtor de sites. Portanto, os não desenvolvedores podem atualizar e visualizar estilos de site usando o conjunto de ferramentas. O recurso também é útil para qualquer cenário no qual as alterações diretas nos temas ou CSS causarão sobrecarga desnecessária.

Os temas nos quais as variáveis de estilo são habilitadas exigem uma predefinição de estilo padrão. Opcionalmente, eles podem incluir opções de predefinição adicionais como parte de um pacote de tema implantado. Por exemplo, um tema pode ser implantado e ter uma única predefinição de estilo padrão de "luz moderna". Como alternativa, ele pode incluir opções de predefinição de estilo adicionais além da predefinição padrão, como "escuro moderno", "claro vintage" ou "escuro vintage". Essas predefinições de tema internas são criadas por desenvolvedores e podem ser usadas como pontos de partida para novos designs de site.

No construtor de sites, os autores podem selecionar entre as predefinições internas de um tema ou podem criar suas próprias predefinições e personalizações de estilo usando as variáveis de estilo habilitadas. Uma predefinição de estilo pode ser visualizada no construtor de sites antes de ser ativada no site ao vivo. Depois que as alterações de estilo do autor forem revisadas, a predefinição de estilo poderá, então, ser definida como "ativa" para o site ao vivo.

## <a name="preview-a-style-preset"></a>Visualizar uma predefinição de estilo

Para visualizar uma predefinição de estilo no seu site no construtor de sites, siga estas etapas.

1. No painel de navegação esquerdo do site, vá para **Configurações do Site \> Design**.
1. Na guia **Predefinições de estilo** na parte superior do editor de design, na lista **Predefinições disponíveis**, selecione uma predefinição e, em seguida, selecione **Exibir** para ir para o editor de predefinições.

    No momento, se não houver predefinições na lista **Predefinições disponíveis**, consulte [Criar uma predefinição de estilo personalizada](#create-a-custom-style-preset) para obter informações sobre como criar uma predefinição de estilo personalizada.

    > [!NOTE]
    > As predefinições incluídas no tema são indicadas por um emblema **Interno**. Essas predefinições internas são somente leitura. Para copiar uma predefinição interna como uma nova predefinição personalizável, selecione o botão de reticências (**...**) para a predefinição e selecione **Calvar como**.

1. Na barra de comandos, selecione **Visualização**.
1. Selecione uma URL do site a ser usada para visualizar a predefinição de estilo e, em seguida, selecione **OK**.
1. Selecione a variante de URL específica do canal e da localidade a ser visualizada selecionando o nome da variante. Uma nova janela de visualização do navegador é aberta, na qual a predefinição de estilo selecionada é aplicada à página especificada.

> [!NOTE]
> A URL de visualização é persistente e autenticada. Portanto, você pode copiá-la, colá-la e enviá-la a outros colaboradores autenticados para revisão antes de defini-la como "ativa" no seu site ao vivo. A URL de visualização também é útil para verificar estilos em diferentes dispositivos, em navegadores diferentes e em telas diferentes.

> [!TIP]
> Enquanto você edita uma predefinição de estilo, pode ser útil deixar a janela de visualização do navegador aberta em uma janela separada do navegador, para que você possa validar rapidamente suas alterações. Depois de salvar as alterações em uma predefinição, atualize a janela do navegador de visualização para validar a experiência do usuário.

## <a name="create-a-custom-style-preset"></a>Criar uma predefinição de estilo personalizada

Para criar uma predefinição de estilo personalizada no construtor de sites, siga estas etapas.

1. No painel de navegação esquerdo do site, vá para **Configurações do Site \> Design**.
1. Na guia **Predefinições de estilo** na parte superior do editor de design, na barra de comandos, selecione **Nova predefinição**.
1. Insira um nome e um descrição para a nova predefinição e selecione **Salvar**. É criada uma nova predefinição personalizável que usa os valores padrão do tema como ponto de partida.

> [!NOTE]
> Você também pode criar uma nova predefinição de estilo personalizado de qualquer predefinição existente, selecionando o botão de reticências (**...**) para essa predefinição e selecionando **Salvar como**. Como alternativa, selecione **Salvar como** na barra de comandos no editor de predefinições.

## <a name="modify-global-and-module-type-style-values"></a>Modificar valores de estilo de tipo global e de módulo

Algumas variáveis de estilo de um tema são compartilhadas entre vários tipos de módulo. Essas variáveis de estilo são mencionadas como variáveis de estilo *globais*. Exemplos incluem cores de site principal, estilos de fonte padrão e estilos de botão. Ao definir variáveis globais, você poderá alterar a aparência entre vários tipos diferentes de módulo.

Alguns valores de estilo podem ser exclusivos para um tipo de módulo, ou talvez precisem substituir um valor global padrão. Se o tema de um site tiver implementado variáveis de estilo de tipo de módulo, os autores do construtor de sites poderão personalizar o estilo de um tipo de módulo independentemente das configurações globais. As variáveis de tipo de módulo podem aumentar ou substituir as variáveis de estilo globais em um tema.

> [!NOTE]
> A hierarquia de valores de estilo em um site se comporta da seguinte maneira. Os valores de estilo que aparecem mais distantes da direita substituem os valores de estilo à esquerda deles.
>
> Valores padrão do tema \< Valores de estilo globais \< Valores de estilo de tipo de módulo \< Substituição de CSS

Para alterar os valores de tipo global ou de módulo de uma predefinição de estilo no construtor de sites, siga estas etapas.

1. No painel de navegação esquerdo do site, vá para **Configurações do Site \> Design**.
1. Na guia **Predefinições de estilo** na parte superior do editor de design, selecione **Exibir** para qualquer predefinição de estilo para ir para o editor de predefinições.
1. Selecione **Visualização** e, em seguida, siga as etapas de seleção da URL para abrir uma visualização de janela inteira do navegador para a predefinição. Deixe esta janela de visualização do navegador aberta.
1. No editor de predefinições, selecione **Editar** no canto superior direito.
1. Use os controles de variável de estilo no editor para alterar alguns valores de estilo global.
1. Na parte superior do editor, na guia **Módulos** à direita da guia **Global**, selecione um tipo de módulo que deve ser estilizado.
1. Use os controles de estilo para alterar alguns valores para o tipo de módulo.
1. Quando estiver pronto para visualizar as alterações, selecione **Salvar** na barra de comandos.
1. Retorne à janela de visualização do navegador aberta e atualize-a. A visualização de tela inteira do navegador é útil para verificar alterações de estilo em diferentes pontos de quebra de exibição, em diferentes navegadores e em diferentes plataformas de dispositivos.
1. Quando todas as alterações tiverem sido concluídas e validadas, selecione **Terminar edição** no canto superior direito do editor.

> [!NOTE]
> Se você estiver editando a predefinição de estilo atualmente ativa no seu site, verá um emblema **Ativo** azul no editor. Esse emblema indica que a predefinição está atualmente ativa no seu site. Se você alterar a predefinição ativa, selecione **Publicar** para enviar essas alterações ao seu site ao vivo.

## <a name="make-a-new-style-preset-active-on-your-live-site"></a>Tornar uma nova predefinição de estilo ativa no seu site ao vivo

Para definir uma predefinição de estilo como a nova predefinição ativa no seu site, siga estas etapas.

- Selecione o **botão Definir como ativo** em um dos seguintes locais:

    - A barra de comandos no editor de predefinição de estilo
    - O menu de reticências (**...**) para qualquer predefinição disponível na exibição principal da guia **Predefinições de estilo** em **Configurações do Site \> Design**

Os valores de estilo da predefinição são ativados no seu site público.

## <a name="additional-resources"></a>Recursos adicionais

[Adicionar um logotipo](add-logo.md)

[Selecionar um tema de site](select-site-theme.md)

[Trabalhar com arquivos de substituição CSS](css-override-files.md)

[Adicionar um favicon](add-favicon.md)

[Adicionar uma mensagem de boas-vindas](add-welcome-message.md)

[Adicionar um aviso de direitos autorais](add-copyright-notice.md)

[Adicionar idiomas ao seu site](add-languages-to-site.md)

[Adicionar o código de script a páginas do site para oferecer suporte à telemetria](add-telemetry.md)
