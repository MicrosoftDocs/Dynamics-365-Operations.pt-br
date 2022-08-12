---
title: Liquidar pendências
description: Você pode liquidar o valor restante da atividade de liquidação aplicando esse valor a uma conta contábil.
author: angelad116
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2018-12-01
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 1b50098470cfa070a6c430e65f2fa24317c14b97
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151171"
---
# <a name="settle-remainder"></a>Liquidar pendências

[!include [banner](../includes/banner.md)]

Você pode liquidar o valor restante da atividade de liquidação aplicando esse valor a uma conta contábil ou a outro cliente. Você poderá liquidar o restante quando estiver liquidando os valores inseridos em um diário ou quando estiver apenas liquidando transações abertas.

## <a name="setting-up-defaults"></a>Configurando padrões 
Você deve habilitar o recurso **Liquidação de pendências** e definir as configurações padrão antes de usar **Liquidar pendências**.

1)  Clique em **Contas a receber > Parâmetros > Liquidações** ou **Contas a pagar > Parâmetros > Liquidações**
2)  Selecione a guia **Liquidação** e clique em **Habilitar a liquidação de pendências**.
3)  Em **Código de motivo padrão**, selecione um código de motivo padrão. Os códigos de motivo já devem ter sido configurados em **Contas a receber > Configuração > Códigos de motivo de baixa contábil** ou **Contas a pagar > Configuração > Códigos de motivo de baixa contábil de cliente**. A **Conta de liquidação de pendências padrão** será padronizada como a conta atribuída ao código de motivo de baixa.
3)  Atualize a **Conta de liquidação de pendências padrão** conforme necessário.
4)  Em **Nome padrão do diário**, selecione um diário de pagamento que será usado se você quiser criar um diário de pagamentos quando você liquidar somente transações abertas. Se você habilitar o recurso do restante do acordo, deverá adicionar um nome de diário padrão.

## <a name="settle-remainder-from-a-journal"></a>Liquidar pendências de um diário
Se não habilitar o recurso **Liquidar pendências**, você ainda poderá inserir uma transação em um diário e liquidar transações nele, como fez no passado. Quando você clica no botão **OK**, o saldo aberto na fatura é reduzido pelo valor em dinheiro. Se o pagamento à vista não liquidar totalmente a fatura, ela será deixada aberta com um valor restante a ser liquidado posteriormente.

Quando o recurso **Liquidar pendências** estiver habilitado, você poderá liquidar o valor restante a uma conta contábil. Você também pode transferir o restante para outra conta de cliente (para transações de cliente) ou para outro fornecedor (para transações do fornecedor) em vez de deixar as faturas abertas. 

Para liquidar o restante da página **Liquidação**, execute as seguintes etapas:

1)  Na página **Liquidação**, marque as faturas ou as transações que você deseja liquidar.
2)  Clique no botão **Liquidar pendências**.
3)  Uma caixa de diálogo aparecerá, mostrando o valor que será liquidado em relação a uma conta contábil, a data que será usada para liquidar as pendências, o código de motivo padrão dos parâmetros e a conta padrão dos parâmetros. 
4)  Selecione um novo motivo de liquidação se desejar alterar o motivo padrão. A conta de liquidação será alterada para a conta associada ao código de motivo.
5)  Edite a conta de liquidação se desejar alterá-la.
6)  Se você estiver liquidando transações de cliente e desejar mover o restante para um outro cliente, selecione um cliente em **Liquidar a pendência na conta de cliente**. Se você estiver liquidando transações de fornecedor e desejar mover o restante para um outro fornecedor, selecione um fornecedor em **Liquidar a pendência na conta de fornecedor**.
6)  Clique em **Liquidar pendências**.
7)  A página **Diário** será exibida. Uma linha de diário adicional será adicionada ao diário com o valor da liquidação de pendências como o valor e com a conta da liquidação de pendências como a contrapartida. Se você adicionou um cliente ou fornecedor para que possa mover o valor da liquidação para um outro cliente ou fornecedor, uma linha adicional será adicionada ao diário para mover o valor da liquidação para esse cliente ou fornecedor.

Quando você lançar o diário, a transação aberta será totalmente liquidada. 

## <a name="settle-remainder-when-you-are-only-settling-open-transactions"></a>Liquide as pendências quando você estiver liquidando somente transações abertas
Você também poderá liquidar as pendências quando estiver liquidando transações abertas de um diário.

Para liquidar as pendências, execute estas etapas:

1)  Na página **Liquidação**, marque as faturas ou as transações que você deseja liquidar.
2)  Clique em **Liquidar pendências**.
3)  Uma caixa de diálogo aparecerá, mostrando o valor que será liquidado em relação a uma conta contábil, a data que será usada para liquidar as pendências, o código de motivo padrão dos parâmetros e a conta padrão dos parâmetros. 
4)  Selecione um novo motivo de liquidação se desejar alterar o motivo padrão. A conta de liquidação será alterada para a conta associada ao código de motivo.
5)  Edite a **conta de liquidação** se desejar alterá-la.
6)  Se você estiver liquidando transações de cliente e desejar mover o restante para um outro cliente, selecione um cliente em **Liquidar a pendência na conta de cliente**. Se você estiver liquidando transações de fornecedor e desejar mover o restante para um outro fornecedor, selecione um fornecedor em **Liquidar a pendência na conta de fornecedor**
7)  Você também pode decidir criar um diário de pagamento com a liquidação de pendências ou apenas lançá-lo sem um diário. Selecione **Sim** para que **Editar o diário** crie um diário de pagamento. É possível editar o diário de pagamento que você criou.
8)  Clique em **Liquidar pendências**. Se optar por criar um diário, o botão será alterado para **Criar diário**. Clique em **Criar diário**.
9)  Se você criar um diário de pagamento, a página do diário será aberta após você clicar em **Liquidar pendências**. Uma linha de diário será adicionada ao diário com o valor da liquidação de pendências como o valor e com a conta da liquidação de pendências como a contrapartida. Se você adicionou um cliente ou fornecedor para que possa mover o valor da liquidação para um outro cliente ou fornecedor, uma linha adicional será adicionada ao diário para mover o valor da liquidação para esse cliente ou fornecedor.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
