---
title: Regras de alocação do razão
description: Este artigo oferece informações gerais sobre as regras de alocação do razão. Ele descreve os diversos componentes dessas regras de alocação e os métodos de alocação que podem ser usados para eles.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAllocation, LedgerAllocationBasisRule, LedgerAllocationRequest, LedgerAllocationRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 15402
ms.assetid: 8147e148-7c11-45ef-95c6-f9889a875b54
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 42896fc8b204df921f1e24797098472eca090d30
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440400"
---
# <a name="ledger-allocation-rules"></a>Regras de alocação do razão

[!include [banner](../includes/banner.md)]

Este artigo oferece informações gerais sobre as regras de alocação do razão. Ele descreve os diversos componentes dessas regras de alocação e os métodos de alocação que podem ser usados para eles.

As regras de alocação do razão são usadas para calcular e gerar automaticamente os diários de alocação e entradas de conta da alocação dos saldos ou valores fixos do razão. Os métodos de alocação podem ser fixos ou variáveis. Os seguintes métodos de alocação podem ser usados para regras de alocação do razão:

-   **Base** – Este método de variável é usado quando a alocação depende do saldo real do razão, com base em critérios de filtragem. Por exemplo, as despesas publicitárias podem ser alocadas com base nas vendas de cada departamento em relação ao total das vendas departamentais.
-   **Percentual fixo** e **Peso fixo** – Para esses métodos, a porcentagem ou peso de alocação é definido diretamente para a regra. Por exemplo, as despesas publicitárias podem ser alocadas, de forma que o Departamento A receba 70 por cento de despesas publicitárias e o Departamento B receba 30 por cento.
-   **Igualmente** – Este método rateia o valor igualmente a cada meta definida. Por exemplo, se os destinos forem definidos para o departamento A e o Departamento B, as despesas publicitárias pode ser alocadas, de forma que o Departamento A e o Departamento B receba 50 por cento de despesas publicitárias.

Se a Base for usada como o método de alocação de uma regra de alocação você também deverá definir uma regras base de alocação do razão à parte. O processo "Solicitação de alocação do processo" permite que os usuários processem a regra de alocação do razão e exiba as entradas de diário de alocação resultantes antes de lançar ou excluir as alocações calculadas.

## <a name="components-of-ledger-allocation-rules"></a>Componentes de regras de alocação do razão
Cada regra de alocação possui quatro componentes: geral, origem, destino e compensação. Um componente adicional, regras básicas de alocação do razão, é necessário se a Base for usada como o método de alocação. Cada componente fornece as informações críticas necessárias para processar as alocações.

-   **Geral** – Este componente é onde o usuário especifica opções, como o método de alocação, configurações de regras intercompanhia e se a regra está ativa.
-   **Origem** – Esse componente é onde o usuário especifica os dados de origem da alocação. A alocação pode ser feita com base nos saldos do razão (**Fonte de dados** = **Razão**) ou valores fixos (**Fonte de dados** = **Valor fixo**). Quando a **Fonte de dados** estiver definida como **Razão**, os critérios de filtragem de origem devem ser definidos para a regra de alocação do razão (por exemplo, para as despesas publicitárias).
-   **Destino** – Esse componente define como o resultado do cálculo de alocação deve ser distribuído e contabilizado. Por exemplo, pode haver uma linha de destino para cada departamento.
-   **Compensação** – Esse componente define como as contas principais e as dimensões devem ser determinadas para as entradas de compensação que equilibram as entradas de destino. As opções definidas pelo usuário normalmente são usadas no lugar das contas e dimensões baseadas na origem. Quando a **Fonte de dados** for definida como **Valor fixo**, a **Origem** não poderá ser usada como padrão.
-   **Regras de base de alocação do razão** – Essas regras usam seus próprios critérios de filtragem de origem para determinar quais saldos do razão devem ser usados para a alocação (por exemplo, a receita por departamento.) Cada regra básica de alocação pode ser usada com várias regras de alocação.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]