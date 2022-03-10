---
title: O número do lote é apagado quando um novo ID do lote é selecionado
description: Quando estiver analisando uma linha do diário da lista de separação, o valor no campo "Número de lote" será apagado se você selecionar um novo valor no campo "ID do lote".
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdJournalTransBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: datra
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6d71720b1d3a34a31639db0f829dee300d6f96d53fd61c0a8740be9f2306d6dd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738810"
---
# <a name="batch-number-is-cleared-when-a-new-lot-id-is-selected"></a>O número do lote é apagado quando um novo ID do lote é selecionado

Número de KB: 4613107

## <a name="symptoms"></a>Sintomas

Quando estiver analisando uma linha do diário da lista de separação, o valor no campo **Número de lote** será apagado se você selecionar um novo valor no campo **ID do lote**.

## <a name="resolution"></a>Resolução

O sistema está agindo como esperado. Se você alterar o ID do lote, altere o contexto do item. Assim, o número do lote será redefinido.

Para associar o número de lote a um ID do lote, você deve definir primeiro o ID do lote.
