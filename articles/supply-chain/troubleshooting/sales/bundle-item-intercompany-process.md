---
title: Item de pacote não compatível em um processo intercompanhia
description: O item de pacote não está disponível para compra. A ordem de venda só compra os componentes do item de pacote, e não o próprio item do pacote.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 21adc7d071837b762157364f6f8ed370c69c7fd3
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475582"
---
# <a name="a-bundle-item-isnt-supported-in-an-intercompany-process"></a>Um item de pacote não é compatível em um processo intercompanhia

## <a name="symptoms"></a>Sintomas

O item de pacote não está disponível para a ordem de compra porque, se você examinar as linhas da ordem de venda para o item de pacote, verá que a quantidade é *0* (zero) e o status é *Cancelado*.

## <a name="resolution"></a>Resolução

Esse comportamento é por design. A ordem de venda compra somente os componentes do item de pacote. Ele não compra o próprio item do pacote. Se você precisar comprar um pacote, considere se é necessário marcá-lo como item de pacote porque essa funcionalidade foi criada para cenários de reconhecimento de receita. Para obter mais informações sobre itens do pacote, consulte [Pacotes](/dynamics365/finance/accounts-receivable/revenue-recognition-setup).
