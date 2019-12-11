---
title: Configurar classificações e opiniões
description: Este tópico descreve como configurar seu site comercial online para mostrar avaliações de cliente e opiniões no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0612b32e7751b32ad851f627a53bce2ac491870f
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770472"
---
# <a name="configure-ratings-and-reviews"></a>Configurar classificações e opiniões

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico descreve como configurar seu site comercial online para mostrar avaliações de cliente e opiniões no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

As avaliações e opiniões sobre sites comerciais online ajudam os clientes a aprenderem sobre produtos antes de realizarem uma decisão de compra, mostrando a eles o que os clientes pensam sobre esses produtos. Para sites de comércio online, avaliações e opiniões também são um mecanismo para coletar feedback de clientes sobre produtos. 

As classificações são mostrados nas páginas de listagem de produto, nas páginas de listas de categoria, nas páginas de resultados da pesquisa, e outras páginas do site. Os histogramas de avaliação e os comentários sobre os produtos são exibidos nas páginas de detalhes do produto (PDPs). Um botão **Escrever uma avaliação** permite que os clientes enviem avaliações e comentários sobre um produto.

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

![Caixa de diálogo escrever uma avaliação](media/rnr-eCommerce-write-review-module.png)

A tabela a seguir mostra a propriedade do módulo para escrever uma revisão que precisa ser configurado na ferramenta de criação.

| Nome da propriedade | Alíquota        | Descrição de propriedade                 |
|---------------|--------------|--------------------------------------|
| Nome          | Escrever avaliação | O nome do módulo escrever uma revisão. |

### <a name="ratings-histogram-module"></a>Módulo de histograma de avaliação

O módulo de histograma de avaliações exibe um histograma de avaliações. Este módulo aparece normalmente entre o módulo para escrever avaliação e o módulo de lista de avaliações de produto em um PDP.

O módulo de histograma de avaliação não exige configuração. Você só tem que adicionar o módulo no modelo de PDP. 

As ilustrações a seguir mostram como um modelo de PDP se parece no Dynamics 365 Commerce quando os módulos de avaliação e revisão são configurados para exibição em PDPs.

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

## <a name="configure-a-site-to-show-ratings-and-reviews"></a>Configurar um site para exibir classificações e opiniões

Os valores de configuração de classificações e revisões, como ID de locatário, comprimento do texto de avaliação, e comprimento de título de avaliação são configurados no nível do site. 

Para configurar um site para exibir avaliações e opiniões, siga estas etapas. 

1. Vá para **Início \> Sites**.
1. Selecione o nome do site. 
1. Vá para **Gerenciamento de sites \> Extensibilidade**. 
1. No campo **Revisar o tamanho máximo do texto**, insira o número máximo de caracteres que o texto de avaliação pode ter (por exemplo, **1000**). 
1. No campo **Revisar o tamanho máximo do título**, insira o número máximo de caracteres que os títulos de avaliação pode ter (por exemplo, **55**). 
1. Selecione **Salvar e publicar**. 

A ilustração a seguir mostra como essa configuração se parece no Dynamics 365 Commerce.

![Configurando um site para exibir classificações e opiniões](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a>Vincule uma avaliação de produto à seção Avaliações de um PDP

Uma classificação de produtos é exibida abaixo do título do produto na parte superior de PDP. A classificação de produto pode ser configurada de forma que está vinculada à seção **Revisões** do mesmo PDP. 

Para vincular um produto que avalie a seção **Avaliações** do PDP, rastreie essas etapas.

1. Abra o modelo do PDP. 
1. Vá para **Comprar configurações de módulo de contêiner de caixa**.
1. Em **Comprar uma caixa**, selecione **Classificações de produtos**, e selecione a caixa de seleção **Vincular o clique ao módulo inteiro de revisões de desempenho**.

A ilustração a seguir mostra como essa configuração se parece no Dynamics 365 Commerce.

![Vinculando uma avaliação de produto à seção Avaliações de um PDP](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a>Configurar o link para a página de privacidade e política

Para configurar o link para a página de privacidade e política, siga estas etapas.

1. Vá para **Início \> Sites**.
1. Selecione o nome do site. 
1. Vá para **Gerenciamento de sites \> Extensibilidade**
1. Na guia **Roteiros**, em **Privacidade e política de RNR**, selecione **Adicionar um link**. Se um link já tiver sido inserido e você desejar substituí-lo, selecione o link. 
1. Na caixa de diálogo **Adicionar um link**, selecione o link para a página de privacidade e política, e selecione **OK**. 
1. Selecione **Salvar e publicar**. 

A ilustração a seguir mostra como essa configuração se parece no Dynamics 365 Commerce.

![Configurando o link para a página de privacidade e política](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de classificações e opiniões](ratings-reviews-overview.md)

[Aceitar usar classificações e opiniões](opt-in-ratings-reviews.md)

[Gerenciar classificações e opiniões](manage-reviews.md)

[Sincronizar classificações de produto no Dynamics 365 Retail](sync-product-ratings.md)
