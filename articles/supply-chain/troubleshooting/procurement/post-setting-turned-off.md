---
title: A configuração Lançar na conta de encargos não está ativada
description: Esse problema ocorre quando uma ordem de compra é faturada, se a opção "Lançar na conta de encargos do razão" estiver habilitada na guia "Fatura" da página "Parâmetros de contas a pagar".
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 592444958dad4624fdc9098dc58df0a2e49e63de
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475600"
---
# <a name="the-post-to-charge-account-in-ledger-setting-isnt-turned-on"></a>A configuração Lançar na conta de encargos não está ativada

## <a name="symptoms"></a>Sintomas

Esse problema ocorre quando uma ordem de compra é faturada, se a opção **Lançar na conta de encargos do razão** estiver definida como *Sim* na guia **Fatura** da página **Parâmetros de contas a pagar**.

## <a name="reproduce-the-issue"></a>Reproduzir o problema

O seguinte procedimento mostra uma forma de reproduzir o problema.

1. Acesse **Contas a pagar \> Configuração \> Parâmetros de contas a pagar**.
1. Na guia **Fatura**, configure a opção **Lançar na conta de encargos do razão** como *Sim*.
1. Acesse **Gerenciamento de estoque \> Configurar \> Lançamento \> Lançamento**.
1. Na guia **Ordem de compra**, certifique-se de ter excluído todas as linhas nas despesas de compra do produto.
1. Acesse **Contas a pagar \> Ordens de compra \> Todas as ordens de compra**.
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

## <a name="resolution"></a>Resolução

Isso depende das configurações de parâmetro para faturas e grupos de faturas. Para obter mais informações, consulte a seguinte postagem no blog: [Contabilização de encargo de compra e variação de estoque](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).
