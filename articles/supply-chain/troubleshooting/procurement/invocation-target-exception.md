---
title: Ocorre uma exceção durante o lançamento da fatura de fornecedor
description: Uma exceção "Exceção lançada pelo destino de uma chamada" ocorre durante o lançamento da fatura de fornecedor.
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
ms.openlocfilehash: ecc63cb7d0d2392105d8e4290f8e837945ae0781
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475576"
---
# <a name="an-exception-occurs-during-vendor-invoice-posting"></a>Ocorre uma exceção durante o lançamento da fatura de fornecedor


## <a name="symptoms"></a>Sintomas

Você recebe a seguinte exceção ao lançar uma fatura de fornecedor:

> Exceção lançada pelo destino de uma chamada

## <a name="cause"></a>Causa

Esse problema pode ocorrer devido a inconsistências nas distribuições da ordem de compra.

## <a name="resolution"></a>Resolução

Para desbloquear esse problema e redefinir a ordem de compra para um estado *Rascunho*, Acesse **Compras e fornecimento \> Tarefas periódicas \> Limpar \> Redefinição de distribuição da ordem de compra**. Para obter mais informações, consulte a seguinte postagem de blog: [Resolver erros de distribuição de OC no Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).
