---
title: Fontes comuns de variações de produção
description: Este artigo aborda várias fontes típicas de cada tipo de variação de produção.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostTrans, ProdCalcVarianceTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79753
ms.assetid: 14ac7db4-fb40-43c1-bb0d-1d51fc91d24f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ce352db56fe41264562fd11260f9fa91931babeeb62d352327a588fb622492d0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6766185"
---
# <a name="common-sources-of-production-variances"></a>Fontes comuns de variações de produção

[!include [banner](../includes/banner.md)]

Este artigo aborda várias fontes típicas de cada tipo de variação de produção. 

Veja a seguir algumas origens típicas de uma variação **tamanho de lote**:

-   A quantidade de bens para uma ordem de produção difere da quantidade de cálculo usada no cálculo do custo padrão. A quantidade dá a base para amortizar custos constantes.
-   O valor dos custos constantes na ordem de produção difere dos custos constantes usados no cálculo do custo padrão. Os custos constantes na ordem de produção podem ser diferentes por muitos motivos. Por exemplo, eles podem refletir os seguintes fatores:
    -   Alterações manuais à lista de materiais (BOM) de produção ou roteiro
    -   A seleção de uma versão da BOM ou do roteiro diferente quando você cria a ordem de produção
    -   Alterações de engenharia planejadas para a versão da BOM ou de roteiro atribuída ao item

Veja a seguir algumas origens típicas de uma variação **preço de produção**:

-   A categoria de custo (e o preço da categoria de custo) para o consumo informado de uma operação de roteiro é diferente da categoria de custo usada no cálculo do custo padrão.
-   O custo ativo do preço da categoria de custo é diferente do preço da categoria de custo usado no cálculo do custo padrão.

Veja a seguir algumas origens típicas de uma variação **quantidade de produção**:

-   Emitir a mais ou a menos um componente de material.
-   Relatar uma operação de roteiro a mais ou a menos.
-   Você recebe a mais ou a menos a quantidade de bens do item principal, relativa a quantidade do pedido. No entanto, você emite componentes e relata operações completamente, com base na quantidade do pedido para a ordem de produção.

Veja a seguir algumas origens típicas de uma variação **substituição de produção**:

-   Você emite um componente de material que não está na BOM de produção.
-   Você adiciona manualmente um componente à BOM de produção e relata o componente como consumido.
-   Você relatar um item como consumido, mas não o adiciona manualmente à BOM de produção.
-   Você adicionar manualmente uma operação à BOM de roteiro de produção e relata aquela operação como consumida.
-   Quando você cria a ordem de produção, você seleciona uma versão da BOM diferente daquela usada no cálculo do custo padrão.
-   Quando você cria a ordem de produção, você seleciona a versão de roteiro diferente daquela usada no cálculo do custo padrão.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]