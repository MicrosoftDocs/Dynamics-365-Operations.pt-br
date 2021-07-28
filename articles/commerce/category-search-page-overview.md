---
title: Visão geral da página de aterrissagem da categoria padrão e da página de resultados da pesquisa
description: Este tópico fornece uma visão geral da página de aterrissagem de categoria padrão e da página de resultados de pesquisa no Dynamics 365 Commerce.
author: ashishmsft
ms.date: 06/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f9fffb5b4f51c86076d62ac2a44bdc779490c7bd
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6351264"
---
# <a name="default-category-landing-page-and-search-results-page-overview"></a>Visão geral da página de aterrissagem da categoria padrão e da página de resultados da pesquisa

[!include [banner](includes/banner.md)]

Este tópico fornece uma visão geral da página de aterrissagem de categoria padrão e da página de resultados de pesquisa no comércio online do Microsoft Dynamics 365 Commerce.

## <a name="default-category-landing-page"></a>Página de aterrissagem da categoria padrão

A página de aterrissagem de categoria padrão é a página para a qual os usuários do site geralmente são levados quando selecionam uma categoria na hierarquia de navegação. A página de categoria permite pesquisar, e você também pode classificar e refinar produtos categorizados.

![Página de aterrissagem da categoria padrão.](./media/SimpleCategoryLandingDressCategory.png)

Na parte superior da página está um cabeçalho que mostra todas as categorias de produtos e outras páginas que o gerente de mercadoria categorizou. A configuração é feita como parte da configuração da hierarquia de navegação de canal. Na parte inferior da página está um rodapé que inclui links rápidos para várias tópicos que podem despertar o interesse de um cliente.

Os componentes a seguir são essenciais para uma categoria:

- **Blocos de posicionamento de produto** mostra os produtos que o gerente de vendas definiu em uma categoria como parte da configuração de hierarquia de navegação.
- **Refinadores e resumo de escolha** são filtros que fornecem contagens e que podem ser usados para refinar itens. O gerente de mercadorias os configura como parte da configuração de metadados relacionados para categorias de canal e atributos de produto.
- **Opções de classificação** são usadas por visitantes de site para classificar os produtos. Por padrão, as opções de classificação a seguir estão disponíveis:

    - Preço – menor para maior
    - Preço – maior para menor
    - Nome do produto – \[A-Z\]
    - Nome do produto – \[Z-A\]
    - Avaliações – baixo para alto
    - Avaliações – alto para baixo

- A **Paginação** permite que os visitantes de site movam-se de uma página de resultados de produto categorizado a outra página.
- **Contagem total** fornece o número total de produtos definidos em uma categoria.

## <a name="enrich-a-category-landing-page"></a>Enriquecer uma página de aterrissagem da categoria

Se deseja uma página de aterrissagem de categoria com uma experiência mais personalizado para uma categoria específica, você pode "enriquecer" a página de aterrissagem da categoria para essa categoria. Por exemplo, você pode adicionar uma vídeo de marketing e uma categoria para contar histórias para obter a atenção do comprador. Para obter mais informações, consulte [Enriqueça uma página de aterrissagem de categoria](enrich-category-page.md).

![Página de aterrissagem da categoria enriquecida.](./media/CategoryLandingPages.png)

## <a name="auto-suggest-and-search-results-pages"></a>Páginas de sugestão automática e resultados de pesquisa

Os usuários do site podem explorar um site indo para uma categoria pela hierarquia de navegação ou inserindo um termo de pesquisa no campo de pesquisa.

Assim que os usuários começarem a digitar no campo de pesquisa, eles recebem uma funcionalidade de sugestão automática imersiva que sugere termos de pesquisa.

Aqui estão alguns dos tipos de sugestões que podem ser exibidas:

- **Palavras-chave** são usada para localizar itens em todos os produtos que estão classificados ao canal.
- **Produtos** fornece as links diretos a página de detalhes de produto.
- **Sugestões de pesquisa de categoria no escopo** lista várias categorias e permite que os usuários pesquisem por palavra-chave em uma categoria específica.

![Sugestão automática imersiva.](./media/ImmersiveAutoSuggestUX.png)

Quando os usuários selecionam uma palavra-chave ou sugestões de pesquisa de categoria no escopo, ou quando não houver nenhuma sugestão do termo de pesquisa que devem entrar, são redirecionados a uma página de resultados de busca. Os usuários podem então procurar, classificar e restringir a lista de resultados de pesquisa para localizar o item desejado.

![Aterrissagem de pesquisa.](./media/SearchLanding.png)

Os componentes a seguir são essenciais para uma página de resultados de pesquisa:

- **Blocos de posicionamento de produto** mostra os produtos da pesquisa do usuário. Por padrão, esses blocos são classificados pela pontuação de relevância de pesquisa baseada em nuvem para a pesquisa de usuário.
- **Refinadores e resumo de escolha** são filtros que fornecem contagens e que podem ser usados para refinar itens. O gerente de mercadorias os configura como parte da configuração de metadados das "categorias de canal e atributos de produto".
- **Opções de classificação** são usadas por visitantes de site para classificar os produtos. Por padrão, as opções de classificação a seguir estão disponíveis:

    - Preço – menor para maior
    - Preço – maior para menor
    - Nome do produto – \[A-Z\]
    - Nome do produto – \[Z-A\]
    - Avaliações – baixo para alto
    - Avaliações – alto para baixo
    - Padrão

- A **Paginação** permite que os visitantes de site movam-se de uma página de resultados de produto categorizado a outra página.
- **Contagem total** fornece o número total de produtos definidos em uma categoria e que correspondem ao critério de pesquisa.

>[!NOTE]
>Esses recursos de pesquisa habilitados para a nuvem estão disponíveis a partir da versão 10.0.8. Verifique se em **Parâmetros do Commerce > Parâmetros de Configuração** há uma entrada para "ProductSearch.UseAzureSearch definido como 'true'". 
![Parâmetros de configuração para pesquisa habilitada para a nuvem.](./media/CloudPoweredSearchConfigurationParameters.png)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da pesquisa habilitada para a nuvem](cloud-powered-search-overview.md)

[Visão geral da página inicial](quick-tour-home-page.md)

[Visão geral das páginas de detalhes do produto](quick-tour-pdp.md)

[Visão geral das páginas de carrinho e de finalização da compra](quick-tour-cart-checkout.md)

[Visão geral das páginas de gerenciamento da conta](quick-tour-account-management.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]