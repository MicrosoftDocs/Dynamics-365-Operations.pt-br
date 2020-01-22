---
title: Adicionar uma nova página do site
description: Este tópico descreve como adicionar uma nova página de site no Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 10/01/2019
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1993e58108ad73aad4adf382bb03ec2e62231add
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945596"
---
# <a name="add-a-new-site-page"></a>Adicionar uma nova página do site

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico descreve como adicionar uma nova página de site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Após a criação de modelos e fragmentos para o seu site, a próxima etapa é começar a criar páginas que os utilizam. Para começar, você deve selecionar um modelo ou layout, um nome de página e uma URL de página.

## <a name="template-or-layout"></a>Modelo ou layout

Você pode usar um modelo ou um layout para sua nova página. Para obter mais informações, consulte [Visão geral de modelos e layouts](templates-layouts-overview.md).

## <a name="page-name"></a>Nome da página

O nome da página deve ser exclusivo para sua página. Deve ser descritivo, para que você possa encontrá-lo facilmente e outras pessoas saibam para que serve a página. Escolha o nome da página com cuidado, porque não pode ser alterado posteriormente.

## <a name="page-url"></a>URL da página

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
1. Selecione **Salvar** e **Fazer Check-in**.
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

[Verificar acessibilidade de conteúdo da página](verify-accessibility.md)
