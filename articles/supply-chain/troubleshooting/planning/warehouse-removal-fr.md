---
title: Não é possível remover a dimensão de previsão de demanda do depósito das linhas de previsão
description: Não é possível remover a dimensão de previsão de demanda do depósito das linhas de previsão.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6b643c4fe51ae6ce73b34ab81d4e458dcd5032df
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026272"
---
# <a name="you-cant-remove-the-warehouse-demand-forecast-dimension-from-forecast-lines"></a>Não é possível remover a dimensão de previsão de demanda do depósito das linhas de previsão

Número de KB: 4614408

## <a name="symptoms"></a>Sintomas

Esse problema ocorre quando a dimensão **Depósito** não é atribuída na guia **Dimensões de previsão** da página **Previsão de demanda**. No entanto, a coluna **Depósito** é exibida na pagina **Previsão de demanda** (**Planejamento mestre \> Previsão \> Entidade de previsão manual \> Linhas de previsão de demanda**).

## <a name="resolution"></a>Resolução

As configurações na guia **Dimensões de previsão** da página **Parâmetro de previsão de demanda** não afetam a página **Previsão de demanda**. Elas controlam a previsão básica que é gerada e mostrada na previsão de demanda ajustada. No entanto, elas não controlam as dimensões necessárias para a previsão de demanda "real". Ao autorizar os registros mostrados na página **Previsão de demanda ajustada**, você pode convertê-los em entradas de previsão "reais" para um modelo de previsão. Assim, esse modelo poderá ser usado para o planejamento mestre.

Na página **Previsão de demanda**, as dimensões da previsão "real" mostradas nas linhas de previsão de demanda fazem parte das dimensões de estoque. (Esse comportamento é semelhante ao comportamento de linhas da ordem de venda.) Se o sistema não estiver configurado para usar o **Depósito** como uma dimensão de estoque obrigatória, você poderá personalizar a página para ocultar a coluna.
