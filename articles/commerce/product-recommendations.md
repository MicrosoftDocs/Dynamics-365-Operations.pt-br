---
title: Visão geral das recomendações de produtos
description: Este artigo fornece informações gerais sobre as recomendações do produto. As recomendações de produtos permitem que os clientes encontrem com facilidade e rapidez os produtos que desejam e até produtos que não pretendiam comprar originalmente.
author: Moonma
ms.date: 05/26/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: moonma
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2cb62638e89dd9cd7c01739244d808f664b3f3b1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8867723"
---
# <a name="product-recommendations-overview"></a>Visão geral das recomendações de produtos

[!include [banner](includes/banner.md)]

O Microsoft Dynamics 365 Commerce pode ser usado para mostrar recomendações de produtos no site de comércio eletrônico e no dispositivo de ponto de venda (PDV). As recomendações de produtos são itens nos quais um cliente pode estar interessado. As recomendações baseiam-se em tendências de compra dos outros clientes em lojas online e físicas.

As recomendações de produtos permitem que os clientes encontrem com facilidade e rapidez os produtos que desejam, enquanto têm uma experiência que os atende bem. A venda cruzada e a adicional podem até ser usadas para ajudar os clientes a encontrar produtos adicionais que eles não pretendiam comprar originalmente. Quando as recomendações são usadas para aprimorar a descoberta do produto, elas criam mais oportunidades de conversão, ajudam a aumentar a receita de vendas e até a aumentar a satisfação e retenção de clientes.

No comércio eletrônico, as recomendações de produtos são baseadas nas tecnologias de aprendizado de máquina do Microsoft Recommendations em larga escala.

Este serviço é um complemento do Dynamics 365 Commerce. Para obter mais informações, baixe o [Guia de licenciamento mais recente do Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).


## <a name="recommendation-service"></a>Serviço de recomendação

O serviço de recomendações de produtos utiliza as tecnologias de inteligência artificial e de vida de máquina (AI-ML) da seguinte maneira:

- Os dados no formato que o serviço de Recomendação exige é extraído do banco de dados operacional do Commerce e enviado ao Azure Data Lake Storage ou à loja da Entidade.
- O serviço da recomendações usa os dados armazenados para treinar modelos da recomendação para as listas **As pessoas também gostam de**, **Frequentemente comprado junto**, **Novo**, **Mais vendidos** e **Mais populares** .

## <a name="scenarios"></a>Cenários

As recomendações de produtos estão disponíveis para os seguintes cenários:

- **Em qualquer página da loja para navegação ou página inicial no comércio eletrônico:** Se os clientes ou associados da loja visitam uma página da loja, o mecanismo de recomendação pode sugerir produtos nas listas **Novo**, **Mais Vendidos** e **Mais Populares**.
- **Na página de detalhes do Produto:** Se os clientes ou associados da loja visitam uma página de **Detalhes do produto**, o mecanismo de recomendação sugere itens adicionais que provavelmente também serão comprados. Esses itens são exibidos na lista **As pessoas também gostam de** .
- **Na página da Transação ou na página de check-out:** O mecanismo de recomendação sugere itens, com base na lista completa de itens na cesta. Esses itens são exibidos na lista **Compra junto com frequência** .
- **Recomendações personalizadas:** os vendedores podem fornecer aos clientes conectados uma lista de **seleções para você** personalizada, além da nova funcionalidade que permite a personalização de cenários de lista existentes com base nesse cliente. Para saber mais, consulte [Habilitar recomendações personalizadas](personalized-recommendations.md).

### <a name="types-of-product-recommendations"></a>Tipos de recomendações de produto

A tabela a seguir descreve vários tipos de recomendações de produto automatizadas disponíveis para varejistas a fim de implementar em sua solução Dynamics 365 Commerce por meio do [módulo de coleção de produtos](product-collection-module-overview.md). Os varejistas também podem mostrar resultados personalizados para um usuário conectado, caso o autor do site escolha essa opção.

| Módulos de coleta de produtos  | Tipo | descrição |
|----------------------------|------|-------------|
| Nova                        | Algorítmico | Este módulo mostra uma lista de produtos mais novos que foram classificadas recentemente para canais e os catálogos. |
| Mais vendidos               | Algorítmico | Este módulo mostra uma lista de produtos que estão classificados por número mais alto de venda. |
| Mais populares                   | Algorítmico | Esse módulo mostra uma lista dos produtos com melhor desempenho por um determinado período, classificado pelo maior número de vendas.  |
| Frequentemente comprado junto | AI-ML | Este módulo recomenda uma lista de produtos que normalmente são comprados juntamente com o conteúdo do carrinho de clientes atual. |
| As pessoas também gostam           | AI-ML | Este módulo recomenda produtos para um determinado produto de semente com base nos padrões de compra do consumidor. |
| Seleções para Você              | AI-ML | Este módulo recomenda uma lista individualizada de produtos com base em padrões de compra do usuário conectado. Para um usuário convidado, esta lista será recolhida. |

## <a name="additional-resources"></a>Recursos adicionais

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

[Perguntas frequentes sobre recomendações de produtos](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
