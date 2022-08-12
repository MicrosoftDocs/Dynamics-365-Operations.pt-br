---
title: Perguntas frequentes sobre catálogos do Commerce para B2B
description: Este artigo fornece respostas a perguntas frequentes sobre os catálogos do Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 07/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: 68c648c5caf2667f413b236dc437fc2c74c40d07
ms.sourcegitcommit: c271b2edc4bf777f7194b09139ccbd174a359c75
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/16/2022
ms.locfileid: "9168976"
---
# <a name="commerce-catalogs-for-b2b-faq"></a>Perguntas frequentes sobre catálogos do Commerce para B2B

[!include [banner](includes/banner.md)]

Este artigo fornece respostas a perguntas frequentes sobre os [catálogos B2B (entre empresas)](catalogs-b2b-sites.md) do Microsoft Dynamics 365 Commerce.

### <a name="why-cant-i-configure-a-catalog-specific-navigation-hierarchy-or-see-an-option-to-associate-a-customer-hierarchy"></a>Por que não posso configurar uma hierarquia de navegação específica do catálogo ou ver uma opção para associar uma hierarquia de cliente?

Certifique-se de que o recurso **Habilitar o uso de vários catálogos em canais de varejo** esteja habilitado no espaço de trabalho **Gerenciamento de recursos** do Commerce headquarters e que seu ambiente seja o Commerce versão 10.0.27 ou posterior. Verifique se você selecionou **B2B** em **Tipo de catálogo**.

### <a name="can-i-view-the-catalog-specific-hierarchy-and-enrich-category-pages-in-commerce-site-builder"></a>Posso exibir a hierarquia específica do catálogo e enriquecer as páginas de categoria no criador de sites do Commerce?

Sim, os usuários do criador de sites do Commerce que têm acesso à página **Produtos** no criador de sites podem selecionar um catálogo e exibir a hierarquia específica do catálogo. Na página **Produtos**, os usuários também podem enriquecer uma página de categoria para uma categoria específica no catálogo. Para obter mais informações, consulte [Enriqueça uma página de aterrissagem de categoria](enrich-category-page.md). Se deseja ter um enriquecimento específico para um catálogo, recomendamos que você tenha uma hierarquia de navegação distinta e exclusiva para esse catálogo.

### <a name="can-a-b2b-shopper-purchase-from-multiple-catalogs-in-a-single-checkout"></a>Um comprador B2B pode comprar de vários catálogos em uma única finalização de compra?

Sim, são permitidas compras de vários catálogos em uma única finalização de compra. Os compradores B2B podem usar o indicador de catálogo na exibição do carrinho para determinar quais itens foram adicionados de quais catálogos.

### <a name="if-a-b2b-shopper-purchases-the-same-item-from-different-catalogs-what-is-the-expected-behavior"></a>Se um comprador B2B compra o mesmo item de catálogos diferentes, qual é o comportamento esperado?

Embora um determinado usuário possa ter acesso a vários catálogos em um determinado momento, a expectativa é que os produtos desses catálogos sejam mutuamente exclusivos. Ou seja, o ideal é que um mesmo produto não faça parte de mais de um catálogo para um determinado usuário.

No entanto, se surgir uma situação em que o mesmo produto pertence a vários catálogos, o sistema manterá várias linhas de carrinhos para esse produto. Haverá uma linha separada para cada catálogo. O mesmo produto de dois catálogos diferentes não será mesclado na finalização da compra.

### <a name="when-a-b2b-shopper-is-shopping-is-there-any-validation-for-catalog-availability"></a>Quando um comprador B2B está comprando, há alguma validação para a disponibilidade do catálogo?

Sim. Um comprador B2B terá permissão para prosseguir para a finalização da compra somente se todos os itens no carrinho forem de catálogos válidos. Se algum item do carrinho for de catálogos expirados ou retirados, eles serão removidos, e o usuário será notificado.

### <a name="during-the-shopping-experience-are-search-and-product-discovery-including-related-and-recommended-product-collections-catalog-specific"></a>Durante a experiência de compra, a pesquisa e a descoberta de produtos (incluindo coleções de produtos relacionados e recomendados) são específicas do catálogo?

Sim. Assim que um usuário seleciona um catálogo específico, toda a jornada de compra se torna específica do catálogo. Essa jornada inclui experiências de descoberta de produtos, como sugestões de pesquisa, resultados de pesquisa, resultados de categorias, refinadores, preços, atributos e produtos recomendados (como novos, mais vendidos, mais populares, comprados frequentemente juntos e produtos relacionados).

### <a name="can-a-b2b-shopper-purchase-from-the-default-assortment-catalogid0"></a>Um comprador B2B pode comprar do sortimento padrão (catalogID=0)?

Não, um comprador B2B não pode comprar do sortimento padrão. Esse sortimento destina-se apenas à navegação anônima. Se um comprador B2B não tiver atribuições de catálogo (atualizações pendentes da administração), ele não poderá ver nenhum catálogo que possa escolher e nenhuma hierarquia de categoria estará visível.

### <a name="can-marketing-content-be-curated-for-a-product-that-is-specific-to-a-catalog"></a>O conteúdo de marketing pode ser selecionado para um produto específico de um catálogo?

Atualmente, o enriquecimento do produto é compatível apenas no nível de site e canal. Ou seja, se um produto for enriquecido e estiver compartilhado em vários catálogos, a página de detalhes do produto (PDP) enriquecido correspondente a esse produto será renderizada da mesma maneira em todos os catálogos de um determinado site. 

### <a name="is-catalog-support-available-for-both-b2b-and-business-to-consumer-b2c-online-channels"></a>O suporte de catálogo está disponível para canais online B2B e B2C (business-to-consumer)?

No momento, os catálogos do Commerce destinam-se a funcionar apenas com canais online B2B.

### <a name="a-new-customer-was-added-to-the-customer-hierarchy-or-a-new-hierarchy-was-associated-with-the-catalog-but-the-catalog-is-not-available-to-the-user-why"></a>Um novo cliente foi adicionado à hierarquia do cliente ou uma nova hierarquia foi associada ao catálogo, mas o catálogo não está disponível para o usuário. Por quê?

Verifique se você executou os trabalhos **1010** depois de ter associado o novo cliente a uma hierarquia de cliente existente e quando criou a nova hierarquia do cliente. Os catálogos associados à hierarquia do cliente só serão visíveis depois que o trabalho **1010** for concluído com êxito. Se o catálogo também for novo, verifique se você executou o trabalho **1150** (catálogo), bem como os trabalhos **1010**. Como em qualquer novo catálogo, aguarde para que os dados sejam sincronizados com o canal e o índice de pesquisa. Se um trabalho tiver o status "Aplicado", isso significará que os dados estão sendo sincronizados para o canal de banco de dados, mas o tempo adicional é necessário para que eles sejam sincronizados com o índice de pesquisa. 

### <a name="can-we-set-up-catalog-specific-upsellcross-sell-items"></a>Podemos configurar itens de venda adicional/venda cruzada específicos do catálogo?

No momento, só há suporte para a funcionalidade de produtos relacionados. No entanto, as configurações de itens de venda adicional e venda cruzada estão disponíveis para call centers.

Os seguintes recursos também são compatíveis apenas com call centers:

- Códigos-fonte do catálogo
- Uso de IDs de origem para rastrear custos e taxas de resposta
- Scripts de itens e ordens específicas de catálogo
- Análise da página do catálogo
- Solicitações de catálogo
- Planos de pagamento
- Produtos gratuitos com base nos códigos-fonte

### <a name="can-we-use-catalog-source-codes-for-b2b-orders-through-the-e-commerce-portal"></a>Podemos usar códigos de origem de catálogo para ordens B2B pelo portal de comércio eletrônico?

Não. Os códigos-fonte do catálogo são compatíveis apenas com canais de call center.

## <a name="additional-resources"></a>Recursos adicionais

[Criar catálogos do Commerce para sites B2B](catalogs-b2b-sites.md)

[Módulo de seletor de catálogo](catalog-picker.md)

[Impacto da extensibilidade de catálogos do Commerce para personalizações B2B](catalogs-b2b-sites-dev.md)
