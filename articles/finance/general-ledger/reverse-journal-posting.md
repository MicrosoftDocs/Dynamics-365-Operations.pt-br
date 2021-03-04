---
title: Reverter lançamento no diário
description: Este tópico descreve recursos que permitem reverter comprovantes da lista de transações de comprovante ou de diários financeiros.
author: MikeFalkner
manager: AnnBe
ms.date: 10/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e3244d857a9135249130672501f8b766ff9a0680
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440360"
---
# <a name="reverse-journal-posting"></a>Reverter lançamento no diário

[!include [banner](../includes/banner.md)]

Este tópico descreve recursos do Microsoft Dynamics 365 Finance que permitem reverter um diário inteiro, ou reverter um ou mais comprovantes da lista de transações de comprovante, independentemente da origem. 

## <a name="reversing-journals"></a>Revertendo diários

Você pode reverter linhas de diário individualmente. Com a reversão de lançamento no diário, também é possível reverter um diário financeiro inteiro. Para reverter um diário: 

- Abra o diário financeiro e filtre por diários lançados.
- Selecione o menu **Reverter** na parte superior da página.
- Você verá o número total de comprovantes e linhas de comprovante, além da quantidade total de linhas que estão sendo revertidas
- Selecione **Sim** para usar as datas de transação existentes ou **Não** para inserir uma nova. Em alguns casos, o período da transação original pode ser fechado e você deve inserir uma nova data de transação para a reversão.
- Caso selecione **Não**, insira uma data de transação para a reversão. 
- Insira um comentário a ser adicionado à transação de reversão.
- Selecione o botão **Reverter**.

As transações serão revertidas. 

Se o comprovante contiver mais de 100 linhas, o processo de reversão será executado usando o processo em lote. É possível examinar os resultados exibindo os comentários no trabalho em lotes. Todas as transações que não puderam ser revertidas serão listadas no histórico do trabalho em lotes.

Se o comprovantes tiverem 100 linhas ou menos, o processo de reversão será executado imediatamente. Os resultados serão apresentados em uma caixa de diálogo que mostra todos os comprovantes que não puderam ser revertidos junto com o motivo da não reversão. Selecione **OK** para fechar a caixa de diálogo.

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a>Revertendo comprovantes da lista de transações de comprovante. 

Você também pode reverter comprovantes da **Lista de transações de comprovante** em todos os sub-razões. Além disso, é possível reverter mais de um comprovante por vez. 

Para reverter um ou vários comprovantes: 

- Selecione o menu **Reverter** na parte superior da página
- Você verá o número total de comprovantes e linhas de comprovante, além da quantidade total de linhas que estão sendo revertidas.
- Selecione **Sim** para usar as datas de transação existentes ou **Não** para inserir uma nova. Em alguns casos, o período da transação original pode ser fechado e você deve inserir uma nova data de transação para revertê-lo.
- Caso selecione **Não**, insira uma data de transação para a reversão. 
- Insira um comentário para descrever a transação de reversão.
- Selecione o botão **Reverter**.

As transações serão revertidas. 

Se tiver mais de 100 linhas no comprovante, o processo de reversão será executado usando o processo em lote. É possível examinar os resultados exibindo os comentários no trabalho em lotes. Todas as transações que não puderam ser revertidas serão anotadas no histórico do trabalho em lotes.

Se o número de linhas do comprovantes for 100 ou menos, o processo de reversão será executado imediatamente. Os resultados serão exibidos em uma caixa de diálogo que mostra todos os comprovantes que não puderam ser revertidos junto com o motivo. Selecione **OK** para fechar a caixa de diálogo.

As transações podem ser revertidas somente se atenderem às regras de negócio para a reversão. Os pagamentos de fornecedores não podem ser revertidos usando o recurso descrito neste tópico. Os pagamentos de fornecedores devem ser revertidos de acordo com as etapas listadas em [Reverter um pagamento de fornecedor](https://docs.microsoft.com/dynamics365/finance/accounts-payable/reverse-vendor-payment)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]