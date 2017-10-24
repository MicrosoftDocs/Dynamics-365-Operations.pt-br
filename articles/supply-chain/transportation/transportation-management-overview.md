---
title: "Visão geral de gerenciamento de transporte"
description: "Este tópico fornece uma visão geral da funcionalidade de gerenciamento de transporte no Microsoft Dynamics 365 for Finance and Operations."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 30251
ms.assetid: d4e3550c-bca8-469c-82df-56ac0083e4ac
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1c71c8f6c4f94342ac18cbfb7dfbc02ddb3f9f35
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="transportation-management-overview"></a><span data-ttu-id="f5ba7-103">Visão geral de gerenciamento de transporte</span><span class="sxs-lookup"><span data-stu-id="f5ba7-103">Transportation management overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="f5ba7-104">Este tópico fornece uma visão geral da funcionalidade de gerenciamento de transporte no Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-104">This topic gives an overview of the transportation management functionality in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="f5ba7-105">O gerenciamento de transporte permite que você gerencie o transporte de sua empresa e também permite que você identifique soluções de fornecedor e de roteiro para ordens de entrada e de saída.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-105">Transportation management lets you use your company’s transportation, and also lets you identify vendor and routing solutions for inbound and outbound orders.</span></span> <span data-ttu-id="f5ba7-106">Por exemplo, você pode identificar o roteiro mais rápido ou a taxa menos dispendiosa para uma remessa.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-106">For example, you can identify the fastest route or the least expensive rate for a shipment.</span></span> <span data-ttu-id="f5ba7-107">A tabela a seguir descreve os principais cenários para o uso do Gerenciamento de transporte no Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-107">The following table describes the main scenarios for using Transportation management in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5ba7-108">Cenário</span><span class="sxs-lookup"><span data-stu-id="f5ba7-108">Scenario</span></span></th>
<th><span data-ttu-id="f5ba7-109">Como o Gerenciamento de transporte pode ajudar</span><span class="sxs-lookup"><span data-stu-id="f5ba7-109">How Transportation management can help</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f5ba7-110">Use fornecedores externos de logística para atividades de transporte.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-110">Use external logistics providers for transportation activities.</span></span></td>
<td><span data-ttu-id="f5ba7-111">Use o Gerenciamento de transporte para o transporte de entrada e/ou de saída.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-111">Use Transportation management for inbound and/or outbound transportation.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f5ba7-112">A frota própria da empresa está disponível para entrega/retirada, e as taxas de entrega são passadas para os clientes.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-112">The company's own fleet is available for delivery/pickup, and delivery charges are passed on to customers.</span></span></td>
<td><span data-ttu-id="f5ba7-113">Para os processos de saída, você pode usar o Gerenciamento de transporte para determinar os encargos de transporte e passá-los para os clientes.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-113">For the outbound processes, you can use Transportation management to determine the transportation charges and pass them on to customers.</span></span> <span data-ttu-id="f5ba7-114">No entanto, o processo de reconciliação da fatura da transportadora não é necessário.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-114">However, the carrier invoice reconciliation process isn't required.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f5ba7-115">A frota própria da empresa está disponível entrega/retirada, mas as taxas de entrega não são passadas para os clientes, já que os preços dos produtos incluem o transporte.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-115">The company's own fleet is available for delivery/pickup, but delivery charges aren't passed on to customers, because product prices include transportation.</span></span></td>
<td><span data-ttu-id="f5ba7-116">Grande parte da funcionalidade do Gerenciamento de transporte não é necessária.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-116">A lot of the Transportation management functionality isn't required.</span></span> <span data-ttu-id="f5ba7-117">No entanto, você pode usar o Gerenciamento de transporte para determinar as taxas de transporte e ajustar o preço de venda adequadamente.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-117">However, you can use Transportation management to determine the transportation rates and adjust the sales price accordingly.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f5ba7-118">O serviço de logística é fornecido por outra entidade legal na mesma empresa.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-118">Logistics service is provided by another legal entity in the same company.</span></span></td>
<td><ul>
<li><span data-ttu-id="f5ba7-119">Você pode usar o Gerenciamento de transporte ai tratar a outra entidade legal como qualquer outra transportadora.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-119">You can use Transportation management by treating the other legal entity like any other shipping carrier.</span></span> <span data-ttu-id="f5ba7-120">Não é possível automatizar as transações econômicas entre as entidades legais.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-120">You can't automate the economic transactions between legal entities.</span></span> <span data-ttu-id="f5ba7-121">Portanto, você deve lidar com essas transações manualmente (por exemplo, criando uma ordem de compra).</span><span class="sxs-lookup"><span data-stu-id="f5ba7-121">Therefore, you must handle these transactions manually (for example, by creating a purchase order).</span></span></li>
<li><span data-ttu-id="f5ba7-122">Na entidade legal que fornece os serviços de logística, o Gerenciamento de transporte pode ser usado para determinar as taxas de transporte.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-122">In the legal entity that provides the logistics services, Transportation management can be used to determine transportation rates.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="planning-transportation-in-finance-and-operations"></a><span data-ttu-id="f5ba7-123">Planejamento de transporte no Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f5ba7-123">Planning transportation in Finance and Operations</span></span>
<span data-ttu-id="f5ba7-124">No Gerenciamento de transporte, o planejamento de transporte pode se basear em ordens ou nas remessas criadas com base nessas ordens.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-124">In Transportation management, transportation planning can be based either on orders or on the shipments that are created based on those orders.</span></span> <span data-ttu-id="f5ba7-125">As remessas sempre existem em algum momento, mas não são obrigatórias para o planejamento de transporte.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-125">The shipments always exist at some point in time but aren't required for transportation planning.</span></span> <span data-ttu-id="f5ba7-126">As ordens de transferência fazem parte do cenário de saída e podem ser planejadas junto com as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-126">Transfer orders are part of the outbound scenario and can be planned together with sales orders.</span></span> 

![Carregar desenho](./media/Load-drawing1-1024x477.jpg)

## <a name="inbound-transportation"></a><span data-ttu-id="f5ba7-128">Transporte de entrada</span><span class="sxs-lookup"><span data-stu-id="f5ba7-128">Inbound transportation</span></span>
<span data-ttu-id="f5ba7-129">Ao encomendar itens de um fornecedor e os itens devem ser entregues ao seu armazém, convém organizar o transporte dos itens.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-129">When you order items from a vendor, and the items must be delivered to your warehouse, you might want to arrange the transport of the items yourself.</span></span> <span data-ttu-id="f5ba7-130">Você pode usar o Finanças e Operações para planejar o transporte e o recebimento de uma carga de entrada.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-130">You can use Finance and Operations to plan the transportation and receipt of the inbound load.</span></span> <span data-ttu-id="f5ba7-131">A ilustração a seguir mostra o fluxo de processos de negócios para planejar o transporte de uma carga de entrada.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-131">The following illustration shows the business process flow for planning transportation for an inbound load.</span></span> 

![Fluxo de processo comercial para transporte de carga de entrada](./media/Businessprocessflowforinboundloadtransportation.jpg)

## <a name="outbound-transportation"></a><span data-ttu-id="f5ba7-133">Transporte de saída</span><span class="sxs-lookup"><span data-stu-id="f5ba7-133">Outbound transportation</span></span>
<span data-ttu-id="f5ba7-134">É possível planejar e processar uma carga de saída para enviar itens específicos do depósito de uma empresa para um cliente.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-134">You can plan and process an outbound load to ship specific items from a company’s warehouse to a customer.</span></span> <span data-ttu-id="f5ba7-135">Você pode usar o Finanças e Operações para planejar o transporte e a entrega de uma carga de saída.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-135">You can use Finance and Operations to plan the transportation and shipping of an outbound load.</span></span> <span data-ttu-id="f5ba7-136">A ilustração a seguir mostra o fluxo de processos de negócios para planejar e processar cargas de saída para remessa.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-136">The following illustration shows the business process flow for planning and processing outbound loads for shipping.</span></span> 

![Planejamento e processamento de cargas de saída](./media/Planningandprocessingoutboundloads.jpg)

## <a name="load-building"></a><span data-ttu-id="f5ba7-138">Criação de carga</span><span class="sxs-lookup"><span data-stu-id="f5ba7-138">Load building</span></span>
<span data-ttu-id="f5ba7-139">O Finanças e Operações fornece uma estratégia de criação de carga chamada Estratégia de criação de carga com base no volume.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-139">Finance and Operations provides a load building strategy that is named the Volume-based load building strategy.</span></span> <span data-ttu-id="f5ba7-140">Essa estratégia permite usar os valores máximos especificados para a altura e o peso do modelo de carga ou substituí-los pelas configurações por meio da inserção de novos valores.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-140">This strategy lets you use the maximum values that are specified for height and weight in the load template, or you can override the settings by entering new values.</span></span> <span data-ttu-id="f5ba7-141">Para usar essa estratégia, selecione-a no campo **Estratégia de criação de carga** na Guia Rápida **Configuração** da página **Bancada de criação de carga**.</span><span class="sxs-lookup"><span data-stu-id="f5ba7-141">To use this strategy, select it in the **Load building strategy** field on the **Setup** FastTab on the **Load building workbench** page.</span></span> <span data-ttu-id="f5ba7-142">Além disso, você pode adicionar suas próprias estratégias de carga criando uma nova classe na Árvore de Objetos de Aplicativo (AOT).</span><span class="sxs-lookup"><span data-stu-id="f5ba7-142">In addition, you can add your own load-building strategies by creating a new class in the Application Object Tree (AOT).</span></span>




