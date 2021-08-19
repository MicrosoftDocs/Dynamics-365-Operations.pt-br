---
title: Reversão de relatório como finalizado cria uma transação em aberto inesperada
description: A reversão do relatório como finalizado que tem uma marcação cria uma transação em aberto em que a quantidade revertida tem as mesmas dimensões de inventário que a transação revertida.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 73ebc45ee83516f573c3f73ef8106da9ae44c590c05d8dbd08520bc5ef19e49a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6714201"
---
# <a name="reversal-of-reporting-as-finished-creates-an-unexpected-open-transaction"></a>Reversão de relatório como finalizado cria uma transação em aberto inesperada

Número da base de dados de conhecimento: 4612469

## <a name="symptoms"></a>Sintomas

Se você reverter o relatório como finalizado que tem uma marcação, o sistema criará uma transação em aberto em que a quantidade revertida tem as mesmas dimensões de inventário que a transação que foi revertida.

## <a name="resolution"></a>Resolução

Quando você reverter uma operação relatar-como-finalizado, a dimensão do inventário é inicializada no diário de produção. Portanto, ela obtém o número do lote. Por conta da marcação, as transações de pedido de venda herdará o número de lote.

A dimensão pode ser redefinida quando o relatório como finalizado é postado.
