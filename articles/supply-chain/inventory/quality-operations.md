---
title: Operações para não conformidades
description: Este tópico descreve como criar e usar operações para não conformidades.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestOperations, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 35619454af8b1cb1b7d383d393362f58d9dd0ea6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573864"
---
# <a name="operations-for-nonconformances"></a>Operações para não conformidades

[!include [banner](../includes/banner.md)]

Este tópico descreve como criar e usar operações para não conformidades.

Use a página **Operações** para definir classificações do trabalho que pode ser realizado para uma não conformidade aprovada. Ao atribuir uma operação relacionada a uma não conformidade, é possível fornecer detalhes como o material associado, as horas de trabalho e os encargos necessários para executar a operação. O sistema usa essas informações para calcular um custo estimado para a operação. As informações detalhadas e os custos estimados são para referência apenas. As operações relacionadas para qualidade diferem das operações que podem ser definidas para um roteiro de produção.

> [!NOTE]
> Embora seja possível rastrear os custos, o tempo e os itens usados em uma operação relacionada a uma não conformidade, os dados inseridos são apenas informativos. Eles não são integrados automaticamente à contabilidade, ao razão auxiliar de estoque ou ao módulo **Horário e presença**.

## <a name="examples-of-operations"></a>Exemplos de operações

Você trabalha para uma empresa de fabricação. Uma não conformidade foi criada e aprovada para itens que foram reprovados em um teste de qualidade. Uma correção foi criada para indicar que o problema estava relacionado a um rolamento danificado em uma máquina. Várias etapas são necessárias para substituir o rolamento, e a responsabilidade por cada operação é rastreada. Por exemplo, as seguintes etapas podem ser necessárias:

1. A linha de produção é interrompida e a rotina de limpeza é executada.
1. A equipe de manutenção substitui o rolamento.
1. A equipe de garantia da qualidade inspeciona a máquina antes de ligá-la novamente.

Neste exemplo, as seguintes operações podem ser criadas para representar o trabalho que deve ser feito:

- Interromper a linha de produção.
- Limpar a linha de produção.
- Realizar a manutenção na máquina.
- Inspecionar a máquina.

## <a name="create-an-operation"></a>Criar uma operação

1. Acesse **Gerenciamento de estoque \> Configuração \> Gerenciamento de qualidade \> Operações**.
1. No Painel de Ação, selecione **Novo** para adicionar uma linha à grade. Defina os seguintes campos para a nova linha:

    - **Operação** – Insira um nome ou uma ID exclusiva para a operação.
    - **Descrição** – Insira uma descrição detalhada da operação.
    - **Tipo** – Se a operação puder ser usada somente com não conformidades relacionadas a um tipo específico de ordem, selecione o tipo de ordem (*Ordem de compra* ou *Ordem de venda*).

1. Feche a página.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral do gerenciamento de qualidade](quality-management-processes.md)
- [Habilitar gerenciamento de qualidade e não conformidade](enable-quality-management.md)
- [Criar e processar não conformidades](tasks/create-process-non-conformance.md)
- [Trabalhadores responsáveis por aprovar não conformidades](quality-responsible-workers.md)
- [Zonas de quarentena para não conformidades](quality-quarantine-zones.md)
- [Tipos de diagnóstico para não conformidades](quality-diagnostic-types.md)
- [Encargos de qualidade para não conformidades](quality-charges.md)
- [Tipos de problema para não conformidades](quality-operations.md)
- [Gerenciamento de qualidade para processos de depósito](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
