---
title: Renunciar, restabelecer ou estornar taxas de juros
description: Este artigo explica como cancelar, reestabelecer, e reverter cobranças de juros e taxas.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustInterestJourList
audience: Application User
ms.reviewer: roschlom
ms.custom: 59461
ms.assetid: 25ec29f3-e3ea-4abb-bf6b-f6240873b315
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b50b6ad0abd566fbcaf9cf8ad36af69fb4b3e551
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814167"
---
# <a name="waive-reinstate-or-reverse-interest-fees"></a>Renunciar, restabelecer ou estornar taxas de juros

[!include [banner](../includes/banner.md)]

Este artigo explica como cancelar, reestabelecer, e reverter cobranças de juros e taxas.

Você pode usar os botões na guia **Coletar** da página de listagem **Todos os clientes** para renunciar, estornar ou restabelecer encargos:

-   Os encargos renunciados são perdoados. Você pode renunciar a um encargo se, por exemplo, um cliente contestar o encargo, e você desejar manter um bom relacionamento comercial com ele.
-   Os encargos reaplicados tornam-se devidos novamente. Você pode reaplicar encargos que foram renunciados anteriormente. Talvez precise reaplicar encargos se você determinar que eles não devem ter sido renunciados.
-   Os encargos revertidos são removidos de uma conta de cliente e não são mais devidos. Você pode reverter encargos se, por exemplo, a taxa de juros incorreta tiver sido selecionada para calcular o valor que um cliente deve. Você pode usar um processo diferente para recalcular juros e criar uma nota de juros cotendo os novos encargos para o cliente.

Todas essas ações mudam uma nota de juros. Uma nota de juros é um documento comercial que informa aos clientes quando os juros ou taxas foram cobrados em sua conta. Quando você renuncia ou reverte juros ou taxas, uma nota de crédito ou uma fatura de ajuste é criada automaticamente para liquidar os encargos. Se você reaplicar encargos renunciados, uma fatura com um valor de débito será criada automaticamente para reaplicar os encargos devidos pelo cliente. A tabela a seguir descreve os resultados de cada ação.

| Ação                                                                                                                                                                                                            | Resultado para o cliente                                                                                             | Processo                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Renunciar notas de juros completas junto com todos os juros e taxas que elas incluem. –ou– Selecionar e renunciar transações de taxas ou de juros que fazem parte de notas de juros.                                        | Os encargos são perdoados.                                                                                           | Uma nota de crédito, ou fatura de ajuste, será criada para o cliente. A nota de crédito é usada para liquidar automaticamente a nota de juros, ou as transações de juros ou taxas selecionadas. O valor liquidado é igual ao valor total dos encargos, menos todos os pagamentos anteriores efetuados pelo cliente e menos os valores antes renunciados ou baixados. Se o valor da nota de crédito excede o valor que o cliente deve, você pode converter a nota de crédito em uma fatura de fornecedor. Você pode reembolsar o cliente.                                                       |
| Reaplicar notas de juros completas junto com todos os juros e taxas que elas incluem. –ou– Selecionar e reaplicar transações de taxas ou de juros que fazem parte das notas de juros.                                | O valor renunciado é devido novamente.                                                                                     | Uma fatura que tem um valor de débito é criada, e o valor é liquidado automaticamente em relação aos encargos antes renunciados. As notas de juros reais não são reaplicadas. Em vez de isso, uma fatura é criada e mostra o valor devido pelo cliente. As notas de crédito, ou faturas de ajuste, que foram criadas para liquidar notas de juros renunciadas, ainda podem existir se não tiverem sido usadas para liquidar as notas de juros. Nesse caso, as notas de crédito pendentes são canceladas. As notas de crédito pendentes geralmente são liquidadas automaticamente quando as notas de juros são renunciadas. No entanto, uma nota de crédito pendente pode existir se um cliente tiver pago uma nota de juros, mesmo que este tenha disputado os encargos. |
| Estornar notas de juros completas. –ou– Estornar transações de juros selecionadas que fazem parte das notas de juros. **Observação:** Não é possível estornar uma taxa. Mas você pode estornar uma nota de juros completa que inclua uma taxa. | Os encargos são não mais devidos pelo cliente. No entanto, os encargos tornam-se devidos novamente se você recalcular os juros. | O processo é igual ao processo de renunciar notas de juros ou transações de juros selecionadas. Uma nota de crédito, ou fatura de ajuste, será criada para o cliente. Essa nota de crédito é usada para liquidar automaticamente a nota de juros. Você pode usar um processo diferente para recalcular juros e criar uma nova nota de juros.                                                                                                                                                                                                                                                                                                                                                                                              |

> [!NOTE] 
> Você também pode usar um processo separado para dar baixa em dívidas inválidas. Esse processo marca todas as transações do cliente para liquidação, em vez de renunciar apenas os encargos que fazem parte de notas de juros.

## <a name="adjust-interest-for-invoices"></a>Ajustar juros para faturas
Além de ajustar notas de juros, você pode remover os encargos de juros em faturas usando um dos processos a seguir. Os dois processos também fazem ajustes às notas de juros relacionadas.

### <a name="correct-an-invoice-that-has-associated-interest"></a>Correção de uma fatura com juros associados

Você pode corrigir uma fatura lançada que está incluída em uma nota de juros. Esse processo copia os detalhes da fatura existente em uma nova fatura para fazer somente as correções desejadas. A fatura é cancelada e uma nova fatura é criada. Os juros na transação também serão revertidas na nota de juros, se a nota de juros tiver sido lançada. 

Você pode fazer a correção usando o botão **Corrigir fatura** no Painel de Ação da fatura de texto livre. Este botão está disponível somente se a chave de configuração **Correção da fatura de texto livre** está selecionada.

### <a name="reverse-a-customer-transaction-that-has-associated-interest"></a>Reverter uma transação do cliente que tem juros associados

Você pode reverter uma transação de cliente em uma fatura se a fatura foi criada incorretamente. Se a transação de cliente revertida tiver juros incluídos em uma nota de juros, e a fatura tiver sido lançada, os juros na transação também serão revertidos na nota de juros. A nota de juros será cancelada se não tiver sido lançada. 

Você pode reverter transações do cliente usando o botão **Reverter** na página **Transações de cliente**.

## <a name="waive-or-reinstate-interest-notes"></a>Renunciar ou reaplicar notas de juros
Você pode renunciar ou reaplicar todos os encargos nas notas de juros selecionadas. Quando você renuncia aos encargos, o valor total a ser renunciado não pode exceder limites de valores definidos. Você pode reaplicar uma nota de juros somente se ela tiver sido renunciada anteriormente. 

Você renunciar ou reaplicar notas de juros usando o botão **Nota de juros** na guia **Coletar** da página **Cliente**.

## <a name="waive-or-reinstate-interest-transactions"></a>Renunciar ou reaplicar transações de juros
Você pode renunciar ou reaplicar transações de juros específicas em uma nota de juros, em vez de ajustar todos os encargos nessa nota de juros. Quando você renuncia aos encargos, o valor total a ser renunciado não pode exceder limites de valores definidos. Você pode reaplicar uma transação de juros somente se ela tiver sido renunciada anteriormente. 

Você pode renunciar ou reaplicar notas de juros usando o botão **Juros da transação** na guia **Coletar** da página **Cliente**.

## <a name="waive-or-reinstate-fees"></a>Renunciar ou reaplicar taxas
Você pode renunciar ou reaplicar taxas específicas em uma nota de juros, em vez de ajustar todos os encargos nessa nota de juros. Quando você renuncia aos encargos, o valor total a ser renunciado não pode exceder limites de valores definidos. Você pode reaplicar uma taxa somente se ela tiver sido renunciada anteriormente. 

Você pode renunciar ou reaplicar notas de juros usando o botão **Taxa** na guia **Coletar** da página **Cliente**.

## <a name="reverse-interest-notes"></a>Reverter notas de juros
Você pode reverter todos os encargos nas notas de juros selecionadas. Os encargos revertidos são removidos de uma conta de cliente e não são mais devidos. Depois que a nota de juros for revertida, é possível recalcular juros e criar uma nova nota de juros. 

Você pode reverter notas de juros usando o botão **Nota de juros** na guia **Coletar** da página **Cliente**.

## <a name="reverse-interest-transactions"></a>Reverter transações de juros
Você pode reverter todas as transações de juros selecionadas. Os encargos revertidos são removidos de uma conta de cliente e não são mais devidos. Depois que as transações forem revertidas, é possível recalcular juros e criar uma nova nota de juros.

Você pode reverter transações de juros usando o botão **Juros da transação** na guia **Coletar** da página **Cliente**.

## <a name="view-the-history-of-adjustments-for-charges-that-were-waived-reinstated-or-reversed"></a>Exibir o histórico de ajustes para os encargos que foram renunciados, reaplicados ou revertidos
Você pode exibir o histórico detalhado de ajustes feitos para notas de juros, como o usuário que lançou o ajuste, o tipo de ajuste, o valor e quando o ajuste foi inserido. Por exemplo, você pode optar por exibir os ajustes anteriores que foram inseridos para uma nota de juros antes de criar uma nova nota de juros. 

Você pode reverter transações de juros usando o botão **Histórico** na guia **Coletar** da página **Cliente**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]