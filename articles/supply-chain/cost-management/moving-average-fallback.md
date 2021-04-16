---
title: Média móvel, sequência de custos de fallback
description: Este tópico fornece informações sobre sequências de custos de fallback para cálculos de média de movimentos no Microsoft Dynamics 365 Supply Chain Management.
author: AndersGirke
ms.date: 03/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-03-25
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 09da3c3a79b5540670db25d5466023132d2848f4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832265"
---
# <a name="moving-average-fallback-cost-sequence"></a>Média móvel, sequência de custos de fallback

Uma maneira de calcular o custo do seu estoque é usando uma _média de movimentos_. Até três valores de custo podem ser associados a cada item de estoque:

- **Problema mais recente** – O custo do problema mais recente atribuído antes de o estoque ficar negativo
- **Custo ativo** – O custo mais recente que foi ativado em uma versão de custo
- **Preço de item** – O custo especificado para o produto lançado

Para determinar quais desses valores de custo devem ser usados nos cálculos da média de movimentos, o sistema usa uma _sequência de custos de fallback_ para estabelecer a ordem de preferência dos valores. Se o valor do custo preferido não estiver disponível, o sistema utilizará o próximo valor preferencial e assim por diante.

Nas versões anteriores do Microsoft Dynamics 365 Supply Chain Management, o sistema usava uma sequência de custos de fallback fixa (_Problema mais recente – Custo ativo – Preço de item_). Na versão 10.0.11, essa sequência ainda é a sequência padrão. Entretanto, você também poderá ativar um recurso que permite selecionar entre três sequências de custos de fallback disponíveis. Esse recurso pode ser especialmente útil para organizações que usam regularmente valores negativos de estoque.

Para disponibilizar o seletor para a sequência de custos de fallback, você (ou um administrador) deve usar [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para ativar o recurso chamado _Média móvel, sequência de custos de fallback_.

Para selecionar a sequência de custos de fallback para os cálculos de média de movimentos, siga as etapas a seguir.

1. Abra a página **Parâmetros**.
2. Na guia **Contabilidade de estoque**, na seção **Média de movimentos**, defina o campo **Sequência de custos de fallback** como um dos seguintes valores:

    - **Problema mais recente – Custo ativo – Preço de item** – Esta sequência é a sequência padrão. É a mesma sequência usada se o recurso _Média móvel, sequência de custos de fallback_ não estiver ativado.
    - **Custo ativo – Problema mais recente**
    - **Custo ativo – Preço de item** – As organizações podem enfrentar problemas de desempenho se usarem processos de negócios em que o estoque fica negativo regularmente e, ao mesmo tempo, o volume de transações é alto. Essa configuração pode ajudar a mitigar esses problemas de desempenho.

![Parâmetros de contabilidade de estoque](media/inventory-accounting-parameters.png "Parâmetros de contabilidade de estoque")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]