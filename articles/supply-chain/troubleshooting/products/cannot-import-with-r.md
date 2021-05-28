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
ms.openlocfilehash: 8182f2f83f6a3e4cf54fe6fa64b25a2f461ff541
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026261"
---
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a>Não é possível importar um item usando a entidade de Produtos liberados V2

Número de KB: 4611825

## <a name="symptoms"></a>Sintomas

Ao tentar importar um item usando a entidade *Produtos liberados V2*, você receberá uma mensagem de erro semelhante ao seguinte exemplo:

> Não é possível criar um registro em Itens - grupos de dimensão de rastreamento (EcoResTrackingDimensionGroupItem). Número do item: 2040663, Lote. O registro já existe.

## <a name="resolution"></a>Resolução

Para importar novos produtos liberados, você deve usar a entidade *Criação de produto liberado V2*, em vez da entidade *Produtos liberados V2*.
