---
title: Habilitar recomendações de "descrição de comprar itens semelhantes"
description: Este tópico descreve como habilitar recomendações de "descrição de comprar itens semelhantes" de produtos no Microsoft Dynamics 365 Commerce.
author: bsokolov
manager: AnnBe
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: b3b7abf47a3bdacaa4b91ae32b68a809a84b0b1d
ms.sourcegitcommit: 872600103d2a444d78963867e5e0cdc62e68c3ec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2021
ms.locfileid: "5098612"
---
# <a name="enable-shop-similar-description-recommendations"></a>Habilitar recomendações de "descrição de comprar itens semelhantes"

[!include [banner](includes/banner.md)]

Este tópico descreve como habilitar recomendações de "descrição de comprar itens semelhantes" de produtos no Microsoft Dynamics 365 Commerce.

O recurso de recomendações de "descrição de comprar itens semelhantes" no Dynamics 365 Commerce usa inteligência artificial e machine learning (IA-ML) para fornecer recomendações de produtos que tenham descrições semelhantes ao que o cliente está pesquisando. Ao disponibilizar as recomendações de "descrição de comprar itens semelhantes" para todos os canais de varejo no Commerce, os varejistas podem ajudar os clientes a encontrar o que desejam com facilidade.

A funcionalidade para as recomendações de "descrição de comprar itens semelhantes" usa o nome e descrição dos produtos de origem para encontrar e recomendar produtos visualmente semelhantes em um catálogo de produtos do varejista.

As recomendações de "descrição de comprar itens semelhante" estão disponíveis nas experiências de PDV (ponto de venda) e comércio eletrônico.

## <a name="example-scenarios"></a>Cenários de exemplo

Os cenários de exemplo a seguir mostram os tipos de recomendações que a funcionalidade "descrição de comprar itens semelhantes" pode fornecer:

- Um cliente vê um par de óculos de hastes estilo retrô e recebe um conjunto de recomendações para outros óculos que têm um design semelhante, no contexto do setor do varejista.
- Um cliente usa recomendações "descrição de comprar itens semelhantes" para descobrir sabores café que sejam semelhantes a um sabor já comprado do varejista.

## <a name="set-up-shop-similar-description-recommendations"></a>Configurar recomendações de "descrição de comprar itens semelhantes"

As recomendações de produto têm suporte somente para clientes do Commerce que migraram seu armazenamento para usar o Azure Data Lake Storage Gen2.

### <a name="prerequisites"></a>Pré-requisitos

Antes que as recomendações de "descrição de comprar itens semelhantes" possam ser exibidas para os clientes, você deve atender aos seguintes pré-requisitos:

- [Habilite recomendações de produtos](enable-product-recommendations.md) na sede do Commerce.
- Confirme se o servidor de mídia oferece suporte a chamadas HTTPS.

### <a name="turn-on-the-shop-similar-description-recommendations-feature"></a>Ativar o recurso "descrição de comprar itens semelhantes"

Para ativar o recurso de recomendações de "descrição de comprar itens semelhantes" na sede do Commerce, siga estas etapas:

1. No espaço de trabalho **Gerenciamento de recursos**, na lista de recursos disponíveis, procure e selecione a **Descrição de comprar itens semelhantes**.
1. No painel à direita, selecione **Habilitar**.

> [!NOTE]
> Quando você ativar o recurso, o sistema começará a gerar listas de recomendação de produtos. Pode ser necessário até um dia para que essas listas fiquem disponíveis e visíveis online nos terminais de PDV.
>
> Se você desativar o recurso, outros tipos de recomendações de produtos não serão afetados. Para obter mais informações sobre recomendações de produtos, consulte [Visão geral de recomendações de produtos](product-recommendations.md).

## <a name="add-a-shop-similar-description-button-to-product-details-pages"></a>Adicionar um botão Descrição de comprar itens semelhantes a páginas de detalhes do produto

Depois que você ativar o recurso de recomendações de "Descrição de comprar itens semelhantes" na matriz do Commerce, você pode adicionar um botão **Descrição de comprar itens semelhantes** à caixa de compra em qualquer página de detalhes do produto (PDP). Um cliente que selecionar esse botão será levado a uma página dedicada de **Descrição de comprar itens semelhantes** que mostra produtos visualmente semelhantes. O cliente poderá usar seletores para filtrar ainda mais os produtos.

Para adicionar um botão **Descrição de comprar itens semelhantes** a uma PDP usando o construtor de sites do Commerce, siga estas etapas:

1. Abra uma página existente do construtor de sites que contenha um módulo de caixa de compra.
1. No painel de navegação esquerdo, selecione o módulo de caixa de compra.
1. No painel direito, marque a caixa de seleção **Habilitar link para Descrição de comprar itens semelhantes**.
1. Selecione **Salvar**.
1. Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo. Depois que a página for publicada, a PDP incluirá um botão **Descrição de comprar itens semelhantes**.

A ilustração a seguir mostra a caixa de seleção **Habilitar link para Descrição de comprar itens semelhantes** e o botão **Descrição de comprar itens semelhantes** em um exemplo de PDP no construtor de sites.

![Habilitar caixa de seleção para link de Descrição de comprar itens semelhantes e botão Descrição de comprar itens semelhantes em uma PDP no construtor de sites](./media/ter_site_builder_buybox_button.png)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral das recomendações de produtos](product-recommendations.md)

[Habilitar Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce](enable-adls-environment.md)

[Habilitar recomendações de produtos](enable-product-recommendations.md)

[Habilitar recomendações de "comprar itens semelhantes"](shop-similar-looks.md)

[Ajustar os resultados das recomendações de AI-ML](modify-product-recommendation-results.md)

[Criar manualmente recomendações selecionadas](create-editorial-recommendation-lists.md)

[Perguntas frequentes sobre recomendações de produtos](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]