---
title: Só é possível concluir uma ação de ordem de compra para números de linhas totalmente distribuídos
description: Só é possível concluir uma ação em uma compra depois que o número de linhas for totalmente distribuído
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
ms.openlocfilehash: 1ef2a938a2a17bc2dbf38d09918eabdbccca8a28
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475618"
---
# <a name="you-can-only-complete-a-purchase-order-action-for-fully-distributed-line-numbers"></a>Só é possível concluir uma ação de ordem de compra para números de linhas totalmente distribuídos

## <a name="symptom"></a>Sintoma

Só é possível concluir uma ação em uma compra depois que o número de linhas for totalmente distribuído.

## <a name="cause"></a>Causa

Esse problema pode ocorrer devido a inconsistências nas distribuições da ordem de compra.

## <a name="resolution"></a>Resolução

Para desbloquear esse problema e redefinir a ordem de compra para um estado *Rascunho*, Acesse **Compras e fornecimento \> Tarefas periódicas \> Limpar \> Redefinição de distribuição da ordem de compra**. Para obter mais informações, consulte a seguinte postagem de blog: [Resolver erros de distribuição de OC no Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).
