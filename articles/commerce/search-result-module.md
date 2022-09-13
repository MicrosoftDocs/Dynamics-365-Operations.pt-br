---
title: Módulo de resultados de pesquisa
description: Este artigo abrange os módulos de resultados de pesquisa e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 08/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: eeb7cd0769fcb866a3d7dcc03e8e87daf24b2c5d
ms.sourcegitcommit: 1d5cebea3e05b6d758cd01225ae7f566e05698d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2022
ms.locfileid: "9405284"
---
# <a name="search-results-module"></a>Módulo de resultados de pesquisa

[!include [banner](includes/banner.md)]

Este artigo abrange os módulos de resultados de pesquisa e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

O módulo de resultados da pesquisa retorna resultados de pesquisa de produtos e uma lista de refinadores aplicáveis para os produtos. Os módulos de resultados de pesquisa em sites do Dynamics 365 Commerce podem ser usados para processar páginas para os seguintes cenários:

- Resultados de pesquisa iniciados por uma pesquisa do usuário
- Resultados de pesquisa que mostram um conjunto específico de produtos, como "comprar visuais semelhantes"
- Lista de produtos que pertencem uma categoria

Para obter mais informações sobre as páginas de categoria e de resultados de pesquisa, consulte [Visão geral da página inicial de categorias e da página de resultados de pesquisa](category-search-page-overview.md).

A ilustração a seguir mostra um exemplo de uma página de resultados de pesquisa para uma categoria do site da Fabrikam.

![Exemplo de uma página de resultados de pesquisa no site da Fabrikam.](./media/SimpleCategoryLandingDressCategory.png)

## <a name="search-results-module-properties"></a>Propriedades do módulo de resultados de pesquisa

A tabela a seguir lista as propriedades dos módulos de resultados de pesquisa, juntamente com seus valores e descrições.

| Propriedade | Valores | descrição |
|----------|--------|-------------|
| Itens por página | Inteiro | O número de itens que devem ser mostrados em cada página. |
| Permitir voltar no PDP | **Verdadeiro** ou **Falso** | Se esta propriedade for definida como **Verdadeiro**, quando um usuário selecionar um produto na página de resultados de pesquisa, a navegação estrutural na página de detalhes do produto (PDP) que for aberta mostrará um link "Voltar para os resultados". |
| Expandir Refinadores | **Todos**, **1**, **2**, **3** ou **4** | O número de refinadores principais que devem ser expandidos quando uma página é carregada. Por exemplo, se esta propriedade for definida como **3**, os três primeiros refinadores na página serão expandidos. |
| Ocultar exibição da hierarquia de categoria | **Verdadeiro** ou **Falso** | Se esta propriedade for definida como **Verdadeiro**, a exibição da hierarquia de categoria na página ficará oculta. Essa propriedade deve ser definida como **Verdadeiro** se você estiver usando o [módulo de trilha de navegação](add-breadcrumb.md) para mostrar a hierarquia de categoria.|
| Incluir atributos de produto nos resultados da pesquisa | **Verdadeiro** ou **Falso** | Se esta propriedade for definida como **Verdadeiro**, os atributos serão devolvidos para os produtos nos resultados da pesquisa. Embora esses atributos possam ser mostrados em um site do Commerce, é necessária uma extensão.|
| Mostrar preços de afiliação | **Verdadeiro** ou **Falso** | Se esta propriedade for definida como **Verdadeiro**, os preços de afiliação para produtos serão mostrados nos resultados da pesquisa quando um usuário conectado navegar na página. |
| Atualizar painel do refinador | **Verdadeiro** ou **Falso** | Se esta propriedade for definida como **Verdadeiro**, o painel do refinador será atualizado quando os refinadores forem selecionados. Neste modo, alguns refinadores de seleção múltipla se comportarão como refinadores de seleção única quando o painel do refinador for atualizado. |

> [!IMPORTANT]
> No Commerce versão 10.0.16 e posterior, a configuração **Mostrar preços de afiliação** pode ser usada para mostrar os preços de afiliação na página.
>
> No Commerce versão 10.0.20 e posterior, a configuração **Atualizar painel do refinador** pode ser usada para atualizar o painel do refinador durante a seleção do refinador.

## <a name="supported-modules"></a>Módulos com suporte

O módulo de resultados de pesquisa oferece suporte ao [módulo de exibição rápida](quick-view-module.md), que permite que os usuários vejam informações sobre o produto e adicionem itens ao carrinho usando uma página de resultados de pesquisa.

## <a name="add-a-search-results-module-to-a-category-page"></a>Adicionar um módulo de resultados de pesquisa a uma página de categoria

Para adicionar um módulo de resultados de pesquisa a uma página de categoria no construtor de sites, siga estas etapas.

1. Acesse **Modelos** e selecione **Novo** para criar um novo modelo.
1. Na caixa de diálogo **Novo modelo**, digite o nome **Resultados de pesquisa** e selecione **OK**.
1. No slot **Corpo**, selecione as reticências (...) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Página Padrão** e, depois, **OK**.
1. No slot **Principal** do módulo **Página padrão**, selecione as reticências (...) e, em seguida, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Contêiner** e, depois, **OK**.
1. No slot **Contêiner**, selecione as reticências (...) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Trilha** e, depois, **OK**.
1. No painel de propriedades **Trilha de navegação**, digite o valor **1** para **Mínimo ocorrer**.
1. No slot **Contêiner**, selecione as reticências (...) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Resultados da pesquisa** e, depois, **OK**.
1. No painel **Propriedades de resultados da pesquisa**, digite o valor **1** para **Mínimo ocorrer** e, em seguida, defina outras propriedades necessárias para o módulo de resultados da pesquisa. Ao definir essas propriedades no modelo, você garante que todas as personalizações em uma página de categoria específica incluam automaticamente essas configurações.
1. Selecione **Concluir edição** e depois selecione **Publicar** para publicar o modelo.
1. Acesse **Páginas** e selecione **Novo** para criar uma nova página.
1. Na caixa de diálogo **Criar uma nova página**, em **Nome da página**, insira **Página da categoria** e selecione **Avançar**.
1. Em **Escolher um modelo**, selecione o módulo **Resultados da pesquisa** que você criou e escolha **Avançar**.
1. Em **Escolher um layout**, selecione um layout de página (por exemplo, **Layout flexível**) e selecione **Avançar**.
1. Em **Revisar e concluir**, revise a configuração da página. Se você precisar editar as informações da página, selecione **Voltar**. Se as informações da página estiverem corretas, selecione **Criar página**.
1. Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

## <a name="inventory-aware-search-results-module"></a>Módulo de resultados da pesquisa com reconhecimento de estoque

O módulo de resultados de pesquisa pode ser configurado para incorporar dados de estoque e fornecer as seguintes experiências:

- Exiba etiquetas de nível de estoque junto com produtos.
- Oculte produtos com estoque esgotado da lista de produtos.
- Exiba produtos com estoque esgotado ao final da lista de produtos.
- Ofereça suporte à filtragem de produtos com base no estoque.

Para habilitar essas experiências, você deve primeiro habilitar o recurso **Descoberta aprimorada de produtos de comércio eletrônico para ter reconhecimento do estoque** e, depois, definir algumas configurações de pré-requisito no Commerce headquarters. Para obter mais informações, consulte [Lista de produtos com reconhecimento de estoque](inventory-aware-product-listing.md).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da página de aterrissagem da categoria padrão e da página de resultados da pesquisa](category-search-page-overview.md)

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de exibição rápida](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
