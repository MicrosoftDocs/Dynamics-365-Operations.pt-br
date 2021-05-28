---
title: Não é possível atualizar o custo unitário previsto ao importar registros de previsão de demanda
description: Quando você usa entidades de dados para importar registros de previsão de demanda, o preço de custo para registros existentes não atualiza para que continue correspondendo aos dados importados.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: c8ea8322a6c7bafe2dfcaaee3e9989f753c85e2a
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026273"
---
# <a name="you-cant-update-the-forecasted-unit-cost-when-you-import-demand-forecast-records"></a>Não é possível atualizar o custo unitário previsto ao importar registros de previsão de demanda

Número de KB: 4614109

## <a name="symptoms"></a>Sintomas

Quando você usa entidades de dados para importar registros de previsão de demanda, o valor do **Custo unitário previsto** para registros existentes não atualiza para que continue correspondendo aos dados importados.

## <a name="cause"></a>Causa

**Custo unitário previsto** é um campo somente leitura. O valor se baseia no custo unitário do produto e não pode ser definido diretamente por meio da importação.

## <a name="resolution"></a>Resolução

Como o campo é somente leitura, não é possível importar valores para ele. O valor será calculado de acordo com a lógica comercial existente.
