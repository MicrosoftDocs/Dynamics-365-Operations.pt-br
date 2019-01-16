---
title: Sincronizar lista de projetos do Finance and Operations no Field Service
description: "Este tópico discute os modelos e as tarefas subjacente usados para sincronizar projetos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service."
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
ms.openlocfilehash: adcb1c1b241ce2b073cd26cf2a8a8d64931c8b0f
ms.contentlocale: pt-br
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a>Sincronizar lista de projetos do Finance and Operations no Field Service

[!include[banner](../includes/banner.md)]

Este tópico discute os modelos e as tarefas subjacente usados para sincronizar projetos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.

[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)

## <a name="templates-and-tasks"></a>Modelos e tarefas
O modelo e as tarefas subjacentes a seguir são usados para executar a sincronização de projetos do Microsoft Dynamics 365 for Finance and Operations para o Microsoft Dynamics 365 for Field Service.

**Nome do modelo na Integração de dados:**
- Projetos (Finance and Operations para Field Service)

**Nomes das tarefas no projeto de Integração de dados:**
- Projetos

As seguintes tarefas de sincronização necessárias antes da sincronização a lista de projetos:
- Contas (Sales para o Finance and Operations) 

## <a name="entity-set"></a>Conjunto de entidades
Field Service   Finance and Operations

| Field Service           | Finance and Operations  |
|-------------------------|-------------------------|
|msdynce_externalprojects | Projetos                |

## <a name="entity-flow"></a>Fluxo de entidades
Os projetos são criados no Finance and Operations. Os projetos de tempo e material **Tipo de projeto** e **Estágio de projeto** em andamento serão sincronizados para a entidade **Projeto Externo** no Field Service, incluindo número do projeto, nome do projeto, estágio do projeto e informações da conta do cliente. A lista **Projeto Externo** é usada para emparelhar ordens de trabalho do Field Service com projetos do Finance and Operations.
A solução CRM do Field Service: o projeto externo é uma nova entidade que obtém todos os projetos de operações.
O campo Projeto Externo foi adicionado à entidade de Ordem de Trabalho. Este campo é uma pesquisa e compra que marca sua ordem de trabalho com um projeto. A ordem de venda será conectada a um projeto em operações. Quando o status do sistema mudar de Aberto - Em Andamento (690,970,000) para a um status superior, o campo Projeto Externo será bloqueado e você não poderá adicionar, remover ou alterar o valor.

## <a name="prerequisites-and-mapping-setup"></a>Pré-requisitos e configuração de mapeamento
### <a name="in-finance-and-operations"></a>No Finance and Operations
Habilitar o controle de alterações para projetos da entidade Dados

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados


### <a name="projects-finance-and-operations-to-field-service-projects"></a>Projetos (Finance and Operations para Field Service): Projetos

[![Mapeamento de modelo na Integração de dados](./media/FSProject1.png)](./media/FSProject1.png)

