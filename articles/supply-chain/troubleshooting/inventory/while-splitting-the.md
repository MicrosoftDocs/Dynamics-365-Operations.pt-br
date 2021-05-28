---
title: Quando uma quantidade em peso variável é dividida, a quantidade mínima é usada em vez da quantidade nominal
description: Quando uma quantidade em peso variável está sendo dividida em lotes, o campo "Selecionar quantidade" usa a quantidade mínima definida para o item, não a quantidade nominal.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 185365ced5c4516d8fcdbdca88794d0078615888
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026278"
---
# <a name="when-a-catch-weight-quantity-is-split-minimum-quantity-is-used-instead-of-nominal-quantity"></a>Quando uma quantidade em peso variável é dividida, a quantidade mínima é usada em vez da quantidade nominal

Número de KB: 4612073

## <a name="symptoms"></a>Sintomas

Quando uma quantidade em peso variável está sendo dividida em lotes, o campo **Selecionar quantidade** usa a quantidade mínima definida para o item, não a quantidade nominal.

## <a name="resolution"></a>Resolução

O sistema está agindo como esperado. O sistema usa a configuração de quantidade mínima de cada item para fazer a seleção.
