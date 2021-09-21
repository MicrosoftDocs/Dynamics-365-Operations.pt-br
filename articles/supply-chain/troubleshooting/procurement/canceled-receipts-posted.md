---
title: As transações podem ser lançadas em uma conta contábil suspensa
description: Se o recebimento de um produtos for cancelado, o sistema permitirá que as transações sejam lançadas nas contas contábeis suspensas, mesmo que as contas principais sejam suspensas
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
ms.openlocfilehash: 20df0ee4107ad62bec0dd9a683660fe2375a3dd1
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475628"
---
# <a name="transactions-can-be-posted-to-a-suspended-ledger-account"></a>As transações podem ser lançadas em uma conta contábil suspensa

## <a name="symptoms"></a>Sintomas

Se um recebimento de produtos for cancelado, o sistema permitirá que as transações sejam lançadas nas contas contábeis suspensas, mesmo que as contas principais sejam suspensas.

## <a name="reproduce-the-issue"></a>Reproduzir o problema

O seguinte procedimento mostra uma forma de reproduzir o problema.

1. Na página **Parâmetros de contas a pagar**, na guia **Geral**, verifique se a opção **Lançar o recebimento de produtos no razão** está definida como *Sim*.
1. Crie uma ordem de compra e adicione uma linha de ordem que tenha uma quantidade de *1.000* para um produto.
1. Confirme uma ordem de compra.
1. Lance o recebimento de produtos e verifique os comprovantes.
1. Suspenda as contas principais, *200140* e *140200* relevantes.
1. Cancele o recebimento de produtos lançados.
1. Observe que as transações podem ser lançadas nas contas contábeis suspensas.

## <a name="resolution"></a>Resolução

As transações podem ser lançadas nas contas contábeis suspensas quando os recebimentos de produtos forem cancelados, pois esse comportamento permite lançamentos corretos.
