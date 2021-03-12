---
title: Configurar um canal de call center
description: Este tópico descreve como criar um novo canal de call center no Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 03/13/2020
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
ms.openlocfilehash: b25626dafc07d576699ceba3cc9ca691db45cb9f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4997741"
---
# <a name="set-up-a-call-center-channel"></a><span data-ttu-id="57dbd-103">Configurar um canal de call center</span><span class="sxs-lookup"><span data-stu-id="57dbd-103">Set up a call center channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="57dbd-104">Este tópico descreve como criar um novo canal de call center no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="57dbd-104">This topic describes how to create a new call center channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="57dbd-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="57dbd-105">Overview</span></span>


<span data-ttu-id="57dbd-106">No Dynamics 365 Commerce, o call center é um tipo de canal do Commerce que pode ser definido no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="57dbd-106">In Dynamics 365 Commerce, a call center is a type of Commerce channel that can be defined in the application.</span></span> <span data-ttu-id="57dbd-107">Definir um canal para as entidades de call center permite que o sistema vincule dados e padrões de processamento de ordens específicos a ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="57dbd-107">Defining a channel for your call center entities allows the system to tie specific data and order processing defaults to sales orders.</span></span> <span data-ttu-id="57dbd-108">Embora uma empresa possa definir vários canais de call center no Commerce, é importante observar que um usuário individual pode estar vinculado apenas a um canal de call center.</span><span class="sxs-lookup"><span data-stu-id="57dbd-108">While a company can define multiple call center channels in Commerce, it is important to note that an individual user may only be linked to one call center channel.</span></span> 

<span data-ttu-id="57dbd-109">Antes de criar um novo canal de call center, verifique se você concluiu os [Pré-requisitos de configuração de canal](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="57dbd-109">Before you create a new call center channel, ensure that you have completed the [Channel setup prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-call-center-channel"></a><span data-ttu-id="57dbd-110">Criar e configurar um novo canal de call center</span><span class="sxs-lookup"><span data-stu-id="57dbd-110">Create and configure a new call center channel</span></span>

<span data-ttu-id="57dbd-111">Para criar e configurar um novo canal de call center, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="57dbd-111">To create and configure a new call center channel, follow these steps.</span></span>

1. <span data-ttu-id="57dbd-112">No painel de navegação, acesse **Varejo e Comércio \> Canais \> Call centers \> Todos os call centers**.</span><span class="sxs-lookup"><span data-stu-id="57dbd-112">In the navigation pane, go to **Retail and Commerce \> Channels \> Call centers \> All call centers**.</span></span>
1. <span data-ttu-id="57dbd-113">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="57dbd-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="57dbd-114">No campo **Nome**, forneça um nome para o novo canal.</span><span class="sxs-lookup"><span data-stu-id="57dbd-114">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="57dbd-115">Selecione a **Entidade legal** apropriada na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="57dbd-115">Select the appropriate **Legal entity** from the drop-down.</span></span>
1. <span data-ttu-id="57dbd-116">Selecione a localização de **Depósito** apropriada na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="57dbd-116">Select the appropriate **Warehouse** location from the drop-down.</span></span> <span data-ttu-id="57dbd-117">Esse local será usado como padrão nas ordens de venda criadas para esse canal de call center, a menos que outros padrões tenham sido definidos no nível do cliente ou do item.</span><span class="sxs-lookup"><span data-stu-id="57dbd-117">This location will be used as the default on sales orders created for this call center channel, unless other defaults have been defined at the customer or item level.</span></span>
1. <span data-ttu-id="57dbd-118">No campo **Cliente padrão**, forneça um cliente padrão válido.</span><span class="sxs-lookup"><span data-stu-id="57dbd-118">In the **Default customer** field, provide a valid default customer.</span></span> <span data-ttu-id="57dbd-119">Esses dados são usados para auxiliar no preenchimento automático de padrões quando novos registros de clientes são criados.</span><span class="sxs-lookup"><span data-stu-id="57dbd-119">This data is used to assist in autopopulating defaults when new customer records are created.</span></span> <span data-ttu-id="57dbd-120">Ao criar ordens de call center, não é aconselhável criar ordens para o cliente padrão.</span><span class="sxs-lookup"><span data-stu-id="57dbd-120">When creating call center orders, it is not advisable to create orders for the default customer.</span></span>
1. <span data-ttu-id="57dbd-121">No campo **Perfil de notificação por email**, forneça um perfil de notificação por email válido.</span><span class="sxs-lookup"><span data-stu-id="57dbd-121">In the **Email notification profile** field, provide a valid email notification profile.</span></span> <span data-ttu-id="57dbd-122">À medida que as ordens de call center são criadas e processadas, o perfil de notificação por email é usado para acionar alertas automáticos por email aos clientes com informações sobre o status da ordem.</span><span class="sxs-lookup"><span data-stu-id="57dbd-122">As call center orders are created and processed, the email notification profile is used to trigger automated email alerts to customers with information about their order status.</span></span>
1. <span data-ttu-id="57dbd-123">Forneça um código informativo de **Substituição de preço**.</span><span class="sxs-lookup"><span data-stu-id="57dbd-123">Provide a **Price override** info code.</span></span> <span data-ttu-id="57dbd-124">Talvez você precise criar um código informativo para isso primeiro.</span><span class="sxs-lookup"><span data-stu-id="57dbd-124">You may need to create an info code for this first.</span></span> <span data-ttu-id="57dbd-125">Esse código de informações fornece o conjunto de códigos de motivo que o usuário será solicitado a escolher ao usar a funcionalidade de substituição de preço em uma ordem de call center.</span><span class="sxs-lookup"><span data-stu-id="57dbd-125">This info code provides the set of reason codes that the user will be prompted to choose from when using the price override functionality on a call center order.</span></span>
1. <span data-ttu-id="57dbd-126">Forneça um código informativo de **Código de bloqueio**.</span><span class="sxs-lookup"><span data-stu-id="57dbd-126">Provide a **Hold code** info code.</span></span> <span data-ttu-id="57dbd-127">Talvez você precise criar um código informativo para isso primeiro.</span><span class="sxs-lookup"><span data-stu-id="57dbd-127">You may need to create an info code for this first.</span></span> <span data-ttu-id="57dbd-128">Esse código de informações fornece o conjunto de códigos de motivo opcionais que o usuário será solicitado a escolher ao fazer uma ordem em espera.</span><span class="sxs-lookup"><span data-stu-id="57dbd-128">This info code provides the set of optional reason codes that the user will be prompted to choose from when placing an order on hold.</span></span>
1. <span data-ttu-id="57dbd-129">Forneça um código informativo de **Crédito**.</span><span class="sxs-lookup"><span data-stu-id="57dbd-129">Provide a **Credit** info code.</span></span> <span data-ttu-id="57dbd-130">Talvez você precise criar um código informativo para isso primeiro.</span><span class="sxs-lookup"><span data-stu-id="57dbd-130">You may need to create an info code for this first.</span></span> <span data-ttu-id="57dbd-131">Esse código de informações fornece o conjunto de códigos de motivo que o usuário pode escolher ao usar a funcionalidade de crédito de ordem do call center para fornecer reembolsos diversos ao cliente por motivos de atendimento ao cliente.</span><span class="sxs-lookup"><span data-stu-id="57dbd-131">This info code provides the set of reason codes that the user can choose from when using the order credit functionality of call center to give misc refunds to the customer for customer service reasons.</span></span>
1. <span data-ttu-id="57dbd-132">Opcional: configure dimensões financeiras na FastTab **Dimensões financeiras**.</span><span class="sxs-lookup"><span data-stu-id="57dbd-132">Optional: set up financial dimensions on the **Financial dimensions** FastTab.</span></span> <span data-ttu-id="57dbd-133">As dimensões inseridas aqui serão padronizadas em qualquer ordem de venda criada neste canal de call center.</span><span class="sxs-lookup"><span data-stu-id="57dbd-133">The dimensions entered here will default on any sales order created in this call center channel.</span></span>
1. <span data-ttu-id="57dbd-134">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="57dbd-134">Click **Save**.</span></span>

<span data-ttu-id="57dbd-135">A imagem a seguir mostra a criação de um novo canal de call center.</span><span class="sxs-lookup"><span data-stu-id="57dbd-135">The following image shows the creation of a new call center channel.</span></span>

![Novo canal de call center](media/channel-setup-callcenter-1.png)

<span data-ttu-id="57dbd-137">A imagem a seguir mostra um exemplo de canal de call center.</span><span class="sxs-lookup"><span data-stu-id="57dbd-137">The following image shows an example call center channel.</span></span>

![Exemplo de canal de call center](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a><span data-ttu-id="57dbd-139">Configuração adicional do canal</span><span class="sxs-lookup"><span data-stu-id="57dbd-139">Additional channel setup</span></span>

<span data-ttu-id="57dbd-140">Outras tarefas necessárias para a configuração do canal de call center incluem configurar métodos de pagamento e modos de entrega.</span><span class="sxs-lookup"><span data-stu-id="57dbd-140">Additional tasks required for call center channel setup include setting up payment methods and modes of delivery.</span></span>

<span data-ttu-id="57dbd-141">A imagem a seguir mostra opções de configuração de **Modos de entrega** e **Métodos de pagamento** na guia **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="57dbd-141">The following image shows **Modes of delivery** and **Payment methods** setup options on the **Set up** tab.</span></span>

![Outras ações de configuração do canal de call center](media/channel-setup-callcenter-3.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="57dbd-143">Configurar métodos de pagamento</span><span class="sxs-lookup"><span data-stu-id="57dbd-143">Set up payment methods</span></span>

<span data-ttu-id="57dbd-144">Para configurar métodos de pagamento, siga as etapas a seguir para cada tipo de pagamento com suporte neste canal.</span><span class="sxs-lookup"><span data-stu-id="57dbd-144">To set up payment methods, follow these steps for each payment type supported on this channel.</span></span> <span data-ttu-id="57dbd-145">Os usuários deverão selecionar métodos de pagamento predefinidos para vinculá-los ao canal de call center.</span><span class="sxs-lookup"><span data-stu-id="57dbd-145">Users will be required to select from pre-defined payment methods to link them to the call center channel.</span></span> <span data-ttu-id="57dbd-146">Antes de configurar os métodos de pagamento do seu call center, primeiro configure os métodos de pagamento principais em **Varejo e Comércio \> Configuração de canal \> Métodos de pagamento \> Métodos de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="57dbd-146">Before setting up your call center payment methods, first set up your master methods of payment in **Retail and Commerce \> Channel setup \> Payment methods \> Payment methods**.</span></span>

1. <span data-ttu-id="57dbd-147">No painel de ação, selecione a guia **Configurar** e, depois, **Métodos de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="57dbd-147">On the action pane, select the **Set up** tab, and then select **Payment methods**.</span></span>
1. <span data-ttu-id="57dbd-148">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="57dbd-148">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="57dbd-149">No painel de navegação, selecione um método de pagamento entre os pagamentos predefinidos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="57dbd-149">In the navigation pane, select a payment method from the pre-defined payments available.</span></span>
1. <span data-ttu-id="57dbd-150">Defina as configurações adicionais necessárias para o tipo de pagamento.</span><span class="sxs-lookup"><span data-stu-id="57dbd-150">Configure any additional settings as required for the payment type.</span></span> <span data-ttu-id="57dbd-151">Para cartões de crédito, cartões-presente ou cartões de fidelidade, é necessária uma configuração adicional selecionando a função **Configuração do cartão**.</span><span class="sxs-lookup"><span data-stu-id="57dbd-151">For credit cards, gift cards, or loyalty cards, additional setup is required by selecting the **Card setup** function.</span></span> 
1. <span data-ttu-id="57dbd-152">Configure as contas de lançamento adequadas para o tipo de pagamento na seção **Lançamento**.</span><span class="sxs-lookup"><span data-stu-id="57dbd-152">Configure proper posting accounts for the payment type in the **Posting** section.</span></span>
1. <span data-ttu-id="57dbd-153">No painel de ações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="57dbd-153">On the action pane, click **Save**.</span></span>

<span data-ttu-id="57dbd-154">A imagem a seguir mostra um exemplo de método de pagamento à vista.</span><span class="sxs-lookup"><span data-stu-id="57dbd-154">The following image shows an example of a cash payment method.</span></span>

![Exemplo de métodos de pagamento](media/channel-setup-callcenter-payments.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="57dbd-156">Configurar os modos de entrega</span><span class="sxs-lookup"><span data-stu-id="57dbd-156">Set up modes of delivery</span></span>

<span data-ttu-id="57dbd-157">Você pode ver os modos de entrega configurados selecionando **Modos de entrega** na guia **Configurar** do **Painel de ação**.</span><span class="sxs-lookup"><span data-stu-id="57dbd-157">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="57dbd-158">Para alterar ou adicionar um modo de entrega a ser associado ao canal de call center, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="57dbd-158">To change or add a mode of delivery to be associated to the call center channel, follow these steps.</span></span>

1. <span data-ttu-id="57dbd-159">No formulário de modos de entrega de call center, selecione **Gerenciar modos de entrega**</span><span class="sxs-lookup"><span data-stu-id="57dbd-159">From the Call center modes of delivery form, select **Manage modes of delivery**</span></span>
1. <span data-ttu-id="57dbd-160">No painel de ação, selecione **Novo** para criar um novo modo de entrega ou selecione um modo existente.</span><span class="sxs-lookup"><span data-stu-id="57dbd-160">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="57dbd-161">Na seção **Canais de varejo**, clique em **Adicionar linha** para adicionar o canal de call center.</span><span class="sxs-lookup"><span data-stu-id="57dbd-161">In the **Retail channels** section, click **Add line** to add the call center channel.</span></span> <span data-ttu-id="57dbd-162">Adicionar canais usando nós de organização em vez de adicionar cada canal individualmente pode otimizar esse processo.</span><span class="sxs-lookup"><span data-stu-id="57dbd-162">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>
1. <span data-ttu-id="57dbd-163">Verifique se o modo de entrega foi configurado com os dados na FastTab **Produtos** e FastTab **Endereços**.</span><span class="sxs-lookup"><span data-stu-id="57dbd-163">Ensure the mode of delivery has been configured with data on the **Products** FastTab and the **Addresses** FastTab.</span></span> <span data-ttu-id="57dbd-164">Se nenhum produto ou endereço de entrega for válido para o modo de entrega, a escolha durante a entrada de ordem resultará em erros.</span><span class="sxs-lookup"><span data-stu-id="57dbd-164">If no products or delivery addresses are valid for the mode of delivery, choosing it during order entry will result in errors.</span></span>
1. <span data-ttu-id="57dbd-165">Após a alteração das configurações do modo de entrega de call center, o trabalho **Processar modos de entrega** deve ser executado para explodir a matriz de alterações.</span><span class="sxs-lookup"><span data-stu-id="57dbd-165">After any changes have been made to the call center mode of delivery configurations, the **Process delivery modes** job must be run to explode the change matrix.</span></span> <span data-ttu-id="57dbd-166">Esse trabalho pode ser encontrado em **Varejo e Comércio \> TI de Varejo e Comércio \> Processar modos de entrega**.</span><span class="sxs-lookup"><span data-stu-id="57dbd-166">This job can be found by navigating to **Retail and Commerce \> Retail and Commerce IT \> Process delivery modes**.</span></span>

<span data-ttu-id="57dbd-167">A imagem a seguir mostra um exemplo de modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="57dbd-167">The following image shows an example of a mode of delivery.</span></span>

![Configurar os modos de entrega](media/channel-setup-retail-7.png)

### <a name="set-up-channel-users"></a><span data-ttu-id="57dbd-169">Configurar usuários do canal</span><span class="sxs-lookup"><span data-stu-id="57dbd-169">Set up channel users</span></span>

<span data-ttu-id="57dbd-170">Para criar uma ordem de venda que esteja vinculada ao canal de call center da sede do Commerce, o usuário que criar a ordem de venda deverá estar vinculada ao canal de call center.</span><span class="sxs-lookup"><span data-stu-id="57dbd-170">To create a sales order that is linked to the call center channel from Commerce Headquarters, the user creating the sales order must be linked to the call center channel.</span></span> <span data-ttu-id="57dbd-171">O usuário não poderá vincular manualmente uma ordem de venda criada na sede do Commerce ao canal de call center.</span><span class="sxs-lookup"><span data-stu-id="57dbd-171">The user cannot manually link a sales order created in Commerce Headquarters to the call center channel.</span></span> <span data-ttu-id="57dbd-172">O link é sistemático e baseado no usuário e no relacionamento do usuário com o canal de call center.</span><span class="sxs-lookup"><span data-stu-id="57dbd-172">The link is systematic, and is based on the user and the user's relationship to the call center channel.</span></span> <span data-ttu-id="57dbd-173">Um usuário pode estar vinculado apenas a um canal de call center.</span><span class="sxs-lookup"><span data-stu-id="57dbd-173">A user may only be linked to one call center channel.</span></span>

1. <span data-ttu-id="57dbd-174">No painel de ação, selecione a guia **Canal** e, depois, **Usuários do canal**.</span><span class="sxs-lookup"><span data-stu-id="57dbd-174">On the action pane, select the **Channel** tab, and then select **Channel users**.</span></span>
1. <span data-ttu-id="57dbd-175">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="57dbd-175">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="57dbd-176">Escolha uma **ID do Usuário** existente na lista de seleção suspensa para vincular esse usuário ao canal de call center</span><span class="sxs-lookup"><span data-stu-id="57dbd-176">Choose an existing **User ID** from the dropdown selection list to link this user to the call center channel</span></span>

<span data-ttu-id="57dbd-177">Depois que a configuração do usuário do canal for concluída e o usuário criar uma ordem de venda na sede do Commerce, a ordem do cliente será vinculada ao canal de call center associado.</span><span class="sxs-lookup"><span data-stu-id="57dbd-177">After the channel user setup is done and the user creates a new sales order in Commerce Headquarters, the sales order will be linked to their associated call center channel.</span></span> <span data-ttu-id="57dbd-178">Quaisquer configurações desse canal serão aplicadas sistematicamente à ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="57dbd-178">Any configurations for this channel will be applied systematically to the sales order.</span></span> <span data-ttu-id="57dbd-179">Um usuário pode confirmar a qual canal de call center a ordem de venda está vinculada, visualizando a referência do nome do canal no cabeçalho da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="57dbd-179">A user can confirm which call center channel the sales order is linked to by viewing the channel name reference on the sales order header.</span></span>


### <a name="set-up-price-groups"></a><span data-ttu-id="57dbd-180">Configurar grupos de preços</span><span class="sxs-lookup"><span data-stu-id="57dbd-180">Set up price groups</span></span>

<span data-ttu-id="57dbd-181">Os grupos de preços são opcionais, mas, se usados, podem controlar quais preços de venda serão oferecidos aos clientes que fazem ordens no canal de call center.</span><span class="sxs-lookup"><span data-stu-id="57dbd-181">Price groups are optional, but if used, can control which sales prices will be offered to customers placing orders in the call center channel.</span></span> <span data-ttu-id="57dbd-182">Se um grupo de preços não tiver sido configurado para o cliente ou se os grupos de preços do catálogo não estiverem sendo aplicados à ordem de venda (usando o campo **ID do código-fonte** no cabeçalho da ordem de call center), o grupo de preços do canal é usado para localizar preços de itens.</span><span class="sxs-lookup"><span data-stu-id="57dbd-182">If a price group has not been configured for the customer, or if catalog price groups are not being applied to the sales order (using the **Source code ID** field on the call center order header), then the channel price group is used to locate item prices.</span></span> <span data-ttu-id="57dbd-183">Se um grupo de preços não for encontrado no canal de call center, os preços padrão do item mestre serão usados.</span><span class="sxs-lookup"><span data-stu-id="57dbd-183">If a price group is not found on the call center channel, the default item master prices are used.</span></span> 

<span data-ttu-id="57dbd-184">Para configurar um grupo de preços, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="57dbd-184">To set up a price group, do the following.</span></span>

1. <span data-ttu-id="57dbd-185">No painel de ação, clique na guia **Canal** e selecione **Grupos de preços**.</span><span class="sxs-lookup"><span data-stu-id="57dbd-185">On the action pane, click the **Channel** tab, and then select **Price groups**.</span></span>
1. <span data-ttu-id="57dbd-186">No painel de ações, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="57dbd-186">On the action pane, click **New**.</span></span>
1. <span data-ttu-id="57dbd-187">Selecione um **Grupo de preços de varejo** na lista de seleção suspensa.</span><span class="sxs-lookup"><span data-stu-id="57dbd-187">Select a **Retail price group** from the dropdown selection list.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="57dbd-188">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="57dbd-188">Additional resources</span></span>

[<span data-ttu-id="57dbd-189">Pré-requisitos de configuração de canal</span><span class="sxs-lookup"><span data-stu-id="57dbd-189">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="57dbd-190">Funcionalidade de vendas do call center</span><span class="sxs-lookup"><span data-stu-id="57dbd-190">Call center sales functionality</span></span>](call-center-functionality.md)

[<span data-ttu-id="57dbd-191">Configurar opções de processamento de ordens do call center</span><span class="sxs-lookup"><span data-stu-id="57dbd-191">Set up call center order processing options</span></span>](set-up-order-processing-options.md)

[<span data-ttu-id="57dbd-192">Catálogos do call center</span><span class="sxs-lookup"><span data-stu-id="57dbd-192">Call center catalogs</span></span>](call-center-catalogs.md)

[<span data-ttu-id="57dbd-193">Configurar e trabalhar com alertas de fraude</span><span class="sxs-lookup"><span data-stu-id="57dbd-193">Set up and work with fraud alerts</span></span>](set-up-fraud-alerts.md)

[<span data-ttu-id="57dbd-194">Configurar programas de continuidade para call centers</span><span class="sxs-lookup"><span data-stu-id="57dbd-194">Set up continuity programs for call centers</span></span>](set-up-continuity-program.md)
