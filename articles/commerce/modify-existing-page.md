---
title: Modificar uma página de site existente
description: Este tópico descreve como modificar uma página do site existente no Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/14/2020
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
ms.openlocfilehash: b633965e45c16cb4e5991fab67783b867223f6ec
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803720"
---
# <a name="modify-an-existing-site-page"></a>Modificar uma página de site existente

[!include [banner](includes/banner.md)]

Este tópico descreve como modificar uma página do site existente no Microsoft Dynamics 365 Commerce.

Quando tiver que modificar uma página, a primeira etapa é abri-la no editor de páginas. Vá para o site que contém sua página e, em seguida, na lista de páginas, localize a página que você deseja. Se você não conseguir encontrar a página, use a funcionalidade de pesquisa sofisticada da ferramenta de criação. Digite o nome exato da página, ou digite as primeiras letras dela e um asterisco (\*). Uma lista filtrada de páginas é exibida. Você pode usar essa lista para localizar a página que deseja. Depois que você encontrar a página correta, selecione o nome da página para abrir a página no editor de páginas.

> [!TIP]
> Se sua página estiver visível no inspetor de páginas, você pode selecionar **Editar** e verificar a página antes de abri-la no editor de páginas. Dessa forma, você pode fazer check-out de várias páginas ao mesmo tempo.

Depois que a página for aberta no editor de páginas, você deve garantir que fez check-out da página. A barra de comandos na ferramenta de criação é dinâmica, contextual e sensível ao estado. Portanto, ela mostra somente as ações que você pode executar atualmente na página. Por exemplo, se você não fez check-out da página, os botões **Salvar** e **Terminar edição** não aparecerão na barra de comandos. O estado da página também é mostrado no lado direito da janela.

Se ainda não foi feito o check-out da página, selecione **Editar** na barra de comandos. A barra de comandos é alterada para refletir o novo estado da página. Você também recebe uma notificação informando que a página foi submetida a check-out por você.

A próxima etapa é fazer suas alterações reais. Geralmente, você usa a árvore em destaque da página à esquerda para localizar e selecionar o módulo que deseja alterar e, em seguida, fazer alterações no painel de propriedades à direita. 

Entretanto, sua alteração pode, às vezes, envolver a adição ou remoção de modelos ou fragmentos. Para adicionar um fragmento ou módulo, use a árvore de destaque da página para localizar o slot no qual você deseja adicionar o módulo ou fragmento e, em seguida, selecione o botão de reticências (**...**) desse slot. É exibido um menu que tem comandos para adicionar um módulo ou fragmento. Para remover um módulo ou fragmento, localize e selecione-o na árvore de destaque da página, selecione o botão de reticências e o comando para excluir o módulo ou o fragmento.

> [!TIP]
> Você também pode exibir e editar as propriedades de qualquer módulo que esteja visível na visualização do construtor de página visual, selecionando-o diretamente.

Depois que terminar de fazer as alterações e visualizar seu efeito, você deve fazer check-in da página, selecionando **Terminar edição** na barra de comandos. 

Para publicar suas alterações imediatamente, selecione **Publicar** na barra de comandos. A versão da página mais recente submetida a check-in modificada é publicada e fica disponível para usuários externos que exibem seu site. 

## <a name="example-change-the-video-on-the-home-page"></a>Exemplo: Alterar o vídeo na home page

O exemplo a seguir mostra como modificar a home page alterando o vídeo que aparece no módulo do player de vídeo.

1. Em **Sites**, selecione **Fabrikam** (ou o nome do seu site).
1. No painel de navegação à esquerda, selecione **Páginas**.
1. Localize e selecione a home page para abri-la no editor de páginas.
1. Na barra de comandos, selecione **Editar**.
1. No destaque da página, selecione o slot **Principal**.
1. No slot **Principal** , expanda os módulos de contêiner fluidos.
1. Localize e selecione o módulo de player do vídeo.
1. No painel de propriedade no lado direito, selecione a propriedade **vídeo**. O seletor de ativos é exibido.
1. No seletor de ativos, selecione um ativo de vídeo disponível ou selecione **Carregar novo ativo** para carregar um novo ativo do vídeo.
1. Selecione **OK**.
1. Selecione **Salvar** e **Finalizar edição**.
1. No campo **Comentários**, insira **Alterou o vídeo** e depois selecione **OK**.
1. Selecione **Visualizar** para visualizar a página atualizada. Quando terminar, feche a guia de visualização para retornar à ferramenta de criação.
1. Selecione **Publicar**.

## <a name="additional-resources"></a>Recursos adicionais

[Adicionar uma nova página do site](add-new-page.md)

[Selecionar layouts de página](select-page-layouts.md)

[Gerenciar metadados de SEO](manage-seo-metadata.md)

[Salvar, visualizar, e publicar uma página](save-preview-publish-page.md)

[Enriquecer uma página de produto](enrich-product-page.md)

[Enriquecer uma página de aterrissagem da categoria](enrich-category-page.md)

[Verificar acessibilidade do conteúdo da página](verify-accessibility.md)

[Criar páginas dinâmicas de comércio eletrônico com base nos parâmetros da URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
