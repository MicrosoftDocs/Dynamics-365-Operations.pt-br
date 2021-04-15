---
title: Módulos de classificações e revisões
description: Este tópico aborda classificações e revisa os módulos usados nas páginas de detalhes do produto no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: Release 10.0.6
ms.openlocfilehash: dee9a6a7e2a5278f069958ce00689b1beb9b1bd7
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792138"
---
# <a name="ratings-and-reviews-modules"></a>Módulos de classificações e opiniões

[!include [banner](includes/banner.md)]

Este tópico aborda classificações e revisa os módulos usados nas páginas de detalhes do produto (PDPs) no Microsoft Dynamics 365 Commerce.

As avaliações e opiniões sobre sites comerciais online ajudam os clientes a aprenderem sobre produtos antes de realizarem uma decisão de compra, e também são um mecanismo para coleta de opinião do cliente sobre produtos. 

As classificações são mostrados nas páginas de listagem de produto, nas páginas de listas de categoria, nas páginas de resultados da pesquisa, e outras páginas do site. 

Os histogramas de avaliação e os comentários sobre os produtos são exibidos nas PDPs. Um botão **Escrever uma avaliação** permite que os clientes enviem avaliações e comentários sobre um produto. Esses recursos de PDP são controlados por classificação e módulos de revisão.

## <a name="ratings-and-reviews-modules-on-pdps"></a>Módulos de classificações e opiniões em PDPs 

Três módulos mostram as avaliações e opiniões resumidas em PDPs:
- Módulo para escrever uma avaliação
- Módulo da lista de revisões de produto
- Módulo de histograma de avaliação
 
A ilustração a seguir mostra como os módulos de avaliações e opiniões se parecem em um PDP.

![Módulos de classificações e opiniões em um PDP](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> Para obter informações sobre como otimizar modelos e layouts de PDP para que você possa compartilhar configurações para módulos de avaliação e opiniões entre vários PDPs no site comercial online, consulte [Visão geral de modelos e layouts](templates-layouts-overview.md).

A ilustração a seguir mostra como a caixa de diálogo **Adicionar o módulo** apresenta módulos de avaliações e opiniões no Dynamics 365 Commerce.
![Adicionar a caixa de diálogo do módulo](media/rnr-eCommerce-pdp-adding-rnr-modules.png)

### <a name="write-review-module"></a>Módulo para escrever uma avaliação

O módulo de escrita de avaliação contém um botão **Escrever uma avaliação** que permite que os usuários se conectem, atribuam uma avaliação e escrevam uma revisão de um produto. Este módulo também permite que os usuários editem uma classificação ou opinião enviada anteriormente. Esse módulos geralmente aparecerá acima do histograma de avaliações e módulos de lista de opiniões sobre produto em um PDP.
A ilustração a seguir mostra a caixa de diálogo **Escrever uma avaliação** exibida quando um cliente seleciona **Escrever uma avaliação**. O cliente pode usar esta caixa de diálogo para enviar uma avaliação e uma revisão.
![Caixa de diálogo escrever uma avaliação](media/rnr-eCommerce-write-review-module.png) A tabela a seguir mostra a propriedade do módulo para escrever uma revisão que precisa ser configurada na ferramenta de criação.
| Nome da propriedade | Alíquota        | Descrição de propriedade                 |
|---------------|--------------|--------------------------------------|
| Nome          | Escrever avaliação | O nome do módulo escrever uma revisão. |

### <a name="ratings-histogram-module"></a>Módulo de histograma de avaliação

O módulo de histograma de avaliações exibe um histograma de avaliações. Este módulo aparece normalmente entre o módulo para escrever avaliação e o módulo de lista de avaliações de produto em um PDP.
O módulo de histograma de avaliação não exige configuração. Você só tem que adicionar o módulo no modelo de PDP. As ilustrações a seguir mostram como um modelo de PDP se parece no Dynamics 365 Commerce quando os módulos de avaliação e revisão são configurados para exibição em PDPs.
![Modelo de PDP quando as avaliações e revisões estão configuradas para a exibição em PDPs](media/rnr-eCommerce-pdp-reviews-modules.png)

### <a name="product-reviews-list-module"></a>Módulo da lista de revisões de produto

O módulo da lista de avaliações de produto mostra uma lista de revisões de produto com o tipo, o filtro, e as opções de paginação. Este módulo geralmente aparece após o módulo de histograma de avaliação em um PDP.
A tabela a seguir mostra as propriedades do módulo de lista de avaliações de produto que precisam ser configurados na ferramenta de criação.

| Nome da propriedade              | Alíquota | Descrição de propriedade |
|----------------------------|-------| ---------------------|
| Revisões mostradas em cada página | 10    | O número de revisões que devem ser mostradas em vez em um PDP. Os botões **Avançar** e **Voltar** estão incluídos, para que os usuários possam mover entre as páginas de avaliações. |

#### <a name="ratings-histogram--summary-view"></a>Histograma de avaliação – Exibição de resumo

O módulo de lista de avaliações de produto inclui um slot onde você pode adicionar um módulo de histograma de avaliações. A ilustração a seguir mostra como é possível adicionar um módulo de histograma de avaliação no módulo da lista de revisões de produtos no Dynamics 365 Commerce.

![Adicionando um módulo de histograma de avaliação em um módulo de lista de avaliações de produto](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de contêiner](add-container-module.md)

[Módulo de carrinho](add-cart-module.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de confirmação da ordem](order-confirmation-module.md)

[Módulo de cabeçalho](author-header-module.md)

[Módulo de rodapé](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]