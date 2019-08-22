---
title: Project Service Automation
description: Este tópico fornece informações sobre a solução de integração do Project Service Automation para o Finance and Operations. Esta solução de integração usa o recurso Integração de dados para sincronizar dados em instâncias do Microsoft Dynamics 365 for Finance and Operations e do Microsoft Dynamics 365 for Project Service Automation por meio do Common Data Service.
author: KimANelson
manager: AnnBe
ms.date: 06/29/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c1d6d0b219666bb31cf08da580c701f93d08389a
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2019
ms.locfileid: "1741213"
---
# <a name="project-service-automation"></a>Project Service Automation

[!include[banner](../includes/banner.md)]

A solução de integração do Project Service Automation para o Finance and Operations usa o recurso Integração de dados para sincronizar dados em instâncias do Microsoft Dynamics 365 for Finance and Operations e do Microsoft Dynamics 365 for Project Service Automation por meio do Common Data Service. Os modelos de integração disponíveis com o recurso Integração de dados permitem o fluxo de projetos, contratos de projeto, linhas de contrato de projeto, marcos de linha do contrato de projeto, tarefas de projeto, categorias de transação de despesa, estimativas de horas e estimativas de despesas do Project Service Automation para o Finance and Operations.

> [!NOTE]
> - Se estiver usando o Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, após instalar o KB 4132657 e o KB 4132660, você poderá usar os modelos para integrar tarefas de projeto, categorias de transação de despesa, estimativas de horas, estimativas de despesas e números reais e para configurar o bloqueio de funcionalidade. Se você precisar redefinir as distribuições contábeis, é recomendável também instalar o KB 4131710.
> - Se estiver usando o Finance and Operations 7.3.0, é preciso instalar o KB 4074835. Isso permitirá que você integre projetos de preço fixo.
> - Se você estiver usando o Finance and Operations 7.3.0 e estiver transferindo as transações de taxa do Project Service Automation, instale o KB 4345320 para incluir essas taxas na fatura do projeto.
> - Se estiver usando o Microsoft Dynamics 365 for Finance and Operations versão 8.0, você poderá usar a integração de tarefas do projeto, as categorias de transação de despesa, as estimativas de horas, as estimativas de despesas e o bloqueio de funcionalidade.
> - Se estiver usando o Microsoft Dynamics 365 for Finance and Operations versão 8.0.1 ou posterior, você poderá sincronizar números reais.

Para integrar o Project Service Automation ao Finance and Operations, configure os parâmetros de integração do Project Service Automation. Para obter mais informações, consulte os [Parâmetros de integração do Project Service Automation](PSA-parameters.md).

Esta solução de integração permite a sincronização direta nos seguintes cenários:

- Manter contratos de projeto no Project Service Automation e sincronizá-los diretamente do Project Service Automation para o Finance and Operations.
- Criar projetos no Project Service Automation e sincronizá-los diretamente do Project Service Automation para o Finance and Operations.
- Manter linhas de contratos do projeto no Project Service Automation e sincronizá-las diretamente do Project Service Automation para o Finance and Operations.
- Manter marcos de linhas de contratos do projeto no Project Service Automation e sincronizá-los diretamente do Project Service Automation para o Finance and Operations.
- Manter tarefas do projeto no Project Service Automation e sincronizá-las diretamente do Project Service Automation para o Finance and Operations.
- Manter categorias de transação de despesas no Finance and Operations e sincronizá-las diretamente do Finance and Operations para o Project Service Automation.
- Criar estimativas de horas do projeto no Project Service Automation e sincronizá-las diretamente do Project Service Automation para o Finance and Operations.
- Criar estimativas de despesas do projeto no Project Service Automation e sincronizá-las diretamente do Project Service Automation para o Finance and Operations.
- Crie hora de projeto, despesa e valores reais de taxas no Project Service Automation, bem como transações do projeto no diário de integração do Project Service Automation para que possam ser publicados no Finance and Operations.

## <a name="data-synchronization"></a>Sincronização de dados

A ilustração a seguir mostra como os dados são sincronizados como parte da integração entre o Project Service Automation e o Finance and Operations.

> [!NOTE]
> Nem todos os modelos estão disponíveis atualmente. Os modelos serão liberados ao serem concluídos.

[![Integração do Project Service Automation com o Finance and Operations](./media/PSA-integration.png)](./media/PSA-integration.png)

## <a name="system-requirements-for-finance-and-operations"></a>Requisitos de sistema para Finance and Operations

Para usar a solução do Project Service Automation para o Finance and Operations, você deve instalar o Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 com a atualização 12 da plataforma ou posterior.

## <a name="system-requirements-for-project-service-automation"></a>Requisitos do sistema para o Project Service Automation

Para usar a solução de integração do Project Service Automation para o Finance and Operations, você deve instalar os seguintes componentes:

- Microsoft Dynamics 365 for Project Service Automation versão 9.0.0.0 ou posterior
- Solução Prospect to cash para o Microsoft Dynamics 365 for Sales, versão 1.14.0.0 (v14) ou posterior.
- O Project Service Automation para a solução Finance and Operations do Microsoft Dynamics 365 for Project Service Automation versão 1.0.0.0 ou posterior

## <a name="install-the-project-service-automation-to-finance-and-operations-integration-solution-in-your-project-service-automation-instance"></a>Instale o Project Service Automation para a solução de integração Finance and Operations na sua instância do Project Service Automation

Baixe a solução de integração do Project Service Automation para o Finance and Operations em [Centro de Download Microsoft](https://www.microsoft.com/download/details.aspx?id=57016) e siga as instruções incluídas na solução.
