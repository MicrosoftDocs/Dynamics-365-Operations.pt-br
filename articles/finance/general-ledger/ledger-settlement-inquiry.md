---
title: Consulta de liquidação do razão
description: Este artigo descreve a janela de consulta de liquidação do razão
author: kweekley
ms.date: 12/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerClosingSheet
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 33ae49d9503c0a83bda7e0093ab6ef69fb4aef0a
ms.sourcegitcommit: 9f3a60a583da21382a14f32ce146fc9ce03f2a09
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2022
ms.locfileid: "9853112"
---
# <a name="ledger-settlement-inquiry"></a>Consulta de liquidação do razão

[!include [banner](../includes/banner.md)]

Este artigo descreve a janela de **consulta de liquidação do razão** que pode ser usada para exibir transações do razão liquidadas, não liquidadas ou liquidadas e não liquidadas para um período fiscal.

## <a name="view-ledger-settlement-transactions"></a>Exibir transações de liquidação do razão
1.  Acesse **Contabilidade > Consultas e relatórios > Consulta de liquidação do razão**.
2.  Use os campos **Data inicial** e **Data final** ou o campo **Intervalo de datas** para especificar um intervalo de datas. Para o balancete, o intervalo de datas deve estar em um único ano fiscal.
3.  No campo **Contas principais**, selecione uma ou mais contas principais para exibir as transações do razão. A lista suspensa mostra somente as contas principais configuradas para liquidação do razão na página **Parâmetros da contabilidade**.
4.  Use o campo **Dimensão financeira** para mostrar as dimensões financeiras na grade. Como a conta principal é obrigatória, o valor do campo da **Conta principal** sempre será mostrado como a primeira coluna, mesmo que você selecione um conjunto de dimensões financeiras que não inclua a conta principal.
5.  No campo **Status**, selecione:
-   **Tudo** para exibir transações liquidadas e não liquidadas
-   **Não liquidadas** para exibir somente as transações não liquidadas 
-   **Liquidadas** para exibir somente as transações liquidadas
6.  Selecione **Mostrar transações**. As transações do razão aparecem na grade, com base nos critérios inseridos. Você pode exportar os resultados da consulta para o Microsoft Excel para uma análise mais detalhada. Selecione e segure (ou clique com o botão direito) a grade.

### <a name="column-details"></a>Detalhes da coluna
A grade na página **Consulta de liquidação do razão** inclui as seguintes colunas:
-   **Conta principal**: esse campo é obrigatório e sempre é exibido.
-   **Dimensões financeiras**: são mostradas com base no conjunto de dimensões financeiras selecionado.
-   **Data da transação**: a data de lançamento da transação do razão.
-   **Data da transação original**: se o fechamento do exercício da contabilidade tiver sido executado e a liquidação do razão estiver configurada de modo a manter os detalhes de uma conta principal, as transações não liquidadas serão mostradas em detalhes como um saldo inicial. A data de lançamento original da transação do razão é mantida no campo **Data da transação original**.
-   **Idade da transação**: o valor é 0 (zero) para todas as transações liquidadas. Para transações não liquidadas, o valor é calculado como o número de dias a partir da data da transação original ou da data da transação até a data em que a consulta é executada.
Por exemplo, uma transação do razão tem uma data de transação de 1º de janeiro de 2022 (01/01/2022) e uma data da transação original de 30 de dezembro de 2021 (30/12/2021). Se a consulta for executada em 2 de janeiro de 2022 (02/01/2022) para o ano fiscal de 2022, o **Valor da idade da transação** será 4. Esse valor é calculado como o número de dias entre a data da transação original (30/12/2021) e 02/01/2022.

Se não houver uma data da transação original, a data da transação será usada.
-   **(Outras informações transacionais)**: as colunas adicionais mostram informações como o número do comprovante, a descrição e os valores de débito e crédito em todas as três moedas (transação, contabilidade e relatórios).
-   **Status**: esse valor é **Liquidado** ou **Não liquidado**.
-   **ID da liquidação**: a ID atribuída às transações liquidadas.

[![Página Consulta de liquidação do razão](./media/Inquiry1.png)](./media/Inquiry1.png)

 
Os totais podem ser mostrados abaixo da grade.
1.  Selecione as reticências (...) à direita da grade e, depois, selecione **Mostrar rodapé**.
2.  Selecione e segure (ou clique com o botão direito) em cada coluna de valor e, em seguida, selecione **Agrupar por esta coluna** para mostrar os totais. Os totais são mostrados no rodapé. Se a consulta for filtrada para que mostre somente transações não liquidadas, você poderá usar os totais para reconciliar os valores com o balancete.







