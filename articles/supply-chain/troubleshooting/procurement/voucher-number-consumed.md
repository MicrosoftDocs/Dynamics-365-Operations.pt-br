---
title: Um número de comprovante de recebimento de produtos é consumido mesmo quando não gera um comprovante
description: Um número de comprovante de recebimento de produtos será consumido mesmo que nenhum comprovante financeiro seja gerado durante o recebimento de produtos
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
ms.openlocfilehash: 0556969950c45e80d177a0e96096c4157d690ae3
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475574"
---
# <a name="a-product-receipt-voucher-number-is-consumed-even-when-not-generating-a-voucher"></a>Um número de comprovante de recebimento de produtos é consumido mesmo quando não gera um comprovante

## <a name="symptoms"></a>Sintomas

Um número de comprovante de recebimento de produtos será consumido mesmo que nenhum comprovante financeiro seja gerado durante o recebimento de produtos.

## <a name="resolution"></a>Resolução

Se a opção **Acumular passivo no recebimento de produtos** estiver definida como *Não* para o grupo de modelos de item, não ocorrerá lançamentos na contabilidade. No entanto, um evento físico será registrado para a finalidade de contabilização em um diário-razão e esse evento exigirá um número de comprovante. Esse número de comprovante é o número de comprovante referido nas transações de estoque.

Recomendamos definir a opção **Acumular passivo no recebimento de produtos** como *Sim*, conforme descrito na seguinte postagem no blog: [Lançar encargos diversos no momento do recebimento do produto](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).
