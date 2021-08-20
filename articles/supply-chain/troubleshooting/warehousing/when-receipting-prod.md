---
title: Somente um rótulo é impresso para vários cabeçalhos de trabalho em um único recibo
description: Somente um rótulo é impresso para vários cabeçalhos de trabalho em um único recibo.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: cf307964a07c2b69eb5e4ef2cf9dc094482736d0970e333e84f674c9be6331c7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740518"
---
# <a name="only-one-label-is-printed-for-multiple-work-headers-on-a-single-receipt"></a>Somente um rótulo é impresso para vários cabeçalhos de trabalho em um único recibo

Número de KB: 4614667

## <a name="symptoms"></a>Sintomas

Vários cabeçalhos de trabalho são criados para a mesma placa de licença de destino que parte de um único aplicativo de depósito. No entanto, apenas uma etiqueta da placa de licença é impressa quando o produto é recebido.

## <a name="resolution"></a>Resolução

O sistema está agindo como esperado.

No design atual, uma etiqueta da placa de licença é sempre gerada, independentemente do número de combinações de cabeçalho de trabalho e de linha de trabalho existentes. A etiqueta gerada inclui as informações para apenas uma combinação.

Para resolver esse problema, certifique-se de que a criação do cabeçalho de trabalho seja sempre mapeada para apenas uma placa de licença de destino.
