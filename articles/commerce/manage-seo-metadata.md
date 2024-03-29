---
title: Gerenciar metadados de SEO
description: Este artigo descreve como gerenciar metadados da otimização do mecanismo de pesquisa (SEO) no Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 04/21/2022
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
ms.openlocfilehash: 4b04d675a903279e667e1f5fcee387f05d979e81
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276819"
---
# <a name="manage-seo-metadata"></a>Gerenciar metadados de SEO

[!include [banner](includes/banner.md)]

Este artigo descreve como gerenciar metadados da otimização do mecanismo de pesquisa (SEO) no Microsoft Dynamics 365 Commerce.

Os metadados de SEO para um site podem ser gerenciados usando mapas do site e metadados da página.
    
## <a name="site-maps"></a>Mapas do site

Um mapa do site é uma lista legível por máquina, no formato XML, das páginas do seu site. Ele deve ser consumido pelos mecanismos de pesquisa, para que eles possam fornecer melhores resultados de pesquisa em seu site. Os mapas do site podem ser incorporados manualmente pelos mecanismos de pesquisa ou publicados em um arquivo robots.txt.

O Dynamics 365 Commerce oferece suporte à geração automática de mapas de site. Os mapas de site são atualizados automaticamente quando as páginas são publicadas e as publicações canceladas.

### <a name="turn-on-site-map-generation"></a>Ative a geração do mapa do site

1. Conectar-se à ferramenta de criação.
1. Em **Sites**, selecione **Fabrikam** (ou o nome do seu site).
1. No painel de navegação à esquerda, selecione **Gerenciamento de sites**.
1. Verifique se a opção **Mapas de site habilitados** está ativada.

## <a name="page-metadata"></a>Metadados da página

O Dynamics 365 Commerce permite gerenciar metadados de SEO para páginas individuais. É possível exibir e modificar estas informações na seção **Propriedades de SEO** de um contêiner de página. As seguintes propriedades de metadados de SEO são suportadas:

- Cargo
- Descrição
- Palavras-chave de SEO
- Etiquetas Aria
- noindex
- nofollow
- noarchive
- nocache
- noOpenDirectoryProject
- nosnippet
- noImageIndex
- unavailableAfter

### <a name="modify-page-metadata"></a>Modificar metadados da página

Para modificar os metadados da página, siga estas etapas.
1. Em **Sites**, selecione o **Fabrikam** (ou o nome do seu site).
1. No painel de navegação à esquerda, selecione **Páginas**.
1. Selecione a home page para abri-la no editor de páginas.
1. Na barra de comandos, selecione **Editar**.
1. No editor de página, na parte superior do controle de estrutura de tópicos à esquerda, selecione a **Opção de modo de estrutura de tópicos** (símbolo de engrenagem) e depois a **Exibição de esboço avançado**.
1. Na exibição de estrutura de tópicos, expanda os controles de árvore para mostrar o conteúdo do slot de **head do HTML**.
1. No slot de **head do HTML**, selecione o módulo de SEO desejado (por exemplo, **Resumo da página**, **Resumo da página do produto**, **Resumo da página de categoria** ou **Metatags**).
1. No painel de propriedades à direita, edite os dados de SEO desejados para o módulo de SEO selecionado (por exemplo, **Título**, **Descrição** ou **Imagem compartilhada**).
1. Selecione **Salvar** e **Finalizar edição**.
1. No campo **Comentários**, insira **Dados de SEO atualizados** e depois selecione **OK**.
1. Selecione **Visualizar** para exibir a página. Quando terminar, feche a guia de visualização para retornar à ferramenta de criação.
1. Selecione **Publicar**.

> [!TIP]
> Os autores podem usar a **Opção de modo de estrutura de tópicos** (símbolo de engrenagem) na parte superior do controle da estrutura de tópicos à esquerda no editor de páginas para alternar entre a **Exibição de esboço básico** e a **Exibição de esboço avançado**. A **Exibição de esboço básico** é a configuração padrão e filtra a estrutura de tópicos para que ela mostre somente os módulos no slot de **corpo** HTML de uma página. A **Exibição de esboço avançado** mostra todo o módulo de página, incluindo os slots de **head de HTML**, **início de corpo** e **fim de corpo**. Essa exibição é útil quando os autores devem editar configurações específicas de módulo de script ou SEO para uma página.

## <a name="additional-resources"></a>Recursos adicionais

[Modificar uma página de site existente](modify-existing-page.md)

[Adicionar uma nova página do site](add-new-page.md)

[Selecionar layouts de página](select-page-layouts.md)

[Salvar, visualizar, e publicar uma página](save-preview-publish-page.md)

[Enriquecer uma página de produto](enrich-product-page.md)

[Enriquecer uma página de aterrissagem da categoria](enrich-category-page.md)

[Verificar acessibilidade do conteúdo da página](verify-accessibility.md)

[Criar páginas dinâmicas de comércio eletrônico com base nos parâmetros da URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
