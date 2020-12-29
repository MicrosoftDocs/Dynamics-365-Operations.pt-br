---
title: Adicionar um antecessor à atividade do fluxo de produção
description: Em uma versão de fluxo de produção, todas as atividades devem ser sequenciadas.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c39cef1174439b42a072bd7fc1ac29ef31ecf864
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4421915"
---
# <a name="add-a-predecessor-to-a-production-flow-activity"></a>Adicionar um antecessor à atividade do fluxo de produção

[!include [banner](../../includes/banner.md)]

Em uma versão de fluxo de produção, todas as atividades devem ser sequenciadas. Uma atividade poderá ter um ou vários predecessores ou sucessores. 

Este procedimento mostra como associar um predecessor a uma atividade. 

Para executar esta tarefa, será necessário um fluxo de produção que tenha a versão de rascunho com pelo menos duas atividades que possam ser conectadas. 

Para saber mais, leia o white paper "Fluxos de produção e atividades em lean manufacturing".


## <a name="find-the-production-flow-and-version"></a>Localizar o fluxo de produção e a versão
1. Vá para Controle de produção > Configuração > Fluxo de produção de lean manufacturing > Fluxos de produção.
2. Na lista, localize e selecione o PDV desejado.
3. Na lista, clique no link na linha selecionada.
4. Na lista, localize e selecione o PDV desejado.
5. Clique em Atividades.

## <a name="select-an-activity-and-add-a-predecessor"></a>Selecionar uma atividade e adicionar um predecessor
1. Na lista, localize e selecione o PDV desejado.
2. Clique em Adicionar predecessor.
3. No campo Atividade, insira ou selecione um valor.
4. No campo Razão do tempo de ciclo, insira um número.
    * A razão do tempo de ciclo padrão de uma relação de atividade é 1. Isso presume que as duas atividades são executadas no mesmo ritmo ou takt time. Se o predecessor for executado em um ritmo maior (takt time menor), a taxa deverá ser menor que 1. Se o predecessor for executado em um ritmo mais lento (takt time maior), a taxa do ciclo de tempo será maior que 1.  
5. Clique em OK.

