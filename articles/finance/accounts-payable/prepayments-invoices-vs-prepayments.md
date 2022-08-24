---
title: Faturas de pagamento antecipado versus pagamentos antecipados
description: Este artigo descreve e compara os dois métodos que as organizações podem usar para pagamentos antecipados.
author: abruer
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, PurchTable
audience: Application User
ms.reviewer: twheeloc
ms.custom: 15871
ms.assetid: a0bb5220-73d4-48ae-84d0-46a171c224fa
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 901683f2176189ce2f4186b4f9b3b5c64ec9f2b1
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2022
ms.locfileid: "9227764"
---
# <a name="prepayment-invoices-vs-prepayments"></a>Faturas de pagamento antecipado versus pagamentos antecipados

[!include [banner](../includes/banner.md)]

Este artigo descreve e compara os dois métodos que as organizações podem usar para pagamentos antecipados. Um método cria uma fatura de pagamento antecipado que esteja associada a uma ordem de compra. O outro método cria comprovantes de diário de pagamentos antecipados criando entradas de diário e marcando-as como comprovantes de diário de pagamentos antecipados.

As organizações podem emitir pagamentos antecipados a fornecedores para mercadorias ou serviços, antes que as mercadorias ou serviços sejam entregues. Dois métodos podem ser usados para emitir pagamentos antecipados aos fornecedores. Para minimizar o risco, é possível rastrear pagamentos antecipados definindo o pagamento antecipado em uma ordem de compra. Para esse método, você deve criar uma fatura de pagamento antecipado que esteja associada a uma ordem de compra. Este método é conhecido como faturação de pagamento antecipado. As organizações que não desejam controlar os pagamentos antecipados de forma tão próxima ou que não recebem uma fatura de pagamento antecipado do fornecedor podem usar comprovantes de diário de pagamentos antecipados em vez do método de faturamento de pagamento antecipado. É possível criar comprovantes de diário de pagamentos antecipados criando entradas de diário e marcando-as como comprovantes de diário de pagamentos antecipados. Nesse método, você não pode controlar quais pagamentos antecipados para um fornecedor são feitos em quais ordens de compra. No entanto, você pode marcar um pagamento antecipado para liquidação em relação a uma ordem de compra.

## <a name="when-to-use-prepayment-invoicing-vs-prepayments"></a>Quando usar o faturamento de pagamento antecipado versus pagamentos antecipados

| Faturamento de pagamento antecipado                                                                | Pagamentos Antecipados                                                              |
|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------|
| Defina um valor de pagamento antecipado na ordem de compra.                                    | Nenhum valor de pagamento antecipado é definido na ordem de compra.                    |
| Uma fatura de pagamento antecipado e uma fatura final devem ser lançadas.                       | Nenhuma fatura de pagamento antecipado deve ser lançada.                                    |
| A responsabilidade do pagamento antecipado é mantida na conta de pagamento antecipado e não na conta AP. | A responsabilidade do pagamento antecipado é mantida na conta AP.                  |
| O saldo de fornecedor não reflete o valor do pagamento antecipado durante o processo.     | O saldo de fornecedor reflete o valor do pagamento antecipado durante o processo. |
| A faturação de pagamento antecipado está disponível apenas em Contas a pagar.                         | Os pagamentos antecipados estão disponíveis em Contas a pagar e em Contas a receber.    |

## <a name="overview-of-the-prepayment-process"></a>Visão geral do processo de pagamento antecipado
As práticas contábeis em muitos países/regiões exigem que os pagamentos antecipados de um cliente ou a um fornecedor não sejam lançados nas contas resumo usuais para o cliente ou fornecedor. Em vez disso, esses pagamentos antecipados são lançados em contas contábeis especiais. Quando uma ordem de compra ou de venda é criada, uma fatura é emitida para o cliente ou do fornecedor. Quando a fatura é paga, o comprovante de pagamento antecipado e de pagamento antecipado de imposto nas contas contábeis de pagamento antecipado são revertidos, e os valores da fatura são lançados automaticamente nas contas resumo usuais. Siga estas etapas para criar um pagamento antecipado.

1.  Configure perfis de lançamento para pagamentos antecipados.
2.  Nos parâmetros de Contas a receber e nos parâmetros de Contas a pagar, sob **Razão e imposto**, selecione o novo perfil de lançamento usando o parâmetro **Perfil de lançamentos para o diário de pagamentos com pagamento antecipado**.
3.  Crie um diário de pagamentos e, depois, crie o novo pagamento.
4.  Você pode sinalizar o pagamento como um pagamento antecipado. Se um pagamento for sinalizado como um pagamento antecipado, o pagamento será lançado nas contas contábeis definidas no perfil de lançamento configurado nas etapas 1 e 2. Além disso, se o pagamento for sinalizado como um pagamento antecipado, os impostos serão calculados. Alguns governos exigem que os impostos sejam pagos quando um pagamento antecipado é registrado, mesmo se que não exista uma fatura.
5.  Lance o pagamento antecipado.
6.  Opcional: Você pode liquidar o pagamento antecipado na ordem de compra ou ordem de venda antes de criar a fatura. Na página da ordem de venda ou ordem de compra, no Painel de Ações, use **Liquidar transações**.
7.  Depois que o fornecedor entregar as mercadorias ou os serviços, registre a fatura. Se você tiver liquidado o pagamento antecipado em relação à ordem de compra ou à ordem de venda na etapa 6, o pagamento antecipado será automaticamente liquidado em relação à fatura que você criou. Se você não tiver liquidado o pagamento antecipado na ordem de compra ou na ordem de venda, poderá liquidá-lo manualmente na fatura usando **Liquidar transações** na página do cliente ou do fornecedor. O valor do pagamento antecipado é revertido temporariamente fora da conta contábil AP/AR. Além disso, se os impostos forem calculados, eles são revertidos, pois a fatura tem os impostos reais.

## <a name="overview-of-the-prepayment-invoicing-process"></a>Visão geral do processo de faturamento de pagamento antecipado
As faturas de pagamento antecipado são uma prática empresarial comum. Um fornecedor emite faturas de pagamento antecipado para exigir um depósito na compra antes do atendimento da ordem de compra. Por exemplo, alguns fornecedores exigem um pagamento antecipado para mercadorias ou serviços personalizados. Se um fornecedor emitir uma fatura que solicite pagamento antecipado, você poderá usar o recurso de faturamento de pagamento antecipado. Um valor do pagamento antecipado pode ser definido na ordem de compra, uma fatura de pagamento antecipado é registrada e paga, e a fatura de pagamento antecipado é aplicada à fatura final. Siga estas etapas para criar um pagamento antecipado.

1.  O agente de compras cria, confirma e então emite uma ordem de compra para a qual o fornecedor solicitou um pagamento antecipado. O valor do pagamento antecipado é definido na ordem de compra como parte do contrato.
2.  O fornecedor envia uma fatura de pagamento antecipado.
3.  O coordenador de Contas a pagar registra a fatura de pagamento antecipado em relação à ordem de compra e então a fatura de pagamento antecipado é paga.
4.  O fornecedor envia uma solicitação de pagamento, chamada de fatura padrão de fornecedor. Após o fornecedor entregar as mercadorias ou serviços e as faturas padrão de fornecedor forem recebidas, o coordenador de Contas a pagar aplica o valor do pagamento antecipado que já foi pago na fatura padrão.
5.  O coordenador de Contas a pagar paga e liquida o valor restante da fatura padrão.

## <a name="set-up-parameters-to-enable-the-prepayment-invoicing-process"></a>Configurar parâmetros para habilitar o processo de faturamento de pagamento antecipado
Uma conta de pagamento antecipado deve ser definida na guia **Ordem de compra** da página **Lançamento de estoque** (**Gerenciamento de estoque \> Configuração \> Lançamento \> Lançamento**). A conta de pagamento antecipado será atualizada, e costuma ser debitada quando a fatura de pagamento antecipado é lançada. O saldo na conta de pagamento antecipado será revertido quando a fatura padrão aplicada à fatura de pagamento antecipado for lançada. Se você não liquidar a fatura do pagamento antecipado antes de aplicar a fatura de pagamento antecipado à fatura padrão, as entradas contábeis da fatura lançada com o pagamento antecipado serão revertidas quando a fatura padrão for lançada.

A conta de Resumo de impostos de contas a pagar é definida no perfil **lançamentos de fornecedores**. Para definir o perfil de lançamento padrão, clique em **Contas a pagar \>Configuração \> Parâmetros das contas a pagar \>Guia de razão e impostos \> Perfil de lançamento com fatura de fornecedor**.

A **Política de aplicação do pagamento antecipado** indica se o sistema automaticamente aplicará as faturas de pagamento antecipado pagas à fatura criada manualmente. As faturas criadas usando uma entidade de dados não seguem a **Política de aplicação do pagamento antecipado**. Você precisará aplicar manualmente as faturas de pagamento antecipado a faturas criadas usando uma entidade de dados. Para definir a política, acesse **Contas a pagar \>Configuração \> Parâmetros de contas a pagar \> Guia de razão e impostos \> Política de aplicação do pagamento antecipado**. Se o campo **Política de aplicação de pagamento antecipado** estiver configurado como **Automático**, a fatura de pagamento antecipado será automaticamente definida para ser paga com a fatura final. Se o campo estiver configurado como **Notificação**, quando a fatura final for criada, será exibida uma indicação visual que o pagamento antecipado da fatura está disponível para aplicação.

## <a name="create-a-purchase-order-that-contains-prepayment-invoice-information"></a>Crie uma ordem de compra que contém informações da fatura de pagamento antecipado
Quando um fornecedor informa que é necessário um pagamento antecipado de bens e serviços contidos em uma ordem de compra, você deve definir o valor do pagamento antecipado da ordem de compra associada. Acesse **Contas a pagar \> Comum \> Ordens de compra \> Todas as ordens de compra** e encontre a ordem de compra do fornecedor. No Painel de ação, selecione a guia **Compra** e **Pagamento antecipado**. Insira informações do pagamento antecipado, incluindo uma descrição, o valor do pagamento antecipado, se o pagamento antecipado é um valor fixo ou uma porcentagem, e um ID da categoria de pagamento antecipado. 

Observe que não são permitidas várias definições de pagamentos antecipados em uma ordem de compra. Se você precisar permitir vários pagamentos antecipados em uma ordem de compra, lance os pagamentos usando o diário de pagamento em vez de uma fatura de pagamento antecipado.

O pagamento antecipado pode ser removido da ordem de compra, exceto se você já tiver feito um pagamento da fatura de pagamento lançada ou lançar a fatura padrão. Para remover uma informação de pagamento antecipado da ordem de compra, selecione **Contas a pagar \> Comum \> Ordens de compra \> Todas as ordens de compra** e localize a ordem de compra do fornecedor. No Painel de ação, selecione a guia **Compra** e **Remover pagamento antecipado**.

## <a name="create-and-post-a-prepayment-invoice"></a>Crie e lance uma fatura de pagamento antecipado
Para registrar a fatura de pagamento antecipado do fornecedor, acesse a página **Fatura de fornecedor** selecionando a opção **Fatura de pagamento antecipado** na página **Ordens de compra** (**Contas a pagar \> Comum \> Ordens de compra \> Todas as ordens de compra \>Guia de fatura \> Fatura de pagamento antecipado**). Insira as informações da fatura de pagamento antecipado, incluindo o número da fatura. Não é possível alterar os valores de uma fatura de pagamento antecipado. Se o fornecedor tiver faturado parte do valor do pagamento antecipado definido na ordem de compra, você poderá atualizar o preço unitário para refletir o valor parcial.

Quando a fatura de pagamento antecipado for lançada, o saldo do fornecedor e a conta de pagamento antecipado serão atualizados. O valor da **Aplicação do pagamento antecipado** na definição de pagamento antecipado contido na ordem de compra também será atualizado. As entradas padrão de dimensão financeira do comprovante de pagamento antecipado lançado serão removidas das informações do cabeçalho da ordem de compra.

Se o recurso **Bloquear dimensões financeiras nas linhas da fatura de pagamento antecipado do fornecedor** na página **Gerenciamento de recursos** estiver ativado, as dimensões nas linhas ou no cabeçalho de pagamento antecipado não poderão ser atualizadas. 

## <a name="post-and-settle-payments-for-the-prepayment-invoice"></a>Lance e faça pagamentos da fatura de pagamento antecipado
Em seguida, a fatura do pagamento antecipado será paga na página **Diário de pagamentos**. Para acessar diários de pagamentos, clique em **Contas a pagar \> Diários \> Pagamentos \> Diários de pagamentos**. Depois de lançar o pagamento na fatura de pagamento antecipado, o valor **restante da aplicação do pagamento antecipado** da ordem de compra será atualizado.

Antes de lançar a fatura padrão da fatura de pagamento antecipado, você pode reverter o pagamento na fatura de pagamento antecipado. No entanto, depois que a fatura padrão for aplicada à fatura de pagamento antecipado, o pagamento não poderá ser revertido da fatura de pagamento antecipado.

## <a name="post-the-standard-vendor-invoice-for-the-purchase-order-and-apply-the-prepayment-invoice-to-the-standard-invoice"></a>Lance a fatura padrão de fornecedor para a ordem de compra e aplique a fatura de pagamento antecipado à fatura padrão
Registre a fatura padrão recebida do fornecedor. Como parte desse processo, você pode aplicar a fatura de pagamento antecipado liquidada à fatura do fornecedor para que o valor da fatura seja reduzido pelo valor que já foi pago. Aplicar a fatura de pagamento antecipado à fatura de fornecedor garantirá que as entradas contábeis da fatura de pagamento antecipado sejam revertidas.

## <a name="application-of-the-prepayment-invoice-after-posting-the-standard-invoice"></a>Aplicação da fatura de pagamento antecipado após o lançamento da fatura padrão
Se você se esquecer de aplicar o pagamento antecipado à fatura padrão de fornecedor no momento do lançamento da fatura de fornecedor, o pagamento antecipado liquidado estará disponível para ser aplicado a outras faturas desse fornecedor na página **Fornecedores** (**Contas a pagar \> Comum \> Fornecedores \> Todos os fornecedores \> Guia de fatura \> Aplicar**).

## <a name="reversal-of-the-prepayment-application-process"></a>Cancelamento do processo de aplicação de pagamento antecipado
Se você precisar cancelar ou reverter a aplicação de uma fatura de pagamento antecipado de uma fatura padrão, selecione a ação **Reverter** na página **Fornecedores** (**Contas a pagar \> Comum \> Fornecedores \> Todos os fornecedores \> Guia de fatura \> Reverter**). Depois que a aplicação de pagamento antecipado for revertida, você poderá aplicar o pagamento antecipado a outra fatura padrão. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
