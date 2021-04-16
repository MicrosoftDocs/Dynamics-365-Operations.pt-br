---
title: Sequência numérica unificada para IDs de trabalho
description: Esse recurso fornece uma sequência numérica única e unificada que gera IDs de trabalho para os módulos Controle de produção, Execução de fabricação e Tempo e presença.
author: johanhoffmann
ms.date: 03/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 00212803c46d898a39eafbc5c62016eb829535e2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824932"
---
# <a name="unified-number-sequence-for-job-ids"></a><span data-ttu-id="544a5-103">Sequência numérica unificada para IDs de trabalho</span><span class="sxs-lookup"><span data-stu-id="544a5-103">Unified number sequence for job IDs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="544a5-104">Esse recurso fornece uma sequência numérica única e unificada que gera IDs de trabalho para os módulos Controle de produção, Execução de fabricação e Tempo e presença.</span><span class="sxs-lookup"><span data-stu-id="544a5-104">This feature provides a single, unified number sequence that generates job IDs for the Production control, Manufacturing execution, and Time and attendance modules.</span></span> <span data-ttu-id="544a5-105">Anteriormente, você conseguia escolher uma sequência numérica diferente para cada um desses módulos, o que podia resultar em uma identificação de trabalho conflitante se duas ou mais dessas sequências usassem um formato idêntico.</span><span class="sxs-lookup"><span data-stu-id="544a5-105">Previously, you were able to choose a different number sequence for each of these modules, which could result in conflicting job IDs if two or more of these sequences used an identical format.</span></span> <span data-ttu-id="544a5-106">Esse conflito pode causar a corrupção de dados.</span><span class="sxs-lookup"><span data-stu-id="544a5-106">Such a conflict can cause data corruption.</span></span>

## <a name="turn-on-this-feature-for-your-system"></a><span data-ttu-id="544a5-107">Ative este recurso para o seu sistema</span><span class="sxs-lookup"><span data-stu-id="544a5-107">Turn on this feature for your system</span></span>

<span data-ttu-id="544a5-108">Se o sistema ainda não incluir o recurso descrito neste tópico, acesse [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative o recurso *Sequência numérica unificada para IDs de trabalho*.</span><span class="sxs-lookup"><span data-stu-id="544a5-108">If your system doesn't already include the feature described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) and turn on the *Unified number sequence for job IDs* feature.</span></span>

## <a name="set-up-the-unified-number-sequence-for-job-ids"></a><span data-ttu-id="544a5-109">Configurar a sequência numérica unificada para identificações de trabalho</span><span class="sxs-lookup"><span data-stu-id="544a5-109">Set up the unified number sequence for job IDs</span></span>

<span data-ttu-id="544a5-110">Depois de habilitar esse recurso, as configurações existentes da sequência numérica **Identificação do trabalho** localizadas nas páginas de parâmetros para os módulos Controle de produção, Execução de fabricação e Tempo e presença serão preteridas e um novo campo **ID do trabalho unificada** será adicionado.</span><span class="sxs-lookup"><span data-stu-id="544a5-110">After enabling this feature, the existing **Job identification** number-sequence settings located on the parameters pages for the Production control, Manufacturing execution, and Time and attendance modules will be deprecated and a new **Unified job ID** field will be added.</span></span> <span data-ttu-id="544a5-111">O valor da **ID do trabalho unificado** é compartilhado por todos os três módulos, garantindo, dessa forma, que todos os módulos façam referência à mesma sequência numérica.</span><span class="sxs-lookup"><span data-stu-id="544a5-111">The **Unified job ID** value is shared by all three modules, thus ensuring that all modules reference the same number sequence.</span></span> <span data-ttu-id="544a5-112">Portanto, as IDs do trabalho serão exclusivas entre os três módulos e um conflito nunca ocorrerá.</span><span class="sxs-lookup"><span data-stu-id="544a5-112">Job IDs will therefore be unique across all three modules and a conflict will never occur.</span></span>

<span data-ttu-id="544a5-113">Para configurar a sequência numérica unificada para IDs do trabalho:</span><span class="sxs-lookup"><span data-stu-id="544a5-113">To set up the unified number sequence for job IDs:</span></span>

1. <span data-ttu-id="544a5-114">Ative o recurso conforme descrito na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="544a5-114">Turn on the feature as described in the previous section.</span></span>
1. <span data-ttu-id="544a5-115">Identifique a sequência numérica que você deseja usar para as IDs do trabalho unificadas ou crie uma nova.</span><span class="sxs-lookup"><span data-stu-id="544a5-115">Either identify the number sequence you want to use for your unified job IDs, or create a new one.</span></span> <span data-ttu-id="544a5-116">Para obter mais informações, consulte [Visão geral de sequências numéricas](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).</span><span class="sxs-lookup"><span data-stu-id="544a5-116">For more information, see [Number sequences overview](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).</span></span>
1. <span data-ttu-id="544a5-117">Vá para a página **Parâmetros de controle de produção**, **Parâmetros de execução de fabricação** ou **Parâmetros de tempo e presença**.</span><span class="sxs-lookup"><span data-stu-id="544a5-117">Go to the **Production control parameters**, **Manufacturing execution parameters**, or **Time and attendance parameters** page.</span></span> <span data-ttu-id="544a5-118">Não importa qual seja a escolha, já que quando você faz essa configuração em qualquer uma dessas páginas, todas as outras páginas são atualizadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="544a5-118">It doesn't matter which one you choose because when you make this setting on any of those pages, all of the other pages will update automatically.</span></span>
1. <span data-ttu-id="544a5-119">Abra a guia **Sequências numéricas** na página de parâmetros selecionada.</span><span class="sxs-lookup"><span data-stu-id="544a5-119">Open the **Number sequences** tab on your selected parameters page.</span></span>
1. <span data-ttu-id="544a5-120">Atribua o **Código de sequência numérica** identificado anteriormente à linha **IDs do trabalho unificadas** da grade.</span><span class="sxs-lookup"><span data-stu-id="544a5-120">Assign the **Number sequence code** that you identified previously to the **Unified job IDs** row of the grid.</span></span>
