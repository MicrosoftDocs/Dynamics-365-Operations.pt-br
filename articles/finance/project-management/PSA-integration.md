---
title: Visão geral do Project Service Automation
description: Este tópico fornece informações sobre o Dynamics 365 Project Service Automation para a solução de integração do Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 07/25/2019
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
ms.openlocfilehash: 31d72591041f8d8cc327aa7c6578c15731ba13c5
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250544"
---
# <a name="project-service-automation-overview"></a>Visão geral do Project Service Automation

[!include[banner](../includes/banner.md)]

A solução de integração Project Service Automation para o Finance usa o recurso Integração de dados para sincronizar dados em instâncias do Dynamics 365 Finance e do Dynamics 365 Project Service Automation por meio do Common Data Service. Os modelos de integração disponíveis com o recurso Integração de dados permitem o fluxo de projetos, contratos de projeto, linhas de contrato de projeto, marcos de linha do contrato de projeto, tarefas de projeto, categorias de transação de despesa, estimativas de horas e estimativas de despesas do Project Service Automation para o Finance.

> [!NOTE]
> - Se estiver usando a versão 7.3.0, instale o KB 4074835. Isso permitirá que você integre projetos de preço fixo.
> - Se você estiver usando a versão 7.3.0 e estiver transferindo as transações de taxa do Project Service Automation, instale o KB 4345320 para incluir essas taxas na fatura do projeto.
> - Se estiver usando a versão 8.0, você poderá usar a integração de tarefas do projeto, as categorias de transação de despesa, as estimativas de horas, as estimativas de despesas e o bloqueio de funcionalidade.
> - Se estiver usando a versão 8.0.1 ou posterior, você poderá sincronizar números reais.

Para integrar o Project Service Automation Finance, configure os parâmetros de integração do Project Service Automation. Para obter mais informações, consulte os [Parâmetros de integração do Project Service Automation](PSA-parameters.md).

Esta solução de integração permite a sincronização direta nos seguintes cenários:

- Manter contratos de projeto no Project Service Automation e sincronizá-los diretamente do Project Service Automation para o Finance.
- Criar projetos no Project Service Automation e sincronizá-los diretamente do Project Service Automation para o Finance.
- Manter linhas de contrato de projeto no Project Service Automation e sincronizá-las diretamente do Project Service Automation para o Finance.
- Manter marcos de linha de contrato de projeto no Project Service Automation e sincronizá-los diretamente do Project Service Automation para o Finance.
- Manter tarefas de projeto no Project Service Automation e sincronizá-las diretamente do Project Service Automation para o Finance.
- Manter categorias de transação de despesas no Finance e sincronizá-las diretamente do Finance para o Project Service Automation.
- Criar estimativas de horas do projeto no Project Service Automation e sincronizá-las diretamente do Project Service Automation para o Finance.
- Criar estimativas de despesa do projeto no Project Service Automation e sincronizá-las diretamente do Project Service Automation para o Finance.
- Criar tempo, despesa e valores reais de taxas do projeto no Project Service Automation, bem como transações do projeto no diário de integração do Project Service Automation para que possam ser publicados no Finance.

## <a name="data-synchronization"></a>Sincronização de dados

A ilustração a seguir mostra como os dados são sincronizados como parte da integração entre o Project Service Automation e o Finance.

> [!NOTE]
> Nem todos os modelos estão disponíveis atualmente. Os modelos serão liberados ao serem concluídos.

[![Integração do Project Service Automation ao Finance](./media/PSA-integration.png)](./media/PSA-integration.png)

## <a name="system-requirements-for-finance"></a>Requisitos do sistema para Finance

Para usar a solução de integração Project Service Automation para o Finance, você deve instalar o Enterprise Edition 7.3 com a atualização 12 ou posterior da plataforma.

## <a name="system-requirements-for-project-service-automation"></a>Requisitos do sistema para o Project Service Automation

Para usar a solução de integração Project Service Automation para o Finance, você deve instalar os seguintes componentes:

- Dynamics 365 Project Service Automation versão 9.0.0.0 ou posterior
- Solução Prospect to cash para Dynamics 365 Sales, versão 1.14.0.0 (v14) ou posterior
- A solução Project Service Automation para o Finance do Dynamics 365 Project Service Automation versão 1.0.0.0 ou posterior

## <a name="install-the-project-service-automation-to-finance-integration-solution-in-your-project-service-automation-instance"></a>Instale a solução de integração Project Service Automation para o Finance na sua instância do Project Service Automation

Baixe a solução de integração Project Service Automation para o Finance em [Centro de Download Microsoft](https://www.microsoft.com/download/details.aspx?id=57016) e siga as instruções incluídas na solução.
