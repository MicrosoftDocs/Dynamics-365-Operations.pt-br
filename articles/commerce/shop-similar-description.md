---
title: Habilitar recomendações de "comprar por descrição semelhante"
description: Este artigo descreve como habilitar recomendações de produto "comprar por descrição semelhante" no Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: bebeale
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.16
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail, eCommerce
ms.search.form: ''
ms.openlocfilehash: c15122d15660144f46528bd8c575029bf9d966c6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274969"
---
# <a name="enable-shop-similar-description-recommendations"></a>Habilitar recomendações de "comprar por descrição semelhante"

[!include [banner](includes/banner.md)]

Este artigo descreve como habilitar recomendações de produto "comprar por descrição semelhante" no Microsoft Dynamics 365 Commerce.

O recurso de recomendações "comprar por descrição semelhante" no Dynamics 365 Commerce usa inteligência artificial e machine learning (IA-ML) para fornecer recomendações de produtos que tenham descrições semelhantes ao que o cliente está pesquisando. Ao disponibilizar as recomendações "comprar por descrição semelhante" para todos os canais de varejo no Commerce, os varejistas podem ajudar os clientes a encontrar o que desejam com facilidade.

A funcionalidade para as recomendações "comprar por descrição semelhante" usa o nome e descrição dos produtos de origem para encontrar e recomendar produtos visualmente semelhantes em um catálogo de produtos do varejista.

As recomendações "comprar por descrição semelhante" estão disponíveis nas experiências de PDV (ponto de venda) e comércio eletrônico.

## <a name="example-scenarios"></a>Cenários de exemplo

Os cenários de exemplo a seguir mostram os tipos de recomendações que a funcionalidade "comprar por descrição semelhante" pode fornecer:

- Um cliente vê um par de óculos de hastes estilo retrô e recebe um conjunto de recomendações para outros óculos que têm um design semelhante, no contexto do setor do varejista.
- Um cliente usa recomendações "comprar por descrição semelhante" para descobrir sabores café que sejam semelhantes a um sabor já comprado do varejista.

## <a name="set-up-shop-similar-description-recommendations"></a>Configurar recomendações "comprar por descrição semelhante"

As recomendações de produto têm suporte somente para clientes do Commerce que migraram seu armazenamento para usar o Azure Data Lake Storage Gen2.

### <a name="prerequisites"></a>Pré-requisitos

Antes que as recomendações "comprar por descrição semelhante" possam ser exibidas para os clientes, você deve atender aos seguintes pré-requisitos:

- [Habilite recomendações de produtos](enable-product-recommendations.md) no Commerce headquarters.
- Confirme se o servidor de mídia oferece suporte a chamadas HTTPS.

### <a name="turn-on-the-shop-similar-description-recommendations-feature"></a>Ativar o recurso "comprar por descrição semelhante"

Para ativar o recurso de recomendações "comprar por descrição semelhante" no Commerce headquarters, siga estas etapas:

1. No espaço de trabalho **Gerenciamento de recursos**, na lista de recursos disponíveis, procure e selecione **Comprar por descrição semelhante**.
1. No painel à direita, selecione **Habilitar**.

> [!NOTE]
> Quando você ativar o recurso, o sistema começará a gerar listas de recomendação de produtos. Pode ser necessário até um dia para que essas listas fiquem disponíveis e visíveis online nos terminais de PDV.
>
> Se você desativar o recurso, outros tipos de recomendações de produtos não serão afetados. Para obter mais informações sobre recomendações de produtos, consulte [Visão geral de recomendações de produtos](product-recommendations.md).

## <a name="add-a-shop-similar-description-button-to-product-details-pages"></a>Adicionar um botão Comprar por descrição semelhante a páginas de detalhes do produto

Depois que você ativar o recurso de recomendações de "comprar por descrição semelhante" no Commerce headquarters, você pode adicionar um botão **Comprar por descrição semelhante** à caixa de compra em qualquer página de detalhes do produto (PDP). Um cliente que selecionar esse botão será levado a uma página dedicada **Comprar por descrição semelhante** que mostra produtos visualmente semelhantes. O cliente poderá usar seletores para filtrar ainda mais os produtos.

Para adicionar um botão **Comprar por descrição semelhante** a uma PDP usando o construtor de sites do Commerce, siga estas etapas:

1. Abra uma página existente do construtor de sites que contenha um módulo de caixa de compra.
1. No painel de navegação esquerdo, selecione o módulo de caixa de compra.
1. No painel direito, marque a caixa de seleção **Habilitar link Comprar por descrição semelhante**.
1. Selecione **Salvar**.
1. Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo. Depois que a página for publicada, a PDP incluirá um botão **Comprar por descrição semelhante**.

A ilustração a seguir mostra a caixa de seleção **Habilitar link Comprar por descrição semelhante** e o botão **Comprar por descrição semelhante** em um exemplo de PDP no construtor de sites.

![Habilitar caixa de seleção para link Comprar por descrição semelhante e botão Comprar por descrição semelhante em uma PDP no construtor de sites.](./media/ter_site_builder_buybox_button.png)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral das recomendações de produtos](product-recommendations.md)

[Habilitar Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce](enable-adls-environment.md)

[Habilitar recomendações de produtos](enable-product-recommendations.md)

[Habilitar recomendações de "comprar itens semelhantes"](shop-similar-looks.md)

[Ajustar os resultados das recomendações de AI-ML](modify-product-recommendation-results.md)

[Criar manualmente recomendações selecionadas](create-editorial-recommendation-lists.md)

[Perguntas frequentes sobre recomendações de produtos](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
