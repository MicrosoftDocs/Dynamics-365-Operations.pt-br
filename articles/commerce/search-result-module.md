---
title: Módulo de resultados de pesquisa
description: Este tópico abrange os módulos de resultados de pesquisa e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 5d852fe1a81b1e42484bc49ae136ef8613a2d3a5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254760"
---
# <a name="search-results-module"></a>Módulo de resultados de pesquisa

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este tópico abrange os módulos de resultados de pesquisa e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

O módulo de resultados da pesquisa retorna resultados de pesquisa de produtos e uma lista de refinadores aplicáveis para os produtos. Os módulos de resultados de pesquisa em sites do Dynamics 365 Commerce podem ser usados para processar páginas para os seguintes cenários:

- Resultados de pesquisa iniciados por uma pesquisa do usuário
- Resultados de pesquisa que mostram um conjunto específico de produtos, como "comprar visuais semelhantes"
- Lista de produtos que pertencem uma categoria

Para obter mais informações sobre as páginas de categoria e de resultados de pesquisa, consulte [Visão geral da página inicial de categorias e da página de resultados de pesquisa](category-search-page-overview.md).

A ilustração a seguir mostra um exemplo de uma página de resultados de pesquisa para uma categoria do site da Fabrikam.

![Exemplo de uma página de resultados de pesquisa no site da Fabrikam](./media/SimpleCategoryLandingDressCategory.png)

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

> [!IMPORTANT]
> No Dynamics 365 Commerce versão 10.0.16 e posterior, a configuração **Mostrar preços de afiliação** pode ser usada para mostrar os preços de afiliação na página.

## <a name="supported-modules"></a>Módulos com suporte

O módulo de resultados de pesquisa oferece suporte ao [módulo de exibição rápida](quick-view-module.md), que permite que os usuários vejam informações sobre o produto e adicionem itens ao carrinho usando uma página de resultados de pesquisa.

## <a name="add-a-search-results-module-to-a-category-page"></a>Adicionar um módulo de resultados de pesquisa a uma página de categoria

Para adicionar um módulo de resultados de pesquisa a uma página de categoria, siga estas etapas.

1. Vá para **Modelos** e selecione **Novo** para criar um novo modelo.
1. Na caixa de diálogo **Novo modelo**, digite o nome **Resultados de pesquisa** e selecione **OK**.
1. No slot **Corpo**, selecione as reticências (...) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Página Padrão** e, depois, **OK**.
1. No slot **Principal** do módulo **Página padrão**, selecione as reticências (...) e, em seguida, **Adicionar módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Contêiner** e, depois, **OK**.
1. No slot **Contêiner**, selecione as reticências (...) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Trilha de navegação** e, depois, **OK**.
1. No painel de propriedades **Trilha de navegação**, digite o valor **1** para **Mínimo ocorrer**.
1. No slot **Contêiner**, selecione as reticências (...) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Resultados de pesquisa** e, depois, **OK**.
1. No painel **Propriedades de resultados da pesquisa**, digite o valor **1** para **Mínimo ocorrer** e, em seguida, defina outras propriedades necessárias para o módulo de resultados da pesquisa. Ao definir essas propriedades no modelo, você garante que todas as personalizações em uma página de categoria específica incluam automaticamente essas configurações.
1. Selecione **Concluir edição** e depois selecione **Publicar** para publicar o modelo.
1. Vá para **Páginas** e selecione **Novo** para criar uma nova página.
1. Na caixa de diálogo **Escolher um modelo**, selecione o modelo **Resultados de pesquisa** que você criou, digite **Página da categoria** para **Nome da página** e selecione **OK**. Como todos os valores são definidos no modelo, a página está pronta para ser publicada.
1. Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da página de aterrissagem da categoria padrão e da página de resultados da pesquisa](category-search-page-overview.md)

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de exibição rápida](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]