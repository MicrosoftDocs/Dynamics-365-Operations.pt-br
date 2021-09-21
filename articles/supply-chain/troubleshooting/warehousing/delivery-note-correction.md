---
title: Não é possível processar a correção da nota de entrega
description: Se tentar corrigir uma nota de entrega depois que ela for lançada, será exibido um erro. Esta página explica como corrigir guias de remessa lançadas para itens habilitados para o WMS.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: bb0d827adff8abd8762bf2de844cad5574628e4b
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475606"
---
# <a name="delivery-note-correction-cant-be-processed"></a>Não é possível processar a correção da nota de entrega

## <a name="symptoms"></a>Sintomas

Depois de postar uma nota de entrega, você não poderá cancelá-la porque o botão **Cancelar** não estará disponível. Você também não poderá corrigir a nota de entrega. Se você tentar, será exibida a seguinte mensagem de erro:

> Não é possível processar a correção da nota de entrega. A nota de entrega contém apenas itens que estão sujeitos a processos de gerenciamento de depósito, uma vez que eles não são compatíveis com a correção de Nota de Entrega.

## <a name="resolution"></a>Resolução

Para corrigir guias de remessa lançadas para itens habilitados para gerenciamento avançado de depósito (WMS), você deve fazer o lançamento da carga, não diretamente usando a ordem.
