---
title: Adicionar uma nova página do site
description: Este artigo descreve como adicionar uma nova página de site no Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 02/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: f6714463c9d5dc844b03f78f0f6ff60c5f270da3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270309"
---
# <a name="add-a-new-site-page"></a>Adicionar uma nova página do site

[!include [banner](includes/banner.md)]

Este artigo descreve como adicionar uma nova página de site no Microsoft Dynamics 365 Commerce.

Após a criação de modelos e fragmentos para o seu site, a próxima etapa é começar a criar páginas que os utilizam. Para começar, você deve selecionar um modelo ou layout, um nome de página e uma URL de página.

## <a name="template-or-layout"></a>Modelo ou layout

Você pode usar um modelo ou um layout para sua nova página. Para obter mais informações, consulte [Visão geral de modelos e layouts](templates-layouts-overview.md).

## <a name="specify-the-page-name"></a>Especifique o nome da página

O nome da página deve exclusivo do seu site e descritivo para permitir a fácil localização e para que outras pessoas saibam para que serve a página. Você pode renomear a página posteriormente editando-a e, depois, selecionando o símbolo da caneta ao lado do nome da página no painel de propriedades.

## <a name="specify-the-page-url"></a>Especifique a URL da página

Você pode ter a opção de inserir uma URL para sua nova página. Ao criar uma página, você poderá inserir uma sequência de caracteres que será usada para formar uma URL completa. Essa sequência de caracteres é conhecida como URL relativa ou campo de dados dinâmico de URL. Uma URL completa é então gerada com base no campo de dados dinâmico da URL e a nova página é atribuída a ele. Você poderá alterar o campo de dados dinâmico da URL posteriormente, antes de publicar a página. Para obter mais informações, consulte [Criar uma URL da página](create-page-URL.md).

> [!NOTE]
> O Dynamics 365 Commerce dissocia URLs e conteúdo. Em outras palavras, é possível criar uma página que não esteja associada a uma URL e criar uma URL que não esteja associado a uma página. Portanto, a troca de conteúdo pode ser feita para uma URL e não requer tempo de inatividade, e os redirecionamentos são mais fáceis de gerenciar.

## <a name="add-a-new-page"></a>Adicionar uma nova página

Para adicionar uma nova página ao site, siga estas etapas.

1. Em **Sites**, selecione **Fabrikam** (ou o nome do seu site).
1. Selecione **Nova página**.
1. Na caixa de diálogo **Nova página**, selecione um modelo e depois **OK**.
1. No campo **Nome da página**, insira um nome de página (por exemplo, **Minha nova página**).
1. No campo **URL**, insira uma sequência de caracteres (campo de dados dinâmico da URL) para concluir a URL (por exemplo, **mynewpage**).
1. Selecione **OK**. O editor de páginas é exibido. Observe que um cabeçalho e um rodapé são adicionados automaticamente à página, com base no modelo que você selecionou.
1. Na descrição da página, selecione o slot **Principal**, selecione o botão de reticências (**...**) e selecione **Adicionar módulo**.
1. Selecione **Contêiner** e, depois, **OK**.
1. Selecione **Contêiner fluido**, selecione o botão de reticências e selecione **Adicionar módulo**.
1. Selecione **Bloco de conteúdo sofisticado** e selecione **OK**.
1. Selecione **Bloco de conteúdo sofisticado**, selecione o botão de reticências e selecione **Adicionar módulo**.
1. Selecione **Item de bloco de conteúdo sofisticado** e selecione **OK**.
1. No painel de propriedades à direita, selecione **Parágrafo** e, no campo, digite **Meu texto de teste**.
1. Selecione **Salvar** e **Finalizar edição**.
1. No campo **Comentários**, insira **Adicionou nova página** e depois selecione **OK**.
1. Selecione **Visualizar** para exibir a página. Quando terminar, feche a guia de visualização para retornar à ferramenta de criação.
1. Selecione **Publicar**.
1. No caminho de navegação (trilha de navegação), selecione **Fabrikam** (ou o nome do seu site).
1. No painel de navegação à esquerda, selecione **URLs**.
1. Encontre e selecione sua URL (**mynewpage**) na lista.
1. Selecione **Publicar**.

## <a name="additional-resources"></a>Recursos adicionais

[Modificar uma página de site existente](modify-existing-page.md)

[Selecionar layouts de página](select-page-layouts.md)

[Gerenciar metadados de SEO](manage-seo-metadata.md)

[Salvar, visualizar, e publicar uma página](save-preview-publish-page.md)

[Enriquecer uma página de produto](enrich-product-page.md)

[Enriquecer uma página de aterrissagem da categoria](enrich-category-page.md)

[Verificar acessibilidade do conteúdo da página](verify-accessibility.md)

[Criar páginas dinâmicas de comércio eletrônico com base nos parâmetros da URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
