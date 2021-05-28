---
title: Conjuntos de dimensões financeiras
description: Este tópico descreve os conjuntos de dimensões financeiras e fornece algumas dicas para otimizar o uso.
author: yukonpeegs
ms.date: 03/23/2021
ms.topic: article
ems.prod: ''
ms.technology: ''
ms.search.form: DimensionFocus, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 25871
ms.search.region: Global
ms.author: epegors
ms.search.validFrom: 2021-03-23
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: ba11be028ebeea140df93e2a07dbb463402e3ef0
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021819"
---
# <a name="financial-dimension-sets"></a>Conjuntos de dimensões financeiras

[!include [banner](../includes/banner.md)]

Este tópico descreve os conjuntos de dimensões financeiras e fornece algumas dicas para otimizar o uso.

Um conjunto de dimensões é uma lista ordenada de dimensões financeiras que podem ser usadas para resumir os dados da contabilidade de forma definida pelo usuário. Um uso principal de conjuntos de dimensões é definir um balancete.

O único conjunto de dimensões padrão é o conjunto de dimensões que contém somente a conta principal.

Use a página **Conjuntos de dimensões financeiras** para criar e gerenciar conjuntos de dimensões financeiras.

## <a name="dimension-set-balances"></a>Saldos do conjunto de dimensões

Um conjunto de dimensões pode ter saldos baseados em dimensões financeiras. Os saldos existem na contabilidade e se baseiam na definição do conjunto de dimensões. Os saldos são resumidos a partir dos dados da contabilidade para ajudar a melhorar o desempenho quando são recuperados (por exemplo, quando um balancete é gerado).

## <a name="create-balances"></a>Criar saldos

Use o botão **Criar saldos** para inicializar os saldos para um conjunto de dimensões sem saldos no momento.

> [!NOTE]
> É recomendável limitar o número de conjuntos de dimensões que têm saldos, pois as atualizações de saldo afetam todas as atividades lançamento de contabilidade.

## <a name="update-balances"></a>Atualizar saldos

Use o botão **Atualizar saldos** para incluir a atividade de lançamento de contabilidade mais recente nos saldos. As atualizações de saldo são operações leves. Elas devem processar somente a atividade de lançamento de contabilidade que ocorreu desde a última atualização.

> [!NOTE]
> A exibição do balancete força uma atualização a garantir que os saldos mostrados sejam atuais. Considere o uso de um trabalho em lotes recorrente para que as atualizações dos conjuntos de dimensões usados com mais frequência sejam rápidas. Dessa forma, você ajuda a minimizar o tempo de espera de usuários do balancete.

## <a name="rebuild-balances"></a>Reconstruir saldos

Use o botão **Recriar saldos** para recriar os saldos desde o início. Dessa forma, você ajuda a garantir que eles correspondam aos dados na contabilidade. Uma recriação de saldos exige muito processamento e geralmente não deve ser necessária.

> [!NOTE]
> Se você tiver um cenário que exija regularmente uma recriação de saldos, será recomendável falar com o suporte ao cliente. O suporte ao cliente pode ajudá-lo a determinar por que os saldos não correspondem aos dados na contabilidade.

## <a name="clear-balances"></a>Limpar saldos

Use o botão **Limpar saldos** para remover os saldos e interromper atualizações adicionais. O conjunto de dimensões não terá mais impacto nas atividades de lançamento da contabilidade.

Para obter mais informações, consulte [Dimensões financeiras](financial-dimensions.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
