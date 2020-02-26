---
title: Habilitar recomendações de produtos
description: Este tópico explica como fazer recomendações de produto com base aprendizado de máquina de inteligência artificial (AI-ML) disponível para Microsoft Dynamics 365 Commerce.
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
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2d3f1bc2526eeacb4bd6338a0679eadd95a75989
ms.sourcegitcommit: b5ecde955a69f577de46e7db10e89caaedeb2b49
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024947"
---
# <a name="enable-product-recommendations"></a>Habilitar recomendações de produtos

[!include [banner](includes/banner.md)]

Este tópico explica como fazer recomendações de produto com base aprendizado de máquina de inteligência artificial (AI-ML) disponível para Microsoft Dynamics 365 Commerce. Para obter mais informações sobre listas de recomendações de produtos, consulte [Visão geral das recomendações de produtos.](product-recommendations.md)

## <a name="recommendations-pre-check"></a>Recomendações de pré-verificação

Antes de habilitar, observe que as recomendações de produto são suportadas apenas para clientes do Commerce que migraram seu armazenamento para usar o Azure Data Lake Storage (ADLS). 

Para ver etapas de como habilitar o ADLS, consulte [Como habilitar o ADLS em um ambiente do Dynamics 365](enable-ADLS-environment.md).

Adicionalmente, verifique se as medições do RetailSale estão habilitadas. Para saber mais sobre esse processo de configuração, clique [aqui.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)


## <a name="turn-on-recommendations"></a>Ative as recomendações

Para ativar as recomendações de produtos, siga estas etapas.

1. Acesse **Retail e Commerce &gt; Recomendações de produto &gt; Parâmetros de recomendação**.
1. Na lista de parâmetros compartilhados, selecione **Listas de Recomendação**.
1. Defina a opção **Habilitar recomendações** como **Sim**.

![habilitar recomendações de produtos](./media/enableproductrecommendations.png)

> [!NOTE]
> Este procedimento inicia o processo de geração de listas recomendação de produto. Até várias horas poderá ser necessário antes que as listas estejam disponíveis e possam ser vistas no ponto de venda (PDV) ou em Dynamics 365 Commerce.

## <a name="configure-recommendation-list-parameters"></a>Configurar parâmetros da lista de recomendação

Por padrão, a lista de recomendação de produtos baseada em AI-ML fornece valores sugeridos. Você pode alterar os valores sugeridos padrão para se adequar ao fluxo de seus negócios. Para saber mais sobre como alterar os parâmetros padrão, acesse [Gerenciar resultados de recomendação de produto baseado em AI-ML](modify-product-recommendation-results.md).

## <a name="show-recommendations-on-pos-devices"></a>Mostrar recomendações em dispositivos POS

Após habilitar recomendações no back office do Commerce, o painel de recomendações deverá ser adicionado à tela PDV de controle por meio da ferramenta de layout. Para saber mais sobre esse processo, consulte [Adicionar um controle de recomendações à tela de transações em dispositivos de PDV](add-recommendations-control-pos-screen.md). 

## <a name="enable-personalized-recommendations"></a>Habilitar recomendações personalizadas

Para saber mais sobre como receber recomendações personalizadas, consulte [Habilitar recomendações personalizadas](personalized-recommendations.md).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de recomendações de produtos](product-recommendations.md)

[Habilitar recomendações personalizadas](personalized-recommendations.md)

[Adicionar listas de recomendações de produto às páginas](add-reco-list-to-page.md)

[Adicionar painel de recomendações a dispositivos POS](add-recommendations-control-pos-screen.md)

[Visão geral do módulo de coleta de produtos](product-collection-module-overview.md)

[Habilitar o ADLS no ambiente do Dynamics 365](enable-ADLS-environment.md)

