---
title: Encargos para operações de não conformidade
description: Este tópico descreve como criar encargos de qualidade que possam ser usados com operações para uma não conformidade.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestMiscCharges
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2c062fecea23017e603c55d11de542942576dba74e0dda07452fd7a91109fe78
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6771482"
---
# <a name="charges-for-nonconformance-operations"></a>Encargos para operações de não conformidade

[!include [banner](../includes/banner.md)]

Este tópico descreve como criar encargos de qualidade que possam ser usados com operações para uma não conformidade.

Use a página **Encargos de qualidade** para definir os tipos de encargos que podem ser adicionados a operações para uma não conformidade. Os encargos permitem acompanhar detalhes sobre taxas ou encargos que você deve a um cliente por produtos que não estão em conformidade ou que um fornecedor deve a você por produtos que não estão em conformidade recebidos. Você também pode usar encargos para rastrear os custos necessários para que fornecedores ou serviços externos executem uma operação.

## <a name="examples-of-quality-charges"></a>Exemplos de encargos de qualidade

Você trabalha para uma empresa de fabricação. Sua empresa tem contratos com vários fornecedores. Esses contratos descrevem os padrões de remessa no prazo, danos e qualidade de produto para itens. Da mesma forma, vários clientes têm contratos com a sua empresa sobre devoluções, danos e qualidade de produto.

Uma estrutura de taxa é definida para cada circunstância e especificada no contrato. Você pode configurar os encargos de qualidade para destacar os vários tipos de encargos, como *Danos*, *Remessa atrasada* e *Qualidade*. Em seguida, ao criar uma não conformidade, adicione uma ou mais operações. Para cada operação, selecione **Encargos** para definir os detalhes sobre as taxas.

## <a name="create-a-quality-charge"></a>Criar um encargo de qualidade

1. Acesse **Gerenciamento de estoque \> Configuração \> Gerenciamento de qualidade \> Encargos de qualidade**.
1. No Painel de Ação, selecione **Novo** para adicionar uma linha à grade. Defina os seguintes campos para a nova linha:

    - **Código de encargos** – Insira um nome ou uma ID exclusiva para o encargo de qualidade.
    - **Descrição** – Insira uma descrição detalhada do encargo de qualidade.

1. Feche a página.

## <a name="add-a-quality-charge-to-an-operation-for-a-nonconformance"></a>Adicionar um encargo de qualidade a uma operação para uma não conformidade

Para obter detalhes sobre como adicionar operações a uma não conformidade e aplicar encargos a elas, consulte [Operações para não conformidades](quality-operations.md).

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral do gerenciamento de qualidade](quality-management-processes.md)
- [Habilitar gerenciamento de qualidade e não conformidade](enable-quality-management.md)
- [Trabalhadores responsáveis por aprovar não conformidades](quality-responsible-workers.md)
- [Zonas de quarentena para não conformidades](quality-quarantine-zones.md)
- [Tipos de diagnóstico para não conformidades](quality-diagnostic-types.md)
- [Encargos de qualidade para não conformidades](quality-charges.md)
- [Operações para não conformidades](quality-operations.md)
- [Gerenciamento de qualidade para processos de depósito](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
