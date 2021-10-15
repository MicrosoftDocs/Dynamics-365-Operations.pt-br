---
title: Tipos de diagnóstico para não conformidades
description: Este tópico descreve como usar e criar tipos de diagnóstico que possam ser usados com não conformidades.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestDiagnosticType, InventTestCorrection
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: edaa3a8b5c6446f039f33589166d832dcd9d0b9a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580927"
---
# <a name="diagnostic-types-for-nonconformances"></a>Tipos de diagnóstico para não conformidades

[!include [banner](../includes/banner.md)]

Este tópico descreve como usar e criar tipos de diagnóstico que possam ser usados com não conformidades.

Use a página **Tipos de diagnóstico** para definir uma classificação de ações de diagnóstico. Em seguida, ao criar uma correção para uma não conformidade, selecione um diagnóstico. Uma correção especifica o tipo de ação de diagnóstico que deve ser tomada para uma não conformidade aprovada e quem deve realizar essa ação. Ela também especifica a data de conclusão solicitada e a data de conclusão planejada.

## <a name="examples-of-diagnostic-types"></a>Exemplos de tipos de diagnóstico

Você trabalha para uma empresa de fabricação e vários itens foram reprovados nos testes de qualidade. Esses itens são movidos para uma área de quarentena e marcados como produtos que não estão em conformidade. Um registro de não conformidade é criado no Microsoft Dynamics 365 Supply Chain Management para acompanhar os detalhes durante a resolução de problemas.

Nesse caso, os problemas de qualidade estão ocorrendo porque rolamentos na máquina que empacota os itens foram danificados e estão superaquecendo. A correção desse problema é substituir as peças na máquina.

Ao configurar os tipos de diagnóstico, você pode criar vários registros, cada um deles representando um tipo diferente de problema que a máquina pode ter. Como alternativa, você pode criar um tipo de diagnóstico genérico que represente o reparo da máquina.

## <a name="create-a-diagnostic-type"></a>Criar um tipo de diagnóstico

1. Acesse **Gerenciamento de estoque \> Configuração \> Gerenciamento de qualidade \> Tipos de diagnóstico**.
1. No Painel de Ação, selecione **Novo** para adicionar uma linha à grade. Defina os seguintes campos para a nova linha:

    - **Diagnóstico** – Insira um nome ou uma ID exclusiva para o tipo de diagnóstico.
    - **Descrição** – Insira uma descrição detalhada do tipo de diagnóstico.

1. Feche a página.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral do gerenciamento de qualidade](quality-management-processes.md)
- [Habilitar gerenciamento de qualidade e não conformidade](enable-quality-management.md)
- [Trabalhadores responsáveis por aprovar não conformidades](quality-responsible-workers.md)
- [Zonas de quarentena para não conformidades](quality-quarantine-zones.md)
- [Tipos de problema para não conformidades](quality-problem-types.md)
- [Encargos de qualidade para não conformidades](quality-charges.md)
- [Operações para não conformidades](quality-operations.md)
- [Gerenciamento de qualidade para processos de depósito](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
