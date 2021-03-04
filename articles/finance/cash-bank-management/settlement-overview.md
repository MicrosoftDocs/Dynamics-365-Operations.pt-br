---
title: Visão geral de liquidação
description: Este tópico oferece informações gerais sobre o processo de liquidação. Descreve quais tipos de transação podem ser liquidados e o tempo e o processo para a liquidação. Também descreve os resultados do processo de liquidação.
author: kweekley
manager: AnnBe
ms.date: 04/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14551
ms.assetid: 0968fa71-5984-415b-8689-759a0136d5d1
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 650b0ef0123cf9acf42c2e7460693b555897744f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440338"
---
# <a name="settlement-overview"></a>Visão geral de liquidação

[!include [banner](../includes/banner.md)]

Este tópico oferece informações gerais sobre o processo de liquidação. Descreve quais tipos de transação podem ser liquidados e o tempo e o processo para a liquidação. Também descreve os resultados do processo de liquidação.

Durante a liquidação, as transações de um documento são aplicadas a transações em outro documento para aumentar ou diminuir o saldo de cada documento. Por exemplo, um pagamento pode ser aplicado a uma fatura. Vários tipos de transações podem ser resolvidos, em momentos diferentes e através de métodos diferentes. O processo de liquidação também pode gerar novas transações.

## <a name="what-transactions-can-be-settled"></a>Quais transações podem ser liquidadas

Em Contas a pagar e Contas a receber, pode ocorrer entre quaisquer tipo de transação que afetarem o saldo do fornecedor ou o saldo do cliente. Esses tipos de transação podem incluir notas fiscais, pagamentos, memorandos de crédito e taxas. Qualquer tipo de transação pode ser liquidado com relação a qualquer outro tipo de transação. Por exemplo, você pode liquidar um pagamento de uma fatura, um memorando de crédito para uma fatura, uma fatura para outra fatura e um pagamento para outro pagamento.

Você pode liquidar pagamentos para uma transação na mesma entidade legal ou em uma entidade legal diferente. Em organizações que usam um módulo de pagamento centralizado, as [pagamentos centralizados](set-up-centralized-payments.md) podem ajudar a simplificar o processo de pagamento.

## <a name="when-to-settle-transactions"></a>Quando liquidar transações

As transações podem ser liquidadas quando os pagamentos são inseridos. Por exemplo, quando você faz um pagamento para um fornecedor, normalmente você seleciona quais faturas a serem pagas. Ao selecionar faturas, você as marca para liquidação contra o pagamento. Quando os auxiliares de pagamento do Contas a Receber registram um pagamento de cliente, eles podem marcar as faturas apropriadas para liquidação, com base nas informações incluídas em cada pagamento do cliente. Você usa a página **Transações de liquidação** para marcar transações para liquidação. Você pode abrir essa página a partir de qualquer fatura ou pagamento não lançado. Quando a transação é lançada, a liquidação também é lançada. 

As transações também podem ser liquidadas depois de serem lançadas. Você pode inserir e lançar um pagamento de cliente sem liquidá-lo em todas as faturas. No entanto, você pode querer garantir que o pagamento é liquidado na fatura correta antes de postar a liquidação. A página **Liquidar transações** pode ser aberta na página **Todos os clientes** ou **Todos os fornecedores** ou na página **Transações** de qualquer cliente ou fornecedor.

Você também pode reservar pagamentos antecipados lançados para uma fatura marcando o pagamento de uma liquidação contra uma ordem de compra ou de venda. Neste caso, o pagamento ainda terá um saldo em aberto, mas não pode ser liquidado contra outra fatura. O pagamento será automaticamente compensado com a fatura criada a partir da ordem de compra ou da ordem do cliente.

## <a name="how-to-settle-transactions"></a>Como liquidar transações

As transações podem ser liquidadas manualmente, automaticamente, ou usando uma combinação dos métodos. A escolha de um método de liquidação depende dos processos comerciais. Nas páginas **Parâmetros de contas a pagar** e **Parâmetros de contas a receber**, você pode configurar o processo de liquidação para que fique alinhado com esses processos comerciais.

Você pode criar pagamentos de fornecedor e pagamentos de débito direto do cliente usando uma proposta de pagamento. Uma proposta de pagamento é usada para selecionar notas fiscais a serem pagas. A proposta de pagamento é iniciada manualmente e o sistema marca automaticamente as faturas selecionadas para liquidação quando os pagamentos são criados.

Se os pagamentos forem criados manualmente, você pode usar a página **Transações de liquidação** para selecionar faturas para liquidação. Também é possível selecionar manualmente as faturas ou você pode usar a opção **Marcar por prioridade** para que as faturas sejam marcadas automaticamente para liquidação. A opção **Marcar por prioridade** fica disponível somente para Contas a receber. Você pode ativar esta opção na guia **Prioridade de liquidação** da página **Parâmetros de contas a receber**.

Se um auxiliar de pagamento inserir um pagamento, mas não liquidar esse pagamento antes dele ser postado, o pagamento poderá ser liquidado automaticamente. Você pode ativar a liquidação automática nas páginas **Parâmetros de contas a receber** e **Parâmetros de contas a pagar**. A liquidação automática liquida as transações somente na mesma entidade legal. Ela não liquida transações entre várias entidades legais.

Quando você utiliza a liquidação automática, pode utilizar a prioridade de liquidação predefinida ou pode definir a sua própria ordem de prioridade de liquidação na página **Parâmetros de contas a receber**. Essa funcionalidade só estará disponível para Contas a receber.

## <a name="results-of-settlement"></a>Os resultados da liquidação

Quando as transações são liquidadas, o saldo pendente de cada transação é aumentado ou diminuído, conforme apropriado. Geralmente, quando uma fatura e um pagamento são liquidados, o status e um saldo de cada transação será atualizado de acordo com as regras a seguir:

- Se o valor do pagamento for maior do que o valor da fatura, o saldo da fatura será reduzido a 0,00 e a fatura será fechada. O pagamento permanece aberto e o saldo é a diferença entre o valor do pagamento e o valor da fatura.
- Se o valor do pagamento for menor do que o valor da fatura, o saldo do pagamento será reduzido a 0,00 e o pagamento será fechado. A fatura permanece aberto e o saldo é a diferença entre o valor da fatura e o valor do pagamento.
- Se o valor do pagamento for igual ao valor da fatura, o pagamento e a fatura serão fechados e o saldo dos dois será reduzido para 0,00.

Se o [valor do pagamento for inferior ao valor da fatura](../accounts-payable/vendor-payments-partial-amount.md) devido a um desconto à vista, baixa ou pagamento a menor, a fatura e o pagamento podem ainda ser fechados, dependendo de como as liquidações são configuradas nas páginas **Parâmetros de contas a pagar** e **Parâmetros de contas a receber**.

As liquidações também pode gerar transações. Por exemplo, a liquidação de uma fatura e de um pagamento pode gerar um desconto à vista, um ganho ou perda realizado, ajustes de impostos, baixas contábeis ou diferenças mínimas.

## <a name="identifying-marked-transactions-during-settlement"></a>Identificando transações marcadas durante liquidação

Ao tentar liquidar uma transação, você pode observar um símbolo que indica que a transação está marcada em outro local. Nesse caso, você pode selecionar a transação na página **Liquidar transações** e selecionar **Consultar \> Liquidação de consulta na janela de liquidação**. A exibição dessa consulta mostra diários, ordens de venda, notas fiscais, propostas de pagamento e localizações de clientes que podem estar impedindo a transação da liquidação. Para resolver o problema, você pode selecionar o link para ir diretamente da consulta para o local bloqueado. Em seguida, você pode atualizar o documento com os ajustes necessários para liquidá-lo. Você também pode usar o indicador **Marcado** para identificar outros documentos incluídos no mesmo local de bloqueio.

## <a name="additional-resources"></a>Recursos adicionais

- [Liquidar pendências](settle-remainder.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]