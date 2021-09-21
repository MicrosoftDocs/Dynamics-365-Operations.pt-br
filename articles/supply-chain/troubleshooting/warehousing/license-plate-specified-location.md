---
title: A placa de licença deve ser especificada para esta localização
description: Se esse erro for exibido depois de criar uma ordem de transferência para um depósito habilitado para WMS, o campo Local de recebimento padrão está em branco para um depósito de trânsito.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 2e562ad2b41dd149f215adc83bd2d54e55dccc05
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475547"
---
# <a name="license-plate-specification-error-when-confirming-shipment-for-a-transfer-order"></a>Erro de especificação da placa de licença ao confirmar a remessa de uma ordem de transferência

## <a name="symptoms"></a>Sintomas

Se criar uma ordem de transferência usando um depósito habilitado para gerenciamento avançado de depósito (WMS) e, depois tentar confirmar a remessa após o trabalho for concluído, você poderá receber a seguinte mensagem de erro:

> A placa de licença deve ser especificada para esta localização.

## <a name="cause"></a>Causa

Isso ocorre porque o campo **Local de recebimento padrão** está em branco para um depósito de trânsito do depósito "de".

## <a name="resolution"></a>Resolução

Para corrigir esse problema, especifique um local de recebimento padrão no depósito de trânsito. Certifique-se de que esse local seja controlado por placa de licença.
