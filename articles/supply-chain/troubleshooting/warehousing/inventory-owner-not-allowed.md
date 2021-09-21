---
title: O proprietário do estoque não é permitido durante o processamento de movimentos
description: Você pode receber o erro "O proprietário de estoque %1 não é permitido". Os processos de gerenciamento de depósito oferecem suporte apenas ao estoque de propriedade da entidade legal.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4ee29cfc7bad990cd1ee5deaa98fca217af772ed
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475556"
---
# <a name="inventory-owner-not-allowed-when-processing-movements-in-the-warehouse-app"></a>O proprietário do estoque não é permitido durante o processamento de movimentos no aplicativo de depósito

## <a name="symptoms"></a>Sintomas

Ao processar movimentos no aplicativo móvel Warehouse Management, você pode receber a seguinte mensagem de erro:

> O proprietário de estoque %1 não é permitido neste processo.

## <a name="cause"></a>Causa

Isso ocorre porque a dimensão de rastreamento do **Proprietário** está ausente quando o aplicativo móvel Warehouse Management é usado para fazer movimentos. Um diário regular de transferência de estoque do cliente do Supply Chain Management parece funcionar conforme o esperado e pode ser lançado apenas se a dimensão do **Proprietário** for preenchida.

## <a name="resolution"></a>Resolução

A Microsoft avaliou esse problema e determinou que é uma limitação de recurso. Atualmente, os processos de gerenciamento de depósito oferecem suporte apenas ao estoque de propriedade da entidade legal.
