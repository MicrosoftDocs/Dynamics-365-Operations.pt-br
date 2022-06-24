---
title: Tipos de lançamento de arrendamento
description: Este artigo descreve os tipos de lançamento usados para transações de arrendamento de ativo.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 26917ed0017e43c2be5ee53e472ad57d12db0978
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8889052"
---
# <a name="lease-posting-types"></a>Tipos de lançamento de arrendamento

[!include [banner](../includes/banner.md)]

Este artigo descreve os tipos de lançamento usados para transações de arrendamento de ativo.

## <a name="lease-asset"></a>Ativo de arrendamento

A conta é associada ao ativo de direito de uso (DDU). Essa conta é debitada quando um arrendamento é reconhecido inicialmente sob os novos padrões de contabilidade de arrendamento, o Tópico 842 da Codificação de Padrões Contábeis (ASC 842) e o Padrão Internacional de Relatórios Financeiros 16 (IFRS 16). Para um arrendamento modificada, essa conta pode ser debitada ou creditada, dependendo se a modificação aumenta ou diminui a responsabilidade com arrendamento.

**Exemplo de entradas de diário:** reconhecimento inicial<br>
**Débito:** ativo de arrendamento XXX<br>
**Crédito:** responsabilidade com arrendamento XXX

## <a name="lease-liability"></a>Responsabilidade com arrendamento

A conta é associada à responsabilidade de arrendamento que ocorre quando os pagamentos são descontados sob os novos padrões IFRS 16 e ASC 842. Essa conta é creditada quando um arrendamento é reconhecido inicialmente sob os novos padrões. É debitado de pagamentos do arrendamento e creditado para acúmulos de juros.

**Exemplo de entradas de diário:** reconhecimento inicial<br>
**Débito:** ativo de arrendamento XXX<br>
**Crédito:** responsabilidade com arrendamento XXX

**Exemplo de entradas de diário:** acúmulo de juros<br>
**Débito:** despesa de juros XXX<br>
**Crédito:** responsabilidade com arrendamento XXX

**Exemplo de entradas de diário:** pagamento do arrendamento<br>
**Débito:** responsabilidade com arrendamento XXX<br>
**Crédito:** fornecedor a pagar/pagamento do arrendamento XXX

## <a name="short-term-lease-liability"></a>Responsabilidade com arrendamento de curto prazo

A conta é associada à responsabilidade com arrendamento de curto prazo quando a entrada de diário de reclassificação de responsabilidade com arrendamento de curto prazo é lançada. Essa conta é creditada no passivo de curto prazo da agenda de amortização no último dia do mês. No entanto, o mesmo valor é debitado no primeiro dia do mês seguinte.

**Exemplo de entradas de diário:** reclassificação de responsabilidade com arrendamento de curto prazo<br>
**Débito:** responsabilidade com arrendamento XXX<br>
**Crédito:** responsabilidade com arrendamento de curto prazo XXX<br>
**Débito:** responsabilidade com arrendamento de curto prazo XXX<br>
**Crédito:** responsabilidade com arrendamento XXX

## <a name="depreciation-expense"></a>Despesa de Depreciação

A conta é associada à despesa relacionada à depreciação do ativo DDU sob o IFRS 16, ASC 842 e os arrendamentos mercantis sob o IAS 17 e ASC 840. Essa conta é debitada quando um ativo DDU é depreciado a cada mês.

**Exemplo de entradas de diário:** acúmulo de depreciação<br>
**Débito:** despesa de depreciação XXX<br>
**Crédito:** depreciação acumulada XXX

## <a name="gainloss-on-lease-modification"></a>Ganho/perda na modificação de arrendamento

A conta é associada a quaisquer ganhos ou perdas que surjam das modificações de arrendamento. Um ganho pode surgir durante uma modificação de arrendamento se a modificação diminuir a responsabilidade com arrendamento por um valor que exceda o valor de carregamento do ativo DDU.

Por exemplo, um arrendamento tem um valor de carregamento atual da responsabilidade com arrendamento de US$ 150.000 e um valor de carregamento do ativo DDU de US$ 100.000. O arrendamento é modificado, e essa modificação gera um novo valor presente dos PVFMLP (pagamentos do arrendamento mínimos futuros) de US$ 40.000. Portanto, a responsabilidade com arrendamento será debitada por US$ 110.000 (US$ 150.000 – US$ 40.000). Como o ativo DDU é de apenas US$ 100.000, a redução de US$ 110.000 diminuirá o ativo após 0 (zero). Portanto, as diretrizes contábeis declaram que o restante deve ser registrado em uma conta de ganho. Nesse caso, a entrada de diário final será um débito para a responsabilidade com arrendamento para US$ 110.000, um crédito ao ativo de arrendamento para US$ 100.000 e um crédito na conta de ganho para US$ 10.000.

**Exemplo de entradas de diário:** modificação do arrendamento<br>
**Débito:** responsabilidade com arrendamento XXX<br>
**Crédito:** ativo de arrendamento XXX<br>
**Crédito:** ganho XXX

## <a name="accumulated-depreciation"></a>Depreciação Acumulada

A conta é associada à conta de contra-ativo do ativo DDU. Essa conta é creditada quando uma despesa de depreciação o é lançada.

**Exemplo de entradas de diário:** acúmulo de depreciação<br>
**Débito:** despesa de depreciação XXX<br>
**Crédito:** depreciação acumulada XXX

## <a name="variable-payment"></a>Pagamento variável

A conta está associada a pagamentos do arrendamento variáveis produzidos por uma reavaliação de índice sob os arrendamentos ASC 842, ASC 840 e IAS 17. Na agenda do pagamento do arrendamento, os pagamentos variáveis são incluídos na coluna **Pagamento variável**. Essa conta é debitada quando uma fatura é criada em uma linha da agenda de pagamento que contém um pagamento variável.

**Exemplo de entradas de diário:** pagamento do arrendamento<br>
**Débito:** responsabilidade com arrendamento XXX<br>
**Débito:** pagamento variável XXX<br>
**Crédito:** fornecedor a pagar/pagamento do arrendamento XXX

## <a name="deferred-rent-asset-liability"></a>Ativo de arrendamento diferido (passivo)

A conta está associada ao ativo ou passivo de arrendamento diferido produzido por um arrendamento de tratamento de arrendamento diferido. Essa conta é debitada quando uma fatura é lançada em relação a um arrendamento de tratamento de arrendamento diferido, se o valor do pagamento do arrendamento for maior do que a despesa de arrendamento linear do período. Será creditado se o pagamento do arrendamento for menor do que a despesa do arrendamento linear do período.

**Exemplo de entradas de diário:** pagamento do arrendamento (arrendamento de tratamento de arrendamento diferido)<br>
**Débito:** despesa de arrendamento XXX<br>
**Crédito:** passivo de arrendamento deferido XXX<br>
**Crédito:** fornecedor a pagar/pagamento do arrendamento XXX

## <a name="lease-expense"></a>Despesa de arrendamento

A conta será associada à despesa de arrendamento se o arrendamento for classificado como um arrendamento de tratamento de arrendamento diferido. Essa conta é debitada quando uma fatura é lançada em relação a um arrendamento de tratamento de arrendamento diferido.

**Exemplo de entradas de diário:** pagamento do arrendamento (arrendamento de tratamento de arrendamento diferido)<br>
**Débito:** despesa de arrendamento XXX<br>
**Crédito:** passivo de arrendamento deferido XXX<br>
**Crédito:** fornecedor a pagar/pagamento do arrendamento XXX

## <a name="impairment-expense"></a>Despesa de redução ao valor recuperável

A conta é lançada em relação ao momento em que um arrendamento tem redução ao valor recuperável. Essa conta é debitada, enquanto a conta de ativo DDU é creditada diretamente.

**Exemplo de entradas de diário:** pagamento do arrendamento<br>
**Débito:** despesa de redução ao valor recuperável XXX<br>
**Crédito:** ativo DDU XXX

## <a name="lease-payment"></a>Pagamento de arrendamento

A conta será lançada se o parâmetro **Pagar ao Fornecedor** estiver desativado. Essa conta será creditada no lugar do fornecedor a pagar se o parâmetro for desativado.

**Exemplo de entradas de diário:** pagamento do arrendamento<br>
**Débito:** responsabilidade com arrendamento XXX<br>
**Crédito:** pagamento do arrendamento XXX

## <a name="expense-type-postings"></a>Lançamentos de tipo de despesa

A conta selecionada para cada tipo de despesa é debitada quando um pagamento para aquele tipo de despesa é gerado. Por exemplo, a conta especificada para o tipo de despesa **Seguro** é debitada sempre que uma entrada de diário de fatura ou de pagamento é criada do plano de custo de execução para despesas de seguro.

**Exemplo de entradas de diário:** pagamento do seguro<br>
**Débito:** conta do tipo de despesa de seguro XXX<br>
**Crédito:** contrapartida XXX

> [!NOTE]
> A contrapartida é selecionada no nível do arrendamento nas linhas da agenda de pagamento de custo de execução. Essa contrapartida pode ser associada ao fornecedor ou a uma conta contábil.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
