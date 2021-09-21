---
title: As ordens de compra não refletem as configurações de idioma da entidade legal
description: O nome do produto em uma ordem de compra é mostrado no idioma do sistema, e não no idioma definido para a entidade legal na qual a ordem de compra foi criada
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
ms.openlocfilehash: 4deec493b5480dc570ac82876243bc31a2ae87aa
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475569"
---
# <a name="purchase-orders-dont-reflect-the-language-settings-of-the-legal-entity"></a>As ordens de compra não refletem as configurações de idioma da entidade legal


## <a name="symptoms"></a>Sintomas

O nome do produto em uma ordem de compra é mostrado no idioma do sistema, e não no idioma definido para a entidade legal na qual a ordem de compra foi criada.

## <a name="reproduce-the-issue"></a>Reproduzir o problema

O seguinte procedimento mostra uma forma de reproduzir o problema.

1. Defina o idioma do sistema como *EN-US* (Inglês dos EUA).
1. Verifique se há um produto no qual os idiomas *EN-US* e *DE* (Alemão) são mantidos para traduções do nome do produto.
1. Altere o idioma de uma entidade legal para *DE*.
1. Na entidade legal onde *DE* é definido como o idioma, crie uma ordem de compra que inclua o produto.
1. Observe que o nome do produto ainda é mostrado em inglês dos EUA (o idioma do sistema).

## <a name="resolution"></a>Resolução

Esse comportamento é por design. Nas ordens de compra, o produto sempre é mostrado no idioma do sistema. A linguagem da ordem de compra é usada quando um diário de confirmação é criado.
