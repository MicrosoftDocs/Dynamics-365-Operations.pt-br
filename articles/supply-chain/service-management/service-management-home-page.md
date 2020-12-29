---
title: Visão geral do gerenciamento de serviço
description: Use Gerenciamento de serviço para estabelecer contratos de serviço e subscrições de serviço, lidar com ordens de serviço e consultas de cliente e gerenciar e analisar a entrega de serviços a clientes.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 451aeebd46d60251eed940016486509c4aa3f458
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4421873"
---
# <a name="service-management-overview"></a><span data-ttu-id="84874-103">Visão geral do gerenciamento de serviço</span><span class="sxs-lookup"><span data-stu-id="84874-103">Service management overview</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="84874-104">Use **Gerenciamento de serviço** para estabelecer contratos de serviço e subscrições de serviço, lidar com ordens de serviço e consultas de cliente e gerenciar e analisar a entrega de serviços a clientes.</span><span class="sxs-lookup"><span data-stu-id="84874-104">Use **Service management** to establish service agreements and service subscriptions, handle service orders and customer inquiries, and to manage and analyze the delivery of services to customers.</span></span> <span data-ttu-id="84874-105">É possível usar os contratos de serviço para definir os recursos usados em uma típica visita de serviço.</span><span class="sxs-lookup"><span data-stu-id="84874-105">You can use service agreements to define the resources that are used in a typical service visit.</span></span> <span data-ttu-id="84874-106">Também é possível usar contratos de serviço para exibir como esses recursos são faturados para o cliente.</span><span class="sxs-lookup"><span data-stu-id="84874-106">You can also use service agreements to view how those resources are invoiced to the customer.</span></span> <span data-ttu-id="84874-107">Um contrato de serviço também pode incluir um contrato de nível de serviço que especifica o tempo de resposta padrão e fornece ferramentas para registrar o tempo real.</span><span class="sxs-lookup"><span data-stu-id="84874-107">A service agreement can also include a service level agreement that specifies standard response times, and offers tools to record the actual time.</span></span>

<span data-ttu-id="84874-108">Você pode criar ordens de serviço para gerenciar informações sobre visitas programadas e não programadas por um técnico de serviço a um site do cliente.</span><span class="sxs-lookup"><span data-stu-id="84874-108">You can create service orders to manage information about scheduled and unscheduled visits by a service technician to a customer site.</span></span> <span data-ttu-id="84874-109">As ordens de serviço incluem informações como:</span><span class="sxs-lookup"><span data-stu-id="84874-109">Service orders include information such as:</span></span>

1.  <span data-ttu-id="84874-110">As horas de trabalho que o técnico de serviço executará</span><span class="sxs-lookup"><span data-stu-id="84874-110">The hours of work that the service technician will perform</span></span>

2.  <span data-ttu-id="84874-111">O tipo de serviço ou reparo</span><span class="sxs-lookup"><span data-stu-id="84874-111">The type of service or repair</span></span>

3.  <span data-ttu-id="84874-112">O item para reparo, incluindo detalhes sobre os sintomas e o diagnóstico</span><span class="sxs-lookup"><span data-stu-id="84874-112">The item to repair, including details about the symptoms and diagnosis</span></span>

4.  <span data-ttu-id="84874-113">Algumas despesas e taxas relacionadas ao serviço ou reparo</span><span class="sxs-lookup"><span data-stu-id="84874-113">Any expenses and fees related to the service or repair</span></span>

<span data-ttu-id="84874-114">É possível receber, processar e expedir solicitações de serviços.</span><span class="sxs-lookup"><span data-stu-id="84874-114">You can receive, process, and dispatch service requests.</span></span> <span data-ttu-id="84874-115">Depois de criar uma ordem de serviço, você pode usar as fases de serviço para monitorar o andamento e especificar as regras que controlam quais ações estão habilitadas em cada fase.</span><span class="sxs-lookup"><span data-stu-id="84874-115">After you have created a service order, you can use service stages to monitor progress and specify rules that control what actions are enabled in each stage.</span></span> <span data-ttu-id="84874-116">Quando uma ordem de serviço é concluída, você pode se desconectar da ordem para confirmar que está concluída e lançar a ordem para iniciar o processo da fatura.</span><span class="sxs-lookup"><span data-stu-id="84874-116">When a service order is complete, you can sign off on the order to confirm that it is complete, and then post the order to start the invoice process.</span></span>

<span data-ttu-id="84874-117">Use as ferramentas de relatório para monitorar transações de subscrição e margens da ordem de serviço e descrições de trabalho de impressão e recebimentos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="84874-117">Use the reporting tools to monitor service order margins and subscription transactions, and print work descriptions and work receipts.</span></span>

## <a name="business-processes"></a><span data-ttu-id="84874-118">Processos empresariais</span><span class="sxs-lookup"><span data-stu-id="84874-118">Business processes</span></span>

<span data-ttu-id="84874-119">O diagrama a seguir ilustra os processos de negócios de alto nível para **Gerenciamento de serviço** e mostra onde os processos de serviço se integram a outros módulos.</span><span class="sxs-lookup"><span data-stu-id="84874-119">The following diagram illustrates the high level business processes for **Service management**, and shows where service processes integrate with other modules.</span></span>

<span data-ttu-id="84874-120">[![Diagrama de processos de negócios do gerenciamento de serviços](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span><span class="sxs-lookup"><span data-stu-id="84874-120">[![Service management business process diagram](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span></span>

## <a name="service-management-at-a-glance"></a><span data-ttu-id="84874-121">Visão geral do gerenciamento de serviços</span><span class="sxs-lookup"><span data-stu-id="84874-121">Service management at a glance</span></span>

|<span data-ttu-id="84874-122">Tarefas importantes</span><span class="sxs-lookup"><span data-stu-id="84874-122">Important tasks</span></span>           | <span data-ttu-id="84874-123">Páginas principais</span><span class="sxs-lookup"><span data-stu-id="84874-123">Primary pages</span></span>                         |<span data-ttu-id="84874-124">Relatórios conhecidos</span><span class="sxs-lookup"><span data-stu-id="84874-124">Popular reports</span></span>              |
|--------------------------|---------------------------------------|-----------------------------|
|<span data-ttu-id="84874-125">Cumprir contratos de serviço</span><span class="sxs-lookup"><span data-stu-id="84874-125">Fulfill service agreements</span></span>|<span data-ttu-id="84874-126">Contratos de serviço</span><span class="sxs-lookup"><span data-stu-id="84874-126">Service agreements</span></span>                     |<span data-ttu-id="84874-127">Margem de ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="84874-127">Service order margin</span></span>         |
|<span data-ttu-id="84874-128">Tratar consultas de cliente</span><span class="sxs-lookup"><span data-stu-id="84874-128">Handle customer inquiries</span></span> |<span data-ttu-id="84874-129">Ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="84874-129">Service orders</span></span>                         |<span data-ttu-id="84874-130">Descrição do trabalho</span><span class="sxs-lookup"><span data-stu-id="84874-130">Work description</span></span>             |
|                          |<span data-ttu-id="84874-131">Quadro de expedição</span><span class="sxs-lookup"><span data-stu-id="84874-131">Dispatch board</span></span>                         |<span data-ttu-id="84874-132">Transação - Subscrição</span><span class="sxs-lookup"><span data-stu-id="84874-132">Transaction - subscription</span></span>   |
|                          |                                       |<span data-ttu-id="84874-133">Transações de taxa de subscrição</span><span class="sxs-lookup"><span data-stu-id="84874-133">Subscription fee transactions</span></span>|


## <a name="integration-of-service-management"></a><span data-ttu-id="84874-134">Integração do gerenciamento de serviços</span><span class="sxs-lookup"><span data-stu-id="84874-134">Integration of Service management</span></span>

<span data-ttu-id="84874-135">O gerenciamento de serviços pode ser integrado aos seguintes módulos:</span><span class="sxs-lookup"><span data-stu-id="84874-135">Service management can be integrated with the following modules:</span></span>

  - [<span data-ttu-id="84874-136">Visão geral de vendas e marketing</span><span class="sxs-lookup"><span data-stu-id="84874-136">Sales and marketing overview</span></span>](../sales-marketing/overview-sales-marketing.md)
  - [<span data-ttu-id="84874-137">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="84874-137">Human resources</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/index)

  

