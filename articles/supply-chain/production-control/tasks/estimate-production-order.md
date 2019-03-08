---
title: Estimar uma ordem de produção
description: Você pode realizar esse procedimento usando a empresa de dados de demonstração USMF ou seu próprio conjunto de dados.
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8274e390a177f51649f5cad70ef7ad5bd50a8830
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "351852"
---
# <a name="estimate-a-production-order"></a><span data-ttu-id="7215a-103">Estimar uma ordem de produção</span><span class="sxs-lookup"><span data-stu-id="7215a-103">Estimate a production order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7215a-104">Você pode realizar esse procedimento usando a empresa de dados de demonstração USMF ou seu próprio conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="7215a-104">You can run this procedure by using the USMF demo data company or your own data set.</span></span> <span data-ttu-id="7215a-105">Em ambos os casos, é necessário uma ordem de produção aberta com o status Criada.</span><span class="sxs-lookup"><span data-stu-id="7215a-105">In both cases, you need to have an open production order that has the Created status.</span></span> <span data-ttu-id="7215a-106">Este é o segundo procedimento de sete que explica o ciclo de vida da ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="7215a-106">This is the second procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="estimate-a-production-order"></a><span data-ttu-id="7215a-107">Estimar uma ordem de produção</span><span class="sxs-lookup"><span data-stu-id="7215a-107">Estimate a production order</span></span>
1. <span data-ttu-id="7215a-108">Vá para Controle de produção > Ordens de produção > Todas as ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="7215a-108">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="7215a-109">Selecione uma ordem com o status Criada na grade.</span><span class="sxs-lookup"><span data-stu-id="7215a-109">Select an order that has the Created status in the grid.</span></span>
3. <span data-ttu-id="7215a-110">No Painel de Ação, clique em Ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="7215a-110">On the Action Pane, click Production order.</span></span>
4. <span data-ttu-id="7215a-111">Clique em Estimar.</span><span class="sxs-lookup"><span data-stu-id="7215a-111">Click Estimate.</span></span>
    * <span data-ttu-id="7215a-112">Nesta etapa, os custos estimados de uma única ordem de produção são calculados.</span><span class="sxs-lookup"><span data-stu-id="7215a-112">In this step, the estimated costs of a single production order is calculated.</span></span>   
5. <span data-ttu-id="7215a-113">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7215a-113">Click OK.</span></span>

## <a name="view-the-calculation-details"></a><span data-ttu-id="7215a-114">Exibir os detalhes do cálculo</span><span class="sxs-lookup"><span data-stu-id="7215a-114">View the calculation details</span></span>
1. <span data-ttu-id="7215a-115">No Painel de Ação, clique em Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="7215a-115">On the Action Pane, click Manage costs.</span></span>
2. <span data-ttu-id="7215a-116">Clique em Exibir detalhes do cálculo.</span><span class="sxs-lookup"><span data-stu-id="7215a-116">Click View calculation details.</span></span>
    * <span data-ttu-id="7215a-117">Esta página exibe a divisão de custo.</span><span class="sxs-lookup"><span data-stu-id="7215a-117">This page displays the cost breakdown.</span></span> <span data-ttu-id="7215a-118">Por exemplo, você pode exibir o preço de custo total por unidade para o produto finalizado na primeira linha.</span><span class="sxs-lookup"><span data-stu-id="7215a-118">For example, you can view the total cost price per unit for the finished product in the first row.</span></span> <span data-ttu-id="7215a-119">As linhas subsequentes contêm custos de acordo com a lista de materiais, o roteiro de produção e os custos indiretos.</span><span class="sxs-lookup"><span data-stu-id="7215a-119">The subsequent rows contain costs according to the bill of materials, production route, and indirect costs.</span></span>  
