---
title: Localizar grades de produtos obsoletos
description: Este procedimento mostra como localizar produtos ou grades de produtos liberados obsoletos e como associar um estado do ciclo de vida do produto aos produtos obsoletos.
author: cvocph
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 807297a87a7f0e59023d80fbd371bffbf2b086bd
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5807983"
---
# <a name="find-obsolete-product-variants"></a><span data-ttu-id="68385-103">Localizar grades de produtos obsoletos</span><span class="sxs-lookup"><span data-stu-id="68385-103">Find obsolete product variants</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="68385-104">Este procedimento mostra como localizar produtos ou grades de produtos liberados obsoletos e como associar um estado do ciclo de vida do produto aos produtos obsoletos.</span><span class="sxs-lookup"><span data-stu-id="68385-104">This procedure shows how to find obsolete released products or product variants and how to associate a product lifecycle state to the obsolete products.</span></span> <span data-ttu-id="68385-105">Pré-requisito: você precisa definir pelo menos um estado do ciclo de vida do produto que esteja inativo para planejar para poder executar este guia de tarefas.</span><span class="sxs-lookup"><span data-stu-id="68385-105">Prerequisite: You need to define at least one product lifecycle state that is inactive for planning before you can play this task guide.</span></span>


## <a name="run-a-simulation"></a><span data-ttu-id="68385-106">Executar uma simulação</span><span class="sxs-lookup"><span data-stu-id="68385-106">Run a simulation</span></span>
1. <span data-ttu-id="68385-107">Vá para Gerenciamento de informações sobre produtos > Tarefas periódicas > Alterar o estado do ciclo de vida para produtos obsoletos.</span><span class="sxs-lookup"><span data-stu-id="68385-107">Go to Product information management > Periodic tasks > Change lifecycle state for obsolete products.</span></span>
2. <span data-ttu-id="68385-108">No campo Novo estado do ciclo de vida do produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="68385-108">In the New product lifecycle state field, enter or select a value.</span></span>
3. <span data-ttu-id="68385-109">Selecione Sim no campo Executar simulação sem atualizar dados de produto.</span><span class="sxs-lookup"><span data-stu-id="68385-109">Select Yes in the Run simulation without updating product data field.</span></span>
4. <span data-ttu-id="68385-110">No campo Excluir produtos criados neste número de dias, digite um número.</span><span class="sxs-lookup"><span data-stu-id="68385-110">In the Exclude products created within this number of days field, enter a number.</span></span>
5. <span data-ttu-id="68385-111">No campo Excluir produtos usados em transações (em número de dias), digite um número.</span><span class="sxs-lookup"><span data-stu-id="68385-111">In the Exclude products used in transactions (in number of days) field, enter a number.</span></span>
6. <span data-ttu-id="68385-112">Expanda os Registros para incluir a seção.</span><span class="sxs-lookup"><span data-stu-id="68385-112">Expand the Records to include section.</span></span>
7. <span data-ttu-id="68385-113">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="68385-113">Click Filter.</span></span>
8. <span data-ttu-id="68385-114">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="68385-114">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="68385-115">No campo Critérios, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="68385-115">In the Criteria field, type a value.</span></span>
10. <span data-ttu-id="68385-116">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="68385-116">Click OK.</span></span>
11. <span data-ttu-id="68385-117">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="68385-117">Click OK.</span></span>

> [!NOTE]
> <span data-ttu-id="68385-118">É recomendável executar a simulação em lote se você espera pesquisar um grande número de produtos.</span><span class="sxs-lookup"><span data-stu-id="68385-118">It is recommended to run the simulation in batch if you expect to search a large number of products.</span></span> <span data-ttu-id="68385-119">Além disso, garanta que a simulação não seja executada durante o horário de trabalho mais ativo da empresa.</span><span class="sxs-lookup"><span data-stu-id="68385-119">Also, make sure that the simulation is not run during the most active working time of the company.</span></span>  

## <a name="review-the-simulation-results"></a><span data-ttu-id="68385-120">Examinar os resultados da simulação</span><span class="sxs-lookup"><span data-stu-id="68385-120">Review the simulation results</span></span>
1. <span data-ttu-id="68385-121">Vá para Gerenciamento de informações sobre produtos > Consultas e relatórios > Histórico de manutenção do estado do ciclo de vida do produto.</span><span class="sxs-lookup"><span data-stu-id="68385-121">Go to Product information management > Inquiries and reports > Product lifecycle state maintenance history.</span></span>
   
> [!NOTE]
> <span data-ttu-id="68385-122">Nesta página, você pode examinar os resultados da simulação e avaliar quantos produtos e grades de produtos serão associados a um novo estado do ciclo de vida do produto ao executar a atualização sem simulação.</span><span class="sxs-lookup"><span data-stu-id="68385-122">On this page, you can review the simulation results and make an assessment of how many products and product variants will be associated with a new product lifecycle state when running the update without simulation.</span></span>  

## <a name="run-the-update-of-the-product-lifecycle-state-for-obsolete-products"></a><span data-ttu-id="68385-123">Executar a atualização do Estado do ciclo de vida do produto para produtos obsoletos</span><span class="sxs-lookup"><span data-stu-id="68385-123">Run the update of the Product lifecycle state for obsolete products</span></span>
1. <span data-ttu-id="68385-124">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="68385-124">Close the page.</span></span>
2. <span data-ttu-id="68385-125">Vá para Gerenciamento de informações sobre produtos > Tarefas periódicas > Alterar o estado do ciclo de vida para produtos obsoletos.</span><span class="sxs-lookup"><span data-stu-id="68385-125">Go to Product information management > Periodic tasks > Change lifecycle state for obsolete products.</span></span>
3. <span data-ttu-id="68385-126">Expanda os Registros para incluir a seção.</span><span class="sxs-lookup"><span data-stu-id="68385-126">Expand the Records to include section.</span></span>

> [!NOTE]
> <span data-ttu-id="68385-127">Observe que a última seleção foi salva.</span><span class="sxs-lookup"><span data-stu-id="68385-127">Note that the last selection has been saved.</span></span>  

4. <span data-ttu-id="68385-128">Selecione Não no campo Executar simulação sem atualizar dados de produto.</span><span class="sxs-lookup"><span data-stu-id="68385-128">Select No in the Run simulation without updating product data field.</span></span>
5. <span data-ttu-id="68385-129">Expanda a seção Executar em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="68385-129">Expand the Run in the background section.</span></span>

> [!NOTE]
> <span data-ttu-id="68385-130">Dependendo da quantidade de produtos e de grades de produtos afetados, considere executar este trabalho em lote.</span><span class="sxs-lookup"><span data-stu-id="68385-130">Depending on how many products and product variants are affected, consider running this job in batch.</span></span> <span data-ttu-id="68385-131">Não execute um trabalho de atualização grande durante o horário de trabalho mais ativo da empresa.</span><span class="sxs-lookup"><span data-stu-id="68385-131">Make sure that you are not running a large update job during the most active working hours in the company.</span></span>  

6. <span data-ttu-id="68385-132">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="68385-132">Click OK.</span></span>
7. <span data-ttu-id="68385-133">Vá para Gerenciamento de informações sobre produtos > Consultas e relatórios > Histórico de manutenção do estado do ciclo de vida do produto.</span><span class="sxs-lookup"><span data-stu-id="68385-133">Go to Product information management > Inquiries and reports > Product lifecycle state maintenance history.</span></span>

> [!NOTE]
> <span data-ttu-id="68385-134">Examinar os produtos e as grades de produtos liberados alterados.</span><span class="sxs-lookup"><span data-stu-id="68385-134">Review the changed released products and product variants.</span></span>  

8. <span data-ttu-id="68385-135">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="68385-135">In the list, find and select the desired record.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]