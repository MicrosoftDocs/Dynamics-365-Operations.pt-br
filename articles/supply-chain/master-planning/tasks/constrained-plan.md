---
title: Gerar um plano restrito
description: Este procedimento mostra como criar um plano que leve em consideração restrições de materiais e de capacidade.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 72cddd58b7068e08cddf24df83da8da2f7af7168
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845275"
---
# <a name="generate-a-constrained-plan"></a>Gerar um plano restrito

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como criar um plano que leve em consideração restrições de materiais e de capacidade. O plano garante que a fabricação não seja iniciada antes dos materiais estarem disponíveis e os recursos e não estarem reservados. 

A empresa de dados demo usada para criar este procedimento é USMF. Esse procedimento é criado para o planejador de produção.


## <a name="set-up-a-constrained-plan"></a>Configurar um plano restrito
1. Clique em Planejamento mestre.
2. Clique em Planos mestre.
3. Na lista, localize e selecione o PDV desejado.
    * Exemplo: StaticPlan  
4. Selecione Sim no campo da capacidade finita.
5. No tempo limite da Capacidade finita, insira '30'.
6. Expanda os limites de tempo na seção de dias.
7. Selecione Sim no campo da Capacidade.
8. No tempo limite de programação de capacidade (dias), insira um número.
    * Exemplo 60  
9. Selecione Sim no campo Atrasos calculados.
10. No tempo limite de Atrasos calculados (dias), insira um número.
    * Exemplo 60  
11. Expanda a seção de atrasos calculada.
12. Selecione Sim no campo Adicionar o atraso calculado à data da requisição.
13. Selecione Sim no campo Adicionar o atraso calculado à data da requisição.
14. Selecione Sim no campo Adicionar o atraso calculado à data da requisição.
15. Feche a página.

## <a name="create-a-constrained-plan"></a>Criar um plano restrito
1. Clique em Executar.
2. No campo Plano mestre, insira ou selecione um valor.
    * Selecione o plano para o qual você configurou restrições.  
3. Clique em OK.
    * Isso pode levar algum tempo.  
4. Clique em Ordens planejadas.

