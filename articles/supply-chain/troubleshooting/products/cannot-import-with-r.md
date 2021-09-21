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
ms.openlocfilehash: bf6eb0eb755de3f2842c235946bfd7ccad04ccf7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7474715"
---
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a>Não é possível importar um item usando a entidade de Produtos liberados V2

Número de KB: 4611825

## <a name="symptoms"></a>Sintomas

Ao tentar importar um item usando a entidade *Produtos liberados V2*, você receberá uma mensagem de erro semelhante ao seguinte exemplo:

> Não é possível criar um registro em Itens - grupos de dimensão de rastreamento (EcoResTrackingDimensionGroupItem). Número do item: 2040663, Lote. O registro já existe.

## <a name="resolution"></a>Resolução

Para importar novos produtos liberados, você deve usar a entidade *Criação de produto liberado V2*, em vez da entidade *Produtos liberados V2*.
