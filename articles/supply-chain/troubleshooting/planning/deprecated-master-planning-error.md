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
# <a name="you-receive-an-error-when-running-the-built-in-master-planning-engine"></a><span data-ttu-id="5f973-103">Você recebe um erro ao executar o mecanismo de planejamento mestre embutido</span><span class="sxs-lookup"><span data-stu-id="5f973-103">You receive an error when running the built-in master planning engine</span></span>

<span data-ttu-id="5f973-104">Código de erro: ReqCalcScheduleItemTablePlanningOptimizationFitError</span><span class="sxs-lookup"><span data-stu-id="5f973-104">Error code: ReqCalcScheduleItemTablePlanningOptimizationFitError</span></span>

## <a name="symptoms"></a><span data-ttu-id="5f973-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="5f973-105">Symptoms</span></span>

<span data-ttu-id="5f973-106">Ao executar o planejamento mestre usando o mecanismo de planejamento mestre embutido, você recebe a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="5f973-106">When you run master planning by using the deprecated built-in master planning engine, you receive the following error message:</span></span>

> <span data-ttu-id="5f973-107">Você recebeu essa mensagem de erro porque o mecanismo de planejamento mestre interno foi usado para cenários com suporte da Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="5f973-107">You receive this error message because the built-in master planning engine was used for scenarios supported by Planning Optimization.</span></span> <span data-ttu-id="5f973-108">Você deve migrar para a Otimização de Planejamento agora, pois o planejamento mestre interno atual será preterido.</span><span class="sxs-lookup"><span data-stu-id="5f973-108">You should migrate to Planning Optimization now, as the current built-in master planning will be deprecated.</span></span> <span data-ttu-id="5f973-109">Observe que essa execução do planejamento mestre foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="5f973-109">Note that this master planning run did complete successfully.</span></span> <span data-ttu-id="5f973-110">Caso sua migração tenha fortes dependências de recursos pendentes, uma exceção para continuar o uso do mecanismo de planejamento mestre interno poderá ser solicitada.</span><span class="sxs-lookup"><span data-stu-id="5f973-110">In case your migration has strong dependencies on pending features, an exception to continued usage of the built-in master planning engine can be requested.</span></span> <span data-ttu-id="5f973-111">Preencha o seguinte questionário para começar e, se for o caso, solicitar uma exceção da migração para a Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="5f973-111">Please complete the following questionnaire to get started and, if relevant, request an exception from migration to Planning Optimization.</span></span> [<span data-ttu-id="5f973-112">Migração e questionário de exceção da Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="5f973-112">Planning Optimization migration and exception questionnaire</span></span>](https://go.microsoft.com/fwlink/?linkid=2144962)

## <a name="cause"></a><span data-ttu-id="5f973-113">Causa</span><span class="sxs-lookup"><span data-stu-id="5f973-113">Cause</span></span>

<span data-ttu-id="5f973-114">Se você executar o planejamento e não usar recursos de controle de produção, você deve considerar migrar para a Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="5f973-114">If you run planning and don't use production control features, you should consider migrating to Planning Optimization.</span></span> <span data-ttu-id="5f973-115">O mecanismo de planejamento mestre embutido está sendo preterido.</span><span class="sxs-lookup"><span data-stu-id="5f973-115">The built-in master planning engine is being deprecated.</span></span> <span data-ttu-id="5f973-116">Portanto, se quiser continuar usando o mecanismo sem receber a mensagem de erro, você deve solicitar uma exceção da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5f973-116">Therefore, if you want to continue to use it without receiving the error message, you must apply for an exception from Microsoft.</span></span>

## <a name="resolution"></a><span data-ttu-id="5f973-117">Resolução</span><span class="sxs-lookup"><span data-stu-id="5f973-117">Resolution</span></span>

<span data-ttu-id="5f973-118">Para obter mais informações sobre como migrar para a Otimização de Planejamento, ou como solicitar uma exceção para que você possa continuar a usar o mecanismo de planejamento incorporado preterido, consulte [Migração para Otimização de Planejamento para planejamento mestre](/dynamics365/supply-chain/master-planning/new-master-planning-engine).</span><span class="sxs-lookup"><span data-stu-id="5f973-118">For more information about how to migrate to Planning Optimization, or how to apply for an exception so that you can continue to use the deprecated built-in planning engine instead, see [Migration to Planning Optimization for master planning](/dynamics365/supply-chain/master-planning/new-master-planning-engine).</span></span>
