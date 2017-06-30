---
title: Faturas de pagamento antecipado versus pagamentos antecipados
description: "Este artigo descreve e compara os dois métodos que as organizações podem usar para pagamentos antecipados. Em um método, você cria uma fatura de pagamento antecipado que esteja associada a uma ordem de compra. No outro método, é possível criar comprovantes de diário de pagamentos antecipados criando entradas de diário e marcando-as como comprovantes de diário de pagamentos antecipados."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, PurchTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 15871
ms.assetid: a0bb5220-73d4-48ae-84d0-46a171c224fa
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: c4f127007cea1d8ccd0b4e9ea637f0674775278d
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="prepayment-invoices-vs-prepayments"></a>Faturas de pagamento antecipado versus pagamentos antecipados

[!include[banner](../includes/banner.md)]


Este artigo descreve e compara os dois métodos que as organizações podem usar para pagamentos antecipados. Em um método, você cria uma fatura de pagamento antecipado que esteja associada a uma ordem de compra. No outro método, é possível criar comprovantes de diário de pagamentos antecipados criando entradas de diário e marcando-as como comprovantes de diário de pagamentos antecipados.

As organizações podem emitir pagamentos antecipados a fornecedores para mercadorias ou serviços, antes que as mercadorias ou serviços sejam entregues. Dois métodos podem ser usados para emitir pagamentos antecipados aos fornecedores. Para minimizar o risco, é possível rastrear pagamentos antecipados definindo o pagamento antecipado em uma ordem de compra. Para esse método, você deve criar uma fatura de pagamento antecipado que esteja associada a uma ordem de compra. Este método é conhecido como faturação de pagamento antecipado. As organizações que não desejam controlar os pagamentos antecipados de forma tão próxima ou que não recebem uma fatura de pagamento antecipado do fornecedor podem usar comprovantes de diário de pagamentos antecipados em vez do método de faturamento de pagamento antecipado. É possível criar comprovantes de diário de pagamentos antecipados criando entradas de diário e marcando-as como comprovantes de diário de pagamentos antecipados. Nesse método, você não pode controlar quais pagamentos antecipados para um fornecedor são feitos em quais ordens de compra. No entanto, você pode marcar um pagamento antecipado para liquidação em relação a uma ordem de compra.

## <a name="when-to-use-prepayment-invoicing-vs-prepayments"></a>Quando usar o faturamento de pagamento antecipado versus pagamentos antecipados
| Faturamento de pagamento antecipado                                                                | Pagamentos Antecipados                                                              |
|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------|
| Defina um valor de pagamento antecipado na ordem de compra.                                    | Nenhum valor de pagamento antecipado é definido na ordem de compra.                    |
| Chave: uma fatura de pagamento antecipado e uma fatura final devem ser lançadas.                       | Nenhuma fatura de pagamento antecipado deve ser lançada.                                    |
| A responsabilidade do pagamento antecipado é mantida na conta de pagamento antecipado e não na conta AP. | A responsabilidade do pagamento antecipado é mantida na conta AP.                  |
| O saldo de fornecedor não reflete o valor do pagamento antecipado durante o processo.     | O saldo de fornecedor reflete o valor do pagamento antecipado durante o processo. |
| A faturação de pagamento antecipado está disponível apenas em Contas a pagar.                         | Os pagamentos antecipados estão disponíveis em Contas a pagar e em Contas a receber.    |

## <a name="overview-of-the-prepayment-process"></a>Visão geral do processo de pagamento antecipado
As práticas contábeis em muitos países/regiões exigem que os pagamentos antecipados de um cliente ou a um vendedor não sejam lançados nas contas resumo usuais para o cliente ou fornecedor. Em vez disso, esses pagamentos antecipados são lançados em contas contábeis especiais. Quando uma ordem de compra ou de venda é criada, uma fatura é emitida ao cliente ou do fornecedor. Quando a fatura é paga, o comprovante de pagamento antecipado e de pagamento antecipado de imposto nas contas contábeis de pagamento antecipado são revertidos, e os valores da fatura são lançados automaticamente nas contas resumo usuais. Siga estas etapas para criar um pagamento antecipado.

1.  Configure perfis de lançamento para pagamentos antecipados.
2.  Nos parâmetros de Contas a receber e nos parâmetros de Contas a pagar, sob **Razão e imposto**, selecione o novo perfil de lançamento usando o parâmetro **Perfil de lançamentos para o diário de pagamentos com pagamento antecipado**.
3.  Crie um diário de pagamentos e crie o novo pagamento.
4.  Você pode sinalizar o pagamento como um pagamento antecipado. Se um pagamento for sinalizado como um pagamento antecipado, o pagamento será lançado nas contas contábeis definidas no perfil de lançamento configurado nas etapas 1 e 2. Além disso, se o pagamento for sinalizado como um pagamento antecipado, os impostos serão calculados. Alguns governos exigem que os impostos sejam pagos quando um pagamento antecipado é registrado, mesmo se não houver uma fatura.
5.  Lance o pagamento antecipado.
6.  Opcional: Você pode liquidar o pagamento antecipado na ordem de compra ou ordem de venda antes de criar a fatura. Na página da ordem de venda ou ordem de compra, no painel de ações, use **Transações de acordo**.
7.  Depois que o fornecedor entregar as mercadorias ou os serviços, registre a fatura. Se você tiver liquidado o pagamento antecipado em relação à ordem de compra ou à ordem de venda na etapa 6, o pagamento antecipado será automaticamente liquidado em relação à fatura que você criou. Se você não tiver liquidado o pagamento antecipado em relação à ordem de compra ou à ordem de venda, poderá liquidá-lo manualmente na fatura usando **Liquidar transações** na página do cliente ou do fornecedor. O valor do pagamento antecipado é revertido temporariamente fora da conta contábil AP/AR. Além disso, se os impostos forem calculados, eles são revertidos, pois a fatura tem os impostos reais.

## <a name="overview-of-the-prepayment-invoicing-process"></a>Visão geral do processo de faturamento de pagamento antecipado
As faturas de pagamento antecipado são uma prática empresarial comum. Um fornecedor emite faturas de pagamento antecipado para exigir um depósito na compra antes do atendimento da ordem de compra. Por exemplo, alguns fornecedores exigem um pagamento antecipado por mercadorias ou serviços específicos. Se um fornecedor emitir uma fatura que solicite pagamento antecipado, você poderá usar o recurso de faturamento de pagamento antecipado. Um valor do pagamento antecipado pode ser definido na ordem de compra, uma fatura de pagamento antecipado é registrada e paga, e a fatura de pagamento antecipado é aplicada à fatura final. Siga estas etapas para criar um pagamento antecipado.

1.  O agente de compras cria, confirma e então emite uma ordem de compra para a qual o fornecedor solicitou um pagamento antecipado. O valor do pagamento antecipado é definido na ordem de compra como parte do contrato.
2.  O fornecedor envia uma fatura de pagamento antecipado.
3.  O coordenador de Contas a pagar registra a fatura de pagamento antecipado em relação à ordem de compra e então a fatura de pagamento antecipado é paga.
4.  Após o fornecedor entregar as mercadorias ou serviços e as faturas relacionadas ao fornecedor forem recebidas, o coordenador de Contas a pagar aplica o valor do pagamento antecipado que já foi pago na fatura.
5.  O coordenador de Contas a pagar paga e liquida o valor restante da fatura.





