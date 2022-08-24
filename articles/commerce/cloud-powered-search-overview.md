---
title: Visão geral da pesquisa habilitada para a nuvem
description: Este artigo fornece uma visão geral de pesquisa baseada em nuvem no Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 02/28/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.assetid: ''
ms.openlocfilehash: ed80ff42ea5c6e6a904ea2855953d006f66aad37
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273657"
---
# <a name="cloud-powered-search-overview"></a>Visão geral da pesquisa habilitada para a nuvem

[!include [banner](includes/banner.md)]

Este artigo fornece uma visão geral de pesquisa baseada em nuvem no Microsoft Dynamics 365 Commerce.

A descoberta de produto ajuda a garantir que clientes podem encontrar produtos rápido e facilmente navegando em categorias, pesquisa e filtros. Os varejistas consideram a descoberta de produtos uma ferramenta principal para a interação do cliente pelos canais da plataforma Cloud Scale Unit (CSU), como comércio eletrônico e ponto de venda (PDV).

Os clientes são acostumados à resposta quase que instantânea de mecanismos de pesquisa da Web, sites de comércio online sofisticados, aplicativos sociais, sugestões automáticas que aparecem conforme digitam termos de pesquisa, navegação multifacetada e destaques. Se os clientes não encontrarem rapidamente o produto que procuram em uma loja de comércio eletrônico, não hesitarão em ir a uma loja de comércio eletrônico diferente.

A descoberta de produtos baseada na nuvem no Commerce ajuda os varejistas a continuarem a aumentar a retenção de consumidores e as taxas de conversão nos canais da plataforma CSU.

A experiência de pesquisa do Commerce tem recursos aprimorados para ajudar varejistas a obter melhor descoberta de produto. Simultaneamente, esses recursos entregam a escalabilidade e o desempenho necessário para o tráfego de comércio eletrônico.

## <a name="browse-and-search"></a>Navegação e pesquisa

A importância e o desempenho da pesquisa são fatores-chave da experiência de omnicanal, pois a descoberta de produção depende principalmente na funcionalidade de pesquisa para a pesquisa documental e navegação de conteúdo. Uma experiência de pesquisa eficaz e eficiente ajuda a melhorar a conversão.

A ilustração a seguir mostra um exemplo típico da funcionalidade de consulta e pesquisa.

![Página de aterrissagem de pesquisa.](./media/SearchLanding.png)

## <a name="faceted-navigation-and-choice-summary"></a>Navegação multifacetada e resumo de escolha 

A navegação multifacetada ajuda clientes a navegarem mais facilmente por conteúdo permitindo que eles filtrem refinadores que são vinculados aos termos em um conjunto de termo. Depois de um cliente selecionar e aplicar refinadores, um resumo das escolhas é exibido. 

Usando a navegação multifacetada, você pode configurar refinadores para termos diferentes em um conjunto de termo, sem ter de criar página as adicionais. 

A ilustração a seguir mostra um exemplo na navegação multifacetada usada em uma pesquisa.

![Resumo de escolhas.](./media/ChoiceSummary.png)

## <a name="immersive-autosuggest"></a>Sugestão automática imersiva

A funcionalidade de sugestão automática mostra apenas palavras-chave que disparam uma pesquisa da palavra-chave correspondente. Devido aos novos aprimoramentos no Commerce, os clientes podem frequentemente descobrir links de produto antes de terminar a digitação.

O Commerce também oferece suporte a funcionalidade de resultados da palavra-chave em várias categorias. Essa funcionalidade permite que os clientes vejam o número de palavras-chave correspondentes entre categorias e aciona uma pesquisa para uma palavra-chave em outras categorias.

A ilustração a seguir mostra um exemplo de sugestão automática mais imersiva sendo usada.

![sugestão automática imersiva.](./media/ImmersiveAutoSuggestUX.png)

## <a name="sort"></a>Classificar

A funcionalidade Classificar permite aos clientes classificar, pesquisar e navegar em resultados de categoria, e refinar por critérios como preço, nome de produto e número do produto. Se você habilitar [Recomendações de produtos](product-recommendations.md) no seu ambiente, os clientes também poderão classificar os resultados com base em critérios de classificação avançados, como novos, mais vendidos e tendências.


> [!NOTE]
> Esses recursos de pesquisa habilitados para a nuvem estão disponíveis a partir da versão 10.0.8. Verifique se há uma entrada para "ProductSearch.UseAzureSearch" definida como 'true' em **Parâmetros do Commerce > Parâmetros de Configuração**. 
![Parâmetros de configuração para pesquisa habilitada para a nuvem.](./media/CloudPoweredSearchConfigurationParameters.png)
>As opções de classificação avançadas, como novos, mais vendidos e tendências, estão disponíveis com o Commerce SSK versão 9.35+ e o Dynamics 365 Commerce versão 10.0.20.  


## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da página de aterrissagem da categoria padrão e da página de resultados da pesquisa](category-search-page-overview.md)

[Gerenciar metadados de SEO](manage-seo-metadata.md)


[!INCLUDE [footer-include](../includes/footer-banner.md)]
