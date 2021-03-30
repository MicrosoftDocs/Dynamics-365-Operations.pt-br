---
title: Configurar um canal online
description: Este tópico descreve como criar um novo canal online no Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 44cc63560c048031c8315dc3f15ef07583bdc266
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5218336"
---
# <a name="set-up-an-online-channel"></a><span data-ttu-id="c5302-103">Configurar um canal online</span><span class="sxs-lookup"><span data-stu-id="c5302-103">Set up an online channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="c5302-104">Este tópico descreve como criar um novo canal online no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c5302-104">This topic describes how to create a new online channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c5302-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="c5302-105">Overview</span></span>

<span data-ttu-id="c5302-106">O Dynamics 365 Commerce oferece suporte a vários canais de varejo.</span><span class="sxs-lookup"><span data-stu-id="c5302-106">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="c5302-107">Esses canais de varejo incluem lojas online, call centers e lojas de varejo (também chamadas de lojas tradicionais).</span><span class="sxs-lookup"><span data-stu-id="c5302-107">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="c5302-108">As lojas online oferecem aos clientes a opção de comprar produtos na loja online do varejista, além das lojas físicas.</span><span class="sxs-lookup"><span data-stu-id="c5302-108">Online stores give customers the option of purchasing products from the retailer's online store in addition to its retail stores.</span></span>

<span data-ttu-id="c5302-109">Para criar uma loja online no Commerce, primeiro você deve criar um canal online.</span><span class="sxs-lookup"><span data-stu-id="c5302-109">To create an online store in Commerce, you must first create an online channel.</span></span> <span data-ttu-id="c5302-110">Antes de criar um novo canal online, verifique se você concluiu os [Pré-requisitos de configuração de canal](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="c5302-110">Before you create a new online channel, ensure that you have completed the [Channel set up prerequisites](channels-prerequisites.md).</span></span>

<span data-ttu-id="c5302-111">Antes de criar um novo site, crie pelo menos uma loja online no Commerce.</span><span class="sxs-lookup"><span data-stu-id="c5302-111">Before you can create a new site, at least one online store must be created in Commerce.</span></span> <span data-ttu-id="c5302-112">Para obter mais informações, consulte [Criar um site de comércio eletrônico](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="c5302-112">For more information, see [Create an e-Commerce site](create-ecommerce-site.md).</span></span>

## <a name="create-and-configure-a-new-online-channel"></a><span data-ttu-id="c5302-113">Criar e configurar um novo canal online</span><span class="sxs-lookup"><span data-stu-id="c5302-113">Create and configure a new online channel</span></span>

<span data-ttu-id="c5302-114">Para criar e configurar um novo canal online, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c5302-114">To create and configure a new online channel, follow these steps.</span></span>

1. <span data-ttu-id="c5302-115">No painel de navegação, vá para **Módulos \> Canais \> Lojas Online**.</span><span class="sxs-lookup"><span data-stu-id="c5302-115">In the navigation pane, go to **Modules \> Channels \> Online Stores**.</span></span>
1. <span data-ttu-id="c5302-116">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c5302-116">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="c5302-117">No campo **Nome**, forneça um nome para o novo canal.</span><span class="sxs-lookup"><span data-stu-id="c5302-117">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="c5302-118">Na lista suspensa **Entidade legal**, insira a entidade legal apropriada.</span><span class="sxs-lookup"><span data-stu-id="c5302-118">In the **Legal entity** drop-down, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="c5302-119">Na lista suspensa **Depósito**, insira o depósito apropriado.</span><span class="sxs-lookup"><span data-stu-id="c5302-119">In the **Warehouse** drop-down, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="c5302-120">No campo **Fuso horário da loja**, selecione o fuso horário apropriado.</span><span class="sxs-lookup"><span data-stu-id="c5302-120">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="c5302-121">No campo **Moeda**, selecione a moeda apropriada.</span><span class="sxs-lookup"><span data-stu-id="c5302-121">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="c5302-122">No campo **Cliente padrão**, forneça um cliente padrão válido.</span><span class="sxs-lookup"><span data-stu-id="c5302-122">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="c5302-123">No campo **Catálogo de endereços do cliente**, forneça um catálogo de endereços válido.</span><span class="sxs-lookup"><span data-stu-id="c5302-123">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="c5302-124">No campo **Perfil de funcionalidade**, selecione um perfil de funcionalidade se aplicável.</span><span class="sxs-lookup"><span data-stu-id="c5302-124">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="c5302-125">No campo **Perfil de notificação por email**, forneça um perfil de notificação por email válido.</span><span class="sxs-lookup"><span data-stu-id="c5302-125">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="c5302-126">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c5302-126">On the action pane, select **Save**.</span></span>

<span data-ttu-id="c5302-127">A imagem a seguir mostra a criação de um novo canal online.</span><span class="sxs-lookup"><span data-stu-id="c5302-127">The following image shows the creation of a new online channel.</span></span>

![Novo canal online](media/channel-setup-online-1.png)

<span data-ttu-id="c5302-129">A imagem a seguir mostra um exemplo de canal online.</span><span class="sxs-lookup"><span data-stu-id="c5302-129">The following image shows an example online channel.</span></span>

![Exemplo de canal online](media/channel-setup-online-2.png)

## <a name="set-up-languages"></a><span data-ttu-id="c5302-131">Configurar idiomas</span><span class="sxs-lookup"><span data-stu-id="c5302-131">Set up languages</span></span>

<span data-ttu-id="c5302-132">Se o seu site de comércio eletrônico der suporte a vários idiomas, expanda a seção **Idiomas** e adicione outros idiomas conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="c5302-132">If your e-Commerce site will support multiple languages, expand the **Languages** section and add additional languages as needed.</span></span>

## <a name="set-up-payment-account"></a><span data-ttu-id="c5302-133">Configurar conta de pagamento</span><span class="sxs-lookup"><span data-stu-id="c5302-133">Set up payment account</span></span>

<span data-ttu-id="c5302-134">Na seção **Conta de pagamento**, você pode adicionar um provedor de serviço de pagamento terceirizado.</span><span class="sxs-lookup"><span data-stu-id="c5302-134">From within the **Payment account** section, you can add a third-party payment provider.</span></span> <span data-ttu-id="c5302-135">Para obter informações sobre como configurar um conector de pagamento Adyen, consulte [Conector de pagamento do Dynamics 365 para Adyen](../retail/dev-itpro/adyen-connector.md).</span><span class="sxs-lookup"><span data-stu-id="c5302-135">For information on setting up an Adyen payment connector, see [Dynamics 365 Payment Connector for Adyen](../retail/dev-itpro/adyen-connector.md).</span></span>

## <a name="additional-channel-setup"></a><span data-ttu-id="c5302-136">Configuração adicional do canal</span><span class="sxs-lookup"><span data-stu-id="c5302-136">Additional channel setup</span></span>

<span data-ttu-id="c5302-137">Outras tarefas que são necessárias para a configuração do canal online incluem configurar métodos de pagamento, modos de entrega e a atribuição de grupo de orçamento.</span><span class="sxs-lookup"><span data-stu-id="c5302-137">Additional tasks that are required for online channel setup include setting up payment methods, modes of delivery, and the fulfillment group assignment.</span></span>

<span data-ttu-id="c5302-138">A imagem a seguir mostra opções de configuração de **Modos de entrega**, **Métodos de pagamento** e **Atribuição de grupo de orçamento** na guia **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="c5302-138">The following image shows **Modes of delivery**, **Payment methods**, and **Fulfillment group assignment** setup options on the **Set up** tab.</span></span>

![Outras ações de configuração do canal online](media/channel-setup-online-3.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="c5302-140">Configurar métodos de pagamento</span><span class="sxs-lookup"><span data-stu-id="c5302-140">Set up payment methods</span></span>

<span data-ttu-id="c5302-141">Para configurar métodos de pagamento, siga estas etapas para cada tipo de pagamento com suporte neste canal.</span><span class="sxs-lookup"><span data-stu-id="c5302-141">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="c5302-142">No painel de ação, selecione a guia **Configurar** e, depois, **Métodos de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="c5302-142">On the action pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="c5302-143">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c5302-143">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="c5302-144">No painel de navegação, selecione o método de pagamento desejado.</span><span class="sxs-lookup"><span data-stu-id="c5302-144">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="c5302-145">Na seção **Geral**, forneça um **Nome de operação** e defina quaisquer outras configurações desejadas.</span><span class="sxs-lookup"><span data-stu-id="c5302-145">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="c5302-146">Defina as configurações adicionais necessárias para o tipo de pagamento.</span><span class="sxs-lookup"><span data-stu-id="c5302-146">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="c5302-147">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c5302-147">On the action pane, select **Save**.</span></span>

<span data-ttu-id="c5302-148">A imagem a seguir mostra um exemplo de método de pagamento à vista.</span><span class="sxs-lookup"><span data-stu-id="c5302-148">The following image shows an example of a cash payment method.</span></span>

![Exemplo de métodos de pagamento](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="c5302-150">Configurar os modos de entrega</span><span class="sxs-lookup"><span data-stu-id="c5302-150">Set up modes of delivery</span></span>

<span data-ttu-id="c5302-151">Você pode ver os modos de entrega configurados selecionando **Modos de entrega** na guia **Configurar** do **Painel de ação**.</span><span class="sxs-lookup"><span data-stu-id="c5302-151">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="c5302-152">Para alterar ou adicionar um modo de entrega, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c5302-152">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="c5302-153">No painel de navegação, vá para **Módulos \> Gerenciamento de estoque \> Modos de entrega**.</span><span class="sxs-lookup"><span data-stu-id="c5302-153">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="c5302-154">No painel de ação, selecione **Novo** para criar um novo modo de entrega ou selecione um modo existente.</span><span class="sxs-lookup"><span data-stu-id="c5302-154">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="c5302-155">Na seção **Canais de varejo**, selecione **Adicionar linha** para adicionar o canal.</span><span class="sxs-lookup"><span data-stu-id="c5302-155">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="c5302-156">Adicionar canais usando nós de organização em vez de adicionar cada canal individualmente pode otimizar esse processo.</span><span class="sxs-lookup"><span data-stu-id="c5302-156">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="c5302-157">A imagem a seguir mostra um exemplo de modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="c5302-157">The following image shows an example of a mode of delivery.</span></span>

![Configurar os modos de entrega](media/channel-setup-retail-7.png)

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="c5302-159">Configurar uma atribuição de grupo de orçamento</span><span class="sxs-lookup"><span data-stu-id="c5302-159">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="c5302-160">Para configurar uma atribuição de grupo de orçamento, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c5302-160">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="c5302-161">No painel de ação, selecione a guia **Configurar** e, depois, **Atribuição de grupo de orçamento**.</span><span class="sxs-lookup"><span data-stu-id="c5302-161">On the action pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="c5302-162">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c5302-162">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="c5302-163">Na lista suspensa **Grupo de orçamento**, selecione um grupo de orçamento.</span><span class="sxs-lookup"><span data-stu-id="c5302-163">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="c5302-164">Na lista suspensa **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="c5302-164">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="c5302-165">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c5302-165">On the action pane, select **Save**.</span></span>

<span data-ttu-id="c5302-166">A imagem a seguir mostra um exemplo de configuração de atribuição de grupo de orçamento.</span><span class="sxs-lookup"><span data-stu-id="c5302-166">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Configurar atribuição de grupo de orçamento](media/channel-setup-retail-9.png)

## <a name="additional-resources"></a><span data-ttu-id="c5302-168">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="c5302-168">Additional resources</span></span>

[<span data-ttu-id="c5302-169">Visão geral de canais</span><span class="sxs-lookup"><span data-stu-id="c5302-169">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="c5302-170">Pré-requisitos de configuração de canal</span><span class="sxs-lookup"><span data-stu-id="c5302-170">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="c5302-171">Configurar um canal de varejo</span><span class="sxs-lookup"><span data-stu-id="c5302-171">Set up a retail channel</span></span>](channel-setup-retail.md)

[<span data-ttu-id="c5302-172">Configurar um canal de call center</span><span class="sxs-lookup"><span data-stu-id="c5302-172">Set up a call center channel</span></span>](channel-setup-callcenter.md)

[<span data-ttu-id="c5302-173">Conector de Pagamento do Dynamics 365 para Adyen</span><span class="sxs-lookup"><span data-stu-id="c5302-173">Dynamics 365 Payment Connector for Adyen</span></span>](../retail/dev-itpro/adyen-connector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]