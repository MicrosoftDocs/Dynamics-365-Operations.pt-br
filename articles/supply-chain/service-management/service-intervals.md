---
title: "Intervalos de serviço"
description: "O intervalo de serviço indica a frequência com a qual as linhas de ordem de serviço são criadas para linhas de contrato de serviço quando você cria ordens de serviço."
author: ShylaThompson
manager: AnnBe
ms.date: 02/20/2018
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
ms.openlocfilehash: 10078cbd02209126e9655b823fcf844b692a4794
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---

# <a name="service-intervals"></a><span data-ttu-id="1cd49-103">Intervalos de serviço</span><span class="sxs-lookup"><span data-stu-id="1cd49-103">Service intervals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1cd49-104">O intervalo do contrato de serviço indica a frequência com a qual as linhas de ordem de serviço são criadas para linhas de contrato de serviço quando você cria ordens de serviço automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1cd49-104">The service agreement interval indicates the frequency with which service order lines are created for service agreement lines when you create service orders automatically.</span></span>

<span data-ttu-id="1cd49-105">Quando você cria ordens de serviço de maneira automática, as linhas da ordem de serviço são criadas de acordo com o intervalo especificado para a linha de contrato de serviço a partir da data de início da linha do contrato.</span><span class="sxs-lookup"><span data-stu-id="1cd49-105">When you create service orders automatically, service order lines are created according to the interval that you have specified for the service agreement line from the start date of the agreement line.</span></span>

<span data-ttu-id="1cd49-106">Se o campo **Intervalo** de uma linha de contrato de serviço na página **Contratos de serviço** estiver em branco, a linha será um evento ocasional e não será usada para criar ordens de serviço repetidamente.</span><span class="sxs-lookup"><span data-stu-id="1cd49-106">If the **Interval** field of a service agreement line in the **Service agreements** page is blank, the line is a one-time event, and it is not used to create service orders repeatedly.</span></span>

## <a name="example"></a><span data-ttu-id="1cd49-107">exemplo</span><span class="sxs-lookup"><span data-stu-id="1cd49-107">Example</span></span>

<span data-ttu-id="1cd49-108">Este exemplo ilustra como um intervalo de serviço afetará as linhas de contrato de serviço e linhas de ordem de serviço em uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="1cd49-108">This example illustrates how a service interval will affect service agreement lines and service order lines on a service order.</span></span>

### <a name="create-a-service-agreement"></a><span data-ttu-id="1cd49-109">Criar um contrato de serviço</span><span class="sxs-lookup"><span data-stu-id="1cd49-109">Create a service agreement</span></span>

<span data-ttu-id="1cd49-110">Primeiro, crie um contrato de serviço e defina a opção **Combinar ordens de serviço** como **Por contrato de serviço**.</span><span class="sxs-lookup"><span data-stu-id="1cd49-110">First, you create a service agreement and set the **Combine service orders** option to **By service agreement**.</span></span>

1. <span data-ttu-id="1cd49-111">Clique em **Contratos de serviço**</span><span class="sxs-lookup"><span data-stu-id="1cd49-111">Click **Service agreements**</span></span>
2. <span data-ttu-id="1cd49-112">No **Painel de Ação**, na guia **Contrato de serviço**, no grupo **Novo**, clique em **Contrato de serviço** para criar um novo contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="1cd49-112">On the **Action Pane**, on the **Service agreement** tab, in the **New** group, click **Service agreement** to create a new service agreement.</span></span>
3. <span data-ttu-id="1cd49-113">Insira uma descrição, selecione um projeto no campo **ID do projeto** e insira uma data no campo **Data de início**.</span><span class="sxs-lookup"><span data-stu-id="1cd49-113">Enter a description, select a project in the **Project ID** field, and enter a date in the **Start date** field.</span></span>
4. <span data-ttu-id="1cd49-114">No campo **Combinar ordens de serviço**, selecione **Por contrato de serviço**.</span><span class="sxs-lookup"><span data-stu-id="1cd49-114">In the **Combine service orders** field, select **By service agreement**.</span></span>

<span data-ttu-id="1cd49-115">Você criou o seguinte contrato de serviço:</span><span class="sxs-lookup"><span data-stu-id="1cd49-115">You have now created the following service agreement:</span></span>

| <span data-ttu-id="1cd49-116">Project</span><span class="sxs-lookup"><span data-stu-id="1cd49-116">Project</span></span>      | <span data-ttu-id="1cd49-117">Data inicial</span><span class="sxs-lookup"><span data-stu-id="1cd49-117">Start date</span></span>                                                                         |
|--------------|------------------------------------------------------------------------------------|
| <span data-ttu-id="1cd49-118">Seu projeto</span><span class="sxs-lookup"><span data-stu-id="1cd49-118">Your project</span></span> | <span data-ttu-id="1cd49-119">A data especificada para o projeto.</span><span class="sxs-lookup"><span data-stu-id="1cd49-119">The date you specified for the project.</span></span> <span data-ttu-id="1cd49-120">Neste exemplo, a data atual é usada.</span><span class="sxs-lookup"><span data-stu-id="1cd49-120">In this example, the current date is used.</span></span> |

### <a name="create-a-service-agreement-line"></a><span data-ttu-id="1cd49-121">Criar uma linha de contrato de serviço</span><span class="sxs-lookup"><span data-stu-id="1cd49-121">Create a service agreement line</span></span>

<span data-ttu-id="1cd49-122">Em seguida, crie uma linha de contrato de serviço que tenha o tipo de transação **Hora**.</span><span class="sxs-lookup"><span data-stu-id="1cd49-122">Next, you create a service agreement line that has the transaction type **Hour**.</span></span>

<span data-ttu-id="1cd49-123">Para concluir essa parte do exemplo, crie um intervalo de serviço de 10 dias na página **Intervalos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="1cd49-123">To complete this part of the example, you must create a service interval of 10 days in the **Service intervals** page.</span></span> 

1. <span data-ttu-id="1cd49-124">Selecione o contrato de serviço que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="1cd49-124">Select the service agreement that you just created.</span></span> 
2. <span data-ttu-id="1cd49-125">Na Guia Rápida **Linhas**, clique no botão **Adicionar** para criar uma nova linha no painel inferior da página **Contratos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="1cd49-125">On the **Lines** FastTab, click the **Add** button to create a new line in the lower pane of the **Service agreements** page.</span></span>
3. <span data-ttu-id="1cd49-126">No campo **Tipo de transação**, selecione **Hora**.</span><span class="sxs-lookup"><span data-stu-id="1cd49-126">In the **Transaction type** field, select **Hour**.</span></span>
4. <span data-ttu-id="1cd49-127">No campo **Trabalhador**, selecione o trabalhador que fornecerá o serviço.</span><span class="sxs-lookup"><span data-stu-id="1cd49-127">In the **Worker** field, select the worker who will deliver the service.</span></span>
5. <span data-ttu-id="1cd49-128">No campo **Intervalo de serviço**, selecione o intervalo de 10 dias.</span><span class="sxs-lookup"><span data-stu-id="1cd49-128">In the **Service interval** field, select the 10 days interval.</span></span>

<span data-ttu-id="1cd49-129">Você acabou de criar uma linha de contrato de serviço com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="1cd49-129">You have now created a service agreement line with the following information:</span></span>

| <span data-ttu-id="1cd49-130">Tipo de transação</span><span class="sxs-lookup"><span data-stu-id="1cd49-130">Transaction type</span></span> | <span data-ttu-id="1cd49-131">Data de início</span><span class="sxs-lookup"><span data-stu-id="1cd49-131">Start date</span></span>                               | <span data-ttu-id="1cd49-132">Intervalo de serviços</span><span class="sxs-lookup"><span data-stu-id="1cd49-132">Service interval</span></span> |
|------------------|------------------------------------------|------------------|
| <span data-ttu-id="1cd49-133">Hora</span><span class="sxs-lookup"><span data-stu-id="1cd49-133">Hour</span></span>             | <span data-ttu-id="1cd49-134">A data atual.</span><span class="sxs-lookup"><span data-stu-id="1cd49-134">The current date.</span></span>                        | <span data-ttu-id="1cd49-135">A cada 10 dias</span><span class="sxs-lookup"><span data-stu-id="1cd49-135">Every 10 days</span></span>    |
| <span data-ttu-id="1cd49-136">Trabalhador</span><span class="sxs-lookup"><span data-stu-id="1cd49-136">Worker</span></span>           | <span data-ttu-id="1cd49-137">O trabalhador que realizará o serviço.</span><span class="sxs-lookup"><span data-stu-id="1cd49-137">The worker who will perform the service.</span></span> |                  |

<span data-ttu-id="1cd49-138">Nenhuma janela de tempo especificada para a linha.</span><span class="sxs-lookup"><span data-stu-id="1cd49-138">There is no time window specified for the line.</span></span> 

### <a name="create-planned-service-orders"></a><span data-ttu-id="1cd49-139">Criar ordens de serviço planejadas</span><span class="sxs-lookup"><span data-stu-id="1cd49-139">Create planned service orders</span></span>

<span data-ttu-id="1cd49-140">Agora você pode criar ordens de serviço e linhas de ordem de serviço planejadas para o mês seguinte.</span><span class="sxs-lookup"><span data-stu-id="1cd49-140">You can now create planned service orders and service order lines for the coming month.</span></span>

1. <span data-ttu-id="1cd49-141">Na página **Contratos de serviço**, no **Painel de Ação**, na guia **Entregar**, clique em **Ordens de serviço planejadas**.</span><span class="sxs-lookup"><span data-stu-id="1cd49-141">In the **Service agreements** page, on the **Action Pane**, on the **Deliver** tab, click **Planned service orders**.</span></span>
2. <span data-ttu-id="1cd49-142">Na página **Criar ordens de serviço**, insira a data atual no campo **A partir da data** e uma data que seja a um mês da data atual no campo **Até a data**.</span><span class="sxs-lookup"><span data-stu-id="1cd49-142">In the **Create service orders** page, enter the current date in the **From date** field and a date that is one month from the current date in the **To date** field.</span></span>
3. <span data-ttu-id="1cd49-143">Defina o controle deslizante **Hora** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="1cd49-143">Set the **Hour** slider to **Yes**.</span></span> 
4. <span data-ttu-id="1cd49-144">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1cd49-144">Click **OK**.</span></span>

<span data-ttu-id="1cd49-145">Como não há agrupamento na ordem de serviço (definido pela opção **Por contrato de serviço** no campo **Combinar ordens de serviço**), uma linha de ordem de serviço é criada por ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="1cd49-145">Because there is no grouping on the service order (defined by the **By service agreement** option in the **Combine service orders** field), one service order line is created per service order.</span></span>

### <a name="service-orders-created"></a><span data-ttu-id="1cd49-146">Ordens de serviço criadas</span><span class="sxs-lookup"><span data-stu-id="1cd49-146">Service orders created</span></span>

<span data-ttu-id="1cd49-147">Três linhas de ordem de serviço foram criadas nesse intervalo de tempo que você especificou na caixa de diálogo **Criar ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="1cd49-147">Three service order lines have been created within the time frame that you specified in the **Create service orders** dialog box.</span></span> <span data-ttu-id="1cd49-148">Você pode visualizar as linhas da ordem de serviço na página **Contratos de serviço** (**Painel de Ação** \> guia **Entregar** \>botão**Exibir** ).</span><span class="sxs-lookup"><span data-stu-id="1cd49-148">You can view the service order lines in the **Service agreements** page (**Action Pane** \> **Deliver** tab \>**View** button).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1cd49-149">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1cd49-149">Related topics</span></span>

[<span data-ttu-id="1cd49-150">Configurar intervalos de serviço</span><span class="sxs-lookup"><span data-stu-id="1cd49-150">Set up service intervals</span></span>](set-up-service-intervals.md)  


