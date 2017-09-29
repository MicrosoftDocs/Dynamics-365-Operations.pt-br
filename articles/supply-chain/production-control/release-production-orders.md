---
title: "Liberar ordens de produção"
description: "Uma ordem de produção liberada é uma ordem que foi autorizada para produção. O termo Liberada é usado para descrever um estado no ciclo de vida da ordem de produção, no qual a ordem de produção está disponível para a execução do chão de fábrica de produção para os processos de depósito."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdParmRelease
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2414
ms.assetid: 50c2257b-2924-44f5-b7c1-11f498092053
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: aa38c50a58bed5702332182b9e0827b863f536f7
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---

# <a name="release-production-orders"></a><span data-ttu-id="755e9-104">Liberar ordens de produção</span><span class="sxs-lookup"><span data-stu-id="755e9-104">Release production orders</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="755e9-105">Uma ordem de produção liberada é uma ordem que foi autorizada para produção.</span><span class="sxs-lookup"><span data-stu-id="755e9-105">A released production order is an order that has been authorized for production.</span></span> <span data-ttu-id="755e9-106">O termo Liberada é usado para descrever um estado no ciclo de vida da ordem de produção, no qual a ordem de produção está disponível para a execução do chão de fábrica de produção para os processos de depósito.</span><span class="sxs-lookup"><span data-stu-id="755e9-106">The term Released is used to describe a state in the production order life cycle, where the production order is available for execution on the production shop floor and for warehouse processes.</span></span> 

<a name="characteristics-of-the-released-state"></a><span data-ttu-id="755e9-107">Características do estado Liberado</span><span class="sxs-lookup"><span data-stu-id="755e9-107">Characteristics of the Released state</span></span>
-------------------------------------

<span data-ttu-id="755e9-108">O estado **Liberado** é um estado no ciclo de vida da ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="755e9-108">The **Released** state is one state in the production order life cycle.</span></span> <span data-ttu-id="755e9-109">As ordens de produção que estão no estado **Liberado** ficam disponíveis para a execução no chão de fábrica de produção e para os processos do depósito.</span><span class="sxs-lookup"><span data-stu-id="755e9-109">Production orders that are in the **Released** state are available for execution on the production shop floor and for warehouse processes.</span></span> <span data-ttu-id="755e9-110">O estado **Liberado** tem as seguintes características:</span><span class="sxs-lookup"><span data-stu-id="755e9-110">The **Released** state has the following characteristics:</span></span>

-   <span data-ttu-id="755e9-111">Uma ordem de produção pode ser alterada para o estado **Liberado** da ordem de produção ou por meio de um processo em lote.</span><span class="sxs-lookup"><span data-stu-id="755e9-111">A production order can be changed to the **Released** state either from the production order or by using a batch process.</span></span> <span data-ttu-id="755e9-112">A ordem de produção também pode ser atualizada automaticamente de ordens de produção planejadas que foram confirmadas usando o campo **Limite de tempo de confirmação** na página **Planejamento mestre**.</span><span class="sxs-lookup"><span data-stu-id="755e9-112">The production order can also be updated automatically from planned production orders that are firmed by using the **Firming time fence** field on the **Master plan** page.</span></span>
-   <span data-ttu-id="755e9-113">O estado **Liberado** é o sinal dos operadores de chão de fábrica (operadores) para iniciar a execução dos trabalhos de produção no chão de fábrica.</span><span class="sxs-lookup"><span data-stu-id="755e9-113">The **Released** state is the signal for the shop floor operators (operators) to start executing the production jobs on the shop floor.</span></span>
-   <span data-ttu-id="755e9-114">Os documentos de produção, como cartões de roteiro, roteiros de trabalho e fichas de trabalho fornecem informações sobre trabalhos de produção e podem ser emitidos.</span><span class="sxs-lookup"><span data-stu-id="755e9-114">Production papers, such as route cards, route jobs, and jobs cards provide information about production jobs and can be issued.</span></span>
-   <span data-ttu-id="755e9-115">Para os materiais que são reservados fisicamente, o trabalho do depósito é gerado para escolher materiais da ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="755e9-115">For materials that are physically reserved, warehouse work is generated to pick materials for the production order.</span></span>

## <a name="releasing-jobs-to-the-shop-floor"></a><span data-ttu-id="755e9-116">Liberação de trabalhos para o chão de fábrica</span><span class="sxs-lookup"><span data-stu-id="755e9-116">Releasing jobs to the shop floor</span></span>
<span data-ttu-id="755e9-117">Depois que uma ordem de produção for liberada, os trabalhos de produção relacionados à ordem ficarão visíveis e prontos para o registro.</span><span class="sxs-lookup"><span data-stu-id="755e9-117">After a production order is released, production jobs that are related to the order are visible and ready for registration.</span></span> <span data-ttu-id="755e9-118">Os operadores podem fazer inscrições de trabalhos, como Iniciar, Parar e Concluir na página **Termino do cartão de trabalho** ou página **Dispositivo de cartão de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="755e9-118">The operators can make job registrations, such as Start, Stop, and Completion, on either the **Job card terminal** page or the **Job card device** page.</span></span> <span data-ttu-id="755e9-119">O tempo e a quantidade registrados são automaticamente transferidos das páginas de registro para revistas de produção para acompanhar o tempo e a quantidade consumidos.</span><span class="sxs-lookup"><span data-stu-id="755e9-119">The registered time and quantity are automatically transferred from the registration pages to production journals to keep track of the consumed time and quantity.</span></span>

## <a name="route-cards"></a><span data-ttu-id="755e9-120">Cartões de roteiro</span><span class="sxs-lookup"><span data-stu-id="755e9-120">Route cards</span></span>
<span data-ttu-id="755e9-121">Os cartões de roteiro fornecem uma visão geral das informações provenientes das configurações de roteiros e operações e dos métodos de agendamento de operações e trabalho.</span><span class="sxs-lookup"><span data-stu-id="755e9-121">A route card provides an overview of information that comes from route and operation setups, and from operation and job scheduling methods.</span></span>

## <a name="route-jobs"></a><span data-ttu-id="755e9-122">Roteiros de trabalho</span><span class="sxs-lookup"><span data-stu-id="755e9-122">Route jobs</span></span>
<span data-ttu-id="755e9-123">Os roteiros de trabalho listam cada trabalho de uma operação em detalhes e incluem os tempos de configuração, processamento, espera e transporte.</span><span class="sxs-lookup"><span data-stu-id="755e9-123">A route job lists each job of an operation in detail, and includes setup, process, queue, and transportation times.</span></span> <span data-ttu-id="755e9-124">Por exemplo, uma operação como pintura poderá exigir trabalhos individuais, como tempo de configuração, tempo de execução para o processo de pintura e tempo de espera para a secagem.</span><span class="sxs-lookup"><span data-stu-id="755e9-124">For example, an operation such as painting might require individual jobs, such as setup time, run time for the painting process, and queue time for drying.</span></span>

## <a name="job-cards"></a><span data-ttu-id="755e9-125">Fichas de trabalho</span><span class="sxs-lookup"><span data-stu-id="755e9-125">Job cards</span></span>
<span data-ttu-id="755e9-126">As fichas de trabalho listam os números dos trabalhos individuais de determinada operação.</span><span class="sxs-lookup"><span data-stu-id="755e9-126">A job card lists the individual job numbers of a particular operation.</span></span> <span data-ttu-id="755e9-127">Um trabalho aparece em cada página.</span><span class="sxs-lookup"><span data-stu-id="755e9-127">One job appears on each page.</span></span> <span data-ttu-id="755e9-128">Os trabalhos incluídos em uma ficha de trabalho e seus tempos estimados baseiam-se nas informações de configuração de roteiros e operações.</span><span class="sxs-lookup"><span data-stu-id="755e9-128">The jobs that are included on a job card, and their estimated times, come from the route and operation setup information.</span></span> <span data-ttu-id="755e9-129">De uma ficha de trabalho, você pode abrir a página **Linhas do diário de produção**, **ficha de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="755e9-129">From a job card, you can open the **Production journal lines**, **job card** page.</span></span> <span data-ttu-id="755e9-130">As pessoas que executam recursos de operações podem fornecer comentários sobre os processos de produção.</span><span class="sxs-lookup"><span data-stu-id="755e9-130">People who run operations resources can provide feedback about the production process.</span></span> <span data-ttu-id="755e9-131">Existem campos onde você pode inserir estatísticas de consumo e informações como a quantidade com erros.</span><span class="sxs-lookup"><span data-stu-id="755e9-131">There are fields where you can enter consumption statistics and information such as the error quantity.</span></span>

## <a name="warehouse-work-for-raw-material-picking"></a><span data-ttu-id="755e9-132">Trabalho de depósito para a separação de matéria-prima</span><span class="sxs-lookup"><span data-stu-id="755e9-132">Warehouse work for raw material picking</span></span>
<span data-ttu-id="755e9-133">O trabalho para a separação de matéria-prima é gerado durante a liberação.</span><span class="sxs-lookup"><span data-stu-id="755e9-133">Work for raw material picking is generated during release.</span></span> <span data-ttu-id="755e9-134">O trabalho é gerado apenas para a quantidade de materiais que foram fisicamente reservados para a ordem de produção antes da ordem ter sido liberada.</span><span class="sxs-lookup"><span data-stu-id="755e9-134">Work is generated only for the quantity of materials that was physically reserved for the production order before the order was released.</span></span> <span data-ttu-id="755e9-135">A seguinte configuração é necessária para gerar trabalho de armazenamento para coleta de matérias-primas:</span><span class="sxs-lookup"><span data-stu-id="755e9-135">The following setup is required to generate warehouse work for raw material picking:</span></span>

-   <span data-ttu-id="755e9-136">Uma diretiva da localização da separação de matéria-prima que determina o local do depósito para escolher os materiais</span><span class="sxs-lookup"><span data-stu-id="755e9-136">A location directive for raw materials picking that determines which warehouse location to pick the materials in</span></span>
-   <span data-ttu-id="755e9-137">Um modelo de onda para matérias-primas, onde as políticas para a execução do trabalho de depósito são configuradas</span><span class="sxs-lookup"><span data-stu-id="755e9-137">A wave template for raw materials, where policies for the execution of warehouse work are configured</span></span>
-   <span data-ttu-id="755e9-138">Uma localização de entrada de produção que determina onde os materiais são colocados</span><span class="sxs-lookup"><span data-stu-id="755e9-138">A production input location that determines where materials are put</span></span>





