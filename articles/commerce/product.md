---
title: Adicionar recomendações de produtos no PDV
description: Este tópico descreve o uso de recomendações de produtos em um dispositivo de ponto de venda (PDV).
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7afe9225b8fc966ca154a5eb7421e8d4cc7c3023
ms.sourcegitcommit: 8905d7a7a010e451c5435086480f66650ec54926
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "3664825"
---
# <a name="add-product-recommendations-on-pos"></a>Adicionar recomendações de produtos no PDV

[!include [banner](includes/banner.md)]

Essencialmente, as recomendações de produtos são um aplicativo de negócios transformador que abrange todos os espaços do comércio para criar experiências de descoberta de produtos sofisticadas, envolventes e personalizadas. Para implementar esse recurso no PDV, siga as etapas sobre [como adicionar recomendações a seus dispositivos de PDV.](add-recommendations-control-pos-screen.md) 

Para obter mais informações sobre os recursos de recomendações de produtos, leia a [visão geral das recomendações de produtos.](../commerce/product-recommendations.md) 

## <a name="scenarios"></a>Cenários

As recomendações de produtos são habilitadas para os seguintes cenários de PDV. Estão disponíveis no Cloud POS ou Modern POS (MPOS).

1. Na página **Detalhes de produto**:

    - Se um associado da loja acessa uma página de **Detalhes de produto** ao procurar por transações anteriores entre diferentes canais, o serviço de recomendações sugere itens adicionais que provavelmente podem ser comprados juntos.

    [![Recomendações na página Detalhes do produto](./media/proddetails.png)](./media/proddetails.png)

2. Na página **Transação**:

    - O mecanismo de recomendação sugere itens com base na lista de itens inteira na cesta que são comprados juntos com frequência.

    > [!NOTE]
    > Para exibir recomendações na página **Transação**, o varejista precisa atualizar o layout da tela no Dynamics 365 Commerce. O controle das **Recomendações** deve ser colocado na página de **Transação**.

    [![Recomendações na página Transação](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

## <a name="configure-commerce-to-enable-pos-recommendations"></a>Configurar o Commerce para permitir recomendações PDV

Para configurar as recomendações de produtos, siga estas etapas:

1. Verifique se o serviço foi atualizado para a **compilação 10.0.6.**
2. Sigas as instruções sobre como [habilitar recomendações de produtos](../commerce/enable-product-recommendations.md) para sua empresa.
3. Opcional: Para exibir recomendações na tela de transação, vá para **Layout de tela**, escolha seu layout de tela, inicie o **Designer do layout da tela** e depois deixe o controle de **recomendações** onde necessário.
4. Vá para **Parâmetros de Commerce**, selecione **Aprendizado de máquina** e **Sim** em **Habilitar recomendações de PDV**.
5. Para consultar recomendações no PDV, rode o trabalho de configuração global **1110**. Para refletir as alterações feitas ao designer de layout de tela do PDV, rode o trabalho de configuração de canal **1070**.

## <a name="troubleshoot-issues-where-you-have-product-recommendations-already-enabled"></a>Solucionar problemas em que as recomendações de produtos já estejam habilitadas

- Navegue até **Parâmetros do Commerce** \> **Listas de recomendação** \> **Desabilitar recomendações de produtos** e execute **Trabalho de configuração global \[9999\]**. 
- Se você adicionou o **Controle de recomendações** à sua tela de transação usando o **Designer do layout da tela**, remova-o também.
- Se tiver outras dúvidas, confira as [Perguntas frequentes sobre recomendações do produto](../commerce/faq-recommendations.md) para obter mais informações.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral das recomendações dos produtos](product-recommendations.md)

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
