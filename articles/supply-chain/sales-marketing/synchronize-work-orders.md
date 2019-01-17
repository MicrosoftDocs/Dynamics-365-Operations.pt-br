---
title: Sincronizar ordens de trabalho do Finance and Operations no Field Service
description: "Este tópico discute os modelos e a tarefa subjacente usados para sincronizar ordens de trabalho com um número de projeto do Microsoft Dynamics 365 for Field Service para o Microsoft Dynamics 365 for Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.translationtype: HT
ms.sourcegitcommit: 8c6cb481f1a3fe48d329c5936118d8df88a4175b
ms.openlocfilehash: f5bd6b8c554688d0d1b2bfd93a34a60a95412bf3
ms.contentlocale: pt-br
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a>Sincronizar ordens de trabalho com um projeto do Field Service para o Finance and Operations

[!include[banner](../includes/banner.md)]

Este tópico discute os modelos e a tarefa subjacente usados para sincronizar ordens de trabalho com um número de projeto do Microsoft Dynamics 365 for Field Service para o Microsoft Dynamics 365 for Finance and Operations.

[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)

O modelo usado **Produtos do Field Service (Finance and Operations para o Field Service)** é baseado no modelo **Produtos (Finance and Operations para o Sales) – Direto** do Prospect to Cash. Para obter mais informações, consulte [Produtos (Finance and Operations para o Sales) – Direto](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).

Este tópico descreve somente as diferenças entre os modelos **Produtos do Field Service (Finance and Operations para Field Service)** e **Produtos do Field Service (Finance and Operations para Field Service)**.

A principal diferença é que este modelo inclui mapeamento do número de projeto atribuído à ordem de trabalho no Field Service, garantindo que a ordem de venda criada no Finance and Operations inclua o número de projeto e que o faturamento possa ocorrer no projeto relacionado. Além disso, este método utiliza Filtragem e consulta avançada.

## <a name="templates-and-tasks"></a>Modelos e tarefas

**Nome do modelo na Integração de dados:**

- Ordens de trabalho com projeto (Field Service para Finance and Operations)

**Nome da tarefa no projeto de Integração de dados:**

- WorkOrderHeader
- WorkOrderHeaderProject
- WorkOrderProduct
- WorkOrderService

## <a name="field-service-crm-solution"></a>Solução Field Service CRM
O campo **Projeto Externo** foi adicionado à entidade Ordem de Trabalho. Este campo é uma pesquisa e compra que marca sua ordem de trabalho com um projeto. A ordem de venda será conectada a um projeto no Finance and Operations. Quando o **Status do Sistema** mudar de Aberto - Em Andamento (690,970,000) para a um status superior, o campo **Projeto Externo** será bloqueado e você não poderá adicionar, remover ou alterar o valor.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheader"></a>Ordens de trabalho com projeto (Field Service para Finance and Operations): WorkOrderHeader

[![Mapeamento de modelo na Integração de dados](./media/FSWOP1.png)](./media/FSWOP1.png)

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheaderproject"></a>Ordens de trabalho com projeto (Field Service para Finance and Operations): WorkOrderHeaderProject

[![Mapeamento de modelo na Integração de dados](./media/FSWOP2.png)](./media/FSWOP2.png)

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderproduct"></a>Ordens de trabalho com projeto (Field Service para Finance and Operations): WorkOrderProduct

[![Mapeamento de modelo na Integração de dados](./media/FSWOP3.png)](./media/FSWOP3.png)

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderservice"></a>Ordens de trabalho com projeto (Field Service para Finance and Operations): WorkOrderService

[![Mapeamento de modelo na Integração de dados](./media/FSWOP4.png)](./media/FSWOP4.png)

