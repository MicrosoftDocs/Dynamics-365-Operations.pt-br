---
title: Parâmetros de integração do Project Service Automation
description: Este tópico explica a forma de configurar como os dados padrão são inseridos durante a integração do Microsoft Dynamics 365 for Project Service Automation com o Microsoft Dynamics 365 for Finance and Operations.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
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
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: b58d2de323395db97d1f8ea146da55bba4e0f9c6
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838968"
---
# <a name="project-service-automation-integration-parameters"></a>Parâmetros de integração do Project Service Automation

[!include[banner](../includes/banner.md)]

Na página **Parâmetros de integração do Project Service Automation**, você pode configurar como os dados padrão são inseridos durante a integração do Microsoft Dynamics 365 for Project Service Automation com o Microsoft Dynamics 365 for Finance and Operations. Para que projetos sejam sincronizados com êxito do Project Service Automation para o Finance and Operations, é preciso configurar os campos a seguir.

> [!NOTE]
> - A integração de tarefas do projeto, as categorias de transação de despesa, as estimativas de horas, as estimativas de despesas e o bloqueio de funcionalidade estão disponíveis no Microsoft Dynamics 365 for Finance and Operations versão 8.0.
> - A integração de valores reais está disponível no Microsoft Dynamics 365 for Finance and Operations versão 8.0.1 ou posterior.
> - Se estiver usando o Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, após instalar o KB 4132657 e o KB 4132660, você poderá usar os modelos para integrar tarefas de projeto, categorias de transação de despesa, estimativas de horas, estimativas de despesas e números reais e para configurar o bloqueio de funcionalidade. Se você precisar redefinir as distribuições contábeis, é recomendável também instalar o KB 4131710.

| Guia                    | Campo                | descrição |
|------------------------|----------------------|-------------|
| Geral                | Tipo de projeto padrão | Selecione o tipo de projeto padrão. Quando os projetos são sincronizados a partir do Project Service Automation, esse valor é usado se você não forneceu um valor padrão no modelo de integração. Durante a sincronização, o campo **Tipo de projeto** de novos projetos é definido com esse valor. Contudo, o valor pode ser atualizado quando as linhas de contrato do projeto são sincronizadas a partir do Project Service Automation. |
|                        | Categoria de tempo        | Selecione a categoria de tempo padrão. Esse valor é usado quando as estimativas de hora são sincronizadas a partir do Project Service Automation. Quando as estimativas de hora e as horas reais são sincronizadas a partir do Project Service Automation, o campo **Categoria** de novas previsões de horas de projeto do Finance and Operations é definido com esse valor. |
|                        | Categoria da taxa         | Selecione a categoria de taxas padrão. Esse valor é usado quando os valores reais de taxas são sincronizados a partir do Project Service Automation. Quando os valores reais de taxas são sincronizados a partir do Project Service Automation, o campo **Categoria** de novas transações de taxas do Finance and Operations é definido com esse valor. |
| Padrões de grupo de projetos | Tipo de projeto         | Clique em **Novo** para adicionar uma linha na qual você possa selecionar o tipo de projeto para o qual definirá o grupo de projetos padrão. Um tipo de projeto específico pode ser selecionado apenas uma vez na configuração. |
|                        | Grupo de projetos        | Selecione o grupo de projetos padrão para o tipo de projeto selecionado. Quando novos projetos são sincronizados a partir do Project Service Automation, o campo **Grupo de projetos** é definido com o valor padrão para o tipo de projeto se você não forneceu um valor padrão no modelo de integração. |
| Padrões de tipo de cobrança  | Tipo de cobrança         | Clique em **Novo** para adicionar uma linha na qual você possa selecionar o tipo de cobrança para o qual definirá a propriedade de linha padrão. Um tipo de cobrança específico pode ser selecionado apenas uma vez na configuração. |
|                        | Propriedade da linha        | Selecione a propriedade de linha padrão para o tipo de cobrança selecionado. Quando novas previsões de horas, novas previsões de despesas ou os novos valores reais forem sincronizados a partir do Project Service Automation, o campo **Propriedade da linha** é definido com o valor padrão para o tipo de cobrança. |
| Bloqueio de funcionalidade  | Não Aplicável       | Selecione a funcionalidade para desabilitar no Finance and Operations para projetos e contratos originados no Project Service Automation. Por exemplo, você pode desativar a capacidade de editar contratos e projetos, criar estruturas de detalhamento de trabalho e inserir folhas de ponto no Finance and Operations. Os campos relacionados à contabilidade continuarão habilitados, mesmo se a configuração do parâmetro torná-los indisponíveis. Por padrão, todas as funcionalidades estão habilitadas. |
