---
title: Sincronizar ordens de trabalho com um projeto do Field Service para o Finance and Operations
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar ordens de trabalho com um número de projeto do Microsoft Dynamics 365 for Field Service para o Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 03/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 5ca01b085315d916a18c512af28fc7534ce76ee8
ms.sourcegitcommit: d9ed934a142b88340d268fd2bd3753475a3712b0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2019
ms.locfileid: "836433"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a>Sincronizar ordens de trabalho com um projeto do Field Service para o Finance and Operations

[!include[banner](../includes/banner.md)]

Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar ordens de trabalho com um número de projeto do Microsoft Dynamics 365 for Field Service para o Microsoft Dynamics 365 for Finance and Operations.

[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)

O modelo **Ordens de trabalho com projeto (Field Service para Fin and Ops)** usado é baseado no modelo **Ordens de trabalho (Field Service para Fin and Ops)**. Para obter mais informações, consulte [Sincronizar ordens de trabalho no Field Service com ordens de venda no Finance and Operations](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

Este tópico descreve apenas as diferenças entre os dois métodos:
- **Ordens de trabalho com projeto (Field Service para Fin and Ops)**
- **Ordens de trabalho (Field Service para Fin and Ops)**

A principal diferença é que este modelo inclui mapeamento do número de projeto atribuído à ordem de trabalho no Field Service, garantindo que a ordem de venda criada no Finance and Operations inclua o número de projeto e que o faturamento possa ocorrer no projeto relacionado. Além disso, este método utiliza Filtragem e consulta avançada.

## <a name="templates-and-tasks"></a>Modelos e tarefas

**Nome do modelo na Integração de dados:**

- Ordens de trabalho com projeto (Field Service para Fin and Ops)

**Nome da tarefa no projeto de Integração de dados:**

- WorkOrderHeader
- WorkOrderHeaderProject
- WorkOrderProduct
- WorkOrderService

## <a name="field-service-crm-solution"></a>Solução Field Service CRM
O campo **Projeto Externo** foi adicionado à entidade Ordem de Trabalho. Este campo é uma pesquisa e compra que marca sua ordem de trabalho com um projeto. A ordem de venda será conectada a um projeto no Finance and Operations. Quando o **Status do Sistema** mudar de Aberto - Em Andamento (690.970.000) para a um status superior, o campo **Projeto Externo** será bloqueado e você não poderá adicionar, remover ou alterar o valor.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheader"></a>Ordens de trabalho com projeto (Field Service para Fin and Ops): WorkOrderHeader

[![Mapeamento de modelo na Integração de dados](./media/FSWOP1.png)](./media/FSWOP1.png)

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheaderproject"></a>Ordens de trabalho com projeto (Field Service para Fin and Ops): WorkOrderHeaderProject

[![Mapeamento de modelo na Integração de dados](./media/FSWOP2.png)](./media/FSWOP2.png)

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderproduct"></a>Ordens de trabalho com projeto (Field Service para Fin and Ops): WorkOrderProduct

[![Mapeamento de modelo na Integração de dados](./media/FSWOP3.png)](./media/FSWOP3.png)

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderservice"></a>Ordens de trabalho com projeto (Field Service para Fin and Ops): WorkOrderService

[![Mapeamento de modelo na Integração de dados](./media/FSWOP4.png)](./media/FSWOP4.png)
