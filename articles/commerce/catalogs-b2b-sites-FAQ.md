---
title: Perguntas frequentes sobre catálogos do Commerce para B2B
description: Este artigo fornece respostas a perguntas frequentes sobre os catálogos do Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 05/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: 0cd11b4469e4dbd1205ace785fe857f6c6001480
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849032"
---
# <a name="commerce-catalogs-for-b2b-faq"></a>Perguntas frequentes sobre catálogos do Commerce para B2B

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este artigo fornece respostas a perguntas frequentes sobre os [catálogos B2B (entre empresas)](catalogs-b2b-sites.md) do Microsoft Dynamics 365 Commerce.

## <a name="why-cant-i-configure-a-catalog-specific-navigation-hierarchy-or-see-an-option-to-associate-a-customer-hierarchy"></a>Por que não posso configurar uma hierarquia de navegação específica do catálogo ou ver uma opção para associar uma hierarquia de cliente?

Certifique-se de que o recurso **Habilitar o uso de vários catálogos em canais de varejo** está habilitado no espaço de trabalho **Gerenciamento de recursos** no Commerce headquarters. Além disso, certifique-se de que seu ambiente esteja usando a versão 10.0.27 ou posterior do Commerce.

## <a name="can-i-view-the-catalog-specific-hierarchy-and-enrich-category-pages-in-commerce-site-builder"></a>Posso exibir a hierarquia específica do catálogo e enriquecer as páginas de categoria no criador de sites do Commerce?

Sim, os usuários do criador de sites do Commerce que têm acesso à página **Produtos** no criador de sites podem selecionar um catálogo e exibir a hierarquia específica do catálogo. Na página **Produtos**, os usuários também podem enriquecer uma página de categoria para uma categoria específica no catálogo. Para obter mais informações, consulte [Enriqueça uma página de aterrissagem de categoria](enrich-category-page.md). Se deseja ter um enriquecimento específico para um catálogo, recomendamos que você tenha uma hierarquia de navegação distinta e exclusiva para esse catálogo.

## <a name="can-a-b2b-shopper-purchase-from-multiple-catalogs-in-a-single-checkout"></a>Um comprador B2B pode comprar de vários catálogos em uma única finalização de compra?

Sim, são permitidas compras de vários catálogos em uma única finalização de compra. Os compradores B2B podem usar o indicador de catálogo na exibição do carrinho para determinar quais itens foram adicionados de quais catálogos.

## <a name="if-a-b2b-shopper-purchases-the-same-item-from-different-catalogs-what-is-the-expected-behavior"></a>Se um comprador B2B compra o mesmo item de catálogos diferentes, qual é o comportamento esperado?

Embora um determinado usuário possa ter acesso a vários catálogos em um determinado momento, a expectativa é que os produtos desses catálogos sejam mutuamente exclusivos. Ou seja, o ideal é que um mesmo produto não faça parte de mais de um catálogo para um determinado usuário.

No entanto, se surgir uma situação em que o mesmo produto pertence a vários catálogos, o sistema manterá várias linhas de carrinhos para esse produto. Haverá uma linha separada para cada catálogo. O mesmo produto de dois catálogos diferentes não será mesclado na finalização da compra.

## <a name="when-a-b2b-shopper-is-shopping-is-there-any-validation-for-catalog-availability"></a>Quando um comprador B2B está comprando, há alguma validação para a disponibilidade do catálogo?

Sim. Um comprador B2B terá permissão para prosseguir para a finalização da compra somente se todos os itens no carrinho forem de catálogos válidos. Se algum item do carrinho for de catálogos expirados ou retirados, eles serão removidos, e o usuário será notificado.

## <a name="during-the-shopping-experience-are-search-and-product-discovery-including-related-and-recommended-product-collections-catalog-specific"></a>Durante a experiência de compra, a pesquisa e a descoberta de produtos (incluindo coleções de produtos relacionados e recomendados) são específicas do catálogo?

Sim. Assim que um usuário seleciona um catálogo específico, toda a jornada de compra se torna específica do catálogo. Essa jornada inclui experiências de descoberta de produtos, como sugestões de pesquisa, resultados de pesquisa, resultados de categorias, refinadores, preços, atributos e produtos recomendados (como novos, mais vendidos, mais populares, comprados frequentemente juntos e produtos relacionados).

## <a name="can-a-b2b-shopper-purchase-from-the-default-assortment-catalogid0"></a>Um comprador B2B pode comprar do sortimento padrão (catalogID=0)?

Não, um comprador B2B não pode comprar do sortimento padrão. Esse sortimento destina-se apenas à navegação anônima. Se um comprador B2B não tiver atribuições de catálogo (atualizações pendentes da administração), ele não poderá ver nenhum catálogo que possa escolher e nenhuma hierarquia de categoria estará visível.

## <a name="can-marketing-content-be-curated-for-a-product-that-is-specific-to-a-catalog"></a>O conteúdo de marketing pode ser selecionado para um produto específico de um catálogo?

Atualmente, o enriquecimento do produto é compatível apenas nos níveis de site e canal. Ou seja, se um produto for enriquecido, ele será compartilhado em vários catálogos, e a página de detalhes do produto (PDP) correspondente a esse produto será renderizada da mesma maneira em todos os catálogos de um determinado site.

## <a name="is-catalog-support-available-for-both-b2b-and-business-to-consumer-b2c-online-channels"></a>O suporte de catálogo está disponível para canais online B2B e B2C (business-to-consumer)?

No momento, os catálogos do Commerce destinam-se a funcionar apenas com canais B2B.

## <a name="can-we-set-up-catalog-specific-upsellcross-sell-items"></a>Podemos configurar itens de venda adicional/venda cruzada específicos do catálogo?

No momento, só há suporte para a funcionalidade de produtos relacionados. No entanto, as configurações de itens de venda adicional e venda cruzada estão disponíveis para call centers.

Os seguintes recursos também são compatíveis apenas com call centers:

- Códigos-fonte do catálogo
- Uso de IDs de origem para rastrear custos e taxas de resposta
- Scripts de itens e ordens específicas de catálogo
- Análise da página do catálogo
- Solicitações de catálogo
- Planos de pagamento
- Produtos gratuitos com base nos códigos-fonte

## <a name="can-we-use-catalog-source-codes-for-b2b-orders-through-the-e-commerce-portal"></a>Podemos usar códigos de origem de catálogo para ordens B2B pelo portal de comércio eletrônico?

Não. Os códigos-fonte do catálogo são compatíveis apenas com canais de call center.

## <a name="additional-resources"></a>Recursos adicionais

[Criar catálogos do Commerce para sites B2B](catalogs-b2b-sites.md)

[Impacto da extensibilidade de catálogos do Commerce para personalizações B2B](catalogs-b2b-sites-dev.md)
