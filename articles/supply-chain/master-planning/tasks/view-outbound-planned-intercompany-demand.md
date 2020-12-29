---
title: Exibir planejamento de demanda intercompanhia de saída
description: Este procedimento mostra como exibir todas as ordens planejadas que serão cumpridas por um fornecedor intercompanhia.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqOutboundIntercompanyDemand
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 259ce229c18466b7d29fd231dc3f0be8a6906c6b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4421958"
---
# <a name="view-outbound-planned-intercompany-demand"></a><span data-ttu-id="c449c-103">Exibir planejamento de demanda intercompanhia de saída</span><span class="sxs-lookup"><span data-stu-id="c449c-103">View outbound planned intercompany demand</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c449c-104">Este procedimento mostra como exibir todas as ordens planejadas que serão cumpridas por um fornecedor intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="c449c-104">This procedure shows how to view all the planned orders that will be fulfilled by an intercompany vendor.</span></span> <span data-ttu-id="c449c-105">A empresa de dados demonstrativos utilizada para criar esse procedimento é a DEMF.</span><span class="sxs-lookup"><span data-stu-id="c449c-105">The demo data company used to create this procedure is DEMF.</span></span>

1. <span data-ttu-id="c449c-106">Clique em Planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="c449c-106">Click Master planning.</span></span>
2. <span data-ttu-id="c449c-107">No campo Plano, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c449c-107">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="c449c-108">No campo Plano, selecione o plano 10.</span><span class="sxs-lookup"><span data-stu-id="c449c-108">In the Plan field, select plan 10.</span></span>  
3. <span data-ttu-id="c449c-109">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="c449c-109">Click Run.</span></span>
4. <span data-ttu-id="c449c-110">No campo Número de threads, insira um número.</span><span class="sxs-lookup"><span data-stu-id="c449c-110">In the Number of threads field, enter a number.</span></span>
    * <span data-ttu-id="c449c-111">Isso representa o número de threads paralelos a serem usados no planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="c449c-111">This represents the number of parallel threads to be used for master planning.</span></span>  
5. <span data-ttu-id="c449c-112">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="c449c-112">Click OK.</span></span>
    * <span data-ttu-id="c449c-113">Isso pode levar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="c449c-113">This may take a while.</span></span>  
6. <span data-ttu-id="c449c-114">Clique em Planejamento de demanda intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="c449c-114">Click Planned intercompany demand.</span></span>
7. <span data-ttu-id="c449c-115">Clique em Planejamento de demanda intercompanhia de saída.</span><span class="sxs-lookup"><span data-stu-id="c449c-115">Click Outbound planned intercompany demand.</span></span>
    * <span data-ttu-id="c449c-116">Esta página fornece uma visão geral de todas as demandas planejadas que serão cumpridas por um fornecedor interno da cadeia de fornecimento.</span><span class="sxs-lookup"><span data-stu-id="c449c-116">This page provides an overview of all the planned demand that will be fulfilled by an internal supply chain vendor.</span></span>  
8. <span data-ttu-id="c449c-117">Expanda a seção Detalhes da demanda upstream.</span><span class="sxs-lookup"><span data-stu-id="c449c-117">Expand the Upstream demand details section.</span></span>
    * <span data-ttu-id="c449c-118">Nesta seção, você poderá ver os detalhes sobre como a solicitação será cumprida.</span><span class="sxs-lookup"><span data-stu-id="c449c-118">In this section, you can see the details about how the demand will be fulfilled.</span></span> <span data-ttu-id="c449c-119">É possível que você tenha que aguardar o planejamento mestre ser executado na empresa de fornecimento antes que possa ver informações adicionais aqui.</span><span class="sxs-lookup"><span data-stu-id="c449c-119">You may need to wait for master planning to be run in the supply company before you can see additional information here.</span></span>  

