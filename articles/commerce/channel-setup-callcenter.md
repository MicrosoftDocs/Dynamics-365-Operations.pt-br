---
title: Configurar um canal de call center
description: Este tópico descreve como criar um novo canal de call center no Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 42448bd54c00b8642b158f422e17d2b46ee25579
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057870"
---
# <a name="set-up-a-call-center-channel"></a><span data-ttu-id="9f5a5-103">Configurar um canal de call center</span><span class="sxs-lookup"><span data-stu-id="9f5a5-103">Set up a call center channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="9f5a5-104">Este tópico descreve como criar um novo canal de call center no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-104">This topic describes how to create a new call center channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9f5a5-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="9f5a5-105">Overview</span></span>

<span data-ttu-id="9f5a5-106">No Dynamics 365 Commerce, call center é um tipo de canal que pode ser definido no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-106">In Dynamics 365 Commerce, a call center is a type of channel that can be defined in the application.</span></span> <span data-ttu-id="9f5a5-107">Definir um canal para as entidades de call center permite que o sistema vincule dados e padrões de processamento de ordens específicos a ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-107">Defining a channel for your call center entities allows the system to tie specific data and order processing defaults to sales orders.</span></span> <span data-ttu-id="9f5a5-108">Uma empresa pode definir vários canais de call center no Commerce.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-108">A company can define multiple call center channels in Commerce.</span></span> 

<span data-ttu-id="9f5a5-109">Antes de criar um novo canal de call center, verifique se você concluiu os [Pré-requisitos de configuração de canal](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="9f5a5-109">Before you create a new call center channel, ensure that you have completed the [Channel set up prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-call-center-channel"></a><span data-ttu-id="9f5a5-110">Criar e configurar um novo canal de call center</span><span class="sxs-lookup"><span data-stu-id="9f5a5-110">Create and configure a new call center channel</span></span>

<span data-ttu-id="9f5a5-111">Para criar e configurar um novo canal de call center, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-111">To create and configure a new call center channel, follow these steps.</span></span>

1. <span data-ttu-id="9f5a5-112">No painel de navegação, vá para **Módulos \> Canais \> Call centers \> Todos os call centers**.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-112">In the navigation pane, go to **Modules \> Channels \> Call centers \> All call centers**.</span></span>
1. <span data-ttu-id="9f5a5-113">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="9f5a5-114">No campo **Nome**, forneça um nome para o novo canal.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-114">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="9f5a5-115">Selecione a **Entidade legal** apropriada na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-115">Select the appropriate **Legal entity** from the drop down.</span></span>
1. <span data-ttu-id="9f5a5-116">Selecione a localização de **Depósito** apropriada na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-116">Select the appropriate **Warehouse** location from the drop down.</span></span>
1. <span data-ttu-id="9f5a5-117">No campo **Cliente padrão**, forneça um cliente padrão válido.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-117">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="9f5a5-118">No campo **Perfil de notificação por email**, forneça um perfil de notificação por email válido.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-118">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="9f5a5-119">Forneça um código informativo de **Substituição de preço**.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-119">Provide a **Price override** info code.</span></span> <span data-ttu-id="9f5a5-120">Talvez você precise criar um código informativo para isso primeiro.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-120">Note you may need to create an info code for this first.</span></span>
1. <span data-ttu-id="9f5a5-121">Forneça um código informativo de **Código de bloqueio**.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-121">Provide a **Hold code** info code.</span></span> <span data-ttu-id="9f5a5-122">Talvez você precise criar um código informativo para isso primeiro.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-122">Note you may need to create an info code for this first.</span></span>
1. <span data-ttu-id="9f5a5-123">Forneça um código informativo de **Crédito**.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-123">Provide a **Credit** info code.</span></span> <span data-ttu-id="9f5a5-124">Talvez você precise criar um código informativo para isso primeiro.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-124">Note you may need to create an info code for this first.</span></span>
1. <span data-ttu-id="9f5a5-125">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-125">Select **Save**.</span></span>

<span data-ttu-id="9f5a5-126">A imagem a seguir mostra a criação de um novo canal de call center.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-126">The following image shows the creation of a new call center channel.</span></span>

![Novo canal de call center](media/channel-setup-callcenter-1.png)

<span data-ttu-id="9f5a5-128">A imagem a seguir mostra um exemplo de canal de call center.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-128">The following image shows an example call center channel.</span></span>

![Exemplo de canal de call center](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a><span data-ttu-id="9f5a5-130">Configuração adicional do canal</span><span class="sxs-lookup"><span data-stu-id="9f5a5-130">Additional channel setup</span></span>

<span data-ttu-id="9f5a5-131">Outras tarefas necessárias para a configuração do canal de call center incluem configurar métodos de pagamento e modos de entrega.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-131">Additional tasks required for call center channel setup include setting up payment methods and modes of delivery.</span></span>

<span data-ttu-id="9f5a5-132">A imagem a seguir mostra opções de configuração de **Modos de entrega** e **Métodos de pagamento** na guia **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-132">The following image shows **Modes of delivery** and **Payment methods** set up options on the **Set up** tab.</span></span>

![Outras ações de configuração do canal de call center](media/channel-setup-callcenter-3.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="9f5a5-134">Configurar métodos de pagamento</span><span class="sxs-lookup"><span data-stu-id="9f5a5-134">Set up payment methods</span></span>

<span data-ttu-id="9f5a5-135">Para configurar métodos de pagamento, siga estas etapas para cada tipo de pagamento com suporte neste canal.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-135">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="9f5a5-136">No painel de ação, selecione a guia **Configurar** e, depois, **Métodos de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-136">On the action pane, select the **Set up** tab, and then select **Payment methods**.</span></span>
1. <span data-ttu-id="9f5a5-137">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-137">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="9f5a5-138">No painel de navegação, selecione o método de pagamento desejado.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-138">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="9f5a5-139">Na seção **Geral**, forneça um **Nome de operação** e defina quaisquer outras configurações desejadas.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-139">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="9f5a5-140">Defina as configurações adicionais necessárias para o tipo de pagamento.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-140">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="9f5a5-141">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-141">On the action pane, select **Save**.</span></span>

<span data-ttu-id="9f5a5-142">A imagem a seguir mostra um exemplo de método de pagamento à vista.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-142">The following image shows an example of a cash payment method.</span></span>

![Exemplo de métodos de pagamento](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="9f5a5-144">Configurar os modos de entrega</span><span class="sxs-lookup"><span data-stu-id="9f5a5-144">Set up modes of delivery</span></span>

<span data-ttu-id="9f5a5-145">Você pode ver os modos de entrega configurados selecionando **Modos de entrega** na guia **Configurar** do **Painel de ação**.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-145">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="9f5a5-146">Para alterar ou adicionar um modo de entrega, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-146">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="9f5a5-147">No painel de navegação, vá para **Módulos \> Gerenciamento de estoque \> Modos de entrega**.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-147">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="9f5a5-148">No painel de ação, selecione **Novo** para criar um novo modo de entrega ou selecione um modo existente.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-148">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="9f5a5-149">Na seção **Canais de varejo**, selecione **Adicionar linha** para adicionar o canal.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-149">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="9f5a5-150">Adicionar canais usando nós de organização em vez de adicionar cada canal individualmente pode otimizar esse processo.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-150">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="9f5a5-151">A imagem a seguir mostra um exemplo de modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="9f5a5-151">The following image shows an example of a mode of delivery.</span></span>

![Configurar os modos de entrega](media/channel-setup-retail-7.png)

## <a name="additional-resources"></a><span data-ttu-id="9f5a5-153">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="9f5a5-153">Additional resources</span></span>

[<span data-ttu-id="9f5a5-154">Pré-requisitos de configuração de canal</span><span class="sxs-lookup"><span data-stu-id="9f5a5-154">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="9f5a5-155">Funcionalidade de vendas do call center</span><span class="sxs-lookup"><span data-stu-id="9f5a5-155">Call center sales functionality</span></span>](call-center-functionality.md)

[<span data-ttu-id="9f5a5-156">Configurar opções de processamento de ordens do call center</span><span class="sxs-lookup"><span data-stu-id="9f5a5-156">Set up call center order processing options</span></span>](set-up-order-processing-options.md)

[<span data-ttu-id="9f5a5-157">Catálogos do call center</span><span class="sxs-lookup"><span data-stu-id="9f5a5-157">Call center catalogs</span></span>](call-center-catalogs.md)

[<span data-ttu-id="9f5a5-158">Configurar e trabalhar com alertas de fraude</span><span class="sxs-lookup"><span data-stu-id="9f5a5-158">Set up and work with fraud alerts</span></span>](set-up-fraud-alerts.md)

[<span data-ttu-id="9f5a5-159">Configurar programas de continuidade para call centers</span><span class="sxs-lookup"><span data-stu-id="9f5a5-159">Set up continuity programs for call centers</span></span>](set-up-continuity-program.md)
