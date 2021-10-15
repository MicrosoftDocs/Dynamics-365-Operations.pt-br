---
title: Princípios de redução de reembolso
description: Este tópico descreve como configurar princípios de redução. Os princípios de redução controlam o comportamento quando vários reembolsos se aplicam ao mesmo item ou transação.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateCategory
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: e6b178704fde18036d526e7a645cb9b4f8bd66c7
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579055"
---
# <a name="rebate-reduction-principles"></a>Princípios de redução de reembolso

[!include [banner](../includes/banner.md)]

Você pode agrupar Acordos de gerenciamento de reembolso em *princípios de redução* para reduzir outras provisões associadas a um item e/ou reduzir os valores resultantes de cálculos de reembolso. Após a configuração dos princípios de redução de reembolso, você poderá atribuí-los opcionalmente, conforme necessário, às linhas de Acordos de gerenciamento de reembolso.

As regras do princípio de redução de reembolso só se aplicam quando acordos de reembolso se sobrepõem. Portanto, elas podem conceder vários reembolsos em situações em que vários reembolsos não são devidos.

## <a name="manage-rebate-reduction-principles"></a>Gerenciar princípios de redução de reembolso

Para trabalhar com princípios de redução de reembolso, acesse **Gerenciamento de reembolso \> Configuração \> Princípios de redução de reembolso**. Use os botões no Painel de Ações para adicionar e remover princípios de redução, conforme necessário. Para cada princípio, defina os campos conforme descrito na tabela a seguir.

| Campo | Descrição |
|---|---|
| Princípio de redução de reembolso | Insira um nome exclusivo para o princípio de redução de reembolso. |
| Descrição | Insira uma descrição do princípio de redução de reembolso. |
| Aplicar redução | Marque esta caixa de seleção para aplicar uma base de redução aos reembolsos pertencentes a esse princípio de redução de reembolso. |
| Base de redução | Se você marcou a caixa de seleção **Aplicar redução**, selecione a base de redução (*Provisão*, *Reembolsos* ou *Ambos*). Se você selecionar *Ambos* e se uma provisão e um reembolso tiverem sido lançados para um acordo anterior, apenas o reembolso será aplicado. |
| Excluir da redução | Se esta caixa de seleção estiver marcada, as provisões e os reembolsos pertencentes a esse princípio de redução de reembolso serão excluídos das reduções subsequentes. A configuração do campo **Base de redução** não se aplica a essa configuração. |

## <a name="examples-of-rebate-reduction-principle-setups"></a>Exemplos de configurações de princípio de redução de reembolso

A tabela a seguir mostra alguns exemplos típicos de configurações de princípio de redução de reembolso. Para cada um desses princípios de redução de reembolso, o valor do campo **Descrição** descreve a finalidade do princípio de redução de reembolso.

| Princípio de redução de reembolso | descrição | Aplicar redução | Base de redução | Excluir da redução |
|---|---|---|---|---|
| Diferido | Reduzir reembolso | Sim | Ambos | Não |
| Exclreb | Excluir reembolso | Sim | Reembolso | Sim |
| Múltiplas | Vários reembolsos | Sim | Ambos(as) | Sim |
| Nenhum | Somente Prov e Reembolso | Não | Ambos(as) | Sim |
| Provisionar | Somente Provisionar | Sim | Provisionar | Não |
| Reembolso | Somente reembolso | Sim | Reembolso | Sim |

## <a name="examples-of-rebate-reduction-principle-calculations"></a>Exemplos de cálculos de princípio de redução de reembolso

Você tem uma ordem de venda com uma única linha de ordem de venda. Esta linha tem um valor de USD 1.000. Os seguintes acordos se aplicam à ordem:

- **Acordo 1:** 10% em USD 1.000
- **Acordo 2:** 15% em USD 1.000
- **Acordo 3:** 20% em USD 1.000
- **Acordo 4:** 25% em USD 1.000

A ordem de processamento é muito importante. A ordem de processamento se baseia na maneira como você trabalha, conforme descrito em [Processar, analisar e lançar reembolsos](process-review-post.md).

Por exemplo, a tabela a seguir resumirá o resultado se você usar a ordem *1, 2, 3, 4* e se processar apenas as provisões.

| Acordo | Descrição e configurações | Resultado da provisão |
|---|---|---|
| 1 | <p>A classificação não verifica outros acordos de reduções. A verificação é feita para provisões e reembolsos.</p><ul><li>**Aplicar redução**: *Não*</li><li>**Base de redução**: *Ambos*</li><li>**Excluir da redução**: *Não*</li></ul> | USD 1.000 × 10% = USD 100 |
| 2 | <p>A classificação verifica outros acordos de reduções, mas é sinalizada para que seja ignorada. A verificação é feita apenas para reembolsos.</p><ul><li>**Aplicar redução**: *Sim*</li><li>**Base de redução**: *Reembolso*</li><li>**Excluir da redução**: *Sim*</li></ul> | USD 1.000 × 15% = USD 150 |
| 3 | <p>A classificação verifica outros acordos de reduções. A verificação é feita para provisões e reembolsos.</p><ul><li>**Aplicar redução**: *Sim*</li><li>**Base de redução**: *Ambos*</li><li>**Excluir da redução**: *Não*</li></ul> | (USD 1.000 – Acordo 1) × 20% = USD 180 |
| 4 | <p>A classificação verifica outros acordos de reduções. A verificação é feita para provisões e reembolsos.</p><ul><li>**Aplicar redução**: *Sim*</li><li>**Base de redução**: *Ambos*</li><li>**Excluir da redução**: *Não*</li></ul> | (USD 1.000 - Acordo 1 - Acordo 3) × 25% = USD 180 |

A tabela a seguir mostra alguns exemplos em que a provisão é processada em ordens diferentes e em que são obtidos totais diferentes. A variação nas provisões depende da ordem em que o sistema processa os acordos. É importante compreender como a ordem de processamento afeta o valor final do reembolso.

| Sequência | Cálculo |
|---|---|
| 1<br>(1, 2, 3, 4) | <ul><li>**Acordo 1:** USD 1.000 × 10% = USD 100</li><li>**Acordo 2:** USD 1.000 × 15% = USD 150</li><li>**Acordo 3:** (USD 1.000 – Acordo 1) × 20% = USD 180</li><li>**Acordo 4:** (USD 1.000 – Acordo 1 – Acordo 2) × 25% = USD 180</li><li>**Provisão total:** USD 610</li></ul> |
| 2<br>(4, 3, 2, 1) | <ul><li>**Acordo 4:** USD 1.000 x 25% = USD 250</li><li>**Acordo 3:** (USD 1.000 – Acordo 4) × 20% = USD 150</li><li>**Acordo 2:** USD 1.000 x 15% = USD 150</li><li>**Acordo 1:** USD 1.000 x 10% = USD 100</li><li>**Provisão total:** USD 650</li></ul> |
| 3<br>(3, 2, 1, 4) | <ul><li>**Acordo 3:** USD 1.000 x 20% = USD 200</li><li>**Acordo 2:** USD 1.000 x 15% = USD 150</li><li>**Acordo 1:** USD 1.000 x 10% = USD 100</li><li>**Acordo 4:** (USD 1.000 – Acordo 3 – Acordo 1) × 25% = USD 175</li><li>**Provisão total:** USD 625</li></ul> |
| 4<br>(2, 4, 1, 3) | <ul><li>**Acordo 2:** USD 1.000 × 15% = USD 150</li><li>**Acordo 4:** USD 1.000 × 25% = USD 250</li><li>**Acordo 1:** USD 1.000 × 10% = USD 100</li><li>**Acordo 3:** (USD 1.000 – Acordo 4 – Acordo 1) × 20% = USD 130</li><li>**Provisão total:** USD 630</li></ul> |
