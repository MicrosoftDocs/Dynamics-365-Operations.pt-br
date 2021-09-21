---
title: As distribuições contábeis estão superdistribuídas ou subdistribuídas
description: Uma ou mais distribuições contábeis são superdistribuídas ou subdistribuídas.
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
ms.openlocfilehash: 7ff0172469df50da9e4272b3fa3f75001a4eb7eb
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475578"
---
# <a name="accounting-distributions-are-either-over--or-under-distributed"></a>As distribuições contábeis estão superdistribuídas ou subdistribuídas


## <a name="symptoms"></a>Sintomas

Você recebe o seguinte erro:

> Uma ou mais distribuições contábeis são superdistribuídas ou subdistribuídas

## <a name="cause"></a>Causa

Esse problema pode ocorrer devido a inconsistências nas distribuições da ordem de compra.

## <a name="resolution"></a>Resolução

Para desbloquear esse problema e redefinir a ordem de compra para um estado *Rascunho*, Acesse **Compras e fornecimento \> Tarefas periódicas \> Limpar \> Redefinição de distribuição da ordem de compra**. Para obter mais informações, consulte a seguinte postagem de blog: [Resolver erros de distribuição de OC no Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).
