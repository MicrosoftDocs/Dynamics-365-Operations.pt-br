---
title: O limite máximo do contrato de compra não é efetivo em uma requisição de compra
description: O limite máximo do contrato de compra não é efetivo em uma requisição de compra
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: c19d40dce65acbe80d4572bfc4e925aa87ea4f02
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475558"
---
# <a name="the-purchase-agreement-maximum-limit-isnt-effective-on-a-purchase-requisition"></a>O limite máximo do contrato de compra não é efetivo em uma requisição de compra

## <a name="symptoms"></a>Sintomas

Quando uma requisição de compra estiver vinculada a um contrato de compra, o limite máximo do contrato de compra não será efetivo na requisição de compra. As informações de preço padrão são inseridas corretamente, mas mais do que o limite máximo do contrato de compra pode ser solicitado na requisição de compra.

## <a name="resolution"></a>Resolução

Esse comportamento é esperado. Como as requisições nem sempre são aprovadas, uma quantidade ou um valor não deve ser reservado no contrato de compra. Portanto, você não atenderá ao limite máximo do contrato de compra.
