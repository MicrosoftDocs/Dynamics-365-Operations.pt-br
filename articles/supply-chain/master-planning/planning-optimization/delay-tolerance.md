---
title: Tolerância de atraso (dias negativos)
description: Este artigo fornece informações sobre o cálculo de tolerância de atraso e como ele afeta a criação de ordens planejadas na Otimização de Planejamento.
author: t-benebo
ms.date: 08/09/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 78ba4236705f1a200d9fe796eb80d0241b0fa537
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740459"
---
# <a name="delay-tolerance-negative-days"></a>Tolerância de atraso (dias negativos)
<!-- KFM: Split topic into PO and classic -->

[!include [banner](../../includes/banner.md)]

A funcionalidade de tolerância ao atraso permite que a "Otimização de planejamento" considere o valor **Dias negativos** definido para grupos de cobertura, cobertura de itens e/ou planos mestre. Ela é usada para estender o período de tolerância de atraso que é aplicado durante o planejamento mestre. Desta forma, você pode evitar a criação de novas ordens de suprimento se a oferta existente for capaz de cobrir a demanda após um curto atraso. O objetivo da funcionalidade é determinar se faz sentido criar uma nova ordem de suprimento para uma determinada demanda.

## <a name="turn-delay-tolerance-features-on-or-off"></a>Ativar ou desativar recursos de tolerância de atraso

Para disponibilizar a funcionalidade de tolerância de atraso no sistema, acesse [Gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative os recursos seguintes:

- *Dias negativos para a otimização do planejamento* – este recurso permite configurações de dias negativos para grupos de cobertura e cobertura de item. A partir do Supply Chain Management versão 10.0.29, o recurso é obrigatório e não pode ser desativado.
- *Automação de fornecimento disponível sob encomenda* – este recurso permite configurações de dias negativos para planos mestre. (Para obter mais informações, consulte [Automação de fornecimento disponível sob encomenda](../make-to-order-supply-automation.md).)

## <a name="delay-tolerance-in-planning-optimization"></a>Tolerância de atraso na Otimização de Planejamento

A tolerância de atraso representa o número de dias fora do prazo que você está disposto a esperar antes de encomendar um novo reabastecimento quando a oferta existente já está planejada. A tolerância de atraso é definida usando dias corridos, e não dias úteis.

No momento do planejamento mestre, quando o sistema calcula a tolerância de atraso, ele considera a configuração **Dias negativos**. Você pode definir um valor para a opção **Dias negativos** nas páginas **Grupos de cobertura**, **Cobertura de item** ou **Planos mestre**. Se os dias negativos forem atribuídos em mais de um nível, o sistema aplicará a hierarquia a seguir para decidir qual configuração usar:

- Se os dias negativos estiverem habilitados na página **Planos mestre**, essa configuração substituirá todas as outras configurações de dias negativos quando o plano for executado.
- Se os dias negativos forem configurados na página **Cobertura de item**, essa configuração substituirá a configuração do grupo de cobertura.
- Os dias negativos configurados na página **Grupos de cobertura** se aplicam somente se os dias negativos não foram configurados para um item ou um plano relevante.

O sistema vincula o cálculo de tolerância de atraso à *data de reabastecimento mais antiga*, que equivale à data de hoje mais o tempo de início. A tolerância de atraso é calculada usando a seguinte fórmula, na qual *max()* considera o maior de dois valores:

*max (Data de reabastecimento mais antiga, data de conclusão da demanda)* – *Data de conclusão da demanda* + *Dias negativos*

Esta fórmula garante que o planejamento mestre não crie novas ordens de suprimento quando existir suprimento suficiente durante o prazo do produto.

> [!NOTE]
> O cálculo de tolerância de atraso na Otimização de Planejamento sempre utiliza o cálculo dinâmico de dias negativos do mecanismo de planejamento mestre preterido. A configuração **Usar dias negativos dinâmicos** na página **Parâmetros de planejamento Mestre não tem efeito** sobre esse comportamento.

Se a oferta existente implicar um atraso de demanda menor ou igual à tolerância de atraso calculada, a Otimização de Planejamento associará a oferta existente com a demanda. Em alguns casos, é melhor atrasar a demanda do que acabar com o excesso de oferta.

As seguintes subseções fornecem exemplos que mostram como a tolerância de atraso afeta a criação de ordens planejadas na Otimização de Planejamento.

### <a name="example-1"></a>Exemplo 1

Um produto tem a seguinte configuração:

- **Prazo:** *10*
- **Dias negativos:** *2*

Existem a seguinte oferta e demanda para o produto:

- **Demanda para hoje:** Uma ordem de vendas para uma quantidade de 10
- **Suprimento em 12 dias:** Uma ordem de compra para uma quantidade de 10

A oferta existente pode cobrir a demanda dentro de 12 dias, e esse período é igual à tolerância de atraso. Portanto, quando o planejamento mestre é executado, nenhuma ordem planejada é criada.

### <a name="example-2"></a>Exemplo 2

Um produto tem a seguinte configuração:

- **Prazo:** *10*
- **Dias negativos:** *0*

Existem a seguinte oferta e demanda para o produto:

- **Demanda para hoje:** Uma ordem de vendas para uma quantidade de 10
- **Suprimento em 12 dias:** Uma ordem de compra para uma quantidade de 10

A oferta existente só pode cobrir a demanda após 12 dias. No entanto, a tolerância de atraso é de 10 dias. Portanto, quando o planejamento mestre é executado, uma ordem planejada para uma quantidade de 10 é criada.

### <a name="example-3"></a>Exemplo 3

Um produto tem a seguinte configuração:

- **Prazo:** *10*
- **Dias negativos:** *2*

Existem a seguinte oferta e demanda para o produto:

- **Demanda em 11 dias:** Uma ordem de venda para uma quantidade de 10
- **Suprimento em 14 dias:** Uma ordem de compra para uma quantidade de 10

A oferta existente só pode cobrir a demanda após três dias. No entanto, a tolerância de atraso é de dois dias. (Neste caso, a tolerância de atraso inclui apenas os dois dias negativos. A data da demanda não está incluída porque ela é posterior ao prazo do produto.) Portanto, quando o planejamento mestre é executado, uma ordem planejada para uma quantidade de 10 é criada.
