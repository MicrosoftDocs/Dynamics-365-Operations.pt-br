---
title: Não é possível consolidar vários recebimentos de produtos em uma única ordem de compra
description: Não é possível consolidar vários recebimentos de produtos em uma única ordem de compra, se as diferentes linhas de recebimento de produtos tiverem datas contábeis diferentes.
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
ms.openlocfilehash: 485306279281ceb55a140526f4216af35574af42
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475549"
---
# <a name="you-cant-consolidate-multiple-product-receipts-into-a-single-purchase-order"></a>Não é possível consolidar vários recebimentos de produtos em uma única ordem de compra

## <a name="symptoms"></a>Sintomas

Não é possível consolidar vários recebimentos de produtos em uma única ordem de compra, se as diferentes linhas de recebimento de produtos tiverem datas contábeis diferentes.

## <a name="resolution"></a>Resolução

Em versões anteriores do Dynamics 365 Supply Chain Management, a consolidação foi permitida nessa situação. No entanto, a prática está sujeita a erros. A data contábil nas linhas da ordem de compra criadas não deve diferir da data contábil nas linhas de recebimento de produtos das quais as linhas da ordem de compra foram criadas. (A data contábil nas linhas da ordem de compra corresponde à data contábil no cabeçalho da ordem de compra.) Portanto, a consolidação de vários recebimentos de produtos em uma única ordem de compra não é mais permitida.

A data contábil é usada, por exemplo, para reservas e ônus de orçamento. Portanto, ele deve ser mantido durante a transição do recebimento de produtos para a ordem de compra.
