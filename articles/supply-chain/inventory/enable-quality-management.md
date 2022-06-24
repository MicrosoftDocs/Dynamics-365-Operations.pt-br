---
title: Habilitar gerenciamento de qualidade e não conformidade
description: Este artigo fornece uma visão geral do processo de configuração de recursos de gerenciamento de qualidade e não conformidade no Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome, InventParameters, InventProblemType, InventProblemTypeSetup, InventQuarantineZone, InventTestDiagnosticType, InventTestReportSetup, SysUserManagement, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 66229e3692e87f774c553eae955794330602598c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874033"
---
# <a name="enable-quality-and-nonconformance-management"></a>Habilitar gerenciamento de qualidade e não conformidade

[!include [banner](../includes/banner.md)]

Este artigo fornece uma visão geral do processo de configuração de recursos de gerenciamento de qualidade e não conformidade no Microsoft Dynamics 365 Supply Chain Management.

## <a name="enable-quality-and-nonconformance-management"></a><a name="enable-qm"></a>Habilitar gerenciamento de qualidade e não conformidade

Siga estas etapas para habilitar o gerenciamento de qualidade no sistema.

1. Ir para **Gerenciamento de estoque \> Configuração \> Parâmetros de gerenciamento de depósito e estoque**.
1. Na guia **Gerenciamento de qualidade**, defina a opção **Usar gerenciamento de qualidade** como *Sim*.
1. No campo **Preço por hora**, insira um preço de mão de obra por hora na moeda local. O preço por hora é usado para calcular o custo de operações relacionadas à não conformidade. O preço por hora e os custos calculados fornecem informações de referência para uma não conformidade. Eles não interagem com outra funcionalidade.
1. Selecione **Configuração de relatório**.
1. Adicione novas linhas para os vários tipos de relatório e selecione o tipo de documento a ser usado para cada relatório.
1. Feche a página.
1. Feche a página.

## <a name="quality-management-configuration-process"></a>Processo de configuração de gerenciamento de qualidade

Antes de começar a usar os recursos de gerenciamento de qualidade e gerar ordens de qualidade, você deve configurar o sistema e os pré-requisitos. Esta é uma lista das etapas necessárias para configurar o gerenciamento de qualidade.

1. [Habilitar gerenciamento de qualidade e não conformidade](#enable-qm).
1. Opcional: [Configurar instrumentos de teste](quality-test-instruments.md).
1. [Configurar testes](quality-tests.md).
1. [Configurar variáveis e resultados de teste](quality-test-variables.md).
1. [Configurar grupos de teste](quality-test-groups.md).
1. Opcional: [Configurar grupos de qualidade e vincular a produtos](quality-groups.md).
1. Opcional: [Configurar associações de qualidade](quality-associations.md).

Depois de concluída a configuração, você pode começar a criar e processar ordens de qualidade. Para obter mais informações sobre como criar e trabalhar com ordens de qualidade, consulte [Ordens de qualidade](quality-orders.md).

## <a name="nonconformance-management-configuration-process"></a>Processo de configuração de gerenciamento de não conformidade

Antes de começar a usar os recursos de gerenciamento de não conformidade e gerar não conformidades, você deve configurar o sistema e os pré-requisitos. Esta é uma lista das etapas necessárias para configurar o gerenciamento de não conformidade.

1. [Habilitar gerenciamento de qualidade e não conformidade](#enable-qm).
1. [Configurar trabalhadores que são responsáveis por aprovar não conformidades](quality-responsible-workers.md).
1. [Configurar tipos de problema](quality-problem-types.md).
1. [Configurar zonas de quarentena](quality-quarantine-zones.md).
1. [Configurar tipos de diagnóstico](quality-diagnostic-types.md).
1. [Configurar operações](quality-operations.md).
1. Opcional: [Configurar encargos de qualidade](quality-charges.md).

Depois de concluída a configuração, você pode começar a criar e processar não conformidades. Para obter mais informações sobre como criar e trabalhar com não conformidades, consulte [Criar e processar não conformidades](tasks/create-process-non-conformance.md).

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral do gerenciamento de qualidade](quality-management-processes.md)
- [Habilitar gerenciamento de qualidade e não conformidade](enable-quality-management.md)
- [Gerenciamento de qualidade para processos de depósito](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
