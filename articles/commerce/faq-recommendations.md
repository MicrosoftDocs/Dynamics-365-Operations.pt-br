---
title: Perguntas frequentes sobre recomendações de produtos
description: Este tópico fornece informações sobre processos e ferramentas que você pode usar para solucionar problemas relacionados a recomendações de produtos ou resultados.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
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
ms.openlocfilehash: cf3df2267671b50c20b28dbdb1c6a21696bf2515
ms.sourcegitcommit: 8905d7a7a010e451c5435086480f66650ec54926
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "3664969"
---
# <a name="product-recommendations-faq"></a>Perguntas frequentes sobre recomendações de produtos


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

Após habilitar recomendações de produto, é preciso adicionar o painel de recomendações à tela PDV de controle. Para obter mais informações, consulte [Adicionar um controle de recomendação à tela de transação em dispositivos do PDV](add-recommendations-control-pos-screen.md).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral das recomendações dos produtos](product-recommendations.md)

[Habilitar Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce](enable-adls-environment.md)

[Habilitar recomendações dos produtos](enable-product-recommendations.md)

[Habilitar recomendações personalizadas](personalized-recommendations.md)

[Cancelar recomendações personalizadas](personalization-gdpr.md)

[Habilitar recomendações de "comprar looks semelhantes"](shop-similar-looks.md)

[Adicionar recomendações dos produtos no PDV](product.md)

[Adicionar recomendações à tela de transações](add-recommendations-control-pos-screen.md)

[Ajustar os resultados das recomendações de AI-ML](modify-product-recommendation-results.md)

[Criar manualmente recomendações selecionadas](create-editorial-recommendation-lists.md)

[Criar recomendações com dados de demonstração](product-recommendations-demo-data.md)
