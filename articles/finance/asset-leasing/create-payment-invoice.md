---
title: Criar faturas de pagamento
description: Este tópico explica como criar faturas de arrendamento mensais. Você pode criar faturas para arrendamentos individuais ou então usar um processo em lote para criá-las para vários arrendamentos.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 32618814d00cb1e1f1082169a64b187cce1e76b4
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "4440538"
---
# <a name="create-payment-invoices"></a>Criar faturas de pagamento

[!include [banner](../includes/banner.md)]

Você pode criar faturas mensais para arrendamentos individuais ou então usar um processo em lote para criá-las para vários arrendamentos. O procedimento a seguir mostra como criar uma entrada de pagamento de arrendamento individual quando o parâmetro **Pagar ao fornecedor** na página **Configuração do registro de arrendamento** está ativado.

1. Na página **Resumo do arrendamento**, selecione um arrendamento e selecione **Registros \> Agendamento de pagamento**.
2. Selecione o pagamento que deve ser feito e selecione **Criar diário**. Você recebe uma mensagem que informa que um diário foi criado com base no pagamento selecionado.
3. Selecione **Diários de faturas** e, em seguida, selecione a fatura que deve ser paga.
4. Na guia **Linhas**, revise a entrada de diário antes de lançá-la na contabilidade.

    > [!NOTE]
    > Por padrão, as linhas da fatura do fornecedor criadas usam o perfil de lançamento do fornecedor na página **Parâmetros de contas a pagar**.

5. Selecione o diário correto e então a fatura que deve ser paga.

    Para este exemplo, o parâmetro **Pagar ao fornecedor** no registro de arrendamento é ativado. Portanto, a fatura estará no diário de faturas. A seção **Visão geral** mostra um resumo da entrada de diário e a seção **Linhas** mostra detalhes das linhas do próprio diário.

    > [!NOTE]
    > Se o parâmetro **Pagar ao fornecedor** estiver desativado, as entradas do diário de pagamento serão listadas na página **Arrendamento de ativos** para o registro de arrendamento, e o sistema criará uma entrada de arrendamento de ativos em vez de uma fatura. A entrada de pagamento do arrendamento será lançada no nome do diário especificado no campo **Diário de arrendamento mensal**.

6. Depois que a transação é lançada, você pode exibir as informações de transação e o valor de transporte da responsabilidade com arrendamento selecionando **Transações de responsabilidade** no registro de arrendamento.

    No agendamento de pagamento, a caixa de seleção **Diário lançado** será marcada, e a linha mostrará o número do diário de faturas. Depois que um diário de pagamentos e uma entrada desse diário tiverem sido criados, você deverá reverter a entrada para que ela possa ser criada novamente.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]