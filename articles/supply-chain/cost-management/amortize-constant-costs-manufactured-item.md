---
title: "Amortização de custos constantes para um item fabricado"
description: "Os custos constantes de um item fabricado refletem os tempos de preparação da operação e os componentes com uma quantidade constante ou um valor de sucata constante."
author: AndersGirke
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCalcDialog, BOMCalcTable, BOMCalcTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 274503
ms.assetid: 535ab25d-a031-4e8c-84ec-478f2987a1ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 75c0f5bcff0aae63aa8c7dae9b0767f8c7e6a81c
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="amortize-constant-costs-for-a-manufactured-item"></a>Amortização de custos constantes para um item fabricado

[!include [banner](../includes/banner.md)]

Os custos constantes de um item fabricado refletem os tempos de preparação da operação e os componentes com uma quantidade constante ou um valor de sucata constante. 

O conceito do tamanho de um lote de custos é usado para amortizar esses custos constantes no custo calculado de um item fabricado. Esse conceito tem vários sinônimos, um dos quais é tamanho de lote contabilidade. O conceito de amortizar custos constantes também tem vários sinônimos, um dos quais é custos constantes proporcionais.

A quantidade de um tamanho de lote de avaliação de custo para um item fabricado é usada em um cálculo de lista de materiais (BOM). A quantidade depende de como você inicia e executa o cálculo de BOM, como explicado a seguir:

-   Quantidade de cálculo padrão no cálculo de BOM de um item: a quantidade de ordem padrão do item para estoque atua como o tamanho de lote de avaliação de custos, mas o valor padrão pode ser uma quantidade maior para refletir o múltiplo da quantidade da ordem do item. O múltiplo e a quantidade de ordem padrão do item podem ser definidos nas configurações de ordem padrão ou de ordem específica ao site.
-   A quantidade de cálculo especificada no cálculo de BOM de um item − a quantidade de cálculo especificada atua como o tamanho de lote de custos do item. A quantidade de cálculo inicialmente usa a quantidade de ordem padrão do item, mas o valor padrão pode ser substituído manualmente. A quantidade de cálculo especificada representa o tamanho do lote de avaliação de custo para o item especificado e para os componentes fabricados com um tipo de linha de BOM de produção. Isso é porque supõe-se que o componente será produzido na quantidade exata. O tamanho de lote de avaliação de custo para outros componentes fabricados com um tipo de linha de BOM igual a item refletirá a quantidade de ordem padrão.
-   A quantidade especificada de marca a ser solicitada no calculo de BOM de um item − a quantidade de cálculo especificada atua como o tamanho de lote de custos para o item e seus componentes fabricados quando os cálculos de BOM usam um modo de detalhamento de marca a ser solicitada. Supõe-se que os componentes fabricados serão produzidos na quantidade exata, assim como um componente fabricado com um tipo de linha de BOM igual a produção.
-   A quantidade de cálculo especificada em um cálculo de BOM específico a uma ordem − um cálculo de BOM específico a uma ordem pode ser realizado para um item de linha em uma ordem de venda, cotação de venda ou ordem de serviço. A quantidade de cálculo especificada usa como padrão a quantidade no item de linha de origem, mas a quantidade padrão pode ser substituída. Você pode selecionar se deseja que o cálculo de BOM específico a uma ordem use um modo de detalhamento de marca a ser solicitada ou de vários níveis.

O valor calculado dos custos constantes amortizados de um item fabricado é denominado encargos.






