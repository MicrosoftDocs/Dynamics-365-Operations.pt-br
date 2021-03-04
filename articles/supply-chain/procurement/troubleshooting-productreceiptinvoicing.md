---
title: Solucionar problemas de recebimentos e faturamento de produtos
description: Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com recebimentos e faturamento de produtos.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: a89effb686d60dde9d11f99be51d4101897ad4ea
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4422608"
---
# <a name="troubleshoot-product-receipts-and-invoicing"></a>Solucionar problemas de recebimentos e faturamento de produtos

Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com recebimentos e faturamento de produtos.

## <a name="i-cant-post-more-than-one-invoice-for-a-purchase-order-line-that-has-category-based-items"></a>Não consigo lançar mais de uma fatura para uma linha da ordem de compra que tem itens baseados em categoria.

Uma quantidade será obrigatória se você quiser lançar faturas. Portanto, se a quantidade total de uma linha for faturada apenas por um valor parcial, não será possível faturar o valor restante em outra fatura.

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a>Recebo uma mensagem de erro "Referência de objeto não definida" durante a confirmação da ordem de compra ou uma "Exceção lançada pelo destino de uma chamada" ocorre durante o lançamento da fatura do fornecedor.

Esse problema pode ocorrer devido a inconsistências nas distribuições da ordem de compra.

Para desbloquear esse problema e redefinir a ordem de compra para um estado *Rascunho*, vá para **Compras e fornecimento \> Tarefas periódicas \> Limpar \> Redefinição de distribuição da ordem de compra**. Para obter mais informações, consulte a seguinte postagem de blog: [Resolver erros de distribuição de OC no Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="i-cant-consolidate-multiple-product-receipts-into-a-single-purchase-order"></a>Não consigo consolidar vários recebimentos de produtos em uma única ordem de compra.

Não é possível consolidar vários recebimentos de produtos em uma única ordem de compra, se as diferentes linhas de recebimento de produtos tiverem datas contábeis diferentes.

Em versões anteriores do Microsoft Dynamics 365 Supply Chain Management, a consolidação foi permitida nessa situação. No entanto, a prática está sujeita a erros. A data contábil nas linhas da ordem de compra criadas não deve diferir da data contábil nas linhas de recebimento de produtos das quais as linhas da ordem de compra foram criadas. (A data contábil nas linhas da ordem de compra corresponde à data contábil no cabeçalho da ordem de compra.) Portanto, a consolidação de vários recebimentos de produtos em uma única ordem de compra não é mais permitida.

A data contábil é usada, por exemplo, para reservas e ônus de orçamento. Portanto, ele deve ser mantido durante a transição do recebimento de produtos para a ordem de compra.

## <a name="when-product-receipts-are-canceled-transactions-can-be-posted-to-a-suspended-ledger-account"></a>Quando os recebimentos de produtos são cancelados, as transações podem ser lançadas em uma conta contábil suspensa.

### <a name="issue-description"></a>Descrição do problema

Se um recebimento de produtos for cancelado, o sistema permitirá que as transações sejam lançadas nas contas contábeis suspensas, mesmo que as contas principais sejam suspensas.

### <a name="reproduce-the-issue"></a>Reproduzir o problema

O seguinte procedimento mostra uma forma de reproduzir o problema.

1. Na página **Parâmetros de contas a pagar**, na guia **Geral**, verifique se a opção **Lançar o recebimento de produtos no razão** está definida como *Sim*.
1. Crie uma ordem de compra e adicione uma linha de ordem que tenha uma quantidade de *1.000* para um produto.
1. Confirme uma ordem de compra.
1. Lance o recebimento de produtos e verifique os comprovantes.
1. Suspenda as contas principais, *200140* e *140200* relevantes.
1. Cancele o recebimento de produtos lançados.
1. Observe que as transações podem ser lançadas nas contas contábeis suspensas.

### <a name="issue-resolution"></a>Resolução do problema

As transações podem ser lançadas nas contas contábeis suspensas quando os recebimentos de produtos forem cancelados, pois esse comportamento permite lançamentos corretos.

## <a name="a-product-receipt-voucher-number-is-consumed-even-if-no-financial-voucher-is-generated-during-product-receipt"></a>Um número de comprovante de recebimento de produtos será consumido mesmo que nenhum comprovante financeiro seja gerado durante o recebimento de produtos.

Se a opção **Acumular passivo no recebimento de produtos** estiver definida como *Não* para o grupo de modelos de item, não ocorrerá lançamentos na contabilidade. No entanto, um evento físico será registrado para a finalidade de contabilização em um diário-razão e esse evento exigirá um número de comprovante. Esse número de comprovante é o número de comprovante referido nas transações de estoque.

Recomendamos definir a opção **Acumular passivo no recebimento de produtos** como *Sim*, conforme descrito na seguinte postagem no blog: [Lançar encargos diversos no momento do recebimento do produto](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).

## <a name="the-post-to-charge-account-in-ledger-setting-isnt-turned-on"></a>A configuração Lançar na conta de encargos não está ativada.

### <a name="issue-description"></a>Descrição do problema

Esse problema ocorre quando uma ordem de compra é faturada, se a opção **Lançar na conta de encargos do razão** estiver definida como *Sim* na guia **Fatura** da página **Parâmetros de contas a pagar**.

### <a name="reproduce-the-issue"></a>Reproduzir o problema

O seguinte procedimento mostra uma forma de reproduzir o problema.

1. Acesse **Contas a pagar \> Configuração \> Parâmetros de contas a pagar**.
1. Na guia **Fatura**, configure a opção **Lançar na conta de encargos do razão** como *Sim*.
1. Vá para **Gerenciamento de estoque \> Configurar \> Lançamento \> Lançamento**.
1. Na guia **Ordem de compra**, certifique-se de ter excluído todas as linhas nas despesas de compra do produto.
1. Vá para **Contas a pagar \> Ordens de compra \> Todas as ordens de compra**.
1. Criar uma ordem de compra. No campo **Conta de fornecedor**, selecione *1001 Suprimentos de Escritórios Acme*.
1. Adicione uma linha da ordem de compra com as seguintes configurações:

    - **Nº do item:** *Projetor Laser D0011*
    - **Local:** *1*
    - **Depósito:** *11*
    - **Quantidade:** *4*

1. No Painel de Ação, na guia **Compra**, no grupo **Ação**, selecione **Confirmar**.
1. No Painel de Ação, na guia **Receber**, no grupo **Gerar**, selecione **Recebimento de produtos**.
1. Na caixa de diálogo **Lançamento de recebimento de produtos**, no campo **Recebimento de produtos**, insira um número arbitrário e selecione **OK**.
1. No Painel de Ação, na guia **Fatura**, no grupo **Gerar**, selecione **Fatura**.
1. No campo **Número**, insira um número arbitrário como o número da fatura.
1. Atualizar o status de conciliação e lançar.
1. Observe que agora você recebe o seguinte erro ao gerar uma fatura de uma ordem de compra: "O número da conta para o tipo de transação Despesas de compra para o produto não existe."

### <a name="issue-resolution"></a>Resolução do problema

Isso depende das configurações de parâmetro para faturas e grupos de faturas. Para obter mais informações, consulte a seguinte postagem no blog: [Contabilização de encargo de compra e variação de estoque](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]