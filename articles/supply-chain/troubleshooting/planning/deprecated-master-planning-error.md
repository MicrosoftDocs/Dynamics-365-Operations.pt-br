---
title: Você recebe um erro ao executar o mecanismo de planejamento mestre embutido
description: Ao executar o mecanismo de planejamento mestre embutido, você recebe uma mensagem de erro.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: Dialog_ReqCalcScheduleItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 9c950292a4f43319d21a7deafdfb341b7bef15d8
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294012"
---
# <a name="you-receive-an-error-when-running-the-built-in-master-planning-engine"></a>Você recebe um erro ao executar o mecanismo de planejamento mestre embutido

Código de erro: ReqCalcScheduleItemTablePlanningOptimizationFitError

## <a name="symptoms"></a>Sintomas

Ao executar o planejamento mestre usando o mecanismo de planejamento mestre embutido, você recebe a seguinte mensagem de erro:

> Você recebeu essa mensagem de erro porque o mecanismo de planejamento mestre interno foi usado para cenários com suporte da Otimização de Planejamento. Você deve migrar para a Otimização de Planejamento agora, pois o planejamento mestre interno atual será preterido. Observe que essa execução do planejamento mestre foi concluída com êxito. Caso sua migração tenha fortes dependências de recursos pendentes, uma exceção para continuar o uso do mecanismo de planejamento mestre interno poderá ser solicitada. Preencha o seguinte questionário para começar e, se for o caso, solicitar uma exceção da migração para a Otimização de Planejamento. [Migração e questionário de exceção da Otimização de Planejamento](https://go.microsoft.com/fwlink/?linkid=2144962)

## <a name="cause"></a>Causa

Se você executar o planejamento e não usar recursos de controle de produção, você deve considerar migrar para a Otimização de Planejamento. O mecanismo de planejamento mestre embutido está sendo preterido. Portanto, se quiser continuar usando o mecanismo sem receber a mensagem de erro, você deve solicitar uma exceção da Microsoft.

## <a name="resolution"></a>Resolução

Para obter mais informações sobre como migrar para a Otimização de Planejamento, ou como solicitar uma exceção para que você possa continuar a usar o mecanismo de planejamento incorporado preterido, consulte [Migração para Otimização de Planejamento para planejamento mestre](/dynamics365/supply-chain/master-planning/new-master-planning-engine).
