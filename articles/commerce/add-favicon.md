---
title: Adicionar um favicon
description: Este artigo explica como adicionar um favicon ao seu site.
author: bicyclingfool
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 41d6d8f823c7364f9206fd0f7588e35b6f0a018a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270428"
---
# <a name="add-a-favicon"></a>Adicionar um favicon

[!include [banner](includes/banner.md)]

Este artigo explica como adicionar um favicon ao seu site.

Um favicon é um pequeno arquivo gráfico que é mostrado em uma guia do navegador da Web, na barra de endereços, no histórico de navegação e em indicadores ou favoritos, entre outros lugares. Recomendamos que você adicione um favicon ao seu site, porque ele representa e reforça sua marca e ajuda a distinguir seu site de outros sites visitados por seus clientes.

Embora você possa adicionar vários favicons de vários tamanhos e tipos de arquivo ao seu site, este artigo mostra como adicionar um único favicon. No entanto, o mesmo processo e local são usados para adicionar mais favicons.

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a>Carregar um favicon na coleção de ativos do seu site

Para carregar um favicon na coleção de ativos do seu site, siga as etapas a seguir.

1. No painel de navegação esquerdo, selecione **Biblioteca de Mídia**.
1. Na barra de comandos, selecione **Carregar \> Carregar Itens de Mídia**.
1. Na janela do explorador de arquivos, navegue até o arquivo de imagem favicon que deseja carregar, selecione-o e, em seguida, selecione **Abrir**.
1. Na caixa de diálogo **Carregar Item de Mídia**, digite o título e o texto alt necessários.
1. Se você deseja publicar as imagens imediatamente após o carregamento, marque a caixa de seleção **Publicar itens de mídia após upload**.

    > [!NOTE]
    > Se você não marcar a caixa de diálogo **Publicar itens de mídia após upload**, será preciso retornar à página **Itens de mídia** e publicar manualmente o favicon depois.

1. Selecione **OK**.
1. No painel de propriedades à direita, copie a URL pública do favicon. Você usará essa URL posteriormente.

## <a name="create-the-html-for-your-favicon"></a>Criar o HTML do favicon

Para criar o HTML do favicon, use a seguinte cadeia de caracteres de código de HTML. No atributo **href**, substitua **URL\_pública\_para\_seu\_favicon** pela URL pública que você copiou anteriormente.

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="create-a-fragment-that-contains-a-metatag-for-your-favicon"></a>Criar um fragmento que contenha uma marca meta para o seu favicon

Para criar um fragmento que contenha uma marca meta para o seu favicon, siga estas etapas.

1. Acesse **Fragmentos** e selecione **Novo**.
1. Na caixa de diálogo **Novo fragmento**, selecione **Marcas meta** como o módulo no qual o fragmento se baseia.
1. Informe um nome para o fragmento e selecione **OK**.
1. Na árvore de hierarquia de fragmento, selecione o filho **Padrão de marcas meta**.
1. No painel à direita, em **Marcas meta**, selecione **Adicionar** e, em seguida, insira a cadeia de caracteres HTML criada anteriormente para o favicon. 
1. Selecione **Concluir edição** e, em seguida, selecione **Publicar** para publicar o fragmento.

## <a name="add-the-metatag-fragment-to-the-html-head-section-of-your-pages"></a>Adicionar o fragmento da marca meta à seção head do HTML de suas páginas

Para adicionar o fragmento da marca meta à seção **head** do HTML de suas páginas, siga estas etapas.

1. Acesse **Modelos** e abra o modelo para as páginas às quais você deseja adicionar seu favicon e seleciona **Editar**.
1. Na árvore de hierarquia de modelos, selecione o botão de reticências (**...**) à direita do contêiner **Head do HTML** e, em seguida, selecione **Adicionar fragmento**.
1. Na caixa de diálogo **Selecionar fragmento**, selecione o fragmento da marca meta criado anteriormente e, em seguida, selecione **OK**.
1. Selecione **Concluir edição** e depois selecione **Publicar** para publicar o modelo.

> [!NOTE]
> Se o site usar mais de um modelo, você deverá adicionar o fragmento de marcas meta a todos eles.

Ao visualizar páginas baseadas no modelo ao qual você adicionou o fragmento de marcas meta, você verá agora o favicon na guia do navegador.

## <a name="additional-resources"></a>Recursos adicionais

[Adicionar um logotipo](add-logo.md)

[Selecionar um tema de site](select-site-theme.md)

[Trabalhar com arquivos de substituição CSS](css-override-files.md)

[Adicionar um aviso de direitos autorais](add-copyright-notice.md)

[Adicionar idiomas ao seu site](add-languages-to-site.md)

[Adicionar o código de script a páginas do site para oferecer suporte à telemetria](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
