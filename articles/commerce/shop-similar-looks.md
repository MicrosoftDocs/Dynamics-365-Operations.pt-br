---
title: Habilitar recomendações de "comprar itens semelhantes"
description: Este artigo descreve como habilitar recomendações de "comprar looks semelhantes" de produtos no Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.13
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail, eCommerce
ms.search.form: ''
ms.openlocfilehash: 26eb436d889ac81cde730daca9b44d1deeda6c74
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282041"
---
# <a name="enable-shop-similar-looks-recommendations"></a>Habilitar recomendações de "comprar itens semelhantes"

[!include [banner](includes/banner.md)]

Este artigo descreve como habilitar recomendações de "comprar looks semelhantes" de produtos no Microsoft Dynamics 365 Commerce.

O recurso de recomendações de "comprar looks semelhantes" no Dynamics 365 Commerce usa o poder da inteligência artificial e do machine learning (IA-ML) para fornecer recomendações de produtos visualmente semelhantes para os clientes. Ao disponibilizar as recomendações de "comprar looks semelhantes" para todos os canais de varejo no Commerce, os varejistas podem aumentar a satisfação do cliente ajudando-os a encontrar o que desejam com facilidade.

A funcionalidade para as recomendações de "comprar looks semelhantes" usa as imagens dos produtos de grades de produtos de origem para encontrar e recomendar produtos visualmente semelhantes em um catálogo de produtos do varejista. 

As recomendações de "comprar looks semelhante" estão disponíveis nas experiências de PDV (ponto de venda) e comércio eletrônico.

### <a name="example-scenarios"></a>Cenários de exemplo

- Um cliente vê um suéter preto listrado e recebe uma recomendação para um suéter semelhante em vermelho. O cliente seleciona o produto recomendado em vez do produto visto originalmente e recebe recomendações para produtos semelhantes em vermelho. 
- Um cliente usa recomendações de "comprar looks semelhantes" para descobrir brincos que combinem com um anel que o cliente esteja interessado em comprar.

## <a name="enable-shop-similar-looks-recommendations-in-commerce-headquarters"></a>Habilitar recomendações de "comprar looks semelhantes" no Commerce headquarters

As recomendações de produto têm suporte somente para clientes do Commerce que migraram seu armazenamento para usar o Azure Data Lake Gen2.

### <a name="prerequisites"></a>Pré-requisitos

Antes que os varejistas comecem a mostrar recomendações de "comprar looks semelhantes" para os clientes, há duas etapas de pré-requisito:

- [Habilite recomendações de produtos](enable-product-recommendations.md) no Commerce headquarters.
- Confirme se o servidor de mídia oferece suporte a chamadas HTTPS.

Para que o mecanismo de recomendações acesse as imagens dos produtos, os varejistas devem gerar as URLs dos produtos. Para gerar as URLs dos produtos no Commerce headquarters, siga estas etapas:

1. Acesse **Imagens de produtos**.
1. No Painel de Ações, selecione **Definir modelo de mídia**.
1. No painel de propriedades **Definir modelo de mídia**, em **URLs de mídia**, selecione **Gerar URLs**.

> [!NOTE]
> Ao habilitar o recurso de recomendações "comprar looks semelhantes", o processo de geração de listas de recomendação de produtos será iniciado. Talvez seja necessário até um dia para que essas listas estejam disponíveis e visíveis online nos terminais de PDV.

Para habilitar o recurso de recomendações de "comprar looks semelhantes" no Commerce headquarters, siga estas etapas:

1. Acesse **Gerenciamento de recursos**.
1. Na lista de recursos disponíveis, procure e selecione **Comprar looks semelhantes**.
1. No painel direito, selecione **Habilitar** para ativar o serviço.

A ilustração a seguir mostra o recurso **Comprar looks semelhantes** na página **Gerenciamento de recursos** no Commerce headquarters.

![O recurso "Comprar looks semelhantes" na página "Gerenciamento de recursos" no Commerce headquarters.](./media/enableshopsimilarlooks.png)

Depois que as tarefas anteriores forem concluídas, os terminais de PDV serão aprimorados automaticamente com um painel contextual **Comprar looks semelhantes**. Ao selecionar **Ver mais**, os usuários do terminal de PDV podem ser levados a uma página dedicada de "Comprar looks semelhantes" que pode ser filtrada ainda mais.

> [!NOTE]
> Se você desativar o recurso de recomendações de "Comprar looks semelhantes", nenhum outro tipo de recomendação de produtos será afetado. Para obter mais informações sobre recomendações de produtos, consulte [Visão geral de recomendações de produtos](product-recommendations.md).

## <a name="add-a-shop-similar-looks-button-to-product-details-pages-by-using-commerce-site-builder"></a>Adicionar um botão Comprar looks semelhantes às páginas de detalhes dos produtos usando o construtor de sites do Commerce

Depois que você habilitar o recurso de recomendações de "Comprar looks semelhantes" no Commerce headquarters, uma opção no construtor de sites do Commerce permitirá que os varejistas adicionem um botão **Comprar looks semelhantes** à caixa de compra em qualquer página de detalhes do produto (PDP). Um cliente que selecionar esse botão será levado a uma página dedicada de "comprar looks semelhantes" que retornará produtos visualmente semelhantes. Nela, o cliente poderá usar seletores para filtrar ainda mais os produtos.

Para adicionar um botão **Comprar looks semelhantes** e uma PDP usando o construtor de sites do Commerce, siga estas etapas:

1. Abra uma página existente do construtor de sites que contenha um módulo de caixa de compra.
1. No painel de navegação esquerdo, selecione o módulo de caixa de compra.
1. No painel de navegação direito, marque a caixa de seleção **Habilitar Link para Comprar Looks Semelhantes**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo. Depois que a página for publicada, a PDP incluirá um botão **Comprar looks semelhantes**.

A ilustração a seguir mostra a caixa de seleção **Habilitar Link para Comprar Looks Semelhantes** e o botão **Comprar looks semelhantes** em um exemplo de PDP no construtor de sites.

![Caixa de seleção Habilitar Link para Comprar Looks Semelhantes e o botão Comprar looks semelhantes em uma PDP no construtor de sites.](./media/SSLecomtooling.png)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral das recomendações de produtos](product-recommendations.md)

[Habilitar Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce](enable-adls-environment.md)

[Habilitar recomendações dos produtos](enable-product-recommendations.md)

[Cancelar recomendações personalizadas](personalization-gdpr.md)

[Adicionar recomendações de produtos no PDV](product.md)

[Adicionar recomendações à tela de transação](add-recommendations-control-pos-screen.md)

[Ajustar os resultados das recomendações de AI-ML](modify-product-recommendation-results.md)

[Criar manualmente recomendações selecionadas](create-editorial-recommendation-lists.md)

[Criar recomendações com dados de demonstração](product-recommendations-demo-data.md)

[Perguntas frequentes sobre recomendações de produtos](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
