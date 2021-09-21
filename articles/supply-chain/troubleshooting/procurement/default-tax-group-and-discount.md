---
title: O grupo de impostos e o desconto à vista padrão não são preenchidos a partir da conta da fatura
description: Um grupo de impostos padrão e um desconto à vista padrão não são preenchidos a partir da conta da fatura
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
ms.openlocfilehash: bb984eb17209dc92e336df5ad475bb0f70c6e35c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475573"
---
# <a name="default-tax-group-and-cash-discount-arent-filled-in-from-the-invoice-account"></a>O grupo de impostos e o desconto à vista padrão não são preenchidos a partir da conta da fatura

## <a name="symptoms"></a>Sintomas

Se você estiver usando uma conta da fatura diferente da conta do cliente, um grupo de impostos padrão e um desconto à vista padrão não serão preenchidos a partir da conta da fatura quando uma ordem de compra for criada.

## <a name="resolution"></a>Resolução

Esse comportamento é por design. Os valores padrão para o grupo de impostos, descontos à vista e outras informações de preço são baseados na conta do cliente, não na conta da fatura.
