---
title: Adicionar recomendações de produtos no PDV
description: Este artigo descreve o uso de recomendações de produtos em um dispositivo de ponto de venda (PDV).
author: bebeale
ms.date: 09/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 170e2bf18aefc79a796620818c7100ff8e6e689a
ms.sourcegitcommit: f88273627ba105ede27f28fe67ccec2d7f78261c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460047"
---
# <a name="add-product-recommendations-on-pos"></a>Adicionar recomendações de produtos no PDV

[!include [banner](includes/banner.md)]

Essencialmente, as recomendações de produtos são um aplicativo de negócios transformador que abrange todos os espaços do comércio para criar experiências de descoberta de produtos sofisticadas, envolventes e personalizadas. Para implementar esse recurso no PDV, siga as etapas sobre [como adicionar recomendações a seus dispositivos de PDV.](add-recommendations-control-pos-screen.md) 

Para obter mais informações sobre os recursos de recomendações de produtos, leia a [visão geral das recomendações de produtos.](../commerce/product-recommendations.md) 

## <a name="scenarios"></a>Cenários

As recomendações de produtos são habilitadas para os seguintes cenários de PDV. Estão disponíveis no Cloud POS ou Modern POS (MPOS).

1. Na página **Detalhes de produto**:

    - Se um associado da loja acessa uma página de **Detalhes de produto** ao procurar por transações anteriores entre diferentes canais, o serviço de recomendações sugere itens adicionais que provavelmente podem ser comprados juntos. Dependendo dos complementos do serviço, os varejistas podem mostrar as recomendações **Comprar looks semelhantes** e **Comprar descrição semelhante** para produtos, além de recomendações personalizadas para usuários que têm um histórico de compras anterior.

    [![Recomendações na página Detalhes do produto.](./media/proddetails.png)](./media/proddetails.png)

2. Na página **Transação**:

    - O mecanismo de recomendação sugere itens com base na lista de itens inteira na cesta que são comprados juntos com frequência.

    > [!NOTE]
    > Para exibir recomendações na página **Transação**, o varejista precisa atualizar o layout da tela no Dynamics 365 Commerce. O controle das **Recomendações** deve ser colocado na página de **Transação**.

    [![Recomendações na página Transação.](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

## <a name="configure-commerce-to-enable-pos-recommendations"></a>Configurar o Commerce para permitir recomendações PDV 

Para configurar as recomendações do produto, confirme se você concluiu o processo de provisionamento das recomendações de produtos do Commerce seguindo as etapas em [Habilitar recomendações de produtos](../commerce/enable-product-recommendations.md). Por padrão, as recomendações são exibidas na página **Detalhes do produto** e na página **Detalhes do cliente** depois que você conclui as etapas de provisionamento e os dados viram cookies. 

## <a name="add-recommendations-to-the-transaction-screen"></a>Adicionar recomendações à tela de transações

1. Para adicionar recomendações à tela de transações, siga as etapas em [Adicionar recomendações à tela de transações](add-recommendations-control-pos-screen.md).
1. Para refletir as alterações feitas no designer do layout da tela PDV, execute o trabalho de configuração do canal **1070** no Commerce Headquarters.

> [!NOTE] 
> Se desejar habilitar as recomendações de PDV usando o arquivo de valores separados por vírgula (CSV) do RecoMock, você deve implantar o arquivo CSV na biblioteca de ativos Microsoft Dynamics Lifecycle Services (LCS) antes de configurar o Gerenciador de layout. Se você usar o arquivo CSV do RecoMock, não será necessário habilitar recomendações. O arquivo CSV só está disponível para fins de demonstração. É recomendável para clientes ou arquitetos de soluções que desejam imitar a aparência de listas de recomendação para fins de demonstração sem precisar comprar uma unidade de manutenção de estoque (SKU) complementar.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral das recomendações de produtos](product-recommendations.md)

[Habilitar Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce](enable-adls-environment.md)

[Habilitar recomendações dos produtos](enable-product-recommendations.md)

[Habilitar recomendações personalizadas](personalized-recommendations.md)

[Cancelar recomendações personalizadas](personalization-gdpr.md)

[Habilitar recomendações de "comprar looks semelhantes"](shop-similar-looks.md)

[Adicionar recomendações à tela de transações](add-recommendations-control-pos-screen.md)

[Ajustar os resultados das recomendações de AI-ML](modify-product-recommendation-results.md)

[Criar manualmente recomendações selecionadas](create-editorial-recommendation-lists.md)

[Criar recomendações com dados de demonstração](product-recommendations-demo-data.md)

[Perguntas frequentes sobre recomendações de produtos](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
