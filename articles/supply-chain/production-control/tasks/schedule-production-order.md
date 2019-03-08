---
title: Agendar uma ordem de produção
description: Este procedimento mostra como agendar uma ordem de produção.
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob, WrkCtrCapResSum
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 20e7ee023f39cc5d02b0f5b80fbb3ae3ad0c9774
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "346355"
---
# <a name="schedule-a-production-order"></a><span data-ttu-id="d4c71-103">Agendar uma ordem de produção</span><span class="sxs-lookup"><span data-stu-id="d4c71-103">Schedule a production order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d4c71-104">Este procedimento mostra como agendar uma ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="d4c71-104">This procedure shows how to schedule a production order.</span></span> <span data-ttu-id="d4c71-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="d4c71-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="d4c71-106">Este é o terceiro procedimento de sete que explica o ciclo de vida da ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="d4c71-106">This is the third procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="schedule-a-production-order"></a><span data-ttu-id="d4c71-107">Agendar uma ordem de produção</span><span class="sxs-lookup"><span data-stu-id="d4c71-107">Schedule a production order</span></span>
1. <span data-ttu-id="d4c71-108">Vá para Controle de produção > Ordens de produção > Todas as ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="d4c71-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="d4c71-109">Selecione uma ordem de produção com o status Estimado.</span><span class="sxs-lookup"><span data-stu-id="d4c71-109">Select a production order that has the Estimated status.</span></span>  
2. <span data-ttu-id="d4c71-110">No Painel de Ação, clique em Agenda.</span><span class="sxs-lookup"><span data-stu-id="d4c71-110">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="d4c71-111">Clique em Agendar trabalhos.</span><span class="sxs-lookup"><span data-stu-id="d4c71-111">Click Schedule jobs.</span></span>
    * <span data-ttu-id="d4c71-112">Os parâmetros para agendar são configurados nessa página.</span><span class="sxs-lookup"><span data-stu-id="d4c71-112">The parameters for scheduling are set up on this page.</span></span> <span data-ttu-id="d4c71-113">Você pode configurar os parâmetros para usuários específicos ou todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="d4c71-113">You can set up the parameters for specific users or all users.</span></span>  
4. <span data-ttu-id="d4c71-114">No campo Direção do plano, selecione 'Avançar a partir de hoje'.</span><span class="sxs-lookup"><span data-stu-id="d4c71-114">In the Scheduling direction field, select 'Forward from today'.</span></span>
5. <span data-ttu-id="d4c71-115">No campo Data de planejamento, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="d4c71-115">In the Scheduling date field, enter a date.</span></span>
6. <span data-ttu-id="d4c71-116">Marque ou desmarque a caixa de seleção Capacidade finita.</span><span class="sxs-lookup"><span data-stu-id="d4c71-116">Select or clear the Finite capacity check box.</span></span>
7. <span data-ttu-id="d4c71-117">Marque ou desmarque a caixa de seleção Material finito.</span><span class="sxs-lookup"><span data-stu-id="d4c71-117">Select or clear the Finite material check box.</span></span>
8. <span data-ttu-id="d4c71-118">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d4c71-118">Click OK.</span></span>

## <a name="view-the-scheduling-results"></a><span data-ttu-id="d4c71-119">Exiba os resultados do agendamento</span><span class="sxs-lookup"><span data-stu-id="d4c71-119">View the scheduling results</span></span>
1. <span data-ttu-id="d4c71-120">No Painel de Ação, clique em Ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="d4c71-120">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="d4c71-121">Clique em Todos os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="d4c71-121">Click All jobs.</span></span>
    * <span data-ttu-id="d4c71-122">Essa página exibe os trabalhos programados que você acabou de gerar.</span><span class="sxs-lookup"><span data-stu-id="d4c71-122">This page displays the scheduled jobs that you have just generated.</span></span>  
3. <span data-ttu-id="d4c71-123">Expanda ou recolha a seção Plano.</span><span class="sxs-lookup"><span data-stu-id="d4c71-123">Expand or collapse the Scheduling section.</span></span>
    * <span data-ttu-id="d4c71-124">Na Guia Rápida Programação, você pode exibir a data e a hora programadas.</span><span class="sxs-lookup"><span data-stu-id="d4c71-124">On the Scheduling FastTab, you can view the scheduled date and time.</span></span>  
4. <span data-ttu-id="d4c71-125">Clique em Consultas.</span><span class="sxs-lookup"><span data-stu-id="d4c71-125">Click Inquiries.</span></span>
5. <span data-ttu-id="d4c71-126">Clique em Capacidade máxima.</span><span class="sxs-lookup"><span data-stu-id="d4c71-126">Click Capacity load.</span></span>
    * <span data-ttu-id="d4c71-127">A página Capacidade máxima exibe a capacidade reservada com o agendamento do trabalho, o número total de horas que está reservado no recurso atualmente, e o número de horas que permanece disponível para o planejamento de trabalho do recurso.</span><span class="sxs-lookup"><span data-stu-id="d4c71-127">The Capacity load page displays the capacity that is reserved through job scheduling, the total number of hours that are currently reserved on the resource, and the number of hours that remain available for job scheduling on the resource.</span></span>  
6. <span data-ttu-id="d4c71-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d4c71-128">Close the page.</span></span>
7. <span data-ttu-id="d4c71-129">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d4c71-129">Close the page.</span></span>

