---
title: "Ordens de serviço"
description: "Uma ordem de serviço representa uma visita de um técnico de serviço a um local de cliente em uma data específica."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 647bbe9cca0167d33048ad07e092708f90b41fc3
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="service-orders"></a><span data-ttu-id="92f6e-103">Ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="92f6e-103">Service orders</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="92f6e-104">Uma ordem de serviço representa uma visita de um técnico de serviço a um local de cliente em uma data específica.</span><span class="sxs-lookup"><span data-stu-id="92f6e-104">A service order represents a visit that a service technician makes to a customer site on a specific date.</span></span> <span data-ttu-id="92f6e-105">Cada ordem de serviço consiste em uma ou mais linhas de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="92f6e-105">Each service order consists of one or more service order lines.</span></span> <span data-ttu-id="92f6e-106">As linhas da ordem de serviço representam as horas de trabalho que deve ser executadas pelo técnico de serviço e os itens, despesas, e taxas relacionados.</span><span class="sxs-lookup"><span data-stu-id="92f6e-106">Service order lines represent the hours of work that must be performed by the service technician, and the related items, expenses, and fees.</span></span>

<span data-ttu-id="92f6e-107">Você pode anexar tarefas e objetos a uma linha de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="92f6e-107">You can attach tasks and objects to a service order line.</span></span> <span data-ttu-id="92f6e-108">Você poderá agrupar linhas de ordem de serviço por tarefa ou por objeto.</span><span class="sxs-lookup"><span data-stu-id="92f6e-108">You can then group service order lines by task or by object.</span></span> <span data-ttu-id="92f6e-109">Também é possível anexar itens listados no estoque a linhas de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="92f6e-109">You can also attach items that are listed in inventory to service order lines.</span></span>

## <a name="create-service-orders"></a><span data-ttu-id="92f6e-110">Criar ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="92f6e-110">Create service orders</span></span>

<span data-ttu-id="92f6e-111">Você pode criar ordens de serviço baseadas em um contrato de serviço e as linhas que estão contidas nesse contrato.</span><span class="sxs-lookup"><span data-stu-id="92f6e-111">You can create service orders based on a service agreement and the lines that are contained in that agreement.</span></span> <span data-ttu-id="92f6e-112">No entanto, você pode criar ordens de serviço associadas a um contrato de serviço somente no período especificado no contrato.</span><span class="sxs-lookup"><span data-stu-id="92f6e-112">However, you can create service orders that are associated with a service agreement only in the period that is specified in the agreement.</span></span> <span data-ttu-id="92f6e-113">Por exemplo, se um contrato de serviço é válido para o ano civil de 2011, você pode criar ordens de serviço para o contrato a partir do dia 1 de janeiro de 2011 ao dia 31 de dezembro de 2011.</span><span class="sxs-lookup"><span data-stu-id="92f6e-113">For example, if a service agreement is valid for the 2011 calendar year, you can create service orders for the agreement from January 1, 2011, and December 31, 2011.</span></span>

<span data-ttu-id="92f6e-114">Você também pode criar ordens de serviço individualmente, sem para associá-las a um contrato.</span><span class="sxs-lookup"><span data-stu-id="92f6e-114">You can also create service orders individually, without associating them with an agreement.</span></span> <span data-ttu-id="92f6e-115">Essas ordens de serviço podem ser usadas para manusear visitas não programadas ou ocasionais de serviço.</span><span class="sxs-lookup"><span data-stu-id="92f6e-115">These service orders can be used to handle unscheduled or one-time service visits.</span></span> <span data-ttu-id="92f6e-116">Por exemplo, no mês de março, seu cliente deseja que um serviço seja realizado em duas máquinas, além das máquinas que são especificadas no contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="92f6e-116">For example, in the month of March, your customer wants service to be performed on two machines, in addition to the machines that are specified in the service agreement.</span></span> <span data-ttu-id="92f6e-117">Para essa tarefa, você cria ordens de serviço mas não as associa a um contrato.</span><span class="sxs-lookup"><span data-stu-id="92f6e-117">For this task, you create service orders but do not associate them with an agreement.</span></span>


> [!NOTE]
> <P><span data-ttu-id="92f6e-118">Para criar ordens de serviço que não estão associadas a um contrato de serviço, você deve marcar a caixa de seleção <STRONG>Permitir sem contrato de serviço</STRONG> no formulário <STRONG>Parâmetros de gerenciamento de serviços</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="92f6e-118">To create service orders that are not associated with a service agreement, you must select the <STRONG>Allow without service agreement</STRONG> check box in the <STRONG>Service management parameters</STRONG> form.</span></span></P>

<span data-ttu-id="92f6e-119">**Cenário**</span><span class="sxs-lookup"><span data-stu-id="92f6e-119">**Scenario**</span></span>

<span data-ttu-id="92f6e-120">O cenário a seguir descreve outra situação na qual é útil criar uma ordem de serviço que não esteja associada a um contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="92f6e-120">The following scenario describes another situation where it is useful to create a service order that is not associated with a service agreement.</span></span>

<span data-ttu-id="92f6e-121">A despachante da empresa recebe uma chamada de solicitação de serviço de emergência em um elevador.</span><span class="sxs-lookup"><span data-stu-id="92f6e-121">The company dispatcher receives a call requesting emergency service on an elevator.</span></span> <span data-ttu-id="92f6e-122">Não há tempo para configurar um contrato de serviço e um projeto do serviço.</span><span class="sxs-lookup"><span data-stu-id="92f6e-122">There is no time to set up a service agreement and a project for the service.</span></span> <span data-ttu-id="92f6e-123">Portanto, o despachante cria uma ordem de serviço diretamente no formulário **Ordens de serviço**, anexa a ordem de serviço a um projeto existente, e cria as linhas da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="92f6e-123">Therefore, the dispatcher creates a service order directly in the **Service orders** form, attaches the service order to an existing project, and creates the service order lines.</span></span> <span data-ttu-id="92f6e-124">O despachante também cria uma tarefa ou relação de objeto para uma ordem de serviço existente, para registrar o servo que não é relacionado ao contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="92f6e-124">The dispatcher also creates a task or object relation for an existing service order, to record work that is not related to the service agreement.</span></span> <span data-ttu-id="92f6e-125">Para obter mais informações, consulte [Criar ordens de serviço manualmente](create-service-orders-manually.md) e [Criar relações de tarefa de serviço](create-service-task-relations.md).</span><span class="sxs-lookup"><span data-stu-id="92f6e-125">For more information, see [Create service orders manually](create-service-orders-manually.md) and [Create service task relations](create-service-task-relations.md).</span></span>

## <a name="monitor-the-progress-of-service-orders"></a><span data-ttu-id="92f6e-126">Monitorar o progresso das ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="92f6e-126">Monitor the progress of service orders</span></span>

<span data-ttu-id="92f6e-127">Para monitorar o progresso da ordem de serviço nas diferentes equipes e processos de trabalho, você pode configurar um sistema de etapas e códigos de motivos para as ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="92f6e-127">To monitor the progress of a sales order through the different teams and work processes, you can set up a system of stages and reason codes for service orders.</span></span> <span data-ttu-id="92f6e-128">Para cada fase, você pode especificar as ações que serão permitidas.</span><span class="sxs-lookup"><span data-stu-id="92f6e-128">For each stage, you can specify the actions that are allowed.</span></span> <span data-ttu-id="92f6e-129">Para obter mais informações, consulte [Criar códigos de motivo](create-reason-codes.md).</span><span class="sxs-lookup"><span data-stu-id="92f6e-129">For more information, see [Create reason codes](create-reason-codes.md).</span></span>

<span data-ttu-id="92f6e-130">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="92f6e-130">**Example**</span></span>

<span data-ttu-id="92f6e-131">Uma ordem de serviço é aprovada pelo despachante.</span><span class="sxs-lookup"><span data-stu-id="92f6e-131">A service order is approved by the dispatcher.</span></span> <span data-ttu-id="92f6e-132">O despachante atualiza a fase da ordem de serviço e especifica um código de motivo que indica que a ordem de serviço foi liberada para o técnico de serviço.</span><span class="sxs-lookup"><span data-stu-id="92f6e-132">The dispatcher updates the stage of the service order and specifies a reason code that indicates that the service order has been released to the service technician.</span></span> <span data-ttu-id="92f6e-133">O técnico vai para o local do cliente e executa o serviço.</span><span class="sxs-lookup"><span data-stu-id="92f6e-133">The technician goes to the customer site and performs the service.</span></span>

## <a name="specify-item-requirements-for-service-orders"></a><span data-ttu-id="92f6e-134">Especificar requisições de itens para ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="92f6e-134">Specify item requirements for service orders</span></span>

<span data-ttu-id="92f6e-135">Você pode especificar os itens de estoque que são necessários para as ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="92f6e-135">You can specify the inventory items that are required for service orders.</span></span> <span data-ttu-id="92f6e-136">No entanto, a ordem de serviço deve estar associada a um projeto.</span><span class="sxs-lookup"><span data-stu-id="92f6e-136">However, the service order must be associated with a project.</span></span> <span data-ttu-id="92f6e-137">As requisições de itens para ordens de serviço são processadas através de um projeto.</span><span class="sxs-lookup"><span data-stu-id="92f6e-137">Item requirements for service orders are processed through a project.</span></span> 

<span data-ttu-id="92f6e-138">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="92f6e-138">**Example**</span></span>

<span data-ttu-id="92f6e-139">As ordens de serviço que são criadas do contrato de serviço são processadas pelo despachante.</span><span class="sxs-lookup"><span data-stu-id="92f6e-139">The service orders that are created from the service agreement are processed by the dispatcher.</span></span> <span data-ttu-id="92f6e-140">Na primeira ordem de serviço, o despachante percebe que o técnico de serviço exige uma peça sobressalente importante que não está disponível no estoque.</span><span class="sxs-lookup"><span data-stu-id="92f6e-140">For the first service order, the dispatcher realizes that the service technician requires an important spare part that is not in the on-hand inventory.</span></span> <span data-ttu-id="92f6e-141">Assim, ele cria uma requisição de item para a peça diretamente da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="92f6e-141">Therefore, the dispatcher creates an item requirement for the spare part directly from the service order.</span></span>

## <a name="move-and-post-lines"></a><span data-ttu-id="92f6e-142">Mover e lançar linhas</span><span class="sxs-lookup"><span data-stu-id="92f6e-142">Move and post lines</span></span>

<span data-ttu-id="92f6e-143">Um técnico de serviço retorna de uma visita e depois altera e atualiza as linhas da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="92f6e-143">A service technician returns from a service visit, and then modifies and updates the service order lines.</span></span> <span data-ttu-id="92f6e-144">Durante a visita de serviço, o técnico realiza um serviço que estava agendado para a próxima visita.</span><span class="sxs-lookup"><span data-stu-id="92f6e-144">During the service visit, the technician performed a service job that was scheduled for the next service visit.</span></span> <span data-ttu-id="92f6e-145">Então, o técnico move as linhas da próxima visita de serviço para a visita de serviço atual.</span><span class="sxs-lookup"><span data-stu-id="92f6e-145">Therefore, the technician moves the lines from the next service visit to the current service visit.</span></span> <span data-ttu-id="92f6e-146">Depois, o técnico posta a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="92f6e-146">The technician then posts the service order.</span></span> <span data-ttu-id="92f6e-147">Para obter mais informações, consulte [Mover linhas da ordem de serviço](move-service-order-lines.md).</span><span class="sxs-lookup"><span data-stu-id="92f6e-147">For more information, see [Move service order lines](move-service-order-lines.md).</span></span>

## <a name="cancel-service-orders"></a><span data-ttu-id="92f6e-148">Cancelar ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="92f6e-148">Cancel service orders</span></span>

<span data-ttu-id="92f6e-149">Uma das outras ordens de serviço que foram geradas para o mês de janeiro fica obsoleta porque o trabalho foi cancelado.</span><span class="sxs-lookup"><span data-stu-id="92f6e-149">One of the other service orders that was generated for the month of January becomes obsolete, because the job is canceled.</span></span> <span data-ttu-id="92f6e-150">Portanto, o despachante do serviço cancela a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="92f6e-150">Therefore, the service dispatcher cancels the service order.</span></span> <span data-ttu-id="92f6e-151">Para obter mais informações, consulte [Cancelar ordens de serviço](cancel-service-orders.md).</span><span class="sxs-lookup"><span data-stu-id="92f6e-151">For more information, see [Cancel service orders](cancel-service-orders.md).</span></span>

## <a name="post-from-projects"></a><span data-ttu-id="92f6e-152">Lançar de projetos</span><span class="sxs-lookup"><span data-stu-id="92f6e-152">Post from projects</span></span>

<span data-ttu-id="92f6e-153">No final de cada semana, o despachante quer lançar todas as ordens de serviço que são anexadas a um projeto específico.</span><span class="sxs-lookup"><span data-stu-id="92f6e-153">At the end of each week, the dispatcher wants to post all service orders that are attached to a specific project.</span></span> <span data-ttu-id="92f6e-154">Portanto, a despachante localiza o projeto relevante no formulário **Projetos** e lança as ordens de serviço que foram concluídas.</span><span class="sxs-lookup"><span data-stu-id="92f6e-154">Therefore, the dispatcher locates the relevant project in the **Projects** form and posts the service orders that have been completed.</span></span> <span data-ttu-id="92f6e-155">Para obter mais informações, consulte [Lançar ordens de serviço (formulário de classe)](https://technet.microsoft.com/en-us/library/aa574685\(v=ax.60\)).</span><span class="sxs-lookup"><span data-stu-id="92f6e-155">For more information, see [Post service orders (class form)](https://technet.microsoft.com/en-us/library/aa574685\(v=ax.60\)).</span></span>

## <a name="delete-service-orders"></a><span data-ttu-id="92f6e-156">Excluir ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="92f6e-156">Delete service orders</span></span>

<span data-ttu-id="92f6e-157">Na segunda metade do ano, o cliente decide que as visitas de serviço são pouco frequentes.</span><span class="sxs-lookup"><span data-stu-id="92f6e-157">During the second half of the year, your customer decides that the service visits are too infrequent.</span></span> <span data-ttu-id="92f6e-158">Você deve criar uma nova série de visitas de serviço mais frequentes para o tempo que resta no contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="92f6e-158">You must create a new, more frequent series of service visits for the remaining time on the service agreement.</span></span> <span data-ttu-id="92f6e-159">Então, você deve excluir as ordens de serviço existentes e criar novas.</span><span class="sxs-lookup"><span data-stu-id="92f6e-159">Therefore, you must delete the existing service orders and create new service orders.</span></span> <span data-ttu-id="92f6e-160">Para obter mais informações, consulte [Excluir ordens de serviço](delete-service-orders.md).</span><span class="sxs-lookup"><span data-stu-id="92f6e-160">For more information, see [Delete service orders](delete-service-orders.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="92f6e-161">Consulte também</span><span class="sxs-lookup"><span data-stu-id="92f6e-161">See also</span></span>

<span data-ttu-id="92f6e-162">[Ordens de serviço (formulário)](https://technet.microsoft.com/en-us/library/aa554361\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="92f6e-162">[Service orders (form)](https://technet.microsoft.com/en-us/library/aa554361\(v=ax.60\))</span></span>

  



