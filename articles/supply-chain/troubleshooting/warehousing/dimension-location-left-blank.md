---
title: Se o número de série for definido, o local da dimensão não poderá ficar em branco
description: Se esse erro for exibido quando você confirmar uma remessa depois de criar uma ordem de transferência para um item serial, o campo Local de recebimento padrão está em branco.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6f58c72438d5d1d93e59e46525debd65d44d9a76
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475616"
---
# <a name="error-when-confirming-shipment-after-creating-a-transfer-order-for-a-serial-item"></a>Erro ao confirmar a remessa após a criação de uma ordem de transferência para um item serial

## <a name="symptoms"></a>Sintomas

Se você criar uma ordem de transferência para um item de série usando um depósito habilitado para gerenciamento avançado de depósito (WMS) e, depois que o trabalho for concluído, tentar confirmar a remessa, será exibida esta mensagem de erro:

> Se o número de série de dimensão for definido, o local da dimensão não poderá ficar em branco.

## <a name="cause"></a>Causa

Isso ocorre porque o campo **Local de recebimento padrão** está em branco para um depósito de trânsito do depósito "de".

## <a name="resolution"></a>Resolução

Para corrigir esse problema, especifique um local de recebimento padrão no depósito de trânsito. Certifique-se de que esse local seja controlado por placa de licença.
