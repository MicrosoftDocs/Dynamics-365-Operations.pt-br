---
title: Exibir planejamento de demanda intercompanhia de saída
description: Este procedimento mostra como exibir todas as ordens planejadas que serão cumpridas por um fornecedor intercompanhia.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqOutboundIntercompanyDemand
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2eb361e1c1d18369d6b945ec18a7e3a6a1ebfb97
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829585"
---
# <a name="view-outbound-planned-intercompany-demand"></a><span data-ttu-id="48bef-103">Exibir planejamento de demanda intercompanhia de saída</span><span class="sxs-lookup"><span data-stu-id="48bef-103">View outbound planned intercompany demand</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="48bef-104">Este procedimento mostra como exibir todas as ordens planejadas que serão cumpridas por um fornecedor intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="48bef-104">This procedure shows how to view all the planned orders that will be fulfilled by an intercompany vendor.</span></span> <span data-ttu-id="48bef-105">A empresa de dados demonstrativos utilizada para criar esse procedimento é a DEMF.</span><span class="sxs-lookup"><span data-stu-id="48bef-105">The demo data company used to create this procedure is DEMF.</span></span>

1. <span data-ttu-id="48bef-106">Clique em Planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="48bef-106">Click Master planning.</span></span>
2. <span data-ttu-id="48bef-107">No campo Plano, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="48bef-107">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="48bef-108">No campo Plano, selecione o plano 10.</span><span class="sxs-lookup"><span data-stu-id="48bef-108">In the Plan field, select plan 10.</span></span>  
3. <span data-ttu-id="48bef-109">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="48bef-109">Click Run.</span></span>
4. <span data-ttu-id="48bef-110">No campo Número de threads, insira um número.</span><span class="sxs-lookup"><span data-stu-id="48bef-110">In the Number of threads field, enter a number.</span></span>
    * <span data-ttu-id="48bef-111">Isso representa o número de threads paralelos a serem usados no planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="48bef-111">This represents the number of parallel threads to be used for master planning.</span></span>  
5. <span data-ttu-id="48bef-112">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="48bef-112">Click OK.</span></span>
    * <span data-ttu-id="48bef-113">Isso pode levar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="48bef-113">This may take a while.</span></span>  
6. <span data-ttu-id="48bef-114">Clique em Planejamento de demanda intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="48bef-114">Click Planned intercompany demand.</span></span>
7. <span data-ttu-id="48bef-115">Clique em Planejamento de demanda intercompanhia de saída.</span><span class="sxs-lookup"><span data-stu-id="48bef-115">Click Outbound planned intercompany demand.</span></span>
    * <span data-ttu-id="48bef-116">Esta página fornece uma visão geral de todas as demandas planejadas que serão cumpridas por um fornecedor interno da cadeia de fornecimento.</span><span class="sxs-lookup"><span data-stu-id="48bef-116">This page provides an overview of all the planned demand that will be fulfilled by an internal supply chain vendor.</span></span>  
8. <span data-ttu-id="48bef-117">Expanda a seção Detalhes da demanda upstream.</span><span class="sxs-lookup"><span data-stu-id="48bef-117">Expand the Upstream demand details section.</span></span>
    * <span data-ttu-id="48bef-118">Nesta seção, você poderá ver os detalhes sobre como a solicitação será cumprida.</span><span class="sxs-lookup"><span data-stu-id="48bef-118">In this section, you can see the details about how the demand will be fulfilled.</span></span> <span data-ttu-id="48bef-119">É possível que você tenha que aguardar o planejamento mestre ser executado na empresa de fornecimento antes que possa ver informações adicionais aqui.</span><span class="sxs-lookup"><span data-stu-id="48bef-119">You may need to wait for master planning to be run in the supply company before you can see additional information here.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]