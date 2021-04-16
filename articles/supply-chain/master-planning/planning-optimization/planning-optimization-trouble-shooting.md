---
title: Solução de problemas de otimização de planejamento
description: Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com a otimização de planejamento.
author: ChristianRytt
ms.date: 05/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-5-7
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 2100235fadabe6af87849aab7d9ec55d85ea66fa
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812874"
---
# <a name="troubleshoot-planning-optimization"></a><span data-ttu-id="0bd75-103">Solução de problemas de otimização de planejamento</span><span class="sxs-lookup"><span data-stu-id="0bd75-103">Troubleshoot Planning Optimization</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0bd75-104">Este tópico descreve como corrigir problemas comuns que podem ocorrer ao trabalhar com a otimização de planejamento.</span><span class="sxs-lookup"><span data-stu-id="0bd75-104">This topic describes how to fix common issues that you might encounter while working with Planning Optimization.</span></span>

## <a name="installation-of-the-planning-optimization-add-in-doesnt-complete"></a><span data-ttu-id="0bd75-105">A instalação do suplemento de otimização de planejamento não conclui</span><span class="sxs-lookup"><span data-stu-id="0bd75-105">Installation of the Planning Optimization add-in doesn't complete</span></span>

<span data-ttu-id="0bd75-106">A Otimização do Planejamento requer um ambiente de alta disponibilidade habilitado para Lifecycle Services (LCS), camada 2 ou superior (não um ambiente OneBox), com o Dynamics 365 Supply Chain Management versão 10.0.7 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="0bd75-106">Planning Optimization requires a Lifecycle Services (LCS) enabled, high-availability environment, tier 2 or higher (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span> <span data-ttu-id="0bd75-107">Se você tentar instalar o suplemento em um ambiente de OneBox, a instalação não será concluída.</span><span class="sxs-lookup"><span data-stu-id="0bd75-107">If you try to install the add-in on a OneBox environment, the installation won't complete.</span></span>

<span data-ttu-id="0bd75-108">**Correção**: Cancele a instalação e use um ambiente de alta disponibilidade, nível 2 ou superior (não um ambiente Onebox).</span><span class="sxs-lookup"><span data-stu-id="0bd75-108">**Fix**: Cancel the installation and use a high-availability environment, tier 2 or higher (not a OneBox environment).</span></span>

## <a name="planning-of-batch-jobs-fails-when-planning-optimization-is-enabled"></a><span data-ttu-id="0bd75-109">O planejamento de trabalhos em lotes falha quando a otimização de planejamento é habilitada</span><span class="sxs-lookup"><span data-stu-id="0bd75-109">Planning of batch jobs fails when Planning Optimization is enabled</span></span>

<span data-ttu-id="0bd75-110">Ao habilitar a otimização de planejamento, o mecanismo de planejamento mestre interno é desabilitado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0bd75-110">When you enable Planning Optimization, the built-in master planning engine is automatically disabled.</span></span> <span data-ttu-id="0bd75-111">Trabalhos em lotes de planejamento mestre criados para o mecanismo de planejamento interno do Supply Chain Management falharão se forem disparados quando a Otimização de Planejamento estiver habilitada.</span><span class="sxs-lookup"><span data-stu-id="0bd75-111">Master planning batch jobs that were created for the built-in Supply Chain Management planning engine will fail if they are triggered while Planning Optimization is enabled.</span></span> <span data-ttu-id="0bd75-112">Você pode receber uma mensagem de erro como *Esta operação disparou o planejamento mestre para o qual não há suporte quando a Otimização de Planejamento está habilitada*.</span><span class="sxs-lookup"><span data-stu-id="0bd75-112">You may receive an error message such as *This operation triggered master planning that isn't supported when Planning Optimization is enabled*.</span></span>

<span data-ttu-id="0bd75-113">**Corrigir**: cancele todos os trabalhos de lote do planejamento mestre criados para o mecanismo de planejamento de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0bd75-113">**Fix**: Cancel all master planning batch jobs that were created for the built-in Supply Chain Management planning engine.</span></span>

## <a name="planning-optimization-results-are-different-from-earlier-results"></a><span data-ttu-id="0bd75-114">Os resultados da otimização de planejamento são diferentes dos resultados anteriores</span><span class="sxs-lookup"><span data-stu-id="0bd75-114">Planning Optimization results are different from earlier results</span></span>

<span data-ttu-id="0bd75-115">A otimização do planejamento é diferente do design de planejamento mestre incorporado em algumas áreas.</span><span class="sxs-lookup"><span data-stu-id="0bd75-115">Planning Optimization differs from the built-in master planning design in some areas.</span></span> <span data-ttu-id="0bd75-116">Isso também pode ser causado por recursos pendentes.</span><span class="sxs-lookup"><span data-stu-id="0bd75-116">This can also be caused by pending features.</span></span>

<span data-ttu-id="0bd75-117">**Correção**: execute a análise de ajuste da otimização do planejamento e analise os resultados enquanto consulta a documentação relacionada para compreender o impacto.</span><span class="sxs-lookup"><span data-stu-id="0bd75-117">**Fix**: Run Planning Optimization fit analysis and then analyze the results while referring to the related documentation to understand the impact.</span></span> <span data-ttu-id="0bd75-118">Para obter mais informações, consulte [Introdução à análise de ajuste da Otimização de Planejamento](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="0bd75-118">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

## <a name="cant-enable-planning-optimization"></a><span data-ttu-id="0bd75-119">A Otimização de Planejamento pode ser habilitada</span><span class="sxs-lookup"><span data-stu-id="0bd75-119">Can't enable Planning Optimization</span></span>

<span data-ttu-id="0bd75-120">O **Status da conexão** deve ser **Conectado** antes que você possa definir **Usar otimização de planejamento** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="0bd75-120">The **Connection status** must be **Connected** before you can set **Use Planning Optimization** to **Yes**.</span></span> <span data-ttu-id="0bd75-121">Para obter mais informações, consulte [Introdução à Otimização de Planejamento](get-started.md).</span><span class="sxs-lookup"><span data-stu-id="0bd75-121">For more information, see [Get started with Planning Optimization](get-started.md).</span></span>

<span data-ttu-id="0bd75-122">**Correção**: verifique se o suplemento de Otimização de Planejamento foi instalado com êxito.</span><span class="sxs-lookup"><span data-stu-id="0bd75-122">**Fix**: Make sure that the Planning Optimization add-in was installed successfully.</span></span>

## <a name="error-message-is-shown-during-ctp"></a><span data-ttu-id="0bd75-123">A mensagem de erro é exibida durante o CTP</span><span class="sxs-lookup"><span data-stu-id="0bd75-123">Error message is shown during CTP</span></span>

<span data-ttu-id="0bd75-124">Se você tentar executar o CTP (capacidade de promessa) a partir de uma ordem de venda quando a Otimização do Planejamento estiver habilitada, você receberá a seguinte mensagem de erro: *Esta operação acionou o planejamento mestre que não tem suporte quando a Otimização de Planejamento está habilitada*.</span><span class="sxs-lookup"><span data-stu-id="0bd75-124">If you try to run capable to promise (CTP) from a sales order when Planning Optimization is enabled, you will receive the following error message: *This operation triggered master planning that isn't supported when the Planning Optimization is enabled*.</span></span>

<span data-ttu-id="0bd75-125">Isso está relacionado a um recurso pendente que está planejado como parte do suporte para ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="0bd75-125">This is related to a pending feature that is planned as part of the support for production orders.</span></span>

<span data-ttu-id="0bd75-126">**Correção:** evite os cálculos do CTP quando a Otimização do Planejamento estiver habilitada até que o suporte do CTP esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="0bd75-126">**Fix:** Avoid CTP calculations when Planning Optimization is enabled until CTP support is available.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0bd75-127">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="0bd75-127">Additional resources</span></span>

[<span data-ttu-id="0bd75-128">Introdução à Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="0bd75-128">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="0bd75-129">Análise de ajuste da Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="0bd75-129">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]