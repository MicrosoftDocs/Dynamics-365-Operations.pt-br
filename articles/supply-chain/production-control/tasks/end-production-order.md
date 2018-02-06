---
title: "Finalizar uma ordem de produção"
description: "Este procedimento mostra como finalizar uma ordem de produção."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: dadf0e87eac8522f61bb094c146e37f46a21fc09
ms.openlocfilehash: 1cc586f804a072ca5499c73ecdf7d37778cbf067
ms.contentlocale: pt-br
ms.lasthandoff: 02/06/2018

---
# <a name="end-a-production-order"></a><span data-ttu-id="19935-103">Finalizar uma ordem de produção</span><span class="sxs-lookup"><span data-stu-id="19935-103">End a production order</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="19935-104">Este procedimento mostra como finalizar uma ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="19935-104">This procedure shows how to end a production order.</span></span> <span data-ttu-id="19935-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="19935-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="19935-106">Este é o último procedimento de sete que explica o ciclo de vida da ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="19935-106">This is the final procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="end-a-production-order"></a><span data-ttu-id="19935-107">Finalizar uma ordem de produção</span><span class="sxs-lookup"><span data-stu-id="19935-107">End a production order</span></span>
1. <span data-ttu-id="19935-108">Vá para Controle de produção > Ordens de produção > Todas as ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="19935-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="19935-109">Selecione uma ordem de produção com o status Relatada como concluída.</span><span class="sxs-lookup"><span data-stu-id="19935-109">Select a production order that has the status Reported as finished.</span></span>  
2. <span data-ttu-id="19935-110">No Painel de Ação, clique em Ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="19935-110">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="19935-111">Clique em Finalizar.</span><span class="sxs-lookup"><span data-stu-id="19935-111">Click End.</span></span>
    * <span data-ttu-id="19935-112">Nesta página, você pode confirmar que deseja finalizar a ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="19935-112">On this page, you can confirm that you want to end the production order.</span></span>  
4. <span data-ttu-id="19935-113">Clique na guia Geral.</span><span class="sxs-lookup"><span data-stu-id="19935-113">Click the General tab.</span></span>
5. <span data-ttu-id="19935-114">No campo Data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="19935-114">In the Date field, enter a date.</span></span>
6. <span data-ttu-id="19935-115">No campo Método de sucata, selecione 'Alocação'.</span><span class="sxs-lookup"><span data-stu-id="19935-115">In the Scrap method field, select 'Allocation'.</span></span>
    * <span data-ttu-id="19935-116">Ao selecionar o método Alocação, os custos dos materiais sucateados são adicionados às mercadorias finalizadas.</span><span class="sxs-lookup"><span data-stu-id="19935-116">When you select the Allocation method, costs from the scrapped materials are added to the finished goods.</span></span>  
7. <span data-ttu-id="19935-117">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="19935-117">Click OK.</span></span>

## <a name="validate-calculation-results"></a><span data-ttu-id="19935-118">Validar resultados do cálculo</span><span class="sxs-lookup"><span data-stu-id="19935-118">Validate calculation results</span></span>
1. <span data-ttu-id="19935-119">No Painel de Ação, clique em Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="19935-119">On the Action Pane, click Manage costs.</span></span>
2. <span data-ttu-id="19935-120">Clique em Visualizar comparação de custo.</span><span class="sxs-lookup"><span data-stu-id="19935-120">Click View cost comparison.</span></span>
    * <span data-ttu-id="19935-121">Após a finalização da ordem de produção, é possível comparar o preço de custo estimado com o preço de custo realizado para obter uma visão geral das variações de produção.</span><span class="sxs-lookup"><span data-stu-id="19935-121">After you have ended the production order, you can compare the estimated cost price against the realized cost price to get an overview of the production variances.</span></span>  

