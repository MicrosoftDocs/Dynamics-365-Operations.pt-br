---
title: Reverter lançamento no diário
description: Este tópico descreve recursos que permitem reverter comprovantes da lista de transações de comprovante ou de diários financeiros.
author: MikeFalkner
manager: AnnBe
ms.date: 08/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a5456e60f1f3cee5f83ac7f725f7e01ba5bd7a1
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248576"
---
# <a name="reverse-journal-posting"></a>Reverter lançamento no diário

[!include [banner](../includes/banner.md)]

Este tópico descreve recursos do Microsoft Dynamics 365 Finance que permitem reverter um diário inteiro, ou reverter um ou mais comprovantes da lista de transações de comprovante, independentemente da origem. 

## <a name="reversing-journals"></a>Revertendo diários

Você pode reverter linhas de diário individualmente. Com a reversão de lançamento no diário, também é possível reverter um diário financeiro inteiro. Para reverter um diário: 
- Abra o diário financeiro e filtre por diários lançados
- Clique no menu Reverter na parte superior da página
- Você verá o número total de comprovantes e linhas de comprovante, além da quantidade total de linhas que estão sendo revertidas
- Selecione Sim para usar as datas de transação existentes ou Não para inserir uma nova. Em alguns casos, o período da transação original pode ser fechado e você quer inserir uma nova data de transação para a reversão.
- Se selecionou Não, insira uma data de transação para a reversão. 
- Insira um comentário a ser adicionado à transação de reversão
- Clique no botão Reverter

As transações serão revertidas. 

Se o número de linhas do comprovante passar de 100, o processo de reversão será executado usando o processo em lote. É possível examinar os resultados da reversão exibindo os comentários no trabalho em lotes que foi executado. Todas as falhas serão notadas no histórico de trabalho em lotes.

Se o número de linhas do comprovantes for 100 ou menos, o processo de reversão será executado imediatamente. Os resultados serão apresentados em uma caixa de diálogo que mostra todos os comprovantes que não puderam ser revertidos e o motivo da não reversão. Clique em OK para fechar a caixa de diálogo.

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a>Revertendo comprovantes da lista de transações de comprovante. 

Você também pode reverter comprovantes da **Lista de transações de comprovante** em todos os sub-razões. Além disso, é possível reverter mais de um comprovante por vez. 

Para reverter um ou vários comprovantes: 
- Clique no menu Reverter na parte superior da página
- Você verá o número total de comprovantes e linhas de comprovante, além da quantidade total de linhas que estão sendo revertidas
- Selecione Sim para usar as datas de transação existentes ou Não para inserir uma nova. Em alguns casos, o período da transação original pode ser fechado e você quer inserir uma nova data de transação para a reversão.
- Se selecionou Não, insira uma data de transação para a reversão. 
- Insira um comentário a ser adicionado à transação de reversão
- Clique no botão Reverter

As transações serão revertidas. 

Se o número de linhas do comprovante passar de 100, o processo de reversão será executado usando o processo em lote. É possível examinar os resultados da reversão exibindo os comentários no trabalho em lotes que foi executado. Todas as falhas serão notadas no histórico de trabalho em lotes.

Se o número de linhas do comprovantes for 100 ou menos, o processo de reversão será executado imediatamente. Os resultados serão apresentados em uma caixa de diálogo que mostra todos os comprovantes que não puderam ser revertidos e o motivo da não reversão. Clique em OK para fechar a caixa de diálogo.

