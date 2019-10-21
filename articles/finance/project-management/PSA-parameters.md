---
title: Parâmetros de integração do Project Service Automation
description: Este tópico explica a forma de configurar como os dados padrão são inseridos durante a integração do Microsoft Dynamics 365 for Project Service Automation ao Microsoft Dynamics 365 Finance.
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
ms.openlocfilehash: f7cef5384812e0dcb7d5e084ddd7668a7687a259
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174753"
---
# <a name="project-service-automation-integration-parameters"></a>Parâmetros de integração do Project Service Automation

[!include[banner](../includes/banner.md)]

Na página **Parâmetros de integração do Project Service Automation**, você pode configurar como os dados padrão são inseridos durante a integração do Dynamics 365 Project Service Automation com o Dynamics 365 Finance. Para que projetos sejam sincronizados com êxito entre o Project Service Automation e o Finance, é preciso configurar os campos a seguir.

> [!NOTE]
> - A integração de tarefas do projeto, as categorias de transação de despesa, as estimativas de horas, as estimativas de despesas e o bloqueio de funcionalidade estão disponíveis na versão 8.0.
> - A integração de valores reais está disponível na versão 8.0.1 ou posterior.


| Guia                    | Campo                | Descrição |
|------------------------|----------------------|-------------|
| Geral                | Tipo de projeto padrão | Selecione o tipo de projeto padrão. Quando os projetos são sincronizados a partir do Project Service Automation, esse valor é usado se você não forneceu um valor padrão no modelo de integração. Durante a sincronização, o campo **Tipo de projeto** de novos projetos é definido com esse valor. Contudo, o valor pode ser atualizado quando as linhas de contrato do projeto são sincronizadas a partir do Project Service Automation. |
|                        | Categoria de tempo        | Selecione a categoria de tempo padrão. Esse valor é usado quando as estimativas de hora são sincronizadas a partir do Project Service Automation. Quando as estimativas de hora e as horas reais são sincronizadas do Project Service Automation, o campo **Categoria** das novas previsões de horas de projeto do Finance é definido com esse valor. |
|                        | Categoria Taxa         | Selecione a categoria de taxas padrão. Esse valor é usado quando os valores reais de taxas são sincronizados a partir do Project Service Automation. Quando os valores reais de taxas são sincronizados do Project Service Automation, o campo **Categoria** das novas transações de taxas no Finance é definido com esse valor. |
| Padrões de grupo de projetos | Tipo de projeto         | Clique em **Novo** para adicionar uma linha na qual você possa selecionar o tipo de projeto para o qual definirá o grupo de projetos padrão. Um tipo de projeto específico pode ser selecionado apenas uma vez na configuração. |
|                        | Grupo de projetos        | Selecione o grupo de projetos padrão para o tipo de projeto selecionado. Quando novos projetos são sincronizados a partir do Project Service Automation, o campo **Grupo de projetos** é definido com o valor padrão para o tipo de projeto se você não forneceu um valor padrão no modelo de integração. |
| Padrões de tipo de cobrança  | Tipo de cobrança         | Clique em **Novo** para adicionar uma linha na qual você possa selecionar o tipo de cobrança para o qual definirá a propriedade de linha padrão. Um tipo de cobrança específico pode ser selecionado apenas uma vez na configuração. |
|                        | Propriedade da linha        | Selecione a propriedade de linha padrão para o tipo de cobrança selecionado. Quando novas previsões de horas, novas previsões de despesas ou os novos valores reais forem sincronizados a partir do Project Service Automation, o campo **Propriedade da linha** é definido com o valor padrão para o tipo de cobrança. |
| Bloqueio de funcionalidade  | Não aplicável       | Selecione a funcionalidade para desabilitar no Finance projetos e contratos originados no Project Service Automation. Por exemplo, você pode desativar a capacidade de editar contratos e projetos, criar estruturas de detalhamento de trabalho e inserir folhas de ponto no Finance. Os campos relacionados à contabilidade continuarão habilitados, mesmo se a configuração do parâmetro torná-los indisponíveis. Por padrão, todas as funcionalidades estão habilitadas. |
