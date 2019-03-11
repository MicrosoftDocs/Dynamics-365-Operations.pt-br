---
title: Sincronizar lista de projetos do Finance and Operations no Field Service
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar projetos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 01/14/2019
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
ms.openlocfilehash: b5aeb4c3925994d7488e8e113e88b9d06ee6b350
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "312499"
---
# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a>Sincronizar lista de projetos do Finance and Operations no Field Service

[!include[banner](../includes/banner.md)]

Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar projetos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.

[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)

## <a name="templates-and-tasks"></a>Modelos e tarefas
O modelo a seguir e as tarefas subjacentes são usados para executar a sincronização de projetos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.

**Modelo na integração de dados**
- Projetos (Finance and Operations para Field Service)

**Tarefas no projeto de integração de dados**
- Projetos

As seguintes tarefas de sincronização necessárias antes da sincronização a lista de projetos:
- Contas (Sales para o Finance and Operations) 

## <a name="entity-set"></a>Conjunto de entidades
| Field Service           | Finance and Operations  |
|-------------------------|-------------------------|
|msdynce_externalprojects | Projetos                |

## <a name="entity-flow"></a>Fluxo de entidades
Os projetos são criados no Finance and Operations. Os projetos com **Tipo de projeto** definido como **Tempo e material** e **Estágio de projeto** definido como **Em andamento** serão sincronizados com a entidade **Projeto Externo** no Field Service, incluindo número do projeto, nome do projeto, estágio do projeto e informações da conta do cliente. A lista **Projeto externo** é usada para emparelhar ordens de trabalho do Field Service com projetos do Finance and Operations.

## <a name="field-service-crm-solution"></a>Solução Field Service CRM
A entidade **Projeto externo** obtém todos os projetos do Finance and Operations. O campo **Projeto externo** foi adicionado à entidade **Ordem de trabalho**. Este é um campo de pesquisa, assim, marcando sua ordem de trabalho com um projeto, a ordem de venda será conectada a um projeto no Finance and Operations. Depois que o **Status do sistema** mudar de **Aberto - Em Andamento (690.970.000)** para a um status superior, o campo **Projeto externo** será bloqueado e você não poderá mais adicionar, remover ou alterar o valor.

## <a name="prerequisites-and-mapping-setup"></a>Pré-requisitos e configuração de mapeamento
### <a name="finance-and-operations"></a>Finance and Operations
Habilitar o controle de alterações para projetos da entidade Dados.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados


### <a name="projects-finance-and-operations-to-field-service-projects"></a>Projetos (Finance and Operations para Field Service): Projetos

[![Mapeamento de modelo na Integração de dados](./media/FSProject1.png)](./media/FSProject1.png)
