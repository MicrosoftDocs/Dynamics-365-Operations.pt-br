---
title: Solucionar problemas de reabastecimento de depósito
description: Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com reabastecimento de depósito no Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 8940f729e1115405e8d6e50eccc92d9fffe37f3e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828073"
---
# <a name="troubleshoot-warehouse-replenishment"></a>Solucionar problemas de reabastecimento de depósito

[!include [banner](../includes/banner.md)]

Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com reabastecimento de depósito no Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-work-1-cannot-be-unblocked-because-it-has-unfinished-replenishment-work"></a>Recebo a seguinte mensagem de erro: "Não é possível desbloquear a ID de trabalho %1 porque existe trabalho de reabastecimento não concluído."

### <a name="issue-description"></a>Descrição do problema

O trabalho de separação está bloqueado por causa do trabalho de reabastecimento dependente.

### <a name="issue-resolution"></a>Resolução do problema

Quando você usa o reabastecimento por demanda de ciclo, se um local de separação deve ser reabastecido para atender à demanda da ordem de origem, o sistema cria o trabalho de reabastecimento e o trabalho de separação. Contudo, ele bloqueia o trabalho de separação até que o trabalho de reabastecimento seja concluído. Esse comportamento é intencional, porque o local de separação não terá estoque suficiente a menos que o trabalho de reabastecimento seja concluído. Conclua o trabalho de reabastecimento e processe o trabalho de separação.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]