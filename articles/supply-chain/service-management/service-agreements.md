---
title: "Contratos de serviço"
description: "Os contratos de serviço permitem definir os recursos usados em uma típica visita de serviços e como esses recursos são faturados para o cliente."
author: ShylaThompson
manager: AnnBe
ms.date: 02/19/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: c6425dcf1c89f625d997be0dd4a52aaecb6e6d65
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---

# <a name="service-agreements"></a><span data-ttu-id="b6fa3-103">Contratos de serviço</span><span class="sxs-lookup"><span data-stu-id="b6fa3-103">Service agreements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b6fa3-104">Os contratos de serviço permitem definir os recursos usados em uma típica visita de serviços e como esses recursos são faturados para o cliente.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-104">Service agreements let you define the resources that are used in a typical service visit and how those resources are invoiced to the customer.</span></span>

<span data-ttu-id="b6fa3-105">Todo contrato de serviço é vinculado a um projeto pelo qual as transações são lançadas e faturadas.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-105">Every service agreement is attached to a project through which transactions are posted and invoiced.</span></span> <span data-ttu-id="b6fa3-106">No entanto, também é possível faturar transações de ordem de serviço diretamente pelo projeto sem ter de associar primeiro a ordem de serviço a um contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-106">However, you can also invoice service order transactions directly through the project without first having to connect the service order to a service agreement.</span></span> <span data-ttu-id="b6fa3-107">Você pode decidir fazer isso se a ordem de serviço for para uma visita de serviço única e a necessidade de processar rapidamente as transações de serviço supere a necessidade de manter informações detalhadas do contrato de serviço sobre o cliente durante um período.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-107">You might decide to do this if the service order is for a one-time-only service visit and the need for processing the service transactions quickly outweighs the need for maintaining detailed service-agreement information about the customer over a period of time.</span></span>

## <a name="service-agreement"></a><span data-ttu-id="b6fa3-108">Contrato de serviço</span><span class="sxs-lookup"><span data-stu-id="b6fa3-108">Service agreement</span></span>

<span data-ttu-id="b6fa3-109">Em cada contrato de serviço você deve especificar um projeto, uma ID de contrato de serviço e um grupo de contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-109">In each service agreement, you must specify a project, a service-agreement ID, and a service-agreement group.</span></span> <span data-ttu-id="b6fa3-110">O grupo de contrato de serviço pode ser usado para classificar e organizar contratos de serviço.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-110">The service-agreement group can be used to sort and organize service agreements.</span></span>

<span data-ttu-id="b6fa3-111">O cabeçalho de um contrato de serviço contém configurações que se aplicam a todas as linhas de contrato anexadas:</span><span class="sxs-lookup"><span data-stu-id="b6fa3-111">A service agreement header contains settings that apply to all attached agreement lines:</span></span>

-  <span data-ttu-id="b6fa3-112">Se o contrato de serviço for suspenso.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-112">Whether the service agreement is suspended.</span></span> <span data-ttu-id="b6fa3-113">Se o contrato de serviço for suspenso, você não poderá gerar ordens de serviço do contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-113">If the service agreement is suspended, you cannot generate service orders from the service agreement.</span></span>
-  <span data-ttu-id="b6fa3-114">A duração do contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-114">The duration of the service agreement.</span></span>
-  <span data-ttu-id="b6fa3-115">Como as linhas de ordem de serviço devem ser combinadas em ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-115">How service-order lines are to be combined into service orders.</span></span>
-  <span data-ttu-id="b6fa3-116">Se o contrato de serviço é um modelo.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-116">Whether the service agreement is a template.</span></span>

<span data-ttu-id="b6fa3-117">No cabeçalho do contrato de serviço, é possível configurar todos os objetos e tarefas de serviço que podem ser usados com o contrato de serviço especificando as tarefas de serviço ou os objetos de serviço específicos que devem ser anexados a várias linhas do contrato.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-117">In the service-agreement header, you also set up all the service objects and service tasks that can be used with the service agreement by entering the specific service tasks or service objects that are to be attached to the various lines of the agreement.</span></span>

<span data-ttu-id="b6fa3-118">Do cabeçalho do contrato de serviço você também poderá copiar linhas de contrato de serviço ou linhas de modelo de serviço no contrato de serviço atual.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-118">From the service-agreement header, you can also copy service-agreement lines or service-template lines into the current service agreement.</span></span>

<span data-ttu-id="b6fa3-119">Você pode suspender contratos de serviço e parar linhas de contratos de serviço individuais.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-119">You can suspend service agreements and stop individual service agreement lines.</span></span>

<span data-ttu-id="b6fa3-120">Se você marcar a caixa de seleção **Suspenso** em um contrato de serviço, você não poderá:</span><span class="sxs-lookup"><span data-stu-id="b6fa3-120">If you select the **Suspended** check box on a service agreement, you cannot:</span></span>

-    <span data-ttu-id="b6fa3-121">Criar ordens de serviço automaticamente ou manualmente a partir do contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-121">Create service orders automatically or manually from the service agreement.</span></span>

<span data-ttu-id="b6fa3-122">Se você marcar a caixa de seleção **Parado** em uma linha de contrato de serviço, você não poderá:</span><span class="sxs-lookup"><span data-stu-id="b6fa3-122">If you select the **Stopped** check box on a service agreement line, you cannot:</span></span>

-    <span data-ttu-id="b6fa3-123">Criar ordens de serviço automaticamente ou manualmente a partir da linha de contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-123">Create service orders automatically or manually from the service agreement line.</span></span>
-    <span data-ttu-id="b6fa3-124">Copiar a linha de contrato de serviço em outro contrato de serviço ou ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-124">Copy the service agreement line into another service agreement or service order.</span></span>


> [!NOTE]
> <span data-ttu-id="b6fa3-125">Se um contrato de serviço for suspenso, todas as linhas anexadas serão paradas, não importando seus status individuais.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-125">If a service agreement is suspended, all the attached lines are stopped, regardless of their individual status.</span></span>

## <a name="service-agreement-lines"></a><span data-ttu-id="b6fa3-126">Linhas do contrato de serviço</span><span class="sxs-lookup"><span data-stu-id="b6fa3-126">Service-agreement lines</span></span>

<span data-ttu-id="b6fa3-127">Cada linha do contrato de serviço descreve em detalhes o conteúdo do trabalho de serviço proposto.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-127">Each service-agreement line describes in detail the content of the proposed service work.</span></span> <span data-ttu-id="b6fa3-128">As linhas contêm as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b6fa3-128">The lines contain the following settings:</span></span>

-  <span data-ttu-id="b6fa3-129">O tipo de transação e a descrição do tipo de transação.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-129">The transaction type and the description of the transaction type.</span></span>
-  <span data-ttu-id="b6fa3-130">O funcionário que executa o serviço.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-130">The employee who performs the service work.</span></span>
-  <span data-ttu-id="b6fa3-131">Os objetos nos quais o serviço deve ser executado para o contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-131">The objects on which service must be performed for the service agreement.</span></span>
-  <span data-ttu-id="b6fa3-132">A freqüência com a qual o trabalho é executado e item, despesa e transações de taxa associados são registrados.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-132">The frequency with which work is performed and associated item, expense, and fee transactions are registered.</span></span>
-  <span data-ttu-id="b6fa3-133">A janela de tempo dentro da qual as linhas de ordem de serviço podem ser agrupadas em uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-133">The time window within which service-order lines can be grouped into a service order.</span></span>
-  <span data-ttu-id="b6fa3-134">As tarefas de serviço usadas para agrupar conjuntos de linhas do contrato em tarefas de trabalho e para resumir aos técnicos de serviço e clientes qual a tarefa de serviço a ser fornecida.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-134">The service tasks that are used to group sets of agreement lines together into work tasks and to summarize for service technicians and customers what service task is to be provided.</span></span>
-  <span data-ttu-id="b6fa3-135">Se uma linha for parada.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-135">Whether a line is stopped.</span></span> <span data-ttu-id="b6fa3-136">Se uma linha for parada, não será possível criar ordens de serviço para aquela linha individual.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-136">If a line is stopped, you cannot create service orders for that individual line.</span></span>
-  <span data-ttu-id="b6fa3-137">Configurações do projeto, como a categoria e a propriedade da linha.</span><span class="sxs-lookup"><span data-stu-id="b6fa3-137">Project settings, such as the category and the line property.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b6fa3-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b6fa3-138">Related topics</span></span>

[<span data-ttu-id="b6fa3-139">Criar contratos de serviço</span><span class="sxs-lookup"><span data-stu-id="b6fa3-139">Create service agreements</span></span>](create-service-agreements.md)

