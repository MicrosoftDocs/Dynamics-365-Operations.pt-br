---
title: Visão geral da pesquisa habilitada para a nuvem
description: Este tópico fornece uma visão geral de pesquisa baseada em nuvem no Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 06/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c78af42313d83ebec5a56f83682f394c5e9d21f08851aaa0493563163d76046b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722021"
---
# <a name="cloud-powered-search-overview"></a>Visão geral da pesquisa habilitada para a nuvem

[!include [banner](includes/banner.md)]

Este tópico fornece uma visão geral de pesquisa baseada em nuvem no Microsoft Dynamics 365 Commerce.

A descoberta de produto ajuda a garantir que clientes podem encontrar produtos rápido e facilmente navegando em categorias, pesquisa e filtros. Os varejistas consideram a descoberta de produtos a principal ferramenta para a interação com os clientes em todos os canais.

Os clientes são acostumados à resposta quase que instantânea de mecanismos de pesquisa da Web, sites de comércio online sofisticados, aplicativos sociais, sugestões automáticas que aparecem conforme digitam termos de pesquisa, navegação multifacetada e destaques. Se os clientes não conseguem encontrar os produtos que estão procurando rapidamente suficiente em um armazenamento de comércio online, eles não hesitarão em ir para uma loja de comércio online diferente.

A descoberta de produto baseada em nuvem no Dynamics 365 Commerce ajuda os vendedores a continuarem a aumentar retenção de cliente e taxas de conversão entre todos os canais, tanto em canais de comércio online e ponto de venda (PDV).

A pesquisa da experiência do Dynamics 365 Commerce melhorou os recursos para ajudar fornecedores a obter melhor descoberta de produto. Simultaneamente, esses recursos entregam a escalabilidade e o desempenho necessário para o tráfego de comércio online.

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

A funcionalidade de sugestão automática mostra apenas palavras-chave que inicial uma pesquisa da palavra-chave correspondente. Devido aos novos aprimoramentos no Dynamics 365 Commerce, os clientes podem frequentemente descobrir links de produto antes de terminar a digitação.

Dynamics 365 Commerce também oferece suporte a funcionalidade de resultados da palavra-chave em várias categorias. Essa funcionalidade permite que os clientes vejam o número de palavras-chave correspondentes entre categorias e aciona uma pesquisa para uma palavra-chave em outras categorias.

A ilustração a seguir mostra um exemplo de sugestão automática mais imersiva sendo usada.

![sugestão automática imersiva.](./media/ImmersiveAutoSuggestUX.png)

## <a name="sort"></a>Classificar

A classificação avançada no Dynamics 365 Commerce permite que cliente classifiquem, pesquisem e naveguem em resultados de busca e refinem por critérios como preço, nome de produto e número de produto. Os clientes também podem classificar resultados baseados em se o produto é novo, muito vendido ou recentemente adicionado.

>[!NOTE]
>Esses recursos de pesquisa habilitados para a nuvem estão disponíveis a partir da versão 10.0.8. Verifique se em **Parâmetros do Commerce > Parâmetros de Configuração** há uma entrada para "ProductSearch.UseAzureSearch definido como 'true'". 
![Parâmetros de configuração para pesquisa habilitada para a nuvem.](./media/CloudPoweredSearchConfigurationParameters.png)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da página de aterrissagem da categoria padrão e da página de resultados da pesquisa](category-search-page-overview.md)

[Gerenciar metadados de SEO](manage-seo-metadata.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
