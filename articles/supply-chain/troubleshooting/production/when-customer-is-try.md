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
ms.openlocfilehash: 71977a04adb066a8b51c9bf7b8c5a4e752ca902e
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026254"
---
# <a name="batch-number-is-cleared-when-a-new-lot-id-is-selected"></a>O número do lote é apagado quando um novo ID do lote é selecionado

Número de KB: 4613107

## <a name="symptoms"></a>Sintomas

Quando estiver analisando uma linha do diário da lista de separação, o valor no campo **Número de lote** será apagado se você selecionar um novo valor no campo **ID do lote**.

## <a name="resolution"></a>Resolução

O sistema está agindo como esperado. Se você alterar o ID do lote, altere o contexto do item. Assim, o número do lote será redefinido.

Para associar o número de lote a um ID do lote, você deve definir primeiro o ID do lote.
