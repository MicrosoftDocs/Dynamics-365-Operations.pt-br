---
title: Contas para transações automáticas
description: Este tópico explica como as contas para transações automáticas são usadas para lançamento pelo Microsoft Dynamics 365 e fornece exemplos de contas principais para transações automáticas.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerSystemAccounts
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 275c74d673d1ba2468e23c5fa443c9272d13a184
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735250"
---
# <a name="accounts-for-automatic-transactions"></a>Contas para transações automáticas

A página **Contas para transações automáticas** (**Contabilidade &gt; Configuração de lançamento &gt; Contas para transações automáticas**) é usada para definir a conta principal padrão usada para cada tipo de lançamento no sistema. Embora a maioria dos tipos de lançamento possa ser configurada em uma página específica de módulo ou recurso, alguns tipos de lançamento só podem ser configurados na página **Contas para transações automáticas**.

Por exemplo, você pode especificar a conta principal usada para o tipo de lançamento **Saldo do cliente** no campo **Resumo** da página **Perfil de lançamento do cliente** e usar uma conta principal diferente para cada perfil de cliente. Dessa forma, você tem um controle mais granular sobre os lançamentos. Por outro lado, você só poderá especificar a conta de erro na página **Contas para transações automáticas**.

Quando você abre a página **Contas para transações automáticas** em uma nova entidade legal, a lista de contas estará vazia. Você pode adicionar os tipos de lançamento mais comuns que devem ser configurados na página, selecionando o botão **Criar tipos padrão**. Então, para cada linha, você pode selecionar a conta principal no campo **Conta principal**. Se deixar o campo **Conta principal** em branco para um tipo de lançamento e não tiver configurado uma conta principal em uma página específica do módulo ou recurso, você receberá uma mensagem de erro ao lançar uma transação que usa o tipo de lançamento. Normalmente, a mensagem será "Não foi possível encontrar a conta para o \[Tipo de lançamento\]".

## <a name="default-posting-types"></a>Tipos de lançamento padrão

A tabela a seguir mostra exemplos dos tipos de lançamento padrão criados quando você seleciona **Criar tipos padrão** na página **Contas para transações automáticas**. Ele mostra descrições e contas principais de exemplo. A coluna "Débito/Crédito?" indica se a transação normalmente lança um débito ou um crédito. Em alguns casos, uma transação pode lançar um débito ou um crédito. A coluna "Conta de compensação" indica se o tipo de lançamento é uma conta de compensação. Se o tipo de lançamento for uma conta de compensação, o valor lançado na conta será automaticamente revertido quando uma transação posterior for lançada.

| Tipo de lançamento | Exemplo de conta principal | Exemplo de nome de conta principal | Tipo de conta | Débito/Crédito? | Conta de compensação | Descrição |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Diferença mínima na moeda de relatório | 618160 | Despesas Diversas | Despesa | Ambos | Não | Esse tipo de lançamento é usado quando uma diferença mínima ocorre quando um valor de transação em uma moeda estrangeira é traduzido para a moeda organizacional. |
| Diferença mínima na moeda contábil | 618160 | Despesas Diversas | Despesa | Ambos | Não | Esse tipo de lançamento é usado quando uma diferença mínima ocorre quando um valor de transação em uma moeda estrangeira é traduzido para a moeda contábil. |
| Conta de erros | 999999 | Conta de Erros | Despesa | Ambos | Não | Esse tipo de lançamento é usado quando ocorre um erro no sistema. A conta deve ser validada a cada período, e todos os erros devem ser resolvidos. |
| Resultado de fim de ano | 300160 | Lucros Retidos | Capital próprio | Ambos | Não | Esse tipo de lançamento é usado quando o processo de fechamento de fim de ano é executado para mover o saldo de contas do tipo **Lucro e perda** para a conta principal selecionada para o resultado de fim de ano. |
| Desconto à vista do cliente | Não aplicável | Não aplicável | Não aplicável | Não aplicável | Não | O tipo de lançamento definido na página **Contas para transações automáticas** não é usado. Uma conta principal é necessária quando descontos à vista são configurados em Contas a receber.|
| Desconto à vista do fornecedor | Não aplicável | Não aplicável | Não aplicável | Não aplicável | Não | O tipo de lançamento definido na página **Contas para transações automáticas** não é usado. Uma conta principal é necessária quando descontos à vista são configurados em Contas a pagar. |

## <a name="additional-posting-types"></a>Tipos de lançamento adicionais

A tabela a seguir mostra exemplos de tipos de lançamento adicionais que deverão ser configurados se você planejar usar os recursos relacionados. Para esses tipos de lançamento, nenhuma configuração de perfil de lançamento está disponível em outro módulo. A coluna "Débito/Crédito?" indica se a transação normalmente lança um débito ou um crédito. Em alguns casos, uma transação pode lançar um débito ou um crédito. A coluna "Conta de compensação" indica se o tipo de lançamento é uma conta de compensação. Se o tipo de lançamento for uma conta de compensação, o valor lançado na conta será automaticamente revertido quando uma transação posterior for lançada.

| Tipo de lançamento | Exemplo de conta principal | Exemplo de nome de conta principal | Tipo de conta | Débito/Crédito? | Conta de compensação | Descrição |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Conta de saldo para diferença de consolidação | 801200 | Ganho e Perda – Reavaliação | Despesa | Ambos | Não | Esse tipo de lançamento é usado quando você executa uma consolidação que envolve uma reavaliação de moeda e as diferenças mínimas ocorrem durante a reavaliação. |
| Conta de lucros e perdas para diferenças de consolidação | 801200 | Ganho e Perda – Reavaliação | Despesa | Ambos | Não | Esse tipo de lançamento é usado quando você executa uma consolidação que envolve uma reavaliação de moeda e as diferenças mínimas ocorrem durante a reavaliação. |
| Interunidade – débito | 133500 | Interunidade a Receber | Ativo | Débito | Não | Esse tipo de lançamento é usado quando você seleciona uma dimensão de balanceamento na página **Razão** e a dimensão não é balanceada em uma transação lançada. |
| Interunidade - crédito | 233500 | Interunidade a Pagar | Passivo | Crédito | Não | Esse tipo de lançamento é usado quando você seleciona uma dimensão de balanceamento na página **Razão** e a dimensão não é balanceada em uma transação lançada. |
