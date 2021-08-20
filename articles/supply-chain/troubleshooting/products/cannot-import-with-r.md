---
title: Não é possível importar um item usando a entidade de Produtos liberados V2
description: Não é possível importar um item usando a entidade de Produtos liberados V2.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended, DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: efd773313f89784d8fca6b37d867e204cb2d06ab29694a19cbec7eed107a8019
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6764683"
---
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a>Não é possível importar um item usando a entidade de Produtos liberados V2

Número de KB: 4611825

## <a name="symptoms"></a>Sintomas

Ao tentar importar um item usando a entidade *Produtos liberados V2*, você receberá uma mensagem de erro semelhante ao seguinte exemplo:

> Não é possível criar um registro em Itens - grupos de dimensão de rastreamento (EcoResTrackingDimensionGroupItem). Número do item: 2040663, Lote. O registro já existe.

## <a name="resolution"></a>Resolução

Para importar novos produtos liberados, você deve usar a entidade *Criação de produto liberado V2*, em vez da entidade *Produtos liberados V2*.
