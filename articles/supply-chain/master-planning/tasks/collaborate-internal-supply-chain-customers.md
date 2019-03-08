---
title: Colaborar com clientes da cadeia de fornecimento interna
description: Este procedimento mostra como exibir todas as ordens planejadas que serão cumpridas por um fornecedor intercompanhia.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqOutboundIntercompanyDemand
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 44b9f516835acc792ec1edba0b5efdcbd2823422
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "358039"
---
# <a name="collaborate-with-internal-supply-chain-customers"></a><span data-ttu-id="b10ab-103">Colaborar com clientes da cadeia de fornecimento interna</span><span class="sxs-lookup"><span data-stu-id="b10ab-103">Collaborate with internal supply chain customers</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b10ab-104">Este procedimento mostra como exibir todas as ordens planejadas que serão cumpridas por um fornecedor intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="b10ab-104">This procedure shows how to view all the planned orders that will be fulfilled by an intercompany vendor.</span></span> <span data-ttu-id="b10ab-105">A empresa de dados demonstrativos utilizada para criar esse procedimento é a DEMF.</span><span class="sxs-lookup"><span data-stu-id="b10ab-105">The demo data company used to create this procedure is DEMF.</span></span>

1. <span data-ttu-id="b10ab-106">Clique em Planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="b10ab-106">Click Master planning.</span></span>
2. <span data-ttu-id="b10ab-107">No campo Plano, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b10ab-107">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="b10ab-108">No campo Plano, selecione o plano 10.</span><span class="sxs-lookup"><span data-stu-id="b10ab-108">In the Plan field, select plan 10.</span></span>  
3. <span data-ttu-id="b10ab-109">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="b10ab-109">Click Run.</span></span>
4. <span data-ttu-id="b10ab-110">No campo Número de threads, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b10ab-110">In the Number of threads field, enter a number.</span></span>
    * <span data-ttu-id="b10ab-111">Isso representa o número de threads paralelos a serem usados no planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="b10ab-111">This represents the number of parallel threads to be used for master planning.</span></span>  
5. <span data-ttu-id="b10ab-112">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b10ab-112">Click OK.</span></span>
    * <span data-ttu-id="b10ab-113">Isso pode levar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="b10ab-113">This may take a while.</span></span>  
6. <span data-ttu-id="b10ab-114">Clique em Planejamento de demanda intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="b10ab-114">Click Planned intercompany demand.</span></span>
7. <span data-ttu-id="b10ab-115">Clique em Planejamento de demanda intercompanhia de saída.</span><span class="sxs-lookup"><span data-stu-id="b10ab-115">Click Outbound planned intercompany demand.</span></span>
    * <span data-ttu-id="b10ab-116">Esta página fornece uma visão geral de todas as demandas planejadas que serão cumpridas por um fornecedor interno da cadeia de fornecimento.</span><span class="sxs-lookup"><span data-stu-id="b10ab-116">This page provides an overview of all the planned demand that will be fulfilled by an internal supply chain vendor.</span></span>  
8. <span data-ttu-id="b10ab-117">Expanda a seção Detalhes da demanda upstream.</span><span class="sxs-lookup"><span data-stu-id="b10ab-117">Expand the Upstream demand details section.</span></span>
    * <span data-ttu-id="b10ab-118">Nesta seção, você poderá ver os detalhes sobre como a solicitação será cumprida.</span><span class="sxs-lookup"><span data-stu-id="b10ab-118">In this section, you can see the details about how the demand will be fulfilled.</span></span> <span data-ttu-id="b10ab-119">É possível que você tenha que aguardar o planejamento mestre ser executado na empresa de fornecimento antes que possa ver informações adicionais aqui.</span><span class="sxs-lookup"><span data-stu-id="b10ab-119">You may need to wait for master planning to be run in the supply company before you can see additional information here.</span></span>  

