---
title: "Gerenciamento de serviços"
description: "Use Gerenciamento de serviço para estabelecer contratos de serviço e subscrições de serviço, lidar com ordens de serviço e consultas de cliente e gerenciar e analisar a entrega de serviços a clientes."
author: YuyuScheller
manager: AnnBe
ms.date: 05/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 02cdf4615e2071f2b7de2e86b6f9e6637c6e5d8d
ms.openlocfilehash: 236ab21b2d1c5a4e82270e5381d163e97437cb7f
ms.contentlocale: pt-br
ms.lasthandoff: 05/09/2018

---


# <a name="service-management"></a><span data-ttu-id="d6c6c-103">Gerenciamento de serviços</span><span class="sxs-lookup"><span data-stu-id="d6c6c-103">Service management</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="d6c6c-104">Use **Gerenciamento de serviço** para estabelecer contratos de serviço e subscrições de serviço, lidar com ordens de serviço e consultas de cliente e gerenciar e analisar a entrega de serviços a clientes.</span><span class="sxs-lookup"><span data-stu-id="d6c6c-104">Use **Service management** to establish service agreements and service subscriptions, handle service orders and customer inquiries, and to manage and analyze the delivery of services to customers.</span></span> <span data-ttu-id="d6c6c-105">É possível usar os contratos de serviço para definir os recursos usados em uma típica visita de serviço.</span><span class="sxs-lookup"><span data-stu-id="d6c6c-105">You can use service agreements to define the resources that are used in a typical service visit.</span></span> <span data-ttu-id="d6c6c-106">Também é possível usar contratos de serviço para exibir como esses recursos são faturados para o cliente.</span><span class="sxs-lookup"><span data-stu-id="d6c6c-106">You can also use service agreements to view how those resources are invoiced to the customer.</span></span> <span data-ttu-id="d6c6c-107">Um contrato de serviço também pode incluir um contrato de nível de serviço que especifica o tempo de resposta padrão e fornece ferramentas para registrar o tempo real.</span><span class="sxs-lookup"><span data-stu-id="d6c6c-107">A service agreement can also include a service level agreement that specifies standard response times, and offers tools to record the actual time.</span></span>

<span data-ttu-id="d6c6c-108">Você pode criar ordens de serviço para gerenciar informações sobre visitas programadas e não programadas por um técnico de serviço a um site do cliente.</span><span class="sxs-lookup"><span data-stu-id="d6c6c-108">You can create service orders to manage information about scheduled and unscheduled visits by a service technician to a customer site.</span></span> <span data-ttu-id="d6c6c-109">As ordens de serviço incluem informações como:</span><span class="sxs-lookup"><span data-stu-id="d6c6c-109">Service orders include information such as:</span></span>

1.  <span data-ttu-id="d6c6c-110">As horas de trabalho que o técnico de serviço executará</span><span class="sxs-lookup"><span data-stu-id="d6c6c-110">The hours of work that the service technician will perform</span></span>

2.  <span data-ttu-id="d6c6c-111">O tipo de serviço ou reparo</span><span class="sxs-lookup"><span data-stu-id="d6c6c-111">The type of service or repair</span></span>

3.  <span data-ttu-id="d6c6c-112">O item para reparo, incluindo detalhes sobre os sintomas e o diagnóstico</span><span class="sxs-lookup"><span data-stu-id="d6c6c-112">The item to repair, including details about the symptoms and diagnosis</span></span>

4.  <span data-ttu-id="d6c6c-113">Algumas despesas e taxas relacionadas ao serviço ou reparo</span><span class="sxs-lookup"><span data-stu-id="d6c6c-113">Any expenses and fees related to the service or repair</span></span>

<span data-ttu-id="d6c6c-114">Os clientes podem enviar solicitações de serviço com a Internet usando Portal Empresarial.</span><span class="sxs-lookup"><span data-stu-id="d6c6c-114">Customers can submit service requests through the Internet by using the Enterprise Portal.</span></span> <span data-ttu-id="d6c6c-115">É possível receber, processar e para despachar essas solicitações.</span><span class="sxs-lookup"><span data-stu-id="d6c6c-115">You can receive, process, and dispatch these requests.</span></span> <span data-ttu-id="d6c6c-116">Depois de criar uma ordem de serviço, você pode usar as fases de serviço para monitorar o andamento e especificar as regras que controlam quais ações estão habilitadas em cada fase.</span><span class="sxs-lookup"><span data-stu-id="d6c6c-116">After you have created a service order, you can use service stages to monitor progress and specify rules that control what actions are enabled in each stage.</span></span> <span data-ttu-id="d6c6c-117">Quando uma ordem de serviço é concluída, você pode se desconectar da ordem para confirmar que está concluída e lançar a ordem para iniciar o processo da fatura.</span><span class="sxs-lookup"><span data-stu-id="d6c6c-117">When a service order is complete, you can sign off on the order to confirm that it is complete, and then post the order to start the invoice process.</span></span>

<span data-ttu-id="d6c6c-118">Use as ferramentas de relatório para monitorar transações de subscrição e margens da ordem de serviço e descrições de trabalho de impressão e recebimentos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d6c6c-118">Use the reporting tools to monitor service order margins and subscription transactions, and print work descriptions and work receipts.</span></span>

## <a name="business-processes"></a><span data-ttu-id="d6c6c-119">Processos empresariais</span><span class="sxs-lookup"><span data-stu-id="d6c6c-119">Business processes</span></span>

<span data-ttu-id="d6c6c-120">O diagrama a seguir ilustra os processos comerciais de alto nível para **Gerenciamento de serviço**, e mostra onde processos de serviço se integram com outros módulos no Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d6c6c-120">The following diagram illustrates the high level business processes for **Service management**, and shows where service processes integrate with other modules in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="d6c6c-121">[![Diagrama de processos de negócios do gerenciamento de serviços](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span><span class="sxs-lookup"><span data-stu-id="d6c6c-121">[![Service management business process diagram](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span></span>

## <a name="service-management-at-a-glance"></a><span data-ttu-id="d6c6c-122">Visão geral do gerenciamento de serviços</span><span class="sxs-lookup"><span data-stu-id="d6c6c-122">Service management at a glance</span></span>

<table>
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="d6c6c-123">Tarefas importantes</span><span class="sxs-lookup"><span data-stu-id="d6c6c-123">Important tasks</span></span></p></th>
<th><p><span data-ttu-id="d6c6c-124">Principais formulários</span><span class="sxs-lookup"><span data-stu-id="d6c6c-124">Primary forms</span></span></p></th>
<th><p><span data-ttu-id="d6c6c-125">Relatórios conhecidos</span><span class="sxs-lookup"><span data-stu-id="d6c6c-125">Popular reports</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6c6c-126">Preencher contrato de serviço</span><span class="sxs-lookup"><span data-stu-id="d6c6c-126">Fulfill service agreements</span></span></a></p></td>
<td><p><span data-ttu-id="d6c6c-127"><a href="https://technet.microsoft.com/en-us/library/aa617823(v=ax.60)">Contratos de serviço (formulário)</a></span><span class="sxs-lookup"><span data-stu-id="d6c6c-127"><a href="https://technet.microsoft.com/en-us/library/aa617823(v=ax.60)">Service agreements (form)</a></span></span></p></td>
<td><p><span data-ttu-id="d6c6c-128"><strong>Margem de ordem de serviço</strong></span><span class="sxs-lookup"><span data-stu-id="d6c6c-128"><strong>Service order margin</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6c6c-129">Tratar consultas de cliente</span><span class="sxs-lookup"><span data-stu-id="d6c6c-129">Handle customer inquiries</span></span></a></p></td>
<td><p><span data-ttu-id="d6c6c-130"><a href="https://technet.microsoft.com/en-us/library/aa554361(v=ax.60)">Ordens de serviço (formulário)</a></span><span class="sxs-lookup"><span data-stu-id="d6c6c-130"><a href="https://technet.microsoft.com/en-us/library/aa554361(v=ax.60)">Service orders (form)</a></span></span></p></td>
<td><p><span data-ttu-id="d6c6c-131"><strong>Descrição do trabalho</strong></span><span class="sxs-lookup"><span data-stu-id="d6c6c-131"><strong>Work description</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="d6c6c-132"><a href="https://technet.microsoft.com/en-us/library/hh242789(v=ax.60)">Quadro de expedição (formulário)</a></span><span class="sxs-lookup"><span data-stu-id="d6c6c-132"><a href="https://technet.microsoft.com/en-us/library/hh242789(v=ax.60)">Dispatch board (form)</a></span></span></p></td>
<td><p><span data-ttu-id="d6c6c-133"><strong>Transação - Subscrição</strong></span><span class="sxs-lookup"><span data-stu-id="d6c6c-133"><strong>Transaction - subscription</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="d6c6c-134"><strong>Transações de taxa de subscrição</strong></span><span class="sxs-lookup"><span data-stu-id="d6c6c-134"><strong>Subscription fee transactions</strong></span></span></p></td>
</tr>
</tbody>
</table>


## <a name="integration-of-service-management"></a><span data-ttu-id="d6c6c-135">Integração do gerenciamento de serviços</span><span class="sxs-lookup"><span data-stu-id="d6c6c-135">Integration of Service management</span></span>

<span data-ttu-id="d6c6c-136">O gerenciamento de serviço pode ser integrado aos seguintes módulos no Microsoft Dynamics 365 for Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="d6c6c-136">Service management can be integrated with the following modules in Microsoft Dynamics 365 for Finance and Operations:</span></span>

  - [<span data-ttu-id="d6c6c-137">Vendas e marketing</span><span class="sxs-lookup"><span data-stu-id="d6c6c-137">Sales and marketing</span></span>](../sales-marketing/overview-sales-marketing.md)

  - [<span data-ttu-id="d6c6c-138">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="d6c6c-138">Human resources</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/index)

  


