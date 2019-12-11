---
title: Perguntas frequentes sobre recomendações de produtos
description: Este tópico fornece informações sobre processos e ferramentas que você pode usar para solucionar problemas relacionados a recomendações de produtos ou resultados.
author: bebeale
manager: AnnBe
ms.date: 10/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, Core, Operations
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f4f053066ef9a10ca8a60e6eb081f73401760eb4
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770107"
---
# <a name="product-recommendations-faq"></a>Perguntas frequentes sobre recomendações de produtos

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico fornece informações sobre processos e ferramentas que você pode usar para solucionar problemas relacionados a [recomendações de produtos](product-recommendations.md) ou resultados.

## <a name="best-practices"></a>Práticas recomendadas
É muito importante usar o conceito produtos mestre e as variantes. O agrupamento correto de variantes de um produto mestre ajuda os algoritmos da lista e serviço a criar melhores modelos. Além disso, o serviço pode servir apenas uma instância de um produto em vez de colocar todas as variantes relacionadas próximas em uma lista. Quando todas as variantes relacionadas próximas são colocadas em uma lista, resultados errados ou duplicados podem ocorrer.

## <a name="why-are-products-missing-from-my-recommendation-lists"></a>Por que tenho produtos faltando nas minhas listas de recomendação?

Normalmente, se um item está ausente em uma lista de recomendação de produto, pode haver um problema de configuração de produto. Por exemplo, pode haver uma data inicial e uma data final incorreta de produto, uma dimensão pode ser configurada errado ou produtos podem não estar na classificação de canal correta, etc.

Se um item está ausente de uma lista de recomendação baseada em aprendizado de máquina de inteligência artificial (AI-ML), o item não pode modificar os critérios da recomendação ou pode não ter transações de compra suficientes para a lista de recomendação exibi-lo.

Recomendamos que você verifique estas etapas:
1. **Verifique se as recomendações de produtos foram habilitadas na matriz.** Para obter mais informações sobre como habilitar este serviço, consulte [Habilitar recomendações de produto](enable-product-recommendations.md).
1. **Verifique se as propriedades básicas de produto básico estão definidas.** Por exemplo, as classificações do produto devem ser definidas como **Incluir**.
1. **Para produtos classificados recentemente, pode levar até 3 horas antes do produto começar a aparecer na nova lista.**
1. **Se um produto ainda não estão aparecendo em Tendência, as Pessoas também gostaram de ou Comprados juntos com frequência, então esse produto pode não ter transações suficientes.** Nesse caso, você pode esperar que mais transações ocorram, atualizar parâmetros padrão de listas de recomendação, ou usar a intervenção manual para alterar os resultados da lista de produtos de recomendação. Para obter mais informações sobre os parâmetros de recomendação, consulte [Gerenciar resultados de recomendação de produto baseado em AI-ML](modify-product-recommendation-results.md).
1. **Verifique se o produto atende aos critérios da recomendação para a lista.** Para obter mais informações sobre os parâmetros de recomendação de produto, consulte [Gerenciar resultados de recomendação de produto baseado em AI-ML](modify-product-recommendation-results.md).

## <a name="how-can-i-prevent-poor-recommendation-results-from-being-returned"></a>Como posso prevenir que resultados incorretos de recomendação sejam retornados?

As listas de recomendação exigem um grande volume de transações para produzir resultados. Portanto, é importante que os usuários fornecem dados de transações de histórico completos.

Adicionalmente, os produtos que não têm nenhuma transação ou poucas transações geralmente não têm resultados **As pessoas também gostam de** ou **Comprado junto com frequência**, e eles não aparecerão em listas de recomendação em **Tendência** ou **Mais vendidos** . Essa situação pode ocorrer para cada produto novo ou para produto antigos que possuem um pequeno número de compras. Novos itens populares superarão esse problema com facilidade.

Recomendamos que você siga estas etapas:
1. **Verifique se o produto atende aos critérios da recomendação para essa lista.** Para obter mais informações sobre os parâmetros de recomendação de produto, consulte Modificar resultados de recomendação de produto baseado em AI-ML.
1. **Se o produto for novo, considere modificar uma lista de recomendação até que o produto tenha mais transações.** Para obter mais informações sobre como modificar os resultados da lista de recomendação, consulte [Gerenciar resultados de recomendação de produto baseado em AI-ML](modify-product-recommendation-results.md).


- **Verifique se o produto atende aos critérios da recomendação para essa lista.** Para obter mais informações sobre os parâmetros de recomendação de produto, consulte [Gerenciar resultados de recomendação de produto baseado em AI-ML](modify-product-recommendation-results.md).
- **Se o produto for novo, considere modificar uma lista de recomendação até que o produto tenha mais transações**. Para obter mais informações sobre como modificar os resultados da lista de recomendação, consulte [Gerenciar resultados de recomendação de produto baseado em AI-ML](modify-product-recommendation-results.md).

## <a name="can-i-remove-a-product-but-still-see-it-in-the-store"></a>Posso remover um produto mas ainda vê-lo na loja?

Você pode ajustar as listas geradas algoritmicamente se uma necessidade comercial acontecer. No entanto, se um produto é removido de uma lista de recomendação, o produto ainda poderá ser descoberto na loja. Para obter mais informações sobre como modificar os resultados da recomendação de produto, consulte [Gerenciar resultados de recomendação de produto baseado em AI-ML](modify-product-recommendation-results.md).

Se precisar bloquear um item de ser descoberto na loja, você deve alterar o valor **Classificações de item** para **Excluir**.

## <a name="how-do-i-add-a-list-to-an-e-commerce-page"></a>Como adiciono uma lista à uma página de comércio online?

Para obter informações sobre como adicionar páginas de recomendação de produto ao site de comércio online, consulte [Adicionar listas de recomendação de produto às páginas](add-reco-list-to-page.md).

## <a name="how-do-i-enable-recommendations-on-pos"></a>Como habilito recomendações em PDV?

Após habilitar recomendações de produto, é preciso adicionar o painel de recomendações à tela PDV de controle. Consulte [esta documentação de recurso](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen) para obter mais informações sobre como adicionar o painel de recomendações ao layout de seu dispositivo PDV.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de recomendações de produtos](product-recommendations.md)

[Habilitar recomendações de produtos](enable-product-recommendations.md)

[Gerenciar resultados da recomendação de produtos com base em IA-ML](modify-product-recommendation-results.md)
