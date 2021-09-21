---
title: Não é possível excluir um produto liberado
description: É possível excluir um produto liberado e todas as suas variantes somente se o produto liberado não tiver nenhuma transação relacionada.
author: SmithaNataraj
ms.date: 06/11/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 2f03d45a36401314a4b02ff354fabb474568c48b
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475612"
---
# <a name="you-cant-delete-a-released-product"></a>Não é possível excluir um produto liberado

## <a name="symptoms"></a>Sintomas

É possível excluir um produto liberado e todas as suas variantes somente se o produto liberado não tiver nenhuma transação relacionada.

## <a name="resolution"></a>Resolução

Siga as etapas a seguir para excluir um produto liberado ou produto mestre.

1. Feche todas as transações em aberto para os itens.
1. Reduza o estoque a 0 (zero).
1. Realize o fechamento do estoque.
1. Exclua todas as variantes do produto para o produto mestre que você deseja excluir.
