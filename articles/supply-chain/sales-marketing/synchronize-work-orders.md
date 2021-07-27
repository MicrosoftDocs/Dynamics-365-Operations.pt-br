---
title: Sincronizar ordens de serviço com projetos do Field Service com o Supply Chain Management
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar ordens de trabalho com um número de projeto do Dynamics 365 Field Service para o Dynamics 365 Supply Chain Management.
author: ChristianRytt
ms.date: 03/12/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: a641789adf27e51b7a3f8ab03269cc2e748eef96
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6359802"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-supply-chain-management"></a>Sincronizar ordens de serviço com projetos do Field Service com o Supply Chain Management

[!include[banner](../includes/banner.md)]

Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar ordens de trabalho com um número de projeto do Dynamics 365 Field Service para o Dynamics 365 Supply Chain Management.

[![Sincronização de processos empresariais entre o Supply Chain Management e o Field Service.](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)

O modelo **Ordens de serviço com projeto (Field Service para Supply Chain Management)** usado é baseado no modelo **Ordens de serviço (Field Service para Supply Chain Management)**. Para obter mais informações, consulte [Sincronizar ordens de serviço no Field Service com ordens de venda no Supply Chain Management](/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

Este tópico descreve apenas as diferenças entre os dois métodos:
- **Ordens de serviço com projeto (Field Service para Supply Chain Management)**
- **Ordens de serviço (Field Service para Supply Chain Management)**

A principal diferença é que este modelo inclui mapeamento do número de projeto atribuído à ordem de serviço no Field Service, garantindo que a ordem de venda criada no Supply Chain Management inclua o número de projeto e que o faturamento possa ocorrer no projeto relacionado. Além disso, este método utiliza Filtragem e consulta avançada.

## <a name="templates-and-tasks"></a>Modelos e tarefas

**Nome do modelo na Integração de dados:**

- Ordens de serviço com projeto (Field Service para Supply Chain Management)

**Nome da tarefa no projeto de Integração de dados:**

- WorkOrderHeader
- WorkOrderHeaderProject
- WorkOrderProduct
- WorkOrderService

## <a name="field-service-crm-solution"></a>Solução Field Service CRM
O campo **Projeto Externo** foi adicionado à entidade Ordem de Trabalho. Este campo é uma pesquisa e compra que marca sua ordem de serviço com um projeto. A ordem de venda será conectada a um projeto no Supply Chain Management. Quando o **Status do Sistema** mudar de Aberto - Em Andamento (690.970.000) para um status superior, o campo **Projeto Externo** será bloqueado, e você não poderá adicionar, remover ou alterar o valor.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheader"></a>Ordens de serviço com projeto (Field Service para Supply Chain Management): WorkOrderHeader

[![Mapeamento de modelo na Integração de dados.](./media/FSWOP1.png)](./media/FSWOP1.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheaderproject"></a>Ordens de serviço com projeto (Field Service para Supply Chain Management): WorkOrderHeaderProject

[![Mapeamento de modelo na Integração de dados.](./media/FSWOP2.png)](./media/FSWOP2.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderproduct"></a>Ordens de serviço com projeto (Field Service para Supply Chain Management): WorkOrderProduct

[![Mapeamento de modelo na Integração de dados.](./media/FSWOP3.png)](./media/FSWOP3.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderservice"></a>Ordens de serviço com projeto (Field Service para Supply Chain Management): WorkOrderService

[![Mapeamento de modelo na Integração de dados.](./media/FSWOP4.png)](./media/FSWOP4.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]