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
ms.openlocfilehash: ea9044a9008e766c7fc92f98e27cfb91076f5b44
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026281"
---
# <a name="reversal-of-reporting-as-finished-creates-an-unexpected-open-transaction"></a>Reversão de relatório como finalizado cria uma transação em aberto inesperada

Número da base de dados de conhecimento: 4612469

## <a name="symptoms"></a>Sintomas

Se você reverter o relatório como finalizado que tem uma marcação, o sistema criará uma transação em aberto em que a quantidade revertida tem as mesmas dimensões de inventário que a transação que foi revertida.

## <a name="resolution"></a>Resolução

Quando você reverter uma operação relatar-como-finalizado, a dimensão do inventário é inicializada no diário de produção. Portanto, ela obtém o número do lote. Por conta da marcação, as transações de pedido de venda herdará o número de lote.

A dimensão pode ser redefinida quando o relatório como finalizado é postado.
