---
title: Os administradores de sistema não podem liberar bloqueios de ordem, pois não estão autorizados a fazer isso
description: Os administradores de sistema não podem liberar bloqueios de ordem, pois não estão autorizados a fazer isso.
author: SmithaNataraj
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 0d0fbcc111d77ae1a362984033216f5973e2bc74f2ee95947b662ef60a13d83e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750897"
---
# <a name="system-administrators-cant-clear-order-holds-because-they-arent-authorized"></a>Os administradores de sistema não podem liberar bloqueios de ordem, pois não estão autorizados a fazer isso

Número de KB: 4614642

## <a name="symptoms"></a>Sintomas

Os administradores de sistema não podem liberar bloqueios de ordem de venda, exceto se desempenhar uma função atribuída no código de bloqueio da ordem.

## <a name="resolution"></a>Resolução

O acesso a algumas operações, como a liberação de ordens de venda, é orientado pela definição de uma política corporativa. Os administradores de sistema geralmente não têm permissão para realizar operações desse tipo. 

Na maioria das vezes, a permissão para realizar tarefas específicas é definida por políticas corporativas, e apenas certas pessoas em uma empresa podem realizar aquela tarefa. Os exemplos incluem aprovações resultantes de permissões de fluxo de trabalho e tarefas específicas que surgem por conta de uma configuração de fluxo de trabalho.

Embora nenhum fluxo de trabalho esteja associado a bloqueios de ordem, o princípio é semelhante. Uma função relevante define o grupo específico de pessoas em uma empresa que têm o direito de liberar bloqueios de ordem. Esse direito não deve necessariamente ser concedido a todos os administradores, pois essa abordagem viola a política corporativa definida.
