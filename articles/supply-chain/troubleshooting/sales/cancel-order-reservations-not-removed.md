---
title: Não é possível remover as reservas ao cancelar uma ordem
description: Não será possível cancelar a ordem de venda até que o trabalho associado a ela seja cancelado e revertido. Para isso, siga estas três etapas.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a8d947e64568246dba5eff3c21fd3920b6494b73
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475591"
---
# <a name="reservations-cannot-be-removed-when-canceling-an-order"></a>Não é possível remover as reservas ao cancelar uma ordem

## <a name="symptoms"></a>Sintomas

Se o trabalho estiver associado a uma ordem de venda e você tentar cancelá-la, a seguinte mensagem de erro será exibida:

> As reservas não podem ser removidas porque há um trabalho criado com base nas reservas.

Não será possível cancelar a ordem de venda até que o trabalho seja cancelado e revertido. Esse requisito se aplica mesmo que o trabalho associado à ordem de venda seja fechado.

## <a name="resolution"></a>Resolução

Para corrigir esse problema, siga estas etapas:

1. Cancele o trabalho e coloque o estoque novamente no local desejado. Acesse o carregamento relevante da ordem de venda e selecione **Reduzir quantidade separada** na linha de carga ou **Reverter trabalho** no Painel de Ações.

    O trabalho agora tem um status *Cancelado* e o novo trabalho de movimentação de estoque é criado automaticamente e processado para colocar o estoque de volta ao local descrito no momento da reversão.

2. Excluir a carga. A remessa também será excluída.

3. Agora, você poderá ir para a ordem de venda e cancelá-la.
