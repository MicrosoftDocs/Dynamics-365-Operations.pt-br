---
title: Configurar e processar pagamentos de transição
description: Este artigo explica como configurar e processar pagamentos de transição de clientes. O pagamento de transição é lançado no livro-razão em duas etapas.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPaymMode, VendPaymMode, LedgerJournalTable, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, LedgerJournalTransDaily
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bb563008f156e1bfa6e4e9a705e9170342719ce7
ms.sourcegitcommit: 9740f9b41a7dcf1821c6baccb2e05b9865ac2966
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2022
ms.locfileid: "9775159"
---
# <a name="set-up-and-process-bridged-payments"></a>Configurar e processar pagamentos de transição

[!include [banner](../includes/banner.md)]

O pagamento de transição é lançado no livro-razão em duas etapas. Normalmente, essa abordagem é usada quando o método de pagamento é definido como **Banco**, e você deve lançar transações para a conta bancária somente quando a transação for compensada pelo banco. No entanto, você também pode usá-la para uma conta do livro-razão. Nesse caso, o valor de uma conta principal será movido para outra quando o lançamento de transição é processado.

Você pode criar pagamentos de transição a partir de contas a pagar ou contas a receber. Embora este artigo explique como configurar o lançamento de transições para contas a receber, as etapas para transações de contas a pagar são semelhantes.

## <a name="set-up-bridging-posting"></a>Configurar lançamento de transição

Para usar o lançamento de transição, você deve configurar uma ou mais formas de pagamento para que usem o método **Lançamento de transição**. Em seguida, você deve selecionar uma conta de transição.

1. Vá para **Contas a receber &gt; Configuração de pagamento &gt; Formas de pagamento**.
2. Selecione uma forma de pagamento existente para habilitar o lançamento de transição dela. Você também pode criar uma nova forma de pagamento.
3. Marque a caixa de seleção **Lançamento de transição**.
4. No campo **Conta de transição**, selecione a conta principal em que os pagamentos devem ser lançados antes de serem compensados para a conta bancária.
5. Feche a página.

## <a name="process-and-transfer-bridging-posting"></a>Processar e transferir lançamento de transição

Para criar e processar lançamentos de transição, siga estas etapas:

1. Acesse **Contas a receber &gt; Pagamentos &gt; Diário de pagamento do cliente**.
2. Para criar um diário, selecione **Novo**.
3. No campo **Nome**, selecione um nome.
4. Adicione linhas ao diário de pagamentos do cliente e selecione a forma de pagamento configurada para lançamento de transição.
5. Lançar o diário. As transações serão lançadas na conta principal selecionada no campo **Conta de transição**, no procedimento anterior.

Quando as transações forem compensadas pelo banco e você quiser transferir o pagamento da conta de transição para a conta de pagamento especificada como forma de pagamento, siga estas etapas:

1. Ir para **Contabilidade &gt; Entradas de diários &gt; Diários gerais**.
2. Para criar um diário, selecione **Novo**.
3. No campo **Nome**, selecione um nome.
4. Selecione **Linhas** para abrir os detalhes do diário.
5. Selecione **Funções &gt; Transações de transição selecionadas**.
6. Marque todos os pagamentos compensados e selecione **Aceitar**.
7. Lançar o diário.
