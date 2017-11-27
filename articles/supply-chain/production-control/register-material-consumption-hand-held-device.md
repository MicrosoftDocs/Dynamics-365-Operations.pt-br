---
title: "Registrar o consumo de materiais usando um dispositivo móvel"
description: "Este tópico descreve um fluxo de trabalho que permite o registro do consumo de matéria-prima na produção usando um dispositivo portátil."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.custom: 1706093
ms.assetid: 75ee68e0-4b9f-4f4d-b286-f498e0eb73fa
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 525b5a21047f0f39b9cd15448c4096d17c0e2dbd
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="register-material-consumption-using-a-mobile-device"></a><span data-ttu-id="f115e-103">Registrar o consumo de materiais usando um dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="f115e-103">Register material consumption using a mobile device</span></span>
<span data-ttu-id="f115e-104">Este tópico descreve um fluxo de trabalho que permite o registro do consumo de matéria-prima na produção usando um dispositivo portátil.</span><span class="sxs-lookup"><span data-stu-id="f115e-104">This topic describes a workflow that enables registration of raw material consumption in production by using a handheld device.</span></span>

<a name="introduction"></a><span data-ttu-id="f115e-105">Introdução</span><span class="sxs-lookup"><span data-stu-id="f115e-105">Introduction</span></span>
------------

<span data-ttu-id="f115e-106">Este fluxo de trabalho é relevante se houver um requisito rigoroso para a rastreabilidade do material.</span><span class="sxs-lookup"><span data-stu-id="f115e-106">This workflow is relevant if there is a strict requirement for material traceability.</span></span> <span data-ttu-id="f115e-107">Nesses casos, para manter a rastreabilidade dos materiais, o tempo e a quantidade exatos devem ser relatados para o consumo.</span><span class="sxs-lookup"><span data-stu-id="f115e-107">In those cases, to maintain traceability of the materials, the exact time and quantity must be reported for the consumption.</span></span> <span data-ttu-id="f115e-108">Este processo pode ser visto em oposição às operações de pré-lavagem ou retrocesso, onde há um deslocamento entre o momento do registro e o tempo em que o consumo real ocorre.</span><span class="sxs-lookup"><span data-stu-id="f115e-108">This process can be seen as opposed to pre- or back-flushing operations, where there is an offset between the time of registration and the time when the actual consumption takes place.</span></span> <span data-ttu-id="f115e-109">Isso explica por que uma estratégia de consumo automático não pode ser usada para alguns materiais com requisitos de rastreabilidade.</span><span class="sxs-lookup"><span data-stu-id="f115e-109">This explains why a strategy of automatic consumption cannot be used for some materials with traceability requirements.</span></span> <span data-ttu-id="f115e-110">Vejamos um cenário simples que explica como configurar um fluxo de trabalho para permitir o registro do consumo de matéria-prima na produção, usando um dispositivo portátil.</span><span class="sxs-lookup"><span data-stu-id="f115e-110">Let’s look at a simple scenario that explains how to set up a workflow to enable registration of raw material consumption in production by using a handheld device.</span></span> <span data-ttu-id="f115e-111">[![configurar um fluxo de trabalho para habilitar o registro de consumo de matéria-prima usando um dispositivo portátil](./media/scenario3.png)](./media/scenario3.png)</span><span class="sxs-lookup"><span data-stu-id="f115e-111">[![set up a workflow to enable registration of raw material consumption by using a handheld device](./media/scenario3.png)](./media/scenario3.png)</span></span>

### <a name="scenario-details"></a><span data-ttu-id="f115e-112">Detalhes do cenário</span><span class="sxs-lookup"><span data-stu-id="f115e-112">Scenario details</span></span>

<span data-ttu-id="f115e-113">Um processo contínuo de produção (5) consome a matéria-prima controlada por lote RM-100.</span><span class="sxs-lookup"><span data-stu-id="f115e-113">A continuous production process (5) consumes the batch-controlled raw material RM-100.</span></span> <span data-ttu-id="f115e-114">O material está disponível no local Bulk-001 (1) na placa PL-1 com dois lotes, B1 e B2, ambos com uma quantidade de 100 lbs.</span><span class="sxs-lookup"><span data-stu-id="f115e-114">The material is on-hand on location Bulk-001 (1) on license plate PL-1 with two batches, B1 and B2, both with a quantity of 100 lbs.</span></span> <span data-ttu-id="f115e-115">O trabalho de depósito (2) é liberado e processado para RM-100 e o material é colhido de Bulk-001 para o local de entrada de produção PIL-01 (3), que é definido como não-placa de matrícula controlada.</span><span class="sxs-lookup"><span data-stu-id="f115e-115">Warehouse work (2) is released and processed for RM-100, and the material is picked from Bulk-001 to the production input location PIL-01 (3), which is defined as non-license plate controlled.</span></span> <span data-ttu-id="f115e-116">O operador da máquina pesa o material do local de entrada de produção (3) e registra o peso e o número do lote como consumido (4).</span><span class="sxs-lookup"><span data-stu-id="f115e-116">The machine operator weighs out material from the production input location (3) and registers the weight and batch number as consumed (4).</span></span> <span data-ttu-id="f115e-117">Do local de entrada de produção, uma parte do material é adicionada manualmente ao processo de produção em intervalos de tempo definidos.</span><span class="sxs-lookup"><span data-stu-id="f115e-117">From the production input location, a portion of the material is manually added to the production process in defined time intervals.</span></span> <span data-ttu-id="f115e-118">Quando o operador da máquina adiciona material, é pesado em uma escala e o número do lote é registrado.</span><span class="sxs-lookup"><span data-stu-id="f115e-118">When the machine operator adds material, it is weighed on a scale and the batch number is registered.</span></span>

## <a name="set-up-the-workflow-to-register-consumption-using-a-handheld-device"></a><span data-ttu-id="f115e-119">Configure o fluxo de trabalho para registrar o consumo usando um dispositivo de mão</span><span class="sxs-lookup"><span data-stu-id="f115e-119">Set up the workflow to register consumption using a handheld device</span></span>
<span data-ttu-id="f115e-120">Crie um produto acabado-bom, FG-100, com uma lista de materiais que possui a matéria-prima MR-100 controlada por lote.</span><span class="sxs-lookup"><span data-stu-id="f115e-120">Create a finished-good product, FG-100, with a bill of material that has the batch-controlled raw material RM-100.</span></span> <span data-ttu-id="f115e-121">Adicione dois lotes, B1 e B2, de RM-100 em uma quantidade de 100 para o local: Bulk-001 na placa: PL-1.</span><span class="sxs-lookup"><span data-stu-id="f115e-121">Add two batches, B1 and B2, of RM-100 in a quantity of 100 to location: Bulk-001 on license plate: PL-1.</span></span> <span data-ttu-id="f115e-122">O princípio de liberação na linha da lista de materiais para RM-100 é **Manual**.</span><span class="sxs-lookup"><span data-stu-id="f115e-122">The flushing principle on the bill of material line for RM-100 is set to **Manual**.</span></span> <span data-ttu-id="f115e-123">Defina a localização da entrada de produção para PIL-01.</span><span class="sxs-lookup"><span data-stu-id="f115e-123">Set  the production input location to PIL-01.</span></span> <span data-ttu-id="f115e-124">Você pode fazer isso selecionando esta localização como a localização de entrada de produção padrão no depósito 51.</span><span class="sxs-lookup"><span data-stu-id="f115e-124">You can do that by selecting this location as the default production input location on warehouse 51.</span></span>

1.  <span data-ttu-id="f115e-125">Crie um novo item de menu de dispositivo móvel:</span><span class="sxs-lookup"><span data-stu-id="f115e-125">Create a new mobile device menu item:</span></span> 

-    <span data-ttu-id="f115e-126">**Nome do item de menu** - Registrar consumo de material.</span><span class="sxs-lookup"><span data-stu-id="f115e-126">**Menu item name** - Register material consumption.</span></span> 
-    <span data-ttu-id="f115e-127">**Título** - Registrar consumo de material.</span><span class="sxs-lookup"><span data-stu-id="f115e-127">**Title** - Register material consumption.</span></span> 
-    <span data-ttu-id="f115e-128">**Modo** - Indireto.</span><span class="sxs-lookup"><span data-stu-id="f115e-128">**Mode** - Indirect.</span></span> 
-    <span data-ttu-id="f115e-129">**Código de atividade** - Registrar consumo de material.</span><span class="sxs-lookup"><span data-stu-id="f115e-129">**Activity code** - Register material consumption.</span></span>

2.  <span data-ttu-id="f115e-130">Adicione o item de menu ao menu de dispositivo **Produção móvel**.</span><span class="sxs-lookup"><span data-stu-id="f115e-130">Add the menu item to the **Production Mobile** device menu.</span></span>
3.  <span data-ttu-id="f115e-131">Crie uma ordem de produção para o produto concluído:</span><span class="sxs-lookup"><span data-stu-id="f115e-131">Create a production order for the finished product:</span></span> 

-    <span data-ttu-id="f115e-132">**Número do item** - FG-100</span><span class="sxs-lookup"><span data-stu-id="f115e-132">**Item number** - FG-100</span></span> 
-    <span data-ttu-id="f115e-133">**Local** - 5</span><span class="sxs-lookup"><span data-stu-id="f115e-133">**Site** - 5</span></span> 
-    <span data-ttu-id="f115e-134">**Depósito** - 51</span><span class="sxs-lookup"><span data-stu-id="f115e-134">**Warehouse** - 51</span></span> 
-    <span data-ttu-id="f115e-135">**Quantidade** - 150</span><span class="sxs-lookup"><span data-stu-id="f115e-135">**Quantity** - 150</span></span>

<span data-ttu-id="f115e-136">A ordem de produção é **Estimada** e **Liberada** e o trabalho de depósito é criado.</span><span class="sxs-lookup"><span data-stu-id="f115e-136">The production order is **Estimated** and **Released** and warehouse work is created.</span></span>

4.  <span data-ttu-id="f115e-137">Complete o trabalho usando o fluxo de trabalho para a escolha da matéria-prima para o dispositivo portátil.</span><span class="sxs-lookup"><span data-stu-id="f115e-137">Complete the work using the workflow for raw material picking for the handheld device.</span></span>

<span data-ttu-id="f115e-138">Isso trará o material da localização em massa para o local de entrada de produção PIL-01.</span><span class="sxs-lookup"><span data-stu-id="f115e-138">This will bring the material from the bulk location to the production input location PIL-01.</span></span> <span data-ttu-id="f115e-139">Depois que o trabalho for concluído, o material terá o status **Escolhido no local de entrada de produção**.</span><span class="sxs-lookup"><span data-stu-id="f115e-139">After the work is completed, the material has the status **Picked on the production input location**.</span></span> <span data-ttu-id="f115e-140">O status depois que os trabalhos foram processados pode ser **Separado** ou **Reservado**.</span><span class="sxs-lookup"><span data-stu-id="f115e-140">The status after work has been processed can be either **Picked** or **Reserved physical**.</span></span> <span data-ttu-id="f115e-141">Isso é configurado com o parâmetro **Status da emissão depois de colocar no formulário do depósito**.</span><span class="sxs-lookup"><span data-stu-id="f115e-141">This is configured with the parameter **Issue status after put on the warehouse form**.</span></span>

5.  <span data-ttu-id="f115e-142">Inicie a ordem de produção a partir do cliente ou do dispositivo portátil usando o item de menu **Início da produção**.</span><span class="sxs-lookup"><span data-stu-id="f115e-142">Start the production order either from the client or from the handheld device by using the **Production start** menu item.</span></span>

<span data-ttu-id="f115e-143">Depois que a ordem de produção for iniciada, você pode registrar o consumo de material com o fluxo de trabalho do dispositivo portátil.</span><span class="sxs-lookup"><span data-stu-id="f115e-143">After the production order has been started, you can register material consumption with the workflow for the handheld device.</span></span> <span data-ttu-id="f115e-144">Vamos começar registrando o consumo de 25 lbs do lote B1.</span><span class="sxs-lookup"><span data-stu-id="f115e-144">Let's start by registering consumption of 25 lbs of batch B1.</span></span>

6.  <span data-ttu-id="f115e-145">Selecione o item de menu **Registrar consumo de** **material** no menu para o dispositivo portátil, e insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="f115e-145">Select the **Register material** **consumption** menu item in the menu for the hand held device, enter the following details:</span></span> 

-    <span data-ttu-id="f115e-146">O número da ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="f115e-146">The production order number.</span></span> 
-    <span data-ttu-id="f115e-147">A localização em que o material será consumido, neste caso PIL-01.</span><span class="sxs-lookup"><span data-stu-id="f115e-147">The location on which the material is going to be consumed, in this case PIL-01.</span></span> 
-    <span data-ttu-id="f115e-148">Número do item RM-100.</span><span class="sxs-lookup"><span data-stu-id="f115e-148">Item number RM-100.</span></span> 
-    <span data-ttu-id="f115e-149">Nº do lote B1.</span><span class="sxs-lookup"><span data-stu-id="f115e-149">Batch number B1.</span></span> 
-    <span data-ttu-id="f115e-150">Uma quantidade de 25.</span><span class="sxs-lookup"><span data-stu-id="f115e-150">A quantity of 25.</span></span>

7.  <span data-ttu-id="f115e-151">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f115e-151">Select **OK**.</span></span>

<span data-ttu-id="f115e-152">Observe que a mensagem "Linha do diário criada" aparece no visor.</span><span class="sxs-lookup"><span data-stu-id="f115e-152">Note that the message "Journal line is created" appears on the display.</span></span> <span data-ttu-id="f115e-153">Na ordem de produção há um diário aberto do tipo **Lista de separação da produção** para o número de item RM-100 e o número de lote B1.</span><span class="sxs-lookup"><span data-stu-id="f115e-153">On the production order there is an open journal of the type **Production picking list** for item number RM-100 and batch number B1.</span></span> 

<span data-ttu-id="f115e-154">Agora você pode escolher continuar o registro, por exemplo, o número de lote B2, e toda vez que você selecionar **OK,** uma nova linha de diário será adicionada ao diário aberto.</span><span class="sxs-lookup"><span data-stu-id="f115e-154">You can now choose to continue your registration, for example on batch number B2, and each time you select **OK,** a new journal line is added to the open journal.</span></span> 

<span data-ttu-id="f115e-155">Após concluir o registro, selecione **Feito** para lançar o diário e termine o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f115e-155">After you have finished your registration, select **Done** to post the journal and end the workflow.</span></span>

### <a name="additional-comments"></a><span data-ttu-id="f115e-156">Comentários adicionais</span><span class="sxs-lookup"><span data-stu-id="f115e-156">Additional comments</span></span> 

-   <span data-ttu-id="f115e-157">Se um usuário cancelar o fluxo de trabalho após a criação de uma linha de diário, o diário fica em um estado não posicionado, mas se o usuário em um ponto posterior usar o fluxo de trabalho para a mesma ordem de produção, as linhas serão adicionadas ao diário aberto, em vez de um novo diário.</span><span class="sxs-lookup"><span data-stu-id="f115e-157">If a user cancels the workflow after a journal line is created, the journal is in an unposted state but if the user at a later point uses the workflow for the same production order, then the lines will be added to the open journal rather than to a new journal.</span></span>
-   <span data-ttu-id="f115e-158">O novo fluxo de trabalho também suporta o registro de números de série.</span><span class="sxs-lookup"><span data-stu-id="f115e-158">The new workflow also supports the registration of serial numbers.</span></span>
-   <span data-ttu-id="f115e-159">Só é possível registrar um número de item definido na lista de materiais ou na fórmula para a ordem de produção selecionada ou a ordem do lote.</span><span class="sxs-lookup"><span data-stu-id="f115e-159">It is only possible to register an item number that is defined in the bill of material or in the formula for the selected production order or batch order.</span></span>
-   <span data-ttu-id="f115e-160">O material pode ser consumido em excesso.</span><span class="sxs-lookup"><span data-stu-id="f115e-160">Material can be overconsumed.</span></span> <span data-ttu-id="f115e-161">Por exemplo, se for estimado que o material será consumido com a quantidade de 100 libras, então pode ser consumido em excesso com uma quantidade de, por exemplo, 105 libras.</span><span class="sxs-lookup"><span data-stu-id="f115e-161">For example, if the material is estimated to be consumed with the quantity of 100 lbs, then it can be overconsumed with a quantity of, for example, 105 lbs.</span></span>



