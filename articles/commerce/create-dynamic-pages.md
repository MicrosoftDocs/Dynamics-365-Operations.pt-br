---
title: Criar páginas de comércio eletrônico dinâmicas com base nos parâmetros da URL
description: Este artigo descreve como configurar uma página de comércio eletrônico do Microsoft Dynamics 365 Commerce que pode fornecer conteúdo dinâmico, com base em parâmetros de URL.
author: bicyclingfool
ms.date: 05/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.openlocfilehash: 718bc099347f2924b299ccd4562d9d7055c43187
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282867"
---
# <a name="create-dynamic-e-commerce-pages-based-on-url-parameters"></a>Criar páginas de comércio eletrônico dinâmicas com base nos parâmetros da URL

[!include [banner](includes/banner.md)]

Este artigo descreve como configurar uma página de comércio eletrônico do Microsoft Dynamics 365 Commerce que pode fornecer conteúdo dinâmico, com base em parâmetros de URL.

Uma página de comércio eletrônico pode ser configurada para fornecer conteúdo diferente, com base em um segmento no caminho da URL. Portanto, a página é conhecida como uma página dinâmica. O segmento é usado como um parâmetro para recuperar o conteúdo da página. Por exemplo, uma página criada no construtor de sites e nomeada **blog\_viewer** é mapeada para a URL `https://fabrikam.com/blog`. Essa página pode ser usada para mostrar conteúdo diferente, com base no último segmento do caminho da URL. Por exemplo, o último segmento na URL `https://fabrikam.com/blog/article-1` é o **artigo-1**.

Também é possível substituir um segmento de URL parametrizada por uma página do construtor de sites. Por exemplo, uma página criada no construtor de sites e nomeada **blog\_summary** pode ser mapeada para a URL `https://fabrikam.com/blog/about-this-blog`. Quando a URL `https://fabrikam.com/blog` é solicitada com o segmento `/about-this-blog` na extremidade, o conteúdo da página **blog\_summary** é retornado em vez do segmento `/about-this-blog` que está sendo interpretado como um parâmetro a ser usado pela página `https://fabrikam.com/blog`. 

Ao selecionar nomes para os parâmetros a serem passados para a página dinâmica, o nome da página dinâmica que aparece na URL (`/blog` no exemplo acima) não pode ser usado como um nome de parâmetro ou uma substring de um nome de parâmetro. 

> [!NOTE]
> A funcionalidade para hospedar, recuperar e mostrar o conteúdo da página dinâmica é implementada usando um módulo personalizado. Para obter mais informações, consulte [Extensibilidade de canal online](e-commerce-extensibility/overview.md).

## <a name="set-up-a-dynamic-e-commerce-page"></a>Configurar uma página dinâmica de comércio eletrônico

Para configurar uma página dinâmica de comércio eletrônico, você deve criar a página dinâmica, criar a URL base e configurar o roteiro para a página dinâmica.

### <a name="create-the-page-that-will-serve-dynamic-content"></a>Criar a página que fornecerá conteúdo dinâmico

Para criar uma página que fornecerá conteúdo dinâmico, siga as etapas em [Adicionar uma nova página do site](add-new-page.md). A página que você criar exigirá a implementação de um módulo que usa o último segmento no caminho da URL para recuperar conteúdo de uma fonte de dados externa. Para obter mais informações sobre o desenvolvimento de módulos personalizados, consulte [Extensibilidade de canal online](e-commerce-extensibility/overview.md).

### <a name="create-the-base-url-for-the-dynamic-page"></a>Criar a URL base para a página dinâmica

Para criar a URL base para a página dinâmica no assistente para criação de sites do Commerce, siga estas etapas.

1. Acesse **URLs** e selecione **Nova \> Nova URL**.
1. Na caixa de diálogo **Criar nova URL**, selecione **Página interna**. Em **Caminho da URL**, insira o caminho que servirá como a raiz da página dinâmica (neste exemplo, **/blog**). Selecione **Avançar**.
1. Na caixa de diálogo **Selecionar uma página**, selecione a página criada para atuar como a página dinâmica e selecione **Salvar**.
1. Selecione **Publicar**.

### <a name="configure-the-route-to-the-dynamic-page"></a>Configurar o roteiro para a página dinâmica

Para configurar o roteiro para a página dinâmica no assistente para criação de sites do Commerce, siga estas etapas.

1. Acesse **Configurações do Site \> Extensões**.
1. Em **Caminhos de URL parametrizada**, selecione **Adicionar** e insira o caminho da URL inserido ao criar a URL (neste exemplo, **/blog**).
1. Selecione **Salvar e publicar**.

Depois que o roteiro for configurado, todas as solicitações ao caminho de URL parametrizada retornarão a página associada a essa URL. Se alguma solicitação contiver um segmento adicional, a página associada será devolvida e o conteúdo da página será recuperado usando o segmento como um parâmetro. Por exemplo, `https://fabrikam.com/blog/article-1` retornará a página `https://fabrikam.com/blog`, exibindo o conteúdo que é recuperado usando o parâmetro **/article-1**.

## <a name="override-a-parameterized-url-with-a-custom-page"></a>Substituir uma URL parametrizada por uma página personalizada

Para substituir uma URL parametrizada por uma página personalizada no assistente para criação de sites do Commerce, siga estas etapas.

1. Acesse **URLs** e selecione **Nova \> Nova URL**.
1. Na caixa de diálogo **Criar nova URL**, selecione **Página interna**. Em **Caminho da URL**, insira o caminho que inclui o segmento a ser substituído (neste exemplo, **/blog/about-this-blog**). Selecione **Avançar**.
1. Na caixa de diálogo **Selecionar uma página**, selecione a página personalizado e, depois, **Salvar**.
1. Selecione **Publicar**.
1. Se a página personalizada ainda não tiver sido publicada, acesse **Páginas**, selecione a página personalizada e selecione **Publicar**.

Depois que a página personalizada for publicada, ela será fornecida em vez da página dinâmica com conteúdo parametrizado.

## <a name="additional-resources"></a>Recursos adicionais

[Modificar uma página de site existente](modify-existing-page.md)

[Adicionar uma nova página do site](add-new-page.md)

[Selecionar layouts de página](select-page-layouts.md)

[Gerenciar metadados de SEO](manage-seo-metadata.md)

[Salvar, visualizar, e publicar uma página](save-preview-publish-page.md)

[Enriquecer uma página de produto](enrich-product-page.md)

[Enriquecer uma página de aterrissagem da categoria](enrich-category-page.md)

[Verificar acessibilidade do conteúdo da página](verify-accessibility.md)

[Extensibilidade do canal online](e-commerce-extensibility/overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
