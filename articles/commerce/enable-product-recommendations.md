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
ms.openlocfilehash: ecda571a356c6968196d09cc19923105cf4544ab
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770130"
---
# <a name="enable-product-recommendations"></a>Habilitar recomendações de produtos

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico explica como fazer recomendações de produto com base aprendizado de máquina de inteligência artificial (AI-ML) disponível para Microsoft Dynamics 365 Commerce. Para obter mais informações sobre listas de recomendações de produtos, consulte [Visão geral das recomendações de produtos.](product-recommendations.md)

## <a name="recommendations-pre-check"></a>Recomendações de pré-verificação
Antes de habilitar, observe que as recomendações de produto são suportadas apenas para clientes F&O compatível com versão 10.0.6 e migraram seu armazenamento usando BDL. 

Adicionalmente, verifique se as medições do RetailSale estão habilitadas. Para saber mais sobre o processo de instalação, vá [aqui.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)


## <a name="turn-on-recommendations"></a>Ative as recomendações

Para ativar as recomendações de produtos, siga estas etapas.

1. Acesse **Varejo** &gt; **Recomendações de produto** &gt; **Parâmetros de recomendação**.
1. Na lista de parâmetros de varejo compartilhados, selecione **Listas de recomendação**.
1. Defina a opção **Habilitar recomendações** como **Sim**.

![habilitar recomendações de produtos](./media/enableproductrecommendations.png)

> [!NOTE]
> Este procedimento inicia o processo de geração de listas recomendação de produto. Até várias horas poderá ser necessário antes que as listas estejam disponíveis e possam ser vistas no ponto de venda (PDV) ou em Dynamics 365 for Commerce.

## <a name="configure-recommendation-list-parameters"></a>Configurar parâmetros da lista de recomendação
Por padrão, a lista de recomendação de produtos baseada em AI-ML fornece valores sugeridos. Você pode alterar os valores sugeridos padrão para se adequar ao fluxo de seus negócios. Para saber mais sobre como alterar os parâmetros padrão, acesse [Gerenciar resultados de recomendação de produto baseado em AI-ML](modify-product-recommendation-results.md).

## <a name="show-recommendations-on-pos-devices"></a>Mostrar recomendações em dispositivos POS
Após habilitar recomendações no back office, o painel de recomendações deve ser adicionado à tela PDV de controle por meio da ferramenta de layout. Para saber mais sobre esse processo, vá [aqui.](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)


## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de recomendações de produtos](product-recommendations.md)

[Adicionar listas de recomendações de produto às páginas](add-reco-list-to-page.md)

[Adicionar painel de recomendações a dispositivos POS](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)


