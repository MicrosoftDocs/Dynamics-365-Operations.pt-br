---
title: "Contratos de nível de serviço"
description: "Em um contrato de nível de serviço, o cliente concorda com um tempo de resposta mínimo com base em quando a empresa de serviços registra o problema até que ele seja resolvido."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServicelevelagreement
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
ms.openlocfilehash: cffe3a7766502dd5d888a7a99a32150967911301
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---

# <a name="service-level-agreements"></a><span data-ttu-id="275f2-103">Contratos de nível de serviço</span><span class="sxs-lookup"><span data-stu-id="275f2-103">Service level agreements</span></span>        

[!include [banner](../includes/banner.md)]


<span data-ttu-id="275f2-104">Um contrato de nível de serviço (SLA) é um contrato entre uma empresa de serviços e um cliente de serviços.</span><span class="sxs-lookup"><span data-stu-id="275f2-104">A service level agreement (SLA) is an agreement between a service company and a service customer.</span></span> <span data-ttu-id="275f2-105">Em um SLA, o cliente concorda com um tempo de resposta mínimo que vai do momento em que a empresa de serviços registra o problema até o momento em que o problema é resolvido.</span><span class="sxs-lookup"><span data-stu-id="275f2-105">In a SLA, the customer agrees to a minimum response time based on when the service company records the issue and when the issue is resolved.</span></span>

<span data-ttu-id="275f2-106">Um SLA garante que um nível padrão de serviço seja oferecido aos clientes e também deixa transparente para uma empresa de serviços quando um serviço deve ser concluído.</span><span class="sxs-lookup"><span data-stu-id="275f2-106">A SLA enforces a standard level of service that is offered to customers, and also makes it transparent to a service company when a service job should be completed.</span></span>

<span data-ttu-id="275f2-107">Pode-se criar qualquer número de SLAs para oferecer aos clientes de serviços níveis diferentes de serviço.</span><span class="sxs-lookup"><span data-stu-id="275f2-107">Any number of SLAs can be created to offer service customers different levels of service.</span></span>

## <a name="create-a-service-level-agreement"></a><span data-ttu-id="275f2-108">Criar um contrato de nível de serviço</span><span class="sxs-lookup"><span data-stu-id="275f2-108">Create a service level agreement</span></span>

1.  <span data-ttu-id="275f2-109">Clique em **Gerenciamento de serviços** \> **Configuração** \> **Contratos de serviço** \> **Contratos de nível de serviço**.</span><span class="sxs-lookup"><span data-stu-id="275f2-109">Click **Service management** \> **Setup** \> **Service agreements** \> **Service level agreements**.</span></span>

2.  <span data-ttu-id="275f2-110">Digite um nome para esse contrato de nível de serviço no campo **Contrato de nível de serviço**.</span><span class="sxs-lookup"><span data-stu-id="275f2-110">Type a name for the service level agreement in the **Service level agreement** field.</span></span>

3.  <span data-ttu-id="275f2-111">Digite o tempo que deseja reservar a conclusão das chamadas de serviço anexadas ao contrato de nível de serviço.</span><span class="sxs-lookup"><span data-stu-id="275f2-111">Type the time that you want to allow for completion of service calls that are attached to the service level agreement.</span></span> <span data-ttu-id="275f2-112">Selecione um calendário se você deseja basear o contrato de nível de serviço em um calendário específico.</span><span class="sxs-lookup"><span data-stu-id="275f2-112">Then select a calendar if you want to base the service level agreement on a specific calendar.</span></span>

## <a name="apply-a-service-level-agreement"></a><span data-ttu-id="275f2-113">Aplicar um contrato de nível de serviço</span><span class="sxs-lookup"><span data-stu-id="275f2-113">Apply a service level agreement</span></span>

<span data-ttu-id="275f2-114">O SLA é aplicado diretamente a um contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="275f2-114">The SLA is applied directly to a service agreement.</span></span>

<span data-ttu-id="275f2-115">As ordens de serviço criadas manualmente e anexadas a um contrato de serviço com um SLA são medidas contra esse SLA.</span><span class="sxs-lookup"><span data-stu-id="275f2-115">Service orders that you create manually and attach to a service agreement that has an SLA are measured against that SLA.</span></span>

<span data-ttu-id="275f2-116">As ordens de serviço criadas automaticamente não são associadas a um SLA.</span><span class="sxs-lookup"><span data-stu-id="275f2-116">Service orders that you create automatically are not attached to an SLA.</span></span>

## <a name="apply-the-service-level-agreement-to-the-service-agreement"></a><span data-ttu-id="275f2-117">Aplicar o contrato de nível de serviço ao contrato de serviço</span><span class="sxs-lookup"><span data-stu-id="275f2-117">Apply the service level agreement to the service agreement</span></span>

1.  <span data-ttu-id="275f2-118">Clique em **Gerenciamento de serviços** \> **Comum** \> **Contratos de serviço** \> **Contratos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="275f2-118">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span> <span data-ttu-id="275f2-119">Selecione o contrato de serviço para o qual você deseja aplicar um SLA, e clique em **Editar** no **Painel de Ação**.</span><span class="sxs-lookup"><span data-stu-id="275f2-119">Select the service agreement that you want to apply the SLA to, and then click **Edit** on the **Action Pane**.</span></span>

2.  <span data-ttu-id="275f2-120">No campo **Contrato de nível de serviço**, selecione o SLA que deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="275f2-120">In the **Service level agreement** field, select the SLA that you want to assign.</span></span>

## <a name="apply-the-service-level-agreement-to-the-service-agreement-group"></a><span data-ttu-id="275f2-121">Aplicar o contrato de nível de serviço ao grupo de contratos de serviço</span><span class="sxs-lookup"><span data-stu-id="275f2-121">Apply the service level agreement to the service agreement group</span></span>

1.  <span data-ttu-id="275f2-122">Clique em **Gerenciamento de serviços** \> **Configuração** \> **Contratos de serviço** \> **Grupos de contratos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="275f2-122">Click **Service management** \> **Setup** \> **Service agreements** \> **Service agreement groups**.</span></span>

2.  <span data-ttu-id="275f2-123">No campo **Contrato de nível de serviço**, selecione o SLA que deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="275f2-123">In the **Service level agreement** field, select the SLA that you want to assign.</span></span>

## <a name="track-time-on-a-service-order-against-an-sla"></a><span data-ttu-id="275f2-124">Rastrear tempo em uma ordem de serviço contra um SLA</span><span class="sxs-lookup"><span data-stu-id="275f2-124">Track time on a service order against an SLA</span></span>

<span data-ttu-id="275f2-125">Quando você cria uma nova ordem de serviço para um contrato de serviço com um SLA for atribuído, o intervalo de tempo para a entrega de serviço é iniciado, e o sistema rastreie o tempo de entrega.</span><span class="sxs-lookup"><span data-stu-id="275f2-125">When you create a new service order for a service agreement that an SLA is assigned to, the time interval for the delivery of the service is initiated, and the system starts to track the delivery time.</span></span> <span data-ttu-id="275f2-126">Além disso, você pode definir estas opções:</span><span class="sxs-lookup"><span data-stu-id="275f2-126">Additionally, you can set the following options:</span></span>

  - <span data-ttu-id="275f2-127">Você pode iniciar e parar o registro do tempo na ordem de serviço para registrar o tempo total gasto nas ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="275f2-127">You can start and stop time recording on the service order to register the total amount of time that is spent on service orders.</span></span>

  - <span data-ttu-id="275f2-128">Você pode monitorar a conformidade com o intervalo de tempo definido no contrato de nível de serviço.</span><span class="sxs-lookup"><span data-stu-id="275f2-128">You can monitor compliance with the time interval that is set in the service level agreement.</span></span>

  - <span data-ttu-id="275f2-129">Você pode definir códigos de motivo que devem ser definidos se o intervalo de tempo do contrato de nível de serviço for ultrapassado.</span><span class="sxs-lookup"><span data-stu-id="275f2-129">You can define reason codes that must be set if the time interval of the service level agreement is exceeded.</span></span>

## <a name="see-also"></a><span data-ttu-id="275f2-130">Consulte também</span><span class="sxs-lookup"><span data-stu-id="275f2-130">See also</span></span>

[<span data-ttu-id="275f2-131">Exibir a conformidade com contratos de nível de serviço</span><span class="sxs-lookup"><span data-stu-id="275f2-131">View compliance with service level agreements</span></span>](view-compliance-with-service-level-agreements.md)

  



